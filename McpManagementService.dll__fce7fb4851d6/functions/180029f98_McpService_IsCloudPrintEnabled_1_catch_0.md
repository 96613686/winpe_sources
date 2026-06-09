# _McpService::IsCloudPrintEnabled_::_1_::catch$0

- ea: `0x180029f98`
- end: `0x180029fce`
- name: `_McpService::IsCloudPrintEnabled_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029fa9`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::IsCloudPrintEnabled_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x29,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029f98  mov     [rsp+arg_8], rdx
0x180029f9d  push    rbp
0x180029f9e  sub     rsp, 20h
0x180029fa2  mov     rbp, rdx
0x180029fa5  mov     rcx, [rbp+28h]; this
0x180029fa9  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029fb0  mov     edx, 29h ; ')'; void *
0x180029fb5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029fba  mov     [rbp+38h], eax
0x180029fbd  mov     rax, 0
0x180029fc7  add     rsp, 20h
0x180029fcb  pop     rbp
0x180029fcc  retn
```
