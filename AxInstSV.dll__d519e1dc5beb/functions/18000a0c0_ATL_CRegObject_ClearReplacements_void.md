# ATL::CRegObject::ClearReplacements(void)

- ea: `0x18000a0c0`
- end: `0x18000a0fb`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800088f8`

## callees

- `0x18000a03c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0d4`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8));
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000a0c0  mov     [rsp+arg_0], rbx
0x18000a0c5  push    rdi
0x18000a0c6  sub     rsp, 20h
0x18000a0ca  lea     rdi, [rcx+20h]
0x18000a0ce  mov     rbx, rcx
0x18000a0d1  mov     rcx, rdi; lpCriticalSection
0x18000a0d4  call    cs:__imp_EnterCriticalSection
0x18000a0da  lea     rcx, [rbx+8]; this
0x18000a0de  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x18000a0e3  mov     rcx, rdi; lpCriticalSection
0x18000a0e6  mov     ebx, eax
0x18000a0e8  call    cs:__imp_LeaveCriticalSection
0x18000a0ee  mov     eax, ebx
0x18000a0f0  mov     rbx, [rsp+28h+arg_0]
0x18000a0f5  add     rsp, 20h
0x18000a0f9  pop     rdi
0x18000a0fa  retn
```
