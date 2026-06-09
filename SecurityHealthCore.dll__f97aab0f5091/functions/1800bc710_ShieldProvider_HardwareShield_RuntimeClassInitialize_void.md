# ShieldProvider::HardwareShield::RuntimeClassInitialize(void)

- ea: `0x1800bc710`
- end: `0x1800bcd53`
- name: `?RuntimeClassInitialize@HardwareShield@ShieldProvider@@QEAAJXZ`
- size: `1603`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800881ec`

## callees

- `0x180001a1c`
- `0x1800034bc`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001c9f8`
- `0x1800894e0`
- `0x18009412c`
- `0x1800b2f6c`
- `0x1800b4a00`
- `0x1800b7fe8`
- `0x1800b81ac`
- `0x1800baa20`
- `0x1800bc0c4`
- `0x1800bc710`
- `0x1800bdd14`
- `0x1800d5b08`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800bc91d`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800bc91d`

## string_xrefs

- `0x1800bc818`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\hardwareshield\hardwareshield.cpp`
- `0x1800bc843`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\hardwareshield\hardwareshield.cpp`
- `0x1800bc86e`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\hardwareshield\hardwareshield.cpp`
- `0x1800bc895`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\hardwareshield\hardwareshield.cpp`
- `0x1800bc986`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\hardwareshield\hardwareshield.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::HardwareShield::RuntimeClassInitialize(ShieldProvider::HardwareShield *this)
{
  ShieldProvider::HardwareShield *v2; // rcx
  int v3; // eax
  unsigned int v4; // esi
  int *v5; // rdx
  __int64 v6; // rdx
  ShieldProvider::HardwareShield *v7; // rcx
  int IsLsaPplInAutoEnableTrialPeriod; // eax
  ShieldProvider::HardwareShield *v9; // rcx
  int v10; // r12d
  int v11; // eax
  ShieldProvider::HardwareShield *v12; // rcx
  int v13; // r14d
  int v14; // eax
  ShieldProvider::HardwareShield *v15; // rcx
  int v16; // r15d
  int IsClientSku; // eax
  int v18; // esi
  int v19; // eax
  ShieldProvider::HardwareShield *v20; // rcx
  __int64 v21; // rdx
  ShieldProvider::HardwareShield *v22; // rcx
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v29; // [rsp+20h] [rbp-1A0h]
  int v30; // [rsp+140h] [rbp-80h] BYREF
  int v31; // [rsp+144h] [rbp-7Ch] BYREF
  int v32; // [rsp+148h] [rbp-78h] BYREF
  int v33; // [rsp+14Ch] [rbp-74h] BYREF
  int v34; // [rsp+150h] [rbp-70h] BYREF
  int v35; // [rsp+154h] [rbp-6Ch] BYREF
  int v36; // [rsp+158h] [rbp-68h] BYREF
  int v37; // [rsp+15Ch] [rbp-64h] BYREF
  int v38; // [rsp+160h] [rbp-60h] BYREF
  int v39; // [rsp+164h] [rbp-5Ch] BYREF
  int v40; // [rsp+168h] [rbp-58h] BYREF
  int v41; // [rsp+16Ch] [rbp-54h] BYREF
  int v42; // [rsp+170h] [rbp-50h] BYREF
  int v43; // [rsp+174h] [rbp-4Ch] BYREF
  int v44; // [rsp+178h] [rbp-48h] BYREF
  int v45; // [rsp+17Ch] [rbp-44h] BYREF
  int v46; // [rsp+180h] [rbp-40h] BYREF
  int v47; // [rsp+184h] [rbp-3Ch] BYREF
  int v48; // [rsp+188h] [rbp-38h] BYREF
  int v49; // [rsp+18Ch] [rbp-34h] BYREF
  int v50; // [rsp+190h] [rbp-30h] BYREF
  int v51; // [rsp+194h] [rbp-2Ch] BYREF
  int v52; // [rsp+198h] [rbp-28h] BYREF
  int v53; // [rsp+19Ch] [rbp-24h] BYREF
  int v54; // [rsp+1A0h] [rbp-20h] BYREF
  int v55; // [rsp+1A4h] [rbp-1Ch] BYREF
  int v56; // [rsp+1A8h] [rbp-18h] BYREF
  int v57; // [rsp+1ACh] [rbp-14h] BYREF
  int v58; // [rsp+1B0h] [rbp-10h] BYREF
  int v59; // [rsp+1B4h] [rbp-Ch] BYREF
  _BYTE v60[16]; // [rsp+1B8h] [rbp-8h] BYREF
  char v61; // [rsp+1C8h] [rbp+8h]
  __int64 v62; // [rsp+1D0h] [rbp+10h] BYREF
  __int64 v63; // [rsp+1D8h] [rbp+18h] BYREF
  __int64 v64[8]; // [rsp+1E0h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+68h]
  int v66; // [rsp+238h] [rbp+78h] BYREF
  int v67; // [rsp+240h] [rbp+80h] BYREF
  int v68; // [rsp+248h] [rbp+88h] BYREF

  v31 = 0;
  ShieldProvider::HardwareShield::RefreshPillarStatusEx(this, 1, &v31);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v60,
    &stru_18013A040);
  v61 = 1;
  if ( ShieldProvider::HardwareShield::m_fCheckedHvciStatePostBoot )
    goto LABEL_4;
  v3 = ShieldProvider::HardwareShield::CheckHvciStatePostBoot(v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    ShieldProvider::HardwareShield::m_fCheckedHvciStatePostBoot = 1;
LABEL_4:
    v61 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v60);
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v60,
      &stru_18013A040);
    if ( !ShieldProvider::HardwareShield::m_fCheckWcosProdConfigPostBoot )
    {
      v66 = 0;
      ShieldProvider::MpIsWcosProductionConfiguration((ShieldProvider *)&v66, v5);
      ShieldProvider::HardwareShield::m_fCheckWcosProdConfigPostBoot = 1;
    }
    v61 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v60);
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v60,
      &stru_18013A040);
    if ( !ShieldProvider::HardwareShield::m_lsaPplSubscription )
    {
      LOBYTE(v6) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::GetImpl'::`2'::impl,
        v6);
      v66 = 0;
      v67 = 1;
      v68 = 1;
      v30 = 1;
      IsLsaPplInAutoEnableTrialPeriod = ShieldProvider::HardwareShield::IsLsaPplInAutoEnableTrialPeriod(v7, &v66);
      v10 = IsLsaPplInAutoEnableTrialPeriod;
      if ( IsLsaPplInAutoEnableTrialPeriod < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16EE,
          (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\hardwareshield\\hardwareshield.cpp",
          (const char *)(unsigned int)IsLsaPplInAutoEnableTrialPeriod,
          v29);
      v11 = ShieldProvider::HardwareShield::WasPplConfigured(v9, &v67);
      v13 = v11;
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16F1,
          (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\hardwareshield\\hardwareshield.cpp",
          (const char *)(unsigned int)v11,
          v29);
      v14 = ShieldProvider::HardwareShield::LsaPplDownlevelCheck(v12, &v68);
      v16 = v14;
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16F4,
          (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\hardwareshield\\hardwareshield.cpp",
          (const char *)(unsigned int)v14,
          v29);
      IsClientSku = ShieldProvider::HardwareShield::IsClientSku(v15, &v30);
      v18 = IsClientSku;
      if ( IsClientSku < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16F7,
          (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\hardwareshield\\hardwareshield.cpp",
          (const char *)(unsigned int)IsClientSku,
          v29);
      if ( v10 >= 0 && v13 >= 0 && v16 >= 0 && v18 >= 0 )
      {
        if ( v66 )
        {
          if ( !v67 && !v68 )
          {
            if ( v30 )
            {
              v29 = (int)this;
              v19 = RtlSubscribeWnfStateChangeNotification(
                      &ShieldProvider::HardwareShield::m_lsaPplSubscription,
                      WNF_CI_LSAPPL_DLL_LOAD_FAILURE_AUDIT_MODE,
                      0,
                      ShieldProvider::HardwareShield::LogUnsignedDllCallback);
              if ( v19 < 0 )
              {
                v20 = (ShieldProvider::HardwareShield *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    400,
                    &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
                    (unsigned int)v19);
                ShieldProvider::HardwareShield::LogUnsignedDll(v20);
              }
            }
          }
        }
      }
    }
    v61 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v60);
    LOBYTE(v21) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::GetImpl'::`2'::impl,
      v21);
    v66 = 0;
    v23 = ShieldProvider::HardwareShield::LsaPplDownlevelCheck(v22, &v66);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x171C,
        (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\hardwareshield\\hardwareshield.cpp",
        (const char *)(unsigned int)v23,
        v29);
    if ( !v66 )
    {
      v24 = ShieldProvider::HardwareShield::AddressAutoEnableTrialState(this);
      if ( v24 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          401,
          &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
          (unsigned int)v24);
    }
    if ( (unsigned int)dword_18012F280 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18012F280, 0x800000000000LL) )
      {
        v67 = *((unsigned __int8 *)this + 166);
        LOBYTE(v66) = *((_BYTE *)this + 167);
        v68 = *((unsigned __int8 *)this + 165);
        v30 = *((unsigned __int8 *)this + 164);
        v62 = *((_QWORD *)this + 21);
        v32 = *((unsigned __int8 *)this + 163);
        v33 = *((unsigned __int8 *)this + 162);
        v63 = *((_QWORD *)this + 22);
        v34 = *((unsigned __int8 *)this + 161);
        v35 = *((unsigned __int8 *)this + 160);
        v36 = *((unsigned __int8 *)this + 159);
        v37 = *((unsigned __int8 *)this + 158);
        v38 = *((unsigned __int8 *)this + 157);
        v39 = *((unsigned __int8 *)this + 156);
        v40 = *((unsigned __int8 *)this + 155);
        v41 = *((unsigned __int8 *)this + 154);
        v42 = *((unsigned __int8 *)this + 153);
        v43 = *((unsigned __int8 *)this + 152);
        v44 = *((unsigned __int8 *)this + 151);
        v45 = *((unsigned __int8 *)this + 150);
        v46 = *((unsigned __int8 *)this + 149);
        v47 = *((unsigned __int8 *)this + 148);
        v48 = *((unsigned __int8 *)this + 147);
        v49 = *((unsigned __int8 *)this + 146);
        v50 = *((unsigned __int8 *)this + 145);
        v51 = *((unsigned __int8 *)this + 144);
        v52 = *((unsigned __int8 *)this + 143);
        v53 = *((unsigned __int8 *)this + 142);
        v54 = *((unsigned __int8 *)this + 141);
        v55 = *((unsigned __int8 *)this + 140);
        v56 = *((unsigned __int8 *)this + 139);
        v57 = *((unsigned __int8 *)this + 138);
        v58 = *((unsigned __int8 *)this + 137);
        v59 = *((unsigned __int8 *)this + 136);
        v64[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&byte_18012227F,
          v26,
          v27,
          (__int64)v64,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v55,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v51,
          (__int64)&v50,
          (__int64)&v49,
          (__int64)&v48,
          (__int64)&v47,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)&v63,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v62,
          (__int64)&v30,
          (__int64)&v68,
          (__int64)&v66,
          (__int64)&v67);
      }
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      399,
      &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
      (unsigned int)v3);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v60);
  return v4;
}

