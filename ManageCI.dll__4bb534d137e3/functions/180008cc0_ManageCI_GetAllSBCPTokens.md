# ManageCI_GetAllSBCPTokens

- ea: `0x180008cc0`
- end: `0x180008e2b`
- name: `ManageCI_GetAllSBCPTokens`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

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
- `0x180008cc0`
- `0x180012c30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008daf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008daf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall ManageCI_GetAllSBCPTokens(_QWORD *a1, _DWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  unsigned __int64 i; // rbx
  _QWORD *v8; // rcx
  __int64 v9; // rax
  void *v10; // rax
  HLOCAL v11; // rcx
  HLOCAL v12; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v15; // [rsp+28h] [rbp-50h] BYREF
  __int64 v16; // [rsp+30h] [rbp-48h]
  __int64 v17; // [rsp+38h] [rbp-40h]
  __int64 v18; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v19[16]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v20; // [rsp+58h] [rbp-20h]

  CodeIntegrity::Management::GetAllSBCPTokens(&v15);
  v6 = v16;
  if ( a1 )
  {
    wil::make_unique_hlocal<unsigned short * [0]>(&v18);
    for ( i = 0; ; ++i )
    {
      v6 = v16;
      v8 = v15;
      if ( i >= (v16 - (__int64)v15) >> 5 )
        break;
      v9 = std::vector<std::wstring>::at(&v15, i);
      std::wstring::wstring((__int64)v19, v9);
      wil::make_unique_hlocal<unsigned short [0]>(&hMem);
      v10 = (void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      std::_Copy_memmove<_GUID *,_GUID *>(v10, (__int64)v10 + 2 * v20, hMem);
      *((_WORD *)hMem + v20) = 0;
      v11 = hMem;
      hMem = 0;
      *(_QWORD *)(v18 + 8 * i) = v11;
      v12 = hMem;
      hMem = 0;
      if ( v12 )
        LocalFree(v12);
      std::wstring::_Tidy_deallocate((__int64)v19);
    }
    *a1 = v18;
  }
  else
  {
    v8 = v15;
  }
  *a2 = (v6 - (__int64)v8) >> 5;
  if ( v8 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v8, v6, v4, v5);
    std::_Deallocate<16>(v15, (v17 - (_QWORD)v15) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x180008cc0  mov     [rsp+arg_10], rbx
0x180008cc5  mov     [rsp+arg_18], rsi
0x180008cca  push    rdi
0x180008ccb  sub     rsp, 70h
0x180008ccf  mov     rax, cs:__security_cookie
0x180008cd6  xor     rax, rsp
0x180008cd9  mov     [rsp+78h+var_10], rax
0x180008cde  mov     rsi, rdx
0x180008ce1  mov     rdi, rcx
0x180008ce4  lea     rcx, [rsp+78h+var_50]
0x180008ce9  call    ?GetAllSBCPTokens@Management@CodeIntegrity@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; CodeIntegrity::Management::GetAllSBCPTokens(void)
0x180008cee  nop
0x180008cef  mov     rdx, [rsp+78h+var_48]
0x180008cf4  test    rdi, rdi
0x180008cf7  jz      loc_180008DD2
0x180008cfd  sub     rdx, [rsp+78h+var_50]
0x180008d02  sar     rdx, 5
0x180008d06  lea     rcx, [rsp+78h+var_38]
0x180008d0b  call    ??$make_unique_hlocal@$$BY0A@PEAG@wil@@YA?AV?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort * [0]>(unsigned __int64)
0x180008d10  nop
0x180008d11  xor     ebx, ebx
0x180008d13  mov     rdx, [rsp+78h+var_48]
0x180008d18  mov     rax, rdx
0x180008d1b  mov     rcx, [rsp+78h+var_50]
0x180008d20  sub     rax, rcx
0x180008d23  sar     rax, 5
0x180008d27  cmp     rbx, rax
0x180008d2a  jnb     loc_180008DC8
0x180008d30  mov     rdx, rbx
0x180008d33  lea     rcx, [rsp+78h+var_50]
0x180008d38  call    ?at@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::vector<std::wstring>::at(unsigned __int64)
0x180008d3d  mov     rdx, rax
0x180008d40  lea     rcx, [rsp+78h+var_30]
0x180008d45  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180008d4a  nop
0x180008d4b  mov     rdx, [rsp+78h+var_20]
0x180008d50  inc     rdx
0x180008d53  lea     rcx, [rsp+78h+hMem]
0x180008d58  call    ??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal<ushort [0]>(unsigned __int64)
0x180008d5d  lea     rcx, [rsp+78h+var_30]
0x180008d62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180008d67  mov     rcx, [rsp+78h+var_20]
0x180008d6c  lea     rdx, [rax+rcx*2]
0x180008d70  mov     r8, [rsp+78h+hMem]
0x180008d75  mov     rcx, rax; Src
0x180008d78  call    ??$_Copy_memmove@PEAU_GUID@@PEAU1@@std@@YAPEAU_GUID@@PEAU1@00@Z; std::_Copy_memmove<_GUID *,_GUID *>(_GUID *,_GUID *,_GUID *)
0x180008d7d  xor     edx, edx
0x180008d7f  mov     rcx, [rsp+78h+hMem]
0x180008d84  mov     rax, [rsp+78h+var_20]
0x180008d89  mov     [rcx+rax*2], dx
0x180008d8d  mov     rcx, [rsp+78h+hMem]
0x180008d92  mov     [rsp+78h+hMem], rdx
0x180008d97  mov     rax, [rsp+78h+var_38]
0x180008d9c  mov     [rax+rbx*8], rcx
0x180008da0  mov     rcx, [rsp+78h+hMem]; hMem
0x180008da5  mov     [rsp+78h+hMem], rdx
0x180008daa  test    rcx, rcx
0x180008dad  jz      short loc_180008DB6
0x180008daf  call    cs:__imp_LocalFree
0x180008db5  nop
0x180008db6  lea     rcx, [rsp+78h+var_30]
0x180008dbb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008dc0  inc     rbx
0x180008dc3  jmp     loc_180008D13
0x180008dc8  mov     rax, [rsp+78h+var_38]
0x180008dcd  mov     [rdi], rax
0x180008dd0  jmp     short loc_180008DD7
0x180008dd2  mov     rcx, [rsp+78h+var_50]
0x180008dd7  mov     rax, rdx
0x180008dda  sub     rax, rcx
0x180008ddd  sar     rax, 5
0x180008de1  mov     [rsi], eax
0x180008de3  test    rcx, rcx
0x180008de6  jz      short loc_180008E03
0x180008de8  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180008ded  mov     rcx, [rsp+78h+var_50]
0x180008df2  mov     rdx, [rsp+78h+var_40]
0x180008df7  sub     rdx, rcx
0x180008dfa  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180008dfe  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008e03  xor     eax, eax
0x180008e05  jmp     short loc_180008E0B
0x180008e07  mov     eax, dword ptr [rsp+78h+hMem]
0x180008e0b  mov     rcx, [rsp+78h+var_10]
0x180008e10  xor     rcx, rsp; StackCookie
0x180008e13  call    __security_check_cookie
0x180008e18  lea     r11, [rsp+78h+var_8]
0x180008e1d  mov     rbx, [r11+20h]
0x180008e21  mov     rsi, [r11+28h]
0x180008e25  mov     rsp, r11
0x180008e28  pop     rdi
0x180008e29  retn
```
