# ATL::CRegObject::ClearReplacements(void)

- ea: `0x1400050f0`
- end: `0x14000512b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a44`

## callees

- `0x140005074`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140005118`
- `KERNEL32!LeaveCriticalSection` at `0x140005118`
- `KERNEL32!EnterCriticalSection` at `0x140005104`
- `KERNEL32!EnterCriticalSection` at `0x140005104`

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
0x1400050f0  mov     [rsp+arg_0], rbx
0x1400050f5  push    rdi
0x1400050f6  sub     rsp, 20h
0x1400050fa  lea     rdi, [rcx+20h]
0x1400050fe  mov     rbx, rcx
0x140005101  mov     rcx, rdi; lpCriticalSection
0x140005104  call    cs:__imp_EnterCriticalSection
0x14000510a  lea     rcx, [rbx+8]; this
0x14000510e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140005113  mov     rcx, rdi; lpCriticalSection
0x140005116  mov     ebx, eax
0x140005118  call    cs:__imp_LeaveCriticalSection
0x14000511e  mov     eax, ebx
0x140005120  mov     rbx, [rsp+28h+arg_0]
0x140005125  add     rsp, 20h
0x140005129  pop     rdi
0x14000512a  retn
```
