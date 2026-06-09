# CMulticastSessionManager::GetCompatibleMulticastProvider(std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>> &,IMulticastProvider * *)

- ea: `0x18011459c`
- end: `0x180114978`
- name: `?GetCompatibleMulticastProvider@CMulticastSessionManager@@AEAAJAEAV?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUIMulticastProvider@@@Z`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b5edc`

## callees

- `0x18000af70`
- `0x1800126bc`
- `0x1800ab014`
- `0x1800b18b4`
- `0x1800cf8c0`
- `0x1800eb744`
- `0x18011451c`
- `0x18011459c`
- `0x180114afc`
- `0x180142be0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18011464c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801146db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114819`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114836`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18011464c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801146db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114819`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114836`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801146a1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801146a1`

## string_xrefs

- `0x180114635`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x1801146b9`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x180114802`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x18011485d`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x1801148ac`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x1801148ff`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CMulticastSessionManager::GetCompatibleMulticastProvider(
        CMulticastSessionManager *a1,
        __int64 *a2,
        struct IMulticastProvider **a3)
{
  __int64 v5; // r15
  struct _GUID *v6; // rdi
  const struct _GUID *v7; // rbx
  __int64 v8; // rcx
  int PropertyStoreProperty; // eax
  unsigned int v10; // esi
  __int64 i; // rsi
  HRESULT v13; // eax
  unsigned int v14; // r14d
  struct _GUID *v15; // r9
  bool v16; // zf
  struct _GUID *j; // rdx
  struct _GUID *v18; // rdx
  int MulticastProvider; // eax
  unsigned int v20; // ebx
  struct IMulticastProvider *v21; // rbx
  struct IMulticastProvider *v22; // [rsp+20h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+28h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-90h]
  struct _GUID *v25[2]; // [rsp+40h] [rbp-88h] BYREF
  __int64 v26; // [rsp+50h] [rbp-78h]
  struct tagPROPVARIANT pvar; // [rsp+58h] [rbp-70h] BYREF
  CMulticastSessionManager *v28; // [rsp+70h] [rbp-58h]
  GUID pclsid; // [rsp+78h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v28 = a1;
  std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(v25);
  v5 = 0;
  v6 = v25[1];
  v7 = v25[0];
  while ( 1 )
  {
    v8 = *a2;
    if ( (unsigned int)v5 >= (unsigned __int64)((a2[1] - *a2) >> 3) )
      break;
    memset(&pvar, 0, sizeof(pvar));
    PropertyStoreProperty = CEndpointCharacteristics::GetPropertyStoreProperty(
                              *(CEndpointCharacteristics **)(v8 + 8 * v5),
                              &PKEY_Multicast_CompatibleProviders,
                              &pvar);
    v10 = PropertyStoreProperty;
    if ( PropertyStoreProperty < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\multicastsessionmanager.cpp",
        (const char *)(unsigned int)PropertyStoreProperty,
        (int)v22);
      PropVariantClear((PROPVARIANT *)&pvar);
      std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
      return v10;
    }
    if ( pvar.vt == 4127 )
    {
      std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(&v23);
      for ( i = 0; (unsigned int)i < pvar.lVal; i = (unsigned int)(i + 1) )
      {
        pclsid = 0;
        v13 = CLSIDFromString(*(LPCOLESTR *)&pvar.bstrblobVal.pData[8 * i], &pclsid);
        v14 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x193,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\multicastsessionmanager.cpp",
            (const char *)(unsigned int)v13,
            (int)v22);
          std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(&v23);
          PropVariantClear((PROPVARIANT *)&pvar);
          std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
          return v14;
        }
        if ( *((_QWORD *)&v23 + 1) == v24 )
        {
          std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(&v23, *((_QWORD *)&v23 + 1), &pclsid);
        }
        else
        {
          **((_OWORD **)&v23 + 1) = pclsid;
          *((_QWORD *)&v23 + 1) += 16LL;
        }
      }
      if ( (_DWORD)v5 )
      {
        *(_QWORD *)&pclsid.Data1 = &v23;
        v22 = (struct IMulticastProvider *)&v23;
        v15 = (struct _GUID *)v7;
        if ( v7 != v6 )
        {
          do
          {
            if ( (unsigned __int8)lambda_29cbe834aaff6b3962c1372fb6672b17_::operator()(&v22, v15) )
              break;
            ++v15;
          }
          while ( v15 != v6 );
        }
        v16 = v15 == v6;
        if ( v15 != v6 )
        {
          for ( j = v15 + 1; j != v6; j = v18 + 1 )
          {
            if ( !(unsigned __int8)lambda_29cbe834aaff6b3962c1372fb6672b17_::operator()(&pclsid, j) )
              *v15++ = *v18;
          }
          v16 = v15 == v6;
        }
        if ( !v16 )
          v6 = v15;
        v25[1] = v6;
      }
      else
      {
        std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
        *(_OWORD *)v25 = v23;
        v26 = v24;
        v23 = 0;
        v24 = 0;
        v6 = (struct _GUID *)_mm_srli_si128(*(__m128i *)v25, 8).m128i_u64[0];
        v7 = v25[0];
      }
      std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(&v23);
    }
    if ( v7 == v6 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\multicastsessionmanager.cpp",
        (const char *)0x80070490LL,
        (int)v22);
      PropVariantClear((PROPVARIANT *)&pvar);
      std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
      return 2147943568LL;
    }
    PropVariantClear((PROPVARIANT *)&pvar);
    v5 = (unsigned int)(v5 + 1);
  }
  if ( (char *)v6 - (char *)v7 == 16 )
  {
    v22 = 0;
    MulticastProvider = CMulticastSessionManager::GetMulticastProvider(v28, v7, &v22);
    v20 = MulticastProvider;
    if ( MulticastProvider >= 0 )
    {
      v21 = v22;
      if ( (*(unsigned __int8 (__fastcall **)(struct IMulticastProvider *))(*(_QWORD *)v22 + 24LL))(v22) )
      {
        v22 = 0;
        *a3 = v21;
        wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v22);
        std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\multicastsessionmanager.cpp",
          (const char *)0x80070490LL,
          (int)v22);
        wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v22);
        std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
        return 2147943568LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\multicastsessionmanager.cpp",
        (const char *)(unsigned int)MulticastProvider,
        (int)v22);
      wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v22);
      std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
      return v20;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\multicastsessionmanager.cpp",
      (const char *)0x80004001LL,
      (int)v22);
    std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(v25);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18011459c  push    rbx
