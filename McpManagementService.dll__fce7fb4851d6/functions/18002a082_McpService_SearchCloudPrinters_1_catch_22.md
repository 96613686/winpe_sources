# _McpService::SearchCloudPrinters_::_1_::catch$22

- ea: `0x18002a082`
- end: `0x18002a0bb`
- name: `_McpService::SearchCloudPrinters_::_1_::catch$22`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x18002a093`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::SearchCloudPrinters_::_1_::catch_22(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 144) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0x1CE,
                            (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002a082  mov     [rsp+arg_8], rdx
0x18002a087  push    rbp
0x18002a088  sub     rsp, 20h
0x18002a08c  mov     rbp, rdx
0x18002a08f  mov     rcx, [rbp+78h]; this
0x18002a093  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002a09a  mov     edx, 1CEh; void *
0x18002a09f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a0a4  mov     [rbp+90h], eax
0x18002a0aa  mov     rax, 0
0x18002a0b4  add     rsp, 20h
0x18002a0b8  pop     rbp
0x18002a0b9  retn
```
