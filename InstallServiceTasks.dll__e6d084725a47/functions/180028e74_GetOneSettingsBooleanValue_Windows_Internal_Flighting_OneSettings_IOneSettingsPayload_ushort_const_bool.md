# _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)

- ea: `0x180028e74`
- end: `0x180028f5f`
- name: `?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z`
- size: `235`
- prototype: `void __fastcall(struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002e654`

## callees

- `0x180003450`
- `0x18000b48c`
- `0x180028e74`
- `0x1800291d8`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028eae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028f3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028ef3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180028ef3`

## string_xrefs

- `0x180028f26`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _GetOneSettingsBooleanValue(
        struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *a1,
        const unsigned __int16 *a2,
        bool *a3)
{
  __int64 (*v3)(void); // rbx
  char v4; // r8
  int v5; // ebx
  int v6; // [rsp+20h] [rbp-88h]
  const WCHAR *v7; // [rsp+58h] [rbp-50h] BYREF
  HSTRING_HEADER v8; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v7 = a2;
  v3 = *(__int64 (**)(void))(*(_QWORD *)a1 + 72LL);
  WindowsDeleteString(0);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v8, &v7, v4);
  try
  {
    v5 = v3();
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        (const char *)(unsigned int)v5,
        v6);
    WindowsDeleteString(0);
  }
  catch ( ... )
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x1F3u,
      "_GetOneSettingsBooleanValue",
      -1,
      L"Exception while reading OneSettings value for %s, using default value",
      0,
      0,
      v7);
  }
}

```

## disassembly

```asm
0x180028e74  push    rbx
0x180028e76  push    rsi
0x180028e77  push    rdi
0x180028e78  sub     rsp, 90h
0x180028e7f  mov     rax, cs:__security_cookie
0x180028e86  xor     rax, rsp
0x180028e89  mov     [rsp+0A8h+var_28], rax
0x180028e91  mov     rdi, r8
0x180028e94  mov     rsi, rcx
0x180028e97  mov     [rsp+0A8h+var_50], rdx
0x180028e9c  mov     [rsp+0A8h+string], 0
0x180028ea5  mov     rax, [rcx]
0x180028ea8  mov     rbx, [rax+48h]
0x180028eac  xor     ecx, ecx; string
0x180028eae  call    cs:__imp_WindowsDeleteString
0x180028eb4  mov     [rsp+0A8h+string], 0
0x180028ebd  lea     rdx, [rsp+0A8h+var_50]
0x180028ec2  lea     rcx, [rsp+0A8h+var_48]
0x180028ec7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180028ecc  nop
0x180028ecd  lea     r8, [rsp+0A8h+string]
0x180028ed2  mov     rdx, [rax+18h]
0x180028ed6  mov     rcx, rsi
0x180028ed9  mov     rax, rbx
0x180028edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ee1  mov     ebx, eax
0x180028ee3  test    eax, eax
0x180028ee5  js      short loc_180028F17
0x180028ee7  mov     rcx, [rsp+0A8h+string]; string
0x180028eec  test    rcx, rcx
0x180028eef  jz      short loc_180028F17
0x180028ef1  xor     edx, edx; length
0x180028ef3  call    cs:__imp_WindowsGetStringRawBuffer
0x180028ef9  mov     edx, 31h ; '1'
0x180028efe  movzx   ecx, word ptr [rax]
0x180028f01  sub     edx, ecx
0x180028f03  jnz     short loc_180028F10
0x180028f05  xor     ecx, ecx
0x180028f07  movzx   edx, cx
0x180028f0a  movzx   eax, word ptr [rax+2]
0x180028f0e  sub     edx, eax
0x180028f10  test    edx, edx
0x180028f12  setz    al
0x180028f15  mov     [rdi], al
0x180028f17  mov     rcx, [rsp+0A8h]; this
0x180028f1f  test    ebx, ebx
0x180028f21  jns     short loc_180028F38
0x180028f23  mov     r9d, ebx; char *
0x180028f26  lea     r8, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x180028f2d  mov     edx, 1EFh; void *
0x180028f32  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028f37  nop
0x180028f38  mov     rcx, [rsp+0A8h+string]; string
0x180028f3d  call    cs:__imp_WindowsDeleteString
0x180028f43  nop
0x180028f44  mov     rcx, [rsp+0A8h+var_28]
0x180028f4c  xor     rcx, rsp; StackCookie
0x180028f4f  call    __security_check_cookie
0x180028f54  add     rsp, 90h
0x180028f5b  pop     rdi
0x180028f5c  pop     rsi
0x180028f5d  pop     rbx
0x180028f5e  retn
```
