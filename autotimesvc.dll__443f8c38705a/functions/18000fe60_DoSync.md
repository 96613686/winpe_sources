# DoSync

- ea: `0x18000fe60`
- end: `0x18000fecb`
- name: `DoSync`
- size: `107`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180010ac0`

## callees

- `0x18000a674`
- `0x18000fe60`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x1800115d9`
- `RPCRT4!RpcExceptionFilter` at `0x1800115d9`
- `RPCRT4!NdrClientCall3` at `0x18000fe8a`
- `RPCRT4!NdrClientCall3` at `0x18000fe8a`

## string_xrefs

- `0x18000feb3`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall DoSync(__int64 a1)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1);
}

```

## disassembly

```asm
0x18000fe60  mov     rax, rsp
0x18000fe63  push    rbx
0x18000fe64  sub     rsp, 40h
0x18000fe68  xor     ebx, ebx
0x18000fe6a  mov     [rax-18h], ebx
0x18000fe6d  mov     [rax+18h], rbx
0x18000fe71  mov     [rax-20h], edx
0x18000fe74  mov     dword ptr [rax-28h], 1
0x18000fe7b  mov     r9, rcx
0x18000fe7e  xor     r8d, r8d; pReturnValue
0x18000fe81  xor     edx, edx; nProcNum
0x18000fe83  lea     rcx, pProxyInfo; pProxyInfo
0x18000fe8a  call    cs:__imp_NdrClientCall3
0x18000fe90  mov     [rsp+48h+arg_10], rax
0x18000fe95  mov     [rsp+48h+var_18], eax
0x18000fe99  jmp     short loc_18000FEA1
0x18000fe9b  mov     ebx, eax
0x18000fe9d  mov     eax, [rsp+48h+var_18]
0x18000fea1  test    ebx, ebx
0x18000fea3  jz      short loc_18000FEC5
0x18000fea5  or      ebx, 80010000h
0x18000feab  mov     rcx, [rsp+48h]; this
0x18000feb0  mov     r9d, ebx; char *
0x18000feb3  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x18000feba  mov     edx, 0EBh; void *
0x18000febf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fec5  add     rsp, 40h
0x18000fec9  pop     rbx
0x18000feca  retn
0x1800115cb  push    rbp
0x1800115cd  sub     rsp, 30h
0x1800115d1  mov     rbp, rdx
0x1800115d4  mov     rcx, [rcx]
0x1800115d7  mov     ecx, [rcx]; ExceptionCode
0x1800115d9  call    cs:__imp_RpcExceptionFilter
0x1800115df  nop
0x1800115e0  add     rsp, 30h
0x1800115e4  pop     rbp
0x1800115e5  retn
```
