# WfpUserModeTimerInternalCallback

- ea: `0x18008aa90`
- end: `0x18008ab02`
- name: `WfpUserModeTimerInternalCallback`
- size: `114`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18008aa90`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008aada`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008aada`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008aaa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008aaa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aac6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008aac6`

## pseudocode

```c
void __fastcall WfpUserModeTimerInternalCallback(
        PTP_CALLBACK_INSTANCE Instance,
        LPCRITICAL_SECTION *Context,
        PTP_TIMER Timer)
{
  char v4; // di

  EnterCriticalSection(Context[4]);
  if ( *((_DWORD *)Context + 6) == 2 )
  {
    v4 = 0;
  }
  else
  {
    v4 = 1;
    *((_DWORD *)Context + 6) = 3;
  }
  LeaveCriticalSection(Context[4]);
  if ( v4 )
  {
    CloseThreadpoolTimer((PTP_TIMER)*Context);
    ((void (__fastcall *)(LPCRITICAL_SECTION *, LPCRITICAL_SECTION))Context[1])(Context, Context[2]);
  }
}

```

## disassembly

```asm
0x18008aa90  mov     [rsp+arg_0], rbx
0x18008aa95  push    rdi
0x18008aa96  sub     rsp, 20h
0x18008aa9a  mov     rcx, [rdx+20h]; lpCriticalSection
0x18008aa9e  mov     rbx, rdx
0x18008aaa1  call    cs:__imp_EnterCriticalSection
0x18008aaa8  nop     dword ptr [rax+rax+00h]
0x18008aaad  cmp     dword ptr [rbx+18h], 2
0x18008aab1  jnz     short loc_18008AAB8
0x18008aab3  xor     dil, dil
0x18008aab6  jmp     short loc_18008AAC2
0x18008aab8  mov     dil, 1
0x18008aabb  mov     dword ptr [rbx+18h], 3
0x18008aac2  mov     rcx, [rbx+20h]; lpCriticalSection
0x18008aac6  call    cs:__imp_LeaveCriticalSection
0x18008aacd  nop     dword ptr [rax+rax+00h]
0x18008aad2  test    dil, dil
0x18008aad5  jz      short loc_18008AAF6
0x18008aad7  mov     rcx, [rbx]; pti
0x18008aada  call    cs:__imp_CloseThreadpoolTimer
0x18008aae1  nop     dword ptr [rax+rax+00h]
0x18008aae6  mov     rdx, [rbx+10h]
0x18008aaea  mov     rcx, rbx
0x18008aaed  mov     rax, [rbx+8]
0x18008aaf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aaf6  mov     rbx, [rsp+28h+arg_0]
0x18008aafb  add     rsp, 20h
0x18008aaff  pop     rdi
0x18008ab00  retn
```
