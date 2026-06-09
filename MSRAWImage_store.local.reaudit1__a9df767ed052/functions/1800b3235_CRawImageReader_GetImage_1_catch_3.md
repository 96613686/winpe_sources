# _CRawImageReader::GetImage_::_1_::catch$3

- ea: `0x1800b3235`
- end: `0x1800b326b`
- name: `_CRawImageReader::GetImage_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800aa7f0`

## string_xrefs

- `0x1800b3249`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::GetImage_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x23F,
                           (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                           a4);
  return &loc_1800AAC58;
}

```

## disassembly

```asm
0x1800b3235  mov     [rsp+arg_8], rdx
0x1800b323a  push    rbp
0x1800b323b  sub     rsp, 40h
0x1800b323f  mov     rbp, rdx
0x1800b3242  mov     rcx, [rbp+0C8h]; this
0x1800b3249  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b3250  mov     edx, 23Fh; void *
0x1800b3255  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b325a  mov     [rbp+48h], eax
0x1800b325d  lea     rax, loc_1800AAC58
0x1800b3264  add     rsp, 40h
0x1800b3268  pop     rbp
0x1800b3269  retn
```
