# UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x140011d64`
- end: `0x140011fe6`
- name: `?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14001186c`

## callees

- `0x1400024b4`
- `0x140002748`
- `0x140002d74`
- `0x14000ff40`
- `0x140011d64`
- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011dda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011e87`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011dc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011e77`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011dc6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011e77`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilGetTokenUserSid(HANDLE TokenHandle, const struct std::nothrow_t *a2)
{
  PSID *v4; // rsi
  PSID v5; // r15
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  signed int LastError; // eax
  int v12; // ebx
  CUserModeHangReport *v13; // rcx
  __int64 v14; // rdx
  signed int v15; // eax
  void *v16; // rcx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  PSID v19; // [rsp+70h] [rbp+40h] BYREF
  __int64 v20; // [rsp+78h] [rbp+48h]

  v4 = 0;
  v20 = 0;
  TokenInformationLength = 0;
  v5 = 0;
  v19 = 0;
  if ( !a2 || !TokenHandle )
  {
    v12 = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
    goto LABEL_39;
  }
  v6 = *(void **)a2;
  *(_QWORD *)a2 = 0;
  if ( v6 )
    operator delete(v6, a2);
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v12 = -2147418113;
    MicrosoftTelemetryAssertTriggeredNoArgs(v8, v7, v9, v10);
    goto LABEL_39;
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  if ( v12 >= 0 )
  {
    v12 = -2147467259;
LABEL_11:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 11;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, (unsigned int)v12);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  if ( (_WORD)v12 != 122 )
    goto LABEL_11;
  v4 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v4 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
    {
      v12 = UtilDuplicateSid(*v4, &v19);
      if ( v12 >= 0 )
      {
        v5 = 0;
        v16 = *(void **)a2;
        *(_QWORD *)a2 = v19;
        if ( v16 )
          operator delete(v16, a2);
        v12 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
            (unsigned int)v12);
        }
        v5 = v19;
      }
    }
    else
    {
      v15 = GetLastError();
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      if ( v15 >= 0 )
        v15 = -2147467259;
      v12 = v15;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 13;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v4 = 0;
    v12 = -2147024882;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids,
        TokenInformationLength);
    }
  }
LABEL_39:
  if ( v5 )
    operator delete(v5, a2);
  if ( v4 )
    operator delete(v4);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140011d64  mov     [rsp-28h+arg_0], rbx
0x140011d69  push    rbp
0x140011d6a  push    rsi
0x140011d6b  push    r12
0x140011d6d  push    r14
0x140011d6f  push    r15
0x140011d71  mov     rbp, rsp
0x140011d74  sub     rsp, 30h
0x140011d78  mov     r14, rdx
0x140011d7b  mov     r12, rcx
0x140011d7e  xor     esi, esi
0x140011d80  mov     [rbp+arg_18], rsi
0x140011d84  mov     [rbp+TokenInformationLength], esi
0x140011d87  xor     r15d, r15d
0x140011d8a  mov     [rbp+arg_10], r15
0x140011d8e  test    rdx, rdx
0x140011d91  jz      loc_140011F82
0x140011d97  test    rcx, rcx
0x140011d9a  jz      loc_140011F82
0x140011da0  mov     rcx, [rdx]; void *
0x140011da3  mov     [rdx], r15
0x140011da6  test    rcx, rcx
0x140011da9  jz      short loc_140011DB0
0x140011dab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011db0  lea     rax, [rbp+TokenInformationLength]
0x140011db4  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140011db9  xor     r9d, r9d; TokenInformationLength
0x140011dbc  xor     r8d, r8d; TokenInformation
0x140011dbf  lea     edx, [r9+1]; TokenInformationClass
0x140011dc3  mov     rcx, r12; TokenHandle
0x140011dc6  call    cs:__imp_GetTokenInformation
0x140011dcd  nop     dword ptr [rax+rax+00h]
0x140011dd2  test    eax, eax
0x140011dd4  jnz     loc_140011F76
0x140011dda  call    cs:__imp_GetLastError
0x140011de1  nop     dword ptr [rax+rax+00h]
0x140011de6  mov     ebx, eax
0x140011de8  test    eax, eax
0x140011dea  jle     short loc_140011DF5
0x140011dec  movzx   ebx, ax
0x140011def  or      ebx, 80070000h
0x140011df5  test    ebx, ebx
0x140011df7  js      short loc_140011E00
0x140011df9  mov     ebx, 80004005h
0x140011dfe  jmp     short loc_140011E06
0x140011e00  cmp     bx, 7Ah ; 'z'
0x140011e04  jz      short loc_140011E44
0x140011e06  lea     rax, WPP_GLOBAL_Control
0x140011e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e14  cmp     rcx, rax
0x140011e17  jz      loc_140011FB6
0x140011e1d  test    byte ptr [rcx+1Ch], 1
0x140011e21  jz      loc_140011FB6
0x140011e27  mov     edx, 0Bh
0x140011e2c  mov     r9d, ebx
0x140011e2f  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140011e36  mov     rcx, [rcx+10h]
0x140011e3a  call    WPP_SF_d
0x140011e3f  jmp     loc_140011FB6
0x140011e44  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x140011e47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011e4e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011e53  mov     rsi, rax
0x140011e56  test    rax, rax
0x140011e59  jz      loc_140011F3D
0x140011e5f  lea     rax, [rbp+TokenInformationLength]
0x140011e63  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140011e68  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140011e6c  mov     r8, rsi; TokenInformation
0x140011e6f  mov     edx, 1; TokenInformationClass
0x140011e74  mov     rcx, r12; TokenHandle
0x140011e77  call    cs:__imp_GetTokenInformation
0x140011e7e  nop     dword ptr [rax+rax+00h]
0x140011e83  test    eax, eax
0x140011e85  jnz     short loc_140011ED6
0x140011e87  call    cs:__imp_GetLastError
0x140011e8e  nop     dword ptr [rax+rax+00h]
0x140011e93  test    eax, eax
0x140011e95  jle     short loc_140011E9F
0x140011e97  movzx   eax, ax
0x140011e9a  or      eax, 80070000h
0x140011e9f  mov     ebx, 80004005h
0x140011ea4  test    eax, eax
0x140011ea6  cmovns  eax, ebx
0x140011ea9  mov     ebx, eax
0x140011eab  lea     rax, WPP_GLOBAL_Control
0x140011eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140011eb9  cmp     rcx, rax
0x140011ebc  jz      loc_140011FB6
0x140011ec2  test    byte ptr [rcx+1Ch], 1
0x140011ec6  jz      loc_140011FB6
0x140011ecc  mov     edx, 0Dh
0x140011ed1  jmp     loc_140011E2C
0x140011ed6  lea     rdx, [rbp+arg_10]
0x140011eda  mov     rcx, [rsi]; pSourceSid
0x140011edd  call    ?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x140011ee2  mov     ebx, eax
0x140011ee4  test    eax, eax
0x140011ee6  jns     short loc_140011F22
0x140011ee8  lea     rax, WPP_GLOBAL_Control
0x140011eef  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ef6  cmp     rcx, rax
0x140011ef9  jz      short loc_140011F19
0x140011efb  test    byte ptr [rcx+1Ch], 1
0x140011eff  jz      short loc_140011F19
0x140011f01  mov     edx, 0Eh
0x140011f06  mov     r9d, ebx
0x140011f09  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140011f10  mov     rcx, [rcx+10h]
0x140011f14  call    WPP_SF_d
0x140011f19  mov     r15, [rbp+arg_10]
0x140011f1d  jmp     loc_140011FB6
0x140011f22  mov     rax, [rbp+arg_10]
0x140011f26  xor     r15d, r15d
0x140011f29  mov     rcx, [r14]; void *
0x140011f2c  mov     [r14], rax
0x140011f2f  test    rcx, rcx
0x140011f32  jz      short loc_140011F39
0x140011f34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011f39  xor     ebx, ebx
0x140011f3b  jmp     short loc_140011FB6
0x140011f3d  xor     esi, esi
0x140011f3f  mov     ebx, 8007000Eh
0x140011f44  lea     rax, WPP_GLOBAL_Control
0x140011f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f52  cmp     rcx, rax
0x140011f55  jz      short loc_140011FB6
0x140011f57  test    byte ptr [rcx+1Ch], 1
0x140011f5b  jz      short loc_140011FB6
0x140011f5d  lea     edx, [rsi+0Ch]
0x140011f60  mov     r9d, [rbp+TokenInformationLength]
0x140011f64  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140011f6b  mov     rcx, [rcx+10h]
0x140011f6f  call    WPP_SF_d
0x140011f74  jmp     short loc_140011FB6
0x140011f76  mov     ebx, 8000FFFFh
0x140011f7b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140011f80  jmp     short loc_140011FB6
0x140011f82  mov     ebx, 80070057h
0x140011f87  lea     rax, WPP_GLOBAL_Control
0x140011f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011f95  cmp     rcx, rax
0x140011f98  jz      short loc_140011FB6
0x140011f9a  test    byte ptr [rcx+1Ch], 1
0x140011f9e  jz      short loc_140011FB6
0x140011fa0  mov     edx, 0Ah
0x140011fa5  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140011fac  mov     rcx, [rcx+10h]
0x140011fb0  call    WPP_SF_
0x140011fb5  nop
0x140011fb6  test    r15, r15
0x140011fb9  jz      short loc_140011FC4
0x140011fbb  mov     rcx, r15; void *
0x140011fbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011fc3  nop
0x140011fc4  test    rsi, rsi
0x140011fc7  jz      short loc_140011FD1
0x140011fc9  mov     rcx, rsi; Block
0x140011fcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011fd1  mov     eax, ebx
0x140011fd3  mov     rbx, [rsp+30h+arg_0]
0x140011fd8  add     rsp, 30h
0x140011fdc  pop     r15
0x140011fde  pop     r14
0x140011fe0  pop     r12
0x140011fe2  pop     rsi
0x140011fe3  pop     rbp
0x140011fe4  retn
```
