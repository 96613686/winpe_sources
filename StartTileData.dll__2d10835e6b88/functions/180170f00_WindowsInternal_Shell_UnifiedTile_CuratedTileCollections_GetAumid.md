# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::GetAumid

- ea: `0x180170f00`
- end: `0x180171106`
- name: `WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::GetAumid`
- size: `518`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18016ee88`
- `0x18016fdb8`
- `0x18017c468`
- `0x180183d50`
- `0x180186f7c`
- `0x180187100`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x1800756e4`
- `0x180170f00`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180170fc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017101a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180171089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801710df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180170fc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017101a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180171089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801710df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180171004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801710c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180171004`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801710c9`

## string_xrefs

- `0x180170f3a`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180170f9d`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180170fec`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x180171062`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`
- `0x1801710b1`: `shellcommon\shell\tiles\CuratedTileCollections\Common\UtmHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::GetAumid(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  PCWSTR StringRawBuffer; // rax
  int v15; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v17; // [rsp+58h] [rbp+28h] BYREF
  HSTRING string; // [rsp+60h] [rbp+30h] BYREF
  __int64 v19; // [rsp+68h] [rbp+38h] BYREF

  v17 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 48LL))(a2, &v17);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
      (const char *)(unsigned int)v4,
      v15);
  if ( v17 == 1 )
  {
    v19 = 0;
    v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a2)(
           a2,
           &GUID_a7668288_cc23_4b67_be8b_6c10455986b8,
           &v19);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
        (const char *)(unsigned int)v9,
        v15);
    string = 0;
    v10 = v19;
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, &string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
        (const char *)(unsigned int)v12,
        v15);
    goto LABEL_15;
  }
  if ( v17 == 2 )
  {
    v19 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a2)(
           a2,
           &GUID_5e8c6b47_79d6_40ac_8f45_30f87e82c583,
           &v19);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
        (const char *)(unsigned int)v5,
        v15);
    string = 0;
    v6 = v19;
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v8 = v7(v6, &string);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"shellcommon\\shell\\tiles\\CuratedTileCollections\\Common\\UtmHelpers.h",
        (const char *)(unsigned int)v8,
        v15);
LABEL_15:
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(a1, StringRawBuffer);
    WindowsDeleteString(string);
    string = 0;
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v19);
    return a1;
  }
  std::wstring::wstring(a1, &String1);
  return a1;
}

```

## disassembly

