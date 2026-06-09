# PrintJobCleanupTask::Worker(void)

- ea: `0x180006730`
- end: `0x180006764`
- name: `?Worker@PrintJobCleanupTask@@EEAAJXZ`
- size: `52`
- prototype: `__int64 __fastcall(PrintJobCleanupTask *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18000670c`
- `0x180006730`
- `0x18000eee4`

## string_xrefs

- `0x180006745`: `printscan\print\shared\printercleanuptask\dll\printjobcleanuptask.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanupTask::Worker(PrintJobCleanupTask *this)
{
  int v1; // eax
  const char *v2; // r9
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification(this);
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\dll\\printjobcleanuptask.cpp",
        (const char *)(unsigned int)v1,
        v4);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\dll\\printjobcleanuptask.cpp",
                           v2);
  }
  return result;
}

```

## disassembly

```asm
0x180006730  sub     rsp, 28h
0x180006734  call    ?TryLaunchStalePrintJobNotification@PrintJobCleanUpUtil@@YAJXZ; PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification(void)
0x180006739  mov     rcx, [rsp+28h]; this
0x18000673e  test    eax, eax
0x180006740  jns     short loc_180006756
0x180006742  mov     r9d, eax; char *
0x180006745  lea     r8, aPrintscanPrint_0; "printscan\\print\\shared\\printercleanu"...
0x18000674c  mov     edx, 0Ah; void *
0x180006751  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180006756  xor     eax, eax
0x180006758  jmp     short loc_18000675E
0x18000675a  mov     eax, [rsp+28h+arg_8]
0x18000675e  add     rsp, 28h
0x180006762  retn
```
