# _CFileIoChannel::OnWriteIrpAvailable_::_1_::catch$1

- ea: `0x18003e02e`
- end: `0x18003e079`
- name: `_CFileIoChannel::OnWriteIrpAvailable_::_1_::catch$1`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180033288`
- `0x180034144`

## string_xrefs

- `0x18003e04d`: `Failed to process Write Irp`

## pseudocode

```c
__int64 __fastcall CFileIoChannel::OnWriteIrpAvailable_::_1_::catch_1(__int64 a1, __int64 a2)
{
  const char *v4; // [rsp+20h] [rbp-18h]

  CFileIoChannel::CancelAllPendingIo(*(_QWORD *)(a2 + 96), 1u);
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Nt_Return_CaughtExceptionMsg(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x448,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           "Failed to process Write Irp",
                           v4);
  return 0;
}

```

## disassembly

```asm
0x18003e02e  mov     [rsp+arg_8], rdx
0x18003e033  push    rbp
0x18003e034  sub     rsp, 30h
0x18003e038  mov     rbp, rdx
0x18003e03b  mov     edx, 1
0x18003e040  mov     rcx, [rbp+60h]
0x18003e044  call    ?CancelAllPendingIo@CFileIoChannel@@QEAAXW4CancelReason@IoPacket@@@Z; CFileIoChannel::CancelAllPendingIo(IoPacket::CancelReason)
0x18003e049  mov     rcx, [rbp+58h]; this
0x18003e04d  lea     r9, aFailedToProces; "Failed to process Write Irp"
0x18003e054  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003e05b  mov     edx, 448h; void *
0x18003e060  call    ?Nt_Return_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Nt_Return_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18003e065  mov     [rbp+60h], eax
0x18003e068  mov     rax, 0
0x18003e072  add     rsp, 30h
0x18003e076  pop     rbp
0x18003e077  retn
```
