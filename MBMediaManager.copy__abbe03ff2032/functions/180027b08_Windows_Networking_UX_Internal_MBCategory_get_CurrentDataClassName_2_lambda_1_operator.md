# _Windows::Networking::UX::Internal::MBCategory::get_CurrentDataClassName_::_2_::_lambda_1_::operator()

- ea: `0x180027b08`
- end: `0x180027bc1`
- name: `_Windows::Networking::UX::Internal::MBCategory::get_CurrentDataClassName_::_2_::_lambda_1_::operator()`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043730`

## callees

- `0x180003558`
- `0x18000ad20`
- `0x18001cb10`
- `0x180027b08`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027bae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027bae`

## string_xrefs

- `0x180027b8f`: `Exit. _currentDataClassName=%ls`
- `0x180027b9b`: `Windows::Networking::UX::Internal::MBCategory::get_CurrentDataClassName::<lambda_1>::operator ()`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::get_CurrentDataClassName_::_2_::_lambda_1_::operator()(
        _QWORD *a1)
{
  __int64 v2; // rax
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HSTRING v5; // rcx
  HSTRING *v6; // rax
  const wchar_t *v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF
  const WCHAR *v12; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a1 + 800LL;
  string = 0;
  if ( *(_QWORD *)(v2 + 24) > 7u )
    v2 = *(_QWORD *)v2;
  v12 = (const WCHAR *)v2;
  v3 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v12);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = string;
    v6 = (HSTRING *)a1[1];
    string = 0;
    *v6 = v5;
    v7 = (const wchar_t *)(*a1 + 800LL);
    if ( *(_QWORD *)(*a1 + 824LL) > 7u )
      v7 = *(const wchar_t **)v7;
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::get_CurrentDataClassName::<lambda_1>::operator ()",
      2285,
      "Exit. _currentDataClassName=%ls",
      v7);
    v4 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8EB,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)v3,
      v9);
  }
  WindowsDeleteString(string);
  return v4;
}

```

## disassembly

```asm
0x180027b08  mov     [rsp+arg_10], rbx
0x180027b0d  push    rdi; int
0x180027b0e  sub     rsp, 20h
0x180027b12  mov     rax, [rcx]
0x180027b15  mov     rdi, rcx
0x180027b18  add     rax, 320h
0x180027b1e  mov     [rsp+28h+string], 0
0x180027b27  cmp     qword ptr [rax+18h], 7
0x180027b2c  jbe     short loc_180027B31
0x180027b2e  mov     rax, [rax]
0x180027b31  lea     rdx, [rsp+28h+arg_8]
0x180027b36  mov     [rsp+28h+arg_8], rax
0x180027b3b  lea     rcx, [rsp+28h+string]; string
0x180027b40  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180027b45  mov     ebx, eax
0x180027b47  test    eax, eax
0x180027b49  jns     short loc_180027B66
0x180027b4b  mov     rcx, [rsp+28h]; this
0x180027b50  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180027b57  mov     r9d, eax; char *
0x180027b5a  mov     edx, 8EBh; void *
0x180027b5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027b64  jmp     short loc_180027BA9
0x180027b66  mov     rcx, [rsp+28h+string]
0x180027b6b  mov     rax, [rdi+8]
0x180027b6f  mov     [rsp+28h+string], 0
0x180027b78  mov     [rax], rcx
0x180027b7b  mov     r9, [rdi]
0x180027b7e  add     r9, 320h
0x180027b85  cmp     qword ptr [r9+18h], 7
0x180027b8a  jbe     short loc_180027B8F
0x180027b8c  mov     r9, [r9]
0x180027b8f  lea     r8, aExitCurrentdat; "Exit. _currentDataClassName=%ls"
0x180027b96  mov     edx, 8EDh; unsigned int
0x180027b9b  lea     rcx, aWindowsNetwork_62; "Windows::Networking::UX::Internal::MBCa"...
0x180027ba2  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180027ba7  xor     ebx, ebx
0x180027ba9  mov     rcx, [rsp+28h+string]; string
0x180027bae  call    cs:__imp_WindowsDeleteString
0x180027bb4  mov     eax, ebx
0x180027bb6  mov     rbx, [rsp+28h+arg_10]
0x180027bbb  add     rsp, 20h
0x180027bbf  pop     rdi
0x180027bc0  retn
```
