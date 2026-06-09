# IEnumUICommand_Next_Proxy

- ea: `0x18000a970`
- end: `0x18000a9cd`
- name: `IEnumUICommand_Next_Proxy`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a970`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000a9b6`
- `RPCRT4!NdrClientCall3` at `0x18000a9b6`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall IEnumUICommand_Next_Proxy(__int64 a1, unsigned int a2, __int64 a3, _DWORD *a4)
{
  CLIENT_CALL_RETURN result; // rax
  int v6; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 <= 1 || a4 )
  {
    v6 = 0;
    result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1801E27E0, 3u, 0, a1, a2, a3, &v6).Pointer;
    if ( a4 )
      *a4 = v6;
  }
  else
  {
    return (CLIENT_CALL_RETURN)2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000a970  push    rbx
0x18000a972  sub     rsp, 40h
0x18000a976  mov     rbx, r9
0x18000a979  cmp     edx, 1
0x18000a97c  jbe     short loc_18000A98A
0x18000a97e  test    rbx, rbx
0x18000a981  jnz     short loc_18000A98A
0x18000a983  mov     eax, 80070057h
0x18000a988  jmp     short loc_18000A9C7
0x18000a98a  lea     rax, [rsp+48h+arg_8]
0x18000a98f  mov     [rsp+48h+arg_8], 0
0x18000a997  mov     [rsp+48h+var_18], rax
0x18000a99c  mov     r9, rcx
0x18000a99f  mov     [rsp+48h+var_20], r8
0x18000a9a4  lea     rcx, stru_1801E27E0; pProxyInfo
0x18000a9ab  xor     r8d, r8d; pReturnValue
0x18000a9ae  mov     [rsp+48h+var_28], edx
0x18000a9b2  lea     edx, [r8+3]; nProcNum
0x18000a9b6  call    cs:__imp_NdrClientCall3
0x18000a9bc  test    rbx, rbx
0x18000a9bf  jz      short loc_18000A9C7
0x18000a9c1  mov     ecx, [rsp+48h+arg_8]
0x18000a9c5  mov     [rbx], ecx
0x18000a9c7  add     rsp, 40h
0x18000a9cb  pop     rbx
0x18000a9cc  retn
```
