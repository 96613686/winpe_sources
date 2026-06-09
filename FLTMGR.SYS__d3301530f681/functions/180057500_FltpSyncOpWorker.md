# FltpSyncOpWorker

- ea: `0x180057500`
- end: `0x1800575c3`
- name: `FltpSyncOpWorker`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009f20`
- `0x18001bb10`
- `0x180024800`
- `0x1800248e0`
- `0x180057500`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x18005759e`
- `ntoskrnl!KeSetEvent` at `0x18005759e`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180057536`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x18005757f`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x180057536`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x18005757f`

## pseudocode

```c
LONG __fastcall FltpSyncOpWorker(__int64 a1)
{
  unsigned int v2; // ebx
  struct _IO_PRIORITY_INFO OutputPriorityInfo; // [rsp+20h] [rbp-28h] BYREF

  OutputPriorityInfo = 0;
  v2 = IoApplyPriorityInfoThread((PIO_PRIORITY_INFO)(a1 + 88), &OutputPriorityInfo, KeGetCurrentThread());
  *(_DWORD *)(a1 + 80) = (*(__int64 (__fastcall **)(_QWORD))(a1 + 40))(*(_QWORD *)(a1 + 48));
  if ( (int)FltpDbgStatus(v2, "minkernel\\fs\\filtermgr\\filter\\worksup.c", 1132, 0) >= 0 )
    IoApplyPriorityInfoThread(&OutputPriorityInfo, 0, KeGetCurrentThread());
  FltpDequeueThrottledWorkItem(*(unsigned int *)(a1 + 84));
  return KeSetEvent((PRKEVENT)(a1 + 56), 1, 0);
}

```

## disassembly

```asm
0x180057500  mov     [rsp+arg_8], rbx
0x180057505  push    rdi
0x180057506  sub     rsp, 40h
0x18005750a  mov     rax, cs:__security_cookie
0x180057511  xor     rax, rsp
0x180057514  mov     [rsp+48h+var_18], rax
0x180057519  xorps   xmm0, xmm0
0x18005751c  lea     rdx, [rsp+48h+OutputPriorityInfo]; OutputPriorityInfo
0x180057521  movups  xmmword ptr [rsp+48h+OutputPriorityInfo.Size], xmm0
0x180057526  mov     r8, gs:188h; Thread
0x18005752f  mov     rdi, rcx
0x180057532  add     rcx, 58h ; 'X'; InputPriorityInfo
0x180057536  call    cs:__imp_IoApplyPriorityInfoThread
0x18005753d  nop     dword ptr [rax+rax+00h]
0x180057542  mov     rcx, [rdi+30h]
0x180057546  mov     ebx, eax
0x180057548  mov     rax, [rdi+28h]
0x18005754c  call    _guard_dispatch_icall
0x180057551  mov     r8d, 46Ch
0x180057557  mov     [rdi+50h], eax
0x18005755a  xor     r9d, r9d
0x18005755d  lea     rdx, aMinkernelFsFil_5; "minkernel\\fs\\filtermgr\\filter\\works"...
0x180057564  mov     ecx, ebx
0x180057566  call    FltpDbgStatus
0x18005756b  test    eax, eax
0x18005756d  js      short loc_18005758B
0x18005756f  mov     r8, gs:188h; Thread
0x180057578  lea     rcx, [rsp+48h+OutputPriorityInfo]; InputPriorityInfo
0x18005757d  xor     edx, edx; OutputPriorityInfo
0x18005757f  call    cs:__imp_IoApplyPriorityInfoThread
0x180057586  nop     dword ptr [rax+rax+00h]
0x18005758b  mov     ecx, [rdi+54h]
0x18005758e  call    FltpDequeueThrottledWorkItem
0x180057593  xor     r8d, r8d; Wait
0x180057596  lea     rcx, [rdi+38h]; Event
0x18005759a  lea     edx, [r8+1]; Increment
0x18005759e  call    cs:__imp_KeSetEvent
0x1800575a5  nop     dword ptr [rax+rax+00h]
0x1800575aa  mov     rcx, [rsp+48h+var_18]
0x1800575af  xor     rcx, rsp; StackCookie
0x1800575b2  call    __security_check_cookie
0x1800575b7  mov     rbx, [rsp+48h+arg_8]
0x1800575bc  add     rsp, 40h
0x1800575c0  pop     rdi
0x1800575c1  retn
```
