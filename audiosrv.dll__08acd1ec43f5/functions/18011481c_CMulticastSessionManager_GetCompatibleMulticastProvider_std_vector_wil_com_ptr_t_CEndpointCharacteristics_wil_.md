# CMulticastSessionManager::GetCompatibleMulticastProvider(std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>> &,IMulticastProvider * *)

- ea: `0x18011481c`
- end: `0x180114bf8`
- name: `?GetCompatibleMulticastProvider@CMulticastSessionManager@@AEAAJAEAV?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@PEAPEAUIMulticastProvider@@@Z`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b41ec`

## callees

- `0x18000b0c0`
- `0x18001280c`
- `0x1800a9354`
- `0x1800afbc4`
- `0x1800cd8d0`
- `0x1800eafc4`
- `0x18011479c`
- `0x18011481c`
- `0x180114d7c`
- `0x1801434f0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801148cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18011495b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114a99`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114ab6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801148cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18011495b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114a99`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180114ab6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180114921`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180114921`

## string_xrefs

- `0x1801148b5`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x180114939`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x180114a82`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x180114add`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x180114b2c`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`
- `0x180114b7f`: `avcore\audiocore\server\audiosrv\dll\multicastsessionmanager.cpp`

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
0x18011481c  push    rbx
0x18011481e  push    rsi
0x18011481f  push    rdi
0x180114820  push    r12
0x180114822  push    r13
0x180114824  push    r14
0x180114826  push    r15
0x180114828  sub     rsp, 90h
0x18011482f  mov     rax, cs:__security_cookie
0x180114836  xor     rax, rsp
0x180114839  mov     [rsp+0C8h+var_40], rax
0x180114841  mov     r13, r8
0x180114844  mov     r12, rdx
0x180114847  mov     [rsp+0C8h+var_58], rcx
0x18011484c  lea     rcx, [rsp+0C8h+var_88]; void *
0x180114851  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x180114856  nop
0x180114857  xor     r15d, r15d
0x18011485a  mov     rdi, [rsp+0C8h+var_88+8]
0x18011485f  mov     rbx, [rsp+0C8h+var_88]
0x180114864  mov     rcx, [r12]
0x180114868  mov     r9d, r15d
0x18011486b  mov     rax, [r12+8]
0x180114870  sub     rax, rcx
0x180114873  sar     rax, 3
0x180114877  cmp     r9, rax
0x18011487a  jnb     loc_180114AC4
0x180114880  xorps   xmm0, xmm0
0x180114883  xor     eax, eax
0x180114885  movups  xmmword ptr [rsp+0C8h+pvar], xmm0
0x18011488a  mov     [rsp+0C8h+var_60], rax
0x18011488f  lea     r8, [rsp+0C8h+pvar]; struct tagPROPVARIANT *
0x180114894  lea     rdx, PKEY_Multicast_CompatibleProviders; struct _tagpropertykey *
0x18011489b  mov     rcx, [rcx+r15*8]; this
0x18011489f  call    ?GetPropertyStoreProperty@CEndpointCharacteristics@@QEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CEndpointCharacteristics::GetPropertyStoreProperty(_tagpropertykey const &,tagPROPVARIANT *)
0x1801148a4  mov     esi, eax
0x1801148a6  test    eax, eax
0x1801148a8  jns     short loc_1801148E4
0x1801148aa  mov     rcx, [rsp+0C8h]; this
0x1801148b2  mov     r9d, eax; char *
0x1801148b5  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1801148bc  mov     edx, 18Ch; void *
0x1801148c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801148c6  nop
0x1801148c7  lea     rcx, [rsp+0C8h+pvar]; pvar
0x1801148cc  call    cs:__imp_PropVariantClear
0x1801148d2  nop
0x1801148d3  lea     rcx, [rsp+0C8h+var_88]
0x1801148d8  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x1801148dd  mov     eax, esi
0x1801148df  jmp     loc_180114BD4
0x1801148e4  mov     eax, 101Fh
0x1801148e9  cmp     word ptr [rsp+0C8h+pvar], ax
0x1801148ee  jnz     loc_180114A6D
0x1801148f4  lea     rcx, [rsp+0C8h+var_A0]; void *
0x1801148f9  call    ??0?$vector@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIWeakReference@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>::vector<wil::com_ptr_t<IWeakReference,wil::err_returncode_policy>>(void)
0x1801148fe  nop
0x1801148ff  xor     esi, esi
0x180114901  cmp     esi, dword ptr [rsp+0C8h+pvar+8]
0x180114905  jnb     loc_1801149A7
0x18011490b  xorps   xmm0, xmm0
0x18011490e  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x180114913  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x180114918  mov     rcx, [rsp+0C8h+var_60]
0x18011491d  mov     rcx, [rcx+rsi*8]; lpsz
0x180114921  call    cs:__imp_CLSIDFromString
0x180114927  mov     r14d, eax
0x18011492a  test    eax, eax
0x18011492c  jns     short loc_180114974
0x18011492e  mov     rcx, [rsp+0C8h]; this
0x180114936  mov     r9d, eax; char *
0x180114939  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114940  mov     edx, 193h; void *
0x180114945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011494a  nop
0x18011494b  lea     rcx, [rsp+0C8h+var_A0]
0x180114950  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114955  nop
0x180114956  lea     rcx, [rsp+0C8h+pvar]; pvar
0x18011495b  call    cs:__imp_PropVariantClear
0x180114961  nop
0x180114962  lea     rcx, [rsp+0C8h+var_88]
0x180114967  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18011496c  mov     eax, r14d
0x18011496f  jmp     loc_180114BD4
0x180114974  mov     rdx, qword ptr [rsp+0C8h+var_A0+8]
0x180114979  cmp     rdx, [rsp+0C8h+var_90]
0x18011497e  jz      short loc_180114991
0x180114980  movups  xmm0, xmmword ptr [rsp+0C8h+pclsid.Data1]
0x180114985  movdqu  xmmword ptr [rdx], xmm0
0x180114989  add     qword ptr [rsp+0C8h+var_A0+8], 10h
0x18011498f  jmp     short loc_1801149A0
0x180114991  lea     r8, [rsp+0C8h+pclsid]
0x180114996  lea     rcx, [rsp+0C8h+var_A0]
0x18011499b  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x1801149a0  inc     esi
0x1801149a2  jmp     loc_180114901
0x1801149a7  test    r15d, r15d
0x1801149aa  jnz     short loc_1801149F3
0x1801149ac  lea     rcx, [rsp+0C8h+var_88]
0x1801149b1  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x1801149b6  movups  xmm2, [rsp+0C8h+var_A0]
0x1801149bb  movups  xmmword ptr [rsp+0C8h+var_88], xmm2
0x1801149c0  movsd   xmm0, [rsp+0C8h+var_90]
0x1801149c6  movsd   [rsp+0C8h+var_78], xmm0
0x1801149cc  xorps   xmm1, xmm1
0x1801149cf  movdqu  [rsp+0C8h+var_A0], xmm1
0x1801149d5  mov     [rsp+0C8h+var_90], 0
0x1801149de  movdqa  xmm0, xmm2
0x1801149e2  psrldq  xmm0, 8
0x1801149e7  movq    rdi, xmm0
0x1801149ec  movq    rbx, xmm2
0x1801149f1  jmp     short loc_180114A63
0x1801149f3  lea     rax, [rsp+0C8h+var_A0]
0x1801149f8  mov     qword ptr [rsp+0C8h+pclsid.Data1], rax
0x1801149fd  lea     rax, [rsp+0C8h+var_A0]
0x180114a02  mov     [rsp+0C8h+var_A8], rax
0x180114a07  mov     r9, rbx
0x180114a0a  cmp     rbx, rdi
0x180114a0d  jz      short loc_180114A29
0x180114a0f  mov     rdx, r9
0x180114a12  lea     rcx, [rsp+0C8h+var_A8]
0x180114a17  call    _lambda_29cbe834aaff6b3962c1372fb6672b17___operator__
0x180114a1c  test    al, al
0x180114a1e  jnz     short loc_180114A29
0x180114a20  add     r9, 10h
0x180114a24  cmp     r9, rdi
0x180114a27  jnz     short loc_180114A0F
0x180114a29  cmp     r9, rdi
0x180114a2c  jz      short loc_180114A5A
0x180114a2e  lea     rdx, [r9+10h]
0x180114a32  jmp     short loc_180114A52
0x180114a34  lea     rcx, [rsp+0C8h+pclsid]
0x180114a39  call    _lambda_29cbe834aaff6b3962c1372fb6672b17___operator__
0x180114a3e  test    al, al
0x180114a40  jnz     short loc_180114A4E
0x180114a42  movups  xmm0, xmmword ptr [rdx]
0x180114a45  movdqu  xmmword ptr [r9], xmm0
0x180114a4a  add     r9, 10h
0x180114a4e  add     rdx, 10h
0x180114a52  cmp     rdx, rdi
0x180114a55  jnz     short loc_180114A34
0x180114a57  cmp     r9, rdi
0x180114a5a  cmovnz  rdi, r9
0x180114a5e  mov     [rsp+0C8h+var_88+8], rdi
0x180114a63  lea     rcx, [rsp+0C8h+var_A0]
0x180114a68  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114a6d  cmp     rbx, rdi
0x180114a70  jnz     short loc_180114AB1
0x180114a72  mov     rcx, [rsp+0C8h]; this
0x180114a7a  mov     ebx, 80070490h
0x180114a7f  mov     r9d, ebx; char *
0x180114a82  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114a89  mov     edx, 1ABh; void *
0x180114a8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114a93  nop
0x180114a94  lea     rcx, [rsp+0C8h+pvar]; pvar
0x180114a99  call    cs:__imp_PropVariantClear
0x180114a9f  nop
0x180114aa0  lea     rcx, [rsp+0C8h+var_88]
0x180114aa5  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114aaa  mov     eax, ebx
0x180114aac  jmp     loc_180114BD4
0x180114ab1  lea     rcx, [rsp+0C8h+pvar]; pvar
0x180114ab6  call    cs:__imp_PropVariantClear
0x180114abc  inc     r15d
0x180114abf  jmp     loc_180114864
0x180114ac4  sub     rdi, rbx
0x180114ac7  cmp     rdi, 10h
0x180114acb  jz      short loc_180114B00
0x180114acd  mov     rcx, [rsp+0C8h]; this
0x180114ad5  mov     ebx, 80004001h
0x180114ada  mov     r9d, ebx; char *
0x180114add  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114ae4  mov     edx, 1B2h; void *
0x180114ae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114aee  nop
0x180114aef  lea     rcx, [rsp+0C8h+var_88]
0x180114af4  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114af9  mov     eax, ebx
0x180114afb  jmp     loc_180114BD4
0x180114b00  mov     [rsp+0C8h+var_A8], 0; int
0x180114b09  lea     r8, [rsp+0C8h+var_A8]; struct IMulticastProvider **
0x180114b0e  mov     rdx, rbx; struct _GUID *
0x180114b11  mov     rcx, [rsp+0C8h+var_58]; this
0x180114b16  call    ?GetMulticastProvider@CMulticastSessionManager@@AEAAJAEBU_GUID@@PEAPEAUIMulticastProvider@@@Z; CMulticastSessionManager::GetMulticastProvider(_GUID const &,IMulticastProvider * *)
0x180114b1b  mov     ebx, eax
0x180114b1d  test    eax, eax
0x180114b1f  jns     short loc_180114B57
0x180114b21  mov     rcx, [rsp+0C8h]; this
0x180114b29  mov     r9d, eax; char *
0x180114b2c  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114b33  mov     edx, 1B6h; void *
0x180114b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114b3d  nop
0x180114b3e  lea     rcx, [rsp+0C8h+var_A8]
0x180114b43  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x180114b48  nop
0x180114b49  lea     rcx, [rsp+0C8h+var_88]
0x180114b4e  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114b53  mov     eax, ebx
0x180114b55  jmp     short loc_180114BD4
0x180114b57  mov     rbx, [rsp+0C8h+var_A8]
0x180114b5c  mov     rax, [rbx]
0x180114b5f  mov     rcx, rbx
0x180114b62  mov     rax, [rax+18h]
0x180114b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114b6b  test    al, al
0x180114b6d  jnz     short loc_180114BAA
0x180114b6f  mov     rcx, [rsp+0C8h]; this
0x180114b77  mov     ebx, 80070490h
0x180114b7c  mov     r9d, ebx; char *
0x180114b7f  lea     r8, aAvcoreAudiocor_22; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180114b86  mov     edx, 1B7h; void *
0x180114b8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114b90  nop
0x180114b91  lea     rcx, [rsp+0C8h+var_A8]
0x180114b96  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x180114b9b  nop
0x180114b9c  lea     rcx, [rsp+0C8h+var_88]
0x180114ba1  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114ba6  mov     eax, ebx
0x180114ba8  jmp     short loc_180114BD4
0x180114baa  mov     [rsp+0C8h+var_A8], 0
0x180114bb3  mov     [r13+0], rbx
0x180114bb7  lea     rcx, [rsp+0C8h+var_A8]
0x180114bbc  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x180114bc1  nop
0x180114bc2  lea     rcx, [rsp+0C8h+var_88]
0x180114bc7  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x180114bcc  xor     eax, eax
0x180114bce  jmp     short loc_180114BD4
0x180114bd0  mov     eax, dword ptr [rsp+0C8h+var_A8]
0x180114bd4  mov     rcx, [rsp+0C8h+var_40]
0x180114bdc  xor     rcx, rsp; StackCookie
0x180114bdf  call    __security_check_cookie
0x180114be4  add     rsp, 90h
0x180114beb  pop     r15
0x180114bed  pop     r14
0x180114bef  pop     r13
0x180114bf1  pop     r12
0x180114bf3  pop     rdi
0x180114bf4  pop     rsi
0x180114bf5  pop     rbx
0x180114bf6  retn
```
