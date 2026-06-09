# PrinterCleanupTask::Worker(void)

- ea: `0x1800066c0`
- end: `0x1800066f4`
- name: `?Worker@PrinterCleanupTask@@EEAAJXZ`
- size: `52`
- prototype: `__int64 __fastcall(PrinterCleanupTask *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1800066c0`
- `0x18000670c`
- `0x180014814`

## string_xrefs

- `0x1800066d5`: `printscan\print\shared\printercleanuptask\dll\printercleanuptask.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanupTask::Worker(PrinterCleanupTask *this)
{
  int v1; // eax
  const char *v2; // r9
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification(this);
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\dll\\printercleanuptask.cpp",
        (const char *)(unsigned int)v1,
        v4);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\dll\\printercleanuptask.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800066c0  sub     rsp, 28h
0x1800066c4  call    ?TryLaunchUnusedPrinterNotification@PrinterCleanUpUtil@@YAJXZ; PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification(void)
0x1800066c9  mov     rcx, [rsp+28h]; this
0x1800066ce  test    eax, eax
0x1800066d0  jns     short loc_1800066E6
0x1800066d2  mov     r9d, eax; char *
0x1800066d5  lea     r8, aPrintscanPrint_2; "printscan\\print\\shared\\printercleanu"...
0x1800066dc  mov     edx, 0Ah; void *
0x1800066e1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800066e6  xor     eax, eax
0x1800066e8  jmp     short loc_1800066EE
0x1800066ea  mov     eax, [rsp+28h+arg_8]
0x1800066ee  add     rsp, 28h
0x1800066f2  retn
```
