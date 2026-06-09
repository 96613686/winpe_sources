# Wallet::WalletLocationManager::CreateGeofence(__MIDL___MIDL_itf_wallettypes_0000_0000_0001,ATL::CComPtr<IWalletItem> &,ATL::CComPtr<Windows::Devices::Geolocation::Geofencing::IGeofence> &)

- ea: `0x180014d28`
- end: `0x1800150c4`
- name: `?CreateGeofence@WalletLocationManager@Wallet@@CAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@AEAV?$CComPtr@UIWalletItem@@@ATL@@AEAV?$CComPtr@UIGeofence@Geofencing@Geolocation@Devices@Windows@@@5@@Z`
- size: `924`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016910`
- `0x180016b60`

## callees

- `0x180003ae4`
- `0x180008cc0`
- `0x18001416c`
- `0x1800141b8`
- `0x180014510`
- `0x180014d28`
- `0x1800159ac`
- `0x180015d2c`
- `0x180015db4`
- `0x180016e78`
- `0x180036a8c`
- `0x180036ae0`
- `0x180036ec8`
- `0x1800376c0`
- `0x180039058`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015055`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015055`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014e07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014edc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014e07`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014edc`

## string_xrefs

- `0x180014f97`: `Wallet::WalletLocationManager::CreateGeofence`
- `0x180014f85`: `Created geofence %S for wallet location item %I64x, latitude %f, longitude %f, altitude %f, radius %f, dwell time %fs`

## pseudocode

```c
__int64 __fastcall Wallet::WalletLocationManager::CreateGeofence(
        unsigned int a1,
        const unsigned __int16 *a2,
        __int64 a3)
{
  const unsigned __int16 (*v6)[48]; // rdx
  int ActivationFactory; // edi
  double RadiusOfWalletItemType; // xmm6_8
  __int64 DwellTimeOfWalletItemType; // rbx
  __int64 v10; // xmm7_8
  __int64 v11; // xmm8_8
  __int64 v12; // xmm9_8
  __int64 v13; // rax
  __int64 v14; // r8
  unsigned __int16 *v15; // rdx
  unsigned int v16; // r8d
  __int64 v17; // r8
  int v18; // eax
  struct IWalletItem *v19; // rdx
  Wallet::Utils *v20; // rcx
  unsigned __int64 WalletItemId; // rax
  int v22; // ebx
  char v24; // [rsp+28h] [rbp-E0h]
  __int64 v25; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING v26; // [rsp+70h] [rbp-98h] BYREF
  __int64 v27; // [rsp+78h] [rbp-90h] BYREF
  __int64 v28; // [rsp+80h] [rbp-88h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-80h] BYREF
  __int64 *v30; // [rsp+90h] [rbp-78h] BYREF
  __int64 v31; // [rsp+98h] [rbp-70h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v33[4]; // [rsp+A8h] [rbp-60h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-40h] BYREF
  HSTRING v35; // [rsp+E8h] [rbp-20h] BYREF
  OLECHAR sz[40]; // [rsp+108h] [rbp+0h] BYREF

  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[38])a2);
  Windows::Internal::StringReference::StringReference(&v35, v6);
  memset_0(sz, 0, sizeof(sz));
  v31 = 0;
  v25 = 0;
  v32 = 0;
  OrderedLockBase<enum WalletLockOrder>::lock(&qword_18006C0E8);
  if ( (int)((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))Wallet::Utils::GetTDoubleProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>)(
              *(_QWORD *)a2,
              40004,
              &v25) < 0 )
  {
    RadiusOfWalletItemType = GetRadiusOfWalletItemType(a1);
    DwellTimeOfWalletItemType = GetDwellTimeOfWalletItemType();
    ActivationFactory = RoGetActivationFactory(string, &GUID_afd6531f_72b1_4f7d_87cc_4ed4c9849c05, &v30);
    if ( ActivationFactory >= 0 )
    {
      ActivationFactory = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))Wallet::Utils::GetTDoubleProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>)(
                            *(_QWORD *)a2,
                            40001,
                            &v31);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))Wallet::Utils::GetTDoubleProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>)(
                              *(_QWORD *)a2,
                              40002,
                              &v25);
        if ( ActivationFactory >= 0 )
        {
          Wallet::Utils::GetTDoubleProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
            *(_QWORD *)a2,
            40003,
            &v32);
          v10 = v31;
          v11 = v25;
          v12 = v32;
          v13 = *v30;
          v33[0] = v31;
          v33[1] = v25;
          v33[2] = v32;
          ActivationFactory = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v13 + 48))(
                                v30,
                                v33,
                                v14,
                                &v29);
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = (**v29)(v29, &GUID_c99ca2af_c729_43c1_8fab_d6dec914df7e, &v28);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = RoGetActivationFactory(v35, &GUID_841f624b_325f_4b90_bca7_2b8022a93796, &v27);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = Wallet::Utils::CreateGuid(sz, v15, v16);
                if ( ActivationFactory >= 0 )
                {
                  v17 = -1;
                  do
                    ++v17;
                  while ( sz[v17] );
                  ActivationFactory = Windows::Internal::String::Initialize((Windows::Internal::String *)&v26, sz, v17);
                  if ( ActivationFactory >= 0 )
                  {
                    ActivationFactory = Wallet::Utils::SetTStringProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                                          *(_QWORD *)a2,
                                          40004,
                                          sz);
                    if ( ActivationFactory >= 0 )
                    {
                      v24 = 0;
                      v18 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64, char, __int64, __int64))(*(_QWORD *)v27 + 64LL))(
                              v27,
                              v26,
                              v28,
                              3,
                              v24,
                              DwellTimeOfWalletItemType,
                              a3);
                      v20 = *(Wallet::Utils **)a2;
                      ActivationFactory = v18;
                      if ( v18 < 0 )
                      {
                        Wallet::Utils::DeleteTProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                          (__int64)v20,
                          40004);
                      }
                      else
                      {
                        WalletItemId = Wallet::Utils::GetWalletItemId(v20, v19);
                        wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
                          5,
                          "Wallet::WalletLocationManager::CreateGeofence",
                          651,
                          "Created geofence %S for wallet location item %I64x, latitude %f, longitude %f, altitude %f, ra"
                          "dius %f, dwell time %fs",
                          (const char *)sz,
                          WalletItemId,
                          v10,
                          v11,
                          v12,
                          RadiusOfWalletItemType,
                          (float)((float)(int)DwellTimeOfWalletItemType / 10000000.0));
                        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 144LL))(*(_QWORD *)a2);
                        ActivationFactory = 0;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    ActivationFactory = -2147418113;
  }
  v22 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (*(unsigned int (__fastcall **)(__int64 *))qword_18006C0E8)(&qword_18006C0E8) != v22 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection(&stru_18006C0F0);
  Windows::Internal::String::~String(&v26);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v27);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v28);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v29);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v30);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180014d28  mov     rax, rsp
