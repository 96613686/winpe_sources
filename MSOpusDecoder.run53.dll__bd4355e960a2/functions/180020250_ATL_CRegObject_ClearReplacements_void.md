# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180020250`
- end: `0x18002028b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800201a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020264`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020278`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020278`

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
0x180020250  mov     [rsp+arg_0], rbx
0x180020255  push    rdi
0x180020256  sub     rsp, 20h
0x18002025a  lea     rdi, [rcx+20h]
0x18002025e  mov     rbx, rcx
0x180020261  mov     rcx, rdi; lpCriticalSection
0x180020264  call    cs:__imp_EnterCriticalSection
0x18002026a  lea     rcx, [rbx+8]; this
0x18002026e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180020273  mov     rcx, rdi; lpCriticalSection
0x180020276  mov     ebx, eax
0x180020278  call    cs:__imp_LeaveCriticalSection
0x18002027e  mov     eax, ebx
0x180020280  mov     rbx, [rsp+28h+arg_0]
0x180020285  add     rsp, 20h
0x180020289  pop     rdi
0x18002028a  retn
```
