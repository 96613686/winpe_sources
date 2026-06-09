# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x1800021e0`
- end: `0x1800022f1`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003f7c`

## callees

- `0x1800021e0`
- `0x18000d010`

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
0x1800021e0  mov     [rsp+arg_10], rbx
0x1800021e5  mov     [rsp+arg_18], rsi
0x1800021ea  push    rdi
0x1800021eb  sub     rsp, 20h
0x1800021ef  mov     rsi, rdx
0x1800021f2  mov     rbx, rcx
0x1800021f5  mov     rdi, [rdx]
0x1800021f8  mov     rcx, [rcx]
0x1800021fb  test    rcx, rcx
0x1800021fe  jnz     short loc_180002211
0x180002200  test    rdi, rdi
0x180002203  jnz     loc_18000229B
0x180002209  mov     dil, 1
0x18000220c  jmp     loc_18000229E
0x180002211  test    rdi, rdi
0x180002214  jz      loc_18000229B
0x18000221a  mov     [rsp+28h+arg_0], 0
0x180002223  mov     [rsp+28h+arg_8], 0
0x18000222c  mov     rax, [rcx]
0x18000222f  lea     r8, [rsp+28h+arg_0]
0x180002234  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000223b  mov     rax, [rax]
0x18000223e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002243  mov     rax, [rdi]
0x180002246  lea     r8, [rsp+28h+arg_8]
0x18000224b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002252  mov     rcx, rdi
0x180002255  mov     rax, [rax]
0x180002258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225d  mov     rcx, [rsp+28h+arg_0]
0x180002262  mov     rdx, [rsp+28h+arg_8]
0x180002267  cmp     rcx, rdx
0x18000226a  setz    dil
0x18000226e  test    rdx, rdx
0x180002271  jz      short loc_180002287
0x180002273  mov     rax, [rdx]
0x180002276  mov     rcx, rdx
0x180002279  mov     rax, [rax+10h]
0x18000227d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002282  mov     rcx, [rsp+28h+arg_0]
0x180002287  test    rcx, rcx
0x18000228a  jz      short loc_180002299
0x18000228c  mov     rax, [rcx]
0x18000228f  mov     rax, [rax+10h]
0x180002293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002298  nop
0x180002299  jmp     short loc_18000229E
0x18000229b  xor     dil, dil
0x18000229e  test    dil, dil
0x1800022a1  jnz     short loc_1800022DE
0x1800022a3  mov     rcx, [rsi]
0x1800022a6  mov     rdi, [rbx]
0x1800022a9  mov     qword ptr [rbx], 0
0x1800022b0  test    rcx, rcx
0x1800022b3  jz      short loc_1800022CA
0x1800022b5  mov     rax, [rcx]
0x1800022b8  mov     r8, rbx
0x1800022bb  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x1800022c2  mov     rax, [rax]
0x1800022c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ca  test    rdi, rdi
0x1800022cd  jz      short loc_1800022DE
0x1800022cf  mov     rax, [rdi]
0x1800022d2  mov     rcx, rdi
0x1800022d5  mov     rax, [rax+10h]
0x1800022d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022de  mov     rax, [rbx]
0x1800022e1  mov     rbx, [rsp+28h+arg_10]
0x1800022e6  mov     rsi, [rsp+28h+arg_18]
0x1800022eb  add     rsp, 20h
0x1800022ef  pop     rdi
0x1800022f0  retn
```
