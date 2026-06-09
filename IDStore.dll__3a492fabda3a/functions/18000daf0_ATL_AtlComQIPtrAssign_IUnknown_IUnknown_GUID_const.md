# ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)

- ea: `0x18000daf0`
- end: `0x18000db58`
- name: `?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z`
- size: `104`
- prototype: `struct IUnknown *__fastcall(struct IUnknown **, struct IUnknown *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012b10`
- `0x180014140`

## callees

- `0x18000daf0`
- `0x18001b010`

## pseudocode

```c
struct IUnknown *__fastcall ATL::AtlComQIPtrAssign(struct IUnknown **a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IUnknown *v3; // r9
  __int64 v5; // rdi

  v3 = a2;
  if ( !a1 )
    return 0;
  v5 = (__int64)*a1;
  *a1 = 0;
  if ( a2 )
    ((void (__fastcall *)(struct IUnknown *, const struct _GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
      a2,
      a3,
      a1);
  if ( v5 )
    (*(void (__fastcall **)(__int64, struct IUnknown *, const struct _GUID *, struct IUnknown *))(*(_QWORD *)v5 + 16LL))(
      v5,
      a2,
      a3,
      v3);
  return *a1;
}

```

## disassembly

```asm
0x18000daf0  push    rbx
0x18000daf2  sub     rsp, 20h
0x18000daf6  mov     r10, r8
0x18000daf9  mov     r9, rdx
0x18000dafc  mov     rbx, rcx
0x18000daff  test    rcx, rcx
0x18000db02  jz      short loc_18000DB3F
0x18000db04  mov     [rsp+28h+arg_0], rdi
0x18000db09  mov     rdi, [rcx]
0x18000db0c  mov     qword ptr [rcx], 0
0x18000db13  test    rdx, rdx
0x18000db16  jz      short loc_18000DB2C
0x18000db18  mov     rax, [rdx]
0x18000db1b  mov     r8, rcx
0x18000db1e  mov     rdx, r10
0x18000db21  mov     rcx, r9
0x18000db24  mov     rax, [rax]
0x18000db27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db2c  test    rdi, rdi
0x18000db2f  jnz     short loc_18000DB47
0x18000db31  mov     rax, [rbx]
0x18000db34  mov     rdi, [rsp+28h+arg_0]
0x18000db39  add     rsp, 20h
0x18000db3d  pop     rbx
0x18000db3e  retn
0x18000db3f  xor     eax, eax
0x18000db41  add     rsp, 20h
0x18000db45  pop     rbx
0x18000db46  retn
0x18000db47  mov     rax, [rdi]
0x18000db4a  mov     rcx, rdi
0x18000db4d  mov     rax, [rax+10h]
0x18000db51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db56  jmp     short loc_18000DB31
```
