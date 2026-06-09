# _RfbDiskFolderWmiQuery::CreatePidl_::_1_::catch$21

- ea: `0x1800186db`
- end: `0x180018712`
- name: `_RfbDiskFolderWmiQuery::CreatePidl_::_1_::catch$21`
- size: `55`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014054`

## pseudocode

```c
__int64 __fastcall RfbDiskFolderWmiQuery::CreatePidl_::_1_::catch_21(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 296),
    (void *)0xE5,
    (unsigned int)"vm\\ux\\ui\\remotefilebrowse\\rfbdiskfolderwmiquery.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800186db  mov     [rsp+arg_8], rdx
0x1800186e0  push    rbp
0x1800186e1  sub     rsp, 30h
0x1800186e5  mov     rbp, rdx
0x1800186e8  mov     rcx, [rbp+128h]; this
0x1800186ef  lea     r8, aVmUxUiRemotefi_2; "vm\\ux\\ui\\remotefilebrowse\\rfbdiskfo"...
0x1800186f6  mov     edx, 0E5h; void *
0x1800186fb  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180018700  nop
0x180018701  mov     rax, 0
0x18001870b  add     rsp, 30h
0x18001870f  pop     rbp
0x180018710  retn
```