0x18011459e  push    rsi
0x18011459f  push    rdi
0x1801145a0  push    r12
0x1801145a2  push    r13
0x1801145a4  push    r14
0x1801145a6  push    r15
0x1801145a8  sub     rsp, 90h
0x1801145af  mov     rax, cs:__security_cookie
0x1801145b6  xor     rax, rsp
0x1801145b9  mov     [rsp+0C8h+var_40], rax
0x1801145c1  mov     r13, r8
0x1801145c4  mov     r12, rdx
0x1801145c7  mov     [rsp+0C8h+var_58], rcx
0x1801145cc  lea     rcx, [rsp+0C8h+var_88]; void *
0x1801145d1  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x1801145d6  nop
0x1801145d7  xor     r15d, r15d
0x1801145da  mov     rdi, [rsp+0C8h+var_88+8]
0x1801145df  mov     rbx, [rsp+0C8h+var_88]
0x1801145e4  mov     rcx, [r12]
0x1801145e8  mov     r9d, r15d
0x1801145eb  mov     rax, [r12+8]
0x1801145f0  sub     rax, rcx
0x1801145f3  sar     rax, 3
0x1801145f7  cmp     r9, rax
0x1801145fa  jnb     loc_180114844
0x180114600  xorps   xmm0, xmm0
0x180114603  xor     eax, eax
0x180114605  movups  xmmword ptr [rsp+0C8h+pvar], xmm0
0x18011460a  mov     [rsp+0C8h+var_60], rax
0x18011460f  lea     r8, [rsp+0C8h+pvar]; struct tagPROPVARIANT *
0x180114614  lea     rdx, PKEY_Multicast_CompatibleProviders; struct _tagpropertykey *
0x18011461b  mov     rcx, [rcx+r15*8]; this
0x18011461f  call    ?GetPropertyStoreProperty@CEndpointCharacteristics@@QEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CEndpointCharacteristics::GetPropertyStoreProperty(_tagpropertykey const &,tagPROPVARIANT *)
0x180114624  mov     esi, eax
0x180114626  test    eax, eax
0x180114628  jns     short loc_180114664
0x18011462a  mov     rcx, [rsp+0C8h]; this
0x180114632  mov     r9d, eax; char *
0x180114635  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18011463c  mov     edx, 18Ch; void *
0x180114641  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114646  nop
0x180114647  lea     rcx, [rsp+0C8h+pvar]; pvar
0x18011464c  call    cs:__imp_PropVariantClear
0x180114652  nop
0x180114653  lea     rcx, [rsp+0C8h+var_88]
0x180114658  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18011465d  mov     eax, esi
0x18011465f  jmp     loc_180114954
0x180114664  mov     eax, 101Fh
0x180114669  cmp     word ptr [rsp+0C8h+pvar], ax
0x18011466e  jnz     loc_1801147ED
0x180114674  lea     rcx, [rsp+0C8h+var_A0]; void *
0x180114679  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x18011467e  nop
0x18011467f  xor     esi, esi
0x180114681  cmp     esi, dword ptr [rsp+0C8h+pvar+8]
0x180114685  jnb     loc_180114727
0x18011468b  xorps   xmm0, xmm0
0x18011468e  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x180114693  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x180114698  mov     rcx, [rsp+0C8h+var_60]
0x18011469d  mov     rcx, [rcx+rsi*8]; lpsz
0x1801146a1  call    cs:__imp_CLSIDFromString
0x1801146a7  mov     r14d, eax
0x1801146aa  test    eax, eax
0x1801146ac  jns     short loc_1801146F4
0x1801146ae  mov     rcx, [rsp+0C8h]; this
0x1801146b6  mov     r9d, eax; char *
0x1801146b9  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801146c0  mov     edx, 193h; void *
0x1801146c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801146ca  nop
0x1801146cb  lea     rcx, [rsp+0C8h+var_A0]
0x1801146d0  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x1801146d5  nop
0x1801146d6  lea     rcx, [rsp+0C8h+pvar]; pvar
0x1801146db  call    cs:__imp_PropVariantClear
0x1801146e1  nop
0x1801146e2  lea     rcx, [rsp+0C8h+var_88]
0x1801146e7  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x1801146ec  mov     eax, r14d
0x1801146ef  jmp     loc_180114954
0x1801146f4  mov     rdx, qword ptr [rsp+0C8h+var_A0+8]
0x1801146f9  cmp     rdx, [rsp+0C8h+var_90]
0x1801146fe  jz      short loc_180114711
0x180114700  movups  xmm0, xmmword ptr [rsp+0C8h+pclsid.Data1]
0x180114705  movdqu  xmmword ptr [rdx], xmm0
0x180114709  add     qword ptr [rsp+0C8h+var_A0+8], 10h
0x18011470f  jmp     short loc_180114720
0x180114711  lea     r8, [rsp+0C8h+pclsid]
0x180114716  lea     rcx, [rsp+0C8h+var_A0]
0x18011471b  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x180114720  inc     esi
0x180114722  jmp     loc_180114681
0x180114727  test    r15d, r15d
0x18011472a  jnz     short loc_180114773
0x18011472c  lea     rcx, [rsp+0C8h+var_88]
0x180114731  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114736  movups  xmm2, [rsp+0C8h+var_A0]
0x18011473b  movups  xmmword ptr [rsp+0C8h+var_88], xmm2
0x180114740  movsd   xmm0, [rsp+0C8h+var_90]
0x180114746  movsd   [rsp+0C8h+var_78], xmm0
0x18011474c  xorps   xmm1, xmm1
0x18011474f  movdqu  [rsp+0C8h+var_A0], xmm1
0x180114755  mov     [rsp+0C8h+var_90], 0
0x18011475e  movdqa  xmm0, xmm2
0x180114762  psrldq  xmm0, 8
0x180114767  movq    rdi, xmm0
0x18011476c  movq    rbx, xmm2
0x180114771  jmp     short loc_1801147E3
0x180114773  lea     rax, [rsp+0C8h+var_A0]
0x180114778  mov     qword ptr [rsp+0C8h+pclsid.Data1], rax
0x18011477d  lea     rax, [rsp+0C8h+var_A0]
0x180114782  mov     [rsp+0C8h+var_A8], rax
0x180114787  mov     r9, rbx
0x18011478a  cmp     rbx, rdi
0x18011478d  jz      short loc_1801147A9
0x18011478f  mov     rdx, r9
0x180114792  lea     rcx, [rsp+0C8h+var_A8]
0x180114797  call    _lambda_29cbe834aaff6b3962c1372fb6672b17___operator__
0x18011479c  test    al, al
0x18011479e  jnz     short loc_1801147A9
0x1801147a0  add     r9, 10h
0x1801147a4  cmp     r9, rdi
0x1801147a7  jnz     short loc_18011478F
0x1801147a9  cmp     r9, rdi
0x1801147ac  jz      short loc_1801147DA
0x1801147ae  lea     rdx, [r9+10h]
0x1801147b2  jmp     short loc_1801147D2
0x1801147b4  lea     rcx, [rsp+0C8h+pclsid]
0x1801147b9  call    _lambda_29cbe834aaff6b3962c1372fb6672b17___operator__
0x1801147be  test    al, al
0x1801147c0  jnz     short loc_1801147CE
0x1801147c2  movups  xmm0, xmmword ptr [rdx]
0x1801147c5  movdqu  xmmword ptr [r9], xmm0
0x1801147ca  add     r9, 10h
0x1801147ce  add     rdx, 10h
0x1801147d2  cmp     rdx, rdi
0x1801147d5  jnz     short loc_1801147B4
0x1801147d7  cmp     r9, rdi
0x1801147da  cmovnz  rdi, r9
0x1801147de  mov     [rsp+0C8h+var_88+8], rdi
0x1801147e3  lea     rcx, [rsp+0C8h+var_A0]
0x1801147e8  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x1801147ed  cmp     rbx, rdi
0x1801147f0  jnz     short loc_180114831
0x1801147f2  mov     rcx, [rsp+0C8h]; this
0x1801147fa  mov     ebx, 80070490h
0x1801147ff  mov     r9d, ebx; char *
0x180114802  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114809  mov     edx, 1ABh; void *
0x18011480e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114813  nop
0x180114814  lea     rcx, [rsp+0C8h+pvar]; pvar
0x180114819  call    cs:__imp_PropVariantClear
0x18011481f  nop
0x180114820  lea     rcx, [rsp+0C8h+var_88]
0x180114825  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18011482a  mov     eax, ebx
0x18011482c  jmp     loc_180114954
0x180114831  lea     rcx, [rsp+0C8h+pvar]; pvar
0x180114836  call    cs:__imp_PropVariantClear
0x18011483c  inc     r15d
0x18011483f  jmp     loc_1801145E4
0x180114844  sub     rdi, rbx
0x180114847  cmp     rdi, 10h
0x18011484b  jz      short loc_180114880
0x18011484d  mov     rcx, [rsp+0C8h]; this
0x180114855  mov     ebx, 80004001h
0x18011485a  mov     r9d, ebx; char *
0x18011485d  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114864  mov     edx, 1B2h; void *
0x180114869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011486e  nop
0x18011486f  lea     rcx, [rsp+0C8h+var_88]
0x180114874  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114879  mov     eax, ebx
0x18011487b  jmp     loc_180114954
0x180114880  mov     [rsp+0C8h+var_A8], 0; int
0x180114889  lea     r8, [rsp+0C8h+var_A8]; struct IMulticastProvider **
0x18011488e  mov     rdx, rbx; struct _GUID *
0x180114891  mov     rcx, [rsp+0C8h+var_58]; this
0x180114896  call    ?GetMulticastProvider@CMulticastSessionManager@@AEAAJAEBU_GUID@@PEAPEAUIMulticastProvider@@@Z; CMulticastSessionManager::GetMulticastProvider(_GUID const &,IMulticastProvider * *)
0x18011489b  mov     ebx, eax
0x18011489d  test    eax, eax
0x18011489f  jns     short loc_1801148D7
0x1801148a1  mov     rcx, [rsp+0C8h]; this
0x1801148a9  mov     r9d, eax; char *
0x1801148ac  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801148b3  mov     edx, 1B6h; void *
0x1801148b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801148bd  nop
0x1801148be  lea     rcx, [rsp+0C8h+var_A8]
0x1801148c3  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x1801148c8  nop
0x1801148c9  lea     rcx, [rsp+0C8h+var_88]
0x1801148ce  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x1801148d3  mov     eax, ebx
0x1801148d5  jmp     short loc_180114954
0x1801148d7  mov     rbx, [rsp+0C8h+var_A8]
0x1801148dc  mov     rax, [rbx]
0x1801148df  mov     rcx, rbx
0x1801148e2  mov     rax, [rax+18h]
0x1801148e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801148eb  test    al, al
0x1801148ed  jnz     short loc_18011492A
0x1801148ef  mov     rcx, [rsp+0C8h]; this
0x1801148f7  mov     ebx, 80070490h
0x1801148fc  mov     r9d, ebx; char *
0x1801148ff  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114906  mov     edx, 1B7h; void *
0x18011490b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114910  nop
0x180114911  lea     rcx, [rsp+0C8h+var_A8]
0x180114916  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x18011491b  nop
0x18011491c  lea     rcx, [rsp+0C8h+var_88]
0x180114921  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114926  mov     eax, ebx
0x180114928  jmp     short loc_180114954
0x18011492a  mov     [rsp+0C8h+var_A8], 0
0x180114933  mov     [r13+0], rbx
0x180114937  lea     rcx, [rsp+0C8h+var_A8]
0x18011493c  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x180114941  nop
0x180114942  lea     rcx, [rsp+0C8h+var_88]
0x180114947  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18011494c  xor     eax, eax
0x18011494e  jmp     short loc_180114954
0x180114950  mov     eax, dword ptr [rsp+0C8h+var_A8]
0x180114954  mov     rcx, [rsp+0C8h+var_40]
0x18011495c  xor     rcx, rsp; StackCookie
0x18011495f  call    __security_check_cookie
0x180114964  add     rsp, 90h
0x18011496b  pop     r15
0x18011496d  pop     r14
0x18011496f  pop     r13
0x180114971  pop     r12
0x180114973  pop     rdi
0x180114974  pop     rsi
0x180114975  pop     rbx
0x180114976  retn
```
