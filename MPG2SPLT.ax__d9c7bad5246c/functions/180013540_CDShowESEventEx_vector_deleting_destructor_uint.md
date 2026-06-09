# CDShowESEventEx::`vector deleting destructor'(uint)

- ea: `0x180013540`
- end: `0x1800135c5`
- name: `??_ECDShowESEventEx@@UEAAPEAXI@Z`
- size: `133`
- prototype: `void *__fastcall(CDShowESEventEx *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180013540`
- `0x180017a28`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180013599`
- `KERNEL32!DeleteCriticalSection` at `0x180013599`
- `KERNEL32!LeaveCriticalSection` at `0x180013590`
- `KERNEL32!LeaveCriticalSection` at `0x180013590`
- `KERNEL32!EnterCriticalSection` at `0x18001356a`
- `KERNEL32!EnterCriticalSection` at `0x18001356a`

## pseudocode

```c
CDShowESEventEx *__fastcall CDShowESEventEx::`vector deleting destructor'(CDShowESEventEx *this, char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)this = &CDShowESEventEx::`vftable';
  CDShowESEventEx::UnRegisterForESEvents(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v4 = *((_QWORD *)this + 6);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 6) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x40u);
  return this;
}

```

## disassembly

```asm
0x180013540  mov     [rsp+arg_0], rbx
0x180013545  mov     [rsp+arg_8], rsi
0x18001354a  push    rdi
0x18001354b  sub     rsp, 20h
0x18001354f  lea     rax, ??_7CDShowESEventEx@@6B@; const CDShowESEventEx::`vftable'
0x180013556  mov     esi, edx
0x180013558  mov     [rcx], rax
0x18001355b  mov     rbx, rcx
0x18001355e  call    ?UnRegisterForESEvents@CDShowESEventEx@@QEAAJXZ; CDShowESEventEx::UnRegisterForESEvents(void)
0x180013563  lea     rdi, [rbx+8]
0x180013567  mov     rcx, rdi; lpCriticalSection
0x18001356a  call    cs:__imp_EnterCriticalSection
0x180013570  mov     rcx, [rdi+28h]
0x180013574  test    rcx, rcx
0x180013577  jz      short loc_18001358D
0x180013579  mov     rax, [rcx]
0x18001357c  mov     rax, [rax+10h]
0x180013580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013585  mov     qword ptr [rdi+28h], 0
0x18001358d  mov     rcx, rdi; lpCriticalSection
0x180013590  call    cs:__imp_LeaveCriticalSection
0x180013596  mov     rcx, rdi; lpCriticalSection
0x180013599  call    cs:__imp_DeleteCriticalSection
0x18001359f  test    sil, 1
0x1800135a3  jz      short loc_1800135B2
0x1800135a5  mov     edx, 40h ; '@'; unsigned __int64
0x1800135aa  mov     rcx, rbx; void *
0x1800135ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800135b2  mov     rsi, [rsp+28h+arg_8]
0x1800135b7  mov     rax, rbx
0x1800135ba  mov     rbx, [rsp+28h+arg_0]
0x1800135bf  add     rsp, 20h
0x1800135c3  pop     rdi
0x1800135c4  retn
```
