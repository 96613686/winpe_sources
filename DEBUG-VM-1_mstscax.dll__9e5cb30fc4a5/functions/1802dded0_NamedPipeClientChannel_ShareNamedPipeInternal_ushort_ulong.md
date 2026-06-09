# NamedPipeClientChannel::ShareNamedPipeInternal(ushort *,ulong)

- ea: `0x1802dded0`
- end: `0x1802de9b1`
- name: `?ShareNamedPipeInternal@NamedPipeClientChannel@@AEAAJPEAGK@Z`
- size: `2785`
- prototype: `__int64 __fastcall(NamedPipeClientChannel *__hidden this, unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1802ddd70`

## callees

- `0x1800058f0`
- `0x180039ce4`
- `0x1800cf50c`
- `0x1800cfa74`
- `0x1800d1db0`
- `0x1800d3818`
- `0x1800f1c88`
- `0x180100a0c`
- `0x180101d30`
- `0x1801208e0`
- `0x180174b04`
- `0x180238a54`
- `0x18023a424`
- `0x18023a684`
- `0x18026de4c`
- `0x1802821ac`
- `0x1802dafcc`
- `0x1802db67c`
- `0x1802db720`
- `0x1802dbd28`
- `0x1802dbe1c`
- `0x1802dded0`
- `0x1802df564`
- `0x1805b3990`
- `0x18068c010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x1802de855`
- `KERNEL32!WaitForSingleObjectEx` at `0x1802de855`
- `KERNEL32!LeaveCriticalSection` at `0x1802de002`
- `KERNEL32!LeaveCriticalSection` at `0x1802de065`
- `KERNEL32!LeaveCriticalSection` at `0x1802de10a`
- `KERNEL32!LeaveCriticalSection` at `0x1802de18f`
- `KERNEL32!LeaveCriticalSection` at `0x1802de1df`
- `KERNEL32!LeaveCriticalSection` at `0x1802de24b`
- `KERNEL32!LeaveCriticalSection` at `0x1802de271`
- `KERNEL32!LeaveCriticalSection` at `0x1802de3b9`
- `KERNEL32!LeaveCriticalSection` at `0x1802de417`
- `KERNEL32!LeaveCriticalSection` at `0x1802de002`
- `KERNEL32!LeaveCriticalSection` at `0x1802de065`
- `KERNEL32!LeaveCriticalSection` at `0x1802de10a`
- `KERNEL32!LeaveCriticalSection` at `0x1802de18f`
- `KERNEL32!LeaveCriticalSection` at `0x1802de1df`
- `KERNEL32!LeaveCriticalSection` at `0x1802de24b`
- `KERNEL32!LeaveCriticalSection` at `0x1802de271`
- `KERNEL32!LeaveCriticalSection` at `0x1802de3b9`
- `KERNEL32!LeaveCriticalSection` at `0x1802de417`
- `KERNEL32!EnterCriticalSection` at `0x1802ddfb6`
- `KERNEL32!EnterCriticalSection` at `0x1802de354`
- `KERNEL32!EnterCriticalSection` at `0x1802ddfb6`
- `KERNEL32!EnterCriticalSection` at `0x1802de354`

## string_xrefs

