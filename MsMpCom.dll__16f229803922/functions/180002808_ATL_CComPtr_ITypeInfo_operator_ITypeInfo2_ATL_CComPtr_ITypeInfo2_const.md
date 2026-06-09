# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x180002808`
- end: `0x180002919`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e28`

## callees

- `0x180002808`
- `0x18000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

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
0x180002808  mov     [rsp+arg_10], rbx
0x18000280d  mov     [rsp+arg_18], rsi
0x180002812  push    rdi
0x180002813  sub     rsp, 20h
0x180002817  mov     rsi, rdx
0x18000281a  mov     rbx, rcx
0x18000281d  mov     rdi, [rdx]
0x180002820  mov     rcx, [rcx]
0x180002823  test    rcx, rcx
0x180002826  jnz     short loc_180002839
0x180002828  test    rdi, rdi
0x18000282b  jnz     loc_1800028C3
0x180002831  mov     dil, 1
0x180002834  jmp     loc_1800028C6
0x180002839  test    rdi, rdi
0x18000283c  jz      loc_1800028C3
0x180002842  mov     [rsp+28h+arg_0], 0
0x18000284b  mov     [rsp+28h+arg_8], 0
0x180002854  mov     rax, [rcx]
0x180002857  lea     r8, [rsp+28h+arg_0]
0x18000285c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002863  mov     rax, [rax]
0x180002866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000286b  mov     rax, [rdi]
0x18000286e  lea     r8, [rsp+28h+arg_8]
0x180002873  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000287a  mov     rcx, rdi
0x18000287d  mov     rax, [rax]
0x180002880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002885  mov     rcx, [rsp+28h+arg_0]
0x18000288a  mov     rdx, [rsp+28h+arg_8]
0x18000288f  cmp     rcx, rdx
0x180002892  setz    dil
0x180002896  test    rdx, rdx
0x180002899  jz      short loc_1800028AF
0x18000289b  mov     rax, [rdx]
0x18000289e  mov     rcx, rdx
0x1800028a1  mov     rax, [rax+10h]
0x1800028a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028aa  mov     rcx, [rsp+28h+arg_0]
0x1800028af  test    rcx, rcx
0x1800028b2  jz      short loc_1800028C1
0x1800028b4  mov     rax, [rcx]
0x1800028b7  mov     rax, [rax+10h]
0x1800028bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c0  nop
0x1800028c1  jmp     short loc_1800028C6
0x1800028c3  xor     dil, dil
0x1800028c6  test    dil, dil
0x1800028c9  jnz     short loc_180002906
0x1800028cb  mov     rcx, [rsi]
0x1800028ce  mov     rdi, [rbx]
0x1800028d1  mov     qword ptr [rbx], 0
0x1800028d8  test    rcx, rcx
0x1800028db  jz      short loc_1800028F2
0x1800028dd  mov     rax, [rcx]
0x1800028e0  mov     r8, rbx
0x1800028e3  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x1800028ea  mov     rax, [rax]
0x1800028ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f2  test    rdi, rdi
0x1800028f5  jz      short loc_180002906
0x1800028f7  mov     rax, [rdi]
0x1800028fa  mov     rcx, rdi
0x1800028fd  mov     rax, [rax+10h]
0x180002901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002906  mov     rax, [rbx]
0x180002909  mov     rbx, [rsp+28h+arg_10]
0x18000290e  mov     rsi, [rsp+28h+arg_18]
0x180002913  add     rsp, 20h
0x180002917  pop     rdi
0x180002918  retn
```
