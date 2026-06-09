# _dynamic_atexit_destructor_for__s_disabledContext__

- ea: `0x1800595f0`
- end: `0x1800596e8`
- name: `_dynamic_atexit_destructor_for__s_disabledContext__`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009c50`
- `0x18004f088`
- `0x18004f338`
- `0x1800595f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800596bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800596ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800596bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800596ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800596e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005964d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005964d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005960f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005960f`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_disabledContext__()
{
  __int64 v0; // rdx
  unsigned int v1; // edx
  __int64 v2; // rbx
  int *v3; // rdi
  CallStackContextNode *v4; // rcx
  CallStackContextNode *v5; // rbx

  qword_180069A90 = (__int64)&CallStackTracing::`vftable';
  EnterCriticalSection(&stru_180069AC8);
  while ( (_QWORD)xmmword_180069B40 )
  {
    v0 = xmmword_180069B40;
    *(_QWORD *)&xmmword_180069B40 = *(_QWORD *)(xmmword_180069B40 + 2032);
    CFreeList<CallStackContextNode,16>::Free(&qword_180069AF8, v0);
  }
  LODWORD(qword_180069B50) = 0;
  LeaveCriticalSection(&stru_180069AC8);
  v2 = 124;
  v3 = &dword_18006A320;
  do
  {
    v3 -= 4;
    --v2;
  }
  while ( v2 );
  v4 = qword_180069B30;
  qword_180069AF8 = (__int64)&CFreeList<CallStackContextNode,16>::`vftable';
  if ( qword_180069B30 )
  {
    do
    {
      v5 = (CallStackContextNode *)*((_QWORD *)v4 + 254);
      --HIDWORD(qword_180069B38);
      CallStackContextNode::`scalar deleting destructor'(v4, v1);
      qword_180069B30 = v5;
      v4 = v5;
    }
    while ( v5 );
  }
  LODWORD(qword_180069B38) = 0;
  DeleteCriticalSection(&stru_180069B08);
  DeleteCriticalSection(&stru_180069AC8);
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x1800595f0  mov     [rsp+arg_0], rbx
0x1800595f5  push    rdi
0x1800595f6  sub     rsp, 20h
0x1800595fa  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x180059601  lea     rcx, stru_180069AC8; lpCriticalSection
0x180059608  mov     cs:qword_180069A90, rax
0x18005960f  call    cs:__imp_EnterCriticalSection
0x180059615  jmp     short loc_180059634
0x180059617  mov     rax, [rcx+7F0h]
0x18005961e  mov     rdx, rcx
0x180059621  lea     rcx, qword_180069AF8
0x180059628  mov     qword ptr cs:xmmword_180069B40, rax
0x18005962f  call    ?Free@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAXPEAVCallStackContextNode@@@Z; CFreeList<CallStackContextNode,16>::Free(CallStackContextNode *)
0x180059634  mov     rcx, qword ptr cs:xmmword_180069B40
0x18005963b  test    rcx, rcx
0x18005963e  jnz     short loc_180059617
0x180059640  mov     dword ptr cs:qword_180069B50, ecx
0x180059646  lea     rcx, stru_180069AC8; lpCriticalSection
0x18005964d  call    cs:__imp_LeaveCriticalSection
0x180059653  mov     ebx, 7Ch ; '|'
0x180059658  lea     rdi, dword_18006A320
0x18005965f  sub     rdi, 10h
0x180059663  mov     rcx, rdi
0x180059666  call    _guard_check_icall_nop
0x18005966b  sub     rbx, 1
0x18005966f  jnz     short loc_18005965F
0x180059671  mov     rcx, cs:qword_180069B30; this
0x180059678  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x18005967f  mov     cs:qword_180069AF8, rax
0x180059686  test    rcx, rcx
0x180059689  jz      short loc_1800596AC
0x18005968b  mov     rbx, [rcx+7F0h]
0x180059692  dec     dword ptr cs:qword_180069B38+4
0x180059698  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x18005969d  mov     cs:qword_180069B30, rbx
0x1800596a4  mov     rcx, rbx
0x1800596a7  test    rbx, rbx
0x1800596aa  jnz     short loc_18005968B
0x1800596ac  lea     rcx, stru_180069B08; lpCriticalSection
0x1800596b3  mov     dword ptr cs:qword_180069B38, 0
0x1800596bd  call    cs:__imp_DeleteCriticalSection
0x1800596c3  lea     rcx, stru_180069AC8; lpCriticalSection
0x1800596ca  call    cs:__imp_DeleteCriticalSection
0x1800596d0  lea     rcx, CriticalSection
0x1800596d7  mov     rbx, [rsp+28h+arg_0]
0x1800596dc  add     rsp, 20h
0x1800596e0  pop     rdi
0x1800596e1  jmp     cs:__imp_DeleteCriticalSection
```
