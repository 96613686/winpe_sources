# _InputToCdsTaskHandler::Start_::_1_::catch$9

- ea: `0x18002f6b3`
- end: `0x18002f6ec`
- name: `_InputToCdsTaskHandler::Start_::_1_::catch$9`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180021458`

## string_xrefs

- `0x18002f6c7`: `onecoreuap\windows\input\cloudstore\lib\inputtocdstaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall InputToCdsTaskHandler::Start_::_1_::catch_9(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x1D7,
                           (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\inputtocdstaskhandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002f6b3  mov     [rsp+arg_8], rdx
0x18002f6b8  push    rbp
0x18002f6b9  sub     rsp, 20h
0x18002f6bd  mov     rbp, rdx
0x18002f6c0  mov     rcx, [rbp+88h]; this
0x18002f6c7  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\input\\cloudstore"...
0x18002f6ce  mov     edx, 1D7h; void *
0x18002f6d3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002f6d8  mov     [rbp+20h], eax
0x18002f6db  mov     rax, 0
0x18002f6e5  add     rsp, 20h
0x18002f6e9  pop     rbp
0x18002f6ea  retn
```
