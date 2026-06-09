# boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,bool>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::_bi::value<bool>>>>::manage(boost::detail::function::function_buffer const &,boost::detail::function::function_buffer &,boost::detail::function::functor_manager_operation_type)

- ea: `0x1400858c0`
- end: `0x14008593b`
- name: `?manage@?$functor_manager@V?$bind_t@_NV?$cmf1@_NVConfigUtil@Uev@@_N@_mfi@boost@@V?$list2@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@V?$value@_N@23@@_bi@3@@_bi@boost@@@function@detail@boost@@SAXAEBTfunction_buffer@234@AEAT5234@W4functor_manager_operation_type@234@@Z`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400858c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400858f6`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400858f6`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager<boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,bool>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::_bi::value<bool>>>>::manage(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
  {
LABEL_6:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,bool>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::_bi::value<bool>>> `RTTI Type Descriptor';
    return;
  }
  if ( a3 > 1 )
  {
    if ( a3 == 2 )
      return;
    if ( a3 == 3 )
    {
      *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CEC28) == 0);
      return;
    }
    goto LABEL_6;
  }
  *(_OWORD *)a2 = *(_OWORD *)a1;
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 16);
}

```

## disassembly

```asm
0x1400858c0  mov     [rsp+arg_0], rbx
0x1400858c5  push    rdi
0x1400858c6  sub     rsp, 20h
0x1400858ca  mov     rbx, rdx
0x1400858cd  mov     rdi, rcx
0x1400858d0  cmp     r8d, 4
0x1400858d4  jz      short loc_14008590E
0x1400858d6  cmp     r8d, 1
0x1400858da  jbe     short loc_140085920
0x1400858dc  cmp     r8d, 2
0x1400858e0  jz      short loc_140085930
0x1400858e2  cmp     r8d, 3
0x1400858e6  jnz     short loc_14008590E
0x1400858e8  mov     rcx, [rdx]
0x1400858eb  lea     rdx, qword_1400CEC28
0x1400858f2  add     rcx, 8
0x1400858f6  call    cs:__imp___std_type_info_compare
0x1400858fc  test    eax, eax
0x1400858fe  setz    al
0x140085901  neg     al
0x140085903  sbb     rcx, rcx
0x140085906  and     rcx, rdi
0x140085909  mov     [rbx], rcx
0x14008590c  jmp     short loc_140085930
0x14008590e  lea     rax, ??_R0?AV?$bind_t@_NV?$cmf1@_NVConfigUtil@Uev@@_N@_mfi@boost@@V?$list2@V?$value@PEAVConfigUtil@Uev@@@_bi@boost@@V?$value@_N@23@@_bi@3@@_bi@boost@@@8; boost::_bi::bind_t<bool,boost::_mfi::cmf1<bool,Uev::ConfigUtil,bool>,boost::_bi::list2<boost::_bi::value<Uev::ConfigUtil *>,boost::_bi::value<bool>>> `RTTI Type Descriptor'
0x140085915  mov     word ptr [rdx+8], 0
0x14008591b  mov     [rdx], rax
0x14008591e  jmp     short loc_140085930
0x140085920  movups  xmm0, xmmword ptr [rcx]
0x140085923  movups  xmmword ptr [rdx], xmm0
0x140085926  movsd   xmm1, qword ptr [rcx+10h]
0x14008592b  movsd   qword ptr [rdx+10h], xmm1
0x140085930  mov     rbx, [rsp+28h+arg_0]
0x140085935  add     rsp, 20h
0x140085939  pop     rdi
0x14008593a  retn
```
