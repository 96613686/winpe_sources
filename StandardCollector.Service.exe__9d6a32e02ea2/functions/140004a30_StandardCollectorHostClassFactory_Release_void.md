# StandardCollectorHostClassFactory::Release(void)

- ea: `0x140004a30`
- end: `0x140004a8b`
- name: `?Release@StandardCollectorHostClassFactory@@UEAAKXZ`
- size: `91`
- prototype: `__int64 __fastcall(StandardCollectorHostClassFactory *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x140004a30`
- `0x14001382c`
- `0x140014c70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004a53`
- `KERNEL32!DeleteCriticalSection` at `0x140004a53`

## pseudocode

```c
__int64 __fastcall StandardCollectorHostClassFactory::Release(StandardCollectorHostClassFactory *this)
{
  unsigned __int32 v2; // edi
  __int64 v3; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v3 = *((_QWORD *)this + 2);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x140004a30  mov     [rsp+arg_0], rbx
0x140004a35  push    rdi
0x140004a36  sub     rsp, 20h
0x140004a3a  mov     rbx, rcx
0x140004a3d  or      edi, 0FFFFFFFFh
0x140004a40  lock xadd [rcx+8], edi
0x140004a45  sub     edi, 1
0x140004a48  jnz     short loc_140004A7E
0x140004a4a  test    rcx, rcx
0x140004a4d  jz      short loc_140004A7E
0x140004a4f  add     rcx, 18h; lpCriticalSection
0x140004a53  call    cs:__imp_DeleteCriticalSection
0x140004a59  nop
0x140004a5a  mov     rcx, [rbx+10h]
0x140004a5e  test    rcx, rcx
0x140004a61  jz      short loc_140004A71
0x140004a63  mov     rdx, [rcx]
0x140004a66  mov     rax, [rdx+10h]
0x140004a6a  call    cs:__guard_dispatch_icall_fptr
0x140004a70  nop
0x140004a71  mov     edx, 40h ; '@'
0x140004a76  mov     rcx, rbx; Block
0x140004a79  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004a7e  mov     eax, edi
0x140004a80  mov     rbx, [rsp+28h+arg_0]
0x140004a85  add     rsp, 20h
0x140004a89  pop     rdi
0x140004a8a  retn
```
