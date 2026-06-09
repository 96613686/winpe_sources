# _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)

- ea: `0x18009f15c`
- end: `0x18009f251`
- name: `?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z`
- size: `245`
- prototype: `void __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f05c`

## callees

- `0x180035afc`
- `0x180075e60`
- `0x18008a17c`
- `0x18009f15c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f1de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f1de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f22a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f22a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _GetOneSettingsBooleanValue(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1,
        const unsigned __int16 *a2,
        bool *a3)
{
  __int64 (*v3)(void); // rbx
  int v4; // ebx
  int v5; // [rsp+20h] [rbp-68h]
  const wchar_t *v6; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v6 = L"DISABLESHADOWADMININLICENSEMANAGER";
  v3 = *(__int64 (**)(void))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v7, &v6);
  try
  {
    v4 = v3();
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licensemanagersettings.cpp",
        (const char *)(unsigned int)v4,
        v5);
    WindowsDeleteString(0);
  }
  catch ( ... )
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\licensemanagersettings.cpp",
      0x20u,
      "_GetOneSettingsBooleanValue",
      (wchar_t *)L"Exception while reading OneSettings value for %s, using default value",
      L"DISABLESHADOWADMININLICENSEMANAGER");
  }
}

```

## disassembly

```asm
0x18009f15c  mov     [rsp+arg_8], rbx
0x18009f161  push    rdi
0x18009f162  sub     rsp, 80h
0x18009f169  mov     rax, cs:__security_cookie
0x18009f170  xor     rax, rsp
0x18009f173  mov     [rsp+88h+var_18], rax
0x18009f178  mov     rdi, rcx
0x18009f17b  lea     rax, aDisableshadowa; "DISABLESHADOWADMININLICENSEMANAGER"
0x18009f182  mov     [rsp+88h+var_48], rax
0x18009f187  mov     [rsp+88h+string], 0
0x18009f190  mov     rax, [rcx]
0x18009f193  mov     rbx, [rax+48h]
0x18009f197  xor     ecx, ecx; string
0x18009f199  call    cs:__imp_WindowsDeleteString
0x18009f19f  mov     [rsp+88h+string], 0
0x18009f1a8  lea     rdx, [rsp+88h+var_48]
0x18009f1ad  lea     rcx, [rsp+88h+var_38]
0x18009f1b2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009f1b7  nop
0x18009f1b8  lea     r8, [rsp+88h+string]
0x18009f1bd  mov     rdx, [rax+18h]
0x18009f1c1  mov     rcx, rdi
0x18009f1c4  mov     rax, rbx
0x18009f1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f1cc  mov     ebx, eax
0x18009f1ce  test    eax, eax
0x18009f1d0  js      short loc_18009F204
0x18009f1d2  mov     rcx, [rsp+88h+string]; string
0x18009f1d7  test    rcx, rcx
0x18009f1da  jz      short loc_18009F204
0x18009f1dc  xor     edx, edx; length
0x18009f1de  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f1e4  mov     edx, 31h ; '1'
0x18009f1e9  movzx   ecx, word ptr [rax]
0x18009f1ec  sub     edx, ecx
0x18009f1ee  jnz     short loc_18009F1FB
0x18009f1f0  xor     ecx, ecx
0x18009f1f2  movzx   edx, cx
0x18009f1f5  movzx   eax, word ptr [rax+2]
0x18009f1f9  sub     edx, eax
0x18009f1fb  test    edx, edx
0x18009f1fd  setz    cs:byte_1800F297C
0x18009f204  mov     rcx, [rsp+88h]; this
0x18009f20c  test    ebx, ebx
0x18009f20e  jns     short loc_18009F225
0x18009f210  mov     r9d, ebx; char *
0x18009f213  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\licensem"...
0x18009f21a  mov     edx, 1Ch; void *
0x18009f21f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009f224  nop
0x18009f225  mov     rcx, [rsp+88h+string]; string
0x18009f22a  call    cs:__imp_WindowsDeleteString
0x18009f230  nop
0x18009f231  jmp     short $+2
0x18009f233  mov     rcx, [rsp+88h+var_18]
0x18009f238  xor     rcx, rsp; StackCookie
0x18009f23b  call    __security_check_cookie
0x18009f240  mov     rbx, [rsp+88h+arg_8]
0x18009f248  add     rsp, 80h
0x18009f24f  pop     rdi
0x18009f250  retn
```
