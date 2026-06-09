# CRpcServerUtility::AllowLocalOnlyServerSecurityCallback(void *,void *)

- ea: `0x180019d80`
- end: `0x180019e3f`
- name: `?AllowLocalOnlyServerSecurityCallback@CRpcServerUtility@@SAJPEAX0@Z`
- size: `191`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019d80`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x180019dc1`
- `RPCRT4!RpcStringBindingParseW` at `0x180019dc1`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180019d99`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180019d99`
- `RPCRT4!RpcStringFreeW` at `0x180019e09`
- `RPCRT4!RpcStringFreeW` at `0x180019e1c`
- `RPCRT4!RpcStringFreeW` at `0x180019e09`
- `RPCRT4!RpcStringFreeW` at `0x180019e1c`
- `RPCRT4!RpcRaiseException` at `0x180019e2b`
- `RPCRT4!RpcRaiseException` at `0x180019e2b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019df0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180019df0`

## pseudocode

```c
__int64 __fastcall CRpcServerUtility::AllowLocalOnlyServerSecurityCallback(void *a1, void *a2)
{
  BOOL v2; // ebx
  RPC_WSTR Protseq; // [rsp+50h] [rbp+18h] BYREF
  RPC_WSTR StringBinding; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  StringBinding = 0;
  if ( !RpcBindingToStringBindingW(a2, &StringBinding) )
  {
    Protseq = 0;
    if ( !RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0) )
      v2 = CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncalrpc", 8) == 2;
    if ( Protseq )
      RpcStringFreeW(&Protseq);
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( !v2 )
    RpcRaiseException(1233);
  return 0;
}

```

## disassembly

```asm
0x180019d80  mov     [rsp+arg_0], rbx
0x180019d85  push    rdi
0x180019d86  sub     rsp, 30h
0x180019d8a  mov     rcx, rdx; Binding
0x180019d8d  xor     ebx, ebx
0x180019d8f  lea     rdx, [rsp+38h+StringBinding]; StringBinding
0x180019d94  mov     [rsp+38h+StringBinding], rbx
0x180019d99  call    cs:__imp_RpcBindingToStringBindingW
0x180019d9f  test    eax, eax
0x180019da1  jnz     short loc_180019E0F
0x180019da3  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180019da8  lea     r8, [rsp+38h+Protseq]; Protseq
0x180019dad  mov     [rsp+38h+NetworkOptions], rbx; NetworkOptions
0x180019db2  xor     r9d, r9d; NetworkAddr
0x180019db5  xor     edx, edx; ObjUuid
0x180019db7  mov     [rsp+38h+Endpoint], rbx; Endpoint
0x180019dbc  mov     [rsp+38h+Protseq], rbx
0x180019dc1  call    cs:__imp_RpcStringBindingParseW
0x180019dc7  test    eax, eax
0x180019dc9  jnz     short loc_180019DFC
0x180019dcb  mov     r8, [rsp+38h+Protseq]; lpString1
0x180019dd0  lea     rax, aNcalrpc; "ncalrpc"
0x180019dd7  lea     edi, [rbx+1]
0x180019dda  mov     dword ptr [rsp+38h+NetworkOptions], 8; cchCount2
0x180019de2  mov     edx, edi; dwCmpFlags
0x180019de4  mov     [rsp+38h+Endpoint], rax; lpString2
0x180019de9  or      r9d, 0FFFFFFFFh; cchCount1
0x180019ded  lea     ecx, [rbx+7Fh]; Locale
0x180019df0  call    cs:__imp_CompareStringW
0x180019df6  cmp     eax, 2
0x180019df9  cmovz   ebx, edi
0x180019dfc  cmp     [rsp+38h+Protseq], 0
0x180019e02  jz      short loc_180019E0F
0x180019e04  lea     rcx, [rsp+38h+Protseq]; String
0x180019e09  call    cs:__imp_RpcStringFreeW
0x180019e0f  cmp     [rsp+38h+StringBinding], 0
0x180019e15  jz      short loc_180019E22
0x180019e17  lea     rcx, [rsp+38h+StringBinding]; String
0x180019e1c  call    cs:__imp_RpcStringFreeW
0x180019e22  test    ebx, ebx
0x180019e24  jnz     short loc_180019E32
0x180019e26  mov     ecx, 4D1h; exception
0x180019e2b  call    cs:__imp_RpcRaiseException
0x180019e31  int     3; Trap to Debugger
0x180019e32  mov     rbx, [rsp+38h+arg_0]
0x180019e37  xor     eax, eax
0x180019e39  add     rsp, 30h
0x180019e3d  pop     rdi
0x180019e3e  retn
```
