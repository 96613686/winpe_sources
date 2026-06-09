# PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::~TriggerCEAggregate(void)

- ea: `0x18001b79c`
- end: `0x18001b869`
- name: `??1TriggerCEAggregate@PRIVATE_NAMESPACE_Triggers_H@@UEAA@XZ`
- size: `205`
- prototype: `void __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b980`

## callees

- `0x18001b79c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b862`
- `EventAggregation!EADeleteAggregateEvent` at `0x18001b7bf`
- `EventAggregation!EADeleteAggregateEvent` at `0x18001b7bf`

## pseudocode

```c
void __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::~TriggerCEAggregate(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        __int64 a3)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  void (__fastcall ***LockSemaphore)(_QWORD, __int64); // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *p_Type; // rdx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::`vftable';
  DebugInfo = this[5].DebugInfo;
  if ( DebugInfo )
  {
    EADeleteAggregateEvent(DebugInfo, a2, a3);
    this[5].DebugInfo = 0;
  }
  LockSemaphore = (void (__fastcall ***)(_QWORD, __int64))this[5].LockSemaphore;
  if ( LockSemaphore )
  {
    (**LockSemaphore)(LockSemaphore, 1);
    this[5].LockSemaphore = 0;
  }
  v6 = this + 6;
  while ( 1 )
  {
    p_Type = &v6->DebugInfo->Type;
    if ( (struct _RTL_CRITICAL_SECTION *)v6->DebugInfo == v6 )
      break;
    v7 = *p_Type;
    v8 = (_QWORD *)p_Type[1];
    *v8 = *p_Type;
    *(_QWORD *)(v7 + 8) = v8;
    --LODWORD(this[5].SpinCount);
    if ( p_Type != (_QWORD *)8 )
      (*(void (__fastcall **)(_QWORD *, __int64))*(p_Type - 1))(p_Type - 1, 1);
  }
  *(_OWORD *)&this[5].LockCount = 0;
  this[4].OwningThread = 0;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Trigger::`vftable';
  DeleteCriticalSection(this + 3);
}

```

## disassembly

```asm
0x18001b79c  mov     [rsp+arg_0], rbx
0x18001b7a1  push    rdi
0x18001b7a2  sub     rsp, 20h
0x18001b7a6  lea     rax, ??_7TriggerCEAggregate@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::`vftable'
0x18001b7ad  mov     rbx, rcx
0x18001b7b0  mov     [rcx], rax
0x18001b7b3  mov     rcx, [rcx+0C8h]
0x18001b7ba  test    rcx, rcx
0x18001b7bd  jz      short loc_18001B7D0
0x18001b7bf  call    cs:__imp_EADeleteAggregateEvent
0x18001b7c5  mov     qword ptr [rbx+0C8h], 0
0x18001b7d0  mov     rcx, [rbx+0E0h]
0x18001b7d7  test    rcx, rcx
0x18001b7da  jz      short loc_18001B7F7
0x18001b7dc  mov     rax, [rcx]
0x18001b7df  mov     edx, 1
0x18001b7e4  mov     rax, [rax]
0x18001b7e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7ec  mov     qword ptr [rbx+0E0h], 0
0x18001b7f7  lea     rdi, [rbx+0F0h]
0x18001b7fe  jmp     short loc_18001B82D
0x18001b800  mov     rcx, [rdx]
0x18001b803  mov     rax, [rdx+8]
0x18001b807  mov     [rax], rcx
0x18001b80a  mov     [rcx+8], rax
0x18001b80e  lea     rcx, [rdx-8]
0x18001b812  dec     dword ptr [rbx+0E8h]
0x18001b818  test    rcx, rcx
0x18001b81b  jz      short loc_18001B82D
0x18001b81d  mov     rax, [rcx]
0x18001b820  mov     edx, 1
0x18001b825  mov     rax, [rax]
0x18001b828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b82d  mov     rdx, [rdi]
0x18001b830  cmp     rdx, rdi
0x18001b833  jnz     short loc_18001B800
0x18001b835  xorps   xmm0, xmm0
0x18001b838  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x18001b83f  movups  xmmword ptr [rbx+0D0h], xmm0
0x18001b846  lea     rcx, [rbx+78h]
0x18001b84a  mov     qword ptr [rbx+0B0h], 0
0x18001b855  mov     [rbx], rax
0x18001b858  mov     rbx, [rsp+28h+arg_0]
0x18001b85d  add     rsp, 20h
0x18001b861  pop     rdi
0x18001b862  jmp     cs:__imp_DeleteCriticalSection
```
