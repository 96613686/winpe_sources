# _CdsToInputTaskHandler::Start_::_1_::catch$9

- ea: `0x18002f8d7`
- end: `0x18002f910`
- name: `_CdsToInputTaskHandler::Start_::_1_::catch$9`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180021458`

## string_xrefs

- `0x18002f8eb`: `onecoreuap\windows\input\cloudstore\lib\cdstoinputtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CdsToInputTaskHandler::Start_::_1_::catch_9(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x1EA,
                           (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\cdstoinputtaskhandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002f8d7  mov     [rsp+arg_8], rdx
0x18002f8dc  push    rbp
0x18002f8dd  sub     rsp, 20h
0x18002f8e1  mov     rbp, rdx
0x18002f8e4  mov     rcx, [rbp+88h]; this
0x18002f8eb  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\input\\cloudstore"...
0x18002f8f2  mov     edx, 1EAh; void *
0x18002f8f7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002f8fc  mov     [rbp+20h], eax
0x18002f8ff  mov     rax, 0
0x18002f909  add     rsp, 20h
0x18002f90d  pop     rbp
0x18002f90e  retn
```
