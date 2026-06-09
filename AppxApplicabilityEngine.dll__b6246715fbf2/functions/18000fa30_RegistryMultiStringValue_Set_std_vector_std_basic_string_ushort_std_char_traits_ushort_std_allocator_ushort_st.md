# RegistryMultiStringValue::Set(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18000fa30`
- end: `0x18000faaa`
- name: `?Set@RegistryMultiStringValue@@UEAAXAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180004080`
- `0x18000fa30`
- `0x18000fab0`
- `0x1800227c0`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryMultiStringValue::Set(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rdx
  _BYTE v5[40]; // [rsp+38h] [rbp-40h] BYREF

  DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>>(v5, *a2, a2[1]);
  v3 = (_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) >= 8u )
    v3 = (_QWORD *)*v3;
  (*(void (__fastcall **)(_QWORD, _QWORD *, __int64, _BYTE *))(**(_QWORD **)(a1 + 8) + 24LL))(
    *(_QWORD *)(a1 + 8),
    v3,
    7,
    v5);
  return std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v5);
}

```

## disassembly

```asm
0x18000fa30  push    rbx
0x18000fa32  sub     rsp, 70h
0x18000fa36  mov     [rsp+78h+var_48], 0FFFFFFFFFFFFFFFEh
0x18000fa3f  mov     rax, cs:__security_cookie
0x18000fa46  xor     rax, rsp
0x18000fa49  mov     [rsp+78h+var_18], rax
0x18000fa4e  mov     rbx, rcx
0x18000fa51  mov     r8, [rdx+8]
0x18000fa55  mov     rdx, [rdx]
0x18000fa58  lea     rcx, [rsp+78h+var_40]
0x18000fa5d  call    ??$DelimitedStringFromItems@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Vector_const_iterator@V?$_Vector_val@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@1@0G@Z; DelimitedStringFromItems<std::_Vector_const_iterator<std::_Vector_val<std::wstring>>>(std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,std::_Vector_const_iterator<std::_Vector_val<std::wstring>>,ushort)
0x18000fa62  nop
0x18000fa63  mov     rcx, [rbx+8]
0x18000fa67  mov     rax, [rcx]
0x18000fa6a  lea     rdx, [rbx+10h]
0x18000fa6e  cmp     qword ptr [rdx+18h], 8
0x18000fa73  jb      short loc_18000FA78
0x18000fa75  mov     rdx, [rdx]
0x18000fa78  lea     r9, [rsp+78h+var_40]
0x18000fa7d  mov     r8d, 7
0x18000fa83  mov     rax, [rax+18h]
0x18000fa87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa8c  nop
0x18000fa8d  lea     rcx, [rsp+78h+var_40]
0x18000fa92  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x18000fa97  mov     rcx, [rsp+78h+var_18]
0x18000fa9c  xor     rcx, rsp; StackCookie
0x18000fa9f  call    __security_check_cookie
0x18000faa4  add     rsp, 70h
0x18000faa8  pop     rbx
0x18000faa9  retn
```