```asm
0x180170f00  mov     [rsp-18h+arg_0], rbx
0x180170f05  push    rbp
0x180170f06  push    rsi
0x180170f07  push    rdi
0x180170f08  mov     rbp, rsp
0x180170f0b  sub     rsp, 30h
0x180170f0f  mov     rbx, rdx
0x180170f12  mov     rsi, rcx
0x180170f15  mov     [rbp+arg_8], 0
0x180170f1c  mov     rax, [rdx]
0x180170f1f  lea     rdx, [rbp+arg_8]
0x180170f23  mov     rcx, rbx
0x180170f26  mov     rax, [rax+30h]
0x180170f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180170f2f  mov     rcx, [rbp+18h]; this
0x180170f33  test    eax, eax
0x180170f35  jns     short loc_180170F4C
0x180170f37  mov     r9d, eax; char *
0x180170f3a  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180170f41  mov     edx, 21h ; '!'; void *
0x180170f46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180170f4c  mov     ecx, [rbp+arg_8]
0x180170f4f  sub     ecx, 1
0x180170f52  jz      loc_180171036
0x180170f58  cmp     ecx, 1
0x180170f5b  jz      short loc_180170F71
0x180170f5d  lea     rdx, String1
0x180170f64  mov     rcx, rsi
0x180170f67  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180170f6c  jmp     loc_1801710F6
0x180170f71  mov     [rbp+arg_18], 0
0x180170f79  mov     rax, [rbx]
0x180170f7c  lea     r8, [rbp+arg_18]
0x180170f80  lea     rdx, _GUID_5e8c6b47_79d6_40ac_8f45_30f87e82c583
0x180170f87  mov     rcx, rbx
0x180170f8a  mov     rax, [rax]
0x180170f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180170f92  mov     rcx, [rbp+18h]; this
0x180170f96  test    eax, eax
0x180170f98  jns     short loc_180170FAF
0x180170f9a  mov     r9d, eax; char *
0x180170f9d  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180170fa4  mov     edx, 31h ; '1'; void *
0x180170fa9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180170faf  mov     [rbp+string], 0
0x180170fb7  mov     rdi, [rbp+arg_18]
0x180170fbb  mov     rax, [rdi]
0x180170fbe  mov     rbx, [rax+30h]
0x180170fc2  xor     ecx, ecx; string
0x180170fc4  call    cs:__imp_WindowsDeleteString
0x180170fca  mov     [rbp+string], 0
0x180170fd2  lea     rdx, [rbp+string]
0x180170fd6  mov     rcx, rdi
0x180170fd9  mov     rax, rbx
0x180170fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180170fe1  mov     rcx, [rbp+18h]; this
0x180170fe5  test    eax, eax
0x180170fe7  jns     short loc_180170FFE
0x180170fe9  mov     r9d, eax; char *
0x180170fec  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180170ff3  mov     edx, 33h ; '3'; void *
0x180170ff8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180170ffe  xor     edx, edx; length
0x180171000  mov     rcx, [rbp+string]; string
0x180171004  call    cs:__imp_WindowsGetStringRawBuffer
0x18017100a  mov     rdx, rax
0x18017100d  mov     rcx, rsi
0x180171010  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180171015  nop
0x180171016  mov     rcx, [rbp+string]; string
0x18017101a  call    cs:__imp_WindowsDeleteString
0x180171020  mov     [rbp+string], 0
0x180171028  lea     rcx, [rbp+arg_18]; void *
0x18017102c  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180171031  jmp     loc_1801710F6
0x180171036  mov     [rbp+arg_18], 0
0x18017103e  mov     rax, [rbx]
0x180171041  lea     r8, [rbp+arg_18]
0x180171045  lea     rdx, _GUID_a7668288_cc23_4b67_be8b_6c10455986b8
0x18017104c  mov     rcx, rbx
0x18017104f  mov     rax, [rax]
0x180171052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180171057  mov     rcx, [rbp+18h]; this
0x18017105b  test    eax, eax
0x18017105d  jns     short loc_180171074
0x18017105f  mov     r9d, eax; char *
0x180171062  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x180171069  mov     edx, 28h ; '('; void *
0x18017106e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180171074  mov     [rbp+string], 0
0x18017107c  mov     rdi, [rbp+arg_18]
0x180171080  mov     rax, [rdi]
0x180171083  mov     rbx, [rax+30h]
0x180171087  xor     ecx, ecx; string
0x180171089  call    cs:__imp_WindowsDeleteString
0x18017108f  mov     [rbp+string], 0
0x180171097  lea     rdx, [rbp+string]
0x18017109b  mov     rcx, rdi
0x18017109e  mov     rax, rbx
0x1801710a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801710a6  mov     rcx, [rbp+18h]; this
0x1801710aa  test    eax, eax
0x1801710ac  jns     short loc_1801710C3
0x1801710ae  mov     r9d, eax; char *
0x1801710b1  lea     r8, aShellcommonShe_21; "shellcommon\\shell\\tiles\\CuratedTileC"...
0x1801710b8  mov     edx, 2Ah ; '*'; void *
0x1801710bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801710c3  xor     edx, edx; length
0x1801710c5  mov     rcx, [rbp+string]; string
0x1801710c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801710cf  mov     rdx, rax
0x1801710d2  mov     rcx, rsi
0x1801710d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801710da  nop
0x1801710db  mov     rcx, [rbp+string]; string
0x1801710df  call    cs:__imp_WindowsDeleteString
0x1801710e5  mov     [rbp+string], 0
0x1801710ed  lea     rcx, [rbp+arg_18]; void *
0x1801710f1  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1801710f6  mov     rax, rsi
0x1801710f9  mov     rbx, [rsp+30h+arg_0]
0x1801710fe  add     rsp, 30h
0x180171102  pop     rdi
0x180171103  pop     rsi
0x180171104  pop     rbp
0x180171105  retn
```
