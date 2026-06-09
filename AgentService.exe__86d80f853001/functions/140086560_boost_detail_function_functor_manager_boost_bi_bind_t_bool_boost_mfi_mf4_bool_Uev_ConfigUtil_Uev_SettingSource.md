# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140086560`
- end: `0x14008663a`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x140086560`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086605`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086605`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,std::wstring const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CD8A8) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140086560  mov     [rsp+arg_0], rbx
0x140086565  mov     [rsp+arg_8], rsi
0x14008656a  push    rdi
0x14008656b  sub     rsp, 20h
0x14008656f  mov     rsi, rdx
0x140086572  mov     rbx, rcx
0x140086575  xor     edi, edi
0x140086577  cmp     r8d, 4
0x14008657b  jz      loc_14008661C
0x140086581  test    r8d, r8d
0x140086584  jnz     short loc_1400865B7
0x140086586  mov     rbx, [rcx]
0x140086589  lea     ecx, [rdi+30h]; Size
0x14008658c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086591  mov     rdi, rax
0x140086594  mov     [rsp+28h+arg_18], rax
0x140086599  mov     rcx, [rbx]
0x14008659c  mov     [rax], rcx
0x14008659f  mov     rcx, [rbx+8]
0x1400865a3  mov     [rax+8], rcx
0x1400865a7  lea     rdx, [rbx+10h]
0x1400865ab  lea     rcx, [rax+10h]
0x1400865af  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400865b4  nop
0x1400865b5  jmp     short loc_1400865EC
0x1400865b7  cmp     r8d, 1
0x1400865bb  jnz     short loc_1400865C8
0x1400865bd  mov     rax, [rcx]
0x1400865c0  mov     [rdx], rax
0x1400865c3  mov     [rcx], rdi
0x1400865c6  jmp     short loc_14008662A
0x1400865c8  cmp     r8d, 2
0x1400865cc  jnz     short loc_1400865F1
0x1400865ce  mov     rbx, [rdx]
0x1400865d1  test    rbx, rbx
0x1400865d4  jz      short loc_1400865EC
0x1400865d6  lea     rcx, [rbx+10h]
0x1400865da  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400865df  mov     edx, 30h ; '0'
0x1400865e4  mov     rcx, rbx; Block
0x1400865e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400865ec  mov     [rsi], rdi
0x1400865ef  jmp     short loc_14008662A
0x1400865f1  cmp     r8d, 3
0x1400865f5  jnz     short loc_14008661C
0x1400865f7  mov     rcx, [rdx]
0x1400865fa  add     rcx, 8
0x1400865fe  lea     rdx, qword_1400CD8A8
0x140086605  call    cs:__imp___std_type_info_compare
0x14008660b  test    eax, eax
0x14008660d  jnz     short loc_140086614
0x14008660f  mov     rax, [rbx]
0x140086612  jmp     short loc_140086617
0x140086614  mov     rax, rdi
0x140086617  mov     [rsi], rax
0x14008661a  jmp     short loc_14008662A
0x14008661c  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@AEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,std::wstring const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140086623  mov     [rdx], rax
0x140086626  mov     [rdx+8], di
0x14008662a  mov     rbx, [rsp+28h+arg_0]
0x14008662f  mov     rsi, [rsp+28h+arg_8]
0x140086634  add     rsp, 20h
0x140086638  pop     rdi
0x140086639  retn
```
