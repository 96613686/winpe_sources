# _CRawImageReader::GetExifMetadata_::_1_::catch$5

- ea: `0x1800b31c3`
- end: `0x1800b31f9`
- name: `_CRawImageReader::GetExifMetadata_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800a98c0`

## string_xrefs

- `0x1800b31d7`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::GetExifMetadata_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 264),
                           (void *)0x319,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           a4);
  return &loc_1800AA7B5;
}

```

## disassembly

```asm
0x1800b31c3  mov     [rsp+arg_8], rdx
0x1800b31c8  push    rbp
0x1800b31c9  sub     rsp, 40h
0x1800b31cd  mov     rbp, rdx
0x1800b31d0  mov     rcx, [rbp+108h]; this
0x1800b31d7  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b31de  mov     edx, 319h; void *
0x1800b31e3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b31e8  mov     [rbp+48h], eax
0x1800b31eb  lea     rax, loc_1800AA7B5
0x1800b31f2  add     rsp, 40h
0x1800b31f6  pop     rbp
0x1800b31f7  retn
```
