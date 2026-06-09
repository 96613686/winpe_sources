# ComDedupedDeviceQueryParametersToCDPDedupedDeviceQueryParameters

- ea: `0x1800125fc`
- end: `0x180012a2b`
- name: `ComDedupedDeviceQueryParametersToCDPDedupedDeviceQueryParameters`
- size: `1071`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18001bb30`

## callees

- `0x180003e60`
- `0x180010c7c`
- `0x180010cc0`
- `0x1800125fc`
- `0x1800130ec`
- `0x1800179f0`
- `0x180018264`
- `0x18001a5b4`
- `0x180026850`
- `0x180030d4c`
- `0x18003214c`
- `0x1800322f4`
- `0x180042b4c`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateAccountInternalForUser` at `0x1800126db`
- `cdp!CDPCreateAccountInternalForUser` at `0x1800126db`
- `cdp!CDPCreateDedupedDeviceQueryParameters` at `0x180012783`
- `cdp!CDPCreateDedupedDeviceQueryParameters` at `0x180012783`

## string_xrefs

- `0x180012626`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180012654`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x18001271b`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800127a4`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800128d1`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800129a0`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ComDedupedDeviceQueryParametersToCDPDedupedDeviceQueryParameters(
        unsigned int *a1,
        unsigned __int64 *a2)
{
  unsigned int v4; // ebx
  int CurrentUserContextToken; // eax
  int v7; // edi
  __int64 v8; // rdi
  __int64 v9; // rsi
  int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int v16; // eax
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  _QWORD *v19; // rdx
  int v20; // eax
  std::_Ref_count_base *v21[2]; // [rsp+20h] [rbp-50h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v23; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+50h] [rbp-20h]
  _QWORD *v25; // [rsp+58h] [rbp-18h] BYREF
  _QWORD *v26; // [rsp+60h] [rbp-10h]
  __int64 v27; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned __int64 v29; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v30; // [rsp+B0h] [rbp+40h] BYREF

  if ( !a2 )
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B9,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      (int)v21[0]);
    return v4;
  }
  CurrentUserContextToken = cdp::GetCurrentUserContextToken((cdp *)&v30, a2);
  v7 = CurrentUserContextToken;
  if ( CurrentUserContextToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)CurrentUserContextToken,
      (int)v21[0]);
    return (unsigned int)v7;
  }
  std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(&v25);
  v29 = *((unsigned __int16 *)a1 + 12);
  if ( v29 > (v27 - (__int64)v25) >> 4 )
    std::vector<std::shared_ptr<ICDPEndpoint>>::_Reallocate<0>(&v25, &v29);
  v8 = *((_QWORD *)a1 + 2);
  v9 = v8 + 16LL * *((unsigned __int16 *)a1 + 12);
  while ( v8 != v9 )
  {
    *(_OWORD *)v22 = 0;
    *(_QWORD *)&v23 = 0;
    *((_QWORD *)&v23 + 1) = v22;
    v10 = CDPCreateAccountInternalForUser(*(_QWORD *)v8, *(unsigned __int16 *)(v8 + 8), v30, &v23);
    cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(&v23);
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C3,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v10,
        (int)v21[0]);
      if ( v22[1] )
        std::_Ref_count_base::_Decref(v22[1]);
      if ( v25 )
      {
        std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(
          (__int64)v25,
          (__int64)v26);
        std::_Deallocate<16>(v25, (v27 - (_QWORD)v25) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      return (unsigned int)v10;
    }
    std::vector<std::shared_ptr<ICDPAccount>>::emplace_back<std::shared_ptr<ICDPAccount> &>(&v25, v22);
    if ( v22[1] )
      std::_Ref_count_base::_Decref(v22[1]);
    v8 += 16;
  }
  *(_OWORD *)v21 = 0;
  *(_QWORD *)&v23 = 0;
  *((_QWORD *)&v23 + 1) = v21;
  v7 = CDPCreateDedupedDeviceQueryParameters(&v23);
  cdp::detail::address_of<ICDPDedupedDeviceQueryParameters>::~address_of<ICDPDedupedDeviceQueryParameters>(&v23);
  if ( v7 < 0 )
  {
    v11 = 968;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v7,
      (int)v21[0]);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    if ( v25 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(
        (__int64)v25,
        (__int64)v26);
      std::_Deallocate<16>(v25, (v27 - (_QWORD)v25) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return (unsigned int)v7;
  }
  v7 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v21[0] + 48LL))(v21[0], *a1);
  if ( v7 < 0 )
  {
    v11 = 970;
    goto LABEL_22;
  }
  LOBYTE(v12) = a1[1] != 0;
  v7 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v21[0] + 64LL))(v21[0], v12);
  if ( v7 < 0 )
  {
    v11 = 971;
    goto LABEL_22;
  }
  LOBYTE(v13) = a1[2] != 0;
  v7 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v21[0] + 80LL))(v21[0], v13);
  if ( v7 < 0 )
  {
    v11 = 972;
    goto LABEL_22;
  }
  LOBYTE(v14) = a1[3] != 0;
  v7 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v21[0] + 112LL))(v21[0], v14);
  if ( v7 < 0 )
  {
    v11 = 973;
    goto LABEL_22;
  }
  LOBYTE(v15) = a1[7] != 0;
  v7 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v21[0] + 136LL))(v21[0], v15);
  if ( v7 < 0 )
  {
    v11 = 974;
    goto LABEL_22;
  }
  v16 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v21[0] + 152LL))(
          v21[0],
          *((_QWORD *)a1 + 4));
  v4 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CF,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)(unsigned int)v16,
      (int)v21[0]);
LABEL_38:
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    if ( v25 )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(
        (__int64)v25,
        (__int64)v26);
      std::_Deallocate<16>(v25, (v27 - (_QWORD)v25) & 0xFFFFFFFFFFFFFFF0uLL);
    }
    return v4;
  }
  if ( ((char *)v26 - (char *)v25) >> 4 )
  {
    v23 = 0;
    v24 = 0;
    std::vector<ICDPAccount *>::_Construct_n<>(&v23);
    v17 = v25;
    v18 = v26;
    v19 = (_QWORD *)v23;
    if ( v25 != v26 )
    {
      do
      {
        *v19 = *v17;
        v17 += 2;
        ++v19;
      }
      while ( v17 != v18 );
      v19 = (_QWORD *)v23;
    }
    v20 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD *, __int64))(*(_QWORD *)v21[0] + 96LL))(
            v21[0],
            v19,
            (__int64)(*((_QWORD *)&v23 + 1) - (_QWORD)v19) >> 3);
    v4 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D8,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v20,
        (int)v21[0]);
      std::vector<ICDPAccount *>::_Tidy(&v23);
      goto LABEL_38;
    }
    std::vector<ICDPAccount *>::_Tidy(&v23);
  }
  (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v21[0] + 8LL))(v21[0]);
  *a2 = (unsigned __int64)v21[0];
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  if ( v25 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(
      (__int64)v25,
      (__int64)v26);
    std::_Deallocate<16>(v25, (v27 - (_QWORD)v25) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x1800125fc  mov     [rsp-28h+arg_0], rbx
0x180012601  push    rbp
0x180012602  push    rsi
0x180012603  push    rdi
0x180012604  push    r14
0x180012606  push    r15
0x180012608  mov     rbp, rsp
0x18001260b  sub     rsp, 70h
0x18001260f  mov     r15, rdx
0x180012612  mov     rbx, rcx
0x180012615  test    rdx, rdx
0x180012618  jnz     short loc_18001263E
0x18001261a  mov     rcx, [rbp+28h]; this
0x18001261e  mov     ebx, 80004003h
0x180012623  mov     r9d, ebx; char *
0x180012626  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18001262d  mov     edx, 3B9h; void *
0x180012632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012637  mov     eax, ebx
0x180012639  jmp     loc_180012A17
0x18001263e  lea     rcx, [rbp+arg_10]; this
0x180012642  call    ?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z; cdp::GetCurrentUserContextToken(unsigned __int64 &)
0x180012647  mov     edi, eax
0x180012649  test    eax, eax
0x18001264b  jns     short loc_18001266C
0x18001264d  mov     rcx, [rbp+28h]; this
0x180012651  mov     r9d, eax; char *
0x180012654  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18001265b  mov     edx, 3BCh; void *
0x180012660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012665  mov     eax, edi
0x180012667  jmp     loc_180012A17
0x18001266c  lea     rcx, [rbp+var_18]
0x180012670  call    ??0?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@QEAA@XZ; std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(void)
0x180012675  nop
0x180012676  movzx   ecx, word ptr [rbx+18h]
0x18001267a  mov     [rbp+arg_8], rcx
0x18001267e  mov     rax, [rbp+var_8]
0x180012682  sub     rax, [rbp+var_18]
0x180012686  sar     rax, 4
0x18001268a  cmp     rcx, rax
0x18001268d  jbe     short loc_18001269C
0x18001268f  lea     rdx, [rbp+arg_8]
0x180012693  lea     rcx, [rbp+var_18]
0x180012697  call    ??$_Reallocate@$0A@@?$vector@V?$shared_ptr@VICDPEndpoint@@@std@@V?$allocator@V?$shared_ptr@VICDPEndpoint@@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::shared_ptr<ICDPEndpoint>>::_Reallocate<0>(unsigned __int64 &)
0x18001269c  mov     rdi, [rbx+10h]
0x1800126a0  movzx   esi, word ptr [rbx+18h]
0x1800126a4  shl     rsi, 4
0x1800126a8  add     rsi, rdi
0x1800126ab  xorps   xmm0, xmm0
0x1800126ae  cmp     rdi, rsi
0x1800126b1  jz      loc_18001276A
0x1800126b7  movdqu  xmmword ptr [rbp+var_40], xmm0
0x1800126bc  mov     qword ptr [rbp+var_30], 0
0x1800126c4  lea     rax, [rbp+var_40]
0x1800126c8  mov     qword ptr [rbp+var_30+8], rax
0x1800126cc  lea     r9, [rbp+var_30]
0x1800126d0  mov     r8, [rbp+arg_10]
0x1800126d4  movzx   edx, word ptr [rdi+8]
0x1800126d8  mov     rcx, [rdi]
0x1800126db  call    cs:__imp_CDPCreateAccountInternalForUser
0x1800126e1  mov     r14d, eax
0x1800126e4  lea     rcx, [rbp+var_30]
0x1800126e8  call    ??1?$address_of@VICDPAccount@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAccount>::~address_of<ICDPAccount>(void)
0x1800126ed  test    r14d, r14d
0x1800126f0  js      short loc_180012714
0x1800126f2  lea     rdx, [rbp+var_40]
0x1800126f6  lea     rcx, [rbp+var_18]
0x1800126fa  call    ??$emplace_back@AEAV?$shared_ptr@VICDPAccount@@@std@@@?$vector@V?$shared_ptr@VICDPAccount@@@std@@V?$allocator@V?$shared_ptr@VICDPAccount@@@std@@@2@@std@@QEAAAEAV?$shared_ptr@VICDPAccount@@@1@AEAV21@@Z; std::vector<std::shared_ptr<ICDPAccount>>::emplace_back<std::shared_ptr<ICDPAccount> &>(std::shared_ptr<ICDPAccount> &)
0x1800126ff  nop
0x180012700  mov     rcx, [rbp+var_40+8]; this
0x180012704  test    rcx, rcx
0x180012707  jz      short loc_18001270E
0x180012709  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001270e  add     rdi, 10h
0x180012712  jmp     short loc_1800126AB
0x180012714  mov     rcx, [rbp+28h]; this
0x180012718  mov     r9d, r14d; char *
0x18001271b  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180012722  mov     edx, 3C3h; void *
0x180012727  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001272c  nop
0x18001272d  mov     rcx, [rbp+var_40+8]; this
0x180012731  test    rcx, rcx
0x180012734  jz      short loc_18001273C
0x180012736  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001273b  nop
0x18001273c  mov     rcx, [rbp+var_18]
0x180012740  test    rcx, rcx
0x180012743  jz      short loc_180012762
0x180012745  mov     rdx, [rbp+var_10]
0x180012749  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> *,std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> * const,std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>> &)
0x18001274e  mov     rcx, [rbp+var_18]
0x180012752  mov     rdx, [rbp+var_8]
0x180012756  sub     rdx, rcx
0x180012759  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001275d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012762  mov     eax, r14d
0x180012765  jmp     loc_180012A17
0x18001276a  movdqu  xmmword ptr [rbp+var_50], xmm0
0x18001276f  mov     qword ptr [rbp+var_30], 0
0x180012777  lea     rax, [rbp+var_50]
0x18001277b  mov     qword ptr [rbp+var_30+8], rax
0x18001277f  lea     rcx, [rbp+var_30]
0x180012783  call    cs:__imp_CDPCreateDedupedDeviceQueryParameters
0x180012789  mov     edi, eax
0x18001278b  lea     rcx, [rbp+var_30]
0x18001278f  call    ??1?$address_of@VICDPDedupedDeviceQueryParameters@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDedupedDeviceQueryParameters>::~address_of<ICDPDedupedDeviceQueryParameters>(void)
0x180012794  test    edi, edi
0x180012796  jns     short loc_1800127EF
0x180012798  mov     edx, 3C8h; void *
0x18001279d  mov     rcx, [rbp+28h]; this
0x1800127a1  mov     r9d, edi; char *
0x1800127a4  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800127ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127b0  nop
0x1800127b1  mov     rcx, [rbp+var_50+8]; this
0x1800127b5  test    rcx, rcx
0x1800127b8  jz      short loc_1800127C0
0x1800127ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800127bf  nop
0x1800127c0  mov     rcx, [rbp+var_18]
0x1800127c4  test    rcx, rcx
0x1800127c7  jz      loc_180012665
0x1800127cd  mov     rdx, [rbp+var_10]
0x1800127d1  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> *,std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> * const,std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>> &)
0x1800127d6  mov     rcx, [rbp+var_18]
0x1800127da  mov     rdx, [rbp+var_8]
0x1800127de  sub     rdx, rcx
0x1800127e1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800127e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800127ea  jmp     loc_180012665
0x1800127ef  mov     rcx, [rbp+var_50]
0x1800127f3  mov     rax, [rcx]
0x1800127f6  mov     edx, [rbx]
0x1800127f8  mov     rax, [rax+30h]
0x1800127fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012801  mov     edi, eax
0x180012803  test    eax, eax
0x180012805  jns     short loc_18001280E
0x180012807  mov     edx, 3CAh
0x18001280c  jmp     short loc_18001279D
0x18001280e  mov     rcx, [rbp+var_50]
0x180012812  mov     rax, [rcx]
0x180012815  cmp     dword ptr [rbx+4], 0
0x180012819  setnz   dl
0x18001281c  mov     rax, [rax+40h]
0x180012820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012825  mov     edi, eax
0x180012827  test    eax, eax
0x180012829  jns     short loc_180012835
0x18001282b  mov     edx, 3CBh
0x180012830  jmp     loc_18001279D
0x180012835  mov     rcx, [rbp+var_50]
0x180012839  mov     rax, [rcx]
0x18001283c  cmp     dword ptr [rbx+8], 0
0x180012840  setnz   dl
0x180012843  mov     rax, [rax+50h]
0x180012847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001284c  mov     edi, eax
0x18001284e  test    eax, eax
0x180012850  jns     short loc_18001285C
0x180012852  mov     edx, 3CCh
0x180012857  jmp     loc_18001279D
0x18001285c  mov     rcx, [rbp+var_50]
0x180012860  mov     rax, [rcx]
0x180012863  cmp     dword ptr [rbx+0Ch], 0
0x180012867  setnz   dl
0x18001286a  mov     rax, [rax+70h]
0x18001286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012873  mov     edi, eax
0x180012875  test    eax, eax
0x180012877  jns     short loc_180012883
0x180012879  mov     edx, 3CDh
0x18001287e  jmp     loc_18001279D
0x180012883  mov     rcx, [rbp+var_50]
0x180012887  mov     rax, [rcx]
0x18001288a  cmp     dword ptr [rbx+1Ch], 0
0x18001288e  setnz   dl
0x180012891  mov     rax, [rax+88h]
0x180012898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001289d  mov     edi, eax
0x18001289f  test    eax, eax
0x1800128a1  jns     short loc_1800128AD
0x1800128a3  mov     edx, 3CEh
0x1800128a8  jmp     loc_18001279D
0x1800128ad  mov     rcx, [rbp+var_50]
0x1800128b1  mov     rax, [rcx]
0x1800128b4  mov     rdx, [rbx+20h]
0x1800128b8  mov     rax, [rax+98h]
0x1800128bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128c4  mov     ebx, eax
0x1800128c6  test    eax, eax
0x1800128c8  jns     short loc_180012921
0x1800128ca  mov     rcx, [rbp+28h]; this
0x1800128ce  mov     r9d, eax; char *
0x1800128d1  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800128d8  mov     edx, 3CFh; void *
0x1800128dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128e2  nop
0x1800128e3  mov     rcx, [rbp+var_50+8]; this
0x1800128e7  test    rcx, rcx
0x1800128ea  jz      short loc_1800128F2
0x1800128ec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800128f1  nop
0x1800128f2  mov     rcx, [rbp+var_18]
0x1800128f6  test    rcx, rcx
0x1800128f9  jz      loc_180012637
0x1800128ff  mov     rdx, [rbp+var_10]
0x180012903  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> *,std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> * const,std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>> &)
0x180012908  mov     rcx, [rbp+var_18]
0x18001290c  mov     rdx, [rbp+var_8]
0x180012910  sub     rdx, rcx
0x180012913  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180012917  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001291c  jmp     loc_180012637
0x180012921  mov     rdx, [rbp+var_10]
0x180012925  sub     rdx, [rbp+var_18]
0x180012929  sar     rdx, 4
0x18001292d  test    rdx, rdx
0x180012930  jz      loc_1800129C9
0x180012936  xorps   xmm0, xmm0
0x180012939  movdqu  [rbp+var_30], xmm0
0x18001293e  mov     [rbp+var_20], 0
0x180012946  lea     rcx, [rbp+var_30]
0x18001294a  call    ??$_Construct_n@$$V@?$vector@PEAVICDPAccount@@V?$allocator@PEAVICDPAccount@@@std@@@std@@AEAAX_K@Z; std::vector<ICDPAccount *>::_Construct_n<>(unsigned __int64)
0x18001294f  nop
0x180012950  mov     rcx, [rbp+var_18]
0x180012954  mov     r8, [rbp+var_10]
0x180012958  mov     rdx, qword ptr [rbp+var_30]
0x18001295c  cmp     rcx, r8
0x18001295f  jz      short loc_180012978
0x180012961  mov     rax, [rcx]
0x180012964  mov     [rdx], rax
0x180012967  add     rcx, 10h
0x18001296b  lea     rdx, [rdx+8]
0x18001296f  cmp     rcx, r8
0x180012972  jnz     short loc_180012961
0x180012974  mov     rdx, qword ptr [rbp+var_30]
0x180012978  mov     rcx, [rbp+var_50]
0x18001297c  mov     rax, [rcx]
0x18001297f  mov     r8, qword ptr [rbp+var_30+8]
0x180012983  sub     r8, rdx
0x180012986  sar     r8, 3
0x18001298a  mov     rax, [rax+60h]
0x18001298e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012993  mov     ebx, eax
0x180012995  test    eax, eax
0x180012997  jns     short loc_1800129C0
0x180012999  mov     rcx, [rbp+28h]; this
0x18001299d  mov     r9d, eax; char *
0x1800129a0  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800129a7  mov     edx, 3D8h; void *
0x1800129ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129b1  nop
0x1800129b2  lea     rcx, [rbp+var_30]
0x1800129b6  call    ?_Tidy@?$vector@PEAVICDPAccount@@V?$allocator@PEAVICDPAccount@@@std@@@std@@AEAAXXZ; std::vector<ICDPAccount *>::_Tidy(void)
0x1800129bb  jmp     loc_1800128E3
0x1800129c0  lea     rcx, [rbp+var_30]
0x1800129c4  call    ?_Tidy@?$vector@PEAVICDPAccount@@V?$allocator@PEAVICDPAccount@@@std@@@std@@AEAAXXZ; std::vector<ICDPAccount *>::_Tidy(void)
0x1800129c9  mov     rcx, [rbp+var_50]
0x1800129cd  mov     rax, [rcx]
0x1800129d0  mov     rax, [rax+8]
0x1800129d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129d9  mov     rax, [rbp+var_50]
0x1800129dd  mov     [r15], rax
0x1800129e0  mov     rcx, [rbp+var_50+8]; this
0x1800129e4  test    rcx, rcx
0x1800129e7  jz      short loc_1800129EF
0x1800129e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800129ee  nop
0x1800129ef  mov     rcx, [rbp+var_18]
0x1800129f3  test    rcx, rcx
0x1800129f6  jz      short loc_180012A15
0x1800129f8  mov     rdx, [rbp+var_10]
0x1800129fc  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VCDPEndpointAccount@CDPDeviceInfo@CDPComDeviceQuery@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>>>(std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> *,std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount> * const,std::allocator<std::shared_ptr<CDPComDeviceQuery::CDPDeviceInfo::CDPEndpointAccount>> &)
0x180012a01  mov     rcx, [rbp+var_18]
0x180012a05  mov     rdx, [rbp+var_8]
0x180012a09  sub     rdx, rcx
0x180012a0c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180012a10  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012a15  xor     eax, eax
0x180012a17  mov     rbx, [rsp+70h+arg_0]
0x180012a1f  add     rsp, 70h
0x180012a23  pop     r15
0x180012a25  pop     r14
0x180012a27  pop     rdi
0x180012a28  pop     rsi
0x180012a29  pop     rbp
0x180012a2a  retn
```
