# NetrSetPrimaryComputerName

- ea: `0x180028ee0`
- end: `0x180028fbe`
- name: `NetrSetPrimaryComputerName`
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
- `0x180028ee0`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028f76`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028f76`

## string_xrefs

- `0x180028f6f`: `NetrSetPrimaryComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrSetPrimaryComputerName(
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
          NetpLogPrintHelper(L"NetrSetPrimaryComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
      }
      else
      {
        v14 = NetpManageAltComputerName(a1, a3, 3u, a4, v15, a6);
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
0x180028ee0  push    rbx
0x180028ee2  push    rbp
0x180028ee3  push    rsi
0x180028ee4  push    rdi
0x180028ee5  push    r14
0x180028ee7  sub     rsp, 50h
0x180028eeb  mov     rbp, r9
0x180028eee  mov     [rsp+78h+var_38], 0
0x180028ef7  mov     r14, r8
0x180028efa  mov     rsi, rcx
0x180028efd  call    WsValidateRpcProtSeq
0x180028f02  test    eax, eax
0x180028f04  jnz     loc_180028FB3
0x180028f0a  mov     rax, cs:NetApiSd
0x180028f11  lea     rcx, WsNetApiMapping
0x180028f18  mov     [rsp+78h+var_48], rcx
0x180028f1d  lea     r8, aNetapi; "NetAPI"
0x180028f24  mov     [rsp+78h+var_50], 1
0x180028f2c  mov     [rsp+78h+var_58], rax
0x180028f31  call    NetpAccessCheckAndAuditEx
0x180028f36  test    eax, eax
0x180028f38  jz      short loc_180028F41
0x180028f3a  mov     eax, 5
0x180028f3f  jmp     short loc_180028FB3
0x180028f41  mov     rdx, [rsp+78h+arg_20]
0x180028f49  lea     r9, [rsp+78h+var_38]
0x180028f4e  xor     r8d, r8d
0x180028f51  mov     rcx, rsi
0x180028f54  call    JoinpDecryptPasswordWithKey
0x180028f59  mov     rdi, [rsp+78h+var_38]
0x180028f5e  mov     ebx, eax
0x180028f60  test    eax, eax
0x180028f62  jz      short loc_180028F7E
0x180028f64  call    IsNetpManageIPCConnectPresent
0x180028f69  test    al, al
0x180028f6b  jz      short loc_180028FA4
0x180028f6d  mov     edx, ebx
0x180028f6f  lea     rcx, aNetrsetprimary; "NetrSetPrimaryComputerName: JoinpDecryp"...
0x180028f76  call    cs:__imp_NetpLogPrintHelper
0x180028f7c  jmp     short loc_180028FA4
0x180028f7e  mov     eax, [rsp+78h+arg_28]
0x180028f85  mov     r9, rbp
0x180028f88  mov     [rsp+78h+var_50], eax
0x180028f8c  mov     r8d, 3
0x180028f92  mov     rdx, r14
0x180028f95  mov     [rsp+78h+var_58], rdi
0x180028f9a  mov     rcx, rsi
0x180028f9d  call    NetpManageAltComputerName
0x180028fa2  mov     ebx, eax
0x180028fa4  test    rdi, rdi
0x180028fa7  jz      short loc_180028FB1
0x180028fa9  mov     rcx, rdi
0x180028fac  call    NetpMemoryFree
0x180028fb1  mov     eax, ebx
0x180028fb3  add     rsp, 50h
0x180028fb7  pop     r14
0x180028fb9  pop     rdi
0x180028fba  pop     rsi
0x180028fbb  pop     rbp
0x180028fbc  pop     rbx
0x180028fbd  retn
```
