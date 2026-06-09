# _Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize_::_1_::catch$1

- ea: `0x140012d17`
- end: `0x140012d63`
- name: `_Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize_::_1_::catch$1`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007dd4`
- `0x140007e14`

## string_xrefs

- `0x140012d3b`: `onecoreuap\ds\security\isolation\broker\lib\filedialogbroker.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileOpenDialogBroker::RuntimeClassInitialize_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  const char *v3; // r9

  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(*(_QWORD *)(a2 + 144) + 120LL);
  *(_DWORD *)(a2 + 152) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0x3B,
                            (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\filedialogbroker.cpp",
                            v3);
  return 0;
}

```

## disassembly

```asm
0x140012d17  mov     [rsp+arg_8], rdx
0x140012d1c  push    rbp
0x140012d1d  sub     rsp, 20h
0x140012d21  mov     rbp, rdx
0x140012d24  mov     rcx, [rbp+90h]
0x140012d2b  add     rcx, 78h ; 'x'
0x140012d2f  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140012d34  mov     rcx, [rbp+88h]; this
0x140012d3b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\isolation\\br"...
0x140012d42  mov     edx, 3Bh ; ';'; void *
0x140012d47  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x140012d4c  mov     [rbp+98h], eax
0x140012d52  mov     rax, 0
0x140012d5c  add     rsp, 20h
0x140012d60  pop     rbp
0x140012d61  retn
```
