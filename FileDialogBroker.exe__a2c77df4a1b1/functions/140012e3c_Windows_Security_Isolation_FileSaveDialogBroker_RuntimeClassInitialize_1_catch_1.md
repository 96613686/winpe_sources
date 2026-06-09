# _Windows::Security::Isolation::FileSaveDialogBroker::RuntimeClassInitialize_::_1_::catch$1

- ea: `0x140012e3c`
- end: `0x140012e88`
- name: `_Windows::Security::Isolation::FileSaveDialogBroker::RuntimeClassInitialize_::_1_::catch$1`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007dd4`
- `0x140007e14`

## string_xrefs

- `0x140012e60`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileSaveDialogBroker::RuntimeClassInitialize_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  const char *v3; // r9

  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(*(_QWORD *)(a2 + 144) + 120LL);
  *(_DWORD *)(a2 + 152) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0xCD,
                            (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                            v3);
  return 0;
}

```

## disassembly

```asm
0x140012e3c  mov     [rsp+arg_8], rdx
0x140012e41  push    rbp
0x140012e42  sub     rsp, 20h
0x140012e46  mov     rbp, rdx
0x140012e49  mov     rcx, [rbp+90h]
0x140012e50  add     rcx, 78h ; 'x'
0x140012e54  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140012e59  mov     rcx, [rbp+88h]; this
0x140012e60  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140012e67  mov     edx, 0CDh; void *
0x140012e6c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140012e71  mov     [rbp+98h], eax
0x140012e77  mov     rax, 0
0x140012e81  add     rsp, 20h
0x140012e85  pop     rbp
0x140012e86  retn
```
