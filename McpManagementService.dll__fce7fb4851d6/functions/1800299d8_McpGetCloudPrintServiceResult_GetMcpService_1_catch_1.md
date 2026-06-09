# _McpGetCloudPrintServiceResult::GetMcpService_::_1_::catch$1

- ea: `0x1800299d8`
- end: `0x180029a0e`
- name: `_McpGetCloudPrintServiceResult::GetMcpService_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x1800299e9`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceresult.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceResult::GetMcpService_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x36,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800299d8  mov     [rsp+arg_8], rdx
0x1800299dd  push    rbp
0x1800299de  sub     rsp, 20h
0x1800299e2  mov     rbp, rdx
0x1800299e5  mov     rcx, [rbp+28h]; this
0x1800299e9  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800299f0  mov     edx, 36h ; '6'; void *
0x1800299f5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800299fa  mov     [rbp+38h], eax
0x1800299fd  mov     rax, 0
0x180029a07  add     rsp, 20h
0x180029a0b  pop     rbp
0x180029a0c  retn
```
