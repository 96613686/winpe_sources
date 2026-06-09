# ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)

- ea: `0x180009d60`
- end: `0x180009e71`
- name: `??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z`
- size: `273`
- prototype: `void (__fastcall ***__fastcall(_QWORD *, void (__fastcall ****)(_QWORD, GUID *, __int64)))(_QWORD, GUID *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a584`

## callees

- `0x180009d60`
- `0x18000f010`

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
0x180009d60  mov     [rsp+arg_10], rbx
0x180009d65  mov     [rsp+arg_18], rsi
0x180009d6a  push    rdi
0x180009d6b  sub     rsp, 20h
0x180009d6f  mov     rsi, rdx
0x180009d72  mov     rbx, rcx
0x180009d75  mov     rdi, [rdx]
0x180009d78  mov     rcx, [rcx]
0x180009d7b  test    rcx, rcx
0x180009d7e  jnz     short loc_180009D91
0x180009d80  test    rdi, rdi
0x180009d83  jnz     loc_180009E1B
0x180009d89  mov     dil, 1
0x180009d8c  jmp     loc_180009E1E
0x180009d91  test    rdi, rdi
0x180009d94  jz      loc_180009E1B
0x180009d9a  mov     [rsp+28h+arg_0], 0
0x180009da3  mov     [rsp+28h+arg_8], 0
0x180009dac  mov     rax, [rcx]
0x180009daf  lea     r8, [rsp+28h+arg_0]
0x180009db4  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009dbb  mov     rax, [rax]
0x180009dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc3  mov     rax, [rdi]
0x180009dc6  lea     r8, [rsp+28h+arg_8]
0x180009dcb  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180009dd2  mov     rcx, rdi
0x180009dd5  mov     rax, [rax]
0x180009dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ddd  mov     rcx, [rsp+28h+arg_0]
0x180009de2  mov     rdx, [rsp+28h+arg_8]
0x180009de7  cmp     rcx, rdx
0x180009dea  setz    dil
0x180009dee  test    rdx, rdx
0x180009df1  jz      short loc_180009E07
0x180009df3  mov     rax, [rdx]
0x180009df6  mov     rcx, rdx
0x180009df9  mov     rax, [rax+10h]
0x180009dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e02  mov     rcx, [rsp+28h+arg_0]
0x180009e07  test    rcx, rcx
0x180009e0a  jz      short loc_180009E19
0x180009e0c  mov     rax, [rcx]
0x180009e0f  mov     rax, [rax+10h]
0x180009e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e18  nop
0x180009e19  jmp     short loc_180009E1E
0x180009e1b  xor     dil, dil
0x180009e1e  test    dil, dil
0x180009e21  jnz     short loc_180009E5E
0x180009e23  mov     rcx, [rsi]
0x180009e26  mov     rdi, [rbx]
0x180009e29  mov     qword ptr [rbx], 0
0x180009e30  test    rcx, rcx
0x180009e33  jz      short loc_180009E4A
0x180009e35  mov     rax, [rcx]
0x180009e38  mov     r8, rbx
0x180009e3b  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180009e42  mov     rax, [rax]
0x180009e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e4a  test    rdi, rdi
0x180009e4d  jz      short loc_180009E5E
0x180009e4f  mov     rax, [rdi]
0x180009e52  mov     rcx, rdi
0x180009e55  mov     rax, [rax+10h]
0x180009e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e5e  mov     rax, [rbx]
0x180009e61  mov     rbx, [rsp+28h+arg_10]
0x180009e66  mov     rsi, [rsp+28h+arg_18]
0x180009e6b  add     rsp, 20h
0x180009e6f  pop     rdi
0x180009e70  retn
```
