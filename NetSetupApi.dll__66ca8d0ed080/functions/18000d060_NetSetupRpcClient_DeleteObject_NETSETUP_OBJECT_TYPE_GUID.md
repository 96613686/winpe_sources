# NetSetupRpcClient::DeleteObject(_NETSETUP_OBJECT_TYPE,_GUID)

- ea: `0x18000d060`
- end: `0x18000d08c`
- name: `?DeleteObject@NetSetupRpcClient@@UEAAXW4_NETSETUP_OBJECT_TYPE@@U_GUID@@@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64, int, __int128 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005e60`

## pseudocode

```c
__int64 __fastcall NetSetupRpcClient::DeleteObject(__int64 a1, int a2, __int128 *a3)
{
  __int128 v3; // xmm0
  __int64 v5; // [rsp+20h] [rbp-28h] BYREF
  int v6; // [rsp+28h] [rbp-20h]
  __int128 v7; // [rsp+2Ch] [rbp-1Ch]

  v3 = *a3;
  v5 = a1;
  v6 = a2;
  v7 = v3;
  return NetSetupExecuteInRpc__lambda_6db56a2b674587f0867f9b199bde32bb_(&v5);
}

```

## disassembly

```asm
0x18000d060  mov     rax, rsp
0x18000d063  sub     rsp, 48h
0x18000d067  movups  xmm0, xmmword ptr [r8]
0x18000d06b  mov     [rax-28h], rcx
0x18000d06f  lea     rcx, [rsp+48h+var_28]
0x18000d074  mov     [rax-20h], edx
0x18000d077  movups  xmmword ptr [rax-1Ch], xmm0
0x18000d07b  mov     eax, [rax-0Ch]
0x18000d07e  mov     [rsp+48h+var_C], eax
0x18000d082  call    NetSetupExecuteInRpc__lambda_6db56a2b674587f0867f9b199bde32bb___; NetSetupExecuteInRpc__lambda_6db56a2b674587f0867f9b199bde32bb_
0x18000d087  add     rsp, 48h
0x18000d08b  retn
```
