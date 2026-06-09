# _CRawImageReader::GetPreview_::_1_::catch$5

- ea: `0x1800b3295`
- end: `0x1800b32cb`
- name: `_CRawImageReader::GetPreview_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800aafe0`

## string_xrefs

- `0x1800b32a9`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::GetPreview_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 216),
                            (void *)0x200,
                            (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                            a4);
  return &loc_1800AB429;
}

```

## disassembly

```asm
0x1800b3295  mov     [rsp+arg_8], rdx
0x1800b329a  push    rbp
0x1800b329b  sub     rsp, 40h
0x1800b329f  mov     rbp, rdx
0x1800b32a2  mov     rcx, [rbp+0D8h]; this
0x1800b32a9  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b32b0  mov     edx, 200h; void *
0x1800b32b5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b32ba  mov     [rbp+78h], eax
0x1800b32bd  lea     rax, loc_1800AB429
0x1800b32c4  add     rsp, 40h
0x1800b32c8  pop     rbp
0x1800b32c9  retn
```
