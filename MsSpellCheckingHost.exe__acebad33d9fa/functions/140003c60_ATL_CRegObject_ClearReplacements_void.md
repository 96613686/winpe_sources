# ATL::CRegObject::ClearReplacements(void)

- ea: `0x140003c60`
- end: `0x140003c9b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003bb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003c88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003c88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003c74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003c74`

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
0x140003c60  mov     [rsp+arg_0], rbx
0x140003c65  push    rdi
0x140003c66  sub     rsp, 20h
0x140003c6a  lea     rdi, [rcx+20h]
0x140003c6e  mov     rbx, rcx
0x140003c71  mov     rcx, rdi; lpCriticalSection
0x140003c74  call    cs:__imp_EnterCriticalSection
0x140003c7a  lea     rcx, [rbx+8]; this
0x140003c7e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x140003c83  mov     rcx, rdi; lpCriticalSection
0x140003c86  mov     ebx, eax
0x140003c88  call    cs:__imp_LeaveCriticalSection
0x140003c8e  mov     eax, ebx
0x140003c90  mov     rbx, [rsp+28h+arg_0]
0x140003c95  add     rsp, 20h
0x140003c99  pop     rdi
0x140003c9a  retn
```
