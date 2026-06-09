# NetrSetPrimaryComputerName2

- ea: `0x180028fd0`
- end: `0x1800290ae`
- name: `NetrSetPrimaryComputerName2`
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
- `0x180026300`
- `0x180026840`
- `0x180028fd0`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029066`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180029066`

## string_xrefs

- `0x18002905f`: `NetrSetPrimaryComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrSetPrimaryComputerName2(
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
      v11 = JoinpDecryptPasswordWithKeyAES(a1, a5, 0, &v15);
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
0x180028fd0  push    rbx
0x180028fd2  push    rbp
0x180028fd3  push    rsi
0x180028fd4  push    rdi
0x180028fd5  push    r14
0x180028fd7  sub     rsp, 50h
0x180028fdb  mov     rbp, r9
0x180028fde  mov     [rsp+78h+var_38], 0
0x180028fe7  mov     r14, r8
0x180028fea  mov     rsi, rcx
0x180028fed  call    WsValidateRpcProtSeq
0x180028ff2  test    eax, eax
0x180028ff4  jnz     loc_1800290A3
0x180028ffa  mov     rax, cs:NetApiSd
0x180029001  lea     rcx, WsNetApiMapping
0x180029008  mov     [rsp+78h+var_48], rcx
0x18002900d  lea     r8, aNetapi; "NetAPI"
0x180029014  mov     [rsp+78h+var_50], 1
0x18002901c  mov     [rsp+78h+var_58], rax
0x180029021  call    NetpAccessCheckAndAuditEx
0x180029026  test    eax, eax
0x180029028  jz      short loc_180029031
0x18002902a  mov     eax, 5
0x18002902f  jmp     short loc_1800290A3
0x180029031  mov     rdx, [rsp+78h+arg_20]
0x180029039  lea     r9, [rsp+78h+var_38]
0x18002903e  xor     r8d, r8d
0x180029041  mov     rcx, rsi
0x180029044  call    JoinpDecryptPasswordWithKeyAES
0x180029049  mov     rdi, [rsp+78h+var_38]
0x18002904e  mov     ebx, eax
0x180029050  test    eax, eax
0x180029052  jz      short loc_18002906E
0x180029054  call    IsNetpManageIPCConnectPresent
0x180029059  test    al, al
0x18002905b  jz      short loc_180029094
0x18002905d  mov     edx, ebx
0x18002905f  lea     rcx, aNetrsetprimary; "NetrSetPrimaryComputerName: JoinpDecryp"...
0x180029066  call    cs:__imp_NetpLogPrintHelper
0x18002906c  jmp     short loc_180029094
0x18002906e  mov     eax, [rsp+78h+arg_28]
0x180029075  mov     r9, rbp
0x180029078  mov     [rsp+78h+var_50], eax
0x18002907c  mov     r8d, 3
0x180029082  mov     rdx, r14
0x180029085  mov     [rsp+78h+var_58], rdi
0x18002908a  mov     rcx, rsi
0x18002908d  call    NetpManageAltComputerName
0x180029092  mov     ebx, eax
0x180029094  test    rdi, rdi
0x180029097  jz      short loc_1800290A1
0x180029099  mov     rcx, rdi
0x18002909c  call    NetpMemoryFree
0x1800290a1  mov     eax, ebx
0x1800290a3  add     rsp, 50h
0x1800290a7  pop     r14
0x1800290a9  pop     rdi
0x1800290aa  pop     rsi
0x1800290ab  pop     rbp
0x1800290ac  pop     rbx
0x1800290ad  retn
```
