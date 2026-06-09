# std::unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____::_unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____

- ea: `0x180012198`
- end: `0x1800121ae`
- name: `std::unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____::_unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____`
- size: `22`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011390`
- `0x180011420`
- `0x180011480`
- `0x180011510`
- `0x180011580`
- `0x1800115e0`
- `0x18001ab98`
- `0x18001cc50`
- `0x180023a9f`

## callees

- `0x1800033f4`
- `0x180012198`

## pseudocode

```c
void __fastcall std::unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____::_unique_ptr__lambda_e0151e82603ed25fc2b10ac46ee2682c__std::default_delete__lambda_e0151e82603ed25fc2b10ac46ee2682c_____(
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
0x180012198  sub     rsp, 28h
0x18001219c  mov     rcx, [rcx]; Block
0x18001219f  test    rcx, rcx
0x1800121a2  jz      short loc_1800121A9
0x1800121a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800121a9  add     rsp, 28h
0x1800121ad  retn
```
