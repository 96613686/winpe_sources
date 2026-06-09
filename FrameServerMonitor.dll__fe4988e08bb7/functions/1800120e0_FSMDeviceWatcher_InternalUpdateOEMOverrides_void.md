# FSMDeviceWatcher::InternalUpdateOEMOverrides(void)

- ea: `0x1800120e0`
- end: `0x1800124ed`
- name: `?InternalUpdateOEMOverrides@FSMDeviceWatcher@@MEAAXXZ`
- size: `1037`
- prototype: `void __fastcall(FSMDeviceWatcher *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005f98`
- `0x180006a98`
- `0x18000d154`
- `0x18000d4f8`
- `0x18000d62c`
- `0x18000e6bc`
- `0x1800120e0`
- `0x180017b98`
- `0x18003b9a4`
- `0x180041778`
- `0x180041d3c`
- `0x18004203c`
- `0x1800452c4`
- `0x1800499ac`
- `0x18004d010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800122a5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800122a5`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180012287`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180012287`

## pseudocode

```c
void __fastcall FSMDeviceWatcher::InternalUpdateOEMOverrides(FSMDeviceWatcher *this, __int64 a2, __int64 a3)
{
  int v4; // eax
  int v5; // edi
  void **i; // rbx
  __int64 v7; // rdx
  CONFIGRET v8; // eax
  signed int v9; // eax
  struct IFSMConfigurationsOEMCollection *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  HKEY phkDeviceInterface; // [rsp+30h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-28h] BYREF
  void **v18[4]; // [rsp+40h] [rbp-20h] BYREF
  bool v19; // [rsp+98h] [rbp+38h] BYREF
  ULONG v20; // [rsp+A0h] [rbp+40h] BYREF
  struct IFSMConfigurationsOEMCollection *v21; // [rsp+A8h] [rbp+48h] BYREF

  v18[0] = (void **)v18;
  v18[2] = 0;
  v18[1] = (void **)v18;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 314, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
  LOBYTE(a3) = 1;
  LOBYTE(a2) = 1;
  v4 = FSMEnumDevicesByCategory(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, a2, a3, v18);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v4);
LABEL_52:
    if ( byte_18005E5A5 )
    {
      v15 = 326;
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  for ( i = v18[0]; i != (void **)v18; i = (void **)*i )
  {
    v21 = 0;
    v19 = 0;
    v17 = 0;
    v20 = 0;
    phkDeviceInterface = 0;
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        316,
        (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
        (_DWORD)this,
        (__int64)i[2]);
    if ( FSIsBlockedSource((const unsigned __int16 *)i[2], 0) )
    {
      if ( (unsigned __int8)byte_18005E5A5 < 8u )
        goto LABEL_50;
      v7 = 317;
      goto LABEL_13;
    }
    FSIsNetworkCamera((LPCWSTR)i[2], &v19);
    if ( v19 )
    {
      if ( byte_18005E5A5 )
      {
        v7 = 318;
LABEL_13:
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), v7, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this);
      }
    }
    else
    {
      if ( !FSIsVirtualCamera((const unsigned __int16 *)i[2]) )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &phkDeviceInterface,
          0);
        v8 = CM_Open_Device_Interface_KeyW((LPCWSTR)i[2], 0x20019u, 1u, &phkDeviceInterface, 0);
        if ( v8 )
        {
          if ( byte_18005E5A5 )
          {
            v9 = CM_MapCrToWin32Err(v8, 0xDu);
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              320,
              &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
              this,
              v9);
          }
          goto LABEL_50;
        }
        v10 = v21;
        v21 = 0;
        if ( v10 )
          (*(void (__fastcall **)(struct IFSMConfigurationsOEMCollection *))(*(_QWORD *)v10 + 16LL))(v10);
        v11 = FSMConfigurationsOEMCollection::CreateInstance(phkDeviceInterface, &v21);
        v5 = v11;
        if ( v11 < 0 )
        {
          if ( byte_18005E5A5 )
          {
            v12 = 321;
            goto LABEL_30;
          }
          goto LABEL_31;
        }
        if ( !(*(unsigned int (__fastcall **)(struct IFSMConfigurationsOEMCollection *))(*(_QWORD *)v21 + 24LL))(v21) )
        {
          FSSaveGlobalConfigurationByName((unsigned __int16 *)i[2], 0);
          if ( (unsigned __int8)byte_18005E5A5 >= 8u )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              322,
              &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
              this,
              0);
          goto LABEL_50;
        }
        v11 = (*(__int64 (__fastcall **)(struct IFSMConfigurationsOEMCollection *, __int64 *, ULONG *))(*(_QWORD *)v21 + 40LL))(
                v21,
                &v17,
                &v20);
        if ( v11 < 0 )
        {
          if ( byte_18005E5A5 )
          {
            v12 = 323;
LABEL_30:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              v12,
              &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
              this,
              v11);
          }
LABEL_31:
          v5 = 0;
          FSSaveGlobalConfigurationByName((unsigned __int16 *)i[2], 0);
          goto LABEL_50;
        }
        if ( v17 && v20 )
        {
          v13 = FSSaveGlobalConfigurationByName((unsigned __int16 *)i[2], v20);
          v5 = v13;
          if ( v13 < 0 )
          {
            if ( byte_18005E5A5 )
            {
              v14 = 325;
              goto LABEL_46;
            }
            goto LABEL_47;
          }
        }
        else
        {
          v13 = FSSaveGlobalConfigurationByName((unsigned __int16 *)i[2], 0);
          v5 = v13;
          if ( v13 < 0 )
          {
            if ( (unsigned __int8)byte_18005E5A5 >= 8u )
            {
              v14 = 324;
LABEL_46:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                v14,
                &WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
                this,
                v13);
            }
LABEL_47:
            v5 = 0;
          }
        }
        if ( v21 )
          (*(void (__fastcall **)(struct IFSMConfigurationsOEMCollection *))(*(_QWORD *)v21 + 48LL))(v21);
        goto LABEL_50;
      }
      if ( byte_18005E5A5 )
      {
        v7 = 319;
        goto LABEL_13;
      }
    }
LABEL_50:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v21);
  }
  if ( v5 < 0 )
    goto LABEL_52;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v15 = 327;
LABEL_56:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v15, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, this, v5);
  }
LABEL_57:
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v18);
}

```

