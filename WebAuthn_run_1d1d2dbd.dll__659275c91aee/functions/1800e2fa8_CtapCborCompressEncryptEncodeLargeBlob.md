# CtapCborCompressEncryptEncodeLargeBlob

- ea: `0x1800e2fa8`
- end: `0x1800e3287`
- name: `CtapCborCompressEncryptEncodeLargeBlob`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e36b4`

## callees

- `0x180007f90`
- `0x18001cd78`
- `0x18002bbf4`
- `0x1800537a4`
- `0x1800d3da4`
- `0x1800e2fa8`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e30a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e313d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e30a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e313d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800e3123`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800e3123`
- `bcrypt!BCryptDestroyKey` at `0x1800e3257`
- `bcrypt!BCryptDestroyKey` at `0x1800e3257`
- `bcrypt!BCryptEncrypt` at `0x1800e31dc`
- `bcrypt!BCryptEncrypt` at `0x1800e31dc`
- `Cabinet!__imp_CreateCompressor` at `0x1800e3052`
- `Cabinet!__imp_CreateCompressor` at `0x1800e3052`
- `Cabinet!__imp_Compress` at `0x1800e3085`
- `Cabinet!__imp_Compress` at `0x1800e30db`
- `Cabinet!__imp_Compress` at `0x1800e3085`
- `Cabinet!__imp_Compress` at `0x1800e30db`
- `Cabinet!__imp_CloseCompressor` at `0x1800e323f`
- `Cabinet!__imp_CloseCompressor` at `0x1800e323f`
- `CRYPTBASE!SystemFunction036` at `0x1800e3165`
- `CRYPTBASE!SystemFunction036` at `0x1800e3165`

## pseudocode

```c
__int64 __fastcall CtapCborCompressEncryptEncodeLargeBlob(
        int a1,
        UCHAR *a2,
        LONG a3,
        const BYTE *a4,
        _DWORD *a5,
        _QWORD *a6)
{
  UCHAR *v6; // rsi
  UCHAR *v7; // rbx
  BYTE *v11; // r14
  unsigned int v12; // eax
  ULONG NonzeroLastError; // ebx
  __int64 v14; // rdi
  ULONG v15; // r13d
  unsigned int v16; // eax
  LONG *dwFlags; // [rsp+30h] [rbp-D0h]
  LONG *dwFlagsa; // [rsp+30h] [rbp-D0h]
  ULONG cbOutput; // [rsp+38h] [rbp-C8h]
  ULONG cbOutputa; // [rsp+38h] [rbp-C8h]
  ULONG pcbResult; // [rsp+50h] [rbp-B0h] BYREF
  PVOID context; // [rsp+58h] [rbp-A8h] BYREF
  LONG input_used[2]; // [rsp+60h] [rbp-A0h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp-98h] BYREF
  UCHAR *v26; // [rsp+70h] [rbp-90h] BYREF
  LONG v27[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v28; // [rsp+80h] [rbp-80h]
  _DWORD *v29; // [rsp+88h] [rbp-78h]
  _DWORD v30[2]; // [rsp+90h] [rbp-70h] BYREF
  UCHAR *v31; // [rsp+98h] [rbp-68h]
  ULONG v32; // [rsp+A0h] [rbp-60h]
  int v33; // [rsp+A4h] [rbp-5Ch]
  __int64 *v34; // [rsp+A8h] [rbp-58h]
  LONG v35; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+B4h] [rbp-4Ch]
  _DWORD pPaddingInfo[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *p_RandomBuffer; // [rsp+C8h] [rbp-38h]
  ULONG v39; // [rsp+D0h] [rbp-30h]
  __int64 *v40; // [rsp+D8h] [rbp-28h]
  ULONG v41; // [rsp+E0h] [rbp-20h]
  UCHAR *v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+120h] [rbp+20h] BYREF
  int v45; // [rsp+128h] [rbp+28h]
  __int64 RandomBuffer; // [rsp+130h] [rbp+30h] BYREF
  int v47; // [rsp+138h] [rbp+38h]

  v6 = 0;
  v7 = a2;
  v26 = a2;
  v29 = a5;
  v28 = a6;
  context = 0;
  v11 = 0;
  *(_QWORD *)input_used = 0;
  *(_QWORD *)v27 = 0;
  phKey = 0;
  memset_0(pPaddingInfo, 0, 0x58u);
  *a5 = 0;
  RandomBuffer = 0;
  v47 = 0;
  v44 = 0;
  v45 = 0;
  pcbResult = 0;
  v30[1] = 0;
  v33 = 0;
  *v28 = 0;
  v36 = 0;
  if ( !(unsigned int)CreateCompressor(536870914, 0, &context) )
    goto LABEL_2;
  if ( !Compress(context, a4, a3, 0, 0, input_used, dwFlags, cbOutput) )
  {
    NonzeroLastError = _GetNonzeroLastError();
    if ( NonzeroLastError != 122 )
      goto LABEL_20;
    v11 = (BYTE *)LocalAlloc(0x40u, (unsigned int)input_used[0]);
    if ( !v11 )
      goto LABEL_2;
    v7 = v26;
  }
  if ( !Compress(context, a4, a3, v11, input_used[0], v27, dwFlagsa, cbOutputa) )
    goto LABEL_2;
  if ( a1 != 32 )
  {
    NonzeroLastError = 13;
    goto LABEL_20;
  }
  v14 = *(_QWORD *)v27 - 2LL;
  NonzeroLastError = BCryptGenerateSymmetricKey((BCRYPT_ALG_HANDLE)0x1E1, &phKey, 0, 0, v7, 0x20u, 0);
  if ( !NonzeroLastError )
  {
    v6 = (UCHAR *)LocalAlloc(0x40u, (unsigned int)(v14 + 16));
    if ( v6 )
    {
      v15 = NonzeroLastError + 12;
      LODWORD(v44) = 1651469410;
      HIDWORD(v44) = a3;
      if ( SystemFunction036(&RandomBuffer, NonzeroLastError + 12) )
      {
        p_RandomBuffer = &RandomBuffer;
        pPaddingInfo[0] = 88;
        v40 = &v44;
        pPaddingInfo[1] = 1;
        v42 = &v6[v14];
        v39 = NonzeroLastError + 12;
        v41 = NonzeroLastError + 12;
        v43 = 16;
        NonzeroLastError = BCryptEncrypt(
                             phKey,
                             v11 + 2,
                             v14,
                             pPaddingInfo,
                             0,
                             NonzeroLastError,
                             v6,
                             v14,
                             &pcbResult,
                             NonzeroLastError);
        if ( !NonzeroLastError )
        {
          if ( pcbResult == (_DWORD)v14 )
          {
            v34 = &RandomBuffer;
            v30[0] = v14 + 16;
            v31 = v6;
            v32 = v15;
            v35 = a3;
            v16 = CtapCborEncodeEncryptedLargeBlob(v30, v29, v28, &v26);
            if ( v16 )
            {
              v12 = CtapCborErrorToWin32Error(v16);
              goto LABEL_3;
            }
            NonzeroLastError = 0;
          }
          else
          {
            NonzeroLastError = -2146893792;
          }
        }
        goto LABEL_20;
      }
    }
LABEL_2:
    v12 = _GetNonzeroLastError();
LABEL_3:
    NonzeroLastError = v12;
  }
LABEL_20:
  if ( context )
    CloseCompressor();
  FidoFree(v11);
  if ( phKey )
    BCryptDestroyKey(phKey);
  FidoFree(v6);
  return NonzeroLastError;
}

