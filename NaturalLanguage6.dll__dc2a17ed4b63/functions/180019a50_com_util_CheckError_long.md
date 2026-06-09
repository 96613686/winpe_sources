# _com_util::CheckError(long)

- ea: `0x180019a50`
- end: `0x180019a65`
- name: `?CheckError@_com_util@@YAXJ@Z`
- size: `21`
- prototype: `void __fastcall(int)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800036c4`
- `0x180005380`
- `0x180016bf4`
- `0x180017aa4`
- `0x180018860`
- `0x180019b10`
- `0x18001a260`
- `0x180023ad0`
- `0x1800241a0`
- `0x180031d50`
- `0x180031ff0`
- `0x180032118`
- `0x180041d90`
- `0x18004cc90`

## callees

- `0x180019a50`
- `0x180036b9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _com_util::CheckError(int a1)
{
  if ( a1 < 0 )
    _com_raise_error(a1, 0);
}

```

## disassembly

```asm
0x180019a50  sub     rsp, 28h
0x180019a54  test    ecx, ecx
0x180019a56  js      short loc_180019A5D
0x180019a58  add     rsp, 28h
0x180019a5c  retn
0x180019a5d  xor     edx, edx; struct IErrorInfo *
0x180019a5f  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
