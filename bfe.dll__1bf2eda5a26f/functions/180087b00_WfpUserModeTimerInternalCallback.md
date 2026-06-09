# WfpUserModeTimerInternalCallback

- ea: `0x180087b00`
- end: `0x180087b5f`
- name: `WfpUserModeTimerInternalCallback`
- size: `95`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180087b00`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180087b3e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180087b3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087b11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087b11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087b30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087b30`

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
0x180087b00  mov     [rsp+arg_0], rbx
0x180087b05  push    rdi
0x180087b06  sub     rsp, 20h
0x180087b0a  mov     rcx, [rdx+20h]; lpCriticalSection
0x180087b0e  mov     rbx, rdx
0x180087b11  call    cs:__imp_EnterCriticalSection
0x180087b17  cmp     dword ptr [rbx+18h], 2
0x180087b1b  jnz     short loc_180087B22
0x180087b1d  xor     dil, dil
0x180087b20  jmp     short loc_180087B2C
0x180087b22  mov     dil, 1
0x180087b25  mov     dword ptr [rbx+18h], 3
0x180087b2c  mov     rcx, [rbx+20h]; lpCriticalSection
0x180087b30  call    cs:__imp_LeaveCriticalSection
0x180087b36  test    dil, dil
0x180087b39  jz      short loc_180087B54
0x180087b3b  mov     rcx, [rbx]; pti
0x180087b3e  call    cs:__imp_CloseThreadpoolTimer
0x180087b44  mov     rdx, [rbx+10h]
0x180087b48  mov     rcx, rbx
0x180087b4b  mov     rax, [rbx+8]
0x180087b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b54  mov     rbx, [rsp+28h+arg_0]
0x180087b59  add     rsp, 20h
0x180087b5d  pop     rdi
0x180087b5e  retn
```
