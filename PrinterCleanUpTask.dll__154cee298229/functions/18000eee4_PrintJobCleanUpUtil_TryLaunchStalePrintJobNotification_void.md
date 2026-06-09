# PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification(void)

- ea: `0x18000eee4`
- end: `0x18000ef45`
- name: `?TryLaunchStalePrintJobNotification@PrintJobCleanUpUtil@@YAJXZ`
- size: `97`
- prototype: `__int64 __fastcall(PrintJobCleanUpUtil *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180006730`

## callees

- `0x18000670c`
- `0x18000b11c`
- `0x18000d424`
- `0x18000eee4`
- `0x180010470`

## string_xrefs

- `0x18000ef04`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000ef26`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrintJobCleanUpUtil::TryLaunchStalePrintJobNotification(PrintJobCleanUpUtil *this)
{
  PrintJobCleanUpUtil *v1; // rcx
  int v2; // eax
  const char *v3; // r9
  int v4; // eax
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( AreAllPrintQueueEmpty() )
    {
      v2 = EnablePrintJobCleanupTask(0);
      if ( v2 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x15B,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
          (const char *)(unsigned int)v2,
          v6);
    }
    else
    {
      v4 = PrintJobCleanUpUtil::LaunchStalePrintJobNotification(v1);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x15F,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
          (const char *)(unsigned int)v4,
          v6);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x163,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000eee4  sub     rsp, 28h
0x18000eee8  call    ?AreAllPrintQueueEmpty@@YA_NXZ; AreAllPrintQueueEmpty(void)
0x18000eeed  test    al, al
0x18000eeef  jz      short loc_18000EF15
0x18000eef1  xor     ecx, ecx
0x18000eef3  call    EnablePrintJobCleanupTask
0x18000eef8  mov     rcx, [rsp+28h]; this
0x18000eefd  test    eax, eax
0x18000eeff  jns     short loc_18000EF37
0x18000ef01  mov     r9d, eax; char *
0x18000ef04  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000ef0b  mov     edx, 15Bh; void *
0x18000ef10  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ef15  call    ?LaunchStalePrintJobNotification@PrintJobCleanUpUtil@@YAJXZ; PrintJobCleanUpUtil::LaunchStalePrintJobNotification(void)
0x18000ef1a  mov     rcx, [rsp+28h]; this
0x18000ef1f  test    eax, eax
0x18000ef21  jns     short loc_18000EF37
0x18000ef23  mov     r9d, eax; char *
0x18000ef26  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000ef2d  mov     edx, 15Fh; void *
0x18000ef32  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000ef37  xor     eax, eax
0x18000ef39  jmp     short loc_18000EF3F
0x18000ef3b  mov     eax, [rsp+28h+arg_0]
0x18000ef3f  add     rsp, 28h
0x18000ef43  retn
```
