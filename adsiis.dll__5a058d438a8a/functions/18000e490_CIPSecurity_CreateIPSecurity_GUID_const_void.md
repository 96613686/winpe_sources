# CIPSecurity::CreateIPSecurity(_GUID const &,void * *)

- ea: `0x18000e490`
- end: `0x18000e500`
- name: `?CreateIPSecurity@CIPSecurity@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e0e0`
- `0x180018518`

## callees

- `0x18000e1d0`
- `0x18000e2e0`
- `0x18000e490`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CIPSecurity::CreateIPSecurity(const struct _GUID *a1, void **a2)
{
  int v4; // eax
  unsigned int v5; // edx
  CIPSecurity *v6; // rbx
  int v7; // edi
  CIPSecurity *v9; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  v4 = CIPSecurity::AllocateIPSecurityObject(&v9);
  v6 = v9;
  v7 = v4;
  if ( v4 < 0
    || (v7 = (**(__int64 (__fastcall ***)(CIPSecurity *, const struct _GUID *, void **))v9)(v9, a1, a2), v7 < 0) )
  {
    if ( v6 )
      CIPSecurity::`scalar deleting destructor'(v6, v5);
  }
  else
  {
    (*(void (__fastcall **)(CIPSecurity *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e490  push    rbx
0x18000e492  push    rbp
0x18000e493  push    rsi
0x18000e494  push    rdi
0x18000e495  sub     rsp, 28h
0x18000e499  mov     rbp, rcx
0x18000e49c  mov     [rsp+48h+arg_10], 0
0x18000e4a5  lea     rcx, [rsp+48h+arg_10]; struct CIPSecurity **
0x18000e4aa  mov     rsi, rdx
0x18000e4ad  call    ?AllocateIPSecurityObject@CIPSecurity@@SAJPEAPEAV1@@Z; CIPSecurity::AllocateIPSecurityObject(CIPSecurity * *)
0x18000e4b2  mov     rbx, [rsp+48h+arg_10]
0x18000e4b7  mov     edi, eax
0x18000e4b9  test    eax, eax
0x18000e4bb  js      short loc_18000E4E8
0x18000e4bd  mov     rax, [rbx]
0x18000e4c0  mov     r8, rsi
0x18000e4c3  mov     rdx, rbp
0x18000e4c6  mov     rcx, rbx
0x18000e4c9  mov     rax, [rax]
0x18000e4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d1  mov     edi, eax
0x18000e4d3  test    eax, eax
0x18000e4d5  js      short loc_18000E4E8
0x18000e4d7  mov     rax, [rbx]
0x18000e4da  mov     rcx, rbx
0x18000e4dd  mov     rax, [rax+10h]
0x18000e4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e6  jmp     short loc_18000E4F5
0x18000e4e8  test    rbx, rbx
0x18000e4eb  jz      short loc_18000E4F5
0x18000e4ed  mov     rcx, rbx; this
0x18000e4f0  call    ??_GCIPSecurity@@QEAAPEAXI@Z; CIPSecurity::`scalar deleting destructor'(uint)
0x18000e4f5  mov     eax, edi
0x18000e4f7  add     rsp, 28h
0x18000e4fb  pop     rdi
0x18000e4fc  pop     rsi
0x18000e4fd  pop     rbp
0x18000e4fe  pop     rbx
0x18000e4ff  retn
```
