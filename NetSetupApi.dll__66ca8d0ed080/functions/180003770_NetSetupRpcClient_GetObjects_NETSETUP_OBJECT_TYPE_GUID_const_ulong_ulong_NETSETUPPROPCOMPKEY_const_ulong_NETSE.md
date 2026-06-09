# NetSetupRpcClient::GetObjects(_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,ulong,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong *,_NETSETUP_OBJECT const * *)

- ea: `0x180003770`
- end: `0x180003810`
- name: `?GetObjects@NetSetupRpcClient@@UEAAXW4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KKPEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@PEAKPEAPEBU_NETSETUP_OBJECT@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int, unsigned int, __int64, int, unsigned __int64, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003818`

## pseudocode

```c
__int64 __fastcall NetSetupRpcClient::GetObjects(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        unsigned __int64 a8,
        unsigned __int64 a9,
        __int64 a10)
{
  __int128 v11; // [rsp+20h] [rbp-A8h]
  __int128 v12; // [rsp+30h] [rbp-98h]
  __int128 v13; // [rsp+40h] [rbp-88h]
  _OWORD v14[4]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v15; // [rsp+B0h] [rbp-18h]

  *(_QWORD *)&v13 = a6;
  DWORD2(v13) = a7;
  *(_QWORD *)&v11 = a1;
  DWORD2(v11) = a2;
  *(_QWORD *)&v12 = a3;
  *((_QWORD *)&v12 + 1) = __PAIR64__(a5, a4);
  v14[0] = v11;
  v14[1] = v12;
  v14[2] = v13;
  v15 = a10;
  v14[3] = __PAIR128__(a9, a8);
  return NetSetupExecuteInRpc__lambda_dfbc2be12003ea79a65dc535afd6433c_(v14);
}

```

## disassembly

```asm
0x180003770  mov     r11, rsp
0x180003773  sub     rsp, 0C8h
0x18000377a  mov     eax, [rsp+0C8h+arg_20]
0x180003781  mov     dword ptr [rsp+0C8h+var_98+0Ch], eax
0x180003785  mov     rax, [rsp+0C8h+arg_28]
0x18000378d  mov     qword ptr [rsp+0C8h+var_88], rax
0x180003792  mov     eax, [rsp+0C8h+arg_30]
0x180003799  mov     dword ptr [rsp+0C8h+var_88+8], eax
0x18000379d  mov     rax, [rsp+0C8h+arg_38]
0x1800037a5  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x1800037aa  lea     rcx, [r11-58h]
0x1800037ae  mov     dword ptr [rsp+0C8h+var_A8+8], edx
0x1800037b2  mov     qword ptr [rsp+0C8h+var_98], r8
0x1800037b7  mov     dword ptr [rsp+0C8h+var_98+8], r9d
0x1800037bc  mov     [r11-78h], rax
0x1800037c0  mov     rax, [rsp+0C8h+arg_40]
0x1800037c8  mov     [r11-70h], rax
0x1800037cc  movups  xmm0, [rsp+0C8h+var_A8]
0x1800037d1  movups  xmm1, [rsp+0C8h+var_98]
0x1800037d6  movaps  [rsp+0C8h+var_58], xmm0
0x1800037db  movups  xmm0, [rsp+0C8h+var_88]
0x1800037e0  movaps  xmmword ptr [r11-48h], xmm1
0x1800037e5  movups  xmm1, [rsp+0C8h+var_78]
0x1800037ea  movaps  xmmword ptr [r11-38h], xmm0
0x1800037ef  movsd   xmm0, [rsp+0C8h+arg_48]
0x1800037f8  movsd   qword ptr [r11-18h], xmm0
0x1800037fe  movaps  xmmword ptr [r11-28h], xmm1
0x180003803  call    NetSetupExecuteInRpc__lambda_dfbc2be12003ea79a65dc535afd6433c___; NetSetupExecuteInRpc__lambda_dfbc2be12003ea79a65dc535afd6433c_
0x180003808  add     rsp, 0C8h
0x18000380f  retn
```
