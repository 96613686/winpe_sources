# McpOperationHandler::WaitForCompletion(long *)

- ea: `0x1800236e4`
- end: `0x180023764`
- name: `?WaitForCompletion@McpOperationHandler@@QEAAJPEAJ@Z`
- size: `128`
- prototype: `int(McpOperationHandler *__hidden this, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022790`
- `0x1800230d0`
- `0x180024de0`

## callees

- `0x180008b20`
- `0x18000c4cc`
- `0x1800236e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002372b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002372b`

## pseudocode

```c
__int64 __fastcall McpOperationHandler::WaitForCompletion(HANDLE *this, int *a2)
{
  DWORD v5; // eax
  __int64 v6; // r8
  const char *v7; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = -2147467259;
    v5 = WaitForSingleObjectEx(this[9], 0xFFFFFFFF, 0);
    if ( v5 != 258 )
    {
      if ( v5 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v6, v7);
    }
    *a2 = *(_DWORD *)this;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpoperationhandler.cpp",
      (const char *)0x80004003LL,
      v8);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800236e4  mov     [rsp+arg_0], rbx
0x1800236e9  push    rdi; int
0x1800236ea  sub     rsp, 20h
0x1800236ee  mov     rbx, rdx
0x1800236f1  mov     rdi, rcx
0x1800236f4  test    rdx, rdx
0x1800236f7  jnz     short loc_18002371B
0x1800236f9  mov     rcx, [rsp+28h]; this
0x1800236fe  mov     ebx, 80004003h
0x180023703  mov     r9d, ebx; char *
0x180023706  lea     r8, aOnecoreuapPrin_9; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002370d  mov     edx, 20h ; ' '; void *
0x180023712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023717  mov     eax, ebx
0x180023719  jmp     short loc_180023758
0x18002371b  mov     dword ptr [rdx], 80004005h
0x180023721  xor     r8d, r8d; bAlertable
0x180023724  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023727  mov     rcx, [rcx+48h]; hHandle
0x18002372b  call    cs:__imp_WaitForSingleObjectEx
0x180023731  cmp     eax, 102h
0x180023736  jz      short loc_18002374C
0x180023738  test    eax, eax
0x18002373a  jz      short loc_18002374C
0x18002373c  mov     rcx, [rsp+28h]; this
0x180023741  mov     edx, 0B0Fh; void *
0x180023746  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002374c  mov     eax, [rdi]
0x18002374e  mov     [rbx], eax
0x180023750  xor     eax, eax
0x180023752  jmp     short loc_180023758
0x180023754  mov     eax, [rsp+28h+arg_8]
0x180023758  mov     rbx, [rsp+28h+arg_0]
0x18002375d  add     rsp, 20h
0x180023761  pop     rdi
0x180023762  retn
```
