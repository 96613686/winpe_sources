# PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::`scalar deleting destructor'(uint)

- ea: `0x18000d9c0`
- end: `0x18000da54`
- name: `??_GTriggerAggregate@PRIVATE_NAMESPACE_Triggers_H@@UEAAPEAXI@Z`
- size: `148`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000d9c0`
- `0x180022010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000da4c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000da4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000da2a`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rdi
  _QWORD *p_Type; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  v3 = this + 5;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::`vftable';
  p_Type = &this[5].DebugInfo->Type;
  if ( p_Type != (_QWORD *)&this[5] )
  {
    do
    {
      v6 = (_QWORD *)p_Type[1];
      v7 = *p_Type;
      *v6 = *p_Type;
      *(_QWORD *)(v7 + 8) = v6;
      if ( p_Type != (_QWORD *)8 )
        (*(void (__fastcall **)(_QWORD *, __int64))*(p_Type - 1))(p_Type - 1, 1);
      p_Type = &v3->DebugInfo->Type;
    }
    while ( (struct _RTL_CRITICAL_SECTION *)v3->DebugInfo != v3 );
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Trigger::`vftable';
  DeleteCriticalSection(this + 3);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d9c0  mov     [rsp+arg_0], rbx
0x18000d9c5  mov     [rsp+arg_8], rsi
0x18000d9ca  push    rdi
0x18000d9cb  sub     rsp, 20h
0x18000d9cf  lea     rax, ??_7TriggerAggregate@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::`vftable'
0x18000d9d6  mov     esi, edx
0x18000d9d8  lea     rdi, [rcx+0C8h]
0x18000d9df  mov     [rcx], rax
0x18000d9e2  mov     rax, [rdi]
0x18000d9e5  mov     rbx, rcx
0x18000d9e8  cmp     rax, rdi
0x18000d9eb  jz      short loc_18000DA1C
0x18000d9ed  mov     rcx, [rax+8]
0x18000d9f1  mov     rdx, [rax]
0x18000d9f4  mov     [rcx], rdx
0x18000d9f7  mov     [rdx+8], rcx
0x18000d9fb  lea     rcx, [rax-8]
0x18000d9ff  test    rcx, rcx
0x18000da02  jz      short loc_18000DA14
0x18000da04  mov     rax, [rcx]
0x18000da07  mov     edx, 1
0x18000da0c  mov     rax, [rax]
0x18000da0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da14  mov     rax, [rdi]
0x18000da17  cmp     rax, rdi
0x18000da1a  jnz     short loc_18000D9ED
0x18000da1c  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x18000da23  lea     rcx, [rbx+78h]; lpCriticalSection
0x18000da27  mov     [rbx], rax
0x18000da2a  call    cs:__imp_DeleteCriticalSection
0x18000da30  test    sil, 1
0x18000da34  jnz     short loc_18000DA49
0x18000da36  mov     rsi, [rsp+28h+arg_8]
0x18000da3b  mov     rax, rbx
0x18000da3e  mov     rbx, [rsp+28h+arg_0]
0x18000da43  add     rsp, 20h
0x18000da47  pop     rdi
0x18000da48  retn
0x18000da49  mov     rcx, rbx
0x18000da4c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000da52  jmp     short loc_18000DA36
```
