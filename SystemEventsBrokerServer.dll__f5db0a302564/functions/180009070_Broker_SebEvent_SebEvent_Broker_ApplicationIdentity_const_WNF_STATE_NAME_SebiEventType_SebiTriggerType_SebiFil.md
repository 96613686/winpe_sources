# Broker::SebEvent::SebEvent(Broker::ApplicationIdentity const &,_WNF_STATE_NAME,_SebiEventType,_SebiTriggerType,_SebiFilterType,uchar const *,ulong,int,int,int,Broker::SebBroker *,_BROKER *,_BROKERED_EVENT *)

- ea: `0x180009070`
- end: `0x1800092dc`
- name: `??0SebEvent@Broker@@QEAA@AEBUApplicationIdentity@1@U_WNF_STATE_NAME@@W4_SebiEventType@@W4_SebiTriggerType@@W4_SebiFilterType@@PEBEKHHHPEAVSebBroker@1@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z`
- size: `620`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, unsigned int, int, int, __int64, unsigned int, int, int, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010cd0`

## callees

- `0x1800076a0`
- `0x1800085c0`
- `0x180009070`
- `0x18000b168`
- `0x180015d30`
- `0x180016844`
- `0x18001a540`
- `0x18001cf74`
- `0x18001f870`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x1800091cb`
- `ntdll!RtlInitializeSRWLock` at `0x1800091cb`

## pseudocode

```c
__int64 __fastcall Broker::SebEvent::SebEvent(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        int a6,
        __int64 a7,
        unsigned int a8,
        int a9,
        int a10,
        int a11,
        __int64 a12,
        __int64 a13,
        __int64 a14)
{
  __int64 v18; // rsi
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  std::_Ref_count_base *v27; // rcx
  _QWORD *v28; // rsi
  _QWORD *v29; // rcx
  __int64 v30; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v31; // [rsp+38h] [rbp-30h]

  *(_QWORD *)a1 = &Broker::SebEvent::`vftable';
  v18 = a1 + 8;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(a1 + 8, a2[1] - *a2, a2);
  v19 = a2 + 3;
  *(_OWORD *)(v18 + 24) = 0;
  *(_QWORD *)(v18 + 40) = 0;
  *(_QWORD *)(v18 + 48) = 0;
  if ( a2[6] > 7u )
    v19 = (_QWORD *)*v19;
  std::wstring::_Construct<2,unsigned short const *>(v18 + 24, v19, a2[5]);
  v20 = a2 + 7;
  *(_OWORD *)(v18 + 56) = 0;
  *(_QWORD *)(v18 + 72) = 0;
  *(_QWORD *)(v18 + 80) = 0;
  if ( a2[10] > 7u )
    v20 = (_QWORD *)*v20;
  std::wstring::_Construct<2,unsigned short const *>(v18 + 56, v20, a2[9]);
  *(_DWORD *)(a1 + 96) = a4;
  *(_DWORD *)(a1 + 100) = a5;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = a9;
  *(_QWORD *)(a1 + 124) = a3;
  *(_DWORD *)(a1 + 132) = 0;
  *(_DWORD *)(a1 + 136) = a10;
  std::vector<_GUID>::vector<_GUID>((_QWORD *)(a1 + 144));
  *(_BYTE *)(a1 + 169) = 0;
  *(_DWORD *)(a1 + 172) = a11;
  *(_QWORD *)(a1 + 176) = 0;
  *(_DWORD *)(a1 + 184) = 8;
  *(_QWORD *)(a1 + 192) = a12;
  *(_QWORD *)(a1 + 216) = a13;
  *(_QWORD *)(a1 + 224) = a14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_Ldd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, a4, v21, v22);
  RtlInitializeSRWLock(a1 + 208);
  *(_BYTE *)(a1 + 168) = 0;
  if ( a6 )
  {
    v28 = operator new(0x20u);
    *(_DWORD *)v28 = a6;
    std::vector<_GUID>::vector<_GUID>(v28 + 1);
    if ( a7 && a8 )
      std::vector<unsigned char>::insert<unsigned char const *,0>((_DWORD)v29, (unsigned int)&a13, *v29, a7, a7 + a8);
    v24 = std::shared_ptr<Broker::SebFilter>::shared_ptr<Broker::SebFilter>(&v30, (__int64)v28);
    v25 = *v24;
    v26 = v24[1];
    *v24 = 0;
    v24[1] = 0;
    *(_QWORD *)(a1 + 104) = v25;
    v27 = *(std::_Ref_count_base **)(a1 + 112);
    *(_QWORD *)(a1 + 112) = v26;
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
  }
  if ( *(_DWORD *)(a1 + 120) )
    ++*(_DWORD *)(a1 + 184);
  return a1;
}

