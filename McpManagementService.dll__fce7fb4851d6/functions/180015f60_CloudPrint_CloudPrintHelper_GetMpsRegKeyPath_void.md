# CloudPrint::CloudPrintHelper::GetMpsRegKeyPath(void)

- ea: `0x180015f60`
- end: `0x180016014`
- name: `?GetMpsRegKeyPath@CloudPrintHelper@CloudPrint@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `180`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800098d8`
- `0x1800193bc`
- `0x1800194dc`

## callees

- `0x180003a60`
- `0x180011de0`
- `0x18001baec`
- `0x18001c0a8`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015fa5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180015fa5`

## string_xrefs

- `0x180015fc2`: `GetPersistedRegistryLocationW failed to get regkey location path`
- `0x180015fd8`: `MpsRegKeyPath=%s`
- `0x180015fdf`: `CloudPrint::CloudPrintHelper::GetMpsRegKeyPath`

## pseudocode

```c
__int64 __fastcall CloudPrint::CloudPrintHelper::GetMpsRegKeyPath(__int64 a1)
{
  unsigned int PersistedRegistryLocationW; // eax
  const char *v4; // [rsp+28h] [rbp-240h]
  _BYTE v5[528]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"CloudPrintMPSKey",
                                 L"Software\\Microsoft\\Print\\MPS",
                                 v5,
                                 520,
                                 0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x710,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
    (const char *)PersistedRegistryLocationW,
    (unsigned int)"GetPersistedRegistryLocationW failed to get regkey location path",
    v4);
  CloudPrintHelperTelemetry::WriteDbgTraceInfo(
    "CloudPrint::CloudPrintHelper::GetMpsRegKeyPath",
    L"MpsRegKeyPath=%s",
    v5);
  std::wstring::wstring(a1, v5);
  return a1;
}

```

## disassembly

```asm
0x180015f60  push    rbx
0x180015f62  sub     rsp, 260h
0x180015f69  mov     rax, cs:__security_cookie
0x180015f70  xor     rax, rsp
0x180015f73  mov     [rsp+268h+var_18], rax
0x180015f7b  mov     rbx, rcx
0x180015f7e  mov     [rsp+268h+var_230], rcx
0x180015f83  lea     rcx, aCloudprintmpsk; "CloudPrintMPSKey"
0x180015f8a  mov     qword ptr [rsp+268h+var_248], 0
0x180015f93  mov     r9d, 208h
0x180015f99  lea     r8, [rsp+268h+var_228]
0x180015f9e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Print\\MPS"
0x180015fa5  call    cs:__imp_GetPersistedRegistryLocationW
0x180015fab  mov     rcx, [rsp+268h]; this
0x180015fb3  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180015fba  mov     r9d, eax; char *
0x180015fbd  mov     edx, 710h; void *
0x180015fc2  lea     rax, aGetpersistedre; "GetPersistedRegistryLocationW failed to"...
0x180015fc9  mov     qword ptr [rsp+268h+var_248], rax; unsigned int
0x180015fce  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180015fd3  lea     r8, [rsp+268h+var_228]
0x180015fd8  lea     rdx, aMpsregkeypathS; "MpsRegKeyPath=%s"
0x180015fdf  lea     rcx, aCloudprintClou_2; "CloudPrint::CloudPrintHelper::GetMpsReg"...
0x180015fe6  call    ?WriteDbgTraceInfo@CloudPrintHelperTelemetry@@SAXPEADPEAGZZ; CloudPrintHelperTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180015feb  lea     rdx, [rsp+268h+var_228]
0x180015ff0  mov     rcx, rbx
0x180015ff3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015ff8  mov     rax, rbx
0x180015ffb  mov     rcx, [rsp+268h+var_18]
0x180016003  xor     rcx, rsp; StackCookie
0x180016006  call    __security_check_cookie
0x18001600b  add     rsp, 260h
0x180016012  pop     rbx
0x180016013  retn
```
