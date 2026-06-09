# CNetworkExplorerFolderViewCB::_StartTimer(void)

- ea: `0x18000ce34`
- end: `0x18000cecf`
- name: `?_StartTimer@CNetworkExplorerFolderViewCB@@AEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(CNetworkExplorerFolderViewCB *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000cc44`

## callees

- `0x18000ce34`
- `0x18000ced8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cea1`
- `KERNEL32!CreateTimerQueue` at `0x18000ce41`
- `KERNEL32!CreateTimerQueue` at `0x18000ce41`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000ce93`
- `KERNEL32!CreateTimerQueueTimer` at `0x18000ce93`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolderViewCB::_StartTimer(CNetworkExplorerFolderViewCB *this)
{
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  signed int v5; // eax

  TimerQueue = CreateTimerQueue();
  *((_QWORD *)this + 5) = TimerQueue;
  if ( TimerQueue )
    goto LABEL_14;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_14:
    if ( CreateTimerQueueTimer((PHANDLE)this + 6, *((HANDLE *)this + 5), ProgressBarHandler, this, 0x1F4u, 0x3E8u, 0) )
    {
      return 0;
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( v4 < 0 )
        CNetworkExplorerFolderViewCB::_StopTimer(this);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000ce34  mov     [rsp+arg_0], rbx
0x18000ce39  push    rdi
0x18000ce3a  sub     rsp, 40h
0x18000ce3e  mov     rdi, rcx
0x18000ce41  call    cs:__imp_CreateTimerQueue
0x18000ce47  mov     [rdi+28h], rax
0x18000ce4b  test    rax, rax
0x18000ce4e  jnz     short loc_18000CE69
0x18000ce50  call    cs:__imp_GetLastError
0x18000ce56  mov     ebx, eax
0x18000ce58  test    eax, eax
0x18000ce5a  jle     short loc_18000CE65
0x18000ce5c  movzx   ebx, ax
0x18000ce5f  or      ebx, 80070000h
0x18000ce65  test    ebx, ebx
0x18000ce67  js      short loc_18000CEC2
0x18000ce69  mov     rdx, [rdi+28h]; TimerQueue
0x18000ce6d  lea     rcx, [rdi+30h]; phNewTimer
0x18000ce71  mov     [rsp+48h+Flags], 0; Flags
0x18000ce79  lea     r8, ?ProgressBarHandler@@YAXPEAXE@Z; Callback
0x18000ce80  mov     [rsp+48h+Period], 3E8h; Period
0x18000ce88  mov     r9, rdi; Parameter
0x18000ce8b  mov     [rsp+48h+DueTime], 1F4h; DueTime
0x18000ce93  call    cs:__imp_CreateTimerQueueTimer
0x18000ce99  test    eax, eax
0x18000ce9b  jz      short loc_18000CEA1
0x18000ce9d  xor     ebx, ebx
0x18000ce9f  jmp     short loc_18000CEC2
0x18000cea1  call    cs:__imp_GetLastError
0x18000cea7  mov     ebx, eax
0x18000cea9  test    eax, eax
0x18000ceab  jle     short loc_18000CEB6
0x18000cead  movzx   ebx, ax
0x18000ceb0  or      ebx, 80070000h
0x18000ceb6  test    ebx, ebx
0x18000ceb8  jns     short loc_18000CEC2
0x18000ceba  mov     rcx, rdi; this
0x18000cebd  call    ?_StopTimer@CNetworkExplorerFolderViewCB@@AEAAJXZ; CNetworkExplorerFolderViewCB::_StopTimer(void)
0x18000cec2  mov     eax, ebx
0x18000cec4  mov     rbx, [rsp+48h+arg_0]
0x18000cec9  add     rsp, 40h
0x18000cecd  pop     rdi
0x18000cece  retn
```