```

## disassembly

```asm
0x1800e2fa8  push    rbp
0x1800e2faa  push    rbx
0x1800e2fab  push    rsi
0x1800e2fac  push    rdi
0x1800e2fad  push    r12
0x1800e2faf  push    r13
0x1800e2fb1  push    r14
0x1800e2fb3  push    r15
0x1800e2fb5  lea     rbp, [rsp-58h]
0x1800e2fba  sub     rsp, 158h
0x1800e2fc1  mov     rax, cs:__security_cookie
0x1800e2fc8  xor     rax, rsp
0x1800e2fcb  mov     [rbp+90h+var_50], rax
0x1800e2fcf  mov     rax, [rbp+90h+arg_28]
0x1800e2fd6  xor     esi, esi
0x1800e2fd8  mov     rdi, [rbp+90h+arg_20]
0x1800e2fdf  mov     rbx, rdx
0x1800e2fe2  mov     r12d, r8d
0x1800e2fe5  mov     r13d, ecx
0x1800e2fe8  mov     [rsp+190h+var_120], rdx
0x1800e2fed  lea     rcx, [rbp+90h+pPaddingInfo]; void *
0x1800e2ff1  lea     r8d, [rsi+58h]; Size
0x1800e2ff5  mov     [rbp+90h+var_108], rdi
0x1800e2ff9  xor     edx, edx; Val
0x1800e2ffb  mov     [rbp+90h+var_110], rax
0x1800e2fff  mov     r15, r9
0x1800e3002  mov     [rsp+190h+context], rsi
0x1800e3007  mov     r14d, esi
0x1800e300a  mov     qword ptr [rsp+190h+var_130], rsi
0x1800e300f  mov     qword ptr [rsp+190h+var_118], rsi
0x1800e3014  mov     [rsp+190h+phKey], rsi
0x1800e3019  call    memset_0
0x1800e301e  xor     ecx, ecx
0x1800e3020  lea     r8, [rsp+190h+context]
0x1800e3025  xor     eax, eax
0x1800e3027  mov     [rdi], ecx
0x1800e3029  mov     [rbp+90h+RandomBuffer], rax
0x1800e302d  xor     edx, edx
0x1800e302f  mov     [rbp+90h+var_58], eax
0x1800e3032  mov     [rbp+90h+var_70], rax
0x1800e3036  mov     [rbp+90h+var_68], eax
0x1800e3039  mov     rax, [rbp+90h+var_110]
0x1800e303d  mov     [rsp+190h+var_140], ecx
0x1800e3041  mov     [rbp+90h+var_FC], ecx
0x1800e3044  mov     [rbp+90h+var_EC], ecx
0x1800e3047  mov     [rax], rcx
0x1800e304a  mov     [rbp+90h+var_DC], ecx
0x1800e304d  mov     ecx, 20000002h
0x1800e3052  call    cs:__imp_CreateCompressor
0x1800e3058  test    eax, eax
0x1800e305a  jnz     short loc_1800E3068
0x1800e305c  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800e3061  mov     ebx, eax
0x1800e3063  jmp     loc_1800E3235
0x1800e3068  mov     rcx, [rsp+190h+context]; context
0x1800e306d  lea     rax, [rsp+190h+var_130]
0x1800e3072  mov     [rsp+190h+input_used], rax; input_used
0x1800e3077  xor     r9d, r9d; output_buffer
0x1800e307a  mov     r8, r12; input_buffer_size
0x1800e307d  mov     qword ptr [rsp+190h+output_buffer_size], rsi; output_buffer_size
0x1800e3082  mov     rdx, r15; input_buffer
0x1800e3085  call    cs:__imp_Compress
0x1800e308b  test    eax, eax
0x1800e308d  jnz     short loc_1800E30B9
0x1800e308f  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800e3094  mov     ebx, eax
0x1800e3096  cmp     eax, 7Ah ; 'z'
0x1800e3099  jnz     loc_1800E3235
0x1800e309f  mov     edx, [rsp+190h+var_130]; uBytes
0x1800e30a3  lea     ecx, [rax-3Ah]; uFlags
0x1800e30a6  call    cs:__imp_LocalAlloc
0x1800e30ac  mov     r14, rax
0x1800e30af  test    rax, rax
0x1800e30b2  jz      short loc_1800E305C
0x1800e30b4  mov     rbx, [rsp+190h+var_120]
0x1800e30b9  mov     rcx, [rsp+190h+context]; context
0x1800e30be  lea     rax, [rsp+190h+var_118]
0x1800e30c3  mov     [rsp+190h+input_used], rax; input_used
0x1800e30c8  mov     r9, r14; output_buffer
0x1800e30cb  mov     rax, qword ptr [rsp+190h+var_130]
0x1800e30d0  mov     r8, r12; input_buffer_size
0x1800e30d3  mov     rdx, r15; input_buffer
0x1800e30d6  mov     qword ptr [rsp+190h+output_buffer_size], rax; output_buffer_size
0x1800e30db  call    cs:__imp_Compress
0x1800e30e1  test    eax, eax
0x1800e30e3  jz      loc_1800E305C
0x1800e30e9  cmp     r13d, 20h ; ' '
0x1800e30ed  jz      short loc_1800E30F9
0x1800e30ef  mov     ebx, 0Dh
0x1800e30f4  jmp     loc_1800E3235
0x1800e30f9  mov     rdi, qword ptr [rsp+190h+var_118]
0x1800e30fe  lea     rdx, [rsp+190h+phKey]; phKey
0x1800e3103  mov     [rsp+190h+dwFlags], esi; dwFlags
0x1800e3107  xor     r9d, r9d; cbKeyObject
0x1800e310a  mov     dword ptr [rsp+190h+input_used], 20h ; ' '; cbSecret
0x1800e3112  xor     r8d, r8d; pbKeyObject
0x1800e3115  mov     ecx, 1E1h; hAlgorithm
0x1800e311a  mov     qword ptr [rsp+190h+output_buffer_size], rbx; pbSecret
0x1800e311f  add     rdi, 0FFFFFFFFFFFFFFFEh
0x1800e3123  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800e3129  mov     ebx, eax
0x1800e312b  test    eax, eax
0x1800e312d  jnz     loc_1800E3235
0x1800e3133  lea     r15d, [rdi+10h]
0x1800e3137  mov     edx, r15d; uBytes
0x1800e313a  lea     ecx, [rax+40h]; uFlags
0x1800e313d  call    cs:__imp_LocalAlloc
0x1800e3143  mov     rsi, rax
0x1800e3146  test    rax, rax
0x1800e3149  jz      loc_1800E305C
0x1800e314f  lea     r13d, [rbx+0Ch]
0x1800e3153  mov     dword ptr [rbp+90h+var_70], 626F6C62h
0x1800e315a  mov     edx, r13d; RandomBufferLength
0x1800e315d  mov     dword ptr [rbp+90h+var_70+4], r12d
0x1800e3161  lea     rcx, [rbp+90h+RandomBuffer]; RandomBuffer
0x1800e3165  call    cs:__imp_SystemFunction036
0x1800e316b  test    al, al
0x1800e316d  jz      loc_1800E305C
0x1800e3173  mov     rcx, [rsp+190h+phKey]; hKey
0x1800e3178  lea     rax, [rbp+90h+RandomBuffer]
0x1800e317c  mov     [rsp+190h+var_148], ebx; dwFlags
0x1800e3180  lea     rdx, [r14+2]; pbInput
0x1800e3184  mov     [rbp+90h+var_C8], rax
0x1800e3188  lea     r9, [rbp+90h+pPaddingInfo]; pPaddingInfo
0x1800e318c  lea     rax, [rbp+90h+var_70]
0x1800e3190  mov     [rbp+90h+pPaddingInfo], 58h ; 'X'
0x1800e3197  mov     [rbp+90h+var_B8], rax
0x1800e319b  mov     r8d, edi; cbInput
0x1800e319e  lea     rax, [rdi+rsi]
0x1800e31a2  mov     [rbp+90h+var_CC], 1
0x1800e31a9  mov     [rbp+90h+var_A8], rax
0x1800e31ad  lea     rax, [rsp+190h+var_140]
0x1800e31b2  mov     [rsp+190h+pcbResult], rax; pcbResult
0x1800e31b7  mov     [rsp+190h+cbOutput], edi; cbOutput
0x1800e31bb  mov     qword ptr [rsp+190h+dwFlags], rsi; pbOutput
0x1800e31c0  mov     dword ptr [rsp+190h+input_used], ebx; cbIV
0x1800e31c4  mov     qword ptr [rsp+190h+output_buffer_size], 0; pbIV
0x1800e31cd  mov     [rbp+90h+var_C0], r13d
0x1800e31d1  mov     [rbp+90h+var_B0], r13d
0x1800e31d5  mov     [rbp+90h+var_A0], 10h
0x1800e31dc  call    cs:__imp_BCryptEncrypt
0x1800e31e2  mov     ebx, eax
0x1800e31e4  test    eax, eax
0x1800e31e6  jnz     short loc_1800E3235
0x1800e31e8  cmp     [rsp+190h+var_140], edi
0x1800e31ec  jz      short loc_1800E31F5
0x1800e31ee  mov     ebx, 80090020h
0x1800e31f3  jmp     short loc_1800E3235
0x1800e31f5  mov     r8, [rbp+90h+var_110]
0x1800e31f9  lea     rax, [rbp+90h+RandomBuffer]
0x1800e31fd  mov     rdx, [rbp+90h+var_108]
0x1800e3201  lea     r9, [rsp+190h+var_120]
0x1800e3206  lea     rcx, [rbp+90h+var_100]
0x1800e320a  mov     [rbp+90h+var_E8], rax
0x1800e320e  mov     [rbp+90h+var_100], r15d
0x1800e3212  mov     [rbp+90h+var_F8], rsi
0x1800e3216  mov     [rbp+90h+var_F0], r13d
0x1800e321a  mov     [rbp+90h+var_E0], r12d
0x1800e321e  call    CtapCborEncodeEncryptedLargeBlob
0x1800e3223  test    eax, eax
0x1800e3225  jz      short loc_1800E3233
0x1800e3227  mov     ecx, eax
0x1800e3229  call    CtapCborErrorToWin32Error
0x1800e322e  jmp     loc_1800E3061
0x1800e3233  xor     ebx, ebx
0x1800e3235  mov     rcx, [rsp+190h+context]
0x1800e323a  test    rcx, rcx
0x1800e323d  jz      short loc_1800E3245
0x1800e323f  call    cs:__imp_CloseCompressor
0x1800e3245  mov     rcx, r14; void *
0x1800e3248  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800e324d  mov     rcx, [rsp+190h+phKey]; hKey
0x1800e3252  test    rcx, rcx
0x1800e3255  jz      short loc_1800E325D
0x1800e3257  call    cs:__imp_BCryptDestroyKey
0x1800e325d  mov     rcx, rsi; void *
0x1800e3260  call    ?FidoFree@@YAXPEAX@Z; FidoFree(void *)
0x1800e3265  mov     eax, ebx
0x1800e3267  mov     rcx, [rbp+90h+var_50]
0x1800e326b  xor     rcx, rsp; StackCookie
0x1800e326e  call    __security_check_cookie
0x1800e3273  add     rsp, 158h
0x1800e327a  pop     r15
0x1800e327c  pop     r14
0x1800e327e  pop     r13
0x1800e3280  pop     r12
0x1800e3282  pop     rdi
0x1800e3283  pop     rsi
0x1800e3284  pop     rbx
0x1800e3285  pop     rbp
0x1800e3286  retn
```
