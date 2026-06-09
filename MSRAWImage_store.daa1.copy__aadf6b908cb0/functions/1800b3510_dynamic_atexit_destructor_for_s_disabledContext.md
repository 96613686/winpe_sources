# _dynamic_atexit_destructor_for__s_disabledContext__

- ea: `0x1800b3510`
- end: `0x1800b3637`
- name: `_dynamic_atexit_destructor_for__s_disabledContext__`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180098740`
- `0x1800a3178`
- `0x1800a3468`
- `0x1800b3510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b3584`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b3584`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3534`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3534`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3609`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b35f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b3609`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b362b`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_disabledContext__()
{
  __int64 i; // rcx
  struct IMFTelemetryComponent *v1; // rdx
  CMFRawTelemetrySession *v2; // rbx
  __int64 v3; // rdi
  CallStackContextNode *v4; // rcx
  CallStackContextNode *v5; // rbx

  off_1800E5190 = &CallStackTracing::`vftable';
  EnterCriticalSection(&stru_1800E51C8);
  for ( i = xmmword_1800E5240; (_QWORD)xmmword_1800E5240; i = xmmword_1800E5240 )
  {
    *(_QWORD *)&xmmword_1800E5240 = *(_QWORD *)(i + 2032);
    CFreeList<CallStackContextNode,16>::Free(&qword_1800E51F8, i);
  }
  LODWORD(qword_1800E5250) = 0;
  LeaveCriticalSection(&stru_1800E51C8);
  v2 = (CMFRawTelemetrySession *)&dword_1800E5A20;
  v3 = 124;
  do
  {
    v2 = (CMFRawTelemetrySession *)((char *)v2 - 16);
    CMFRawTelemetrySession::RegisterCallback(v2, v1);
    --v3;
  }
  while ( v3 );
  v4 = qword_1800E5230;
  qword_1800E51F8 = (__int64)&CFreeList<CallStackContextNode,16>::`vftable';
  if ( qword_1800E5230 )
  {
    do
    {
      v5 = (CallStackContextNode *)*((_QWORD *)v4 + 254);
      --HIDWORD(qword_1800E5238);
      CallStackContextNode::`scalar deleting destructor'(v4, (unsigned int)v1);
      qword_1800E5230 = v5;
      v4 = v5;
    }
    while ( v5 );
  }
  LODWORD(qword_1800E5238) = 0;
  DeleteCriticalSection(&stru_1800E5208);
  DeleteCriticalSection(&stru_1800E51C8);
  DeleteCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x1800b3510  mov     [rsp+arg_0], rbx
0x1800b3515  mov     [rsp+arg_8], rsi
0x1800b351a  push    rdi
0x1800b351b  sub     rsp, 20h
0x1800b351f  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x1800b3526  lea     rcx, stru_1800E51C8; lpCriticalSection
0x1800b352d  mov     cs:off_1800E5190, rax
0x1800b3534  call    cs:__imp_EnterCriticalSection
0x1800b353b  nop     dword ptr [rax+rax+00h]
0x1800b3540  mov     rcx, qword ptr cs:xmmword_1800E5240
0x1800b3547  test    rcx, rcx
0x1800b354a  jz      short loc_1800B3575
0x1800b354c  mov     rax, [rcx+7F0h]
0x1800b3553  mov     rdx, rcx
0x1800b3556  lea     rcx, qword_1800E51F8
0x1800b355d  mov     qword ptr cs:xmmword_1800E5240, rax
0x1800b3564  call    ?Free@?$CFreeList@VCallStackContextNode@@$0BA@@@QEAAXPEAVCallStackContextNode@@@Z; CFreeList<CallStackContextNode,16>::Free(CallStackContextNode *)
0x1800b3569  mov     rcx, qword ptr cs:xmmword_1800E5240
0x1800b3570  test    rcx, rcx
0x1800b3573  jnz     short loc_1800B354C
0x1800b3575  xor     esi, esi
0x1800b3577  lea     rcx, stru_1800E51C8; lpCriticalSection
0x1800b357e  mov     dword ptr cs:qword_1800E5250, esi
0x1800b3584  call    cs:__imp_LeaveCriticalSection
0x1800b358b  nop     dword ptr [rax+rax+00h]
0x1800b3590  lea     rbx, dword_1800E5A20
0x1800b3597  mov     edi, 7Ch ; '|'
0x1800b359c  sub     rbx, 10h
0x1800b35a0  mov     rcx, rbx; this
0x1800b35a3  call    ?RegisterCallback@CMFRawTelemetrySession@@UEAAXPEAUIMFTelemetryComponent@@@Z; CMFRawTelemetrySession::RegisterCallback(IMFTelemetryComponent *)
0x1800b35a8  sub     rdi, 1
0x1800b35ac  jnz     short loc_1800B359C
0x1800b35ae  mov     rcx, cs:qword_1800E5230; this
0x1800b35b5  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x1800b35bc  mov     cs:qword_1800E51F8, rax
0x1800b35c3  test    rcx, rcx
0x1800b35c6  jz      short loc_1800B35E9
0x1800b35c8  mov     rbx, [rcx+7F0h]
0x1800b35cf  dec     dword ptr cs:qword_1800E5238+4
0x1800b35d5  call    ??_GCallStackContextNode@@QEAAPEAXI@Z; CallStackContextNode::`scalar deleting destructor'(uint)
0x1800b35da  mov     cs:qword_1800E5230, rbx
0x1800b35e1  mov     rcx, rbx
0x1800b35e4  test    rbx, rbx
0x1800b35e7  jnz     short loc_1800B35C8
0x1800b35e9  lea     rcx, stru_1800E5208; lpCriticalSection
0x1800b35f0  mov     dword ptr cs:qword_1800E5238, esi
0x1800b35f6  call    cs:__imp_DeleteCriticalSection
0x1800b35fd  nop     dword ptr [rax+rax+00h]
0x1800b3602  lea     rcx, stru_1800E51C8; lpCriticalSection
0x1800b3609  call    cs:__imp_DeleteCriticalSection
0x1800b3610  nop     dword ptr [rax+rax+00h]
0x1800b3615  lea     rcx, CriticalSection
0x1800b361c  mov     rbx, [rsp+28h+arg_0]
0x1800b3621  mov     rsi, [rsp+28h+arg_8]
0x1800b3626  add     rsp, 20h
0x1800b362a  pop     rdi
0x1800b362b  jmp     cs:__imp_DeleteCriticalSection
```
