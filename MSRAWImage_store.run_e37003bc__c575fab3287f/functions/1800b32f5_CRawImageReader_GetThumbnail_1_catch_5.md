# _CRawImageReader::GetThumbnail_::_1_::catch$5

- ea: `0x1800b32f5`
- end: `0x1800b332b`
- name: `_CRawImageReader::GetThumbnail_::_1_::catch$5`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18009d350`
- `0x1800ab5b0`

## string_xrefs

- `0x1800b3309`: `avcore\mf\rawimage\rawimagereader\rawimagereader.cpp`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CRawImageReader::GetThumbnail_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 120) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 216),
                            (void *)0x1C2,
                            (unsigned int)"avcore\\mf\\rawimage\\rawimagereader\\rawimagereader.cpp",
                            a4);
  return &loc_1800ABA03;
}

```

## disassembly

```asm
0x1800b32f5  mov     [rsp+arg_8], rdx
0x1800b32fa  push    rbp
0x1800b32fb  sub     rsp, 40h
0x1800b32ff  mov     rbp, rdx
0x1800b3302  mov     rcx, [rbp+0D8h]; this
0x1800b3309  lea     r8, aAvcoreMfRawima_0; "avcore\\mf\\rawimage\\rawimagereader\\r"...
0x1800b3310  mov     edx, 1C2h; void *
0x1800b3315  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800b331a  mov     [rbp+78h], eax
0x1800b331d  lea     rax, loc_1800ABA03
0x1800b3324  add     rsp, 40h
0x1800b3328  pop     rbp
0x1800b3329  retn
```
