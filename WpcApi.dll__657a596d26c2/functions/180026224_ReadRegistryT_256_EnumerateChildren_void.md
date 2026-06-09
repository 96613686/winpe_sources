# ReadRegistryT<256>::EnumerateChildren(void)

- ea: `0x180026224`
- end: `0x1800262f5`
- name: `?EnumerateChildren@?$ReadRegistryT@$0BAA@@@UEBA?AV?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@XZ`
- size: `209`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180026210`

## callees

- `0x1800032c4`
- `0x180024550`
- `0x180024640`
- `0x180026224`
- `0x18002c010`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18002628c`

## pseudocode

```c
__int64 __fastcall ReadRegistryT<256>::EnumerateChildren(__int64 a1, __int64 a2)
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
    RegEnumKeyExW,
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
0x180026224  mov     [rsp+arg_0], rbx
0x180026229  push    rdi
0x18002622a  sub     rsp, 40h
0x18002622e  mov     rdi, rdx
0x180026231  mov     rbx, rcx
0x180026234  mov     ecx, 28h ; '('; Size
0x180026239  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002623e  mov     [rsp+48h+arg_8], rax
0x180026243  xorps   xmm0, xmm0
0x180026246  movups  xmmword ptr [rax], xmm0
0x180026249  mov     ecx, 1
0x18002624e  mov     [rax+8], ecx
0x180026251  mov     [rax+0Ch], ecx
0x180026254  lea     rcx, ??_7?$_Ref_count_obj2@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable'
0x18002625b  mov     [rax], rcx
0x18002625e  lea     rcx, [rax+10h]
0x180026262  mov     qword ptr [rcx], 0
0x180026269  mov     qword ptr [rcx+8], 0
0x180026271  mov     qword ptr [rcx+10h], 0
0x180026279  mov     [rsp+48h+var_20], rcx
0x18002627e  mov     [rsp+48h+var_18], rax
0x180026283  lea     r8, [rsp+48h+var_20]
0x180026288  mov     rdx, [rbx-20h]
0x18002628c  mov     rcx, cs:__imp_RegEnumKeyExW
0x180026293  call    _anonymous_namespace___Enum_long____cdecl___HKEY_____unsigned_long_unsigned_short___unsigned_long___unsigned_long___unsigned_long___unsigned_char___unsigned_long____std__shared_ptr_std__vector_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__allocator_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________
0x180026298  lea     rdx, [rsp+48h+var_20]
0x18002629d  mov     rcx, rdi
0x1800262a0  call    ??$?0V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@?$Enumerable@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Collections@@QEAA@AEBV?$shared_ptr@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@Z; Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(std::shared_ptr<std::vector<std::wstring>> const &)
0x1800262a5  nop
0x1800262a6  mov     rbx, [rsp+48h+var_18]
0x1800262ab  test    rbx, rbx
0x1800262ae  jz      short loc_1800262E7
0x1800262b0  or      eax, 0FFFFFFFFh
0x1800262b3  lock xadd [rbx+8], eax
0x1800262b8  cmp     eax, 1
0x1800262bb  jnz     short loc_1800262E7
0x1800262bd  mov     rax, [rbx]
0x1800262c0  mov     rcx, rbx
0x1800262c3  mov     rax, [rax]
0x1800262c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262cb  or      eax, 0FFFFFFFFh
0x1800262ce  lock xadd [rbx+0Ch], eax
0x1800262d3  cmp     eax, 1
0x1800262d6  jnz     short loc_1800262E7
0x1800262d8  mov     rax, [rbx]
0x1800262db  mov     rcx, rbx
0x1800262de  mov     rax, [rax+8]
0x1800262e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262e7  mov     rax, rdi
0x1800262ea  mov     rbx, [rsp+48h+arg_0]
0x1800262ef  add     rsp, 40h
0x1800262f3  pop     rdi
0x1800262f4  retn
```
