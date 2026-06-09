# _com_error::`scalar deleting destructor'(uint)

- ea: `0x180036240`
- end: `0x1800362a0`
- name: `??_G_com_error@@UEAAPEAXI@Z`
- size: `96`
- prototype: `_com_error *__fastcall(_com_error *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18003509c`
- `0x180036240`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180036278`
- `KERNEL32!LocalFree` at `0x180036278`

## pseudocode

```c
_com_error *__fastcall _com_error::`scalar deleting destructor'(_com_error *this, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &_com_error::`vftable';
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (void *)*((_QWORD *)this + 3);
  if ( v5 )
    LocalFree(v5);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180036240  mov     [rsp+arg_0], rbx
0x180036245  push    rdi
0x180036246  sub     rsp, 20h
0x18003624a  mov     edi, edx
0x18003624c  mov     rbx, rcx
0x18003624f  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180036256  mov     [rcx], rax
0x180036259  mov     rcx, [rcx+10h]
0x18003625d  test    rcx, rcx
0x180036260  jz      short loc_18003626F
0x180036262  mov     rax, [rcx]
0x180036265  mov     rax, [rax+10h]
0x180036269  call    cs:__guard_dispatch_icall_fptr
0x18003626f  mov     rcx, [rbx+18h]; hMem
0x180036273  test    rcx, rcx
0x180036276  jz      short loc_18003627F
0x180036278  call    cs:__imp_LocalFree
0x18003627e  nop
0x18003627f  test    dil, 1
0x180036283  jz      short loc_180036292
0x180036285  mov     edx, 20h ; ' '; unsigned __int64
0x18003628a  mov     rcx, rbx; void *
0x18003628d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180036292  mov     rax, rbx
0x180036295  mov     rbx, [rsp+28h+arg_0]
0x18003629a  add     rsp, 20h
0x18003629e  pop     rdi
0x18003629f  retn
```
