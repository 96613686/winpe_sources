# ServiceManager::ResetOperationState(void)

- ea: `0x18001b79c`
- end: `0x18001b840`
- name: `?ResetOperationState@ServiceManager@@AEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800142c4`
- `0x18001aea4`

## callees

- `0x18001b79c`
- `0x180022658`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001b834`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001b834`

## string_xrefs

- `0x18001b825`: `ServiceManager::ResetOperationState`

## pseudocode

```c
void __fastcall ServiceManager::ResetOperationState(ServiceManager *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  int v4; // eax

  *((_QWORD *)this + 440) = 0;
  *((_DWORD *)this + 1090) = -1;
  v2 = *((_QWORD *)this + 434);
  if ( v2 != *((_QWORD *)this + 435) )
    *((_QWORD *)this + 435) = v2;
  v3 = *((_QWORD *)this + 437);
  if ( v3 != *((_QWORD *)this + 438) )
    *((_QWORD *)this + 438) = v3;
  *(_WORD *)((char *)this + 4313) = 0;
  *(_QWORD *)((char *)this + 4332) = 0;
  *((_QWORD *)this + 543) = 0;
  *((_QWORD *)this + 544) = 0;
  v4 = TimerQueue::CancelAll((ServiceManager *)((char *)this + 4280));
  if ( v4 < 0 )
    ZTraceReportIgnore(v4, "ServiceManager::ResetOperationState", 713, this);
}

```

## disassembly

```asm
0x18001b79c  push    rbx
0x18001b79e  sub     rsp, 20h
0x18001b7a2  mov     qword ptr [rcx+0DC0h], 0
0x18001b7ad  mov     rbx, rcx
0x18001b7b0  mov     dword ptr [rcx+1108h], 0FFFFFFFFh
0x18001b7ba  mov     rax, [rcx+0D90h]
0x18001b7c1  cmp     rax, [rcx+0D98h]
0x18001b7c8  jz      short loc_18001B7D1
0x18001b7ca  mov     [rcx+0D98h], rax
0x18001b7d1  mov     rax, [rcx+0DA8h]
0x18001b7d8  cmp     rax, [rcx+0DB0h]
0x18001b7df  jz      short loc_18001B7E8
0x18001b7e1  mov     [rcx+0DB0h], rax
0x18001b7e8  mov     word ptr [rcx+10D9h], 0
0x18001b7f1  mov     qword ptr [rcx+10ECh], 0
0x18001b7fc  mov     qword ptr [rcx+10F8h], 0
0x18001b807  mov     qword ptr [rcx+1100h], 0
0x18001b812  add     rcx, 10B8h; this
0x18001b819  call    ?CancelAll@TimerQueue@@QEAAJXZ; TimerQueue::CancelAll(void)
0x18001b81e  test    eax, eax
0x18001b820  jns     short loc_18001B83A
0x18001b822  mov     r9, rbx
0x18001b825  lea     rdx, aServicemanager_67; "ServiceManager::ResetOperationState"
0x18001b82c  mov     r8d, 2C9h
0x18001b832  mov     ecx, eax
0x18001b834  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001b83a  add     rsp, 20h
0x18001b83e  pop     rbx
0x18001b83f  retn
```
