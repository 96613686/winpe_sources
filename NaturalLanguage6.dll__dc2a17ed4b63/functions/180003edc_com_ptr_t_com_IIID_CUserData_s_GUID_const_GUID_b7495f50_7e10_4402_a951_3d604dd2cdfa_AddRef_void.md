# _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)

- ea: `0x180003edc`
- end: `0x180003f03`
- name: `?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004220`
- `0x180005380`
- `0x180005b50`
- `0x180010b80`
- `0x180011624`
- `0x180011d10`
- `0x180014488`
- `0x180015e58`
- `0x18002cb78`
- `0x18002d7e8`
- `0x18002d83c`
- `0x1800367c0`
- `0x180036940`
- `0x18003b8d0`
- `0x18003d1f4`
- `0x18004d624`
- `0x18004d6d0`
- `0x18004d77c`
- `0x18004d874`
- `0x18004d8e0`
- `0x18004d94c`
- `0x18004d9b8`
- `0x18004da24`
- `0x18004df04`
- `0x18004e2d0`
- `0x18004e320`
- `0x18004e450`
- `0x18004ea14`
- `0x180051df4`
- `0x180051f1c`
- `0x180052218`
- `0x1800522d0`
- `0x180054674`
- `0x180054f40`
- `0x1800568d8`
- `0x180057ec0`
- `0x1800589f0`
- `0x180059860`
- `0x180059e00`
- `0x18005c480`
- `0x18005d41c`
- `0x18006b1d4`
- `0x18006b38c`
- `0x18006b554`
- `0x18006bbe0`
- `0x18006eec0`

## callees

- `0x180003edc`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180003edc  sub     rsp, 38h
0x180003ee0  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180003ee9  mov     rcx, [rcx]
0x180003eec  test    rcx, rcx
0x180003eef  jz      short loc_180003EFE
0x180003ef1  mov     rax, [rcx]
0x180003ef4  mov     rax, [rax+8]
0x180003ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003efd  nop
0x180003efe  add     rsp, 38h
0x180003f02  retn
```
