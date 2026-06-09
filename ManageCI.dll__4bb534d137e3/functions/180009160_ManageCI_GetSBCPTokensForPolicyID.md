# ManageCI_GetSBCPTokensForPolicyID

- ea: `0x180009160`
- end: `0x1800092ce`
- name: `ManageCI_GetSBCPTokensForPolicyID`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002a90`
- `0x180004a98`
- `0x180004acc`
- `0x180004b04`
- `0x180004b8c`
- `0x180004bdc`
- `0x180004e34`
- `0x18000828c`
- `0x180008474`
- `0x180008564`
- `0x180009160`
- `0x180012f50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009252`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ManageCI_GetSBCPTokensForPolicyID(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  unsigned __int64 i; // rbx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  void *v11; // rax
  HLOCAL v12; // rcx
  HLOCAL v13; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v16; // [rsp+28h] [rbp-50h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h]
  __int64 v18; // [rsp+38h] [rbp-40h]
  __int64 v19; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v20[16]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-20h]

  CodeIntegrity::Management::GetSBCPTokensForPolicyID(&v16);
  v7 = v17;
  if ( a2 )
  {
    wil::make_unique_hlocal<unsigned short * [0]>(&v19);
    for ( i = 0; ; ++i )
    {
      v7 = v17;
      v9 = v16;
      if ( i >= (v17 - (__int64)v16) >> 5 )
        break;
      v10 = std::vector<std::wstring>::at(&v16, i);
      std::wstring::wstring((__int64)v20, v10);
      wil::make_unique_hlocal<unsigned short [0]>(&hMem);
      v11 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      std::_Copy_memmove<_GUID *,_GUID *>(v11, (__int64)v11 + 2 * v21, hMem);
      *((_WORD *)hMem + v21) = 0;
      v12 = hMem;
      hMem = 0;
      *(_QWORD *)(v19 + 8 * i) = v12;
      v13 = hMem;
      hMem = 0;
      if ( v13 )
        LocalFree(v13);
      std::wstring::_Tidy_deallocate((__int64)v20);
    }
    *a2 = v19;
  }
  else
  {
    v9 = v16;
  }
  *a3 = (v7 - (__int64)v9) >> 5;
  if ( v9 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v9, v7, v5, v6);
    std::_Deallocate<16>(v16, (v18 - (_QWORD)v16) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x180009160  mov     [rsp+arg_0], rbx
0x180009165  mov     [rsp+arg_18], rsi
0x18000916a  push    rdi
0x18000916b  sub     rsp, 70h
0x18000916f  mov     rax, cs:__security_cookie
0x180009176  xor     rax, rsp
0x180009179  mov     [rsp+78h+var_10], rax
0x18000917e  mov     rsi, r8
0x180009181  mov     rdi, rdx
0x180009184  mov     rdx, rcx
0x180009187  lea     rcx, [rsp+78h+var_50]
0x18000918c  call    ?GetSBCPTokensForPolicyID@Management@CodeIntegrity@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBU_GUID@@@Z; CodeIntegrity::Management::GetSBCPTokensForPolicyID(_GUID const *)
0x180009191  nop
0x180009192  mov     rdx, [rsp+78h+var_48]
0x180009197  test    rdi, rdi
0x18000919a  jz      loc_180009275
0x1800091a0  sub     rdx, [rsp+78h+var_50]
0x1800091a5  sar     rdx, 5
0x1800091a9  lea     rcx, [rsp+78h+var_38]
0x1800091ae  call    ??$make_unique_hlocal@$$BY0A@PEAG@wil@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort * [0]>(unsigned __int64)
0x1800091b3  nop
0x1800091b4  xor     ebx, ebx
0x1800091b6  mov     rdx, [rsp+78h+var_48]
0x1800091bb  mov     rax, rdx
0x1800091be  mov     rcx, [rsp+78h+var_50]
0x1800091c3  sub     rax, rcx
0x1800091c6  sar     rax, 5
0x1800091ca  cmp     rbx, rax
0x1800091cd  jnb     loc_18000926B
0x1800091d3  mov     rdx, rbx
0x1800091d6  lea     rcx, [rsp+78h+var_50]
0x1800091db  call    ?at@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::vector<std::wstring>::at(unsigned __int64)
0x1800091e0  mov     rdx, rax
0x1800091e3  lea     rcx, [rsp+78h+var_30]
0x1800091e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800091ed  nop
0x1800091ee  mov     rdx, [rsp+78h+var_20]
0x1800091f3  inc     rdx
0x1800091f6  lea     rcx, [rsp+78h+hMem]
0x1800091fb  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x180009200  lea     rcx, [rsp+78h+var_30]
0x180009205  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000920a  mov     rcx, [rsp+78h+var_20]
0x18000920f  lea     rdx, [rax+rcx*2]
0x180009213  mov     r8, [rsp+78h+hMem]
0x180009218  mov     rcx, rax; Src
0x18000921b  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180009220  xor     edx, edx
0x180009222  mov     rcx, [rsp+78h+hMem]
0x180009227  mov     rax, [rsp+78h+var_20]
0x18000922c  mov     [rcx+rax*2], dx
0x180009230  mov     rcx, [rsp+78h+hMem]
0x180009235  mov     [rsp+78h+hMem], rdx
0x18000923a  mov     rax, [rsp+78h+var_38]
0x18000923f  mov     [rax+rbx*8], rcx
0x180009243  mov     rcx, [rsp+78h+hMem]; hMem
0x180009248  mov     [rsp+78h+hMem], rdx
0x18000924d  test    rcx, rcx
0x180009250  jz      short loc_180009259
0x180009252  call    cs:__imp_LocalFree
0x180009258  nop
0x180009259  lea     rcx, [rsp+78h+var_30]
0x18000925e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009263  inc     rbx
0x180009266  jmp     loc_1800091B6
0x18000926b  mov     rax, [rsp+78h+var_38]
0x180009270  mov     [rdi], rax
0x180009273  jmp     short loc_18000927A
0x180009275  mov     rcx, [rsp+78h+var_50]
0x18000927a  mov     rax, rdx
0x18000927d  sub     rax, rcx
0x180009280  sar     rax, 5
0x180009284  mov     [rsi], eax
0x180009286  test    rcx, rcx
0x180009289  jz      short loc_1800092A6
0x18000928b  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180009290  mov     rcx, [rsp+78h+var_50]
0x180009295  mov     rdx, [rsp+78h+var_40]
0x18000929a  sub     rdx, rcx
0x18000929d  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800092a1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800092a6  xor     eax, eax
0x1800092a8  jmp     short loc_1800092AE
0x1800092aa  mov     eax, dword ptr [rsp+78h+hMem]
0x1800092ae  mov     rcx, [rsp+78h+var_10]
0x1800092b3  xor     rcx, rsp; StackCookie
0x1800092b6  call    __security_check_cookie
0x1800092bb  lea     r11, [rsp+78h+var_8]
0x1800092c0  mov     rbx, [r11+10h]
0x1800092c4  mov     rsi, [r11+28h]
0x1800092c8  mov     rsp, r11
0x1800092cb  pop     rdi
0x1800092cc  retn
```