- `0x1802ddf28`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802ddfed`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de050`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de0f5`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de17a`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de1ca`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de236`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de2df`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de317`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de3a5`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de3e6`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de45b`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de49e`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de50e`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de551`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de5b4`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de5f7`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de720`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de763`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de7d4`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de817`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de871`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de8b5`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de8f9`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`
- `0x1802de93c`: `clientcore\termsrv\client\plugins\dynvcplugins\namedpipe\namedpipeclientchannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall NamedPipeClientChannel::ShareNamedPipeInternal(NamedPipeClientChannel *this, char *a2, int a3)
{
  char v3; // bl
  __int64 result; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  struct ITSPlatform *v12; // r12
  int PipeId; // eax
  unsigned int v14; // r15d
  int v15; // eax
  unsigned int v16; // r15d
  unsigned __int16 v17; // r15
  int v18; // eax
  unsigned int v19; // r12d
  int v20; // eax
  int v21; // eax
  __int64 v22; // rsi
  int v23; // eax
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  int v27; // r12d
  HKEY *v28; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // eax
  int v33; // eax
  DWORD v34; // eax
  unsigned int v35; // [rsp+20h] [rbp-C8h]
  unsigned int v36; // [rsp+20h] [rbp-C8h]
  int v37; // [rsp+20h] [rbp-C8h]
  int v38; // [rsp+20h] [rbp-C8h]
  int v39; // [rsp+20h] [rbp-C8h]
  struct INamedPipeAdaptor **v40; // [rsp+28h] [rbp-C0h]
  struct INamedPipeAdaptor *v41; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+48h] [rbp-A0h] BYREF
  HANDLE hHandle; // [rsp+50h] [rbp-98h] BYREF
  __m128i si128; // [rsp+58h] [rbp-90h] BYREF
  __int64 v45; // [rsp+68h] [rbp-80h]
  _QWORD v46[2]; // [rsp+70h] [rbp-78h] BYREF
  __int64 v47; // [rsp+80h] [rbp-68h]
  NamedPipeClientChannel *v48; // [rsp+88h] [rbp-60h]
  __int16 v49; // [rsp+90h] [rbp-58h]
  int v50; // [rsp+92h] [rbp-56h]
  __int16 v51; // [rsp+96h] [rbp-52h]
  char *v52; // [rsp+98h] [rbp-50h]
  char v53; // [rsp+A0h] [rbp-48h]
  __int64 v54; // [rsp+A8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  unsigned __int64 v56; // [rsp+F8h] [rbp+10h] BYREF
  int v57; // [rsp+100h] [rbp+18h]
  char *v58; // [rsp+108h] [rbp+20h] BYREF

  v57 = a3;
  v54 = -2;
  v3 = a3;
  v42 = 0;
  v41 = 0;
  LOWORD(v56) = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
      (const char *)0x80004003LL,
      v35);
    wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
    return 2147500035LL;
  }
  try
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a2, v3);
    }
    v46[0] = (char *)this + 104;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    if ( *((_DWORD *)this + 36) != 4 )
    {
      LODWORD(v40) = *((_DWORD *)this + 36);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)0x8007139FLL,
        (int)"Channel in invalid state (%d, should be %d)",
        (const char *)v40,
        4);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return 2147947423LL;
    }
    SmartPtr<CRIMObjectPoolBase>::operator=(&v42, *((_QWORD *)this + 21));
    v9 = v42;
    if ( !v42 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)0x80004003LL,
        v35);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return 2147500035LL;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 88LL))(*((_QWORD *)this + 20));
    v11 = v10 + 8 + *(int *)(*(_QWORD *)(v10 + 8) + 4LL);
    v12 = (struct ITSPlatform *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 40LL))(v11);
    v47 = (*(__int64 (__fastcall **)(struct ITSPlatform *))(*(_QWORD *)v12 + 64LL))(v12);
    PipeId = NamedPipeClientChannel::AllocatePipeId(this, a2, (unsigned __int16 *)&v56);
    v14 = PipeId;
    if ( PipeId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)PipeId,
        v35);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return v14;
    }
    wil::com_ptr_t<ITSCoreApi,wil::err_returncode_policy>::reset(&v41);
    v15 = CreateNamedPipeClientAdaptor(
            v56,
            (const unsigned __int16 *)a2,
            v12,
            (struct INamedPipeChannelCallback *)(((unsigned __int64)this + 80) & -(__int64)(this != 0)),
            v35,
            &v41);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v15,
        v36);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return v16;
    }
    if ( !v41 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)0x8007000ELL,
        v36);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return 2147942414LL;
    }
    if ( !*(_BYTE *)(utl::_Tree<unsigned short,utl::pair<unsigned short const,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy>>,utl::less<unsigned short>,utl::allocator<utl::pair<unsigned short const,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy>>>,0>::emplace<unsigned short &,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy> &,0>(
                       (char *)this + 176,
                       v46,
                       &v56,
                       &v41)
                   + 8) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)0x8007000ELL,
        v36);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return 2147942414LL;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v17 = v56;
    v48 = this;
    v49 = v56;
    v50 = *(__int32 *)((char *)&si128.m128i_i32[2] + 2);
    v51 = si128.m128i_i16[7];
    v52 = a2;
    v53 = 1;
    hHandle = 0;
    v18 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            &hHandle,
            1);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v18,
        v36);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v20 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v20 < 0 )
        goto LABEL_34;
      goto LABEL_35;
    }
    LODWORD(v58) = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v46[0] = &hHandle;
    v46[1] = &v58;
    if ( !*(_BYTE *)(utl::_Tree_unsigned_short_utl::pair_unsigned_short_const__utl::function_void___cdecl_unsigned_int_____utl::less_unsigned_short__utl::allocator_utl::pair_unsigned_short_const__utl::function_void___cdecl_unsigned_int_______0_::emplace_unsigned_short____lambda_29efd29e736783bf2afdb9818eec9446__0_(
                       (char *)this + 208,
                       &si128,
                       &v56,
                       v46)
                   + 8) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)0x8007000ELL,
        v36);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v21 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v21 >= 0 )
      {
LABEL_25:
        wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
        wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
        return 2147942414LL;
      }
LABEL_24:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v21,
        v38);
      goto LABEL_25;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v45 = -1;
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(&si128, 528) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D4,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)0x8007000ELL,
        v36);
      utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v21 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v21 >= 0 )
        goto LABEL_25;
      goto LABEL_24;
    }
    v22 = si128.m128i_i64[0];
    *(_WORD *)si128.m128i_i64[0] = 4;
    *(_WORD *)(v22 + 6) = v56;
    *(_DWORD *)(v22 + 8) = v57;
    v23 = StringCchCopyW((unsigned __int16 *)(v22 + 14), 0x101u, (const unsigned __int16 *)a2);
    v19 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v23,
        v36);
      utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v20 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v20 < 0 )
        goto LABEL_34;
      goto LABEL_35;
    }
    v56 = 0;
    v24 = StringCchLengthW((const unsigned __int16 *)(v22 + 14), 0x101u, &v56);
    v19 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DB,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v24,
        v36);
      utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v20 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v20 < 0 )
LABEL_34:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1C0,
          (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
          (const char *)(unsigned int)v20,
          v37);
LABEL_35:
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return v19;
    }
    v27 = (unsigned __int16)v56;
    *(_WORD *)(v22 + 12) = v56;
    *(_DWORD *)(v22 + 2) = 2 * v27 + 14;
    v28 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      LODWORD(v56) = *(_DWORD *)(v22 + 8);
      LODWORD(v46[0]) = *(unsigned __int16 *)(v22 + 6);
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdddS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_2affdf29434134f8fe179140e06dfec9_Traceguids,
        CurrentThreadActivityIdPrefix,
        v46[0],
        v56,
        v27,
        v22 + 14);
    }
    if ( (unsigned int)dword_1808B4C80 > 4 )
    {
      v46[0] = a2;
      LOWORD(v56) = *(_WORD *)(v22 + 6);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v28,
        (unsigned int)byte_1808680C5,
        v25,
        v26,
        (__int64)&v56,
        (__int64)v46);
    }
    v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v9 + 24LL))(
            v9,
            *(unsigned int *)(v22 + 2),
            v22,
            0);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E4,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v30,
        v36);
      utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v32 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v32 < 0 )
        goto LABEL_55;
      goto LABEL_56;
    }
    if ( v47 )
    {
      v33 = (*(__int64 (__fastcall **)(__int64, HANDLE, __int64, __int64))(*(_QWORD *)v47 + 72LL))(
              v47,
              hHandle,
              3,
              20000);
      v31 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EC,
          (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
          (const char *)(unsigned int)v33,
          v36);
        utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        v32 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
        if ( v32 < 0 )
          goto LABEL_55;
        goto LABEL_56;
      }
    }
    else
    {
      do
        v34 = WaitForSingleObjectEx(hHandle, 0x4E20u, 1);
      while ( v34 == 192 );
      if ( v34 )
      {
        v31 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1F6,
                (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
                (const char *)v34,
                v36);
        utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        v32 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
        if ( v32 < 0 )
          goto LABEL_55;
        goto LABEL_56;
      }
    }
    v31 = (unsigned int)v58;
    if ( (int)v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
        (const char *)(unsigned int)v58,
        v36);
      utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
      v32 = NamedPipeClientChannel::ClosePipeAdaptorIfOpen(this, v17);
      if ( v32 < 0 )
LABEL_55:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1C0,
          (unsigned int)"clientcore\\termsrv\\client\\plugins\\dynvcplugins\\namedpipe\\namedpipeclientchannel.cpp",
          (const char *)(unsigned int)v32,
          v39);
LABEL_56:
      wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
      wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
      return v31;
    }
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(&v42);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v56) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x1FF, v7, v8);
    return (unsigned int)v56;
  }
  return result;
}

```

