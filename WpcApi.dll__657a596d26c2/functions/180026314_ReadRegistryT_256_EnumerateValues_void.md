# ReadRegistryT<256>::EnumerateValues(void)

- ea: `0x180026314`
- end: `0x1800263e5`
- name: `?EnumerateValues@?$ReadRegistryT@$0BAA@@@UEBA?AV?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@XZ`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026300`

## callees

- `0x1800032c4`
- `0x180024550`
- `0x180024640`
- `0x180026314`
- `0x18002c010`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18002637c`

## pseudocode

```c
__int64 __fastcall ReadRegistryT<256>::EnumerateValues(__int64 a1, __int64 a2)
{
  volatile signed __int32 *v4; // rbx
  char *v6; // [rsp+28h] [rbp-20h] BYREF
  volatile signed __int32 *v7; // [rsp+30h] [rbp-18h]
  _DWORD *v8; // [rsp+58h] [rbp+10h]

  v8 = operator new(0x28u);
  *(_OWORD *)v8 = 0;
  v8[2] = 1;
  v8[3] = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable';
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  *((_QWORD *)v8 + 4) = 0;
  v6 = (char *)(v8 + 4);
  v7 = v8;
  anonymous_namespace_::Enum_long____cdecl___HKEY_____unsigned_long_unsigned_short___unsigned_long___unsigned_long___unsigned_long___unsigned_char___unsigned_long____std::shared_ptr_std::vector_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________(
    RegEnumValueW,
    *(_QWORD *)(a1 - 32),
    &v6);
  Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(a2, &v6);
  v4 = v7;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180026314  mov     [rsp+arg_0], rbx
0x180026319  push    rdi
0x18002631a  sub     rsp, 40h
0x18002631e  mov     rdi, rdx
0x180026321  mov     rbx, rcx
0x180026324  mov     ecx, 28h ; '('; Size
0x180026329  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002632e  mov     [rsp+48h+arg_8], rax
0x180026333  xorps   xmm0, xmm0
0x180026336  movups  xmmword ptr [rax], xmm0
0x180026339  mov     ecx, 1
0x18002633e  mov     [rax+8], ecx
0x180026341  mov     [rax+0Ch], ecx
0x180026344  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable'
0x18002634b  mov     [rax], rcx
0x18002634e  lea     rcx, [rax+10h]
0x180026352  mov     qword ptr [rcx], 0
0x180026359  mov     qword ptr [rcx+8], 0
0x180026361  mov     qword ptr [rcx+10h], 0
0x180026369  mov     [rsp+48h+var_20], rcx
0x18002636e  mov     [rsp+48h+var_18], rax
0x180026373  lea     r8, [rsp+48h+var_20]
0x180026378  mov     rdx, [rbx-20h]
0x18002637c  mov     rcx, cs:__imp_RegEnumValueW
0x180026383  call    _anonymous_namespace___Enum_long____cdecl___HKEY_____unsigned_long_unsigned_short___unsigned_long___unsigned_long___unsigned_long___unsigned_char___unsigned_long____std__shared_ptr_std__vector_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________
0x180026388  lea     rdx, [rsp+48h+var_20]
0x18002638d  mov     rcx, rdi
0x180026390  call    ??$?0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEAA@AEBV?$shared_ptr@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@Z; Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(std::shared_ptr<std::vector<std::wstring>> const &)
0x180026395  nop
0x180026396  mov     rbx, [rsp+48h+var_18]
0x18002639b  test    rbx, rbx
0x18002639e  jz      short loc_1800263D7
0x1800263a0  or      eax, 0FFFFFFFFh
0x1800263a3  lock xadd [rbx+8], eax
0x1800263a8  cmp     eax, 1
0x1800263ab  jnz     short loc_1800263D7
0x1800263ad  mov     rax, [rbx]
0x1800263b0  mov     rcx, rbx
0x1800263b3  mov     rax, [rax]
0x1800263b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263bb  or      eax, 0FFFFFFFFh
0x1800263be  lock xadd [rbx+0Ch], eax
0x1800263c3  cmp     eax, 1
0x1800263c6  jnz     short loc_1800263D7
0x1800263c8  mov     rax, [rbx]
0x1800263cb  mov     rcx, rbx
0x1800263ce  mov     rax, [rax+8]
0x1800263d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263d7  mov     rax, rdi
0x1800263da  mov     rbx, [rsp+48h+arg_0]
0x1800263df  add     rsp, 40h
0x1800263e3  pop     rdi
0x1800263e4  retn
```