0x180014d2b  mov     [rax+20h], rbx
0x180014d2f  push    rbp
0x180014d30  push    rsi
0x180014d31  push    rdi
0x180014d32  push    r14
0x180014d34  push    r15
0x180014d36  lea     rbp, [rax-0C8h]
0x180014d3d  sub     rsp, 1A0h
0x180014d44  movaps  xmmword ptr [rax-38h], xmm6
0x180014d48  movaps  xmmword ptr [rax-48h], xmm7
0x180014d4c  movaps  xmmword ptr [rax-58h], xmm8
0x180014d51  movaps  xmmword ptr [rax-68h], xmm9
0x180014d56  mov     rax, cs:__security_cookie
0x180014d5d  xor     rax, rsp
0x180014d60  mov     [rbp+0C0h+var_70], rax
0x180014d64  xor     r15d, r15d
0x180014d67  mov     ebx, ecx
0x180014d69  lea     rcx, [rbp+0C0h+string]; string
0x180014d6d  mov     [rbp+0C0h+var_138], r15
0x180014d71  mov     [rbp+0C0h+var_140], r15
0x180014d75  mov     r14, r8
0x180014d78  mov     [rsp+1C0h+var_148], r15
0x180014d7d  mov     rsi, rdx
0x180014d80  mov     [rsp+1C0h+var_150], r15
0x180014d85  mov     [rsp+1C0h+var_158], r15
0x180014d8a  call    ??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[38])
0x180014d8f  lea     rcx, [rbp+0C0h+var_E0]; string
0x180014d93  call    ??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[48])
0x180014d98  xor     edx, edx; Val
0x180014d9a  lea     r8d, [r15+50h]; Size
0x180014d9e  lea     rcx, [rbp+0C0h+sz]; void *
0x180014da2  call    memset_0
0x180014da7  xorps   xmm0, xmm0
0x180014daa  lea     rcx, qword_18006C0E8
0x180014db1  movsd   [rbp+0C0h+var_130], xmm0
0x180014db6  movsd   [rsp+1C0h+var_160], xmm0
0x180014dbc  movsd   [rbp+0C0h+var_128], xmm0
0x180014dc1  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180014dc6  mov     rcx, [rsi]
0x180014dc9  lea     r8, [rsp+1C0h+var_160]
0x180014dce  mov     edx, 9C44h
0x180014dd3  call    ??$GetTDoubleProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAN@Z; Wallet::Utils::GetTDoubleProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,double *)
0x180014dd8  test    eax, eax
0x180014dda  js      short loc_180014DE6
0x180014ddc  mov     edi, 8000FFFFh
0x180014de1  jmp     loc_180015002
0x180014de6  mov     ecx, ebx
0x180014de8  call    ?GetRadiusOfWalletItemType@@YANW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@@Z; GetRadiusOfWalletItemType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001)
0x180014ded  movaps  xmm6, xmm0
0x180014df0  call    ?GetDwellTimeOfWalletItemType@@YA?AUTimeSpan@Foundation@Windows@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@@Z; GetDwellTimeOfWalletItemType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001)
0x180014df5  mov     rcx, [rbp+0C0h+string]
0x180014df9  lea     r8, [rbp+0C0h+var_138]
0x180014dfd  lea     rdx, _GUID_afd6531f_72b1_4f7d_87cc_4ed4c9849c05
0x180014e04  mov     rbx, rax
0x180014e07  call    cs:__imp_RoGetActivationFactory
0x180014e0d  mov     edi, eax
0x180014e0f  test    eax, eax
0x180014e11  js      loc_180015002
0x180014e17  mov     rcx, [rsi]
0x180014e1a  lea     r8, [rbp+0C0h+var_130]
0x180014e1e  mov     edx, 9C41h
0x180014e23  call    ??$GetTDoubleProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAN@Z; Wallet::Utils::GetTDoubleProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,double *)
0x180014e28  mov     edi, eax
0x180014e2a  test    eax, eax
0x180014e2c  js      loc_180015002
0x180014e32  mov     rcx, [rsi]
0x180014e35  lea     r8, [rsp+1C0h+var_160]
0x180014e3a  mov     edx, 9C42h
0x180014e3f  call    ??$GetTDoubleProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAN@Z; Wallet::Utils::GetTDoubleProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,double *)
0x180014e44  mov     edi, eax
0x180014e46  test    eax, eax
0x180014e48  js      loc_180015002
0x180014e4e  mov     rcx, [rsi]
0x180014e51  lea     r8, [rbp+0C0h+var_128]
0x180014e55  mov     edx, 9C43h
0x180014e5a  call    ??$GetTDoubleProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAN@Z; Wallet::Utils::GetTDoubleProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,double *)
0x180014e5f  mov     rcx, [rbp+0C0h+var_138]
0x180014e63  lea     r9, [rbp+0C0h+var_140]
0x180014e67  movsd   xmm7, [rbp+0C0h+var_130]
0x180014e6c  lea     rdx, [rbp+0C0h+var_120]
0x180014e70  movsd   xmm8, [rsp+1C0h+var_160]
0x180014e77  movaps  xmm2, xmm6
0x180014e7a  movsd   xmm9, [rbp+0C0h+var_128]
0x180014e80  mov     rax, [rcx]
0x180014e83  movsd   [rbp+0C0h+var_120], xmm7
0x180014e88  movsd   [rbp+0C0h+var_118], xmm8
0x180014e8e  movsd   [rbp+0C0h+var_110], xmm9
0x180014e94  mov     rax, [rax+30h]
0x180014e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e9d  mov     edi, eax
0x180014e9f  test    eax, eax
0x180014ea1  js      loc_180015002
0x180014ea7  mov     rcx, [rbp+0C0h+var_140]
0x180014eab  lea     r8, [rsp+1C0h+var_148]
0x180014eb0  lea     rdx, _GUID_c99ca2af_c729_43c1_8fab_d6dec914df7e
0x180014eb7  mov     rax, [rcx]
0x180014eba  mov     rax, [rax]
0x180014ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec2  mov     edi, eax
0x180014ec4  test    eax, eax
0x180014ec6  js      loc_180015002
0x180014ecc  mov     rcx, [rbp+0C0h+var_E0]
0x180014ed0  lea     r8, [rsp+1C0h+var_150]
0x180014ed5  lea     rdx, _GUID_841f624b_325f_4b90_bca7_2b8022a93796
0x180014edc  call    cs:__imp_RoGetActivationFactory
0x180014ee2  mov     edi, eax
0x180014ee4  test    eax, eax
0x180014ee6  js      loc_180015002
0x180014eec  lea     rcx, [rbp+0C0h+sz]; lpsz
0x180014ef0  call    ?CreateGuid@Utils@Wallet@@YAJPEAGI@Z; Wallet::Utils::CreateGuid(ushort *,uint)
0x180014ef5  mov     edi, eax
0x180014ef7  test    eax, eax
0x180014ef9  js      loc_180015002
0x180014eff  lea     rax, [rbp+0C0h+sz]
0x180014f03  or      r8, 0FFFFFFFFFFFFFFFFh
0x180014f07  inc     r8; unsigned int
0x180014f0a  cmp     [rax+r8*2], r15w
0x180014f0f  jnz     short loc_180014F07
0x180014f11  lea     rdx, [rbp+0C0h+sz]; unsigned __int16 *
0x180014f15  lea     rcx, [rsp+1C0h+var_158]; this
0x180014f1a  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x180014f1f  mov     edi, eax
0x180014f21  test    eax, eax
0x180014f23  js      loc_180015002
0x180014f29  mov     rcx, [rsi]
0x180014f2c  lea     r8, [rbp+0C0h+sz]
0x180014f30  mov     edx, 9C44h
0x180014f35  call    ??$SetTStringProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z; Wallet::Utils::SetTStringProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)
0x180014f3a  mov     edi, eax
0x180014f3c  test    eax, eax
0x180014f3e  js      loc_180015002
0x180014f44  mov     rcx, [rsp+1C0h+var_150]
0x180014f49  mov     r9d, 3
0x180014f4f  mov     r8, [rsp+1C0h+var_148]
0x180014f54  mov     rdx, [rsp+1C0h+var_158]
0x180014f59  mov     [rsp+1C0h+var_190], r14
0x180014f5e  mov     rax, [rcx]
0x180014f61  mov     [rsp+1C0h+var_198], rbx
0x180014f66  mov     byte ptr [rsp+1C0h+var_1A0], r15b
0x180014f6b  mov     rax, [rax+40h]
0x180014f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f74  mov     rcx, [rsi]; this
0x180014f77  mov     edi, eax
0x180014f79  test    eax, eax
0x180014f7b  js      short loc_180014FF8
0x180014f7d  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x180014f82  xorps   xmm0, xmm0
0x180014f85  lea     r9, aCreatedGeofenc; "Created geofence %S for wallet location"...
0x180014f8c  cvtsi2ss xmm0, rbx
0x180014f91  mov     r8d, 28Bh
0x180014f97  lea     rdx, aWalletWalletlo_0; "Wallet::WalletLocationManager::CreateGe"...
0x180014f9e  mov     ecx, 5
0x180014fa3  divss   xmm0, cs:__real@4b189680
0x180014fab  cvtps2pd xmm0, xmm0
0x180014fae  movsd   [rsp+1C0h+var_170], xmm0
0x180014fb4  movsd   [rsp+1C0h+var_178], xmm6
0x180014fba  movsd   [rsp+1C0h+var_180], xmm9
0x180014fc1  movsd   [rsp+1C0h+var_188], xmm8
0x180014fc8  movsd   [rsp+1C0h+var_190], xmm7
0x180014fce  mov     [rsp+1C0h+var_198], rax
0x180014fd3  lea     rax, [rbp+0C0h+sz]
0x180014fd7  mov     [rsp+1C0h+var_1A0], rax
0x180014fdc  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180014fe1  mov     rcx, [rsi]
0x180014fe4  mov     rax, [rcx]
0x180014fe7  mov     rax, [rax+90h]
0x180014fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff3  mov     edi, r15d
0x180014ff6  jmp     short loc_180015002
0x180014ff8  mov     edx, 9C44h
0x180014ffd  call    ??$DeleteTProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; Wallet::Utils::DeleteTProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010)
0x180015002  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180015009  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180015010  mov     rax, [rax+8]
0x180015014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015019  mov     rdx, cs:qword_18006C0E8
0x180015020  lea     rcx, qword_18006C0E8
0x180015027  mov     ebx, eax
0x180015029  mov     rax, [rdx]
0x18001502c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015031  cmp     eax, ebx
0x180015033  jz      short loc_180015037
0x180015035  int     2Ch; Windows NT - assertion failure
0x180015037  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18001503e  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180015045  mov     rax, [rax+10h]
0x180015049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001504e  lea     rcx, stru_18006C0F0; lpCriticalSection
0x180015055  call    cs:__imp_LeaveCriticalSection
0x18001505b  lea     rcx, [rsp+1C0h+var_158]; this
0x180015060  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180015065  lea     rcx, [rsp+1C0h+var_150]
0x18001506a  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001506f  lea     rcx, [rsp+1C0h+var_148]
0x180015074  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180015079  lea     rcx, [rbp+0C0h+var_140]
0x18001507d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180015082  lea     rcx, [rbp+0C0h+var_138]
0x180015086  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001508b  mov     eax, edi
0x18001508d  mov     rcx, [rbp+0C0h+var_70]
0x180015091  xor     rcx, rsp; StackCookie
0x180015094  call    __security_check_cookie
0x180015099  lea     r11, [rsp+1C0h+var_20]
0x1800150a1  mov     rbx, [r11+48h]
0x1800150a5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800150aa  movaps  xmm7, xmmword ptr [r11-20h]
0x1800150af  movaps  xmm8, xmmword ptr [r11-30h]
0x1800150b4  movaps  xmm9, xmmword ptr [r11-40h]
0x1800150b9  mov     rsp, r11
0x1800150bc  pop     r15
0x1800150be  pop     r14
0x1800150c0  pop     rdi
0x1800150c1  pop     rsi
0x1800150c2  pop     rbp
0x1800150c3  retn
```
