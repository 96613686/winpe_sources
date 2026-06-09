# Trigger::`scalar deleting destructor'(uint)

- ea: `0x18001b8f0`
- end: `0x18001b92f`
- name: `??_GTrigger@@UEAAPEAXI@Z`
- size: `63`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18001b8f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b91b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b91b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b90d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b90d`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall Trigger::`scalar deleting destructor'(
        struct _RTL_CRITICAL_SECTION *this,
        char a2)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&Trigger::`vftable';
  DeleteCriticalSection(this + 3);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001b8f0  mov     [rsp+arg_0], rbx
0x18001b8f5  push    rdi
0x18001b8f6  sub     rsp, 20h
0x18001b8fa  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x18001b901  mov     rdi, rcx
0x18001b904  mov     [rcx], rax
0x18001b907  mov     ebx, edx
0x18001b909  add     rcx, 78h ; 'x'; lpCriticalSection
0x18001b90d  call    cs:__imp_DeleteCriticalSection
0x18001b913  test    bl, 1
0x18001b916  jz      short loc_18001B921
0x18001b918  mov     rcx, rdi
0x18001b91b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b921  mov     rbx, [rsp+28h+arg_0]
0x18001b926  mov     rax, rdi
0x18001b929  add     rsp, 20h
0x18001b92d  pop     rdi
0x18001b92e  retn
```
