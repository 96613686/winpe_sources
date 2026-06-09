# MP_CComObjectRootEx::`scalar deleting destructor'(uint)

- ea: `0x180002f40`
- end: `0x180002f8a`
- name: `??_GMP_CComObjectRootEx@@UEAAPEAXI@Z`
- size: `74`
- prototype: `void *__fastcall(MP_CComObjectRootEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002f40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002f76`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002f76`
- `KERNEL32!DeleteCriticalSection` at `0x180002f67`
- `KERNEL32!DeleteCriticalSection` at `0x180002f67`

## pseudocode

```c
MP_CComObjectRootEx *__fastcall MP_CComObjectRootEx::`scalar deleting destructor'(MP_CComObjectRootEx *this, char a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  *(_QWORD *)this = &MP_CComObjectRootEx::`vftable';
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
0x180002f40  mov     [rsp+arg_0], rbx
0x180002f45  push    rdi
0x180002f46  sub     rsp, 20h
0x180002f4a  lea     rax, ??_7MP_CComObjectRootEx@@6B@; const MP_CComObjectRootEx::`vftable'
0x180002f51  mov     rbx, rcx
0x180002f54  mov     [rcx], rax
0x180002f57  mov     edi, edx
0x180002f59  add     rcx, 10h; lpCriticalSection
0x180002f5d  cmp     byte ptr [rcx+28h], 0
0x180002f61  jz      short loc_180002F6D
0x180002f63  mov     byte ptr [rcx+28h], 0
0x180002f67  call    cs:__imp_DeleteCriticalSection
0x180002f6d  test    dil, 1
0x180002f71  jz      short loc_180002F7C
0x180002f73  mov     rcx, rbx
0x180002f76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002f7c  mov     rax, rbx
0x180002f7f  mov     rbx, [rsp+28h+arg_0]
0x180002f84  add     rsp, 20h
0x180002f88  pop     rdi
0x180002f89  retn
```
