# ATL::CComClassFactory::`vector deleting destructor'(uint)

- ea: `0x1800035c0`
- end: `0x18000360e`
- name: `??_ECComClassFactory@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `ATL::CComClassFactory *__fastcall(ATL::CComClassFactory *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180007a90`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800035e7`
- `KERNEL32!DeleteCriticalSection` at `0x1800035e7`

## pseudocode

```c
ATL::CComClassFactory *__fastcall ATL::CComClassFactory::`vector deleting destructor'(
        ATL::CComClassFactory *this,
        char a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  *(_QWORD *)this = &ATL::CComClassFactory::`vftable';
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  if ( LOBYTE(v4[1].DebugInfo) )
  {
    LOBYTE(v4[1].DebugInfo) = 0;
    DeleteCriticalSection(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800035c0  mov     [rsp+arg_0], rbx
0x1800035c5  push    rdi
0x1800035c6  sub     rsp, 20h
0x1800035ca  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800035d1  mov     rbx, rcx
0x1800035d4  mov     [rcx], rax
0x1800035d7  mov     edi, edx
0x1800035d9  add     rcx, 10h; lpCriticalSection
0x1800035dd  cmp     byte ptr [rcx+28h], 0
0x1800035e1  jz      short loc_1800035ED
0x1800035e3  mov     byte ptr [rcx+28h], 0
0x1800035e7  call    cs:__imp_DeleteCriticalSection
0x1800035ed  test    dil, 1
0x1800035f1  jz      short loc_180003600
0x1800035f3  mov     edx, 48h ; 'H'
0x1800035f8  mov     rcx, rbx; Block
0x1800035fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003600  mov     rax, rbx
0x180003603  mov     rbx, [rsp+28h+arg_0]
0x180003608  add     rsp, 20h
0x18000360c  pop     rdi
0x18000360d  retn
```
