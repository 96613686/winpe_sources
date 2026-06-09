# FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EnqueueEvent(FingerprintCollectorStateMachine<FingerprintCollectorTimer>::Event)

- ea: `0x18001ef50`
- end: `0x18001f013`
- name: `?EnqueueEvent@?$FingerprintCollectorStateMachine@VFingerprintCollectorTimer@@@@QEAAXW4Event@1@@Z`
- size: `195`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e8d0`
- `0x18001ee78`
- `0x18001fd40`

## callees

- `0x18001ef50`
- `0x1800312dc`
- `0x180032048`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f00b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f00b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001efce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001efce`

## pseudocode

```c
void __fastcall FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EnqueueEvent(
        _QWORD *a1,
        unsigned __int16 a2)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rbp
  int v5; // eax
  bool v6; // si
  void (__fastcall *v7)(_QWORD, __int64); // rax
  __int64 v8; // rdx

  v2 = *a1;
  v3 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)(*a1 + 976LL);
  EnterCriticalSection(v4);
  v5 = *(_DWORD *)(v2 + 972);
  if ( v5 == 5 )
  {
    if ( (_WORD)v3 == *(_WORD *)(v2 + 880) )
    {
      v7 = *(void (__fastcall **)(_QWORD, __int64))(v2 + 912);
      if ( v7 )
      {
        if ( (_WORD)v3 )
          v8 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v2 + 888) + 16LL) + 4 * v3);
        else
          v8 = 0;
        v7(*(_QWORD *)(v2 + 896), v8);
      }
      *(_WORD *)(v2 + 880) = 0;
LABEL_10:
      *(_WORD *)(v2 + 966) = 0;
      *(_DWORD *)(v2 + 968) = GetCurrentThreadId();
      SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue((SmFx::StateMachineEngine::StateMachineEngineImpl *)v2);
      return;
    }
    v6 = 0;
  }
  else
  {
    v6 = v5 == 1;
  }
  if ( SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEventWithDisposition(
         (SmFx::StateMachineEngine::StateMachineEngineImpl *)v2,
         v3) )
  {
    if ( !v6 )
    {
      LeaveCriticalSection(v4);
      return;
    }
    goto LABEL_10;
  }
}

```

## disassembly

```asm
0x18001ef50  push    rbx
0x18001ef52  push    rbp
0x18001ef53  push    rsi
0x18001ef54  push    rdi
0x18001ef55  push    r14
0x18001ef57  sub     rsp, 20h
0x18001ef5b  mov     rbx, [rcx]
0x18001ef5e  movzx   edi, dx
0x18001ef61  lea     rbp, [rbx+3D0h]
0x18001ef68  mov     rcx, rbp; lpCriticalSection
0x18001ef6b  call    cs:__imp_EnterCriticalSection
0x18001ef71  mov     eax, [rbx+3CCh]
0x18001ef77  xor     r14d, r14d
0x18001ef7a  cmp     eax, 5
0x18001ef7d  jnz     short loc_18001EFED
0x18001ef7f  cmp     di, [rbx+370h]
0x18001ef86  jz      short loc_18001EF8D
0x18001ef88  mov     sil, r14b
0x18001ef8b  jmp     short loc_18001EFF4
0x18001ef8d  mov     rax, [rbx+390h]
0x18001ef94  test    rax, rax
0x18001ef97  jz      short loc_18001EFBE
0x18001ef99  test    di, di
0x18001ef9c  jnz     short loc_18001EFA3
0x18001ef9e  mov     edx, r14d
0x18001efa1  jmp     short loc_18001EFB2
0x18001efa3  mov     rcx, [rbx+378h]
0x18001efaa  mov     rcx, [rcx+10h]
0x18001efae  movzx   edx, word ptr [rcx+rdi*4]
0x18001efb2  mov     rcx, [rbx+380h]
0x18001efb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efbe  mov     [rbx+370h], r14w
0x18001efc6  mov     [rbx+3C6h], r14w
0x18001efce  call    cs:__imp_GetCurrentThreadId
0x18001efd4  mov     rcx, rbx; this
0x18001efd7  mov     [rbx+3C8h], eax
0x18001efdd  call    ?ProcessEventQueue@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAXXZ; SmFx::StateMachineEngine::StateMachineEngineImpl::ProcessEventQueue(void)
0x18001efe2  add     rsp, 20h
0x18001efe6  pop     r14
0x18001efe8  pop     rdi
0x18001efe9  pop     rsi
0x18001efea  pop     rbp
0x18001efeb  pop     rbx
0x18001efec  retn
0x18001efed  cmp     eax, 1
0x18001eff0  setz    sil
0x18001eff4  movzx   edx, di; unsigned __int16
0x18001eff7  mov     rcx, rbx; this
0x18001effa  call    ?EnqueueEventWithDisposition@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAA_NG@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::EnqueueEventWithDisposition(ushort)
0x18001efff  test    al, al
0x18001f001  jz      short loc_18001EFE2
0x18001f003  test    sil, sil
0x18001f006  jnz     short loc_18001EFC6
0x18001f008  mov     rcx, rbp; lpCriticalSection
0x18001f00b  call    cs:__imp_LeaveCriticalSection
0x18001f011  jmp     short loc_18001EFE2
```
