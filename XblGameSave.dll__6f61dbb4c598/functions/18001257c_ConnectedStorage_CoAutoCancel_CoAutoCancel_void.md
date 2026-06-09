# ConnectedStorage::CoAutoCancel::~CoAutoCancel(void)

- ea: `0x18001257c`
- end: `0x1800125bb`
- name: `??1CoAutoCancel@ConnectedStorage@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(ConnectedStorage::CoAutoCancel *__hidden this)`
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016a40`
- `0x180019540`
- `0x180019660`
- `0x1800261d0`
- `0x180035e20`
- `0x18004ae14`
- `0x18004c830`
- `0x18004c8b0`
- `0x18004c900`
- `0x18005e8e4`
- `0x18006d2a0`
- `0x18006d4ec`
- `0x18006d74c`
- `0x18006d9b0`
- `0x18006dbf0`
- `0x18006dd64`
- `0x18006de64`
- `0x180076968`
- `0x18008678e`
- `0x18008a355`
- `0x18008be22`
- `0x18008be6a`

## callees

- `0x18001257c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800125af`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x1800125af`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180012593`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180012593`

## pseudocode

```c
void __fastcall ConnectedStorage::CoAutoCancel::~CoAutoCancel(HANDLE *this)
{
  if ( *this )
  {
    DeleteTimerQueueTimer(0, *this, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *this = 0;
  }
  if ( *((_DWORD *)this + 2) )
  {
    *((_DWORD *)this + 2) = 0;
    CoDisableCallCancellation(0);
  }
}

```

## disassembly

```asm
0x18001257c  push    rbx
0x18001257e  sub     rsp, 20h
0x180012582  mov     rdx, [rcx]; Timer
0x180012585  mov     rbx, rcx
0x180012588  test    rdx, rdx
0x18001258b  jz      short loc_1800125A0
0x18001258d  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180012591  xor     ecx, ecx; TimerQueue
0x180012593  call    cs:__imp_DeleteTimerQueueTimer
0x180012599  mov     qword ptr [rbx], 0
0x1800125a0  cmp     dword ptr [rbx+8], 0
0x1800125a4  jz      short loc_1800125B5
0x1800125a6  xor     ecx, ecx; pReserved
0x1800125a8  mov     dword ptr [rbx+8], 0
0x1800125af  call    cs:__imp_CoDisableCallCancellation
0x1800125b5  add     rsp, 20h
0x1800125b9  pop     rbx
0x1800125ba  retn
```
