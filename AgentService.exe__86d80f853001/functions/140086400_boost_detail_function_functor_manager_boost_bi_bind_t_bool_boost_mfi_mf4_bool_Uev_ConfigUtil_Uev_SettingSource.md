# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,boost::arg<2>,boost::arg<3>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x140086400`
- end: `0x1400864da`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
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
- `0x140086400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400864a5`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400864a5`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>>>::manage(
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
    *a2 = (char *)&boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,enum Uev::SettingSource,std::wstring const &,unsigned long const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor';
    *((_WORD *)a2 + 4) = 0;
  }
  else
  {
    if ( (unsigned int)__std_type_info_compare(*a2 + 8, &qword_1400CDB68) )
      v8 = 0;
    else
      v8 = *a1;
    *a2 = v8;
  }
}

```

## disassembly

```asm
0x140086400  mov     [rsp+arg_0], rbx
0x140086405  mov     [rsp+arg_8], rsi
0x14008640a  push    rdi
0x14008640b  sub     rsp, 20h
0x14008640f  mov     rsi, rdx
0x140086412  mov     rbx, rcx
0x140086415  xor     edi, edi
0x140086417  cmp     r8d, 4
0x14008641b  jz      loc_1400864BC
0x140086421  test    r8d, r8d
0x140086424  jnz     short loc_140086457
0x140086426  mov     rbx, [rcx]
0x140086429  lea     ecx, [rdi+30h]; Size
0x14008642c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086431  mov     rdi, rax
0x140086434  mov     [rsp+28h+arg_18], rax
0x140086439  mov     rcx, [rbx]
0x14008643c  mov     [rax], rcx
0x14008643f  mov     rcx, [rbx+8]
0x140086443  mov     [rax+8], rcx
0x140086447  lea     rdx, [rbx+10h]
0x14008644b  lea     rcx, [rax+10h]
0x14008644f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140086454  nop
0x140086455  jmp     short loc_14008648C
0x140086457  cmp     r8d, 1
0x14008645b  jnz     short loc_140086468
0x14008645d  mov     rax, [rcx]
0x140086460  mov     [rdx], rax
0x140086463  mov     [rcx], rdi
0x140086466  jmp     short loc_1400864CA
0x140086468  cmp     r8d, 2
0x14008646c  jnz     short loc_140086491
0x14008646e  mov     rbx, [rdx]
0x140086471  test    rbx, rbx
0x140086474  jz      short loc_14008648C
0x140086476  lea     rcx, [rbx+10h]
0x14008647a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008647f  mov     edx, 30h ; '0'
0x140086484  mov     rcx, rbx; Block
0x140086487  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14008648c  mov     [rsi], rdi
0x14008648f  jmp     short loc_1400864CA
0x140086491  cmp     r8d, 3
0x140086495  jnz     short loc_1400864BC
0x140086497  mov     rcx, [rdx]
0x14008649a  add     rcx, 8
0x14008649e  lea     rdx, qword_1400CDB68
0x1400864a5  call    cs:__imp___std_type_info_compare
0x1400864ab  test    eax, eax
0x1400864ad  jnz     short loc_1400864B4
0x1400864af  mov     rax, [rbx]
0x1400864b2  jmp     short loc_1400864B7
0x1400864b4  mov     rax, rdi
0x1400864b7  mov     [rsi], rax
0x1400864ba  jmp     short loc_1400864CA
0x1400864bc  lea     rax, ??_R0?AV?$bind_t@_NV?$mf4@_NVConfigUtil@Uev@@W4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBKAEAJ@_mfi@boost@@V?$list5@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@U?$arg@$00@3@V?$value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@23@U?$arg@$01@3@U?$arg@$02@3@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::mf4<bool,Uev::ConfigUtil,Uev::SettingSource,std::wstring const &,ulong const &,long &>,boost::_bi::list5<boost::_bi::value<Uev::ConfigUtil *>,boost::arg<1>,boost::_bi::value<std::wstring>,boost::arg<2>,boost::arg<3>>> `RTTI Type Descriptor'
0x1400864c3  mov     [rdx], rax
0x1400864c6  mov     [rdx+8], di
0x1400864ca  mov     rbx, [rsp+28h+arg_0]
0x1400864cf  mov     rsi, [rsp+28h+arg_8]
0x1400864d4  add     rsp, 20h
0x1400864d8  pop     rdi
0x1400864d9  retn
```
