# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf5<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,long &,bool>,boost::_bi::list6<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>,boost::_bi::value<bool>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140085fb0`
- end: `0x140086093`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf5@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@AEAJ_N@_mfi@boost@@V?$list6@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@V?$value@_N@23@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003e74`
- `0x140003f88`
- `0x14000adb4`
- `0x14000ba60`
- `0x140085fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14008605e`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x14008605e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf5<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool>,boost::_bi::list6<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>,boost::_bi::value<bool>>>>::manage(
        char **a1,
        char **a2,
        int a3)
{
  char *v5; // rdi
  char *v6; // rbx
  char *v7; // rax
  _QWORD *v8; // [rsp+48h] [rbp+20h]

  switch ( a3 )
  {
    case 4:
      goto LABEL_15;
    case 0:
      v5 = *a1;
      v8 = operator new(0x38u);
      *v8 = *(_QWORD *)v5;
      v8[1] = *((_QWORD *)v5 + 1);
      std::wstring::wstring((__int64)(v8 + 2), (__int64)(v5 + 16));
      *((_BYTE *)v8 + 48) = v5[48];
      *a2 = (char *)v8;
      return;
    case 1:
      *a2 = *a1;
      *a1 = 0;
      return;
    case 2:
      v6 = *a2;
      if ( *a2 )
      {
        std::wstring::_Tidy_deallocate(v6 + 16);
        operator delete(v6);
      }
      *a2 = 0;
      return;
  }
  if ( a3 != 3 )
  {
LABEL_15:
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::cmf5<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool>,boost::_bi::list6<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>,boost::_bi::value<bool>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
    return;
  }
  if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CC6C8) )
    v7 = 0;
  else
    v7 = *a1;
  *a2 = v7;
}

```

## disassembly

```asm
0x140085fb0  mov     [rsp+arg_0], rbx
0x140085fb5  mov     [rsp+arg_8], rsi
0x140085fba  push    rdi
0x140085fbb  sub     rsp, 20h
0x140085fbf  mov     rsi, rdx
0x140085fc2  mov     rbx, rcx
0x140085fc5  xor     edi, edi
0x140085fc7  cmp     r8d, 4
0x140085fcb  jz      loc_140086075
0x140085fd1  test    r8d, r8d
0x140085fd4  jnz     short loc_140086010
0x140085fd6  mov     rdi, [rcx]
0x140085fd9  lea     ecx, [r8+38h]; Size
0x140085fdd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140085fe2  mov     rbx, rax
0x140085fe5  mov     [rsp+28h+arg_18], rax
0x140085fea  mov     rcx, [rdi]
0x140085fed  mov     [rax], rcx
0x140085ff0  mov     rcx, [rdi+8]
0x140085ff4  mov     [rax+8], rcx
0x140085ff8  lea     rdx, [rdi+10h]
0x140085ffc  lea     rcx, [rax+10h]
0x140086000  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140086005  mov     cl, [rdi+30h]
0x140086008  mov     [rbx+30h], cl
0x14008600b  mov     [rsi], rbx
0x14008600e  jmp     short loc_140086083
0x140086010  cmp     r8d, 1
0x140086014  jnz     short loc_140086021
0x140086016  mov     rax, [rcx]
0x140086019  mov     [rdx], rax
0x14008601c  mov     [rcx], rdi
0x14008601f  jmp     short loc_140086083
0x140086021  cmp     r8d, 2
0x140086025  jnz     short loc_14008604A
0x140086027  mov     rbx, [rdx]
0x14008602a  test    rbx, rbx
0x14008602d  jz      short loc_140086045
0x14008602f  lea     rcx, [rbx+10h]
0x140086033  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140086038  mov     edx, 38h ; '8'
0x14008603d  mov     rcx, rbx; Block
0x140086040  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140086045  mov     [rsi], rdi
0x140086048  jmp     short loc_140086083
0x14008604a  cmp     r8d, 3
0x14008604e  jnz     short loc_140086075
0x140086050  mov     rcx, [rdx]
0x140086053  add     rcx, 8
0x140086057  lea     rdx, qword_1400CC6C8
0x14008605e  call    cs:__imp___std_type_info_compare
0x140086064  test    eax, eax
0x140086066  jnz     short loc_14008606D
0x140086068  mov     rax, [rbx]
0x14008606b  jmp     short loc_140086070
0x14008606d  mov     rax, rdi
0x140086070  mov     [rsi], rax
0x140086073  jmp     short loc_140086083
0x140086075  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf5@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV45@AEAJ_N@_mfi@boost@@V?$list6@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@V?$value@_N@23@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf5<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,std::wstring &,long &,bool>,boost::_bi::list6<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>,boost::_bi::value<bool>>> `RTTI Type Descriptor'
0x14008607c  mov     [rdx], rax
0x14008607f  mov     [rdx+8], di
0x140086083  mov     rbx, [rsp+28h+arg_0]
0x140086088  mov     rsi, [rsp+28h+arg_8]
0x14008608d  add     rsp, 20h
0x140086091  pop     rdi
0x140086092  retn
```
