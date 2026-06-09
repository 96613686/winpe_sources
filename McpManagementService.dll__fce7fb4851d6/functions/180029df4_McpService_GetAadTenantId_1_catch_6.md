# _McpService::GetAadTenantId_::_1_::catch$6

- ea: `0x180029df4`
- end: `0x180029e2a`
- name: `_McpService::GetAadTenantId_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029e05`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::GetAadTenantId_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0xAB,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029df4  mov     [rsp+arg_8], rdx
0x180029df9  push    rbp
0x180029dfa  sub     rsp, 20h
0x180029dfe  mov     rbp, rdx
0x180029e01  mov     rcx, [rbp+78h]; this
0x180029e05  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029e0c  mov     edx, 0ABh; void *
0x180029e11  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029e16  mov     [rbp+20h], eax
0x180029e19  mov     rax, 0
0x180029e23  add     rsp, 20h
0x180029e27  pop     rbp
0x180029e28  retn
```
