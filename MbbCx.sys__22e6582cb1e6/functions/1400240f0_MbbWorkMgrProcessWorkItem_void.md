# MbbWorkMgrProcessWorkItem(void *)

- ea: `0x1400240f0`
- end: `0x140024266`
- name: `?MbbWorkMgrProcessWorkItem@@YAXPEAX@Z`
- size: `374`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14001ddf4`
- `0x1400240f0`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x140024249`
- `ntoskrnl!PsTerminateSystemThread` at `0x140024249`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140024233`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140024233`
- `ntoskrnl!KeResetEvent` at `0x14002419b`
- `ntoskrnl!KeResetEvent` at `0x14002419b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400241ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400241ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024137`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024137`

## pseudocode

```c
void __fastcall MbbWorkMgrProcessWorkItem(char *StartContext)
{
  struct _KEVENT *v1; // rsi
  char *v3; // rax
  void ***v4; // rcx
  _QWORD *v5; // rcx
  void **v6; // rbx
  __int64 v7; // rax
  NTSTATUS v8; // eax
  void *v9[2]; // [rsp+40h] [rbp-28h] BYREF
  PVOID Object[3]; // [rsp+50h] [rbp-18h] BYREF

  v1 = (struct _KEVENT *)(StartContext + 48);
  Object[0] = StartContext + 24;
  *(_OWORD *)v9 = 0;
  Object[1] = StartContext + 48;
LABEL_11:
  while ( 1 )
  {
    v8 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 1u, 0, 0);
    if ( !v8 )
      break;
    if ( v8 == 1 )
    {
      v9[1] = v9;
      v9[0] = v9;
      StartContext[8] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)StartContext);
      v3 = StartContext + 72;
      v4 = (void ***)*((_QWORD *)StartContext + 10);
      if ( *v4 == (void **)(StartContext + 72) )
      {
        v9[1] = *((void **)StartContext + 10);
        v9[0] = StartContext + 72;
        *v4 = v9;
        *((_QWORD *)StartContext + 10) = v9;
        v5 = *(_QWORD **)v3;
        if ( *(char **)(*(_QWORD *)v3 + 8LL) == v3 && v9[0] == v3 )
        {
          v9[0] = *(void **)v3;
          v5[1] = v9;
          *((_QWORD *)StartContext + 10) = v3;
          *(_QWORD *)v3 = v3;
          KeResetEvent(v1);
          KeReleaseSpinLock((PKSPIN_LOCK)StartContext, StartContext[8]);
          while ( 1 )
          {
            v6 = (void **)v9[0];
            if ( *((void ***)v9[0] + 1) != v9 )
              break;
            v7 = *(_QWORD *)v9[0];
            if ( *(void **)(*(_QWORD *)v9[0] + 8LL) != v9[0] )
              break;
            v9[0] = *(void **)v9[0];
            *(_QWORD *)(v7 + 8) = v9;
            if ( v6 == v9 )
              goto LABEL_11;
            ((void (__fastcall *)(void *, void *, void *, void *))v6[6])(v6[2], v6[3], v6[4], v6[5]);
            MbbAllocMgrFree(v6);
          }
        }
      }
      __fastfail(3u);
    }
  }
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x1400240f0  push    rbp
0x1400240f2  push    rbx
0x1400240f3  push    rsi
0x1400240f4  push    rdi
0x1400240f5  mov     rbp, rsp
0x1400240f8  sub     rsp, 68h
0x1400240fc  xorps   xmm0, xmm0
0x1400240ff  lea     rax, [rcx+18h]
0x140024103  lea     rsi, [rcx+30h]
0x140024107  mov     [rbp+Object], rax
0x14002410b  movups  xmmword ptr [rbp+var_28], xmm0
0x14002410f  mov     [rbp+var_10], rsi
0x140024113  mov     rdi, rcx
0x140024116  jmp     loc_140024208
0x14002411b  cmp     eax, 1
0x14002411e  jnz     loc_140024208
0x140024124  lea     rax, [rbp+var_28]
0x140024128  mov     rcx, rdi; SpinLock
0x14002412b  mov     [rbp+var_28+8], rax
0x14002412f  lea     rax, [rbp+var_28]
0x140024133  mov     [rbp+var_28], rax
0x140024137  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002413e  nop     dword ptr [rax+rax+00h]
0x140024143  mov     [rdi+8], al
0x140024146  lea     rax, [rdi+48h]
0x14002414a  mov     rcx, [rax+8]
0x14002414e  cmp     [rcx], rax
0x140024151  jnz     loc_14002425F
0x140024157  mov     [rbp+var_28+8], rcx
0x14002415b  lea     rdx, [rbp+var_28]
0x14002415f  mov     [rbp+var_28], rax
0x140024163  mov     [rcx], rdx
0x140024166  lea     rcx, [rbp+var_28]
0x14002416a  mov     [rax+8], rcx
0x14002416e  mov     rcx, [rax]
0x140024171  cmp     [rcx+8], rax
0x140024175  jnz     loc_14002425F
0x14002417b  cmp     [rbp+var_28], rax
0x14002417f  jnz     loc_14002425F
0x140024185  mov     [rbp+var_28], rcx
0x140024189  lea     rdx, [rbp+var_28]
0x14002418d  mov     [rcx+8], rdx
0x140024191  mov     rcx, rsi; Event
0x140024194  mov     [rdi+50h], rax
0x140024198  mov     [rax], rax
0x14002419b  call    cs:__imp_KeResetEvent
0x1400241a2  nop     dword ptr [rax+rax+00h]
0x1400241a7  mov     dl, [rdi+8]; NewIrql
0x1400241aa  mov     rcx, rdi; SpinLock
0x1400241ad  call    cs:__imp_KeReleaseSpinLock
0x1400241b4  nop     dword ptr [rax+rax+00h]
0x1400241b9  jmp     short loc_1400241DC
0x1400241bb  mov     rax, [rbx+30h]
0x1400241bf  mov     r9, [rbx+28h]
0x1400241c3  mov     r8, [rbx+20h]
0x1400241c7  mov     rdx, [rbx+18h]
0x1400241cb  mov     rcx, [rbx+10h]
0x1400241cf  call    _guard_dispatch_icall
0x1400241d4  mov     rcx, rbx; void *
0x1400241d7  call    ?MbbAllocMgrFree@@YAXPEAX@Z; MbbAllocMgrFree(void *)
0x1400241dc  mov     rbx, [rbp+var_28]
0x1400241e0  lea     rax, [rbp+var_28]
0x1400241e4  cmp     [rbx+8], rax
0x1400241e8  jnz     short loc_14002425F
0x1400241ea  mov     rax, [rbx]
0x1400241ed  cmp     [rax+8], rbx
0x1400241f1  jnz     short loc_14002425F
0x1400241f3  mov     [rbp+var_28], rax
0x1400241f7  lea     rcx, [rbp+var_28]
0x1400241fb  mov     [rax+8], rcx
0x1400241ff  lea     rax, [rbp+var_28]
0x140024203  cmp     rbx, rax
0x140024206  jnz     short loc_1400241BB
0x140024208  xor     r9d, r9d; WaitReason
0x14002420b  mov     [rsp+68h+WaitBlockArray], 0; WaitBlockArray
0x140024214  mov     [rsp+68h+Timeout], 0; Timeout
0x14002421d  lea     rdx, [rbp+Object]; Object
0x140024221  mov     [rsp+68h+Alertable], 1; Alertable
0x140024226  mov     [rsp+68h+WaitMode], 0; WaitMode
0x14002422b  lea     r8d, [r9+1]; WaitType
0x14002422f  lea     ecx, [r9+2]; Count
0x140024233  call    cs:__imp_KeWaitForMultipleObjects
0x14002423a  nop     dword ptr [rax+rax+00h]
0x14002423f  test    eax, eax
0x140024241  jnz     loc_14002411B
0x140024247  xor     ecx, ecx; ExitStatus
0x140024249  call    cs:__imp_PsTerminateSystemThread
0x140024250  nop     dword ptr [rax+rax+00h]
0x140024255  add     rsp, 68h
0x140024259  pop     rdi
0x14002425a  pop     rsi
0x14002425b  pop     rbx
0x14002425c  pop     rbp
0x14002425d  retn
0x14002425f  mov     ecx, 3
0x140024264  int     29h; Win8: RtlFailFast(ecx)
```
