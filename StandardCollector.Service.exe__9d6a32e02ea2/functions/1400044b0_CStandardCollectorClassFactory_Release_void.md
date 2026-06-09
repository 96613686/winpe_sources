# CStandardCollectorClassFactory::Release(void)

- ea: `0x1400044b0`
- end: `0x14000450b`
- name: `?Release@CStandardCollectorClassFactory@@UEAAKXZ`
- size: `91`
- prototype: `__int64 __fastcall(CStandardCollectorClassFactory *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1400044b0`
- `0x14001382c`
- `0x140014c70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400044d3`
- `KERNEL32!DeleteCriticalSection` at `0x1400044d3`

## pseudocode

```c
__int64 __fastcall CStandardCollectorClassFactory::Release(CStandardCollectorClassFactory *this)
{
  unsigned __int32 v2; // edi
  __int64 v3; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    v3 = *((_QWORD *)this + 3);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1400044b0  mov     [rsp+arg_0], rbx
0x1400044b5  push    rdi
0x1400044b6  sub     rsp, 20h
0x1400044ba  mov     rbx, rcx
0x1400044bd  or      edi, 0FFFFFFFFh
0x1400044c0  lock xadd [rcx+8], edi
0x1400044c5  sub     edi, 1
0x1400044c8  jnz     short loc_1400044FE
0x1400044ca  test    rcx, rcx
0x1400044cd  jz      short loc_1400044FE
0x1400044cf  add     rcx, 20h ; ' '; lpCriticalSection
0x1400044d3  call    cs:__imp_DeleteCriticalSection
0x1400044d9  nop
0x1400044da  mov     rcx, [rbx+18h]
0x1400044de  test    rcx, rcx
0x1400044e1  jz      short loc_1400044F1
0x1400044e3  mov     rdx, [rcx]
0x1400044e6  mov     rax, [rdx+10h]
0x1400044ea  call    cs:__guard_dispatch_icall_fptr
0x1400044f0  nop
0x1400044f1  mov     edx, 48h ; 'H'
0x1400044f6  mov     rcx, rbx; Block
0x1400044f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400044fe  mov     eax, edi
0x140004500  mov     rbx, [rsp+28h+arg_0]
0x140004505  add     rsp, 20h
0x140004509  pop     rdi
0x14000450a  retn
```