```

## disassembly

```asm
0x1800bc710  mov     [rsp-8+arg_0], rbx
0x1800bc715  push    rbp
0x1800bc716  push    rsi
0x1800bc717  push    rdi
0x1800bc718  push    r12
0x1800bc71a  push    r13
0x1800bc71c  push    r14
0x1800bc71e  push    r15
0x1800bc720  lea     rbp, [rsp-30h]
0x1800bc725  sub     rsp, 1F0h
0x1800bc72c  xor     r13d, r13d
0x1800bc72f  lea     r8, [rbp+60h+var_DC]; int *
0x1800bc733  mov     rbx, rcx
0x1800bc736  mov     [rbp+60h+var_DC], r13d
0x1800bc73a  lea     esi, [r13+1]
0x1800bc73e  mov     edx, esi; int
0x1800bc740  call    ?RefreshPillarStatusEx@HardwareShield@ShieldProvider@@AEAAJHPEAH@Z; ShieldProvider::HardwareShield::RefreshPillarStatusEx(int,int *)
0x1800bc745  lea     rdi, stru_18013A040
0x1800bc74c  mov     rdx, rdi
0x1800bc74f  lea     rcx, [rbp+60h+var_68]
0x1800bc753  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bc758  cmp     cs:?m_fCheckedHvciStatePostBoot@HardwareShield@ShieldProvider@@0_NA, r13b; bool ShieldProvider::HardwareShield::m_fCheckedHvciStatePostBoot
0x1800bc75f  mov     [rbp+60h+var_58], sil
0x1800bc763  jnz     short loc_1800BC77F
0x1800bc765  call    ?CheckHvciStatePostBoot@HardwareShield@ShieldProvider@@AEAAJXZ; ShieldProvider::HardwareShield::CheckHvciStatePostBoot(void)
0x1800bc76a  mov     esi, eax
0x1800bc76c  test    eax, eax
0x1800bc76e  js      loc_1800BCD15
0x1800bc774  lea     esi, [r13+1]
0x1800bc778  mov     cs:?m_fCheckedHvciStatePostBoot@HardwareShield@ShieldProvider@@0_NA, sil; bool ShieldProvider::HardwareShield::m_fCheckedHvciStatePostBoot
0x1800bc77f  lea     rcx, [rbp+60h+var_68]
0x1800bc783  mov     [rbp+60h+var_58], r13b
0x1800bc787  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bc78c  mov     rdx, rdi
0x1800bc78f  lea     rcx, [rbp+60h+var_68]
0x1800bc793  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bc798  cmp     cs:?m_fCheckWcosProdConfigPostBoot@HardwareShield@ShieldProvider@@0_NA, r13b; bool ShieldProvider::HardwareShield::m_fCheckWcosProdConfigPostBoot
0x1800bc79f  jnz     short loc_1800BC7B5
0x1800bc7a1  lea     rcx, [rbp+60h+arg_8]; this
0x1800bc7a5  mov     [rbp+60h+arg_8], r13d
0x1800bc7a9  call    ?MpIsWcosProductionConfiguration@ShieldProvider@@YAJPEAH@Z; ShieldProvider::MpIsWcosProductionConfiguration(int *)
0x1800bc7ae  mov     cs:?m_fCheckWcosProdConfigPostBoot@HardwareShield@ShieldProvider@@0_NA, sil; bool ShieldProvider::HardwareShield::m_fCheckWcosProdConfigPostBoot
0x1800bc7b5  lea     rcx, [rbp+60h+var_68]
0x1800bc7b9  mov     [rbp+60h+var_58], r13b
0x1800bc7bd  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bc7c2  mov     rdx, rdi
0x1800bc7c5  lea     rcx, [rbp+60h+var_68]
0x1800bc7c9  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bc7ce  cmp     cs:?m_lsaPplSubscription@HardwareShield@ShieldProvider@@0PEAU_WNF_USER_SUBSCRIPTION@@EA, r13; _WNF_USER_SUBSCRIPTION * ShieldProvider::HardwareShield::m_lsaPplSubscription
0x1800bc7d5  lea     rdi, WPP_GLOBAL_Control
0x1800bc7dc  jnz     loc_1800BC956
0x1800bc7e2  mov     dl, sil
0x1800bc7e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnablePplOnUpgrade@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnablePplOnUpgrade@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePplOnUpgrade> `wil::Feature<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::GetImpl(void)'::`2'::impl
0x1800bc7ec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnablePplOnUpgrade@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bc7f1  lea     rdx, [rbp+60h+arg_8]; int *
0x1800bc7f5  mov     [rbp+60h+arg_8], r13d
0x1800bc7f9  mov     [rbp+60h+arg_10], esi
0x1800bc7ff  mov     [rbp+60h+arg_18], esi
0x1800bc805  mov     [rbp+60h+var_E0], esi
0x1800bc808  call    ?IsLsaPplInAutoEnableTrialPeriod@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::IsLsaPplInAutoEnableTrialPeriod(int *)
0x1800bc80d  mov     r12d, eax
0x1800bc810  test    eax, eax
0x1800bc812  jns     short loc_1800BC82C
0x1800bc814  mov     rcx, [rbp+68h]; this
0x1800bc818  lea     r8, aOnecoreAmcoreA_0; "onecore\\amcore\\antimalware\\source\\s"...
0x1800bc81f  mov     r9d, eax; char *
0x1800bc822  mov     edx, 16EEh; void *
0x1800bc827  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc82c  lea     rdx, [rbp+60h+arg_10]; int *
0x1800bc833  call    ?WasPplConfigured@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::WasPplConfigured(int *)
0x1800bc838  mov     r14d, eax
0x1800bc83b  test    eax, eax
0x1800bc83d  jns     short loc_1800BC857
0x1800bc83f  mov     rcx, [rbp+68h]; this
0x1800bc843  lea     r8, aOnecoreAmcoreA_0; "onecore\\amcore\\antimalware\\source\\s"...
0x1800bc84a  mov     r9d, eax; char *
0x1800bc84d  mov     edx, 16F1h; void *
0x1800bc852  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc857  lea     rdx, [rbp+60h+arg_18]; int *
0x1800bc85e  call    ?LsaPplDownlevelCheck@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::LsaPplDownlevelCheck(int *)
0x1800bc863  mov     r15d, eax
0x1800bc866  test    eax, eax
0x1800bc868  jns     short loc_1800BC882
0x1800bc86a  mov     rcx, [rbp+68h]; this
0x1800bc86e  lea     r8, aOnecoreAmcoreA_0; "onecore\\amcore\\antimalware\\source\\s"...
0x1800bc875  mov     r9d, eax; char *
0x1800bc878  mov     edx, 16F4h; void *
0x1800bc87d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc882  lea     rdx, [rbp+60h+var_E0]; int *
0x1800bc886  call    ?IsClientSku@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::IsClientSku(int *)
0x1800bc88b  mov     esi, eax
0x1800bc88d  test    eax, eax
0x1800bc88f  jns     short loc_1800BC8A9
0x1800bc891  mov     rcx, [rbp+68h]; this
0x1800bc895  lea     r8, aOnecoreAmcoreA_0; "onecore\\amcore\\antimalware\\source\\s"...
0x1800bc89c  mov     r9d, eax; char *
0x1800bc89f  mov     edx, 16F7h; void *
0x1800bc8a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc8a9  test    r12d, r12d
0x1800bc8ac  js      loc_1800BC956
0x1800bc8b2  test    r14d, r14d
0x1800bc8b5  js      loc_1800BC956
0x1800bc8bb  test    r15d, r15d
0x1800bc8be  js      loc_1800BC956
0x1800bc8c4  test    esi, esi
0x1800bc8c6  js      loc_1800BC956
0x1800bc8cc  cmp     [rbp+60h+arg_8], r13d
0x1800bc8d0  jz      loc_1800BC956
0x1800bc8d6  cmp     [rbp+60h+arg_10], r13d
0x1800bc8dd  jnz     short loc_1800BC956
0x1800bc8df  cmp     [rbp+60h+arg_18], r13d
0x1800bc8e6  jnz     short loc_1800BC956
0x1800bc8e8  cmp     [rbp+60h+var_E0], r13d
0x1800bc8ec  jz      short loc_1800BC956
0x1800bc8ee  mov     rdx, cs:WNF_CI_LSAPPL_DLL_LOAD_FAILURE_AUDIT_MODE
0x1800bc8f5  lea     r9, ?LogUnsignedDllCallback@HardwareShield@ShieldProvider@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; ShieldProvider::HardwareShield::LogUnsignedDllCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800bc8fc  mov     dword ptr [rsp+220h+var_1E8], 1
0x1800bc904  lea     rcx, ?m_lsaPplSubscription@HardwareShield@ShieldProvider@@0PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * ShieldProvider::HardwareShield::m_lsaPplSubscription
0x1800bc90b  mov     dword ptr [rsp+220h+var_1F0], r13d
0x1800bc910  xor     r8d, r8d
0x1800bc913  mov     [rsp+220h+var_1F8], r13
0x1800bc918  mov     qword ptr [rsp+220h+var_200], rbx; int
0x1800bc91d  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800bc923  test    eax, eax
0x1800bc925  jns     short loc_1800BC956
0x1800bc927  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc92e  cmp     rcx, rdi
0x1800bc931  jz      short loc_1800BC951
0x1800bc933  test    byte ptr [rcx+1Ch], 2
0x1800bc937  jz      short loc_1800BC951
0x1800bc939  mov     rcx, [rcx+10h]
0x1800bc93d  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800bc944  mov     edx, 190h
0x1800bc949  mov     r9d, eax
0x1800bc94c  call    WPP_SF_d
0x1800bc951  call    ?LogUnsignedDll@HardwareShield@ShieldProvider@@AEAAJXZ; ShieldProvider::HardwareShield::LogUnsignedDll(void)
0x1800bc956  lea     rcx, [rbp+60h+var_68]
0x1800bc95a  mov     [rbp+60h+var_58], r13b
0x1800bc95e  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bc963  mov     dl, 1
0x1800bc965  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnablePplOnUpgrade@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnablePplOnUpgrade@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePplOnUpgrade> `wil::Feature<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::GetImpl(void)'::`2'::impl
0x1800bc96c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnablePplOnUpgrade@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnablePplOnUpgrade>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bc971  lea     rdx, [rbp+60h+arg_8]; int *
0x1800bc975  mov     [rbp+60h+arg_8], r13d
0x1800bc979  call    ?LsaPplDownlevelCheck@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::LsaPplDownlevelCheck(int *)
0x1800bc97e  test    eax, eax
0x1800bc980  jns     short loc_1800BC99A
0x1800bc982  mov     rcx, [rbp+68h]; this
0x1800bc986  lea     r8, aOnecoreAmcoreA_0; "onecore\\amcore\\antimalware\\source\\s"...
0x1800bc98d  mov     r9d, eax; char *
0x1800bc990  mov     edx, 171Ch; void *
0x1800bc995  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc99a  cmp     [rbp+60h+arg_8], r13d
0x1800bc99e  jnz     short loc_1800BC9D6
0x1800bc9a0  mov     rcx, rbx; this
0x1800bc9a3  call    ?AddressAutoEnableTrialState@HardwareShield@ShieldProvider@@AEAAJXZ; ShieldProvider::HardwareShield::AddressAutoEnableTrialState(void)
0x1800bc9a8  test    eax, eax
0x1800bc9aa  jns     short loc_1800BC9D6
0x1800bc9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bc9b3  cmp     rcx, rdi
0x1800bc9b6  jz      short loc_1800BC9D6
0x1800bc9b8  test    byte ptr [rcx+1Ch], 1
0x1800bc9bc  jz      short loc_1800BC9D6
0x1800bc9be  mov     rcx, [rcx+10h]
0x1800bc9c2  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800bc9c9  mov     edx, 191h
0x1800bc9ce  mov     r9d, eax
0x1800bc9d1  call    WPP_SF_d
0x1800bc9d6  mov     eax, cs:dword_18012F280
0x1800bc9dc  cmp     eax, 5
0x1800bc9df  jbe     loc_1800BCCF8
0x1800bc9e5  mov     rdx, 800000000000h
0x1800bc9ef  lea     rcx, dword_18012F280
0x1800bc9f6  call    _tlgKeywordOn
0x1800bc9fb  test    al, al
0x1800bc9fd  jz      loc_1800BCCF8
0x1800bca03  movzx   eax, byte ptr [rbx+0A6h]
0x1800bca0a  mov     [rbp+60h+arg_10], eax
0x1800bca10  mov     al, [rbx+0A7h]
0x1800bca16  mov     byte ptr [rbp+60h+arg_8], al
0x1800bca19  movzx   eax, byte ptr [rbx+0A5h]
0x1800bca20  mov     [rbp+60h+arg_18], eax
0x1800bca26  movzx   eax, byte ptr [rbx+0A4h]
0x1800bca2d  mov     [rbp+60h+var_E0], eax
0x1800bca30  mov     rax, [rbx+0A8h]
0x1800bca37  mov     [rbp+60h+var_50], rax
0x1800bca3b  movzx   eax, byte ptr [rbx+0A3h]
0x1800bca42  mov     [rbp+60h+var_D8], eax
0x1800bca45  movzx   eax, byte ptr [rbx+0A2h]
0x1800bca4c  mov     [rbp+60h+var_D4], eax
0x1800bca4f  mov     rax, [rbx+0B0h]
0x1800bca56  mov     [rbp+60h+var_48], rax
0x1800bca5a  movzx   eax, byte ptr [rbx+0A1h]
0x1800bca61  mov     [rbp+60h+var_D0], eax
0x1800bca64  movzx   eax, byte ptr [rbx+0A0h]
0x1800bca6b  mov     [rbp+60h+var_CC], eax
0x1800bca6e  movzx   eax, byte ptr [rbx+9Fh]
0x1800bca75  mov     [rbp+60h+var_C8], eax
0x1800bca78  movzx   eax, byte ptr [rbx+9Eh]
0x1800bca7f  mov     [rbp+60h+var_C4], eax
0x1800bca82  movzx   eax, byte ptr [rbx+9Dh]
0x1800bca89  mov     [rbp+60h+var_C0], eax
0x1800bca8c  movzx   eax, byte ptr [rbx+9Ch]
0x1800bca93  mov     [rbp+60h+var_BC], eax
0x1800bca96  movzx   eax, byte ptr [rbx+9Bh]
0x1800bca9d  mov     [rbp+60h+var_B8], eax
0x1800bcaa0  movzx   eax, byte ptr [rbx+9Ah]
0x1800bcaa7  mov     [rbp+60h+var_B4], eax
0x1800bcaaa  movzx   eax, byte ptr [rbx+99h]
0x1800bcab1  mov     [rbp+60h+var_B0], eax
0x1800bcab4  movzx   eax, byte ptr [rbx+98h]
0x1800bcabb  mov     [rbp+60h+var_AC], eax
0x1800bcabe  movzx   eax, byte ptr [rbx+97h]
0x1800bcac5  mov     [rbp+60h+var_A8], eax
0x1800bcac8  movzx   eax, byte ptr [rbx+96h]
0x1800bcacf  mov     [rbp+60h+var_A4], eax
0x1800bcad2  movzx   eax, byte ptr [rbx+95h]
0x1800bcad9  mov     [rbp+60h+var_A0], eax
0x1800bcadc  movzx   eax, byte ptr [rbx+94h]
0x1800bcae3  mov     [rbp+60h+var_9C], eax
0x1800bcae6  movzx   eax, byte ptr [rbx+93h]
0x1800bcaed  mov     [rbp+60h+var_98], eax
0x1800bcaf0  movzx   eax, byte ptr [rbx+92h]
0x1800bcaf7  mov     [rbp+60h+var_94], eax
0x1800bcafa  movzx   eax, byte ptr [rbx+91h]
0x1800bcb01  mov     [rbp+60h+var_90], eax
0x1800bcb04  movzx   eax, byte ptr [rbx+90h]
0x1800bcb0b  mov     [rbp+60h+var_8C], eax
0x1800bcb0e  movzx   eax, byte ptr [rbx+8Fh]
0x1800bcb15  mov     [rbp+60h+var_88], eax
0x1800bcb18  movzx   eax, byte ptr [rbx+8Eh]
0x1800bcb1f  mov     [rbp+60h+var_84], eax
0x1800bcb22  movzx   eax, byte ptr [rbx+8Dh]
0x1800bcb29  mov     [rbp+60h+var_80], eax
0x1800bcb2c  movzx   eax, byte ptr [rbx+8Ch]
0x1800bcb33  mov     [rbp+60h+var_7C], eax
0x1800bcb36  movzx   eax, byte ptr [rbx+8Bh]
0x1800bcb3d  mov     [rbp+60h+var_78], eax
0x1800bcb40  movzx   eax, byte ptr [rbx+8Ah]
0x1800bcb47  mov     [rbp+60h+var_74], eax
0x1800bcb4a  movzx   eax, byte ptr [rbx+89h]
0x1800bcb51  mov     [rbp+60h+var_70], eax
0x1800bcb54  movzx   eax, byte ptr [rbx+88h]
0x1800bcb5b  mov     [rbp+60h+var_6C], eax
0x1800bcb5e  lea     rax, [rbp+60h+arg_10]
0x1800bcb65  mov     [rsp+220h+var_F0], rax
0x1800bcb6d  lea     rax, [rbp+60h+arg_8]
0x1800bcb71  mov     [rsp+220h+var_F8], rax
0x1800bcb79  lea     rax, [rbp+60h+arg_18]
0x1800bcb80  mov     [rsp+220h+var_100], rax
0x1800bcb88  lea     rax, [rbp+60h+var_E0]
0x1800bcb8c  mov     [rsp+220h+var_108], rax
0x1800bcb94  lea     rax, [rbp+60h+var_50]
0x1800bcb98  mov     [rsp+220h+var_110], rax
0x1800bcba0  lea     rax, [rbp+60h+var_D8]
0x1800bcba4  mov     [rsp+220h+var_118], rax
0x1800bcbac  mov     [rbp+60h+var_40], 1000000h
0x1800bcbb4  lea     rax, [rbp+60h+var_D4]
0x1800bcbb8  mov     [rsp+220h+var_120], rax
0x1800bcbc0  lea     rdx, byte_18012227F
0x1800bcbc7  lea     rax, [rbp+60h+var_48]
0x1800bcbcb  mov     [rsp+220h+var_128], rax
0x1800bcbd3  lea     rax, [rbp+60h+var_D0]
0x1800bcbd7  mov     [rsp+220h+var_130], rax
0x1800bcbdf  lea     rax, [rbp+60h+var_CC]
0x1800bcbe3  mov     [rsp+220h+var_138], rax
0x1800bcbeb  lea     rax, [rbp+60h+var_C8]
0x1800bcbef  mov     [rsp+220h+var_140], rax
0x1800bcbf7  lea     rax, [rbp+60h+var_C4]
0x1800bcbfb  mov     [rsp+220h+var_148], rax
0x1800bcc03  lea     rax, [rbp+60h+var_C0]
0x1800bcc07  mov     [rsp+220h+var_150], rax
0x1800bcc0f  lea     rax, [rbp+60h+var_BC]
0x1800bcc13  mov     [rsp+220h+var_158], rax
0x1800bcc1b  lea     rax, [rbp+60h+var_B8]
0x1800bcc1f  mov     [rsp+220h+var_160], rax
0x1800bcc27  lea     rax, [rbp+60h+var_B4]
0x1800bcc2b  mov     [rsp+220h+var_168], rax
0x1800bcc33  lea     rax, [rbp+60h+var_B0]
0x1800bcc37  mov     [rsp+220h+var_170], rax
0x1800bcc3f  lea     rax, [rbp+60h+var_AC]
0x1800bcc43  mov     [rsp+220h+var_178], rax
0x1800bcc4b  lea     rax, [rbp+60h+var_A8]
0x1800bcc4f  mov     [rsp+220h+var_180], rax
0x1800bcc57  lea     rax, [rbp+60h+var_A4]
0x1800bcc5b  mov     [rsp+220h+var_188], rax
0x1800bcc63  lea     rax, [rbp+60h+var_A0]
0x1800bcc67  mov     [rsp+220h+var_190], rax
0x1800bcc6f  lea     rax, [rbp+60h+var_9C]
0x1800bcc73  mov     [rsp+220h+var_198], rax
0x1800bcc7b  lea     rax, [rbp+60h+var_98]
0x1800bcc7f  mov     [rsp+220h+var_1A0], rax
0x1800bcc87  lea     rax, [rbp+60h+var_94]
0x1800bcc8b  mov     [rsp+220h+var_1A8], rax
0x1800bcc90  lea     rax, [rbp+60h+var_90]
0x1800bcc94  mov     [rsp+220h+var_1B0], rax
0x1800bcc99  lea     rax, [rbp+60h+var_8C]
0x1800bcc9d  mov     [rsp+220h+var_1B8], rax
0x1800bcca2  lea     rax, [rbp+60h+var_88]
0x1800bcca6  mov     [rsp+220h+var_1C0], rax
  ... truncated ...
```
