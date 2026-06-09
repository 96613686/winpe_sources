# _CRawImageReader::InitializeRawProcessorForDecodeImage_::_1_::catch$3

- ea: `0x1800b3391`
- end: `0x1800b33c7`
- name: `_CRawImageReader::InitializeRawProcessorForDecodeImage_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800abf54`

## string_xrefs

- `0x1800b33a5`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::InitializeRawProcessorForDecodeImage_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 52) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x680,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           a4);
  return &loc_1800AC531;
}

```

## disassembly

```asm
0x1800b3391  mov     [rsp+arg_8], rdx
0x1800b3396  push    rbp
0x1800b3397  sub     rsp, 30h
0x1800b339b  mov     rbp, rdx
0x1800b339e  mov     rcx, [rbp+0F8h]; this
0x1800b33a5  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b33ac  mov     edx, 680h; void *
0x1800b33b1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b33b6  mov     [rbp+34h], eax
0x1800b33b9  lea     rax, loc_1800AC531
0x1800b33c0  add     rsp, 30h
0x1800b33c4  pop     rbp
0x1800b33c5  retn
```
