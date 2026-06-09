# _CFileIoChannel::OnReadIrpAvailable_::_1_::catch$1

- ea: `0x18003dfcd`
- end: `0x18003e016`
- name: `_CFileIoChannel::OnReadIrpAvailable_::_1_::catch$1`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180017a8c`
- `0x180033288`

## string_xrefs

- `0x18003dfec`: `Failed to process Read Irp`

## pseudocode

```c
__int64 __fastcall CFileIoChannel::OnReadIrpAvailable_::_1_::catch_1(__int64 a1, __int64 a2)
{
  const char *v4; // [rsp+20h] [rbp-18h]

  CFileIoChannel::CancelAllPendingIo(*(_QWORD *)(a2 + 80), 1u);
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x408,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
    "Failed to process Read Irp",
    v4);
  return 0;
}

```

## disassembly

```asm
0x18003dfcd  mov     [rsp+arg_8], rdx
0x18003dfd2  push    rbp
0x18003dfd3  sub     rsp, 30h
0x18003dfd7  mov     rbp, rdx
0x18003dfda  mov     edx, 1
0x18003dfdf  mov     rcx, [rbp+50h]
0x18003dfe3  call    ?CancelAllPendingIo@CFileIoChannel@@QEAAXW4CancelReason@IoPacket@@@Z; CFileIoChannel::CancelAllPendingIo(IoPacket::CancelReason)
0x18003dfe8  mov     rcx, [rbp+48h]; this
0x18003dfec  lea     r9, aFailedToProces_1; "Failed to process Read Irp"
0x18003dff3  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003dffa  mov     edx, 408h; void *
0x18003dfff  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18003e004  nop
0x18003e005  mov     rax, 0
0x18003e00f  add     rsp, 30h
0x18003e013  pop     rbp
0x18003e014  retn
```
