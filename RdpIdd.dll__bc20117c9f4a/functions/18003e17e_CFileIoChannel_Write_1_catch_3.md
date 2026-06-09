# _CFileIoChannel::Write_::_1_::catch$3

- ea: `0x18003e17e`
- end: `0x18003e1c9`
- name: `_CFileIoChannel::Write_::_1_::catch$3`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180033288`
- `0x180034c48`

## string_xrefs

- `0x18003e19d`: `Failed to write IO packet`

## pseudocode

```c
__int64 __fastcall CFileIoChannel::Write_::_1_::catch_3(__int64 a1, __int64 a2)
{
  const char *v4; // [rsp+20h] [rbp-18h]

  CFileIoChannel::CancelAllPendingIo(*(_QWORD *)(a2 + 96), 1u);
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtExceptionMsg(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x204,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           "Failed to write IO packet",
                           v4);
  return 0;
}

```

## disassembly

```asm
0x18003e17e  mov     [rsp+arg_8], rdx
0x18003e183  push    rbp
0x18003e184  sub     rsp, 30h
0x18003e188  mov     rbp, rdx
0x18003e18b  mov     edx, 1
0x18003e190  mov     rcx, [rbp+60h]
0x18003e194  call    ?CancelAllPendingIo@CFileIoChannel@@QEAAXW4CancelReason@IoPacket@@@Z; CFileIoChannel::CancelAllPendingIo(IoPacket::CancelReason)
0x18003e199  mov     rcx, [rbp+58h]; this
0x18003e19d  lea     r9, aFailedToWriteI; "Failed to write IO packet"
0x18003e1a4  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003e1ab  mov     edx, 204h; void *
0x18003e1b0  call    ?Return_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18003e1b5  mov     [rbp+60h], eax
0x18003e1b8  mov     rax, 0
0x18003e1c2  add     rsp, 30h
0x18003e1c6  pop     rbp
0x18003e1c7  retn
```
