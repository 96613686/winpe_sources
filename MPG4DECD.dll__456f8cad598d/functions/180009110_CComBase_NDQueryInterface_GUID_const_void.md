# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x180009110`
- end: `0x18000915d`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c00`

## callees

- `0x180009110`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CComBase::NDQueryInterface(CComBase *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CComBase *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180009110  sub     rsp, 28h
0x180009114  test    r8, r8
0x180009117  jnz     short loc_180009120
0x180009119  mov     eax, 80004003h
0x18000911e  jmp     short loc_180009158
0x180009120  mov     rax, [rdx]
0x180009123  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000912a  jnz     short loc_18000914C
0x18000912c  mov     rax, [rdx+8]
0x180009130  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180009137  jnz     short loc_18000914C
0x180009139  mov     [r8], rcx
0x18000913c  mov     rax, [rcx]
0x18000913f  mov     rax, [rax+8]
0x180009143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009148  xor     eax, eax
0x18000914a  jmp     short loc_180009158
0x18000914c  mov     qword ptr [r8], 0
0x180009153  mov     eax, 80004002h
0x180009158  add     rsp, 28h
0x18000915c  retn
```
