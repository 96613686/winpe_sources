# CPimcManager::TerminateHookThread(CHookThreadItem *)

- ea: `0x18000ac94`
- end: `0x18000ad0c`
- name: `?TerminateHookThread@CPimcManager@@SAXPEAUCHookThreadItem@@@Z`
- size: `120`
- prototype: `void __fastcall(struct CHookThreadItem *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ada8`
- `0x18000b39c`

## callees

- `0x180001360`
- `0x18000ac94`

## import_xrefs

- `KERNEL32!SignalObjectAndWait` at `0x18000acc4`
- `KERNEL32!SignalObjectAndWait` at `0x18000acc4`
- `USER32!UnhookWindowsHookEx` at `0x18000acaf`
- `USER32!UnhookWindowsHookEx` at `0x18000acaf`

## pseudocode

```c
void __fastcall CPimcManager::TerminateHookThread(struct CHookThreadItem *a1)
{
  HHOOK v2; // rcx

  v2 = (HHOOK)*((_QWORD *)a1 + 1);
  if ( v2 )
  {
    UnhookWindowsHookEx(v2);
    SignalObjectAndWait(*((HANDLE *)a1 + 9), *((HANDLE *)a1 + 10), 0xFFFFFFFF, 0);
    *((_QWORD *)a1 + 1) = 0;
    SafeCloseHandle((void **)a1 + 7);
    SafeCloseHandle((void **)a1 + 8);
    SafeCloseHandle((void **)a1 + 9);
    SafeCloseHandle((void **)a1 + 10);
    SafeCloseHandle((void **)a1 + 11);
  }
}

```

## disassembly

```asm
0x18000ac94  mov     [rsp+arg_0], rbx
0x18000ac99  mov     [rsp+arg_8], rsi
0x18000ac9e  push    rdi
0x18000ac9f  sub     rsp, 20h
0x18000aca3  mov     rsi, rcx
0x18000aca6  mov     rcx, [rcx+8]; hhk
0x18000acaa  test    rcx, rcx
0x18000acad  jz      short loc_18000ACFC
0x18000acaf  call    cs:__imp_UnhookWindowsHookEx
0x18000acb5  mov     rdx, [rsi+50h]; hObjectToWaitOn
0x18000acb9  xor     r9d, r9d; bAlertable
0x18000acbc  mov     rcx, [rsi+48h]; hObjectToSignal
0x18000acc0  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000acc4  call    cs:__imp_SignalObjectAndWait
0x18000acca  and     qword ptr [rsi+8], 0
0x18000accf  lea     rcx, [rsi+38h]; void **
0x18000acd3  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000acd8  lea     rcx, [rsi+40h]; void **
0x18000acdc  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000ace1  lea     rcx, [rsi+48h]; void **
0x18000ace5  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000acea  lea     rcx, [rsi+50h]; void **
0x18000acee  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000acf3  lea     rcx, [rsi+58h]; void **
0x18000acf7  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x18000acfc  mov     rbx, [rsp+28h+arg_0]
0x18000ad01  mov     rsi, [rsp+28h+arg_8]
0x18000ad06  add     rsp, 20h
0x18000ad0a  pop     rdi
0x18000ad0b  retn
```
