# DIGEST_AUTH_PROVIDER::TerminateInstance(void)

- ea: `0x1800046d8`
- end: `0x18000477e`
- name: `?TerminateInstance@DIGEST_AUTH_PROVIDER@@QEAAXXZ`
- size: `166`
- prototype: `void __fastcall(DIGEST_AUTH_PROVIDER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fb0`
- `0x180004650`

## callees

- `0x1800046d8`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800046fd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004744`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800046fd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180004744`

## pseudocode

```c
void __fastcall DIGEST_AUTH_PROVIDER::TerminateInstance(DIGEST_AUTH_PROVIDER *this)
{
  __int64 v1; // rdi
  void *v3; // rdx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  __int64 v5; // rdi
  void *v6; // rdx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    v3 = *(void **)(v1 + 88);
    if ( v3 )
    {
      DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *(_QWORD *)(v1 + 88) = 0;
    }
    v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
    if ( v4 )
      (**v4)(v4, 1);
    *((_QWORD *)this + 2) = 0;
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    v6 = *(void **)(v5 + 88);
    if ( v6 )
    {
      DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *(_QWORD *)(v5 + 88) = 0;
    }
    v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
    if ( v7 )
      (**v7)(v7, 1);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x1800046d8  mov     [rsp+arg_0], rbx
0x1800046dd  push    rdi
0x1800046de  sub     rsp, 20h
0x1800046e2  mov     rdi, [rcx+10h]
0x1800046e6  mov     rbx, rcx
0x1800046e9  test    rdi, rdi
0x1800046ec  jz      short loc_18000472C
0x1800046ee  mov     rdx, [rdi+58h]; Timer
0x1800046f2  test    rdx, rdx
0x1800046f5  jz      short loc_18000470B
0x1800046f7  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800046fb  xor     ecx, ecx; TimerQueue
0x1800046fd  call    cs:__imp_DeleteTimerQueueTimer
0x180004703  mov     qword ptr [rdi+58h], 0
0x18000470b  mov     rcx, [rbx+10h]
0x18000470f  test    rcx, rcx
0x180004712  jz      short loc_180004724
0x180004714  mov     rax, [rcx]
0x180004717  mov     edx, 1
0x18000471c  mov     rax, [rax]
0x18000471f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004724  mov     qword ptr [rbx+10h], 0
0x18000472c  mov     rdi, [rbx+18h]
0x180004730  test    rdi, rdi
0x180004733  jz      short loc_180004773
0x180004735  mov     rdx, [rdi+58h]; Timer
0x180004739  test    rdx, rdx
0x18000473c  jz      short loc_180004752
0x18000473e  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180004742  xor     ecx, ecx; TimerQueue
0x180004744  call    cs:__imp_DeleteTimerQueueTimer
0x18000474a  mov     qword ptr [rdi+58h], 0
0x180004752  mov     rcx, [rbx+18h]
0x180004756  test    rcx, rcx
0x180004759  jz      short loc_18000476B
0x18000475b  mov     rax, [rcx]
0x18000475e  mov     edx, 1
0x180004763  mov     rax, [rax]
0x180004766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476b  mov     qword ptr [rbx+18h], 0
0x180004773  mov     rbx, [rsp+28h+arg_0]
0x180004778  add     rsp, 20h
0x18000477c  pop     rdi
0x18000477d  retn
```
