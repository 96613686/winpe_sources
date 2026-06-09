# std::unique_ptr<_SIPOLICY_FILE_ITEM [0],std::default_delete<_SIPOLICY_FILE_ITEM [0]>>::~unique_ptr<_SIPOLICY_FILE_ITEM [0],std::default_delete<_SIPOLICY_FILE_ITEM [0]>>(void)

- ea: `0x18000a308`
- end: `0x18000a31e`
- name: `??1?$unique_ptr@$$BY0A@U_SIPOLICY_FILE_ITEM@@U?$default_delete@$$BY0A@U_SIPOLICY_FILE_ITEM@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000ad4c`
- `0x18000dfe0`
- `0x18000e148`
- `0x180017ca8`
- `0x18002a310`
- `0x18002a4cd`
- `0x18002b23a`

## callees

- `0x180002ea4`
- `0x18000a308`

## pseudocode

```c
void __fastcall std::unique_ptr<_SIPOLICY_FILE_ITEM [0]>::~unique_ptr<_SIPOLICY_FILE_ITEM [0]>(
        void **a1,
        unsigned __int64 a2)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
    operator delete(v2, a2);
}

```

## disassembly

```asm
0x18000a308  sub     rsp, 28h
0x18000a30c  mov     rcx, [rcx]; void *
0x18000a30f  test    rcx, rcx
0x18000a312  jz      short loc_18000A319
0x18000a314  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a319  add     rsp, 28h
0x18000a31d  retn
```
