# CalRpcWriteCache

- ea: `0x18001a5c4`
- end: `0x18001a6ac`
- name: `CalRpcWriteCache`
- size: `232`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, int, int, int, int pExceptionObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180012730`

## callees

- `0x180006bf0`
- `0x180007940`
- `0x180007bc0`
- `0x18001991c`
- `0x18001a5c4`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a645`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a645`
- `RPCRT4!NdrClientCall3` at `0x18001a608`
- `RPCRT4!NdrClientCall3` at `0x18001a608`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CalRpcWriteCache(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, int a6)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800342C8, 1u, 0, a1, a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x18001a5c4  mov     r11, rsp
0x18001a5c7  push    rbx
0x18001a5c8  sub     rsp, 60h
0x18001a5cc  mov     qword ptr [r11-10h], 0
0x18001a5d4  mov     eax, [rsp+68h+arg_28]
0x18001a5db  mov     [rsp+68h+var_28], eax
0x18001a5df  mov     rax, [rsp+68h+arg_20]
0x18001a5e7  mov     [r11-30h], rax
0x18001a5eb  mov     [r11-38h], r9
0x18001a5ef  mov     [r11-40h], r8d
0x18001a5f3  mov     [r11-48h], rdx
0x18001a5f7  mov     r9, rcx
0x18001a5fa  xor     r8d, r8d; pReturnValue
0x18001a5fd  lea     edx, [r8+1]; nProcNum
0x18001a601  lea     rcx, stru_1800342C8; pProxyInfo
0x18001a608  call    cs:__imp_NdrClientCall3
0x18001a60e  mov     [rsp+68h+var_10], rax
0x18001a613  mov     [rsp+68h+var_18], eax
0x18001a617  add     rsp, 60h
0x18001a61b  pop     rbx
0x18001a61c  retn
0x18001a61d  mov     ebx, eax
0x18001a61f  mov     edx, 2
0x18001a624  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001a629  mov     [rsp+arg_48], ebx
0x18001a62d  call    SCardAccessStartedEvent
0x18001a632  test    rax, rax
0x18001a635  jnz     short loc_18001A640
0x18001a637  lea     ebx, [rax+5]
0x18001a63a  mov     [rsp+arg_48], ebx
0x18001a63e  jmp     short loc_18001A65E
0x18001a640  xor     edx, edx; dwMilliseconds
0x18001a642  mov     rcx, rax; hHandle
0x18001a645  call    cs:__imp_WaitForSingleObject
0x18001a64b  mov     ecx, 8010001Dh
0x18001a650  test    eax, eax
0x18001a652  cmovnz  ebx, ecx
0x18001a655  mov     [rsp+arg_48], ebx
0x18001a659  call    SCardReleaseStartedEvent
0x18001a65e  lea     rax, WPP_GLOBAL_Control
0x18001a665  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a66c  cmp     rcx, rax
0x18001a66f  jz      short loc_18001A696
0x18001a671  test    byte ptr [rcx+1Ch], 10h
0x18001a675  jz      short loc_18001A696
0x18001a677  cmp     byte ptr [rcx+19h], 2
0x18001a67b  jb      short loc_18001A696
0x18001a67d  mov     edx, 1Fh
0x18001a682  mov     [rsp+arg_18], ebx
0x18001a686  lea     r8, WPP_4ef5272161b43f82534a52b1beb9ecde_Traceguids
0x18001a68d  mov     rcx, [rcx+10h]
0x18001a691  call    WPP_SF_sd
0x18001a696  mov     [rsp+pExceptionObject], ebx
0x18001a69a  lea     rdx, _TI1K; pThrowInfo
0x18001a6a1  lea     rcx, [rsp+pExceptionObject]; pExceptionObject
0x18001a6a6  call    _CxxThrowException_0
```
