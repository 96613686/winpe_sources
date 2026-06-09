# GetAppUriHandlerRegistrationEntryFromJson(Windows::Data::Json::IJsonArray *,HSTRING__ *)

- ea: `0x14000bef8`
- end: `0x14000c140`
- name: `?GetAppUriHandlerRegistrationEntryFromJson@@YA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAUIJsonArray@Json@Data@Windows@@PEAUHSTRING__@@@Z`
- size: `584`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000eb7c`
- `0x14000ed9c`

## callees

- `0x140002210`
- `0x14000834c`
- `0x14000bef8`
- `0x14000d49c`
- `0x14000fbb0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x14000c063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x14000c063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c017`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c07f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c0d4`

## pseudocode

```c
_QWORD *__fastcall GetAppUriHandlerRegistrationEntryFromJson(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        HSTRING a3)
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  int v8; // eax
  unsigned int i; // r14d
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v14; // rax
  HRESULT v15; // eax
  __int64 v16; // rbx
  HSTRING string2; // [rsp+20h] [rbp-60h] BYREF
  __int64 v19; // [rsp+28h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+30h] [rbp-50h] BYREF
  INT32 result; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  int v23; // [rsp+40h] [rbp-40h]
  _QWORD *v24; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER v25; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v24 = a1;
  v23 = 0;
  v20 = 0;
  v22 = 0;
  v6 = **a2;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v22);
  v7 = v6(a2, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v22);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x231,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v7,
      (int)string2);
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v22 + 56LL))(v22, &v20);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x232,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)(unsigned int)v8,
      (int)string2);
  *a1 = 0;
  v23 = 1;
  for ( i = 0; i < v20; ++i )
  {
    v19 = 0;
    v10 = (*a2)[6];
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v19);
    v11 = v10(a2, (GUID *)i, &v19);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x238,
        (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
        (const char *)(unsigned int)v11,
        (int)string2);
    string2 = 0;
    v12 = v19;
    v13 = *(int (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v19 + 80LL);
    WindowsDeleteString(0);
    string2 = 0;
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v25, (const WCHAR **)&off_14001B058);
    if ( v13(v12, v14[1].Reserved.Reserved1, &string2) >= 0 )
    {
      result = -1;
      v15 = WindowsCompareStringOrdinal(a3, string2, &result);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x23F,
          (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
          (const char *)(unsigned int)v15,
          (int)string2);
      if ( !result )
      {
        v16 = v19;
        if ( *a1 != v19 )
        {
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
          v24 = (_QWORD *)*a1;
          *a1 = v16;
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v24);
        }
        WindowsDeleteString(string2);
        string2 = 0;
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v19);
        break;
      }
    }
    WindowsDeleteString(string2);
    string2 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v19);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&v22);
  return a1;
}

```

## disassembly

