# AfdCompleteIrpList

- ea: `0x14001e120`
- end: `0x14001e26b`
- name: `AfdCompleteIrpList`
- size: `331`
- prototype: `void __fastcall(_QWORD **, __int64, NTSTATUS, __int64 (__fastcall *)())`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001b938`
- `0x14001ceb0`
- `0x14001d524`
- `0x140020970`
- `0x14003d6c0`

## callees

- `0x14001e120`
- `0x140072920`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001e1e2`
- `ntoskrnl!IofCompleteRequest` at `0x14001e1e2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e1b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e20c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e1b9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001e20c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e157`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e1f6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e157`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001e1f6`

## pseudocode

```c
void __fastcall AfdCompleteIrpList(_QWORD **a1, __int64 a2, NTSTATUS a3, __int64 (__fastcall *a4)())
{
  KSPIN_LOCK *v4; // rdi
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  IRP *v10; // rbp
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF

  v4 = (KSPIN_LOCK *)(a2 + 56);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a2 + 56), &LockHandle);
  while ( 1 )
  {
    v8 = *a1;
    if ( *a1 == a1 )
      break;
    if ( (_QWORD **)v8[1] != a1 || (v9 = (_QWORD *)*v8, *(_QWORD **)(*v8 + 8LL) != v8) )
      __fastfail(3u);
    *a1 = v9;
    v10 = (IRP *)(v8 - 21);
    v9[1] = a1;
    if ( _InterlockedExchange64(v8 - 8, 0) )
    {
      if ( !a4 || ((unsigned __int8 (__fastcall *)(_QWORD *))a4)(v8 - 21) )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( a3 || a4 != AfdBCleanupRecvIrpUponDisconnect )
        {
          v10->IoStatus.Status = a3;
          v10->IoStatus.Information = 0;
        }
        IofCompleteRequest(v10, AfdPriorityBoost);
        KeAcquireInStackQueuedSpinLock(v4, &LockHandle);
      }
    }
    else
    {
      *v8 = 0;
    }
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x14001e120  mov     [rsp+arg_8], rbx
0x14001e125  mov     [rsp+arg_10], rsi
0x14001e12a  push    rdi
0x14001e12b  push    r14
0x14001e12d  push    r15
0x14001e12f  sub     rsp, 40h
0x14001e133  lea     rdi, [rdx+38h]
0x14001e137  mov     rbx, rcx
0x14001e13a  xorps   xmm0, xmm0
0x14001e13d  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14001e142  xor     eax, eax
0x14001e144  mov     rcx, rdi; SpinLock
0x14001e147  mov     r14, r9
0x14001e14a  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14001e14f  mov     esi, r8d
0x14001e152  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14001e157  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001e15e  nop     dword ptr [rax+rax+00h]
0x14001e163  lea     r15, AfdBCleanupRecvIrpUponDisconnect
0x14001e16a  mov     [rsp+58h+arg_0], rbp
0x14001e16f  mov     rcx, [rbx]
0x14001e172  cmp     rcx, rbx
0x14001e175  jz      loc_14001E207
0x14001e17b  cmp     [rcx+8], rbx
0x14001e17f  jnz     loc_14001E264
0x14001e185  mov     rax, [rcx]
0x14001e188  cmp     [rax+8], rcx
0x14001e18c  jnz     loc_14001E264
0x14001e192  mov     [rbx], rax
0x14001e195  lea     rbp, [rcx-0A8h]
0x14001e19c  mov     [rax+8], rbx
0x14001e1a0  xor     eax, eax
0x14001e1a2  xchg    rax, [rbp+68h]
0x14001e1a6  test    rax, rax
0x14001e1a9  jz      loc_14001E24A
0x14001e1af  test    r14, r14
0x14001e1b2  jnz     short loc_14001E232
0x14001e1b4  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14001e1b9  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001e1c0  nop     dword ptr [rax+rax+00h]
0x14001e1c5  test    esi, esi
0x14001e1c7  jz      loc_14001E256
0x14001e1cd  mov     [rbp+30h], esi
0x14001e1d0  mov     qword ptr [rbp+38h], 0
0x14001e1d8  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x14001e1df  mov     rcx, rbp; Irp
0x14001e1e2  call    cs:__imp_IofCompleteRequest
0x14001e1e9  nop     dword ptr [rax+rax+00h]
0x14001e1ee  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14001e1f3  mov     rcx, rdi; SpinLock
0x14001e1f6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14001e1fd  nop     dword ptr [rax+rax+00h]
0x14001e202  jmp     loc_14001E16F
0x14001e207  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14001e20c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001e213  nop     dword ptr [rax+rax+00h]
0x14001e218  mov     rbp, [rsp+58h+arg_0]
0x14001e21d  mov     rbx, [rsp+58h+arg_8]
0x14001e222  mov     rsi, [rsp+58h+arg_10]
0x14001e227  add     rsp, 40h
0x14001e22b  pop     r15
0x14001e22d  pop     r14
0x14001e22f  pop     rdi
0x14001e230  retn
0x14001e232  mov     rcx, rbp
0x14001e235  mov     rax, r14
0x14001e238  call    _guard_dispatch_icall
0x14001e23d  test    al, al
0x14001e23f  jnz     loc_14001E1B4
0x14001e245  jmp     loc_14001E16F
0x14001e24a  mov     qword ptr [rcx], 0
0x14001e251  jmp     loc_14001E16F
0x14001e256  cmp     r14, r15
0x14001e259  jz      loc_14001E1D8
0x14001e25f  jmp     loc_14001E1CD
0x14001e264  mov     ecx, 3
0x14001e269  int     29h; Win8: RtlFailFast(ecx)
```
