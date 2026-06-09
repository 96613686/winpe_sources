# _lambda_c3ddcf9081ed21b3602a2c72fc5f6745_::operator()(void)

- ea: `0x180012bb0`
- end: `0x180012e5c`
- name: `??R_lambda_c3ddcf9081ed21b3602a2c72fc5f6745_@@QEBA@XZ`
- size: `684`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b1f8`

## callees

- `0x1800033d0`
- `0x180004a10`
- `0x180006900`
- `0x180012bb0`
- `0x180013dc4`
- `0x18001bb70`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012c19`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180012c19`

## string_xrefs

- `0x180012c2c`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180012cb1`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180012d1e`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180012dad`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180012bee`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_c3ddcf9081ed21b3602a2c72fc5f6745_::operator()(__int64 a1)
{
  __int64 v2; // rbx
  int ActivationFactory; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // r8d
  const WCHAR *v8; // rdx
  unsigned __int64 v9; // r9
  unsigned int v10; // r8d
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v20; // [rsp+20h] [rbp-49h] BYREF
  __int64 v21; // [rsp+28h] [rbp-41h] BYREF
  __int64 v22; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-31h] BYREF
  HSTRING_HEADER v24; // [rsp+40h] [rbp-29h] BYREF
  __int64 v25; // [rsp+58h] [rbp-11h]
  HSTRING_HEADER v26; // [rsp+60h] [rbp-9h] BYREF
  __int64 v27; // [rsp+78h] [rbp+Fh]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+17h] BYREF
  __int64 v29; // [rsp+98h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v23 = 0;
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v2 = v29;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v23);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DA,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
      (const char *)(unsigned int)ActivationFactory,
      v20);
LABEL_18:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
    return v4;
  }
  v20 = 0;
  v5 = v23;
  v6 = *v23;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
  v29 = 0;
  v8 = *(const WCHAR **)a1;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, (int)v8, v7);
    JUMPOUT(0x180012E5BLL);
  }
  v10 = v9 + 1;
  if ( (int)v9 + 1 < (unsigned int)v9 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, (int)v8, v10);
    __debugbreak();
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v8, v10, v9);
  v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v6 + 48))(v5, v29, &v20);
  v4 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5DD,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
      (const char *)(unsigned int)v11,
      v20);
LABEL_17:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
    goto LABEL_18;
  }
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v24, L"Badge", 6u, 5u);
  v21 = 0;
  v12 = v20;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v20 + 64LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
  v14 = v13(v12, v25, &v21);
  v4 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E1,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
      (const char *)(unsigned int)v14,
      v20);
LABEL_16:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
    v25 = 0;
    goto LABEL_17;
  }
  v27 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v26, L"Type", 5u, 4u);
  v22 = 0;
  v15 = v21;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v21 + 48LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
  v17 = v16(v15, v27, &v22);
  v4 = v17;
  if ( v17 < 0 )
  {
    v18 = 1509;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
      (const char *)(unsigned int)v17,
      v20);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
    v27 = 0;
    goto LABEL_16;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v22 + 72LL))(v22, *(_QWORD *)(a1 + 8));
  v4 = v17;
  if ( v17 < 0 )
  {
    v18 = 1511;
    goto LABEL_15;
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v22);
  v27 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v21);
  v25 = 0;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v23);
  return 0;
}

```

## disassembly

