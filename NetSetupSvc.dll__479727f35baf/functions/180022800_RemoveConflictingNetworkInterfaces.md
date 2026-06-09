# RemoveConflictingNetworkInterfaces

- ea: `0x180022800`
- end: `0x180022e27`
- name: `RemoveConflictingNetworkInterfaces`
- size: `1575`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800207bc`

## callees

- `0x1800027c0`
- `0x180006e34`
- `0x180007048`
- `0x180007d80`
- `0x180008380`
- `0x18000d954`
- `0x18000d974`
- `0x18000d9b4`
- `0x180018490`
- `0x18001caa4`
- `0x18001d89c`
- `0x180022800`
- `0x1800243ec`
- `0x18002455c`
- `0x180024b14`
- `0x18002bba8`
- `0x18002c1e4`
- `0x18002c89c`
- `0x18002cab8`
- `0x18002d038`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RemoveConflictingNetworkInterfaces(_QWORD *a1, NetSetup2::ObjectCreationTemplate *a2)
{
  int v4; // edi
  int Release_high; // ebx
  struct Property v6; // rax
  unsigned __int64 Uint64; // rbx
  struct Property v8; // rax
  bool v9; // bl
  struct Property v10; // rax
  struct Property v11; // rax
  __int64 v12; // r8
  int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rcx
  NetSetup2::ActiveObject **v16; // r12
  NetSetup2::ActiveObject **v17; // r14
  unsigned __int128 v18; // kr20_16
  int v19; // eax
  int v20; // r8d
  unsigned __int64 v21; // kr00_8
  NetSetup2::ActiveObject **v22; // rdi
  __int64 v23; // rbx
  int v24; // esi
  int v25; // eax
  int v26; // r8d
  unsigned int v27; // [rsp+40h] [rbp-158h]
  struct Property v28; // [rsp+48h] [rbp-150h] BYREF
  __int128 v29; // [rsp+50h] [rbp-148h]
  __int128 v30; // [rsp+60h] [rbp-138h] BYREF
  __int128 v31; // [rsp+70h] [rbp-128h]
  NetSetup2::ActiveObject **v32; // [rsp+80h] [rbp-118h]
  struct _GUID v33; // [rsp+90h] [rbp-108h] BYREF
  _BYTE v34[32]; // [rsp+B0h] [rbp-E8h] BYREF
  _QWORD *v35; // [rsp+D0h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+D8h] [rbp-C0h]
  __int64 v37; // [rsp+E0h] [rbp-B8h]
  unsigned __int64 v38; // [rsp+E8h] [rbp-B0h] BYREF
  __int128 v39; // [rsp+F0h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+100h] [rbp-98h]
  struct _GUID v41; // [rsp+110h] [rbp-88h] BYREF
  _BYTE v42[16]; // [rsp+120h] [rbp-78h] BYREF
  int v43; // [rsp+130h] [rbp-68h]
  _BYTE v44[16]; // [rsp+140h] [rbp-58h] BYREF
  int v45; // [rsp+150h] [rbp-48h]

  v4 = 0;
  std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(&v35);
  std::wstring::wstring((__int64)v44);
  std::wstring::wstring((__int64)v42);
  v38 = 0;
  v41 = 0;
  v28.lpVtbl = (struct PropertyVtbl *)3145728;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(&v35, &v28);
  Release_high = HIDWORD(NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl->Release);
  std::vector<unsigned char>::_Tidy((__int64)&v30);
  if ( Release_high )
  {
    v6.lpVtbl = NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl;
    NetSetup2::Property::GetString(v6.lpVtbl, &v33);
    v4 = 16;
    std::vector<unsigned char>::_Tidy((__int64)&v30);
    std::wstring::operator=(v44, &v33);
    std::wstring::_Tidy_deallocate((__int64)&v33);
    v28.lpVtbl = (struct PropertyVtbl *)131074;
    v29 = NETSETUPPKEY_Interface_IfAlias;
    v30 = 0x10u;
    LODWORD(v31) = 18;
    DWORD1(v31) = 2 * v45 + 2;
    *((_QWORD *)&v31 + 1) = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(&v35, &v28);
  }
  Uint64 = HIDWORD(NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl->Release);
  std::vector<unsigned char>::_Tidy((__int64)&v30);
  if ( (_DWORD)Uint64 )
  {
    v8.lpVtbl = NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl;
    NetSetup2::Property::GetString(v8.lpVtbl, &v33);
    v4 |= 0x20u;
    std::vector<unsigned char>::_Tidy((__int64)&v30);
    std::wstring::operator=(v42, &v33);
    std::wstring::_Tidy_deallocate((__int64)&v33);
    v28.lpVtbl = (struct PropertyVtbl *)131074;
    v29 = NETSETUPPKEY_Interface_IfDescr;
    v30 = 0x12u;
    LODWORD(v31) = 18;
    DWORD1(v31) = 2 * v43 + 2;
    *((_QWORD *)&v31 + 1) = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(&v35, &v28);
  }
  v9 = HIDWORD(NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl->Release) != 0;
  std::vector<unsigned char>::_Tidy((__int64)&v30);
  if ( v9 )
  {
    v10.lpVtbl = NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl;
    Uint64 = NetSetup2::Property::GetUint64((NetSetup2::Property *)v10.lpVtbl);
    std::vector<unsigned char>::_Tidy((__int64)&v30);
    v38 = Uint64;
    v28.lpVtbl = (struct PropertyVtbl *)2;
    v29 = NETSETUPPKEY_Interface_NetLuid;
    v30 = 4u;
    *(_QWORD *)&v31 = 0x800000009LL;
    *((_QWORD *)&v31 + 1) = &v38;
    std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(&v35, &v28);
  }
  LOBYTE(Uint64) = HIDWORD(NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl->Release) != 0;
  std::vector<unsigned char>::_Tidy((__int64)&v30);
  if ( (_BYTE)Uint64 )
  {
    v11.lpVtbl = NetSetup2::ObjectCreationTemplate::GetProperty(a2, &v28).lpVtbl;
    NetSetup2::Property::GetGuid((NetSetup2::Property *)v11.lpVtbl, &v33);
    std::vector<unsigned char>::_Tidy((__int64)&v30);
    v41 = v33;
    v28.lpVtbl = (struct PropertyVtbl *)2;
    v29 = NETSETUPPKEY_Object_Id;
    v30 = 2u;
    *(_QWORD *)&v31 = 0x100000000DLL;
    *((_QWORD *)&v31 + 1) = &v41;
    std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(&v35, &v28);
  }
  v28.lpVtbl = (struct PropertyVtbl *)0x400000;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(&v35, &v28);
  if ( (unsigned __int64)(0x6DB6DB6DB6DB6DB7LL * ((v36 - (__int64)v35) >> 3)) > 2 )
  {
    NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(
      a1,
      (__int64 *)&v39,
      v12,
      0,
      0,
      (__int64)v35,
      -1227133513 * ((v36 - (__int64)v35) >> 3));
    v13 = v4 | 0x40;
    v27 = v13;
    __SET_PAIR__(v14, v15, v39);
    v18 = v39;
    v16 = (NetSetup2::ActiveObject **)(v18 >> 64);
    v17 = (NetSetup2::ActiveObject **)v18;
    *(_QWORD *)&v33.Data1 = *((_QWORD *)&v39 + 1);
    while ( 1 )
    {
      v32 = v17;
      if ( v17 == v16 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        NetSetup2::NetworkInterface::get_PnpInstance(*v17, &v28);
        Uint64 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        NetSetup2::NetworkInterface::get_IfAlias(*v17, v34);
        v13 |= 3u;
        v27 = v13;
        v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, v20, v19, Uint64);
      }
      if ( (v13 & 2) != 0 )
      {
        v13 &= ~2u;
        v27 = v13;
        std::wstring::_Tidy_deallocate((__int64)v34);
      }
      if ( (v13 & 1) != 0 )
      {
        v13 &= ~1u;
        v27 = v13;
        std::wstring::_Tidy_deallocate((__int64)&v28);
      }
      try
      {
        NetSetup2::ActiveObject::Delete(*v17);
      }
      catch ( ... )
      {
        v21 = Uint64;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          v24 = v27;
        }
        else
        {
          v22 = v32;
          NetSetup2::NetworkInterface::get_PnpInstance(*v32, v34);
          v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          NetSetup2::NetworkInterface::get_IfAlias(*v22, &v28);
          v24 = v27 | 0xC;
          v27 |= 0xCu;
          v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v26, v25, v23);
        }
        if ( (v24 & 8) != 0 )
        {
          v24 &= ~8u;
          v27 = v24;
          std::wstring::_Tidy_deallocate((__int64)&v28);
        }
        if ( (v24 & 4) != 0 )
        {
          v27 = v24 & 0xFFFFFFFB;
          std::wstring::_Tidy_deallocate((__int64)v34);
        }
        Uint64 = v21;
        v17 = v32;
        v16 = *(NetSetup2::ActiveObject ***)&v33.Data1;
        v13 = v27;
      }
      ++v17;
      v14 = *((_QWORD *)&v39 + 1);
      v15 = v39;
    }
    if ( v15 )
    {
      std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(v15, v14);
      std::_Deallocate<16>((_QWORD *)v39, (v40 - v39) & 0xFFFFFFFFFFFFFFF8uLL);
      v39 = 0;
      v40 = 0;
    }
  }
  std::wstring::_Tidy_deallocate((__int64)v42);
  std::wstring::_Tidy_deallocate((__int64)v44);
  if ( v35 )
    std::_Deallocate<16>(v35, 8 * ((v37 - (__int64)v35) >> 3));
}

```

