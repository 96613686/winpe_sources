# CtapCborReencodeGetAssertionRequestWithUvAndHmacSecret

- ea: `0x1800cafd4`
- end: `0x1800cb52b`
- name: `CtapCborReencodeGetAssertionRequestWithUvAndHmacSecret`
- size: `1367`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, ULONG cbSecret, __int64, int, __int64, int, LONG input_buffer_size, __int64, __int64, int, __int64, __int64, __int64, __int64, int, int, __int64, __int64, __int64)`
- caller_count: `13`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e4390`
- `0x1800e6540`
- `0x1800e810c`
- `0x1800e97ec`
- `0x1800eb4e0`
- `0x1800ecfac`
- `0x1800ef978`
- `0x1800f1040`
- `0x1800f5e90`
- `0x1800f7858`
- `0x1800f99f0`
- `0x1800fb20c`
- `0x1801076ec`

## callees

- `0x180007f90`
- `0x1800187d0`
- `0x18001cd78`
- `0x18002bbf4`
- `0x1800c8660`
- `0x1800c93e8`
- `0x1800cafd4`
- `0x1800d1018`
- `0x1800d4588`
- `0x1800d74d0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cb374`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cb374`
- `Cabinet!__imp_CreateCompressor` at `0x1800cb314`
- `Cabinet!__imp_CreateCompressor` at `0x1800cb314`
- `Cabinet!__imp_Compress` at `0x1800cb351`
- `Cabinet!__imp_Compress` at `0x1800cb3bd`
- `Cabinet!__imp_Compress` at `0x1800cb351`
- `Cabinet!__imp_Compress` at `0x1800cb3bd`
- `Cabinet!__imp_CloseCompressor` at `0x1800cb4e3`
- `Cabinet!__imp_CloseCompressor` at `0x1800cb4e3`

## pseudocode

```c
__int64 __fastcall CtapCborReencodeGetAssertionRequestWithUvAndHmacSecret(
        int a1,
        int a2,
        _DWORD *a3,
        int a4,
        int a5,
        int a6,
        ULONG cbSecret,
        UCHAR *a8,
        int a9,
        __int64 a10,
        int a11,
        LONG input_buffer_size,
        BYTE *a13,
        __int64 a14,
        int a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        int a20,
        unsigned int a21,
        _DWORD *a22,
        _QWORD *a23,
        _DWORD *a24)
{
  _DWORD *v24; // r12
  __int64 v26; // rbx
  BYTE *v27; // r14
  signed int v28; // esi
  unsigned int v29; // edi
  unsigned int AssertionRequest; // eax
  _DWORD *v31; // r12
  unsigned int v32; // edi
  __int128 *v33; // rcx
  int v34; // eax
  __int64 v35; // r12
  _DWORD *v36; // rax
  unsigned int v37; // edx
  __int64 v38; // rcx
  unsigned int NonzeroLastError; // eax
  BYTE *v40; // r13
  int v41; // edx
  __int64 v42; // r8
  __int64 v43; // r8
  int v44; // edx
  unsigned int AssertionRequest2; // eax
  LONG *v47; // [rsp+30h] [rbp-C9h]
  LONG *v48; // [rsp+30h] [rbp-C9h]
  INT v49; // [rsp+38h] [rbp-C1h]
  INT v50; // [rsp+38h] [rbp-C1h]
  int v51; // [rsp+40h] [rbp-B9h] BYREF
  BYTE *v52; // [rsp+48h] [rbp-B1h]
  __int64 v53; // [rsp+50h] [rbp-A9h]
  PVOID context; // [rsp+58h] [rbp-A1h] BYREF
  char v55[8]; // [rsp+60h] [rbp-99h] BYREF
  LONG input_used[2]; // [rsp+68h] [rbp-91h] BYREF
  __int64 v57; // [rsp+70h] [rbp-89h] BYREF
  __int64 v58; // [rsp+78h] [rbp-81h]
  BYTE *input_buffer; // [rsp+80h] [rbp-79h]
  LONG v60[2]; // [rsp+88h] [rbp-71h] BYREF
  PUCHAR pbSecret; // [rsp+90h] [rbp-69h]
  __int64 v62; // [rsp+98h] [rbp-61h]
  __int64 v63; // [rsp+A0h] [rbp-59h]
  __int64 v64; // [rsp+A8h] [rbp-51h]
  _QWORD *v65; // [rsp+B0h] [rbp-49h]
  _DWORD *v66; // [rsp+B8h] [rbp-41h]
  char v67; // [rsp+C0h] [rbp-39h] BYREF
  __int128 v68; // [rsp+C8h] [rbp-31h] BYREF
  UCHAR pbOutput[16]; // [rsp+D8h] [rbp-21h] BYREF
  __int128 v70; // [rsp+E8h] [rbp-11h]

  v24 = a24;
  pbSecret = a8;
  input_buffer = a13;
  v58 = a16;
  v63 = a17;
  v62 = a18;
  v64 = a19;
  v51 = a4;
  v66 = a22;
  v26 = 0;
  v65 = a23;
  v27 = 0;
  *a22 = 0;
  *a23 = 0;
  v53 = (__int64)a24;
  v57 = 0;
  context = 0;
  v52 = 0;
  *(_QWORD *)v60 = 0;
  *(_QWORD *)input_used = 0;
  v68 = 0;
  *(_OWORD *)pbOutput = 0;
  v70 = 0;
  if ( !a1 )
  {
    v28 = a20;
    v29 = 13;
    goto LABEL_73;
  }
  AssertionRequest = CtapCborDecodeGetAssertionRequest(
                       a1 - 1,
                       a2 + 1,
                       (unsigned int)&v57,
                       (unsigned int)&v67,
                       (__int64)v55);
  v26 = v57;
  if ( AssertionRequest )
  {
    v28 = 0;
    v29 = CtapCborErrorToWin32Error(AssertionRequest);
    goto LABEL_71;
  }
  v28 = a20;
  if ( a20 < 0 )
  {
    v29 = 87;
    goto LABEL_71;
  }
  v31 = (_DWORD *)(v57 + 48);
  v32 = *(_DWORD *)(v57 + 48);
  if ( a20 > 0 )
  {
    if ( v32 )
    {
      while ( 1 )
      {
        if ( v28 > v32 || (unsigned int)v28 > 0x28 )
        {
          v28 = -1;
          goto LABEL_35;
        }
        v37 = a3[21];
        if ( !v37 || *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v57 + 56) + 8LL * v28 - 8) + 4LL) <= v37 )
        {
          v38 = *(_QWORD *)(*(_QWORD *)(v57 + 56) + 8LL * v28 - 8);
          if ( !*(_DWORD *)(v38 + 24) || !a21 || (a21 & *(_DWORD *)(v38 + 24)) != 0 )
            break;
        }
        ++v28;
      }
      if ( v28 != 1 )
        **(_QWORD **)(v57 + 56) = *(_QWORD *)(*(_QWORD *)(v57 + 56) + 8LL * v28 - 8);
      *v31 = 1;
    }
    else
    {
      v28 = 0;
    }
  }
  CtapCborUpdateCredentialListForTransportAndAuthenticator(v26 + 48, a3, a21);
  if ( !v32 || *v31 )
  {
    v33 = *(__int128 **)(v26 + 80);
    v29 = 0;
    if ( !v33 )
    {
      *(_QWORD *)(v26 + 80) = &v68;
      v33 = &v68;
      LODWORD(v68) = 1;
    }
    *((_DWORD *)v33 + 1) = v51;
    *((_DWORD *)v33 + 2) = a5;
    if ( cbSecret )
    {
      v29 = CtapCborClientPinHMACToken(cbSecret, pbSecret, *(_DWORD *)(v26 + 32), *(PUCHAR *)(v26 + 40), pbOutput);
      v34 = 16;
      if ( a3[46] == 2 )
        v34 = 32;
      *(_DWORD *)(v26 + 92) = v34;
      *(_QWORD *)(v26 + 96) = pbOutput;
    }
    *(_DWORD *)(v26 + 88) = a6;
    if ( a15 && a14 )
    {
      v35 = v58;
      if ( !(unsigned int)CtapCborUpdateHmacSecretExtensionFromSaltValues(
                            a15,
                            v58,
                            (_DWORD)a3,
                            (int)v26 + 48,
                            v63,
                            a14,
                            v62) )
      {
        v36 = (_DWORD *)v64;
        *(_QWORD *)(v26 + 104) = a14;
        if ( v36 )
          *v36 = 1;
      }
    }
    else
    {
      v35 = v58;
      *(_QWORD *)(v26 + 104) = a14;
    }
    if ( (int)a3[52] > 0 && a15 && v35 )
    {
      *(_DWORD *)(v26 + 112) = a15;
      *(_QWORD *)(v26 + 120) = v35;
    }
    if ( (int)a3[53] > 0 )
    {
      *(_QWORD *)(v26 + 168) = a10;
      *(_DWORD *)(v26 + 164) = a9;
    }
    if ( (int)a3[63] <= 0 )
      goto LABEL_56;
    if ( a11 == 1 )
    {
      *(_DWORD *)(v26 + 140) = 1;
      goto LABEL_56;
    }
    if ( a11 == 2 )
    {
      *(_DWORD *)(v26 + 140) = 2;
      if ( !(unsigned int)CreateCompressor(536870914, 0, &context) )
      {
LABEL_48:
        NonzeroLastError = _GetNonzeroLastError();
LABEL_68:
        v29 = NonzeroLastError;
        goto LABEL_69;
      }
      if ( Compress(context, input_buffer, input_buffer_size, 0, 0, input_used, v47, v49) )
      {
        v40 = v52;
      }
      else
      {
        v29 = _GetNonzeroLastError();
        if ( v29 != 122 )
        {
LABEL_69:
          v27 = v52;
          goto LABEL_70;
        }
        v29 = 0;
        v52 = (BYTE *)LocalAlloc(0x40u, (unsigned int)input_used[0]);
        v40 = v52;
        if ( !v52 )
        {
          v29 = _GetNonzeroLastError();
          v27 = 0;
          goto LABEL_70;
        }
      }
      if ( !Compress(context, input_buffer, input_buffer_size, v40, input_used[0], v60, v48, v50) )
        goto LABEL_48;
      *(_QWORD *)(v26 + 152) = v40 + 2;
      *(_DWORD *)(v26 + 144) = v60[0] - 2;
      *(_DWORD *)(v26 + 160) = input_buffer_size;
    }
LABEL_56:
    if ( *(_DWORD *)(v26 + 92) || *(_DWORD *)(v26 + 88) )
      *(_DWORD *)(v26 + 128) = a3[46];
    v41 = *(_DWORD *)(v26 + 64);
    if ( v41 )
    {
      if ( (int)a3[55] > 0 )
      {
        v42 = *(_QWORD *)(v26 + 72);
        v51 = 0;
        CtapCborDecodeBoolExtension((unsigned int)L"credBlob", v41, v42, (unsigned int)&v51, 0, 0);
        if ( v51 )
          *(_DWORD *)(v26 + 132) = 1;
      }
      if ( (int)a3[62] > 0 )
      {
        v43 = *(_QWORD *)(v26 + 72);
        v44 = *(_DWORD *)(v26 + 64);
        v51 = 0;
        CtapCborDecodeBoolExtension((unsigned int)L"largeBlobKey", v44, v43, (unsigned int)&v51, 0, 0);
        if ( v51 )
          *(_DWORD *)(v26 + 136) = 1;
      }
    }
    AssertionRequest2 = CtapCborEncodeGetAssertionRequest2(v26, 0, (_DWORD)v66, (_DWORD)v65, (__int64)v55);
    if ( !AssertionRequest2 )
      goto LABEL_69;
    v28 = 0;
    NonzeroLastError = CtapCborErrorToWin32Error(AssertionRequest2);
    goto LABEL_68;
  }
