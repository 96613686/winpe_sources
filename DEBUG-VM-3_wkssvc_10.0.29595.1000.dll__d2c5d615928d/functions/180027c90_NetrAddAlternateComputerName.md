# NetrAddAlternateComputerName

- ea: `0x180027c90`
- end: `0x180027d6e`
- name: `NetrAddAlternateComputerName`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007604`
- `0x180009a40`
- `0x18000a0c0`
- `0x18002016c`
- `0x180026088`
- `0x180026840`
- `0x180027c90`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027d26`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027d26`

## string_xrefs

- `0x180027d1f`: `NetrAddAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrAddAlternateComputerName(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  const WCHAR *v13; // rdi
  unsigned int v14; // ebx
  const WCHAR *v15; // [rsp+40h] [rbp-38h] BYREF

  v15 = 0;
  result = WsValidateRpcProtSeq(a1);
  if ( !(_DWORD)result )
  {
    if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    {
      return 5;
    }
    else
    {
      v11 = JoinpDecryptPasswordWithKey(a1, a5, 0, (__int64 *)&v15);
      v13 = v15;
      v14 = v11;
      if ( v11 )
      {
        if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v12) )
          NetpLogPrintHelper(L"NetrAddAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
      }
      else
      {
        v14 = NetpManageAltComputerName(a1, a3, 1u, a4, v15, a6);
      }
      if ( v13 )
        NetpMemoryFree(v13);
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027c90  push    rbx
0x180027c92  push    rbp
0x180027c93  push    rsi
0x180027c94  push    rdi
0x180027c95  push    r14
0x180027c97  sub     rsp, 50h
0x180027c9b  mov     rbp, r9
0x180027c9e  mov     [rsp+78h+var_38], 0
0x180027ca7  mov     r14, r8
0x180027caa  mov     rsi, rcx
0x180027cad  call    WsValidateRpcProtSeq
0x180027cb2  test    eax, eax
0x180027cb4  jnz     loc_180027D63
0x180027cba  mov     rax, cs:NetApiSd
0x180027cc1  lea     rcx, WsNetApiMapping
0x180027cc8  mov     [rsp+78h+var_48], rcx
0x180027ccd  lea     r8, aNetapi; "NetAPI"
0x180027cd4  mov     [rsp+78h+var_50], 1
0x180027cdc  mov     [rsp+78h+var_58], rax
0x180027ce1  call    NetpAccessCheckAndAuditEx
0x180027ce6  test    eax, eax
0x180027ce8  jz      short loc_180027CF1
0x180027cea  mov     eax, 5
0x180027cef  jmp     short loc_180027D63
0x180027cf1  mov     rdx, [rsp+78h+arg_20]
0x180027cf9  lea     r9, [rsp+78h+var_38]
0x180027cfe  xor     r8d, r8d
0x180027d01  mov     rcx, rsi
0x180027d04  call    JoinpDecryptPasswordWithKey
0x180027d09  mov     rdi, [rsp+78h+var_38]
0x180027d0e  mov     ebx, eax
0x180027d10  test    eax, eax
0x180027d12  jz      short loc_180027D2E
0x180027d14  call    IsNetpManageIPCConnectPresent
0x180027d19  test    al, al
0x180027d1b  jz      short loc_180027D54
0x180027d1d  mov     edx, ebx
0x180027d1f  lea     rcx, aNetraddalterna; "NetrAddAlternateComputerName: JoinpDecr"...
0x180027d26  call    cs:__imp_NetpLogPrintHelper
0x180027d2c  jmp     short loc_180027D54
0x180027d2e  mov     eax, [rsp+78h+arg_28]
0x180027d35  mov     r9, rbp
0x180027d38  mov     [rsp+78h+var_50], eax
0x180027d3c  mov     r8d, 1
0x180027d42  mov     rdx, r14
0x180027d45  mov     [rsp+78h+var_58], rdi
0x180027d4a  mov     rcx, rsi
0x180027d4d  call    NetpManageAltComputerName
0x180027d52  mov     ebx, eax
0x180027d54  test    rdi, rdi
0x180027d57  jz      short loc_180027D61
0x180027d59  mov     rcx, rdi
0x180027d5c  call    NetpMemoryFree
0x180027d61  mov     eax, ebx
0x180027d63  add     rsp, 50h
0x180027d67  pop     r14
0x180027d69  pop     rdi
0x180027d6a  pop     rsi
0x180027d6b  pop     rbp
0x180027d6c  pop     rbx
0x180027d6d  retn
```