## disassembly

```asm
0x180022800  mov     [rsp+arg_10], rbx
0x180022805  push    rsi
0x180022806  push    rdi
0x180022807  push    r12
0x180022809  push    r14
0x18002280b  push    r15
0x18002280d  sub     rsp, 170h
0x180022814  mov     rax, cs:__security_cookie
0x18002281b  xor     rax, rsp
0x18002281e  mov     [rsp+198h+var_38], rax
0x180022826  mov     r14, rdx
0x180022829  mov     r12, rcx
0x18002282c  xor     esi, esi
0x18002282e  mov     edi, esi
0x180022830  mov     [rsp+198h+var_158], esi
0x180022834  lea     rcx, [rsp+198h+var_C8]
0x18002283c  call    ??0?$vector@PEAUNETSETUP_RPC_CONTEXT@@V?$allocator@PEAUNETSETUP_RPC_CONTEXT@@@std@@@std@@QEAA@XZ; std::vector<NETSETUP_RPC_CONTEXT *>::vector<NETSETUP_RPC_CONTEXT *>(void)
0x180022841  nop
0x180022842  lea     rcx, [rsp+198h+var_58]
0x18002284a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002284f  nop
0x180022850  lea     rcx, [rsp+198h+var_78]
0x180022858  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002285d  nop
0x18002285e  mov     [rsp+198h+var_B0], rsi
0x180022866  xorps   xmm0, xmm0
0x180022869  movups  [rsp+198h+var_88], xmm0
0x180022871  mov     [rsp+198h+var_150], 300000h
0x18002287a  movups  [rsp+198h+var_148], xmm0
0x18002287f  movups  [rsp+198h+var_138], xmm0
0x180022884  movups  [rsp+198h+var_128], xmm0
0x180022889  lea     rdx, [rsp+198h+var_150]
0x18002288e  lea     rcx, [rsp+198h+var_C8]
0x180022896  call    ??$emplace_back@U_NETSETUPPROP_FILTER_EXPRESSION@@@?$vector@U_NETSETUPPROP_FILTER_EXPRESSION@@V?$allocator@U_NETSETUPPROP_FILTER_EXPRESSION@@@std@@@std@@QEAAAEAU_NETSETUPPROP_FILTER_EXPRESSION@@$$QEAU2@@Z; std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(_NETSETUPPROP_FILTER_EXPRESSION &&)
0x18002289b  lea     r8, NETSETUPPKEY_Interface_IfAlias
0x1800228a2  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x1800228a7  mov     rcx, r14; this
0x1800228aa  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x1800228af  mov     ebx, [rax+14h]
0x1800228b2  lea     rcx, [rsp+198h+var_138]
0x1800228b7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800228bc  test    ebx, ebx
0x1800228be  jz      loc_180022980
0x1800228c4  lea     r8, NETSETUPPKEY_Interface_IfAlias
0x1800228cb  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x1800228d0  mov     rcx, r14; this
0x1800228d3  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x1800228d8  nop
0x1800228d9  lea     rdx, [rsp+198h+var_108]
0x1800228e1  mov     rcx, rax
0x1800228e4  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x1800228e9  lea     edi, [rsi+10h]
0x1800228ec  lea     rcx, [rsp+198h+var_138]
0x1800228f1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800228f6  lea     rdx, [rsp+198h+var_108]
0x1800228fe  lea     rcx, [rsp+198h+var_58]
0x180022906  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002290b  lea     rcx, [rsp+198h+var_108]
0x180022913  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022918  mov     [rsp+198h+var_150], 20002h
0x180022921  movups  xmm0, cs:NETSETUPPKEY_Interface_IfAlias
0x180022928  movups  [rsp+198h+var_148], xmm0
0x18002292d  mov     eax, cs:dword_180037938
0x180022933  mov     dword ptr [rsp+198h+var_138], eax
0x180022937  xor     eax, eax
0x180022939  mov     qword ptr [rsp+198h+var_138+4], rax
0x18002293e  mov     dword ptr [rsp+198h+var_138+0Ch], eax
0x180022942  mov     dword ptr [rsp+198h+var_128], 12h
0x18002294a  mov     eax, [rsp+198h+var_48]
0x180022951  lea     eax, ds:2[rax*2]
0x180022958  mov     dword ptr [rsp+198h+var_128+4], eax
0x18002295c  lea     rcx, [rsp+198h+var_58]
0x180022964  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022969  mov     qword ptr [rsp+198h+var_128+8], rax
0x18002296e  lea     rdx, [rsp+198h+var_150]
0x180022973  lea     rcx, [rsp+198h+var_C8]
0x18002297b  call    ??$emplace_back@U_NETSETUPPROP_FILTER_EXPRESSION@@@?$vector@U_NETSETUPPROP_FILTER_EXPRESSION@@V?$allocator@U_NETSETUPPROP_FILTER_EXPRESSION@@@std@@@std@@QEAAAEAU_NETSETUPPROP_FILTER_EXPRESSION@@$$QEAU2@@Z; std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(_NETSETUPPROP_FILTER_EXPRESSION &&)
0x180022980  lea     r8, NETSETUPPKEY_Interface_IfDescr
0x180022987  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x18002298c  mov     rcx, r14; this
0x18002298f  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x180022994  mov     ebx, [rax+14h]
0x180022997  lea     rcx, [rsp+198h+var_138]
0x18002299c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800229a1  test    ebx, ebx
0x1800229a3  jz      loc_180022A65
0x1800229a9  lea     r8, NETSETUPPKEY_Interface_IfDescr
0x1800229b0  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x1800229b5  mov     rcx, r14; this
0x1800229b8  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x1800229bd  nop
0x1800229be  lea     rdx, [rsp+198h+var_108]
0x1800229c6  mov     rcx, rax
0x1800229c9  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x1800229ce  or      edi, 20h
0x1800229d1  lea     rcx, [rsp+198h+var_138]
0x1800229d6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800229db  lea     rdx, [rsp+198h+var_108]
0x1800229e3  lea     rcx, [rsp+198h+var_78]
0x1800229eb  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800229f0  lea     rcx, [rsp+198h+var_108]
0x1800229f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800229fd  mov     [rsp+198h+var_150], 20002h
0x180022a06  movups  xmm0, cs:NETSETUPPKEY_Interface_IfDescr
0x180022a0d  movups  [rsp+198h+var_148], xmm0
0x180022a12  mov     eax, cs:dword_18003F160
0x180022a18  mov     dword ptr [rsp+198h+var_138], eax
0x180022a1c  xor     eax, eax
0x180022a1e  mov     qword ptr [rsp+198h+var_138+4], rax
0x180022a23  mov     dword ptr [rsp+198h+var_138+0Ch], eax
0x180022a27  mov     dword ptr [rsp+198h+var_128], 12h
0x180022a2f  mov     eax, [rsp+198h+var_68]
0x180022a36  lea     eax, ds:2[rax*2]
0x180022a3d  mov     dword ptr [rsp+198h+var_128+4], eax
0x180022a41  lea     rcx, [rsp+198h+var_78]
0x180022a49  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022a4e  mov     qword ptr [rsp+198h+var_128+8], rax
0x180022a53  lea     rdx, [rsp+198h+var_150]
0x180022a58  lea     rcx, [rsp+198h+var_C8]
0x180022a60  call    ??$emplace_back@U_NETSETUPPROP_FILTER_EXPRESSION@@@?$vector@U_NETSETUPPROP_FILTER_EXPRESSION@@V?$allocator@U_NETSETUPPROP_FILTER_EXPRESSION@@@std@@@std@@QEAAAEAU_NETSETUPPROP_FILTER_EXPRESSION@@$$QEAU2@@Z; std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(_NETSETUPPROP_FILTER_EXPRESSION &&)
0x180022a65  lea     r8, NETSETUPPKEY_Interface_NetLuid
0x180022a6c  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x180022a71  mov     rcx, r14; this
0x180022a74  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x180022a79  cmp     [rax+14h], esi
0x180022a7c  setnz   bl
0x180022a7f  lea     rcx, [rsp+198h+var_138]
0x180022a84  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022a89  test    bl, bl
0x180022a8b  jz      loc_180022B1C
0x180022a91  lea     r8, NETSETUPPKEY_Interface_NetLuid
0x180022a98  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x180022a9d  mov     rcx, r14; this
0x180022aa0  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x180022aa5  nop
0x180022aa6  mov     rcx, rax; this
0x180022aa9  call    ?GetUint64@Property@NetSetup2@@QEBA_KXZ; NetSetup2::Property::GetUint64(void)
0x180022aae  mov     rbx, rax
0x180022ab1  lea     rcx, [rsp+198h+var_138]
0x180022ab6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022abb  mov     [rsp+198h+var_B0], rbx
0x180022ac3  mov     [rsp+198h+var_150], 2
0x180022acc  movups  xmm0, cs:NETSETUPPKEY_Interface_NetLuid
0x180022ad3  movups  [rsp+198h+var_148], xmm0
0x180022ad8  mov     eax, cs:dword_18003F1D8
0x180022ade  mov     dword ptr [rsp+198h+var_138], eax
0x180022ae2  xor     eax, eax
0x180022ae4  mov     qword ptr [rsp+198h+var_138+4], rax
0x180022ae9  mov     dword ptr [rsp+198h+var_138+0Ch], eax
0x180022aed  mov     dword ptr [rsp+198h+var_128], 9
0x180022af5  mov     dword ptr [rsp+198h+var_128+4], 8
0x180022afd  lea     rax, [rsp+198h+var_B0]
0x180022b05  mov     qword ptr [rsp+198h+var_128+8], rax
0x180022b0a  lea     rdx, [rsp+198h+var_150]
0x180022b0f  lea     rcx, [rsp+198h+var_C8]
0x180022b17  call    ??$emplace_back@U_NETSETUPPROP_FILTER_EXPRESSION@@@?$vector@U_NETSETUPPROP_FILTER_EXPRESSION@@V?$allocator@U_NETSETUPPROP_FILTER_EXPRESSION@@@std@@@std@@QEAAAEAU_NETSETUPPROP_FILTER_EXPRESSION@@$$QEAU2@@Z; std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(_NETSETUPPROP_FILTER_EXPRESSION &&)
0x180022b1c  lea     r8, NETSETUPPKEY_Object_Id
0x180022b23  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x180022b28  mov     rcx, r14; this
0x180022b2b  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x180022b30  cmp     [rax+14h], esi
0x180022b33  setnz   bl
0x180022b36  lea     rcx, [rsp+198h+var_138]
0x180022b3b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022b40  test    bl, bl
0x180022b42  jz      loc_180022BE2
0x180022b48  lea     r8, NETSETUPPKEY_Object_Id
0x180022b4f  lea     rdx, [rsp+198h+var_150]; struct _NETSETUPPROPKEY *
0x180022b54  mov     rcx, r14; this
0x180022b57  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x180022b5c  nop
0x180022b5d  lea     rdx, [rsp+198h+var_108]; retstr
0x180022b65  mov     rcx, rax; this
0x180022b68  call    ?GetGuid@Property@NetSetup2@@QEBA?AU_GUID@@XZ; NetSetup2::Property::GetGuid(void)
0x180022b6d  nop
0x180022b6e  lea     rcx, [rsp+198h+var_138]
0x180022b73  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022b78  movaps  xmm0, xmmword ptr [rsp+198h+var_108.Data1]
0x180022b80  movdqa  [rsp+198h+var_88], xmm0
0x180022b89  mov     [rsp+198h+var_150], 2
0x180022b92  movups  xmm0, cs:NETSETUPPKEY_Object_Id
0x180022b99  movups  [rsp+198h+var_148], xmm0
0x180022b9e  mov     eax, cs:dword_18003F280
0x180022ba4  mov     dword ptr [rsp+198h+var_138], eax
0x180022ba8  xor     eax, eax
0x180022baa  mov     qword ptr [rsp+198h+var_138+4], rax
0x180022baf  mov     dword ptr [rsp+198h+var_138+0Ch], eax
0x180022bb3  mov     dword ptr [rsp+198h+var_128], 0Dh
0x180022bbb  mov     dword ptr [rsp+198h+var_128+4], 10h
0x180022bc3  lea     rax, [rsp+198h+var_88]
0x180022bcb  mov     qword ptr [rsp+198h+var_128+8], rax
0x180022bd0  lea     rdx, [rsp+198h+var_150]
0x180022bd5  lea     rcx, [rsp+198h+var_C8]
0x180022bdd  call    ??$emplace_back@U_NETSETUPPROP_FILTER_EXPRESSION@@@?$vector@U_NETSETUPPROP_FILTER_EXPRESSION@@V?$allocator@U_NETSETUPPROP_FILTER_EXPRESSION@@@std@@@std@@QEAAAEAU_NETSETUPPROP_FILTER_EXPRESSION@@$$QEAU2@@Z; std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(_NETSETUPPROP_FILTER_EXPRESSION &&)
0x180022be2  mov     [rsp+198h+var_150], 400000h
0x180022beb  xorps   xmm0, xmm0
0x180022bee  movups  [rsp+198h+var_148], xmm0
0x180022bf3  movups  [rsp+198h+var_138], xmm0
0x180022bf8  movups  [rsp+198h+var_128], xmm0
0x180022bfd  lea     rdx, [rsp+198h+var_150]
0x180022c02  lea     rcx, [rsp+198h+var_C8]
0x180022c0a  call    ??$emplace_back@U_NETSETUPPROP_FILTER_EXPRESSION@@@?$vector@U_NETSETUPPROP_FILTER_EXPRESSION@@V?$allocator@U_NETSETUPPROP_FILTER_EXPRESSION@@@std@@@std@@QEAAAEAU_NETSETUPPROP_FILTER_EXPRESSION@@$$QEAU2@@Z; std::vector<_NETSETUPPROP_FILTER_EXPRESSION>::emplace_back<_NETSETUPPROP_FILTER_EXPRESSION>(_NETSETUPPROP_FILTER_EXPRESSION &&)
0x180022c0f  mov     rax, [rsp+198h+var_C0]
0x180022c17  mov     rcx, [rsp+198h+var_C8]
0x180022c1f  sub     rax, rcx
0x180022c22  sar     rax, 3
0x180022c26  mov     r15, 6DB6DB6DB6DB6DB7h
0x180022c30  imul    rax, r15
0x180022c34  cmp     rax, 2
0x180022c38  jbe     loc_180022DBA
0x180022c3e  mov     [rsp+198h+var_168], eax
0x180022c42  mov     [rsp+198h+var_170], rcx
0x180022c47  mov     dword ptr [rsp+198h+var_178], esi
0x180022c4b  xor     r9d, r9d
0x180022c4e  lea     rdx, [rsp+198h+var_A8]
0x180022c56  mov     rcx, r12
0x180022c59  call    ??$GetAllObjectsInner@VNetworkInterface@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x180022c5e  or      edi, 40h
0x180022c61  mov     [rsp+198h+var_158], edi
0x180022c65  mov     rcx, qword ptr [rsp+198h+var_A8]
0x180022c6d  mov     r14, rcx
0x180022c70  mov     rdx, qword ptr [rsp+198h+var_A8+8]
0x180022c78  mov     r12, rdx
0x180022c7b  mov     qword ptr [rsp+198h+var_108.Data1], rdx
0x180022c83  mov     [rsp+198h+var_118], r14
0x180022c8b  cmp     r14, r12
0x180022c8e  jz      loc_180022D80
0x180022c94  lea     rcx, WPP_GLOBAL_Control
0x180022c9b  mov     rax, cs:WPP_GLOBAL_Control
0x180022ca2  cmp     rax, rcx
0x180022ca5  jz      short loc_180022D09
0x180022ca7  cmp     byte ptr [rax+19h], 3
0x180022cab  jb      short loc_180022D09
0x180022cad  lea     rdx, [rsp+198h+var_150]
0x180022cb2  mov     rcx, [r14]
0x180022cb5  call    ?get_PnpInstance@NetworkInterface@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::NetworkInterface::get_PnpInstance(void)
0x180022cba  nop
0x180022cbb  or      edi, 1
0x180022cbe  mov     [rsp+198h+var_158], edi
0x180022cc2  mov     rcx, rax
0x180022cc5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022cca  mov     rbx, rax
0x180022ccd  lea     rdx, [rsp+198h+var_E8]
0x180022cd5  mov     rcx, [r14]
0x180022cd8  call    ?get_IfAlias@NetworkInterface@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::NetworkInterface::get_IfAlias(void)
0x180022cdd  or      edi, 2
0x180022ce0  mov     [rsp+198h+var_158], edi
0x180022ce4  mov     rcx, rax
0x180022ce7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022cec  mov     edx, 31h ; '1'
0x180022cf1  mov     [rsp+198h+var_178], rbx
0x180022cf6  mov     r9, rax
0x180022cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d00  mov     rcx, [rcx+10h]
0x180022d04  call    WPP_SF_SS
0x180022d09  test    dil, 2
0x180022d0d  jz      short loc_180022D24
0x180022d0f  and     edi, 0FFFFFFFDh
0x180022d12  mov     [rsp+198h+var_158], edi
0x180022d16  lea     rcx, [rsp+198h+var_E8]
0x180022d1e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d23  nop
0x180022d24  test    dil, 1
0x180022d28  jz      short loc_180022D3C
0x180022d2a  and     edi, 0FFFFFFFEh
0x180022d2d  mov     [rsp+198h+var_158], edi
0x180022d31  lea     rcx, [rsp+198h+var_150]
0x180022d36  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022d3b  nop
0x180022d3c  mov     rcx, [r14]; this
0x180022d3f  call    ?Delete@ActiveObject@NetSetup2@@QEAAXXZ; NetSetup2::ActiveObject::Delete(void)
0x180022d44  nop
0x180022d45  jmp     short loc_180022D67
0x180022d47  xor     esi, esi
0x180022d49  mov     r15, 6DB6DB6DB6DB6DB7h
0x180022d53  mov     r14, [rsp+198h+var_118]
0x180022d5b  mov     r12, qword ptr [rsp+198h+var_108.Data1]
0x180022d63  mov     edi, [rsp+198h+var_158]
0x180022d67  add     r14, 8
0x180022d6b  mov     rdx, qword ptr [rsp+198h+var_A8+8]
0x180022d73  mov     rcx, qword ptr [rsp+198h+var_A8]
0x180022d7b  jmp     loc_180022C83
0x180022d80  test    rcx, rcx
0x180022d83  jz      short loc_180022DBA
0x180022d85  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<NetSetup2::ClientDriver>>>(std::unique_ptr<NetSetup2::ClientDriver> *,std::unique_ptr<NetSetup2::ClientDriver> * const,std::allocator<std::unique_ptr<NetSetup2::ClientDriver>> &)
0x180022d8a  mov     rcx, qword ptr [rsp+198h+var_A8]
0x180022d92  mov     rdx, [rsp+198h+var_98]
0x180022d9a  sub     rdx, rcx
0x180022d9d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180022da1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180022da6  xorps   xmm0, xmm0
0x180022da9  movdqu  [rsp+198h+var_A8], xmm0
0x180022db2  mov     [rsp+198h+var_98], rsi
0x180022dba  lea     rcx, [rsp+198h+var_78]
0x180022dc2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022dc7  nop
0x180022dc8  lea     rcx, [rsp+198h+var_58]
0x180022dd0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022dd5  nop
0x180022dd6  mov     rcx, [rsp+198h+var_C8]
  ... truncated ...
```
