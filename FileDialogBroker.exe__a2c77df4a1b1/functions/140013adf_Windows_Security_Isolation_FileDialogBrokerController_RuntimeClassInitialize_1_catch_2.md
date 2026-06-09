# _Windows::Security::Isolation::FileDialogBrokerController::RuntimeClassInitialize_::_1_::catch$2

- ea: `0x140013adf`
- end: `0x140013b36`
- name: `_Windows::Security::Isolation::FileDialogBrokerController::RuntimeClassInitialize_::_1_::catch$2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007dd4`
- `0x140007e14`

## string_xrefs

- `0x140013b0d`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbrokercontroller.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerController::RuntimeClassInitialize_::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  const char *v4; // r9

  v3 = *(_QWORD *)(a2 + 144);
  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(v3 + 40);
  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(v3 + 32);
  *(_DWORD *)(a2 + 152) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0x39,
                            (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbrokercontroller.cpp",
                            v4);
  return 0;
}

```

## disassembly

```asm
0x140013adf  mov     [rsp+arg_8], rdx
0x140013ae4  push    rbx
0x140013ae5  push    rbp
0x140013ae6  sub     rsp, 28h
0x140013aea  mov     rbp, rdx
0x140013aed  mov     rbx, [rbp+90h]
0x140013af4  lea     rcx, [rbx+28h]
0x140013af8  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140013afd  lea     rcx, [rbx+20h]
0x140013b01  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140013b06  mov     rcx, [rbp+88h]; this
0x140013b0d  lea     r8, aOnecoreuapDsSe_3; "onecoreuap\\ds\\security\\isolation\\br"...
0x140013b14  mov     edx, 39h ; '9'; void *
0x140013b19  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140013b1e  mov     [rbp+98h], eax
0x140013b24  mov     rax, 0
0x140013b2e  add     rsp, 28h
0x140013b32  pop     rbp
0x140013b33  pop     rbx
0x140013b34  retn
```
