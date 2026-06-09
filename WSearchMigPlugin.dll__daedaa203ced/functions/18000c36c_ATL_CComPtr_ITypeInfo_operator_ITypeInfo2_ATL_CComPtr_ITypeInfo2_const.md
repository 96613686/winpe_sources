# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x18000c36c`
- end: `0x18000c487`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `283`
- prototype: `void (__fastcall ***__fastcall(_QWORD *, void (__fastcall ****)(_QWORD, GUID *, __int64)))(_QWORD, GUID *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fc68`

## callees

- `0x18000c36c`
- `0x180018010`

## pseudocode

```c
void (__fastcall ***__fastcall ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(
        _QWORD *a1,
        void (__fastcall ****a2)(_QWORD, GUID *, __int64)))(_QWORD, GUID *, __int64 *)
{
  void (__fastcall ***v4)(_QWORD, GUID *, __int64); // rdi
  void (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  bool v6; // di
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, GUID *, __int64); // rcx
  void (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  v4 = *a2;
  v5 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
  if ( !v5 )
  {
    if ( !v4 )
    {
      v6 = 1;
      goto LABEL_11;
    }
    goto LABEL_10;
  }
  if ( !v4 )
  {
LABEL_10:
    v6 = 0;
    goto LABEL_11;
  }
  v11 = 0;
  v12 = 0;
  (**v5)(v5, &GUID_00000000_0000_0000_c000_000000000046, &v11);
  (**v4)(v4, &GUID_00000000_0000_0000_c000_000000000046, (__int64)&v12);
  v7 = v11;
  v6 = v11 == v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v7 = v11;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_11:
  if ( !v6 )
  {
    v8 = *a2;
    v9 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
    *a1 = 0;
    if ( v8 )
      (**v8)(v8, &GUID_00020401_0000_0000_c000_000000000046, (__int64)a1);
    if ( v9 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v9)[2])(v9);
  }
  return (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1;
}

```

## disassembly

```asm
0x18000c36c  push    rdi
0x18000c36e  sub     rsp, 30h
0x18000c372  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000c37b  mov     [rsp+38h+arg_10], rbx
0x18000c380  mov     [rsp+38h+arg_18], rsi
0x18000c385  mov     rsi, rdx
0x18000c388  mov     rbx, rcx
0x18000c38b  mov     rdi, [rdx]
0x18000c38e  mov     rcx, [rcx]
0x18000c391  test    rcx, rcx
0x18000c394  jnz     short loc_18000C3A7
0x18000c396  test    rdi, rdi
0x18000c399  jnz     loc_18000C431
0x18000c39f  mov     dil, 1
0x18000c3a2  jmp     loc_18000C434
0x18000c3a7  test    rdi, rdi
0x18000c3aa  jz      loc_18000C431
0x18000c3b0  mov     [rsp+38h+arg_0], 0
0x18000c3b9  mov     [rsp+38h+arg_8], 0
0x18000c3c2  mov     rax, [rcx]
0x18000c3c5  lea     r8, [rsp+38h+arg_0]
0x18000c3ca  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c3d1  mov     rax, [rax]
0x18000c3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3d9  mov     rax, [rdi]
0x18000c3dc  lea     r8, [rsp+38h+arg_8]
0x18000c3e1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c3e8  mov     rcx, rdi
0x18000c3eb  mov     rax, [rax]
0x18000c3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f3  mov     rcx, [rsp+38h+arg_0]
0x18000c3f8  mov     rdx, [rsp+38h+arg_8]
0x18000c3fd  cmp     rcx, rdx
0x18000c400  setz    dil
0x18000c404  test    rdx, rdx
0x18000c407  jz      short loc_18000C41D
0x18000c409  mov     rax, [rdx]
0x18000c40c  mov     rcx, rdx
0x18000c40f  mov     rax, [rax+10h]
0x18000c413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c418  mov     rcx, [rsp+38h+arg_0]
0x18000c41d  test    rcx, rcx
0x18000c420  jz      short loc_18000C42F
0x18000c422  mov     rax, [rcx]
0x18000c425  mov     rax, [rax+10h]
0x18000c429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42e  nop
0x18000c42f  jmp     short loc_18000C434
0x18000c431  xor     dil, dil
0x18000c434  test    dil, dil
0x18000c437  jnz     short loc_18000C474
0x18000c439  mov     rcx, [rsi]
0x18000c43c  mov     rdi, [rbx]
0x18000c43f  mov     qword ptr [rbx], 0
0x18000c446  test    rcx, rcx
0x18000c449  jz      short loc_18000C460
0x18000c44b  mov     rax, [rcx]
0x18000c44e  mov     r8, rbx
0x18000c451  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x18000c458  mov     rax, [rax]
0x18000c45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c460  test    rdi, rdi
0x18000c463  jz      short loc_18000C474
0x18000c465  mov     rax, [rdi]
0x18000c468  mov     rcx, rdi
0x18000c46b  mov     rax, [rax+10h]
0x18000c46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c474  mov     rax, [rbx]
0x18000c477  mov     rbx, [rsp+38h+arg_10]
0x18000c47c  mov     rsi, [rsp+38h+arg_18]
0x18000c481  add     rsp, 30h
0x18000c485  pop     rdi
0x18000c486  retn
```
