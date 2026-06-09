# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x1400861a0`
- end: `0x14008627a`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140003e74`
- `0x140003f88`
- `0x14000adb4`
- `0x14000ba60`
- `0x1400861a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086245`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086245`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>>>::manage(
        char **a1,
        char **a2,
        int a3)
{
  char *v5; // rdi
  char *v6; // rbx
  char *v7; // rbx
  char *v8; // rax

  v5 = 0;
  switch ( a3 )
  {
    case 4:
      goto LABEL_15;
    case 0:
      v6 = *a1;
      v5 = (char *)operator new(0x30u);
      *(_QWORD *)v5 = *(_QWORD *)v6;
      *((_QWORD *)v5 + 1) = *((_QWORD *)v6 + 1);
      std::wstring::wstring((__int64)(v5 + 16), (__int64)(v6 + 16));
LABEL_9:
      *a2 = v5;
      return;
    case 1:
      *a2 = *a1;
      *a1 = 0;
      return;
    case 2:
      v7 = *a2;
      if ( *a2 )
      {
        std::wstring::_Tidy_deallocate(v7 + 16);
        operator delete(v7);
      }
      goto LABEL_9;
  }
  if ( a3 != 3 )
  {
LABEL_15:
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CDA18) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x1400861a0  mov     [rsp+arg_0], rbx
0x1400861a5  mov     [rsp+arg_8], rsi
0x1400861aa  push    rdi
0x1400861ab  sub     rsp, 20h
0x1400861af  mov     rsi, rdx
0x1400861b2  mov     rbx, rcx
0x1400861b5  xor     edi, edi
0x1400861b7  cmp     r8d, 4
0x1400861bb  jz      loc_14008625C
0x1400861c1  test    r8d, r8d
0x1400861c4  jnz     short loc_1400861F7
0x1400861c6  mov     rbx, [rcx]
0x1400861c9  lea     ecx, [rdi+30h]; Size
0x1400861cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400861d1  mov     rdi, rax
0x1400861d4  mov     [rsp+28h+arg_18], rax
0x1400861d9  mov     rcx, [rbx]
0x1400861dc  mov     [rax], rcx
0x1400861df  mov     rcx, [rbx+8]
0x1400861e3  mov     [rax+8], rcx
0x1400861e7  lea     rdx, [rbx+10h]
0x1400861eb  lea     rcx, [rax+10h]
0x1400861ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400861f4  nop
0x1400861f5  jmp     short loc_14008622C
0x1400861f7  cmp     r8d, 1
0x1400861fb  jnz     short loc_140086208
0x1400861fd  mov     rax, [rcx]
0x140086200  mov     [rdx], rax
0x140086203  mov     [rcx], rdi
0x140086206  jmp     short loc_14008626A
0x140086208  cmp     r8d, 2
0x14008620c  jnz     short loc_140086231
0x14008620e  mov     rbx, [rdx]
0x140086211  test    rbx, rbx
0x140086214  jz      short loc_14008622C
0x140086216  lea     rcx, [rbx+10h]
0x14008621a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008621f  mov     edx, 30h ; '0'
0x140086224  mov     rcx, rbx; Block
0x140086227  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14008622c  mov     [rsi], rdi
0x14008622f  jmp     short loc_14008626A
0x140086231  cmp     r8d, 3
0x140086235  jnz     short loc_14008625C
0x140086237  mov     rcx, [rdx]
0x14008623a  add     rcx, 8
0x14008623e  lea     rdx, qword_1400CDA18
0x140086245  call    cs:__imp___std_type_info_compare
0x14008624b  test    eax, eax
0x14008624d  jnz     short loc_140086254
0x14008624f  mov     rax, [rbx]
0x140086252  jmp     short loc_140086257
0x140086254  mov     rax, rdi
0x140086257  mov     [rsi], rax
0x14008625a  jmp     short loc_14008626A
0x14008625c  lea     rax, ??_R0?AV?$bind_t@_NV?$mf3@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAJ@_mfi@boost@@V?$list4@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf3<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,long &>,boost::_bi::list4<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>>> `RTTI Type Descriptor'
0x140086263  mov     [rdx], rax
0x140086266  mov     [rdx+8], di
0x14008626a  mov     rbx, [rsp+28h+arg_0]
0x14008626f  mov     rsi, [rsp+28h+arg_8]
0x140086274  add     rsp, 20h
0x140086278  pop     rdi
0x140086279  retn
```
