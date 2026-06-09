# std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Compile(void)

- ea: `0x18001e2dc`
- end: `0x18001e36c`
- name: `?_Compile@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Root_node@2@XZ`
- size: `144`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18001bc48`

## callees

- `0x18001bfcc`
- `0x18001d8d0`
- `0x18001db58`
- `0x18001e3f4`
- `0x18001f14c`
- `0x18001ffd8`

## pseudocode

```c
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
0x18001e2dc  mov     [rsp+arg_8], rbx
0x18001e2e1  mov     [rsp+arg_10], rsi
0x18001e2e6  push    rdi
0x18001e2e7  sub     rsp, 20h
0x18001e2eb  mov     rsi, rcx
0x18001e2ee  lea     rdi, [rcx+38h]
0x18001e2f2  mov     [rsp+28h+arg_0], rdi
0x18001e2f7  xor     edx, edx
0x18001e2f9  mov     rcx, rdi
0x18001e2fc  call    ?_Begin_capture_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@I@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_capture_group(uint)
0x18001e301  mov     rbx, rax
0x18001e304  mov     rcx, rsi
0x18001e307  call    ?_Disjunction@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x18001e30c  mov     rdx, rbx
0x18001e30f  mov     rcx, rdi
0x18001e312  call    ?_End_group@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18001e317  mov     edx, 15h
0x18001e31c  mov     rcx, rdi
0x18001e31f  call    ?_New_node@?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x18001e324  mov     rbx, [rdi]
0x18001e327  mov     ecx, [rsi+68h]
0x18001e32a  mov     [rbx+20h], ecx
0x18001e32d  mov     ecx, [rsi+10h]
0x18001e330  inc     ecx
0x18001e332  mov     [rbx+28h], ecx
0x18001e335  xor     r9d, r9d
0x18001e338  xor     r8d, r8d
0x18001e33b  mov     rdx, rbx
0x18001e33e  mov     rcx, rsi
0x18001e341  call    ?_Calculate_loop_simplicity@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@AEAAXPEAV_Node_base@2@0PEAV_Node_rep@2@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Calculate_loop_simplicity(std::_Node_base *,std::_Node_base *,std::_Node_rep *)
0x18001e346  mov     [rsp+28h+arg_0], 0
0x18001e34f  lea     rcx, [rsp+28h+arg_0]
0x18001e354  call    ??1?$_Tidy_guard@V?$_Builder2@PEBGGV?$regex_traits@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>>::~_Tidy_guard<std::_Builder2<ushort const *,ushort,std::regex_traits<ushort>>>(void)
0x18001e359  mov     rax, rbx
0x18001e35c  mov     rbx, [rsp+28h+arg_8]
0x18001e361  mov     rsi, [rsp+28h+arg_10]
0x18001e366  add     rsp, 20h
0x18001e36a  pop     rdi
0x18001e36b  retn
```