```asm
0x180012bb0  mov     [rsp-8+arg_8], rbx
0x180012bb5  mov     [rsp-8+arg_10], rsi
0x180012bba  push    rbp
0x180012bbb  push    rdi
0x180012bbc  push    r14
0x180012bbe  lea     rbp, [rsp-47h]
0x180012bc3  sub     rsp, 0B0h
0x180012bca  mov     rax, cs:__security_cookie
0x180012bd1  xor     rax, rsp
0x180012bd4  mov     [rbp+57h+var_20], rax
0x180012bd8  mov     rsi, rcx
0x180012bdb  xor     r14d, r14d
0x180012bde  mov     [rbp+57h+var_88], r14
0x180012be2  mov     [rbp+57h+var_28], r14
0x180012be6  lea     r9d, [r14+1Ch]; unsigned int
0x180012bea  lea     r8d, [r14+1Dh]; unsigned int
0x180012bee  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180012bf5  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180012bf9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180012bfe  mov     rbx, [rbp+57h+var_28]
0x180012c02  lea     rcx, [rbp+57h+var_88]
0x180012c06  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012c0b  lea     r8, [rbp+57h+var_88]
0x180012c0f  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180012c16  mov     rcx, rbx
0x180012c19  call    cs:__imp_RoGetActivationFactory
0x180012c1f  mov     ebx, eax
0x180012c21  test    eax, eax
0x180012c23  jns     short loc_180012C42
0x180012c25  mov     rcx, [rbp+5Fh]; this
0x180012c29  mov     r9d, eax; char *
0x180012c2c  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180012c33  mov     edx, 5DAh; void *
0x180012c38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c3d  jmp     loc_180012DE4
0x180012c42  mov     [rbp+57h+var_A0], r14
0x180012c46  mov     rbx, [rbp+57h+var_88]
0x180012c4a  mov     rdi, [rbx]
0x180012c4d  lea     rcx, [rbp+57h+var_A0]
0x180012c51  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012c56  mov     [rbp+57h+var_28], r14
0x180012c5a  mov     rdx, [rsi]; int
0x180012c5d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180012c61  inc     r9; unsigned int
0x180012c64  cmp     [rdx+r9*2], r14w
0x180012c69  jnz     short loc_180012C61
0x180012c6b  mov     eax, 0FFFFFFFFh
0x180012c70  cmp     r9, rax
0x180012c73  ja      loc_180012E51
0x180012c79  lea     r8d, [r9+1]; unsigned int
0x180012c7d  cmp     r8d, r9d
0x180012c80  jb      loc_180012E46
0x180012c86  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180012c8a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180012c8f  nop
0x180012c90  lea     r8, [rbp+57h+var_A0]
0x180012c94  mov     rdx, [rbp+57h+var_28]
0x180012c98  mov     rcx, rbx
0x180012c9b  mov     rax, [rdi+30h]
0x180012c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ca4  mov     ebx, eax
0x180012ca6  test    eax, eax
0x180012ca8  jns     short loc_180012CC7
0x180012caa  mov     rcx, [rbp+5Fh]; this
0x180012cae  mov     r9d, eax; char *
0x180012cb1  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180012cb8  mov     edx, 5DDh; void *
0x180012cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012cc2  jmp     loc_180012DDA
0x180012cc7  mov     [rbp+57h+var_68], r14
0x180012ccb  mov     r9d, 5; unsigned int
0x180012cd1  lea     r8d, [r9+1]; unsigned int
0x180012cd5  lea     rdx, sourceString; "Badge"
0x180012cdc  lea     rcx, [rbp+57h+var_80]; hstringHeader
0x180012ce0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180012ce5  nop
0x180012ce6  mov     [rbp+57h+var_98], r14
0x180012cea  mov     rdi, [rbp+57h+var_A0]
0x180012cee  mov     rax, [rdi]
0x180012cf1  mov     rbx, [rax+40h]
0x180012cf5  lea     rcx, [rbp+57h+var_98]
0x180012cf9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012cfe  lea     r8, [rbp+57h+var_98]
0x180012d02  mov     rdx, [rbp+57h+var_68]
0x180012d06  mov     rcx, rdi
0x180012d09  mov     rax, rbx
0x180012d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d11  mov     ebx, eax
0x180012d13  test    eax, eax
0x180012d15  jns     short loc_180012D34
0x180012d17  mov     rcx, [rbp+5Fh]; this
0x180012d1b  mov     r9d, eax; char *
0x180012d1e  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180012d25  mov     edx, 5E1h; void *
0x180012d2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d2f  jmp     loc_180012DCC
0x180012d34  mov     [rbp+57h+var_48], r14
0x180012d38  mov     r9d, 4; unsigned int
0x180012d3e  lea     r8d, [r9+1]; unsigned int
0x180012d42  lea     rdx, aType; "Type"
0x180012d49  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x180012d4d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180012d52  nop
0x180012d53  mov     [rbp+57h+var_90], r14
0x180012d57  mov     rdi, [rbp+57h+var_98]
0x180012d5b  mov     rax, [rdi]
0x180012d5e  mov     rbx, [rax+30h]
0x180012d62  lea     rcx, [rbp+57h+var_90]
0x180012d66  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012d6b  lea     r8, [rbp+57h+var_90]
0x180012d6f  mov     rdx, [rbp+57h+var_48]
0x180012d73  mov     rcx, rdi
0x180012d76  mov     rax, rbx
0x180012d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d7e  mov     ebx, eax
0x180012d80  test    eax, eax
0x180012d82  jns     short loc_180012D8B
0x180012d84  mov     edx, 5E5h
0x180012d89  jmp     short loc_180012DAA
0x180012d8b  mov     rcx, [rbp+57h+var_90]
0x180012d8f  mov     rax, [rcx]
0x180012d92  mov     rdx, [rsi+8]
0x180012d96  mov     rax, [rax+48h]
0x180012d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d9f  mov     ebx, eax
0x180012da1  test    eax, eax
0x180012da3  jns     short loc_180012E13
0x180012da5  mov     edx, 5E7h; void *
0x180012daa  mov     r9d, eax; char *
0x180012dad  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180012db4  mov     rcx, [rbp+5Fh]; this
0x180012db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012dbd  nop
0x180012dbe  lea     rcx, [rbp+57h+var_90]
0x180012dc2  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012dc7  nop
0x180012dc8  mov     [rbp+57h+var_48], r14
0x180012dcc  lea     rcx, [rbp+57h+var_98]
0x180012dd0  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012dd5  nop
0x180012dd6  mov     [rbp+57h+var_68], r14
0x180012dda  lea     rcx, [rbp+57h+var_A0]
0x180012dde  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012de3  nop
0x180012de4  lea     rcx, [rbp+57h+var_88]
0x180012de8  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012ded  mov     eax, ebx
0x180012def  mov     rcx, [rbp+57h+var_20]
0x180012df3  xor     rcx, rsp; StackCookie
0x180012df6  call    __security_check_cookie
0x180012dfb  lea     r11, [rsp+0C0h+var_10]
0x180012e03  mov     rbx, [r11+28h]
0x180012e07  mov     rsi, [r11+30h]
0x180012e0b  mov     rsp, r11
0x180012e0e  pop     r14
0x180012e10  pop     rdi
0x180012e11  pop     rbp
0x180012e12  retn
0x180012e13  lea     rcx, [rbp+57h+var_90]
0x180012e17  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012e1c  nop
0x180012e1d  mov     [rbp+57h+var_48], r14
0x180012e21  lea     rcx, [rbp+57h+var_98]
0x180012e25  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012e2a  nop
0x180012e2b  mov     [rbp+57h+var_68], r14
0x180012e2f  lea     rcx, [rbp+57h+var_A0]
0x180012e33  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012e38  nop
0x180012e39  lea     rcx, [rbp+57h+var_88]
0x180012e3d  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180012e42  xor     eax, eax
0x180012e44  jmp     short loc_180012DEF
0x180012e46  mov     ecx, 80070216h; this
0x180012e4b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180012e50  int     3; Trap to Debugger
0x180012e51  mov     ecx, 80070216h; this
0x180012e56  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
