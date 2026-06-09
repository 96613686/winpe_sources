# _McpGetCloudPrintServiceOperation::WaitForCompletion_::_1_::catch$1

- ea: `0x180029745`
- end: `0x18002977b`
- name: `_McpGetCloudPrintServiceOperation::WaitForCompletion_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029756`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceOperation::WaitForCompletion_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x6C,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029745  mov     [rsp+arg_8], rdx
0x18002974a  push    rbp
0x18002974b  sub     rsp, 30h
0x18002974f  mov     rbp, rdx
0x180029752  mov     rcx, [rbp+38h]; this
0x180029756  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002975d  mov     edx, 6Ch ; 'l'; void *
0x180029762  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029767  mov     [rbp+48h], eax
0x18002976a  mov     rax, 0
0x180029774  add     rsp, 30h
0x180029778  pop     rbp
0x180029779  retn
```
