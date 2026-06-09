# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140086640`
- end: `0x14008671a`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x140086640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400866e5`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400866e5`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::list<std::wstring> const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CF0E8) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140086640  mov     [rsp+arg_0], rbx
0x140086645  mov     [rsp+arg_8], rsi
0x14008664a  push    rdi
0x14008664b  sub     rsp, 20h
0x14008664f  mov     rsi, rdx
0x140086652  mov     rbx, rcx
0x140086655  xor     edi, edi
0x140086657  cmp     r8d, 4
0x14008665b  jz      loc_1400866FC
0x140086661  test    r8d, r8d
0x140086664  jnz     short loc_140086697
0x140086666  mov     rbx, [rcx]
0x140086669  lea     ecx, [rdi+30h]; Size
0x14008666c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086671  mov     rdi, rax
0x140086674  mov     [rsp+28h+arg_18], rax
0x140086679  mov     rcx, [rbx]
0x14008667c  mov     [rax], rcx
0x14008667f  mov     rcx, [rbx+8]
0x140086683  mov     [rax+8], rcx
0x140086687  lea     rdx, [rbx+10h]
0x14008668b  lea     rcx, [rax+10h]
0x14008668f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140086694  nop
0x140086695  jmp     short loc_1400866CC
0x140086697  cmp     r8d, 1
0x14008669b  jnz     short loc_1400866A8
0x14008669d  mov     rax, [rcx]
0x1400866a0  mov     [rdx], rax
0x1400866a3  mov     [rcx], rdi
0x1400866a6  jmp     short loc_14008670A
0x1400866a8  cmp     r8d, 2
0x1400866ac  jnz     short loc_1400866D1
0x1400866ae  mov     rbx, [rdx]
0x1400866b1  test    rbx, rbx
0x1400866b4  jz      short loc_1400866CC
0x1400866b6  lea     rcx, [rbx+10h]
0x1400866ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400866bf  mov     edx, 30h ; '0'
0x1400866c4  mov     rcx, rbx; Block
0x1400866c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400866cc  mov     [rsi], rdi
0x1400866cf  jmp     short loc_14008670A
0x1400866d1  cmp     r8d, 3
0x1400866d5  jnz     short loc_1400866FC
0x1400866d7  mov     rcx, [rdx]
0x1400866da  add     rcx, 8
0x1400866de  lea     rdx, qword_1400CF0E8
0x1400866e5  call    cs:__imp___std_type_info_compare
0x1400866eb  test    eax, eax
0x1400866ed  jnz     short loc_1400866F4
0x1400866ef  mov     rax, [rbx]
0x1400866f2  jmp     short loc_1400866F7
0x1400866f4  mov     rax, rdi
0x1400866f7  mov     [rsi], rax
0x1400866fa  jmp     short loc_14008670A
0x1400866fc  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,std::list<std::wstring> const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140086703  mov     [rdx], rax
0x140086706  mov     [rdx+8], di
0x14008670a  mov     rbx, [rsp+28h+arg_0]
0x14008670f  mov     rsi, [rsp+28h+arg_8]
0x140086714  add     rsp, 20h
0x140086718  pop     rdi
0x140086719  retn
```
