# _McpService::GetOAuthAuthority_::_1_::catch$6

- ea: `0x180029ee4`
- end: `0x180029f1a`
- name: `_McpService::GetOAuthAuthority_::_1_::catch$6`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029ef5`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::GetOAuthAuthority_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x75,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029ee4  mov     [rsp+arg_8], rdx
0x180029ee9  push    rbp
0x180029eea  sub     rsp, 20h
0x180029eee  mov     rbp, rdx
0x180029ef1  mov     rcx, [rbp+78h]; this
0x180029ef5  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029efc  mov     edx, 75h ; 'u'; void *
0x180029f01  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029f06  mov     [rbp+20h], eax
0x180029f09  mov     rax, 0
0x180029f13  add     rsp, 20h
0x180029f17  pop     rbp
0x180029f18  retn
```
