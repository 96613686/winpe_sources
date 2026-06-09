# CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint::CDPEndpoint(CDPComEndpoint *,unsigned __int64)

- ea: `0x180035b18`
- end: `0x180035e18`
- name: `??0CDPEndpoint@CDPDeviceInfo@CDPComDeviceQuery@@QEAA@PEAUCDPComEndpoint@@_K@Z`
- size: `768`
- prototype: `CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint *__fastcall(CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint *this, const char **, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180034e3c`

## callees

- `0x180003e60`
- `0x18000c2e8`
- `0x18000c914`
- `0x180010c7c`
- `0x180018264`
- `0x180027ab8`
- `0x18002bbec`
- `0x1800322f4`
- `0x180034cd8`
- `0x180034ddc`
- `0x180034e9c`
- `0x180035b18`
- `0x180038de0`
- `0x180038e94`

## import_xrefs

- `cdp!CDPCreateAccountInternalForUser` at `0x180035c68`
- `cdp!CDPCreateAccountInternalForUser` at `0x180035d31`
- `cdp!CDPCreateAccountInternalForUser` at `0x180035c68`
- `cdp!CDPCreateAccountInternalForUser` at `0x180035d31`

## string_xrefs

- `0x180035db4`: `.\cdpcomdevicequery.cpp`
- `0x180035ded`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint *__fastcall CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint::CDPEndpoint(
        CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint *this,
        const char **a2,
        __int64 a3)
{
  const char *v6; // rsi
  const char *v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // r8
  const char *v10; // rsi
  int v11; // ebx
  const char *v12; // rdi
  const char *v14; // rdi
  const char *v15; // rsi
  int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  std::_Ref_count_base *v20[2]; // [rsp+20h] [rbp-78h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+30h] [rbp-68h] BYREF
  char v22[8]; // [rsp+40h] [rbp-58h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-50h]
  _BYTE v24[32]; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int64 v26; // [rsp+A8h] [rbp+10h] BYREF

  *(_QWORD *)this = &cdp::unknown<ICDPEndpoint,>::`vftable';
  *((_DWORD *)this + 2) = 1;
  std::make_shared<cdp::detail::weak_ref_control_block,>((char *)this + 16);
  *(_QWORD *)this = &CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint::`vftable';
  std::string::string((char *)this + 32);
  std::string::string((char *)this + 64);
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  v6 = qword_180076D60;
  v7 = qword_180076D60;
  if ( *a2 )
    v7 = *a2;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v7[v9] );
  std::string::_Assign<char>((char *)this + 32);
  if ( a2[1] )
    v6 = a2[1];
  do
    ++v8;
  while ( v6[v8] );
  std::string::_Assign<char>((char *)this + 64);
  *((_WORD *)this + 64) = *((_WORD *)a2 + 17);
  *((_DWORD *)this + 24) = *((_DWORD *)a2 + 4);
  v26 = *((unsigned __int16 *)a2 + 16);
  if ( v26 > (__int64)(*((_QWORD *)this + 15) - *((_QWORD *)this + 13)) >> 4 )
    std::vector<std::shared_ptr<ICDPEndpoint>>::_Reallocate<0>((char *)this + 104, &v26);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CDPAccessviolation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_CDPAccessviolation>::GetImpl'::`2'::impl) )
  {
    try
    {
      v12 = a2[3];
      v10 = &v12[16 * *((unsigned __int16 *)a2 + 16)];
      while ( v12 != v10 )
      {
        *(_OWORD *)v21 = 0;
        v20[0] = 0;
        v20[1] = (std::_Ref_count_base *)v21;
        v11 = CDPCreateAccountInternalForUser(*(_QWORD *)v12, *((unsigned __int16 *)v12 + 4), a3, v20);
        cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(v20);
        if ( v11 < 0 )
        {
          std::vector<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>::clear((char *)this + 104);
          cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(
            (cdp::CDPSourceLocationInfo *)v20,
            ".\\cdpcomdevicequery.cpp",
            651);
          v18 = cdp::MakeException<std::runtime_error,>(v24);
          cdp::CdpThrow<std::runtime_error>(v20, v18);
        }
        LOBYTE(v26) = 0;
        cdp::MakeShared<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount,std::shared_ptr<ICDPAccount> &,bool>(
          v22,
          v21,
          &v26);
        std::vector<std::shared_ptr<ICDPAccount>>::emplace_back<std::shared_ptr<ICDPAccount> &>((char *)this + 104, v22);
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
        if ( v21[1] )
          std::_Ref_count_base::_Decref(v21[1]);
        v12 += 16;
      }
    }
    catch ( ... )
    {
      std::vector<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>::clear((char *)this + 104);
      cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(
        (cdp::CDPSourceLocationInfo *)v22,
        ".\\cdpcomdevicequery.cpp",
        662);
      v19 = cdp::MakeException<std::invalid_argument,>((std::exception *)v24);
      cdp::CdpThrow<std::invalid_argument>(v22, v19);
    }
  }
  else
  {
    v14 = a2[3];
    v15 = &v14[16 * *((unsigned __int16 *)a2 + 16)];
    while ( v14 != v15 )
    {
      *(_OWORD *)v20 = 0;
      v21[0] = 0;
      v21[1] = (std::_Ref_count_base *)v20;
      v16 = CDPCreateAccountInternalForUser(*(_QWORD *)v14, *((unsigned __int16 *)v14 + 4), a3, v21);
      cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(v21);
      if ( v16 < 0 )
      {
        std::vector<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>::clear((char *)this + 104);
        cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(
          (cdp::CDPSourceLocationInfo *)v22,
          ".\\cdpcomdevicequery.cpp",
          674);
        v17 = cdp::MakeException<std::runtime_error,>(v24);
        cdp::CdpThrow<std::runtime_error>(v22, v17);
      }
      LOBYTE(v26) = 0;
      cdp::MakeShared<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount,std::shared_ptr<ICDPAccount> &,bool>(
        v22,
        v20,
        &v26);
      std::vector<std::shared_ptr<ICDPAccount>>::emplace_back<std::shared_ptr<ICDPAccount> &>((char *)this + 104, v22);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
      if ( v20[1] )
        std::_Ref_count_base::_Decref(v20[1]);
      v14 += 16;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180035b18  mov     [rsp+arg_10], rbx
0x180035b1d  mov     [rsp+arg_18], rsi
0x180035b22  mov     [rsp+arg_0], rcx
0x180035b27  push    rdi
0x180035b28  push    r12
0x180035b2a  push    r13
0x180035b2c  push    r14
0x180035b2e  push    r15
0x180035b30  sub     rsp, 70h
0x180035b34  mov     r13, r8
0x180035b37  mov     rbx, rdx
0x180035b3a  mov     r14, rcx
0x180035b3d  lea     rax, ??_7?$unknown@VICDPEndpoint@@$$V@cdp@@6B@; const cdp::unknown<ICDPEndpoint,>::`vftable'
0x180035b44  mov     [rcx], rax
0x180035b47  mov     dword ptr [rcx+8], 1
0x180035b4e  add     rcx, 10h
0x180035b52  call    ??$make_shared@Uweak_ref_control_block@detail@cdp@@$$V@std@@YA?AV?$shared_ptr@Uweak_ref_control_block@detail@cdp@@@0@XZ; std::make_shared<cdp::detail::weak_ref_control_block,>(void)
0x180035b57  nop
0x180035b58  lea     rax, ??_7CDPEndpoint@CDPDeviceInfo@CDPComDeviceQuery@@6B@; const CDPComDeviceQuery::CDPDeviceInfo::CDPEndpoint::`vftable'
0x180035b5f  mov     [r14], rax
0x180035b62  lea     rcx, [r14+20h]
0x180035b66  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180035b6b  nop
0x180035b6c  lea     rcx, [r14+40h]
0x180035b70  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180035b75  nop
0x180035b76  lea     r15, [r14+68h]
0x180035b7a  xor     eax, eax
0x180035b7c  mov     [r15], rax
0x180035b7f  mov     [r15+8], rax
0x180035b83  mov     [r15+10h], rax
0x180035b87  lea     rsi, qword_180076D60
0x180035b8e  mov     rdx, rsi
0x180035b91  cmp     [rbx], rax
0x180035b94  cmovnz  rdx, [rbx]
0x180035b98  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180035b9c  mov     r8, rdi
0x180035b9f  inc     r8
0x180035ba2  cmp     [rdx+r8], al
0x180035ba6  jnz     short loc_180035B9F
0x180035ba8  lea     rcx, [r14+20h]
0x180035bac  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180035bb1  cmp     qword ptr [rbx+8], 0
0x180035bb6  cmovnz  rsi, [rbx+8]
0x180035bbb  inc     rdi
0x180035bbe  cmp     byte ptr [rsi+rdi], 0
0x180035bc2  jnz     short loc_180035BBB
0x180035bc4  mov     r8, rdi
0x180035bc7  mov     rdx, rsi
0x180035bca  lea     rcx, [r14+40h]
0x180035bce  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180035bd3  movzx   eax, word ptr [rbx+22h]
0x180035bd7  mov     [r14+80h], ax
0x180035bdf  mov     eax, [rbx+10h]
0x180035be2  mov     [r14+60h], eax
0x180035be6  movzx   ecx, word ptr [rbx+20h]
0x180035bea  mov     [rsp+98h+arg_8], rcx
0x180035bf2  mov     rax, [r15+10h]
0x180035bf6  sub     rax, [r15]
0x180035bf9  sar     rax, 4
0x180035bfd  cmp     rcx, rax
0x180035c00  jbe     short loc_180035C12
0x180035c02  lea     rdx, [rsp+98h+arg_8]
0x180035c0a  mov     rcx, r15
0x180035c0d  call    ??$_Reallocate@$0A@@?$vector@V?$shared_ptr@VICDPEndpoint@@@std@@V?$allocator@V?$shared_ptr@VICDPEndpoint@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::shared_ptr<ICDPEndpoint>>::_Reallocate<0>(unsigned __int64 &)
0x180035c12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_CDPAccessviolation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CDPAccessviolation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CDPAccessviolation> `wil::Feature<__WilFeatureTraits_Feature_Servicing_CDPAccessviolation>::GetImpl(void)'::`2'::impl
0x180035c19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CDPAccessviolation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CDPAccessviolation>::__private_IsEnabled(void)
0x180035c1e  xor     r12d, r12d
0x180035c21  test    al, al
0x180035c23  jz      loc_180035CF6
0x180035c29  mov     rdi, [rbx+18h]
0x180035c2d  movzx   esi, word ptr [rbx+20h]
0x180035c31  shl     rsi, 4
0x180035c35  add     rsi, rdi
0x180035c38  cmp     rdi, rsi
0x180035c3b  jz      loc_180035CD9
0x180035c41  xorps   xmm0, xmm0
0x180035c44  movdqu  xmmword ptr [rsp+98h+var_68], xmm0
0x180035c4a  mov     [rsp+98h+var_78], r12
0x180035c4f  lea     rax, [rsp+98h+var_68]
0x180035c54  mov     [rsp+98h+var_78+8], rax
0x180035c59  lea     r9, [rsp+98h+var_78]
0x180035c5e  mov     r8, r13
0x180035c61  movzx   edx, word ptr [rdi+8]
0x180035c65  mov     rcx, [rdi]
0x180035c68  call    cs:__imp_CDPCreateAccountInternalForUser
0x180035c6e  mov     ebx, eax
0x180035c70  lea     rcx, [rsp+98h+var_78]
0x180035c75  call    ??1?$address_of@VICDPAccount@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(void)
0x180035c7a  test    ebx, ebx
0x180035c7c  js      loc_180035DDE
0x180035c82  mov     byte ptr [rsp+98h+arg_8], r12b
0x180035c8a  lea     r8, [rsp+98h+arg_8]
0x180035c92  lea     rdx, [rsp+98h+var_68]
0x180035c97  lea     rcx, [rsp+98h+var_58]
0x180035c9c  call    ??$MakeShared@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@AEAV?$shared_ptr@VICDPAccount@@@std@@_N@cdp@@YA?AV?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@AEAV?$shared_ptr@VICDPAccount@@@2@$$QEA_N@Z; cdp::MakeShared<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount,std::shared_ptr<ICDPAccount> &,bool>(std::shared_ptr<ICDPAccount> &,bool &&)
0x180035ca1  nop
0x180035ca2  lea     rcx, [r14+68h]
0x180035ca6  lea     rdx, [rsp+98h+var_58]
0x180035cab  call    ??$emplace_back@AEAV?$shared_ptr@VICDPAccount@@@std@@@?$vector@V?$shared_ptr@VICDPAccount@@@std@@V?$allocator@V?$shared_ptr@VICDPAccount@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VICDPAccount@@@1@AEAV21@@Z; std::vector<std::shared_ptr<ICDPAccount>>::emplace_back<std::shared_ptr<ICDPAccount> &>(std::shared_ptr<ICDPAccount> &)
0x180035cb0  nop
0x180035cb1  mov     rcx, [rsp+98h+var_50]; this
0x180035cb6  test    rcx, rcx
0x180035cb9  jz      short loc_180035CC1
0x180035cbb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035cc0  nop
0x180035cc1  mov     rcx, [rsp+98h+var_68+8]; this
0x180035cc6  test    rcx, rcx
0x180035cc9  jz      short loc_180035CD0
0x180035ccb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035cd0  add     rdi, 10h
0x180035cd4  jmp     loc_180035C38
0x180035cd9  mov     rax, r14
0x180035cdc  lea     r11, [rsp+98h+var_28]
0x180035ce1  mov     rbx, [r11+40h]
0x180035ce5  mov     rsi, [r11+48h]
0x180035ce9  mov     rsp, r11
0x180035cec  pop     r15
0x180035cee  pop     r14
0x180035cf0  pop     r13
0x180035cf2  pop     r12
0x180035cf4  pop     rdi
0x180035cf5  retn
0x180035cf6  mov     rdi, [rbx+18h]
0x180035cfa  movzx   esi, word ptr [rbx+20h]
0x180035cfe  shl     rsi, 4
0x180035d02  add     rsi, rdi
0x180035d05  jmp     loc_180035D98
0x180035d0a  xorps   xmm0, xmm0
0x180035d0d  movdqu  xmmword ptr [rsp+98h+var_78], xmm0
0x180035d13  mov     [rsp+98h+var_68], r12
0x180035d18  lea     rax, [rsp+98h+var_78]
0x180035d1d  mov     [rsp+98h+var_68+8], rax
0x180035d22  lea     r9, [rsp+98h+var_68]
0x180035d27  mov     r8, r13
0x180035d2a  movzx   edx, word ptr [rdi+8]
0x180035d2e  mov     rcx, [rdi]
0x180035d31  call    cs:__imp_CDPCreateAccountInternalForUser
0x180035d37  mov     ebx, eax
0x180035d39  lea     rcx, [rsp+98h+var_68]
0x180035d3e  call    ??1?$address_of@VICDPAccount@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(void)
0x180035d43  test    ebx, ebx
0x180035d45  js      short loc_180035DA6
0x180035d47  mov     byte ptr [rsp+98h+arg_8], r12b
0x180035d4f  lea     r8, [rsp+98h+arg_8]
0x180035d57  lea     rdx, [rsp+98h+var_78]
0x180035d5c  lea     rcx, [rsp+98h+var_58]
0x180035d61  call    ??$MakeShared@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@AEAV?$shared_ptr@VICDPAccount@@@std@@_N@cdp@@YA?AV?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@AEAV?$shared_ptr@VICDPAccount@@@2@$$QEA_N@Z; cdp::MakeShared<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount,std::shared_ptr<ICDPAccount> &,bool>(std::shared_ptr<ICDPAccount> &,bool &&)
0x180035d66  nop
0x180035d67  lea     rdx, [rsp+98h+var_58]
0x180035d6c  mov     rcx, r15
0x180035d6f  call    ??$emplace_back@AEAV?$shared_ptr@VICDPAccount@@@std@@@?$vector@V?$shared_ptr@VICDPAccount@@@std@@V?$allocator@V?$shared_ptr@VICDPAccount@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VICDPAccount@@@1@AEAV21@@Z; std::vector<std::shared_ptr<ICDPAccount>>::emplace_back<std::shared_ptr<ICDPAccount> &>(std::shared_ptr<ICDPAccount> &)
0x180035d74  nop
0x180035d75  mov     rcx, [rsp+98h+var_50]; this
0x180035d7a  test    rcx, rcx
0x180035d7d  jz      short loc_180035D85
0x180035d7f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035d84  nop
0x180035d85  mov     rcx, [rsp+98h+var_78+8]; this
0x180035d8a  test    rcx, rcx
0x180035d8d  jz      short loc_180035D94
0x180035d8f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035d94  add     rdi, 10h
0x180035d98  cmp     rdi, rsi
0x180035d9b  jnz     loc_180035D0A
0x180035da1  jmp     loc_180035CD9
0x180035da6  mov     rcx, r15
0x180035da9  call    ?clear@?$vector@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@V?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>::clear(void)
0x180035dae  mov     r8d, 2A2h; int
0x180035db4  lea     rdx, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180035dbb  lea     rcx, [rsp+98h+var_58]; this
0x180035dc0  call    ??0CDPSourceLocationInfo@cdp@@QEAA@PEBDH@Z; cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(char const *,int)
0x180035dc5  lea     rcx, [rsp+98h+var_48]
0x180035dca  call    ??$MakeException@Vruntime_error@std@@$$V@cdp@@YA?AVruntime_error@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::runtime_error,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180035dcf  nop
0x180035dd0  mov     rdx, rax
0x180035dd3  lea     rcx, [rsp+98h+var_58]
0x180035dd8  call    ??$CdpThrow@Vruntime_error@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVruntime_error@std@@@Z; cdp::CdpThrow<std::runtime_error>(cdp::CDPSourceLocationInfo const &,std::runtime_error &&)
0x180035dde  lea     rcx, [r14+68h]
0x180035de2  call    ?clear@?$vector@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@V?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>::clear(void)
0x180035de7  mov     r8d, 28Bh; int
0x180035ded  lea     rdx, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x180035df4  lea     rcx, [rsp+98h+var_78]; this
0x180035df9  call    ??0CDPSourceLocationInfo@cdp@@QEAA@PEBDH@Z; cdp::CDPSourceLocationInfo::CDPSourceLocationInfo(char const *,int)
0x180035dfe  lea     rcx, [rsp+98h+var_48]
0x180035e03  call    ??$MakeException@Vruntime_error@std@@$$V@cdp@@YA?AVruntime_error@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::runtime_error,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180035e08  nop
0x180035e09  mov     rdx, rax
0x180035e0c  lea     rcx, [rsp+98h+var_78]
0x180035e11  call    ??$CdpThrow@Vruntime_error@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVruntime_error@std@@@Z; cdp::CdpThrow<std::runtime_error>(cdp::CDPSourceLocationInfo const &,std::runtime_error &&)
```
