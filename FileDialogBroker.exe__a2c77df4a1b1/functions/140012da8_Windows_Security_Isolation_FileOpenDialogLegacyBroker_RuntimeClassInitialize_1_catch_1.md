# _Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize_::_1_::catch$1

- ea: `0x140012da8`
- end: `0x140012df7`
- name: `_Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize_::_1_::catch$1`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007dd4`
- `0x140007e14`

## string_xrefs

- `0x140012dcf`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogLegacyBroker::RuntimeClassInitialize_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  const char *v3; // r9

  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(*(_QWORD *)(a2 + 144) + 136LL);
  *(_DWORD *)(a2 + 152) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0x15D,
                            (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                            v3);
  return 0;
}

```

## disassembly

```asm
0x140012da8  mov     [rsp+arg_8], rdx
0x140012dad  push    rbp
0x140012dae  sub     rsp, 20h
0x140012db2  mov     rbp, rdx
0x140012db5  mov     rcx, [rbp+90h]
0x140012dbc  add     rcx, 88h
0x140012dc3  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140012dc8  mov     rcx, [rbp+88h]; this
0x140012dcf  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140012dd6  mov     edx, 15Dh; void *
0x140012ddb  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140012de0  mov     [rbp+98h], eax
0x140012de6  mov     rax, 0
0x140012df0  add     rsp, 20h
0x140012df4  pop     rbp
0x140012df5  retn
```
