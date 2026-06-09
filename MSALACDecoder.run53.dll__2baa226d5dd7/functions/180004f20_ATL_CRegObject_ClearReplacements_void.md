# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180004f20`
- end: `0x180004f5b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004e68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f34`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx
  unsigned int v3; // edx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8), v3);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004f20  mov     [rsp+arg_0], rbx
0x180004f25  push    rdi
0x180004f26  sub     rsp, 20h
0x180004f2a  lea     rdi, [rcx+20h]
0x180004f2e  mov     rbx, rcx
0x180004f31  mov     rcx, rdi; lpCriticalSection
0x180004f34  call    cs:__imp_EnterCriticalSection
0x180004f3a  lea     rcx, [rbx+8]; this
0x180004f3e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004f43  mov     rcx, rdi; lpCriticalSection
0x180004f46  mov     ebx, eax
0x180004f48  call    cs:__imp_LeaveCriticalSection
0x180004f4e  mov     eax, ebx
0x180004f50  mov     rbx, [rsp+28h+arg_0]
0x180004f55  add     rsp, 20h
0x180004f59  pop     rdi
0x180004f5a  retn
```
