# _McpGetCloudPrintServiceResult::RuntimeClassInitialize_::_1_::catch$3

- ea: `0x180029a50`
- end: `0x180029a86`
- name: `_McpGetCloudPrintServiceResult::RuntimeClassInitialize_::_1_::catch$3`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029a61`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceresult.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceResult::RuntimeClassInitialize_::_1_::catch_3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x13,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029a50  mov     [rsp+arg_8], rdx
0x180029a55  push    rbp
0x180029a56  sub     rsp, 20h
0x180029a5a  mov     rbp, rdx
0x180029a5d  mov     rcx, [rbp+48h]; this
0x180029a61  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029a68  mov     edx, 13h; void *
0x180029a6d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029a72  mov     [rbp+58h], eax
0x180029a75  mov     rax, 0
0x180029a7f  add     rsp, 20h
0x180029a83  pop     rbp
0x180029a84  retn
```
