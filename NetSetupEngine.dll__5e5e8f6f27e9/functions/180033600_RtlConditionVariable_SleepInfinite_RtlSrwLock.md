# RtlConditionVariable::SleepInfinite(RtlSrwLock &)

- ea: `0x180033600`
- end: `0x18003365c`
- name: `?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z`
- size: `92`
- prototype: `void __fastcall(PCONDITION_VARIABLE ConditionVariable, PSRWLOCK SRWLock)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c90`
- `0x1800096d0`
- `0x18000a460`
- `0x180013c20`
- `0x180033540`
- `0x1800377b8`
- `0x180037ba0`
- `0x180037c74`
- `0x180037d30`
- `0x1800391f4`
- `0x18004d764`
- `0x18004de5c`
- `0x18004f540`
- `0x1800530c8`
- `0x180053168`
- `0x1800587b4`
- `0x18005a654`
- `0x18005ca14`

## callees

- `0x180033600`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033643`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180033639`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180033639`

## pseudocode

```c
void __fastcall RtlConditionVariable::SleepInfinite(PCONDITION_VARIABLE ConditionVariable, PSRWLOCK SRWLock)
{
  ULONG v4; // edi

  if ( LODWORD(SRWLock[1].Ptr) == GetCurrentThreadId() )
  {
    v4 = 0;
    LODWORD(SRWLock[1].Ptr) = 0;
  }
  else
  {
    v4 = 1;
  }
  SleepConditionVariableSRW(ConditionVariable, SRWLock, 0xFFFFFFFF, v4);
  if ( !v4 )
    LODWORD(SRWLock[1].Ptr) = GetCurrentThreadId();
}

```

## disassembly

```asm
0x180033600  mov     [rsp+arg_0], rbx
0x180033605  mov     [rsp+arg_8], rsi
0x18003360a  push    rdi
0x18003360b  sub     rsp, 20h
0x18003360f  mov     rbx, rdx
0x180033612  mov     rsi, rcx
0x180033615  call    cs:__imp_GetCurrentThreadId
0x18003361b  cmp     [rbx+8], eax
0x18003361e  jnz     short loc_180033627
0x180033620  xor     edi, edi
0x180033622  mov     [rbx+8], edi
0x180033625  jmp     short loc_18003362C
0x180033627  mov     edi, 1
0x18003362c  mov     r9d, edi; Flags
0x18003362f  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180033633  mov     rdx, rbx; SRWLock
0x180033636  mov     rcx, rsi; ConditionVariable
0x180033639  call    cs:__imp_SleepConditionVariableSRW
0x18003363f  test    edi, edi
0x180033641  jnz     short loc_18003364C
0x180033643  call    cs:__imp_GetCurrentThreadId
0x180033649  mov     [rbx+8], eax
0x18003364c  mov     rbx, [rsp+28h+arg_0]
0x180033651  mov     rsi, [rsp+28h+arg_8]
0x180033656  add     rsp, 20h
0x18003365a  pop     rdi
0x18003365b  retn
```
