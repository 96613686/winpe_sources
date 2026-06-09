# NetSetupRpcClient::CreateObject(_NETSETUP_OBJECT_TYPE,ulong,_NETSETUPPROPERTY const *,_GUID *)

- ea: `0x18000d010`
- end: `0x18000d03e`
- name: `?CreateObject@NetSetupRpcClient@@UEAAXW4_NETSETUP_OBJECT_TYPE@@KPEBU_NETSETUPPROPERTY@@PEAU_GUID@@@Z`
- size: `46`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005ce4`

## pseudocode

```c
__int64 __fastcall NetSetupRpcClient::CreateObject(__int64 a1, int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  int v7; // [rsp+28h] [rbp-20h]
  int v8; // [rsp+2Ch] [rbp-1Ch]
  __int64 v9; // [rsp+30h] [rbp-18h]
  __int64 v10; // [rsp+38h] [rbp-10h]

  v6 = a1;
  v7 = a2;
  v8 = a3;
  v9 = a4;
  v10 = a5;
  return NetSetupExecuteInRpc__lambda_dc7a49ce44bba89c8ddbcb0617d67e2f_(&v6);
}

```

## disassembly

```asm
0x18000d010  mov     r11, rsp
0x18000d013  sub     rsp, 48h
0x18000d017  mov     rax, [rsp+48h+arg_20]
0x18000d01c  mov     [r11-28h], rcx
0x18000d020  lea     rcx, [r11-28h]
0x18000d024  mov     [rsp+48h+var_20], edx
0x18000d028  mov     [r11-1Ch], r8d
0x18000d02c  mov     [r11-18h], r9
0x18000d030  mov     [r11-10h], rax
0x18000d034  call    NetSetupExecuteInRpc__lambda_dc7a49ce44bba89c8ddbcb0617d67e2f___; NetSetupExecuteInRpc__lambda_dc7a49ce44bba89c8ddbcb0617d67e2f_
0x18000d039  add     rsp, 48h
0x18000d03d  retn
```
