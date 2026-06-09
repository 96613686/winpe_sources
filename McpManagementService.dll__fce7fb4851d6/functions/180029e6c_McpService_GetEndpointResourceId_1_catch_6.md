# _McpService::GetEndpointResourceId_::_1_::catch$6

- ea: `0x180029e6c`
- end: `0x180029ea2`
- name: `_McpService::GetEndpointResourceId_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029e7d`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::GetEndpointResourceId_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0xC6,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029e6c  mov     [rsp+arg_8], rdx
0x180029e71  push    rbp
0x180029e72  sub     rsp, 20h
0x180029e76  mov     rbp, rdx
0x180029e79  mov     rcx, [rbp+78h]; this
0x180029e7d  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029e84  mov     edx, 0C6h; void *
0x180029e89  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029e8e  mov     [rbp+20h], eax
0x180029e91  mov     rax, 0
0x180029e9b  add     rsp, 20h
0x180029e9f  pop     rbp
0x180029ea0  retn
```
