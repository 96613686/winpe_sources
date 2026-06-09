# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Compile(void)

- ea: `0x180037f34`
- end: `0x180037fc4`
- name: `?_Compile@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Root_node@2@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18001cf6c`

## callees

- `0x180035924`
- `0x18003754c`
- `0x1800377a0`
- `0x180038190`
- `0x180038ff0`
- `0x180039a90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Compile(
        __int64 a1)
{
  __int64 *v2; // rdi
  __int64 v3; // rbx
  __int64 v4; // rbx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = (__int64 *)(a1 + 56);
  v6 = a1 + 56;
  v3 = std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_capture_group(
         a1 + 56,
         0);
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1);
  std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v2, v3);
  std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(v2, 21);
  v4 = *v2;
  *(_DWORD *)(v4 + 32) = *(_DWORD *)(a1 + 104);
  *(_DWORD *)(v4 + 40) = *(_DWORD *)(a1 + 16) + 1;
  std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Calculate_loop_simplicity(
    a1,
    v4,
    0,
    0);
  v6 = 0;
  std::_Tidy_guard<std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>>::~_Tidy_guard<std::_Builder2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>>(&v6);
  return v4;
}

```

## disassembly

```asm
0x180037f34  mov     [rsp+arg_8], rbx
0x180037f39  mov     [rsp+arg_10], rsi
0x180037f3e  push    rdi
0x180037f3f  sub     rsp, 20h
0x180037f43  mov     rsi, rcx
0x180037f46  lea     rdi, [rcx+38h]
0x180037f4a  mov     [rsp+28h+arg_0], rdi
0x180037f4f  xor     edx, edx
0x180037f51  mov     rcx, rdi
0x180037f54  call    ?_Begin_capture_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@I@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_capture_group(uint)
0x180037f59  mov     rbx, rax
0x180037f5c  mov     rcx, rsi
0x180037f5f  call    ?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x180037f64  mov     rdx, rbx
0x180037f67  mov     rcx, rdi
0x180037f6a  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x180037f6f  mov     edx, 15h
0x180037f74  mov     rcx, rdi
0x180037f77  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x180037f7c  mov     rbx, [rdi]
0x180037f7f  mov     ecx, [rsi+68h]
0x180037f82  mov     [rbx+20h], ecx
0x180037f85  mov     ecx, [rsi+10h]
0x180037f88  inc     ecx
0x180037f8a  mov     [rbx+28h], ecx
0x180037f8d  xor     r9d, r9d
0x180037f90  xor     r8d, r8d
0x180037f93  mov     rdx, rbx
0x180037f96  mov     rcx, rsi
0x180037f99  call    ?_Calculate_loop_simplicity@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEAV_Node_base@2@0PEAV_Node_rep@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Calculate_loop_simplicity(std::_Node_base *,std::_Node_base *,std::_Node_rep *)
0x180037f9e  mov     [rsp+28h+arg_0], 0
0x180037fa7  lea     rcx, [rsp+28h+arg_0]
0x180037fac  call    ??1?$_Tidy_guard@V?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>>::~_Tidy_guard<std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>>(void)
0x180037fb1  mov     rax, rbx
0x180037fb4  mov     rbx, [rsp+28h+arg_8]
0x180037fb9  mov     rsi, [rsp+28h+arg_10]
0x180037fbe  add     rsp, 20h
0x180037fc2  pop     rdi
0x180037fc3  retn
```
