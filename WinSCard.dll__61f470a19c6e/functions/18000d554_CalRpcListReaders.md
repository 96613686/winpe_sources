# CalRpcListReaders

- ea: `0x18000d554`
- end: `0x18000d631`
- name: `CalRpcListReaders`
- size: `221`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, int, int pExceptionObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cae0`

## callees

- `0x180006bf0`
- `0x180007940`
- `0x180007bc0`
- `0x18000d554`
- `0x18001991c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d5ca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d5ca`
- `RPCRT4!NdrClientCall3` at `0x18000d58d`
- `RPCRT4!NdrClientCall3` at `0x18000d58d`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CalRpcListReaders(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180034330, 0xBu, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000d554  mov     r11, rsp
0x18000d557  push    rbx
0x18000d558  sub     rsp, 50h
0x18000d55c  mov     qword ptr [r11-10h], 0
0x18000d564  mov     rax, [rsp+58h+arg_20]
0x18000d56c  mov     [r11-20h], rax
0x18000d570  mov     [r11-28h], r9
0x18000d574  mov     [r11-30h], r8d
0x18000d578  mov     [r11-38h], rdx
0x18000d57c  mov     r9, rcx
0x18000d57f  xor     r8d, r8d; pReturnValue
0x18000d582  lea     edx, [r8+0Bh]; nProcNum
0x18000d586  lea     rcx, stru_180034330; pProxyInfo
0x18000d58d  call    cs:__imp_NdrClientCall3
0x18000d593  mov     [rsp+58h+var_10], rax
0x18000d598  mov     [rsp+58h+var_18], eax
0x18000d59c  add     rsp, 50h
0x18000d5a0  pop     rbx
0x18000d5a1  retn
0x18000d5a2  mov     ebx, eax
0x18000d5a4  mov     edx, 2
0x18000d5a9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000d5ae  mov     [rsp+arg_38], ebx
0x18000d5b2  call    SCardAccessStartedEvent
0x18000d5b7  test    rax, rax
0x18000d5ba  jnz     short loc_18000D5C5
0x18000d5bc  lea     ebx, [rax+5]
0x18000d5bf  mov     [rsp+arg_38], ebx
0x18000d5c3  jmp     short loc_18000D5E3
0x18000d5c5  xor     edx, edx; dwMilliseconds
0x18000d5c7  mov     rcx, rax; hHandle
0x18000d5ca  call    cs:__imp_WaitForSingleObject
0x18000d5d0  mov     ecx, 8010001Dh
0x18000d5d5  test    eax, eax
0x18000d5d7  cmovnz  ebx, ecx
0x18000d5da  mov     [rsp+arg_38], ebx
0x18000d5de  call    SCardReleaseStartedEvent
0x18000d5e3  lea     rax, WPP_GLOBAL_Control
0x18000d5ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5f1  cmp     rcx, rax
0x18000d5f4  jz      short loc_18000D61B
0x18000d5f6  test    byte ptr [rcx+1Ch], 10h
0x18000d5fa  jz      short loc_18000D61B
0x18000d5fc  cmp     byte ptr [rcx+19h], 2
0x18000d600  jb      short loc_18000D61B
0x18000d602  mov     edx, 15h
0x18000d607  mov     [rsp+arg_18], ebx
0x18000d60b  lea     r8, WPP_4ef5272161b43f82534a52b1beb9ecde_Traceguids
0x18000d612  mov     rcx, [rcx+10h]
0x18000d616  call    WPP_SF_sd
0x18000d61b  mov     [rsp+pExceptionObject], ebx
0x18000d61f  lea     rdx, _TI1K; pThrowInfo
0x18000d626  lea     rcx, [rsp+pExceptionObject]; pExceptionObject
0x18000d62b  call    _CxxThrowException_0
```
