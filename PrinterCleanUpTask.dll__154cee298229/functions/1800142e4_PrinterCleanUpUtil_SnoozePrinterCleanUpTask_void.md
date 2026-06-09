# PrinterCleanUpUtil::SnoozePrinterCleanUpTask(void)

- ea: `0x1800142e4`
- end: `0x180014355`
- name: `?SnoozePrinterCleanUpTask@PrinterCleanUpUtil@@YAJXZ`
- size: `113`
- prototype: `__int64 __fastcall(PrinterCleanUpUtil *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180011d8c`

## callees

- `0x18000c31c`
- `0x1800142e4`
- `0x180014d84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014330`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180014330`

## string_xrefs

- `0x180014322`: `SYSTEM\CurrentControlSet\Control\Print\PrinterCleanupTask\`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::SnoozePrinterCleanUpTask(PrinterCleanUpUtil *this)
{
  unsigned int v1; // eax
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  __int64 result; // rax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _FILETIME Data; // [rsp+40h] [rbp+8h] BYREF

  Data = GetCurrentFileTime();
  v1 = RegSetKeyValueW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Print\\PrinterCleanupTask\\",
         L"SnoozeDate",
         0xBu,
         &Data,
         8u);
  try
  {
    if ( v1 )
      wil::details::in1diag3::_Throw_Win32(retaddr, v2, v3, (const char *)v1, lpData);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE3,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800142e4  sub     rsp, 38h
0x1800142e8  call    ?GetCurrentFileTime@@YA?AU_FILETIME@@XZ; GetCurrentFileTime(void)
0x1800142ed  mov     dword ptr [rsp+38h+Data], eax
0x1800142f1  shr     rax, 20h
0x1800142f5  mov     dword ptr [rsp+38h+Data+4], eax
0x1800142f9  mov     rax, [rsp+38h+Data]
0x1800142fe  mov     [rsp+38h+Data], rax
0x180014303  mov     [rsp+38h+cbData], 8; cbData
0x18001430b  lea     rax, [rsp+38h+Data]
0x180014310  mov     [rsp+38h+lpData], rax; unsigned int
0x180014315  mov     r9d, 0Bh; dwType
0x18001431b  lea     r8, ValueName; "SnoozeDate"
0x180014322  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x180014329  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014330  call    cs:__imp_RegSetKeyValueW
0x180014336  mov     rcx, [rsp+38h]; this
0x18001433b  test    eax, eax
0x18001433d  jz      short loc_180014347
0x18001433f  mov     r9d, eax; char *
0x180014342  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180014347  xor     eax, eax
0x180014349  jmp     short loc_18001434F
0x18001434b  mov     eax, dword ptr [rsp+38h+Data]
0x18001434f  add     rsp, 38h
0x180014353  retn
```