## disassembly

```asm
0x1802dded0  mov     r11, rsp
0x1802dded3  mov     [r11+18h], r8d
0x1802dded7  push    rbx
0x1802dded8  push    rsi
0x1802dded9  push    rdi
0x1802ddeda  push    r12
0x1802ddedc  push    r13
0x1802ddede  push    r14
0x1802ddee0  push    r15
0x1802ddee2  sub     rsp, 0B0h
0x1802ddee9  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x1802ddef1  mov     ebx, r8d
0x1802ddef4  mov     r13, rdx
0x1802ddef7  mov     rdi, rcx
0x1802ddefa  mov     [rsp+0E8h+var_A0], 0
0x1802ddf03  mov     [rsp+0E8h+var_A8], 0
0x1802ddf0c  xor     eax, eax
0x1802ddf0e  mov     [r11+10h], ax
0x1802ddf13  test    rdx, rdx
0x1802ddf16  jnz     short loc_1802DDF56
0x1802ddf18  mov     rcx, [rsp+0E8h]; this
0x1802ddf20  mov     ebx, 80004003h
0x1802ddf25  mov     r9d, ebx; char *
0x1802ddf28  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802ddf2f  mov     edx, 1A3h; void *
0x1802ddf34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802ddf39  nop
0x1802ddf3a  lea     rcx, [rsp+0E8h+var_A8]
0x1802ddf3f  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802ddf44  nop
0x1802ddf45  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802ddf4a  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802ddf4f  mov     eax, ebx
0x1802ddf51  jmp     loc_1802DE99D
0x1802ddf56  lea     rcx, WPP_GLOBAL_Control
0x1802ddf5d  mov     rax, cs:WPP_GLOBAL_Control
0x1802ddf64  mov     r14d, 4
0x1802ddf6a  cmp     rax, rcx
0x1802ddf6d  jz      short loc_1802DDFAA
0x1802ddf6f  test    dword ptr [rax+1Ch], 1000h
0x1802ddf76  jz      short loc_1802DDFAA
0x1802ddf78  cmp     [rax+19h], r14b
0x1802ddf7c  jb      short loc_1802DDFAA
0x1802ddf7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802ddf83  lea     edx, [r14+13h]
0x1802ddf87  mov     dword ptr [rsp+0E8h+var_C0], ebx; char
0x1802ddf8b  mov     qword ptr [rsp+0E8h+var_C8], r13; int
0x1802ddf90  mov     r9d, eax
0x1802ddf93  lea     r8, WPP_2affdf29434134f8fe179140e06dfec9_Traceguids
0x1802ddf9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1802ddfa1  mov     rcx, [rcx+10h]; LoggerHandle
0x1802ddfa5  call    WPP_SF_DSd
0x1802ddfaa  lea     rsi, [rdi+68h]
0x1802ddfae  mov     [rsp+0E8h+var_78], rsi
0x1802ddfb3  mov     rcx, rsi; lpCriticalSection
0x1802ddfb6  call    cs:__imp_EnterCriticalSection
0x1802ddfbc  nop
0x1802ddfbd  mov     eax, [rdi+90h]
0x1802ddfc3  cmp     eax, r14d
0x1802ddfc6  jz      short loc_1802DE025
0x1802ddfc8  mov     rcx, [rsp+0E8h]; this
0x1802ddfd0  mov     [rsp+0E8h+var_B8], r14d
0x1802ddfd5  mov     dword ptr [rsp+0E8h+var_C0], eax; char *
0x1802ddfd9  lea     rax, aChannelInInval; "Channel in invalid state (%d, should be"...
0x1802ddfe0  mov     qword ptr [rsp+0E8h+var_C8], rax; int
0x1802ddfe5  mov     ebx, 8007139Fh
0x1802ddfea  mov     r9d, ebx; char *
0x1802ddfed  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802ddff4  mov     edx, 1A9h; void *
0x1802ddff9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1802ddffe  nop
0x1802ddfff  mov     rcx, rsi; lpCriticalSection
0x1802de002  call    cs:__imp_LeaveCriticalSection
0x1802de008  nop
0x1802de009  lea     rcx, [rsp+0E8h+var_A8]
0x1802de00e  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de013  nop
0x1802de014  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de019  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de01e  mov     eax, ebx
0x1802de020  jmp     loc_1802DE99D
0x1802de025  mov     rdx, [rdi+0A8h]
0x1802de02c  lea     rcx, [rsp+0E8h+var_A0]
0x1802de031  call    ??4?$SmartPtr@VCRIMObjectPoolBase@@@@QEAAAEAV0@PEAVCRIMObjectPoolBase@@@Z; SmartPtr<CRIMObjectPoolBase>::operator=(CRIMObjectPoolBase *)
0x1802de036  mov     rbx, [rsp+0E8h+var_A0]
0x1802de03b  test    rbx, rbx
0x1802de03e  jnz     short loc_1802DE088
0x1802de040  mov     rcx, [rsp+0E8h]; this
0x1802de048  mov     ebx, 80004003h
0x1802de04d  mov     r9d, ebx; char *
0x1802de050  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de057  mov     edx, 1ABh; void *
0x1802de05c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de061  nop
0x1802de062  mov     rcx, rsi; lpCriticalSection
0x1802de065  call    cs:__imp_LeaveCriticalSection
0x1802de06b  nop
0x1802de06c  lea     rcx, [rsp+0E8h+var_A8]
0x1802de071  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de076  nop
0x1802de077  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de07c  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de081  mov     eax, ebx
0x1802de083  jmp     loc_1802DE99D
0x1802de088  mov     rcx, [rdi+0A0h]
0x1802de08f  mov     rax, [rcx]
0x1802de092  mov     rax, [rax+58h]
0x1802de096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de09b  mov     rcx, [rax+8]
0x1802de09f  movsxd  rcx, dword ptr [rcx+4]
0x1802de0a3  add     rax, 8
0x1802de0a7  add     rcx, rax
0x1802de0aa  mov     rax, [rcx]
0x1802de0ad  mov     rax, [rax+28h]
0x1802de0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de0b6  mov     r12, rax
0x1802de0b9  mov     rcx, [rax]
0x1802de0bc  mov     rax, [rcx+40h]
0x1802de0c0  mov     rcx, r12
0x1802de0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802de0c8  mov     [rsp+0E8h+var_68], rax
0x1802de0d0  lea     r8, [rsp+0E8h+arg_8]; unsigned __int16 *
0x1802de0d8  mov     rdx, r13; char *
0x1802de0db  mov     rcx, rdi; this
0x1802de0de  call    ?AllocatePipeId@NamedPipeClientChannel@@AEAAJPEBGAEAG@Z; NamedPipeClientChannel::AllocatePipeId(ushort const *,ushort &)
0x1802de0e3  mov     r15d, eax
0x1802de0e6  test    eax, eax
0x1802de0e8  jns     short loc_1802DE12E
0x1802de0ea  mov     rcx, [rsp+0E8h]; this
0x1802de0f2  mov     r9d, eax; char *
0x1802de0f5  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de0fc  mov     edx, 1B3h; void *
0x1802de101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de106  nop
0x1802de107  mov     rcx, rsi; lpCriticalSection
0x1802de10a  call    cs:__imp_LeaveCriticalSection
0x1802de110  nop
0x1802de111  lea     rcx, [rsp+0E8h+var_A8]
0x1802de116  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de11b  nop
0x1802de11c  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de121  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de126  mov     eax, r15d
0x1802de129  jmp     loc_1802DE99D
0x1802de12e  lea     rcx, [rsp+0E8h+var_A8]
0x1802de133  call    ?reset@?$com_ptr_t@VITSCoreApi@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<ITSCoreApi,wil::err_returncode_policy>::reset(void)
0x1802de138  mov     rax, rdi
0x1802de13b  lea     rcx, [rdi+50h]
0x1802de13f  neg     rax
0x1802de142  sbb     r9, r9
0x1802de145  and     r9, rcx; struct INamedPipeChannelCallback *
0x1802de148  lea     rax, [rsp+0E8h+var_A8]
0x1802de14d  mov     [rsp+0E8h+var_C0], rax; struct INamedPipeAdaptor **
0x1802de152  mov     r8, r12; struct ITSPlatform *
0x1802de155  mov     rdx, r13; unsigned __int16 *
0x1802de158  movzx   ecx, word ptr [rsp+0E8h+arg_8]; unsigned __int16
0x1802de160  call    ?CreateNamedPipeClientAdaptor@@YAJGPEBGPEAVITSPlatform@@PEAUINamedPipeChannelCallback@@IPEAPEAUINamedPipeAdaptor@@@Z; CreateNamedPipeClientAdaptor(ushort,ushort const *,ITSPlatform *,INamedPipeChannelCallback *,uint,INamedPipeAdaptor * *)
0x1802de165  mov     r15d, eax
0x1802de168  xor     r12d, r12d
0x1802de16b  test    eax, eax
0x1802de16d  jns     short loc_1802DE1B3
0x1802de16f  mov     rcx, [rsp+0E8h]; this
0x1802de177  mov     r9d, eax; char *
0x1802de17a  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de181  mov     edx, 1B4h; void *
0x1802de186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de18b  nop
0x1802de18c  mov     rcx, rsi; lpCriticalSection
0x1802de18f  call    cs:__imp_LeaveCriticalSection
0x1802de195  nop
0x1802de196  lea     rcx, [rsp+0E8h+var_A8]
0x1802de19b  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de1a0  nop
0x1802de1a1  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de1a6  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de1ab  mov     eax, r15d
0x1802de1ae  jmp     loc_1802DE99D
0x1802de1b3  cmp     [rsp+0E8h+var_A8], r12
0x1802de1b8  jnz     short loc_1802DE202
0x1802de1ba  mov     rcx, [rsp+0E8h]; this
0x1802de1c2  mov     ebx, 8007000Eh
0x1802de1c7  mov     r9d, ebx; char *
0x1802de1ca  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de1d1  mov     edx, 1B5h; void *
0x1802de1d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de1db  nop
0x1802de1dc  mov     rcx, rsi; lpCriticalSection
0x1802de1df  call    cs:__imp_LeaveCriticalSection
0x1802de1e5  nop
0x1802de1e6  lea     rcx, [rsp+0E8h+var_A8]
0x1802de1eb  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de1f0  nop
0x1802de1f1  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de1f6  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de1fb  mov     eax, ebx
0x1802de1fd  jmp     loc_1802DE99D
0x1802de202  lea     rcx, [rdi+0B0h]
0x1802de209  lea     r9, [rsp+0E8h+var_A8]
0x1802de20e  lea     r8, [rsp+0E8h+arg_8]
0x1802de216  lea     rdx, [rsp+0E8h+var_78]
0x1802de21b  call    ??$emplace@AEAGAEAV?$com_ptr_t@UINamedPipeAdaptor@@Uerr_returncode_policy@wil@@@wil@@$0A@@?$_Tree@GU?$pair@$$CBGV?$com_ptr_t@UINamedPipeAdaptor@@Uerr_returncode_policy@wil@@@wil@@@utl@@U?$less@G@2@V?$allocator@U?$pair@$$CBGV?$com_ptr_t@UINamedPipeAdaptor@@Uerr_returncode_policy@wil@@@wil@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBGV?$com_ptr_t@UINamedPipeAdaptor@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@_N@1@AEAGAEAV?$com_ptr_t@UINamedPipeAdaptor@@Uerr_returncode_policy@wil@@@wil@@@Z; utl::_Tree<ushort,utl::pair<ushort const,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy>>,utl::less<ushort>,utl::allocator<utl::pair<ushort const,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy>>>,0>::emplace<ushort &,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy> &,0>(ushort &,wil::com_ptr_t<INamedPipeAdaptor,wil::err_returncode_policy> &)
0x1802de220  cmp     [rax+8], r12b
0x1802de224  jnz     short loc_1802DE26E
0x1802de226  mov     rcx, [rsp+0E8h]; this
0x1802de22e  mov     ebx, 8007000Eh
0x1802de233  mov     r9d, ebx; char *
0x1802de236  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de23d  mov     edx, 1BAh; void *
0x1802de242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de247  nop
0x1802de248  mov     rcx, rsi; lpCriticalSection
0x1802de24b  call    cs:__imp_LeaveCriticalSection
0x1802de251  nop
0x1802de252  lea     rcx, [rsp+0E8h+var_A8]
0x1802de257  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de25c  nop
0x1802de25d  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de262  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de267  mov     eax, ebx
0x1802de269  jmp     loc_1802DE99D
0x1802de26e  mov     rcx, rsi; lpCriticalSection
0x1802de271  call    cs:__imp_LeaveCriticalSection
0x1802de277  movzx   r15d, word ptr [rsp+0E8h+arg_8]
0x1802de280  mov     [rsp+0E8h+var_60], rdi
0x1802de288  mov     [rsp+0E8h+var_58], r15w
0x1802de291  mov     eax, dword ptr [rsp+0E8h+var_90+0Ah]
0x1802de295  mov     [rsp+0E8h+var_56], eax
0x1802de29c  movzx   eax, word ptr [rsp+0E8h+var_90+0Eh]
0x1802de2a1  mov     [rsp+0E8h+var_52], ax
0x1802de2a9  mov     [rsp+0E8h+var_50], r13
0x1802de2b1  mov     [rsp+0E8h+var_48], 1
0x1802de2b9  mov     [rsp+0E8h+hHandle], r12
0x1802de2be  mov     edx, 1
0x1802de2c3  lea     rcx, [rsp+0E8h+hHandle]
0x1802de2c8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1802de2cd  mov     r12d, eax
0x1802de2d0  test    eax, eax
0x1802de2d2  jns     short loc_1802DE346
0x1802de2d4  mov     rcx, [rsp+0E8h]; this
0x1802de2dc  mov     r9d, eax; char *
0x1802de2df  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de2e6  mov     edx, 1C6h; void *
0x1802de2eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de2f0  nop
0x1802de2f1  lea     rcx, [rsp+0E8h+hHandle]
0x1802de2f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802de2fb  nop
0x1802de2fc  movzx   edx, r15w; unsigned __int16
0x1802de300  mov     rcx, rdi; this
0x1802de303  call    ?ClosePipeAdaptorIfOpen@NamedPipeClientChannel@@AEAAJG@Z; NamedPipeClientChannel::ClosePipeAdaptorIfOpen(ushort)
0x1802de308  mov     rcx, [rsp+0E8h]; this
0x1802de310  test    eax, eax
0x1802de312  jns     short loc_1802DE329
0x1802de314  mov     r9d, eax; char *
0x1802de317  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de31e  mov     edx, 1C0h; void *
0x1802de323  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802de328  nop
0x1802de329  lea     rcx, [rsp+0E8h+var_A8]
0x1802de32e  call    ??1?$com_ptr_t@UIPropertyBag@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPropertyBag,wil::err_returncode_policy>::~com_ptr_t<IPropertyBag,wil::err_returncode_policy>(void)
0x1802de333  nop
0x1802de334  lea     rcx, [rsp+0E8h+var_A0]; void *
0x1802de339  call    ??1?$com_ptr_t@UID3D10Multithread@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>::~com_ptr_t<ID3D10Multithread,wil::err_returncode_policy>(void)
0x1802de33e  mov     eax, r12d
0x1802de341  jmp     loc_1802DE99D
0x1802de346  mov     dword ptr [rsp+0E8h+arg_18], 0
0x1802de351  mov     rcx, rsi; lpCriticalSection
0x1802de354  call    cs:__imp_EnterCriticalSection
0x1802de35a  lea     rax, [rsp+0E8h+hHandle]
0x1802de35f  mov     [rsp+0E8h+var_78], rax
0x1802de364  lea     rax, [rsp+0E8h+arg_18]
0x1802de36c  mov     [rsp+0E8h+var_70], rax
0x1802de371  lea     rcx, [rdi+0D0h]
0x1802de378  lea     r9, [rsp+0E8h+var_78]
0x1802de37d  lea     r8, [rsp+0E8h+arg_8]
0x1802de385  lea     rdx, [rsp+0E8h+var_90]
0x1802de38a  call    utl___Tree_unsigned_short_utl__pair_unsigned_short_const__utl__function_void___cdecl_unsigned_int_____utl__less_unsigned_short__utl__allocator_utl__pair_unsigned_short_const__utl__function_void___cdecl_unsigned_int_______0___emplace_unsigned_short____lambda_29efd29e736783bf2afdb9818eec9446__0_
0x1802de38f  cmp     byte ptr [rax+8], 0
0x1802de393  jnz     short loc_1802DE414
0x1802de395  mov     rcx, [rsp+0E8h]; this
0x1802de39d  mov     ebx, 8007000Eh
0x1802de3a2  mov     r9d, ebx; char *
0x1802de3a5  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de3ac  mov     edx, 1CDh; void *
0x1802de3b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802de3b6  mov     rcx, rsi; lpCriticalSection
0x1802de3b9  call    cs:__imp_LeaveCriticalSection
0x1802de3bf  nop
0x1802de3c0  lea     rcx, [rsp+0E8h+hHandle]
0x1802de3c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802de3ca  nop
0x1802de3cb  movzx   edx, r15w; unsigned __int16
0x1802de3cf  mov     rcx, rdi; this
0x1802de3d2  call    ?ClosePipeAdaptorIfOpen@NamedPipeClientChannel@@AEAAJG@Z; NamedPipeClientChannel::ClosePipeAdaptorIfOpen(ushort)
0x1802de3d7  mov     rcx, [rsp+0E8h]; this
0x1802de3df  test    eax, eax
0x1802de3e1  jns     short loc_1802DE3F8
0x1802de3e3  mov     r9d, eax; char *
0x1802de3e6  lea     r8, aClientcoreTerm_41; "clientcore\\termsrv\\client\\plugins\\d"...
0x1802de3ed  mov     edx, 1C0h; void *
  ... truncated ...
```