```

## disassembly

```asm
0x180009070  mov     [rsp+arg_10], rbx
0x180009075  mov     [rsp+arg_0], rcx
0x18000907a  push    rbp
0x18000907b  push    rsi
0x18000907c  push    rdi
0x18000907d  push    r14
0x18000907f  push    r15
0x180009081  sub     rsp, 40h
0x180009085  mov     r14d, r9d
0x180009088  mov     rbx, r8
0x18000908b  mov     rbp, rdx
0x18000908e  mov     rdi, rcx
0x180009091  lea     rax, ??_7SebEvent@Broker@@6B@; const Broker::SebEvent::`vftable'
0x180009098  mov     [rcx], rax
0x18000909b  lea     rsi, [rcx+8]
0x18000909f  mov     [rsp+68h+arg_8], rsi
0x1800090a4  xor     r15d, r15d
0x1800090a7  mov     [rsi], r15
0x1800090aa  mov     [rsi+8], r15
0x1800090ae  mov     [rsi+10h], r15
0x1800090b2  lea     r9, [rdx+8]
0x1800090b6  mov     rdx, [r9]
0x1800090b9  sub     rdx, [rbp+0]
0x1800090bd  mov     r8, rbp
0x1800090c0  mov     rcx, rsi
0x1800090c3  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x1800090c8  nop
0x1800090c9  lea     rcx, [rsi+18h]
0x1800090cd  lea     rdx, [rbp+18h]
0x1800090d1  xorps   xmm0, xmm0
0x1800090d4  movups  xmmword ptr [rcx], xmm0
0x1800090d7  mov     [rcx+10h], r15
0x1800090db  mov     [rcx+18h], r15
0x1800090df  mov     r8, [rdx+10h]
0x1800090e3  cmp     qword ptr [rdx+18h], 7
0x1800090e8  jbe     short loc_1800090ED
0x1800090ea  mov     rdx, [rdx]
0x1800090ed  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800090f2  nop
0x1800090f3  lea     rcx, [rsi+38h]
0x1800090f7  lea     rdx, [rbp+38h]
0x1800090fb  xorps   xmm0, xmm0
0x1800090fe  movups  xmmword ptr [rcx], xmm0
0x180009101  mov     [rcx+10h], r15
0x180009105  mov     [rcx+18h], r15
0x180009109  mov     r8, [rdx+10h]
0x18000910d  cmp     qword ptr [rdx+18h], 7
0x180009112  ja      loc_180009208
0x180009118  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18000911d  nop
0x18000911e  mov     [rdi+60h], r14d
0x180009122  mov     edx, [rsp+68h+arg_20]
0x180009129  mov     [rdi+64h], edx
0x18000912c  mov     [rdi+68h], r15
0x180009130  mov     [rdi+70h], r15
0x180009134  mov     eax, [rsp+68h+arg_40]
0x18000913b  mov     [rdi+78h], eax
0x18000913e  mov     [rdi+7Ch], rbx
0x180009142  mov     [rdi+84h], r15d
0x180009149  mov     r8d, [rsp+68h+arg_48]
0x180009151  mov     [rdi+88h], r8d
0x180009158  lea     rcx, [rdi+90h]
0x18000915f  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180009164  nop
0x180009165  mov     byte ptr [rdi+0A9h], 0
0x18000916c  mov     eax, [rsp+68h+arg_50]
0x180009173  mov     [rdi+0ACh], eax
0x180009179  mov     [rdi+0B0h], r15
0x180009180  mov     dword ptr [rdi+0B8h], 8
0x18000918a  mov     rax, [rsp+68h+arg_58]
0x180009192  mov     [rdi+0C0h], rax
0x180009199  mov     rax, [rsp+68h+arg_60]
0x1800091a1  mov     [rdi+0D8h], rax
0x1800091a8  mov     rax, [rsp+68h+arg_68]
0x1800091b0  mov     [rdi+0E0h], rax
0x1800091b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091be  test    byte ptr [rcx+1Ch], 40h
0x1800091c2  jnz     short loc_180009210
0x1800091c4  lea     rcx, [rdi+0D0h]
0x1800091cb  call    cs:__imp_RtlInitializeSRWLock
0x1800091d1  mov     byte ptr [rdi+0A8h], 0
0x1800091d8  mov     ebx, [rsp+68h+arg_28]
0x1800091df  test    ebx, ebx
0x1800091e1  jnz     loc_180009276
0x1800091e7  cmp     dword ptr [rdi+78h], 0
0x1800091eb  jnz     loc_1800092D0
0x1800091f1  mov     rax, rdi
0x1800091f4  mov     rbx, [rsp+68h+arg_10]
0x1800091fc  add     rsp, 40h
0x180009200  pop     r15
0x180009202  pop     r14
0x180009204  pop     rdi
0x180009205  pop     rsi
0x180009206  pop     rbp
0x180009207  retn
0x180009208  mov     rdx, [rdx]
0x18000920b  jmp     loc_180009118
0x180009210  cmp     byte ptr [rcx+19h], 4
0x180009214  jb      short loc_1800091C4
0x180009216  mov     [rsp+68h+var_40], r8d
0x18000921b  mov     dword ptr [rsp+68h+var_48], edx
0x18000921f  mov     r9d, r14d
0x180009222  mov     rcx, [rcx+10h]
0x180009226  call    WPP_SF_Ldd
0x18000922b  jmp     short loc_1800091C4
0x18000922d  mov     rdx, rsi
0x180009230  lea     rcx, [rsp+68h+var_38]
0x180009235  call    ??$?0VSebFilter@Broker@@$0A@@?$shared_ptr@VSebFilter@Broker@@@std@@QEAA@PEAVSebFilter@Broker@@@Z; std::shared_ptr<Broker::SebFilter>::shared_ptr<Broker::SebFilter>(Broker::SebFilter *)
0x18000923a  mov     rcx, [rax]
0x18000923d  mov     rdx, [rax+8]
0x180009241  mov     [rax], r15
0x180009244  mov     [rax+8], r15
0x180009248  mov     [rdi+68h], rcx
0x18000924c  mov     rcx, [rdi+70h]; this
0x180009250  mov     [rdi+70h], rdx
0x180009254  test    rcx, rcx
0x180009257  jz      short loc_18000925E
0x180009259  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000925e  mov     rcx, [rsp+68h+var_30]; this
0x180009263  test    rcx, rcx
0x180009266  jz      loc_1800091E7
0x18000926c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009271  jmp     loc_1800091E7
0x180009276  mov     ecx, 20h ; ' '; Size
0x18000927b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009280  mov     rsi, rax
0x180009283  mov     [rsp+68h+arg_58], rax
0x18000928b  mov     [rax], ebx
0x18000928d  lea     rcx, [rax+8]
0x180009291  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180009296  nop
0x180009297  mov     r9, [rsp+68h+arg_30]
0x18000929f  test    r9, r9
0x1800092a2  jz      short loc_18000922D
0x1800092a4  mov     eax, [rsp+68h+arg_38]
0x1800092ab  test    eax, eax
0x1800092ad  jz      loc_18000922D
0x1800092b3  add     rax, r9
0x1800092b6  mov     [rsp+68h+var_48], rax
0x1800092bb  mov     r8, [rcx]
0x1800092be  lea     rdx, [rsp+68h+arg_60]
0x1800092c6  call    ??$insert@PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEBE1@Z; std::vector<uchar>::insert<uchar const *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar const *,uchar const *)
0x1800092cb  jmp     loc_18000922D
0x1800092d0  inc     dword ptr [rdi+0B8h]
0x1800092d6  jmp     loc_1800091F1
```
