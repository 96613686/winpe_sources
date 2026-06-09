# _McpGetCloudPrintServiceResult::GetOperationResult_::_1_::catch$0

- ea: `0x180029a14`
- end: `0x180029a4a`
- name: `_McpGetCloudPrintServiceResult::GetOperationResult_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029a25`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceresult.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceResult::GetOperationResult_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x1E,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029a14  mov     [rsp+arg_8], rdx
0x180029a19  push    rbp
0x180029a1a  sub     rsp, 20h
0x180029a1e  mov     rbp, rdx
0x180029a21  mov     rcx, [rbp+28h]; this
0x180029a25  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029a2c  mov     edx, 1Eh; void *
0x180029a31  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029a36  mov     [rbp+38h], eax
0x180029a39  mov     rax, 0
0x180029a43  add     rsp, 20h
0x180029a47  pop     rbp
0x180029a48  retn
```
