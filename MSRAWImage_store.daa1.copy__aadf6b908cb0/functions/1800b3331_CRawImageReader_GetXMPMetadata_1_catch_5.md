# _CRawImageReader::GetXMPMetadata_::_1_::catch$5

- ea: `0x1800b3331`
- end: `0x1800b3367`
- name: `_CRawImageReader::GetXMPMetadata_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800aba40`

## string_xrefs

- `0x1800b3345`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::GetXMPMetadata_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 216),
                            (void *)0x335,
                            (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                            a4);
  return &loc_1800ABF19;
}

```

## disassembly

```asm
0x1800b3331  mov     [rsp+arg_8], rdx
0x1800b3336  push    rbp
0x1800b3337  sub     rsp, 40h
0x1800b333b  mov     rbp, rdx
0x1800b333e  mov     rcx, [rbp+0D8h]; this
0x1800b3345  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b334c  mov     edx, 335h; void *
0x1800b3351  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b3356  mov     [rbp+70h], eax
0x1800b3359  lea     rax, loc_1800ABF19
0x1800b3360  add     rsp, 40h
0x1800b3364  pop     rbp
0x1800b3365  retn
```
