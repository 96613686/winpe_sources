# VmSwitchNetSetupPlugin::EnableBindings(_NETSETUP_OBJECT_ID const &,bool)

- ea: `0x18007e824`
- end: `0x18007eb66`
- name: `?EnableBindings@VmSwitchNetSetupPlugin@@AEAAXAEBU_NETSETUP_OBJECT_ID@@_N@Z`
- size: `834`
- prototype: `void __fastcall(VmSwitchNetSetupPlugin *__hidden this, const struct _NETSETUP_OBJECT_ID *, bool)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ef78`

## callees

- `0x18000a430`
- `0x18000fd70`
- `0x180016a20`
- `0x180017320`
- `0x1800179a8`
- `0x180029d20`
- `0x180037558`
- `0x1800433c4`
- `0x180043428`
- `0x18004462c`
- `0x180056c04`
- `0x18005b1e4`
- `0x18005bd70`
- `0x18005c848`
- `0x180062e34`
- `0x180064704`
- `0x18006c8ac`
- `0x18007e824`
- `0x1800810d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18007ea39`
- `msvcrt!_wcsicmp` at `0x18007eabf`
- `msvcrt!_wcsicmp` at `0x18007ea39`
- `msvcrt!_wcsicmp` at `0x18007eabf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall VmSwitchNetSetupPlugin::EnableBindings(
        VmSwitchNetSetupPlugin *this,
        const struct _NETSETUP_OBJECT_ID *a2,
        char a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  NetSetup2::BindingPath **v7; // rbx
  NetSetup2::BindingPath **v8; // rdi
  int v9; // eax
  __int64 ProtocolDriverById; // rax
  const wchar_t *v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  NetSetup2::ActiveObject *FilterDriverById; // rax
  struct Property v15; // rax
  const wchar_t *v16; // rcx
  int v17; // eax
  __int128 v18; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-C0h]
  __int128 v20; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A8h]
  void *Block; // [rsp+70h] [rbp-98h] BYREF
  NetSetup2::BindingPath **v23; // [rsp+78h] [rbp-90h]
  __int64 v24; // [rsp+88h] [rbp-80h]
  char v25[24]; // [rsp+90h] [rbp-78h] BYREF
  char v26[24]; // [rsp+A8h] [rbp-60h] BYREF
  char v27[8]; // [rsp+C0h] [rbp-48h] BYREF
  wchar_t *String1[3]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 v29; // [rsp+E0h] [rbp-28h]
  int v30; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v31[28]; // [rsp+ECh] [rbp-1Ch] BYREF
  int v32; // [rsp+108h] [rbp+0h] BYREF
  __int128 v33; // [rsp+110h] [rbp+8h]
  int v34; // [rsp+120h] [rbp+18h]
  __int64 v35; // [rsp+124h] [rbp+1Ch]
  int v36; // [rsp+12Ch] [rbp+24h]
  int v37; // [rsp+130h] [rbp+28h]
  int v38; // [rsp+134h] [rbp+2Ch]
  const struct _NETSETUP_OBJECT_ID *v39; // [rsp+138h] [rbp+30h]
  int v40; // [rsp+140h] [rbp+38h]
  __int128 v41; // [rsp+148h] [rbp+40h]
  int v42; // [rsp+158h] [rbp+50h]
  __int64 v43; // [rsp+15Ch] [rbp+54h]
  int v44; // [rsp+164h] [rbp+5Ch]
  int v45; // [rsp+168h] [rbp+60h]
  int v46; // [rsp+16Ch] [rbp+64h]
  const wchar_t *v47; // [rsp+170h] [rbp+68h]
  int v48; // [rsp+178h] [rbp+70h]
  __int128 v49; // [rsp+180h] [rbp+78h]
  int v50; // [rsp+190h] [rbp+88h]
  __int64 v51; // [rsp+194h] [rbp+8Ch]
  int v52; // [rsp+19Ch] [rbp+94h]
  __int128 v53; // [rsp+1A0h] [rbp+98h]

  v24 = -2;
  v32 = 2;
  v33 = *(_OWORD *)&NETSETUPPKEY_Binding_Lowest;
  v34 = 10;
  v35 = 0;
  v36 = 0;
  v37 = 129;
  v38 = 20;
  v39 = a2;
  v40 = 805502978;
  v41 = NETSETUPPKEY_Driver_Identifier;
  v42 = 2;
  v43 = 0;
  v44 = 0;
  v45 = 18;
  v46 = 14;
  v47 = L"vms_pp";
  v48 = 65537;
  v49 = NETSETUPPKEY_Binding_ReasonPathIsCritical;
  v50 = 30;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  NetSetup2::details::TransactionBase::GetAllBindingPaths<3>(*(_QWORD *)this, (__int64)&Block, (__int64)&v32);
  v7 = (NetSetup2::BindingPath **)Block;
  v8 = v23;
  while ( v7 != v8 )
  {
    NetSetup2::details::TryGetObjectWithFilter<NetSetup2::BindingPath>(
      (__int64)&v18,
      *(_QWORD *)this,
      v6,
      *(_DWORD *)v7 + 20);
    if ( !(_BYTE)v21 )
      goto LABEL_25;
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete((_QWORD **)&v18 + 1);
    if ( a3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
      v18 = NETSETUPPKEY_Binding_EnabledByUser;
      v19 = 4;
      v20 = 0;
      v21 = 0;
      NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property>(*v7, &v18);
      std::vector<_NETSETUPPROPKEY>::_Tidy(&v20);
    }
    else
    {
      NetSetup2::BindingPath::get_Highest(*v7, &v30);
      if ( !NetSetup2::BindingPath::get_IsEnabled(*v7) )
        goto LABEL_25;
      v9 = v30;
      if ( v30 == 4 )
      {
        ProtocolDriverById = NetSetup2::details::TransactionBase::GetProtocolDriverById(*(_QWORD *)this, &v18, v31);
        NetSetup2::ProtocolDriver::get_Identifier(ProtocolDriverById, String1);
        std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete((_QWORD **)&v18 + 1);
        v11 = (const wchar_t *)String1;
        if ( v29 >= 8 )
          v11 = String1[0];
        v12 = _wcsicmp(v11, L"ms_lldp");
        LOBYTE(v13) = 1;
        if ( !v12 )
        {
LABEL_14:
          std::wstring::_Tidy(String1, v13, 0);
          goto LABEL_25;
        }
        std::wstring::_Tidy(String1, v13, 0);
        v9 = v30;
      }
      if ( v9 == 3 )
      {
        FilterDriverById = (NetSetup2::ActiveObject *)NetSetup2::details::TransactionBase::GetFilterDriverById(
                                                        *(_QWORD *)this,
                                                        &v18,
                                                        v31);
        v15.lpVtbl = NetSetup2::ActiveObject::GetProperty(FilterDriverById, (const struct _NETSETUPPROPKEY *)v25).lpVtbl;
        NetSetup2::Property::GetString(v15.lpVtbl, String1);
        std::vector<_NETSETUPPROPKEY>::_Tidy(v26);
        std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete((_QWORD **)&v18 + 1);
        v16 = (const wchar_t *)String1;
        if ( v29 >= 8 )
          v16 = String1[0];
        v17 = _wcsicmp(v16, L"ms_l1vhlwf");
        LOBYTE(v13) = 1;
        if ( !v17 )
          goto LABEL_14;
        std::wstring::_Tidy(String1, v13, 0);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
      v27[0] = 0;
      NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(*v7, &NETSETUPPKEY_Binding_EnabledByUser, v27);
    }
LABEL_25:
    ++v7;
  }
  if ( Block )
  {
    std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Destroy(v5, Block, v23);
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x18007e824  mov     rax, rsp
0x18007e827  push    rbp
0x18007e828  push    rsi
0x18007e829  push    rdi
0x18007e82a  push    r12
0x18007e82c  push    r14
0x18007e82e  lea     rbp, [rax-0E8h]
0x18007e835  sub     rsp, 1C0h
0x18007e83c  mov     [rbp+0E0h+var_160], 0FFFFFFFFFFFFFFFEh
0x18007e844  mov     [rax+18h], rbx
0x18007e848  mov     rax, cs:__security_cookie
0x18007e84f  xor     rax, rsp
0x18007e852  mov     [rbp+0E0h+var_30], rax
0x18007e859  mov     r14b, r8b
0x18007e85c  mov     rsi, rcx
0x18007e85f  mov     [rbp+0E0h+var_E0], 2
0x18007e866  movups  xmm0, cs:NETSETUPPKEY_Binding_Lowest
0x18007e86d  movups  [rbp+0E0h+var_D8], xmm0
0x18007e871  mov     eax, cs:dword_18009A030
0x18007e877  mov     [rbp+0E0h+var_C8], eax
0x18007e87a  xor     eax, eax
0x18007e87c  mov     [rbp+0E0h+var_C4], rax
0x18007e880  mov     [rbp+0E0h+var_BC], eax
0x18007e883  mov     [rbp+0E0h+var_B8], 81h
0x18007e88a  mov     [rbp+0E0h+var_B4], 14h
0x18007e891  mov     [rbp+0E0h+var_B0], rdx
0x18007e895  mov     [rbp+0E0h+var_A8], 30030002h
0x18007e89c  movups  xmm0, cs:NETSETUPPKEY_Driver_Identifier
0x18007e8a3  movaps  [rbp+0E0h+var_A0], xmm0
0x18007e8a7  mov     eax, cs:dword_18009A018
0x18007e8ad  mov     [rbp+0E0h+var_90], eax
0x18007e8b0  xor     eax, eax
0x18007e8b2  mov     [rbp+0E0h+var_8C], rax
0x18007e8b6  mov     [rbp+0E0h+var_84], eax
0x18007e8b9  mov     [rbp+0E0h+var_80], 12h
0x18007e8c0  mov     [rbp+0E0h+var_7C], 0Eh
0x18007e8c7  lea     rax, aVmsPp_0; "vms_pp"
0x18007e8ce  mov     [rbp+0E0h+var_78], rax
0x18007e8d2  mov     [rbp+0E0h+var_70], 10001h
0x18007e8d9  movups  xmm0, cs:NETSETUPPKEY_Binding_ReasonPathIsCritical
0x18007e8e0  movups  [rbp+0E0h+var_68], xmm0
0x18007e8e4  mov     eax, cs:dword_1800A40E8
0x18007e8ea  mov     [rbp+0E0h+var_58], eax
0x18007e8f0  xor     eax, eax
0x18007e8f2  mov     [rbp+0E0h+var_54], rax
0x18007e8f9  mov     [rbp+0E0h+var_4C], eax
0x18007e8ff  xorps   xmm0, xmm0
0x18007e902  movups  [rbp+0E0h+var_48], xmm0
0x18007e909  lea     r8, [rbp+0E0h+var_E0]
0x18007e90d  lea     rdx, [rsp+1E0h+Block]
0x18007e912  mov     rcx, [rcx]
0x18007e915  call    ??$GetAllBindingPaths@$02@TransactionBase@details@NetSetup2@@QEAA?AV?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAY02$$CBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::TransactionBase::GetAllBindingPaths<3>(_NETSETUPPROP_FILTER_EXPRESSION const (&)[3])
0x18007e91a  nop
0x18007e91b  mov     rbx, [rsp+1E0h+Block]
0x18007e920  mov     rdi, [rsp+1E0h+var_170]
0x18007e925  lea     r12, WPP_GLOBAL_Control
0x18007e92c  cmp     rbx, rdi
0x18007e92f  jz      loc_18007EB22
0x18007e935  mov     r9, [rbx]
0x18007e938  add     r9, 14h
0x18007e93c  mov     rdx, [rsi]
0x18007e93f  lea     rcx, [rsp+1E0h+var_1B8+8]
0x18007e944  call    ??$TryGetObjectWithFilter@VBindingPath@NetSetup2@@@details@NetSetup2@@YA?AV?$Optional@VBindingPath@NetSetup2@@@01@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::TryGetObjectWithFilter<NetSetup2::BindingPath>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x18007e949  cmp     byte ptr [rsp+1E0h+var_188], 0
0x18007e94e  jz      loc_18007EB19
0x18007e954  lea     rcx, [rsp+1E0h+var_1A8]
0x18007e959  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18007e95e  test    r14b, r14b
0x18007e961  jz      short loc_18007E9D7
0x18007e963  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e96a  cmp     rcx, r12
0x18007e96d  jz      short loc_18007E98A
0x18007e96f  cmp     byte ptr [rcx+19h], 4
0x18007e973  jb      short loc_18007E98A
0x18007e975  mov     edx, 18h
0x18007e97a  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007e981  mov     rcx, [rcx+10h]
0x18007e985  call    WPP_SF_
0x18007e98a  movups  xmm0, cs:NETSETUPPKEY_Binding_EnabledByUser
0x18007e991  movups  [rsp+1E0h+var_1B8+8], xmm0
0x18007e996  mov     eax, cs:dword_18009AF08
0x18007e99c  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x18007e9a0  mov     dword ptr [rsp+1E0h+var_1A0+4], 0
0x18007e9a8  xorps   xmm0, xmm0
0x18007e9ab  movdqu  [rsp+1E0h+var_1A0+8], xmm0
0x18007e9b1  mov     [rsp+1E0h+var_188], 0
0x18007e9ba  lea     rdx, [rsp+1E0h+var_1B8+8]
0x18007e9bf  mov     rcx, [rbx]
0x18007e9c2  call    ??$SetPropertyUniversal@VProperty@NetSetup2@@@ActiveObject@NetSetup2@@AEAAX$$QEAVProperty@1@@Z; NetSetup2::ActiveObject::SetPropertyUniversal<NetSetup2::Property>(NetSetup2::Property &&)
0x18007e9c7  nop
0x18007e9c8  lea     rcx, [rsp+1E0h+var_1A0+8]
0x18007e9cd  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18007e9d2  jmp     loc_18007EB19
0x18007e9d7  lea     rdx, [rbp+0E0h+var_100]
0x18007e9db  mov     rcx, [rbx]
0x18007e9de  call    ?get_Highest@BindingPath@NetSetup2@@QEBA?AU_NETSETUP_OBJECT_ID@@XZ; NetSetup2::BindingPath::get_Highest(void)
0x18007e9e3  mov     rcx, [rbx]; this
0x18007e9e6  call    ?get_IsEnabled@BindingPath@NetSetup2@@QEBA_NXZ; NetSetup2::BindingPath::get_IsEnabled(void)
0x18007e9eb  test    al, al
0x18007e9ed  jz      loc_18007EB19
0x18007e9f3  mov     eax, [rbp+0E0h+var_100]
0x18007e9f6  cmp     eax, 4
0x18007e9f9  jnz     short loc_18007EA5E
0x18007e9fb  lea     r8, [rbp+0E0h+var_FC]
0x18007e9ff  lea     rdx, [rsp+1E0h+var_1B8+8]
0x18007ea04  mov     rcx, [rsi]
0x18007ea07  call    ?GetProtocolDriverById@TransactionBase@details@NetSetup2@@QEAA?AVProtocolDriver@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetProtocolDriverById(_GUID const &)
0x18007ea0c  nop
0x18007ea0d  lea     rdx, [rbp+0E0h+String1]
0x18007ea11  mov     rcx, rax
0x18007ea14  call    ?get_Identifier@ProtocolDriver@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::ProtocolDriver::get_Identifier(void)
0x18007ea19  nop
0x18007ea1a  lea     rcx, [rsp+1E0h+var_1A8]
0x18007ea1f  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18007ea24  lea     rcx, [rbp+0E0h+String1]
0x18007ea28  cmp     [rbp+0E0h+var_108], 8
0x18007ea2d  cmovnb  rcx, [rbp+0E0h+String1]; String1
0x18007ea32  lea     rdx, aMsLldp; "ms_lldp"
0x18007ea39  call    cs:__imp__wcsicmp
0x18007ea3f  xor     r8d, r8d
0x18007ea42  mov     dl, 1
0x18007ea44  lea     rcx, [rbp+0E0h+String1]
0x18007ea48  test    eax, eax
0x18007ea4a  jnz     short loc_18007EA56
0x18007ea4c  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18007ea51  jmp     loc_18007EB19
0x18007ea56  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18007ea5b  mov     eax, [rbp+0E0h+var_100]
0x18007ea5e  cmp     eax, 3
0x18007ea61  jnz     short loc_18007EADB
0x18007ea63  lea     r8, [rbp+0E0h+var_FC]
0x18007ea67  lea     rdx, [rsp+1E0h+var_1B8+8]
0x18007ea6c  mov     rcx, [rsi]
0x18007ea6f  call    ?GetFilterDriverById@TransactionBase@details@NetSetup2@@QEAA?AVFilterDriver@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetFilterDriverById(_GUID const &)
0x18007ea74  nop
0x18007ea75  lea     r8, NETSETUPPKEY_Driver_Identifier
0x18007ea7c  lea     rdx, [rbp+0E0h+var_158]; struct _NETSETUPPROPKEY *
0x18007ea80  mov     rcx, rax; this
0x18007ea83  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18007ea88  nop
0x18007ea89  lea     rdx, [rbp+0E0h+String1]
0x18007ea8d  mov     rcx, rax
0x18007ea90  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18007ea95  nop
0x18007ea96  lea     rcx, [rbp+0E0h+var_140]
0x18007ea9a  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18007ea9f  nop
0x18007eaa0  lea     rcx, [rsp+1E0h+var_1A8]
0x18007eaa5  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18007eaaa  lea     rcx, [rbp+0E0h+String1]
0x18007eaae  cmp     [rbp+0E0h+var_108], 8
0x18007eab3  cmovnb  rcx, [rbp+0E0h+String1]; String1
0x18007eab8  lea     rdx, aMsL1vhlwf; "ms_l1vhlwf"
0x18007eabf  call    cs:__imp__wcsicmp
0x18007eac5  xor     r8d, r8d
0x18007eac8  mov     dl, 1
0x18007eaca  lea     rcx, [rbp+0E0h+String1]
0x18007eace  test    eax, eax
0x18007ead0  jz      loc_18007EA4C
0x18007ead6  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18007eadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eae2  cmp     rcx, r12
0x18007eae5  jz      short loc_18007EB02
0x18007eae7  cmp     byte ptr [rcx+19h], 4
0x18007eaeb  jb      short loc_18007EB02
0x18007eaed  mov     edx, 19h
0x18007eaf2  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18007eaf9  mov     rcx, [rcx+10h]
0x18007eafd  call    WPP_SF_
0x18007eb02  mov     [rbp+0E0h+var_128], 0
0x18007eb06  lea     r8, [rbp+0E0h+var_128]
0x18007eb0a  lea     rdx, NETSETUPPKEY_Binding_EnabledByUser
0x18007eb11  mov     rcx, [rbx]
0x18007eb14  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18007eb19  add     rbx, 8
0x18007eb1d  jmp     loc_18007E92C
0x18007eb22  mov     rdx, [rsp+1E0h+Block]
0x18007eb27  test    rdx, rdx
0x18007eb2a  jz      short loc_18007EB40
0x18007eb2c  mov     r8, [rsp+1E0h+var_170]
0x18007eb31  call    ?_Destroy@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Destroy(std::unique_ptr<NetSetup2::BindingPath> *,std::unique_ptr<NetSetup2::BindingPath> *)
0x18007eb36  mov     rcx, [rsp+1E0h+Block]; Block
0x18007eb3b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007eb40  mov     rcx, [rbp+0E0h+var_30]
0x18007eb47  xor     rcx, rsp; StackCookie
0x18007eb4a  call    __security_check_cookie
0x18007eb4f  mov     rbx, [rsp+1E0h+arg_10]
0x18007eb57  add     rsp, 1C0h
0x18007eb5e  pop     r14
0x18007eb60  pop     r12
0x18007eb62  pop     rdi
0x18007eb63  pop     rsi
0x18007eb64  pop     rbp
0x18007eb65  retn
```
