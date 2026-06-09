# RegisterForStoppedCallback(_REDIRECTION_CONTEXT *)

- ea: `0x180014970`
- end: `0x180014a27`
- name: `?RegisterForStoppedCallback@@YAHPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180017ac0`

## callees

- `0x180014970`
- `0x180014d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014991`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014991`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800149f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800149e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800149e7`
- `ntdll!RtlDllShutdownInProgress` at `0x1800149d0`
- `ntdll!RtlDllShutdownInProgress` at `0x1800149d0`

## pseudocode

```c
__int64 __fastcall RegisterForStoppedCallback(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE v2; // rsi
  unsigned int v3; // edi

  if ( !dword_180045A10 )
    return 0;
  EnterCriticalSection(&CriticalSection);
  if ( !h )
    h = CreateSCEvent(0x3Du);
  LeaveCriticalSection(&CriticalSection);
  v2 = h;
  if ( !h )
    return 0;
  EnterCriticalSection(lpCriticalSection);
  v3 = 0;
  if ( !LOBYTE(lpCriticalSection[1].DebugInfo) && !RtlDllShutdownInProgress() )
  {
    SetThreadpoolWait((PTP_WAIT)lpCriticalSection[3].SpinCount, v2, 0);
    v3 = 1;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180014970  mov     [rsp+arg_8], rbx
0x180014975  push    rsi
0x180014976  sub     rsp, 20h
0x18001497a  cmp     cs:dword_180045A10, 0
0x180014981  mov     rbx, rcx
0x180014984  jz      loc_180014A0D
0x18001498a  lea     rcx, CriticalSection; lpCriticalSection
0x180014991  call    cs:__imp_EnterCriticalSection
0x180014997  cmp     cs:h, 0
0x18001499f  jz      short loc_180014A11
0x1800149a1  lea     rcx, CriticalSection; lpCriticalSection
0x1800149a8  call    cs:__imp_LeaveCriticalSection
0x1800149ae  mov     rsi, cs:h
0x1800149b5  test    rsi, rsi
0x1800149b8  jz      short loc_180014A0D
0x1800149ba  mov     rcx, rbx; lpCriticalSection
0x1800149bd  mov     [rsp+28h+arg_0], rdi
0x1800149c2  call    cs:__imp_EnterCriticalSection
0x1800149c8  xor     edi, edi
0x1800149ca  cmp     [rbx+28h], dil
0x1800149ce  jnz     short loc_1800149F2
0x1800149d0  call    cs:__imp_RtlDllShutdownInProgress
0x1800149d6  test    al, al
0x1800149d8  jnz     short loc_1800149F2
0x1800149da  mov     rcx, [rbx+98h]; pwa
0x1800149e1  xor     r8d, r8d; pftTimeout
0x1800149e4  mov     rdx, rsi; h
0x1800149e7  call    cs:__imp_SetThreadpoolWait
0x1800149ed  mov     edi, 1
0x1800149f2  mov     rcx, rbx; lpCriticalSection
0x1800149f5  call    cs:__imp_LeaveCriticalSection
0x1800149fb  mov     eax, edi
0x1800149fd  mov     rdi, [rsp+28h+arg_0]
0x180014a02  mov     rbx, [rsp+28h+arg_8]
0x180014a07  add     rsp, 20h
0x180014a0b  pop     rsi
0x180014a0c  retn
0x180014a0d  xor     eax, eax
0x180014a0f  jmp     short loc_180014A02
0x180014a11  mov     ecx, 3Dh ; '='; unsigned int
0x180014a16  call    ?CreateSCEvent@@YAPEAXK@Z; CreateSCEvent(ulong)
0x180014a1b  mov     cs:h, rax
0x180014a22  jmp     loc_1800149A1
```
