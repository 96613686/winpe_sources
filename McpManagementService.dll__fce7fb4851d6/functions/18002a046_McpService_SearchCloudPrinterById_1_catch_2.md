# _McpService::SearchCloudPrinterById_::_1_::catch$2

- ea: `0x18002a046`
- end: `0x18002a07c`
- name: `_McpService::SearchCloudPrinterById_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x18002a057`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::SearchCloudPrinterById_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x15A,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002a046  mov     [rsp+arg_8], rdx
0x18002a04b  push    rbp
0x18002a04c  sub     rsp, 20h
0x18002a050  mov     rbp, rdx
0x18002a053  mov     rcx, [rbp+68h]; this
0x18002a057  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002a05e  mov     edx, 15Ah; void *
0x18002a063  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002a068  mov     [rbp+20h], eax
0x18002a06b  mov     rax, 0
0x18002a075  add     rsp, 20h
0x18002a079  pop     rbp
0x18002a07a  retn
```