LABEL_35:
  v29 = -2146893043;
LABEL_70:
  v24 = (_DWORD *)v53;
LABEL_71:
  if ( context )
    CloseCompressor();
LABEL_73:
  FidoFree(v27);
  FidoFree((void *)v26);
  if ( v24 )
    *v24 = v28;
  return v29;
}

```

## disassembly

```asm
0x1800cafd4  mov     [rsp-8+arg_18], rbx
0x1800cafd9  push    rbp
0x1800cafda  push    rsi
0x1800cafdb  push    rdi
0x1800cafdc  push    r12
0x1800cafde  push    r13
0x1800cafe0  push    r14
0x1800cafe2  push    r15
0x1800cafe4  lea     rbp, [rsp-7]
0x1800cafe9  sub     rsp, 100h
0x1800caff0  mov     rax, cs:__security_cookie
0x1800caff7  xor     rax, rsp
0x1800caffa  mov     [rbp+37h+var_38], rax
0x1800caffe  mov     rax, [rbp+37h+arg_38]
0x1800cb002  xorps   xmm0, xmm0
0x1800cb005  mov     r12, [rbp+37h+arg_B8]
0x1800cb00c  mov     r15, r8
0x1800cb00f  mov     r8, [rbp+37h+arg_B0]
0x1800cb016  mov     r13, [rbp+37h+arg_68]
0x1800cb01d  mov     [rbp+37h+pbSecret], rax
0x1800cb021  mov     rax, [rbp+37h+arg_60]
0x1800cb028  mov     [rbp+37h+input_buffer], rax
0x1800cb02c  mov     rax, [rbp+37h+arg_78]
0x1800cb033  mov     [rsp+130h+var_B8], rax
0x1800cb038  mov     rax, [rbp+37h+arg_80]
0x1800cb03f  mov     [rbp+37h+var_90], rax
0x1800cb043  mov     rax, [rbp+37h+arg_88]
0x1800cb04a  mov     [rbp+37h+var_98], rax
0x1800cb04e  mov     rax, [rbp+37h+arg_90]
0x1800cb055  mov     [rbp+37h+var_88], rax
0x1800cb059  mov     rax, [rbp+37h+arg_A8]
0x1800cb060  mov     [rsp+130h+var_F0], r9d
0x1800cb065  xor     r9d, r9d
0x1800cb068  mov     [rbp+37h+var_78], rax
0x1800cb06c  mov     ebx, r9d
0x1800cb06f  mov     [rbp+37h+var_80], r8
0x1800cb073  mov     r14d, r9d
0x1800cb076  mov     [rax], r9d
0x1800cb079  mov     [r8], r9
0x1800cb07c  mov     [rsp+130h+var_E0], r12
0x1800cb081  mov     [rsp+130h+var_C0], rbx
0x1800cb086  mov     [rsp+130h+context], r9
0x1800cb08b  mov     [rsp+130h+var_E8], r9
0x1800cb090  mov     qword ptr [rbp+37h+var_A8], r9
0x1800cb094  mov     qword ptr [rsp+130h+var_C8], r9
0x1800cb099  movups  [rbp+37h+var_68], xmm0
0x1800cb09d  movups  xmmword ptr [rbp+37h+pbOutput], xmm0
0x1800cb0a1  movups  [rbp+37h+var_48], xmm0
0x1800cb0a5  cmp     ecx, 1
0x1800cb0a8  jnb     short loc_1800CB0B9
0x1800cb0aa  mov     esi, [rbp+37h+arg_98]
0x1800cb0b0  lea     edi, [r9+0Dh]
0x1800cb0b4  jmp     loc_1800CB4E9
0x1800cb0b9  inc     rdx
0x1800cb0bc  lea     rax, [rsp+130h+var_D0]
0x1800cb0c1  dec     ecx
0x1800cb0c3  mov     qword ptr [rsp+130h+output_buffer_size], rax
0x1800cb0c8  lea     r9, [rbp+37h+var_70]
0x1800cb0cc  lea     r8, [rsp+130h+var_C0]
0x1800cb0d1  call    CtapCborDecodeGetAssertionRequest
0x1800cb0d6  mov     rbx, [rsp+130h+var_C0]
0x1800cb0db  test    eax, eax
0x1800cb0dd  jz      short loc_1800CB0EF
0x1800cb0df  xor     esi, esi
0x1800cb0e1  mov     ecx, eax
0x1800cb0e3  call    CtapCborErrorToWin32Error
0x1800cb0e8  mov     edi, eax
0x1800cb0ea  jmp     loc_1800CB4D9
0x1800cb0ef  mov     esi, [rbp+37h+arg_98]
0x1800cb0f5  test    esi, esi
0x1800cb0f7  jns     short loc_1800CB103
0x1800cb0f9  mov     edi, 57h ; 'W'
0x1800cb0fe  jmp     loc_1800CB4D9
0x1800cb103  mov     r8d, [rbp+37h+arg_A0]
0x1800cb10a  lea     r12, [rbx+30h]
0x1800cb10e  mov     edi, [r12]
0x1800cb112  test    esi, esi
0x1800cb114  jle     short loc_1800CB120
0x1800cb116  test    edi, edi
0x1800cb118  jnz     loc_1800CB212
0x1800cb11e  xor     esi, esi
0x1800cb120  mov     rdx, r15
0x1800cb123  mov     rcx, r12
0x1800cb126  call    CtapCborUpdateCredentialListForTransportAndAuthenticator
0x1800cb12b  test    edi, edi
0x1800cb12d  jz      short loc_1800CB139
0x1800cb12f  cmp     [r12], r14d
0x1800cb133  jz      loc_1800CB278
0x1800cb139  mov     rcx, [rbx+50h]
0x1800cb13d  xor     edi, edi
0x1800cb13f  test    rcx, rcx
0x1800cb142  jnz     short loc_1800CB157
0x1800cb144  lea     rax, [rbp+37h+var_68]
0x1800cb148  mov     [rbx+50h], rax
0x1800cb14c  lea     rcx, [rbp+37h+var_68]
0x1800cb150  mov     dword ptr [rbp+37h+var_68], 1
0x1800cb157  mov     eax, [rsp+130h+var_F0]
0x1800cb15b  mov     [rcx+4], eax
0x1800cb15e  mov     eax, [rbp+37h+arg_20]
0x1800cb161  mov     [rcx+8], eax
0x1800cb164  mov     ecx, [rbp+37h+cbSecret]; cbSecret
0x1800cb167  test    ecx, ecx
0x1800cb169  jz      short loc_1800CB1A5
0x1800cb16b  mov     r9, [rbx+28h]; pbInput
0x1800cb16f  lea     rax, [rbp+37h+pbOutput]
0x1800cb173  mov     r8d, [rbx+20h]; cbInput
0x1800cb177  mov     rdx, [rbp+37h+pbSecret]; pbSecret
0x1800cb17b  mov     qword ptr [rsp+130h+output_buffer_size], rax; pbOutput
0x1800cb180  call    CtapCborClientPinHMACToken
0x1800cb185  cmp     dword ptr [r15+0B8h], 2
0x1800cb18d  mov     edi, eax
0x1800cb18f  mov     eax, 10h
0x1800cb194  lea     ecx, [rax+10h]
0x1800cb197  cmovz   eax, ecx
0x1800cb19a  mov     [rbx+5Ch], eax
0x1800cb19d  lea     rax, [rbp+37h+pbOutput]
0x1800cb1a1  mov     [rbx+60h], rax
0x1800cb1a5  mov     r14d, [rbp+37h+arg_70]
0x1800cb1ac  mov     eax, [rbp+37h+arg_28]
0x1800cb1af  mov     [rbx+58h], eax
0x1800cb1b2  test    r14d, r14d
0x1800cb1b5  jz      loc_1800CB282
0x1800cb1bb  test    r13, r13
0x1800cb1be  jz      loc_1800CB282
0x1800cb1c4  mov     rax, [rbp+37h+var_98]
0x1800cb1c8  mov     r9, r12
0x1800cb1cb  mov     r12, [rsp+130h+var_B8]
0x1800cb1d0  mov     r8, r15
0x1800cb1d3  mov     [rsp+130h+var_100], rax
0x1800cb1d8  mov     rdx, r12
0x1800cb1db  mov     rax, [rbp+37h+var_90]
0x1800cb1df  mov     ecx, r14d
0x1800cb1e2  mov     [rsp+130h+input_used], r13
0x1800cb1e7  mov     qword ptr [rsp+130h+output_buffer_size], rax
0x1800cb1ec  call    CtapCborUpdateHmacSecretExtensionFromSaltValues
0x1800cb1f1  test    eax, eax
0x1800cb1f3  jnz     loc_1800CB28B
0x1800cb1f9  mov     rax, [rbp+37h+var_88]
0x1800cb1fd  mov     [rbx+68h], r13
0x1800cb201  test    rax, rax
0x1800cb204  jz      loc_1800CB28B
0x1800cb20a  mov     dword ptr [rax], 1
0x1800cb210  jmp     short loc_1800CB28B
0x1800cb212  cmp     esi, edi
0x1800cb214  ja      short loc_1800CB275
0x1800cb216  cmp     esi, 28h ; '('
0x1800cb219  ja      short loc_1800CB275
0x1800cb21b  mov     edx, [r15+54h]
0x1800cb21f  test    edx, edx
0x1800cb221  jz      short loc_1800CB235
0x1800cb223  mov     rax, [r12+8]
0x1800cb228  movsxd  rcx, esi
0x1800cb22b  mov     rcx, [rax+rcx*8-8]
0x1800cb230  cmp     [rcx+4], edx
0x1800cb233  ja      short loc_1800CB253
0x1800cb235  mov     rax, [r12+8]
0x1800cb23a  movsxd  rdx, esi
0x1800cb23d  mov     rcx, [rax+rdx*8-8]
0x1800cb242  cmp     [rcx+18h], r14d
0x1800cb246  jz      short loc_1800CB257
0x1800cb248  test    r8d, r8d
0x1800cb24b  jz      short loc_1800CB257
0x1800cb24d  test    [rcx+18h], r8d
0x1800cb251  jnz     short loc_1800CB257
0x1800cb253  inc     esi
0x1800cb255  jmp     short loc_1800CB212
0x1800cb257  cmp     esi, 1
0x1800cb25a  jz      short loc_1800CB268
0x1800cb25c  mov     rcx, [rbx+38h]
0x1800cb260  mov     rax, [rcx+rdx*8-8]
0x1800cb265  mov     [rcx], rax
0x1800cb268  mov     dword ptr [r12], 1
0x1800cb270  jmp     loc_1800CB120
0x1800cb275  or      esi, 0FFFFFFFFh
0x1800cb278  mov     edi, 8009030Dh
0x1800cb27d  jmp     loc_1800CB4D4
0x1800cb282  mov     r12, [rsp+130h+var_B8]
0x1800cb287  mov     [rbx+68h], r13
0x1800cb28b  cmp     dword ptr [r15+0D0h], 0
0x1800cb293  jle     short loc_1800CB2A7
0x1800cb295  test    r14d, r14d
0x1800cb298  jz      short loc_1800CB2A7
0x1800cb29a  test    r12, r12
0x1800cb29d  jz      short loc_1800CB2A7
0x1800cb29f  mov     [rbx+70h], r14d
0x1800cb2a3  mov     [rbx+78h], r12
0x1800cb2a7  cmp     dword ptr [r15+0D4h], 0
0x1800cb2af  jle     short loc_1800CB2CB
0x1800cb2b1  mov     rax, [rbp+37h+arg_48]
0x1800cb2b8  mov     [rbx+0A8h], rax
0x1800cb2bf  mov     eax, [rbp+37h+arg_40]
0x1800cb2c5  mov     [rbx+0A4h], eax
0x1800cb2cb  cmp     dword ptr [r15+0FCh], 0
0x1800cb2d3  jle     loc_1800CB3E9
0x1800cb2d9  cmp     [rbp+37h+arg_50], 1
0x1800cb2e0  jnz     short loc_1800CB2F1
0x1800cb2e2  mov     dword ptr [rbx+8Ch], 1
0x1800cb2ec  jmp     loc_1800CB3E9
0x1800cb2f1  cmp     [rbp+37h+arg_50], 2
0x1800cb2f8  jnz     loc_1800CB3E9
0x1800cb2fe  lea     r8, [rsp+130h+context]
0x1800cb303  mov     dword ptr [rbx+8Ch], 2
0x1800cb30d  xor     edx, edx
0x1800cb30f  mov     ecx, 20000002h
0x1800cb314  call    cs:__imp_CreateCompressor
0x1800cb31a  test    eax, eax
0x1800cb31c  jnz     short loc_1800CB328
0x1800cb31e  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800cb323  jmp     loc_1800CB4CD
0x1800cb328  mov     r14d, [rbp+37h+input_buffer_size]
0x1800cb32f  lea     rax, [rsp+130h+var_C8]
0x1800cb334  mov     rdx, [rbp+37h+input_buffer]; input_buffer
0x1800cb338  mov     r8d, r14d; input_buffer_size
0x1800cb33b  mov     rcx, [rsp+130h+context]; context
0x1800cb340  xor     r9d, r9d; output_buffer
0x1800cb343  mov     [rsp+130h+input_used], rax; input_used
0x1800cb348  mov     qword ptr [rsp+130h+output_buffer_size], 0; output_buffer_size
0x1800cb351  call    cs:__imp_Compress
0x1800cb357  test    eax, eax
0x1800cb359  jnz     short loc_1800CB396
0x1800cb35b  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800cb360  mov     edi, eax
0x1800cb362  cmp     eax, 7Ah ; 'z'
0x1800cb365  jnz     loc_1800CB4CF
0x1800cb36b  mov     edx, [rsp+130h+var_C8]; uBytes
0x1800cb36f  lea     ecx, [rax-3Ah]; uFlags
0x1800cb372  xor     edi, edi
0x1800cb374  call    cs:__imp_LocalAlloc
0x1800cb37a  mov     [rsp+130h+var_E8], rax
0x1800cb37f  mov     r13, rax
0x1800cb382  test    rax, rax
0x1800cb385  jnz     short loc_1800CB39B
0x1800cb387  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x1800cb38c  mov     edi, eax
0x1800cb38e  mov     r14, r13
0x1800cb391  jmp     loc_1800CB4D4
0x1800cb396  mov     r13, [rsp+130h+var_E8]
0x1800cb39b  mov     rdx, [rbp+37h+input_buffer]; input_buffer
0x1800cb39f  lea     rax, [rbp+37h+var_A8]
0x1800cb3a3  mov     rcx, [rsp+130h+context]; context
0x1800cb3a8  mov     r9, r13; output_buffer
0x1800cb3ab  mov     [rsp+130h+input_used], rax; input_used
0x1800cb3b0  mov     r8, r14; input_buffer_size
0x1800cb3b3  mov     rax, qword ptr [rsp+130h+var_C8]
0x1800cb3b8  mov     qword ptr [rsp+130h+output_buffer_size], rax; output_buffer_size
0x1800cb3bd  call    cs:__imp_Compress
0x1800cb3c3  test    eax, eax
0x1800cb3c5  jz      loc_1800CB31E
0x1800cb3cb  lea     rax, [r13+2]
0x1800cb3cf  mov     [rbx+98h], rax
0x1800cb3d6  mov     eax, [rbp+37h+var_A8]
0x1800cb3d9  add     eax, 0FFFFFFFEh
0x1800cb3dc  mov     [rbx+90h], eax
0x1800cb3e2  mov     [rbx+0A0h], r14d
0x1800cb3e9  cmp     dword ptr [rbx+5Ch], 0
0x1800cb3ed  jnz     short loc_1800CB3F5
0x1800cb3ef  cmp     dword ptr [rbx+58h], 0
0x1800cb3f3  jz      short loc_1800CB402
0x1800cb3f5  mov     eax, [r15+0B8h]
0x1800cb3fc  mov     [rbx+80h], eax
0x1800cb402  mov     edx, [rbx+40h]
0x1800cb405  test    edx, edx
0x1800cb407  jz      loc_1800CB4A4
0x1800cb40d  cmp     dword ptr [r15+0DCh], 0
0x1800cb415  jle     short loc_1800CB457
0x1800cb417  mov     r8, [rbx+48h]
0x1800cb41b  lea     r9, [rsp+130h+var_F0]
0x1800cb420  mov     [rsp+130h+input_used], 0
0x1800cb429  lea     rcx, aCredblob; "credBlob"
0x1800cb430  mov     qword ptr [rsp+130h+output_buffer_size], 0
0x1800cb439  mov     [rsp+130h+var_F0], 0
0x1800cb441  call    CtapCborDecodeBoolExtension
0x1800cb446  cmp     [rsp+130h+var_F0], 0
0x1800cb44b  jz      short loc_1800CB457
0x1800cb44d  mov     dword ptr [rbx+84h], 1
0x1800cb457  cmp     dword ptr [r15+0F8h], 0
0x1800cb45f  jle     short loc_1800CB4A4
0x1800cb461  mov     r8, [rbx+48h]
0x1800cb465  lea     r9, [rsp+130h+var_F0]
0x1800cb46a  mov     edx, [rbx+40h]
0x1800cb46d  lea     rcx, aLargeblobkey; "largeBlobKey"
0x1800cb474  mov     [rsp+130h+input_used], 0
0x1800cb47d  mov     qword ptr [rsp+130h+output_buffer_size], 0
0x1800cb486  mov     [rsp+130h+var_F0], 0
0x1800cb48e  call    CtapCborDecodeBoolExtension
0x1800cb493  cmp     [rsp+130h+var_F0], 0
0x1800cb498  jz      short loc_1800CB4A4
0x1800cb49a  mov     dword ptr [rbx+88h], 1
0x1800cb4a4  mov     r9, [rbp+37h+var_80]
0x1800cb4a8  lea     rax, [rsp+130h+var_D0]
0x1800cb4ad  mov     r8, [rbp+37h+var_78]
0x1800cb4b1  xor     edx, edx
0x1800cb4b3  mov     rcx, rbx
0x1800cb4b6  mov     qword ptr [rsp+130h+output_buffer_size], rax
0x1800cb4bb  call    CtapCborEncodeGetAssertionRequest2
0x1800cb4c0  test    eax, eax
0x1800cb4c2  jz      short loc_1800CB4CF
0x1800cb4c4  xor     esi, esi
0x1800cb4c6  mov     ecx, eax
0x1800cb4c8  call    CtapCborErrorToWin32Error
  ... truncated ...
```
