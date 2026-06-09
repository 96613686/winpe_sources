# std::unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______::_unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______

- ea: `0x1800057d4`
- end: `0x1800057ef`
- name: `std::unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______::_unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004c30`
- `0x180007534`
- `0x180011091`

## callees

- `0x180002f84`
- `0x1800057d4`

## pseudocode

```c
void __fastcall std::unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______::_unique_ptr_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d____std::default_delete_std::tuple__lambda_b5dea6a8ef435d535c6f4b6b71f3f11d_______(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800057d4  sub     rsp, 28h
0x1800057d8  mov     rcx, [rcx]; Block
0x1800057db  test    rcx, rcx
0x1800057de  jz      short loc_1800057EA
0x1800057e0  mov     edx, 10h
0x1800057e5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800057ea  add     rsp, 28h
0x1800057ee  retn
```
