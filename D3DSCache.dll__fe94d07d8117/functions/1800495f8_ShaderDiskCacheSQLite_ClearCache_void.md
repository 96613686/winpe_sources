# ShaderDiskCacheSQLite::ClearCache(void)

- ea: `0x1800495f8`
- end: `0x180049629`
- name: `?ClearCache@ShaderDiskCacheSQLite@@QEAAJXZ`
- size: `49`
- prototype: `__int64 __fastcall(ShaderDiskCacheSQLite *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002a2d0`
- `0x180049838`

## callees

- `0x1800334f0`

## string_xrefs

- `0x180049600`: `PRAGMA foreign_keys=OFF;DELETE FROM vals;DELETE FROM keys;PRAGMA foreign_keys=ON;`

## pseudocode

```c
__int64 __fastcall ShaderDiskCacheSQLite::ClearCache(ShaderDiskCacheSQLite *this)
{
  return (unsigned int)sqlite3_exec(
                         *((_QWORD *)this + 1),
                         (unsigned int)"PRAGMA foreign_keys=OFF;DELETE FROM vals;DELETE FROM keys;PRAGMA foreign_keys=ON;",
                         0,
                         0,
                         0) != 0
       ? 0x80004005
       : 0;
}

```

## disassembly

```asm
0x1800495f8  sub     rsp, 38h
0x1800495fc  mov     rcx, [rcx+8]
0x180049600  lea     rdx, aPragmaForeignK; "PRAGMA foreign_keys=OFF;DELETE FROM val"...
0x180049607  xor     r9d, r9d
0x18004960a  mov     [rsp+38h+var_18], 0
0x180049613  xor     r8d, r8d
0x180049616  call    sqlite3_exec
0x18004961b  neg     eax
0x18004961d  sbb     eax, eax
0x18004961f  and     eax, 80004005h
0x180049624  add     rsp, 38h
0x180049628  retn
```
