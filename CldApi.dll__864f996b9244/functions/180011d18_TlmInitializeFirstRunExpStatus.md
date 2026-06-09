# TlmInitializeFirstRunExpStatus

- ea: `0x180011d18`
- end: `0x180011e12`
- name: `TlmInitializeFirstRunExpStatus`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006060`

## callees

- `0x180011d18`
- `0x180018ce0`
- `0x18001a3a0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011d69`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011d69`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e06`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e06`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011dd7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180011dd7`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180011da6`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180011da6`

## pseudocode

```c
void __fastcall TlmInitializeFirstRunExpStatus(__int64 a1, void *a2, void *a3)
{
  if ( byte_180028930 && !NtCurrentPeb()->Ldr->ShutdownInProgress && !byte_180028968 )
  {
    TlmiInitializeProviderGlobalData(a2, a3);
    RtlAcquireSRWLockExclusive(&qword_180028970);
    if ( !byte_180028968 )
    {
      qword_180028978 = a1;
      qword_180028988 = 0;
      qword_180028990 = a1;
      qword_180028998 = 0;
      hTimer = CreateWaitableTimerW(0, 1, 0);
      if ( hTimer )
      {
        qword_1800289A0 = CreateThread(0, 0, TlmiFirstRunExpWorker, 0, 0, 0);
        if ( qword_1800289A0 )
          byte_180028968 = 1;
      }
    }
    if ( !byte_180028968 )
      TlmiUninitializeFirstRunExpStatus();
    RtlReleaseSRWLockExclusive(&qword_180028970);
  }
}

```

## disassembly

```asm
0x180011d18  push    rbx
0x180011d1a  sub     rsp, 30h
0x180011d1e  cmp     cs:byte_180028930, 0
0x180011d25  mov     r10, rdx
0x180011d28  mov     rbx, rcx
0x180011d2b  jz      loc_180011E0C
0x180011d31  mov     rax, gs:60h
0x180011d3a  mov     r9, [rax+18h]
0x180011d3e  cmp     byte ptr [r9+48h], 0
0x180011d43  jnz     loc_180011E0C
0x180011d49  mov     al, cs:byte_180028968
0x180011d4f  test    al, al
0x180011d51  jnz     loc_180011E0C
0x180011d57  mov     rdx, r8; void *
0x180011d5a  mov     rcx, r10; Src
0x180011d5d  call    TlmiInitializeProviderGlobalData
0x180011d62  lea     rcx, qword_180028970
0x180011d69  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011d6f  mov     al, cs:byte_180028968
0x180011d75  test    al, al
0x180011d77  jnz     short loc_180011DF0
0x180011d79  xor     r8d, r8d; lpTimerName
0x180011d7c  mov     cs:qword_180028978, rbx
0x180011d83  xor     ecx, ecx; lpTimerAttributes
0x180011d85  mov     cs:qword_180028988, 0
0x180011d90  mov     cs:qword_180028990, rbx
0x180011d97  mov     cs:qword_180028998, 0
0x180011da2  lea     edx, [r8+1]; bManualReset
0x180011da6  call    cs:__imp_CreateWaitableTimerW
0x180011dac  mov     cs:hTimer, rax
0x180011db3  test    rax, rax
0x180011db6  jz      short loc_180011DF0
0x180011db8  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180011dc1  lea     r8, TlmiFirstRunExpWorker; lpStartAddress
0x180011dc8  xor     r9d, r9d; lpParameter
0x180011dcb  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180011dd3  xor     edx, edx; dwStackSize
0x180011dd5  xor     ecx, ecx; lpThreadAttributes
0x180011dd7  call    cs:__imp_CreateThread
0x180011ddd  mov     cs:qword_1800289A0, rax
0x180011de4  test    rax, rax
0x180011de7  jz      short loc_180011DF0
0x180011de9  mov     cs:byte_180028968, 1
0x180011df0  mov     al, cs:byte_180028968
0x180011df6  test    al, al
0x180011df8  jnz     short loc_180011DFF
0x180011dfa  call    TlmiUninitializeFirstRunExpStatus
0x180011dff  lea     rcx, qword_180028970
0x180011e06  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011e0c  add     rsp, 30h
0x180011e10  pop     rbx
0x180011e11  retn
```