## disassembly

```asm
0x1800120e0  mov     [rsp-28h+arg_0], rbx
0x1800120e5  push    rbp
0x1800120e6  push    rsi
0x1800120e7  push    rdi
0x1800120e8  push    r14
0x1800120ea  push    r15
0x1800120ec  mov     rbp, rsp
0x1800120ef  sub     rsp, 60h
0x1800120f3  lea     rax, [rbp+var_20]
0x1800120f7  xor     r14d, r14d
0x1800120fa  mov     [rbp+var_20], rax
0x1800120fe  mov     rsi, rcx
0x180012101  lea     rax, [rbp+var_20]
0x180012105  mov     [rbp+var_10], r14
0x180012109  mov     [rbp+var_18], rax
0x18001210d  cmp     cs:byte_18005E5A5, 8
0x180012114  lea     r15, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x18001211b  jb      short loc_18001213B
0x18001211d  mov     r9, rcx
0x180012120  mov     edx, 13Ah
0x180012125  mov     rcx, cs:WPP_GLOBAL_Control
0x18001212c  mov     r8, r15
0x18001212f  mov     rcx, [rcx+0D8h]
0x180012136  call    WPP_SF_q
0x18001213b  mov     r8b, 1
0x18001213e  lea     r9, [rbp+var_20]
0x180012142  mov     dl, r8b
0x180012145  lea     rcx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x18001214c  call    FSMEnumDevicesByCategory
0x180012151  mov     edi, eax
0x180012153  test    eax, eax
0x180012155  jns     short loc_180012188
0x180012157  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001215e  jb      loc_180012495
0x180012164  mov     rcx, cs:WPP_GLOBAL_Control
0x18001216b  mov     edx, 13Bh
0x180012170  mov     r9, rsi
0x180012173  mov     [rsp+60h+ulFlags], eax
0x180012177  mov     r8, r15
0x18001217a  mov     rcx, [rcx+10h]
0x18001217e  call    WPP_SF_qD
0x180012183  jmp     loc_180012495
0x180012188  mov     rbx, [rbp+var_20]
0x18001218c  lea     rax, [rbp+var_20]
0x180012190  cmp     rbx, rax
0x180012193  jz      loc_180012491
0x180012199  mov     [rbp+arg_18], r14
0x18001219d  mov     [rbp+arg_8], r14b
0x1800121a1  mov     [rbp+var_28], r14
0x1800121a5  mov     [rbp+arg_10], r14d
0x1800121a9  mov     [rbp+phkDeviceInterface], r14
0x1800121ad  cmp     cs:byte_18005E5A5, 8
0x1800121b4  jb      short loc_1800121DD
0x1800121b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121bd  mov     edx, 13Ch
0x1800121c2  mov     rax, [rbx+10h]
0x1800121c6  mov     r9, rsi
0x1800121c9  mov     r8, r15
0x1800121cc  mov     qword ptr [rsp+60h+ulFlags], rax
0x1800121d1  mov     rcx, [rcx+0D8h]
0x1800121d8  call    WPP_SF_qS
0x1800121dd  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800121e1  xor     edx, edx; bool *
0x1800121e3  call    ?FSIsBlockedSource@@YA_NPEBGPEA_N@Z; FSIsBlockedSource(ushort const *,bool *)
0x1800121e8  test    al, al
0x1800121ea  jz      short loc_18001221C
0x1800121ec  cmp     cs:byte_18005E5A5, 8
0x1800121f3  jb      loc_180012477
0x1800121f9  mov     edx, 13Dh
0x1800121fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012205  mov     r9, rsi
0x180012208  mov     r8, r15
0x18001220b  mov     rcx, [rcx+0D8h]
0x180012212  call    WPP_SF_q
0x180012217  jmp     loc_180012477
0x18001221c  mov     rcx, [rbx+10h]; pszDeviceInterface
0x180012220  lea     rdx, [rbp+arg_8]; bool *
0x180012224  call    ?FSIsNetworkCamera@@YAJPEBGPEA_N@Z; FSIsNetworkCamera(ushort const *,bool *)
0x180012229  cmp     [rbp+arg_8], r14b
0x18001222d  jz      short loc_180012243
0x18001222f  cmp     cs:byte_18005E5A5, 1
0x180012236  jb      loc_180012477
0x18001223c  mov     edx, 13Eh
0x180012241  jmp     short loc_1800121FE
0x180012243  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180012247  call    ?FSIsVirtualCamera@@YA_NPEBG@Z; FSIsVirtualCamera(ushort const *)
0x18001224c  test    al, al
0x18001224e  jz      short loc_180012264
0x180012250  cmp     cs:byte_18005E5A5, 1
0x180012257  jb      loc_180012477
0x18001225d  mov     edx, 13Fh
0x180012262  jmp     short loc_1800121FE
0x180012264  xor     edx, edx
0x180012266  lea     rcx, [rbp+phkDeviceInterface]
0x18001226a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001226f  mov     rcx, [rbx+10h]; pszDeviceInterface
0x180012273  lea     r9, [rbp+phkDeviceInterface]; phkDeviceInterface
0x180012277  mov     edx, 20019h; samDesired
0x18001227c  mov     [rsp+60h+ulFlags], r14d; ulFlags
0x180012281  mov     r8d, 1; Disposition
0x180012287  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18001228d  test    eax, eax
0x18001228f  jz      short loc_1800122DE
0x180012291  cmp     cs:byte_18005E5A5, 1
0x180012298  jb      loc_180012477
0x18001229e  mov     edx, 0Dh; DefaultErr
0x1800122a3  mov     ecx, eax; CmReturnCode
0x1800122a5  call    cs:__imp_CM_MapCrToWin32Err
0x1800122ab  test    eax, eax
0x1800122ad  jle     short loc_1800122B7
0x1800122af  movzx   eax, ax
0x1800122b2  or      eax, 80070000h
0x1800122b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122be  mov     edx, 140h
0x1800122c3  mov     r9, rsi
0x1800122c6  mov     [rsp+60h+ulFlags], eax
0x1800122ca  mov     r8, r15
0x1800122cd  mov     rcx, [rcx+0D8h]
0x1800122d4  call    WPP_SF_qD
0x1800122d9  jmp     loc_180012477
0x1800122de  mov     rcx, [rbp+arg_18]
0x1800122e2  mov     [rbp+arg_18], r14
0x1800122e6  test    rcx, rcx
0x1800122e9  jz      short loc_1800122F7
0x1800122eb  mov     rax, [rcx]
0x1800122ee  mov     rax, [rax+10h]
0x1800122f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122f7  mov     rcx, [rbp+phkDeviceInterface]; HKEY
0x1800122fb  lea     rdx, [rbp+arg_18]; struct IFSMConfigurationsOEMCollection **
0x1800122ff  call    ?CreateInstance@FSMConfigurationsOEMCollection@@SAJPEAUHKEY__@@PEAPEAUIFSMConfigurationsOEMCollection@@@Z; FSMConfigurationsOEMCollection::CreateInstance(HKEY__ *,IFSMConfigurationsOEMCollection * *)
0x180012304  mov     edi, eax
0x180012306  test    eax, eax
0x180012308  jns     short loc_180012351
0x18001230a  cmp     cs:byte_18005E5A5, 1
0x180012311  jb      short loc_180012335
0x180012313  mov     edx, 141h
0x180012318  mov     rcx, cs:WPP_GLOBAL_Control
0x18001231f  mov     r9, rsi
0x180012322  mov     r8, r15
0x180012325  mov     [rsp+60h+ulFlags], eax
0x180012329  mov     rcx, [rcx+0D8h]
0x180012330  call    WPP_SF_qD
0x180012335  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180012339  xor     r9d, r9d
0x18001233c  xor     r8d, r8d
0x18001233f  mov     [rsp+60h+ulFlags], r14d; ULONG
0x180012344  mov     edi, r14d
0x180012347  call    FSSaveGlobalConfigurationByName
0x18001234c  jmp     loc_180012477
0x180012351  mov     rcx, [rbp+arg_18]
0x180012355  mov     rax, [rcx]
0x180012358  mov     rax, [rax+18h]
0x18001235c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012361  test    eax, eax
0x180012363  jnz     short loc_1800123AE
0x180012365  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180012369  xor     r9d, r9d
0x18001236c  xor     r8d, r8d
0x18001236f  mov     [rsp+60h+ulFlags], r14d; ULONG
0x180012374  call    FSSaveGlobalConfigurationByName
0x180012379  cmp     cs:byte_18005E5A5, 8
0x180012380  jb      loc_180012477
0x180012386  mov     rcx, cs:WPP_GLOBAL_Control
0x18001238d  mov     edx, 142h
0x180012392  mov     r9, rsi
0x180012395  mov     [rsp+60h+ulFlags], r14d
0x18001239a  mov     r8, r15
0x18001239d  mov     rcx, [rcx+0D8h]
0x1800123a4  call    WPP_SF_qD
0x1800123a9  jmp     loc_180012477
0x1800123ae  mov     rcx, [rbp+arg_18]
0x1800123b2  lea     r8, [rbp+arg_10]
0x1800123b6  lea     rdx, [rbp+var_28]
0x1800123ba  mov     rax, [rcx]
0x1800123bd  mov     rax, [rax+28h]
0x1800123c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123c6  test    eax, eax
0x1800123c8  jns     short loc_1800123E1
0x1800123ca  cmp     cs:byte_18005E5A5, 1
0x1800123d1  jb      loc_180012335
0x1800123d7  mov     edx, 143h
0x1800123dc  jmp     loc_180012318
0x1800123e1  mov     r9, [rbp+var_28]
0x1800123e5  test    r9, r9
0x1800123e8  jz      short loc_18001241A
0x1800123ea  mov     eax, [rbp+arg_10]
0x1800123ed  test    eax, eax
0x1800123ef  jz      short loc_18001241A
0x1800123f1  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800123f5  mov     r8d, 1003h
0x1800123fb  mov     [rsp+60h+ulFlags], eax; ULONG
0x1800123ff  call    FSSaveGlobalConfigurationByName
0x180012404  mov     edi, eax
0x180012406  test    eax, eax
0x180012408  jns     short loc_180012462
0x18001240a  cmp     cs:byte_18005E5A5, 1
0x180012411  jb      short loc_18001245F
0x180012413  mov     edx, 145h
0x180012418  jmp     short loc_180012442
0x18001241a  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18001241e  xor     r9d, r9d
0x180012421  xor     r8d, r8d
0x180012424  mov     [rsp+60h+ulFlags], r14d; ULONG
0x180012429  call    FSSaveGlobalConfigurationByName
0x18001242e  mov     edi, eax
0x180012430  test    eax, eax
0x180012432  jns     short loc_180012462
0x180012434  cmp     cs:byte_18005E5A5, 8
0x18001243b  jb      short loc_18001245F
0x18001243d  mov     edx, 144h
0x180012442  mov     rcx, cs:WPP_GLOBAL_Control
0x180012449  mov     r9, rsi
0x18001244c  mov     r8, r15
0x18001244f  mov     [rsp+60h+ulFlags], eax
0x180012453  mov     rcx, [rcx+0D8h]
0x18001245a  call    WPP_SF_qD
0x18001245f  mov     edi, r14d
0x180012462  mov     rcx, [rbp+arg_18]
0x180012466  test    rcx, rcx
0x180012469  jz      short loc_180012477
0x18001246b  mov     rax, [rcx]
0x18001246e  mov     rax, [rax+30h]
0x180012472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012477  lea     rcx, [rbp+phkDeviceInterface]
0x18001247b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012480  lea     rcx, [rbp+arg_18]
0x180012484  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180012489  mov     rbx, [rbx]
0x18001248c  jmp     loc_18001218C
0x180012491  test    edi, edi
0x180012493  jns     short loc_1800124A5
0x180012495  cmp     cs:byte_18005E5A5, 1
0x18001249c  jb      short loc_1800124D0
0x18001249e  mov     edx, 146h
0x1800124a3  jmp     short loc_1800124B3
0x1800124a5  cmp     cs:byte_18005E5A5, 8
0x1800124ac  jb      short loc_1800124D0
0x1800124ae  mov     edx, 147h
0x1800124b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124ba  mov     r9, rsi
0x1800124bd  mov     r8, r15
0x1800124c0  mov     [rsp+60h+ulFlags], edi
0x1800124c4  mov     rcx, [rcx+0D8h]
0x1800124cb  call    WPP_SF_qD
0x1800124d0  lea     rcx, [rbp+var_20]
0x1800124d4  call    ?clear@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAAXXZ; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::clear(void)
0x1800124d9  mov     rbx, [rsp+60h+arg_0]
0x1800124e1  add     rsp, 60h
0x1800124e5  pop     r15
0x1800124e7  pop     r14
0x1800124e9  pop     rdi
0x1800124ea  pop     rsi
0x1800124eb  pop     rbp
0x1800124ec  retn
```
