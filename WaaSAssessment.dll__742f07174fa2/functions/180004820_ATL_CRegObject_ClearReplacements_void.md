# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180004820`
- end: `0x18000485b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004768`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004834`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004834`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ATL::CRegObject *v2; // rbx
  int v3; // edx
  unsigned int v4; // r8d

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v2 = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  LODWORD(v2) = ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)v2 + 8), v3, v4);
  LeaveCriticalSection(v1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004820  mov     [rsp+arg_0], rbx
0x180004825  push    rdi
0x180004826  sub     rsp, 20h
0x18000482a  lea     rdi, [rcx+20h]
0x18000482e  mov     rbx, rcx
0x180004831  mov     rcx, rdi; lpCriticalSection
0x180004834  call    cs:__imp_EnterCriticalSection
0x18000483a  lea     rcx, [rbx+8]; this
0x18000483e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180004843  mov     rcx, rdi; lpCriticalSection
0x180004846  mov     ebx, eax
0x180004848  call    cs:__imp_LeaveCriticalSection
0x18000484e  mov     eax, ebx
0x180004850  mov     rbx, [rsp+28h+arg_0]
0x180004855  add     rsp, 20h
0x180004859  pop     rdi
0x18000485a  retn
```