```asm
0x14000bef8  push    rbp
0x14000befa  push    rbx
0x14000befb  push    rsi
0x14000befc  push    rdi
0x14000befd  push    r12
0x14000beff  push    r14
0x14000bf01  push    r15
0x14000bf03  mov     rbp, rsp
0x14000bf06  sub     rsp, 80h
0x14000bf0d  mov     rax, cs:__security_cookie
0x14000bf14  xor     rax, rsp
0x14000bf17  mov     [rbp+var_10], rax
0x14000bf1b  mov     r12, r8
0x14000bf1e  mov     r15, rdx
0x14000bf21  mov     rsi, rcx
0x14000bf24  mov     [rbp+var_38], rcx
0x14000bf28  mov     [rbp+var_40], 0
0x14000bf2f  mov     [rbp+var_50], 0
0x14000bf36  mov     [rbp+var_48], 0
0x14000bf3e  mov     rax, [rdx]
0x14000bf41  mov     rbx, [rax]
0x14000bf44  lea     rcx, [rbp+var_48]
0x14000bf48  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000bf4d  lea     r8, [rbp+var_48]
0x14000bf51  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x14000bf58  mov     rcx, r15
0x14000bf5b  mov     rax, rbx
0x14000bf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf63  mov     rcx, [rbp+38h]; this
0x14000bf67  test    eax, eax
0x14000bf69  jns     short loc_14000BF80
0x14000bf6b  mov     r9d, eax; char *
0x14000bf6e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000bf75  mov     edx, 231h; void *
0x14000bf7a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000bf80  mov     rcx, [rbp+var_48]
0x14000bf84  mov     rax, [rcx]
0x14000bf87  lea     rdx, [rbp+var_50]
0x14000bf8b  mov     rax, [rax+38h]
0x14000bf8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf94  mov     rcx, [rbp+38h]; this
0x14000bf98  test    eax, eax
0x14000bf9a  jns     short loc_14000BFB1
0x14000bf9c  mov     r9d, eax; char *
0x14000bf9f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000bfa6  mov     edx, 232h; void *
0x14000bfab  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000bfb1  mov     qword ptr [rsi], 0
0x14000bfb8  mov     [rbp+var_40], 1
0x14000bfbf  xor     r14d, r14d
0x14000bfc2  cmp     r14d, [rbp+var_50]
0x14000bfc6  jnb     loc_14000C0EC
0x14000bfcc  mov     [rbp+var_58], 0
0x14000bfd4  mov     rax, [r15]
0x14000bfd7  mov     rbx, [rax+30h]
0x14000bfdb  lea     rcx, [rbp+var_58]
0x14000bfdf  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000bfe4  lea     r8, [rbp+var_58]
0x14000bfe8  mov     edx, r14d
0x14000bfeb  mov     rcx, r15
0x14000bfee  mov     rax, rbx
0x14000bff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bff6  mov     rcx, [rbp+38h]; this
0x14000bffa  test    eax, eax
0x14000bffc  js      loc_14000C12B
0x14000c002  mov     [rbp+string2], 0
0x14000c00a  mov     rdi, [rbp+var_58]
0x14000c00e  mov     rax, [rdi]
0x14000c011  mov     rbx, [rax+50h]
0x14000c015  xor     ecx, ecx; string
0x14000c017  call    cs:__imp_WindowsDeleteString
0x14000c01d  mov     [rbp+string2], 0
0x14000c025  lea     rdx, off_14001B058; "packageFamilyName"
0x14000c02c  lea     rcx, [rbp+var_30]
0x14000c030  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x14000c035  nop
0x14000c036  lea     r8, [rbp+string2]
0x14000c03a  mov     rdx, [rax+18h]
0x14000c03e  mov     rcx, rdi
0x14000c041  mov     rax, rbx
0x14000c044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c049  nop
0x14000c04a  shr     eax, 1Fh
0x14000c04d  xor     al, 1
0x14000c04f  jz      short loc_14000C07B
0x14000c051  mov     [rbp+result], 0FFFFFFFFh
0x14000c058  lea     r8, [rbp+result]; result
0x14000c05c  mov     rdx, [rbp+string2]; string2
0x14000c060  mov     rcx, r12; string1
0x14000c063  call    cs:__imp_WindowsCompareStringOrdinal
0x14000c069  mov     rcx, [rbp+38h]; this
0x14000c06d  test    eax, eax
0x14000c06f  js      loc_14000C116
0x14000c075  cmp     [rbp+result], 0
0x14000c079  jz      short loc_14000C09E
0x14000c07b  mov     rcx, [rbp+string2]; string
0x14000c07f  call    cs:__imp_WindowsDeleteString
0x14000c085  mov     [rbp+string2], 0
0x14000c08d  lea     rcx, [rbp+var_58]
0x14000c091  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c096  inc     r14d
0x14000c099  jmp     loc_14000BFC2
0x14000c09e  mov     rbx, [rbp+var_58]
0x14000c0a2  cmp     [rsi], rbx
0x14000c0a5  jz      short loc_14000C0D0
0x14000c0a7  test    rbx, rbx
0x14000c0aa  jz      short loc_14000C0BC
0x14000c0ac  mov     rax, [rbx]
0x14000c0af  mov     rcx, rbx
0x14000c0b2  mov     rax, [rax+8]
0x14000c0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0bb  nop
0x14000c0bc  mov     rax, [rsi]
0x14000c0bf  mov     [rbp+var_38], rax
0x14000c0c3  mov     [rsi], rbx
0x14000c0c6  lea     rcx, [rbp+var_38]
0x14000c0ca  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c0cf  nop
0x14000c0d0  mov     rcx, [rbp+string2]; string
0x14000c0d4  call    cs:__imp_WindowsDeleteString
0x14000c0da  mov     [rbp+string2], 0
0x14000c0e2  lea     rcx, [rbp+var_58]
0x14000c0e6  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c0eb  nop
0x14000c0ec  lea     rcx, [rbp+var_48]
0x14000c0f0  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x14000c0f5  mov     rax, rsi
0x14000c0f8  mov     rcx, [rbp+var_10]
0x14000c0fc  xor     rcx, rsp; StackCookie
0x14000c0ff  call    __security_check_cookie
0x14000c104  add     rsp, 80h
0x14000c10b  pop     r15
0x14000c10d  pop     r14
0x14000c10f  pop     r12
0x14000c111  pop     rdi
0x14000c112  pop     rsi
0x14000c113  pop     rbx
0x14000c114  pop     rbp
0x14000c115  retn
0x14000c116  mov     r9d, eax; char *
0x14000c119  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c120  mov     edx, 23Fh; void *
0x14000c125  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c12b  mov     r9d, eax; char *
0x14000c12e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c135  mov     edx, 238h; void *
0x14000c13a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
