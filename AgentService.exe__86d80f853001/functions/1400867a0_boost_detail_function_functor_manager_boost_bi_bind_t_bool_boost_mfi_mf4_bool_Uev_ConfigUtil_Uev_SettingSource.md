# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64 const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x1400867a0`
- end: `0x14008687a`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_KAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x1400867a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086845`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x140086845`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CD618) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x1400867a0  mov     [rsp+arg_0], rbx
0x1400867a5  mov     [rsp+arg_8], rsi
0x1400867aa  push    rdi
0x1400867ab  sub     rsp, 20h
0x1400867af  mov     rsi, rdx
0x1400867b2  mov     rbx, rcx
0x1400867b5  xor     edi, edi
0x1400867b7  cmp     r8d, 4
0x1400867bb  jz      loc_14008685C
0x1400867c1  test    r8d, r8d
0x1400867c4  jnz     short loc_1400867F7
0x1400867c6  mov     rbx, [rcx]
0x1400867c9  lea     ecx, [rdi+30h]; Size
0x1400867cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400867d1  mov     rdi, rax
0x1400867d4  mov     [rsp+28h+arg_18], rax
0x1400867d9  mov     rcx, [rbx]
0x1400867dc  mov     [rax], rcx
0x1400867df  mov     rcx, [rbx+8]
0x1400867e3  mov     [rax+8], rcx
0x1400867e7  lea     rdx, [rbx+10h]
0x1400867eb  lea     rcx, [rax+10h]
0x1400867ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400867f4  nop
0x1400867f5  jmp     short loc_14008682C
0x1400867f7  cmp     r8d, 1
0x1400867fb  jnz     short loc_140086808
0x1400867fd  mov     rax, [rcx]
0x140086800  mov     [rdx], rax
0x140086803  mov     [rcx], rdi
0x140086806  jmp     short loc_14008686A
0x140086808  cmp     r8d, 2
0x14008680c  jnz     short loc_140086831
0x14008680e  mov     rbx, [rdx]
0x140086811  test    rbx, rbx
0x140086814  jz      short loc_14008682C
0x140086816  lea     rcx, [rbx+10h]
0x14008681a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008681f  mov     edx, 30h ; '0'
0x140086824  mov     rcx, rbx; Block
0x140086827  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14008682c  mov     [rsi], rdi
0x14008682f  jmp     short loc_14008686A
0x140086831  cmp     r8d, 3
0x140086835  jnz     short loc_14008685C
0x140086837  mov     rcx, [rdx]
0x14008683a  add     rcx, 8
0x14008683e  lea     rdx, qword_1400CD618
0x140086845  call    cs:__imp___std_type_info_compare
0x14008684b  test    eax, eax
0x14008684d  jnz     short loc_140086854
0x14008684f  mov     rax, [rbx]
0x140086852  jmp     short loc_140086857
0x140086854  mov     rax, rdi
0x140086857  mov     [rsi], rax
0x14008685a  jmp     short loc_14008686A
0x14008685c  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEB_KAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,unsigned __int64 const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x140086863  mov     [rdx], rax
0x140086866  mov     [rdx+8], di
0x14008686a  mov     rbx, [rsp+28h+arg_0]
0x14008686f  mov     rsi, [rsp+28h+arg_8]
0x140086874  add     rsp, 20h
0x140086878  pop     rdi
0x140086879  retn
```
