# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003960`
- end: `0x18000399b`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003898`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003988`
- `KERNEL32!LeaveCriticalSection` at `0x180003988`
- `KERNEL32!EnterCriticalSection` at `0x180003974`
- `KERNEL32!EnterCriticalSection` at `0x180003974`

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
0x180003960  mov     [rsp+arg_0], rbx
0x180003965  push    rdi
0x180003966  sub     rsp, 20h
0x18000396a  lea     rdi, [rcx+20h]
0x18000396e  mov     rbx, rcx
0x180003971  mov     rcx, rdi; lpCriticalSection
0x180003974  call    cs:__imp_EnterCriticalSection
0x18000397a  lea     rcx, [rbx+8]; this
0x18000397e  call    ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
0x180003983  mov     rcx, rdi; lpCriticalSection
0x180003986  mov     ebx, eax
0x180003988  call    cs:__imp_LeaveCriticalSection
0x18000398e  mov     eax, ebx
0x180003990  mov     rbx, [rsp+28h+arg_0]
0x180003995  add     rsp, 20h
0x180003999  pop     rdi
0x18000399a  retn
```
