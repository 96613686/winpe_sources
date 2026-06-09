# _McpService::SearchCloudPrinters_::_1_::catch$17

- ea: `0x18002a0c1`
- end: `0x18002a0fa`
- name: `_McpService::SearchCloudPrinters_::_1_::catch$17`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x18002a0d5`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::SearchCloudPrinters_::_1_::catch_17(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 152),
                           (void *)0x14D,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a0c1  mov     [rsp+arg_8], rdx
0x18002a0c6  push    rbp
0x18002a0c7  sub     rsp, 20h
0x18002a0cb  mov     rbp, rdx
0x18002a0ce  mov     rcx, [rbp+98h]; this
0x18002a0d5  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002a0dc  mov     edx, 14Dh; void *
0x18002a0e1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a0e6  mov     [rbp+20h], eax
0x18002a0e9  mov     rax, 0
0x18002a0f3  add     rsp, 20h
0x18002a0f7  pop     rbp
0x18002a0f8  retn
```
