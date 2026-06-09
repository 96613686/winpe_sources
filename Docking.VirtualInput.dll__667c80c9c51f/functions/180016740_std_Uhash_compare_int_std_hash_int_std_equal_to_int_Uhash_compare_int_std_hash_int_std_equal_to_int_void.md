# std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>(void)

- ea: `0x180016740`
- end: `0x180016780`
- name: `??0?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEAA@XZ`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016864`

## callees

- `0x180015800`

## pseudocode

```c
__int64 __fastcall std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>(
        __int64 a1)
{
  _BYTE v2[4]; // [rsp+20h] [rbp-18h] BYREF
  int v3; // [rsp+24h] [rbp-14h] BYREF
  __int64 v4; // [rsp+28h] [rbp-10h]

  v4 = a1;
  v3 = 0;
  std::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>(
    a1,
    v2[1],
    (__int64)v2,
    (__int64)&v3);
  return a1;
}

```

## disassembly

```asm
0x180016740  mov     [rsp+arg_0], rcx
0x180016745  sub     rsp, 38h
0x180016749  mov     rax, [rsp+38h+arg_0]
0x18001674e  mov     [rsp+38h+var_10], rax
0x180016753  xorps   xmm0, xmm0
0x180016756  movss   [rsp+38h+var_14], xmm0
0x18001675c  lea     r9, [rsp+38h+var_14]
0x180016761  lea     r8, [rsp+38h+var_18]
0x180016766  movzx   edx, [rsp+38h+var_17]
0x18001676b  mov     rcx, [rsp+38h+var_10]
0x180016770  call    ??$?0U_Zero_then_variadic_args_t@std@@M@?$_Compressed_pair@U?$hash@H@std@@V?$_Compressed_pair@U?$equal_to@H@std@@M$00@2@$00@std@@QEAA@U_Zero_then_variadic_args_t@1@$$QEAU21@$$QEAM@Z; std::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>(std::_Zero_then_variadic_args_t,std::_Zero_then_variadic_args_t &&,float &&)
0x180016775  nop
0x180016776  mov     rax, [rsp+38h+arg_0]
0x18001677b  add     rsp, 38h
0x18001677f  retn
```
