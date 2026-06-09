# ProvIumCreateMachineCertificateRequest

- ea: `0x1400044d0`
- end: `0x140004804`
- name: `ProvIumCreateMachineCertificateRequest`
- size: `820`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140003e58`
- `0x1400044d0`
- `0x140004ca8`
- `0x140004d1c`
- `0x1400066f0`
- `0x140006720`
- `0x140038cd2`

## import_xrefs

- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x1400046ab`
- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x140004752`
- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x1400046ab`
- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x140004752`
- `iumcrypt!iumCryptEncodeObjectEx` at `0x1400045e9`
- `iumcrypt!iumCryptEncodeObjectEx` at `0x1400045e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000475c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004798`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400045fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000475c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004798`
- `bcrypt!BCryptDestroyKey` at `0x1400047cc`
- `bcrypt!BCryptDestroyKey` at `0x1400047cc`

## string_xrefs

- `0x1400045a2`: `ProvIumCreateMachineCertificateRequest`
- `0x1400047aa`: `ProvIumCreateMachineCertificateRequest`

## pseudocode

```c
__int64 __fastcall ProvIumCreateMachineCertificateRequest(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  unsigned __int8 **v8; // r14
  int v9; // eax
  __int128 *v10; // r12
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  int v13; // edx
  __int128 v14; // xmm0
  char LastError; // al
  int v16; // r8d
  int v17; // edx
  unsigned __int8 *v18; // rax
  BCRYPT_KEY_HANDLE hKey; // [rsp+50h] [rbp-71h] BYREF
  void *v21; // [rsp+58h] [rbp-69h] BYREF
  __int64 v22; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v23[2]; // [rsp+68h] [rbp-59h] BYREF
  struct _CRYPT_ALGORITHM_IDENTIFIER v24; // [rsp+78h] [rbp-49h] BYREF
  _DWORD v25[4]; // [rsp+90h] [rbp-31h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-21h]
  __int128 v27; // [rsp+A8h] [rbp-19h]
  __int128 v28; // [rsp+B8h] [rbp-9h]
  __int128 v29; // [rsp+C8h] [rbp+7h]
  unsigned int v30; // [rsp+128h] [rbp+67h] BYREF

  if ( !a2 )
    return 3221225485LL;
  if ( !a3 )
    return 3221225485LL;
  if ( !a4 )
    return 3221225485LL;
  v8 = a5;
  if ( !a5 )
    return 3221225485LL;
  hKey = 0;
  v22 = 0;
  v30 = 0;
  v23[0] = 0;
  v23[1] = 0;
  v21 = 0;
  memset_0(v25, 0, 0x58u);
  *a4 = 0;
  *v8 = 0;
  memset(&v24, 0, sizeof(v24));
  v9 = ImportMachineKey(a3, a2, &hKey, &v21);
  v10 = (__int128 *)v21;
  v11 = v9;
  if ( v9 >= 0 )
  {
    if ( iumCryptEncodeObjectEx(1u, (const char *)7, v23, 0x8000u, 0, &v22, &v30) )
    {
      v26 = v22;
      v25[2] = v30;
      v25[0] = 0;
      v27 = *v10;
      v28 = v10[1];
      v14 = v10[2];
      v24.pszObjId = "1.2.840.113549.1.1.11";
      v29 = v14;
      if ( iumCryptSignAndEncodeCertificate(hKey, 0, 1u, (const char *)4, v25, &v24, 0, 0, a4) )
      {
        v18 = (unsigned __int8 *)MIDL_user_allocate(*a4);
        *v8 = v18;
        if ( !v18 )
        {
          v11 = -1073741801;
          goto LABEL_34;
        }
        if ( iumCryptSignAndEncodeCertificate(hKey, 0, 1u, (const char *)4, v25, &v24, 0, v18, a4) )
          goto LABEL_34;
        v11 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_34;
        LastError = GetLastError();
        v17 = 31;
      }
      else
      {
        if ( (int)GetLastError() > 0 )
          v11 = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          v11 = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_34;
        LastError = GetLastError();
        v17 = 30;
      }
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v16,
        (unsigned int)"ProvIumCreateMachineCertificateRequest",
        LastError,
        v11);
      goto LABEL_34;
    }
    if ( (int)GetLastError() > 0 )
      v11 = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      v11 = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v13 = 29;
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_34;
    v13 = 28;
  }
  WPP_SF_sd(
    v12[2],
    v13,
    (unsigned int)&WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids,
    (unsigned int)"ProvIumCreateMachineCertificateRequest",
    v11);
LABEL_34:
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v10 )
    SafeAllocaFreeToHeap(v10);
  return v11;
}

```

