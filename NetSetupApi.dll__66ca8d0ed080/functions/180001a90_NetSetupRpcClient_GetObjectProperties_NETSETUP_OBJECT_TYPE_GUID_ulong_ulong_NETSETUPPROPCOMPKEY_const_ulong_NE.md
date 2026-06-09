# NetSetupRpcClient::GetObjectProperties(_NETSETUP_OBJECT_TYPE,_GUID,ulong,ulong,_NETSETUPPROPCOMPKEY const *,ulong *,_NETSETUPPROPERTY const * *)

- ea: `0x180001a90`
- end: `0x180001af4`
- name: `?GetObjectProperties@NetSetupRpcClient@@UEAAXW4_NETSETUP_OBJECT_TYPE@@U_GUID@@KKPEBU_NETSETUPPROPCOMPKEY@@PEAKPEAPEBU_NETSETUPPROPERTY@@@Z`
- size: `100`
- prototype: `__int64 __fastcall(__int64, int, __int128 *, int, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001afc`

## pseudocode

```c
__int64 __fastcall NetSetupRpcClient::GetObjectProperties(
        __int64 a1,
        int a2,
        __int128 *a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int128 v8; // xmm0
  __int64 v10; // [rsp+20h] [rbp-48h] BYREF
  int v11; // [rsp+28h] [rbp-40h]
  __int128 v12; // [rsp+2Ch] [rbp-3Ch]
  int v13; // [rsp+3Ch] [rbp-2Ch]
  int v14; // [rsp+40h] [rbp-28h]
  __int64 v15; // [rsp+48h] [rbp-20h]
  __int64 v16; // [rsp+50h] [rbp-18h]
  __int64 v17; // [rsp+58h] [rbp-10h]

  v8 = *a3;
  v14 = a5;
  v15 = a6;
  v16 = a7;
  v10 = a1;
  v17 = a8;
  v11 = a2;
  v12 = v8;
  v13 = a4;
  return NetSetupExecuteInRpc__lambda_364dec93115ff357338516143ccbe19e_(&v10);
}

```

## disassembly

```asm
0x180001a90  sub     rsp, 68h
0x180001a94  mov     eax, [rsp+68h+arg_20]
0x180001a9b  movups  xmm0, xmmword ptr [r8]
0x180001a9f  mov     [rsp+68h+var_28], eax
0x180001aa3  mov     eax, [rsp+68h+var_24]
0x180001aa7  mov     [rsp+68h+var_24], eax
0x180001aab  mov     rax, [rsp+68h+arg_28]
0x180001ab3  mov     [rsp+68h+var_20], rax
0x180001ab8  mov     rax, [rsp+68h+arg_30]
0x180001ac0  mov     [rsp+68h+var_18], rax
0x180001ac5  mov     rax, [rsp+68h+arg_38]
0x180001acd  mov     [rsp+68h+var_48], rcx
0x180001ad2  lea     rcx, [rsp+68h+var_48]
0x180001ad7  mov     [rsp+68h+var_10], rax
0x180001adc  mov     [rsp+68h+var_40], edx
0x180001ae0  movups  [rsp+68h+var_3C], xmm0
0x180001ae5  mov     [rsp+68h+var_2C], r9d
0x180001aea  call    NetSetupExecuteInRpc__lambda_364dec93115ff357338516143ccbe19e___; NetSetupExecuteInRpc__lambda_364dec93115ff357338516143ccbe19e_
0x180001aef  add     rsp, 68h
0x180001af3  retn
```
