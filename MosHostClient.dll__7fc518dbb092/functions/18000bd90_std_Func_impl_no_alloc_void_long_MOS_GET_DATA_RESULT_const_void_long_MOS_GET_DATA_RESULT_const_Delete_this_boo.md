# std::_Func_impl_no_alloc<void (*)(long,MOS_GET_DATA_RESULT const &),void,long,MOS_GET_DATA_RESULT const &>::_Delete_this(bool)

- ea: `0x18000bd90`
- end: `0x18000bda7`
- name: `?_Delete_this@?$_Func_impl_no_alloc@P6AXJAEBUMOS_GET_DATA_RESULT@@@ZXJAEBU1@@std@@EEAAX_N@Z`
- size: `23`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800029b4`
- `0x18000bd90`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc<void (*)(long,MOS_GET_DATA_RESULT const &),void,long,MOS_GET_DATA_RESULT const &>::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x18000bd90  sub     rsp, 28h
0x18000bd94  test    dl, dl
0x18000bd96  jz      short loc_18000BDA2
0x18000bd98  mov     edx, 10h
0x18000bd9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bda2  add     rsp, 28h
0x18000bda6  retn
```