## disassembly

```asm
0x1400044d0  mov     [rsp-8+arg_0], rbx
0x1400044d5  mov     [rsp-8+arg_10], rsi
0x1400044da  push    rbp
0x1400044db  push    rdi
0x1400044dc  push    r12
0x1400044de  push    r13
0x1400044e0  push    r14
0x1400044e2  lea     rbp, [rsp-2Fh]
0x1400044e7  sub     rsp, 0F0h
0x1400044ee  xor     r13d, r13d
0x1400044f1  mov     rsi, r9
0x1400044f4  mov     rbx, r8
0x1400044f7  mov     edi, edx
0x1400044f9  test    edx, edx
0x1400044fb  jz      loc_1400047E3
0x140004501  test    rbx, rbx
0x140004504  jz      loc_1400047E3
0x14000450a  test    r9, r9
0x14000450d  jz      loc_1400047E3
0x140004513  mov     r14, [rbp+4Fh+arg_20]
0x140004517  test    r14, r14
0x14000451a  jz      loc_1400047E3
0x140004520  xor     edx, edx; Val
0x140004522  mov     [rbp+4Fh+hKey], r13
0x140004526  lea     r8d, [r13+58h]; Size
0x14000452a  mov     [rbp+4Fh+var_B0], r13
0x14000452e  lea     rcx, [rbp+4Fh+var_80]; void *
0x140004532  mov     [rbp+4Fh+arg_8], r13d
0x140004536  mov     [rbp+4Fh+var_A8], r13
0x14000453a  mov     [rbp+4Fh+var_A0], r13
0x14000453e  mov     [rbp+4Fh+var_B8], r13
0x140004542  call    memset_0
0x140004547  xorps   xmm0, xmm0
0x14000454a  mov     [rsi], r13d
0x14000454d  xor     eax, eax
0x14000454f  mov     [r14], r13
0x140004552  lea     r9, [rbp+4Fh+var_B8]
0x140004556  mov     [rbp+4Fh+var_88], rax
0x14000455a  lea     r8, [rbp+4Fh+hKey]
0x14000455e  mov     edx, edi
0x140004560  mov     rcx, rbx
0x140004563  movups  [rbp+4Fh+var_98], xmm0
0x140004567  call    ImportMachineKey
0x14000456c  mov     r12, [rbp+4Fh+var_B8]
0x140004570  mov     ebx, eax
0x140004572  test    eax, eax
0x140004574  jns     short loc_1400045BE
0x140004576  mov     rcx, cs:WPP_GLOBAL_Control
0x14000457d  lea     rax, WPP_GLOBAL_Control
0x140004584  cmp     rcx, rax
0x140004587  jz      loc_1400047C2
0x14000458d  lea     edi, [r13+1]
0x140004591  test    [rcx+1Ch], dil
0x140004595  jz      loc_1400047C2
0x14000459b  lea     edx, [rdi+1Bh]
0x14000459e  mov     rcx, [rcx+10h]
0x1400045a2  lea     r9, aProviumcreatem; "ProvIumCreateMachineCertificateRequest"
0x1400045a9  lea     r8, WPP_51646ada86fc316e06b18fa5421f3daa_Traceguids
0x1400045b0  mov     dword ptr [rsp+110h+var_F0], ebx
0x1400045b4  call    WPP_SF_sd
0x1400045b9  jmp     loc_1400047C2
0x1400045be  mov     edx, 7
0x1400045c3  lea     rax, [rbp+4Fh+arg_8]
0x1400045c7  mov     [rsp+110h+var_E0], rax
0x1400045cc  lea     r8, [rbp+4Fh+var_A8]
0x1400045d0  lea     rax, [rbp+4Fh+var_B0]
0x1400045d4  mov     r9d, 8000h
0x1400045da  mov     [rsp+110h+var_E8], rax
0x1400045df  lea     edi, [rdx-6]
0x1400045e2  mov     [rsp+110h+var_F0], r13
0x1400045e7  mov     ecx, edi
0x1400045e9  call    cs:__imp_?iumCryptEncodeObjectEx@@YAHKPEBDPEBXKPEAU_CRYPT_ENCODE_PARA@@PEAXPEAK@Z; iumCryptEncodeObjectEx(ulong,char const *,void const *,ulong,_CRYPT_ENCODE_PARA *,void *,ulong *)
0x1400045ef  test    eax, eax
0x1400045f1  jnz     short loc_140004641
0x1400045f3  call    cs:__imp_GetLastError
0x1400045f9  test    eax, eax
0x1400045fb  jg      short loc_140004607
0x1400045fd  call    cs:__imp_GetLastError
0x140004603  mov     ebx, eax
0x140004605  jmp     short loc_140004616
0x140004607  call    cs:__imp_GetLastError
0x14000460d  movzx   ebx, ax
0x140004610  or      ebx, 0C0070000h
0x140004616  mov     rcx, cs:WPP_GLOBAL_Control
0x14000461d  lea     rax, WPP_GLOBAL_Control
0x140004624  cmp     rcx, rax
0x140004627  jz      loc_1400047C2
0x14000462d  test    [rcx+1Ch], dil
0x140004631  jz      loc_1400047C2
0x140004637  mov     edx, 1Dh
0x14000463c  jmp     loc_14000459E
0x140004641  mov     rax, [rbp+4Fh+var_B0]
0x140004645  mov     r9d, 4
0x14000464b  mov     rcx, [rbp+4Fh+hKey]
0x14000464f  mov     r8d, edi
0x140004652  mov     [rbp+4Fh+var_70], rax
0x140004656  xor     edx, edx
0x140004658  mov     eax, [rbp+4Fh+arg_8]
0x14000465b  mov     [rbp+4Fh+var_78], eax
0x14000465e  lea     rax, a12840113549111; "1.2.840.113549.1.1.11"
0x140004665  mov     [rbp+4Fh+var_80], r13d
0x140004669  movups  xmm0, xmmword ptr [r12]
0x14000466e  mov     [rsp+110h+var_D0], rsi
0x140004673  mov     [rsp+110h+var_D8], r13
0x140004678  movups  [rbp+4Fh+var_68], xmm0
0x14000467c  mov     [rsp+110h+var_E0], r13
0x140004681  movups  xmm1, xmmword ptr [r12+10h]
0x140004687  movups  [rbp+4Fh+var_58], xmm1
0x14000468b  movups  xmm0, xmmword ptr [r12+20h]
0x140004691  mov     qword ptr [rbp+4Fh+var_98], rax
0x140004695  lea     rax, [rbp+4Fh+var_98]
0x140004699  mov     [rsp+110h+var_E8], rax
0x14000469e  lea     rax, [rbp+4Fh+var_80]
0x1400046a2  mov     [rsp+110h+var_F0], rax
0x1400046a7  movups  [rbp+4Fh+var_48], xmm0
0x1400046ab  call    cs:__imp_?iumCryptSignAndEncodeCertificate@@YAHPEAXKKPEBDPEBXPEAU_CRYPT_ALGORITHM_IDENTIFIER@@2PEAEPEAK@Z; iumCryptSignAndEncodeCertificate(void *,ulong,ulong,char const *,void const *,_CRYPT_ALGORITHM_IDENTIFIER *,void const *,uchar *,ulong *)
0x1400046b1  test    eax, eax
0x1400046b3  jnz     short loc_140004709
0x1400046b5  call    cs:__imp_GetLastError
0x1400046bb  test    eax, eax
0x1400046bd  jg      short loc_1400046C9
0x1400046bf  call    cs:__imp_GetLastError
0x1400046c5  mov     ebx, eax
0x1400046c7  jmp     short loc_1400046D8
0x1400046c9  call    cs:__imp_GetLastError
0x1400046cf  movzx   ebx, ax
0x1400046d2  or      ebx, 0C0070000h
0x1400046d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046df  lea     rax, WPP_GLOBAL_Control
0x1400046e6  cmp     rcx, rax
0x1400046e9  jz      loc_1400047C2
0x1400046ef  test    [rcx+1Ch], dil
0x1400046f3  jz      loc_1400047C2
0x1400046f9  call    cs:__imp_GetLastError
0x1400046ff  mov     edx, 1Eh
0x140004704  jmp     loc_1400047A3
0x140004709  mov     ecx, [rsi]; size
0x14000470b  call    MIDL_user_allocate
0x140004710  mov     [r14], rax
0x140004713  test    rax, rax
0x140004716  jnz     short loc_140004722
0x140004718  mov     ebx, 0C0000017h
0x14000471d  jmp     loc_1400047C2
0x140004722  mov     rcx, [rbp+4Fh+hKey]
0x140004726  mov     r9d, 4
0x14000472c  mov     [rsp+110h+var_D0], rsi
0x140004731  mov     r8d, edi
0x140004734  mov     [rsp+110h+var_D8], rax
0x140004739  xor     edx, edx
0x14000473b  lea     rax, [rbp+4Fh+var_98]
0x14000473f  mov     [rsp+110h+var_E0], r13
0x140004744  mov     [rsp+110h+var_E8], rax
0x140004749  lea     rax, [rbp+4Fh+var_80]
0x14000474d  mov     [rsp+110h+var_F0], rax
0x140004752  call    cs:__imp_?iumCryptSignAndEncodeCertificate@@YAHPEAXKKPEBDPEBXPEAU_CRYPT_ALGORITHM_IDENTIFIER@@2PEAEPEAK@Z; iumCryptSignAndEncodeCertificate(void *,ulong,ulong,char const *,void const *,_CRYPT_ALGORITHM_IDENTIFIER *,void const *,uchar *,ulong *)
0x140004758  test    eax, eax
0x14000475a  jnz     short loc_1400047C2
0x14000475c  call    cs:__imp_GetLastError
0x140004762  test    eax, eax
0x140004764  jg      short loc_140004770
0x140004766  call    cs:__imp_GetLastError
0x14000476c  mov     ebx, eax
0x14000476e  jmp     short loc_14000477F
0x140004770  call    cs:__imp_GetLastError
0x140004776  movzx   ebx, ax
0x140004779  or      ebx, 0C0070000h
0x14000477f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004786  lea     rax, WPP_GLOBAL_Control
0x14000478d  cmp     rcx, rax
0x140004790  jz      short loc_1400047C2
0x140004792  test    [rcx+1Ch], dil
0x140004796  jz      short loc_1400047C2
0x140004798  call    cs:__imp_GetLastError
0x14000479e  mov     edx, 1Fh
0x1400047a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047aa  lea     r9, aProviumcreatem; "ProvIumCreateMachineCertificateRequest"
0x1400047b1  mov     dword ptr [rsp+110h+var_E8], ebx
0x1400047b5  mov     dword ptr [rsp+110h+var_F0], eax
0x1400047b9  mov     rcx, [rcx+10h]
0x1400047bd  call    WPP_SF_sdD
0x1400047c2  cmp     [rbp+4Fh+hKey], r13
0x1400047c6  jz      short loc_1400047D2
0x1400047c8  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1400047cc  call    cs:__imp_BCryptDestroyKey
0x1400047d2  test    r12, r12
0x1400047d5  jz      short loc_1400047DF
0x1400047d7  mov     rcx, r12; void *
0x1400047da  call    SafeAllocaFreeToHeap
0x1400047df  mov     eax, ebx
0x1400047e1  jmp     short loc_1400047E8
0x1400047e3  mov     eax, 0C000000Dh
0x1400047e8  lea     r11, [rsp+110h+var_20]
0x1400047f0  mov     rbx, [r11+30h]
0x1400047f4  mov     rsi, [r11+40h]
0x1400047f8  mov     rsp, r11
0x1400047fb  pop     r14
0x1400047fd  pop     r13
0x1400047ff  pop     r12
0x140004801  pop     rdi
0x140004802  pop     rbp
0x140004803  retn
```
