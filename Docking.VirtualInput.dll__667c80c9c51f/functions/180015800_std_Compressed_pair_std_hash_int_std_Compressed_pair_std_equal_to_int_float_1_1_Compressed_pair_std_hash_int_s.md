# std::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>(std::_Zero_then_variadic_args_t,std::_Zero_then_variadic_args_t &&,float &&)

- ea: `0x180015800`
- end: `0x180015860`
- name: `??$?0U_Zero_then_variadic_args_t@std@@M@?$_Compressed_pair@U?$hash@H@std@@V?$_Compressed_pair@U?$equal_to@H@std@@M$00@2@$00@std@@QEAA@U_Zero_then_variadic_args_t@1@$$QEAU21@$$QEAM@Z`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016740`

## callees

- `0x18000b810`
- `0x180015710`

## pseudocode

```c
__int64 __fastcall std::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>::_Compressed_pair<std::hash<int>,std::_Compressed_pair<std::equal_to<int>,float,1>,1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int8 v5; // [rsp+20h] [rbp-28h]
  __int64 v6; // [rsp+28h] [rbp-20h]

  v6 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a4);
  v5 = *(_BYTE *)Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  std::_Compressed_pair<std::equal_to<int>,float,1>::_Compressed_pair<std::equal_to<int>,float,1>(a1, v5, v6);
  return a1;
}

```

## disassembly

```asm
0x180015800  mov     [rsp+arg_18], r9
0x180015805  mov     [rsp+arg_10], r8
0x18001580a  mov     [rsp+arg_8], dl
0x18001580e  mov     [rsp+arg_0], rcx
0x180015813  sub     rsp, 48h
0x180015817  mov     rax, [rsp+48h+arg_0]
0x18001581c  mov     [rsp+48h+var_18], rax
0x180015821  mov     rcx, [rsp+48h+arg_18]
0x180015826  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001582b  mov     [rsp+48h+var_20], rax
0x180015830  mov     rcx, [rsp+48h+arg_10]
0x180015835  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001583a  movzx   eax, byte ptr [rax]
0x18001583d  mov     [rsp+48h+var_28], al
0x180015841  mov     r8, [rsp+48h+var_20]
0x180015846  movzx   edx, [rsp+48h+var_28]
0x18001584b  mov     rcx, [rsp+48h+var_18]
0x180015850  call    ??$?0M@?$_Compressed_pair@U?$equal_to@H@std@@M$00@std@@QEAA@U_Zero_then_variadic_args_t@1@$$QEAM@Z; std::_Compressed_pair<std::equal_to<int>,float,1>::_Compressed_pair<std::equal_to<int>,float,1>(std::_Zero_then_variadic_args_t,float &&)
0x180015855  nop
0x180015856  mov     rax, [rsp+48h+arg_0]
0x18001585b  add     rsp, 48h
0x18001585f  retn
```
