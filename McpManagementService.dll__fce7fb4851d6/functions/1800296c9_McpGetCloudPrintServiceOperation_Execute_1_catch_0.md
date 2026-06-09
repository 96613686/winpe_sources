# _McpGetCloudPrintServiceOperation::Execute_::_1_::catch$0

- ea: `0x1800296c9`
- end: `0x1800296fd`
- name: `_McpGetCloudPrintServiceOperation::Execute_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180019be8`

## string_xrefs

- `0x1800296da`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceOperation::Execute_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x73,
    (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800296c9  mov     [rsp+arg_8], rdx
0x1800296ce  push    rbp
0x1800296cf  sub     rsp, 20h
0x1800296d3  mov     rbp, rdx
0x1800296d6  mov     rcx, [rbp+28h]; this
0x1800296da  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800296e1  mov     edx, 73h ; 's'; void *
0x1800296e6  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800296eb  nop
0x1800296ec  mov     rax, 0
0x1800296f6  add     rsp, 20h
0x1800296fa  pop     rbp
0x1800296fb  retn
```
