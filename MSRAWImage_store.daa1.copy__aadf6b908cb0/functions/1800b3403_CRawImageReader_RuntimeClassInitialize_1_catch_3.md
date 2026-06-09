# _CRawImageReader::RuntimeClassInitialize_::_1_::catch$3

- ea: `0x1800b3403`
- end: `0x1800b3439`
- name: `_CRawImageReader::RuntimeClassInitialize_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800ad600`

## string_xrefs

- `0x1800b3417`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::RuntimeClassInitialize_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x16D,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           a4);
  return &loc_1800AD966;
}

```

## disassembly

```asm
0x1800b3403  mov     [rsp+arg_8], rdx
0x1800b3408  push    rbp
0x1800b3409  sub     rsp, 30h
0x1800b340d  mov     rbp, rdx
0x1800b3410  mov     rcx, [rbp+98h]; this
0x1800b3417  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b341e  mov     edx, 16Dh; void *
0x1800b3423  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b3428  mov     [rbp+38h], eax
0x1800b342b  lea     rax, loc_1800AD966
0x1800b3432  add     rsp, 30h
0x1800b3436  pop     rbp
0x1800b3437  retn
```
