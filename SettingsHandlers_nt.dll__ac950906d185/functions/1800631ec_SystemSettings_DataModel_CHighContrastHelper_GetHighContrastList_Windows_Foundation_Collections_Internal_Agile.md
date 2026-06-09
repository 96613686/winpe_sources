# SystemSettings::DataModel::CHighContrastHelper::GetHighContrastList(Windows::Foundation::Collections::Internal::AgileObservableVector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>> *)

- ea: `0x1800631ec`
- end: `0x1800634f3`
- name: `?GetHighContrastList@CHighContrastHelper@DataModel@SystemSettings@@QEAAJPEAV?$AgileObservableVector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@@Internal@Collections@Foundation@Windows@@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066978`

## callees

- `0x180011bb0`
- `0x180013d4c`
- `0x1800167dc`
- `0x1800212b0`
- `0x1800336b0`
- `0x18003d038`
- `0x180040000`
- `0x180046850`
- `0x1800631ec`
- `0x180065f28`
- `0x180066828`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800633cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800633cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800634cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800634cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063372`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800633e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063372`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800633e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800633a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800633a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::DataModel::CHighContrastHelper::GetHighContrastList(__int64 a1, __int64 a2)
{
  int SureHCThemesLoaded; // edi
  _QWORD *v4; // r14
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r12
  unsigned __int64 v7; // r15
  __int64 v8; // rbx
  _QWORD *v9; // rax
  unsigned __int64 i; // r15
  __int64 v11; // rcx
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r12
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v18; // rbx
  unsigned __int64 j; // r12
  int Size; // eax
  unsigned __int64 k; // rbx
  __int64 v23; // [rsp+30h] [rbp-40h]
  char v24[8]; // [rsp+38h] [rbp-38h] BYREF
  unsigned __int64 v25; // [rsp+40h] [rbp-30h]
  _QWORD *v26; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v27; // [rsp+50h] [rbp-20h]
  __int64 v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  __int64 v30; // [rsp+B0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v32; // [rsp+C8h] [rbp+58h] BYREF

  HIDWORD(v30) = HIDWORD(a1);
  LODWORD(v30) = 0;
  SureHCThemesLoaded = SystemSettings::DataModel::CHighContrastHelper::_MakeSureHCThemesLoaded(
                         (SystemSettings::DataModel::CHighContrastHelper *)&qword_18039D2C0,
                         (enum SystemSettings::DataModel::ELoadStatus *)&v30);
  if ( SureHCThemesLoaded >= 0 && (_DWORD)v30 == 2 )
  {
    v4 = 0;
    v26 = 0;
    v5 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    Microsoft::WRL::Wrappers::SRWLock::LockShared(v24, &stru_18039D430);
    v6 = qword_18039D3F0;
    v7 = 0;
    do
    {
      if ( v7 >= v6 )
        break;
      v8 = *(_QWORD *)(*((_QWORD *)*(&xmmword_18039D3E0 + 1) + v7) + 8LL);
      v30 = v8;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v30);
      SureHCThemesLoaded = 0;
      if ( v5 == v29 )
      {
        SureHCThemesLoaded = CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(
                               &v26,
                               v5 + 1);
        v5 = v27;
        v4 = v26;
        if ( SureHCThemesLoaded < 0 )
          continue;
      }
      v27 = ++v5;
      v9 = &v4[v5 - 1];
      if ( v9 )
        *v9 = v8;
      if ( SureHCThemesLoaded >= 0 )
        v8 = 0;
      v30 = v8;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      ++v7;
    }
    while ( SureHCThemesLoaded >= 0 );
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v24);
    for ( i = 0; i < v5; ++i )
    {
      v11 = v4[i];
      v23 = v11;
      if ( SureHCThemesLoaded >= 0 )
      {
        LODWORD(v30) = 0;
        SureHCThemesLoaded = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
                               a2,
                               &v30);
        v13 = (unsigned int)v30;
        v25 = (unsigned int)v30;
        v14 = i;
        while ( SureHCThemesLoaded >= 0 )
        {
          if ( v14 >= v13 )
          {
            v18 = v25;
            goto LABEL_24;
          }
          v32 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          SureHCThemesLoaded = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                                 a2,
                                 (unsigned int)v14,
                                 &v32);
          if ( SureHCThemesLoaded >= 0 )
          {
            string = 0;
            v15 = v32;
            v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 48LL);
            WindowsDeleteString(0);
            string = 0;
            SureHCThemesLoaded = v16(v15, &string);
            if ( SureHCThemesLoaded >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(*(LPCWCH *)(v23 + 256), -1, StringRawBuffer, -1, 1) == 2 )
              {
                v18 = v14;
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
LABEL_24:
                for ( j = i; j < v18; ++j )
                  Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
                    a2,
                    (unsigned int)i,
                    0);
                if ( v18 == (unsigned int)v30 )
                {
                  LOBYTE(v12) = 1;
                  SureHCThemesLoaded = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                                         a2,
                                         0,
                                         v23,
                                         v12);
                }
                break;
              }
            }
            WindowsDeleteString(string);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          ++v14;
          v13 = (unsigned int)v30;
        }
        v11 = v23;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( SureHCThemesLoaded >= 0 )
    {
      LODWORD(v30) = 0;
      Size = Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(
               a2,
               &v30);
      for ( k = v5; ; ++k )
      {
        SureHCThemesLoaded = Size;
        if ( Size < 0 || k >= (unsigned int)v30 )
          break;
        Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(
                 a2,
                 (unsigned int)v5,
                 0);
      }
    }
    Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockShared *)v24);
    if ( v4 )
      CoTaskMemFree(v4);
  }
  return (unsigned int)SureHCThemesLoaded;
}

```

## disassembly

```asm
0x1800631ec  mov     [rsp-38h+arg_8], rbx
0x1800631f1  mov     [rsp-38h+arg_0], rcx
0x1800631f6  push    rbp
0x1800631f7  push    rsi
0x1800631f8  push    rdi
0x1800631f9  push    r12
0x1800631fb  push    r13
0x1800631fd  push    r14
0x1800631ff  push    r15
0x180063201  mov     rbp, rsp
0x180063204  sub     rsp, 70h
0x180063208  mov     r13, rdx
0x18006320b  mov     dword ptr [rbp+arg_0], 0
0x180063212  lea     rdx, [rbp+arg_0]; enum SystemSettings::DataModel::ELoadStatus *
0x180063216  lea     rcx, qword_18039D2C0; this
0x18006321d  call    ?_MakeSureHCThemesLoaded@CHighContrastHelper@DataModel@SystemSettings@@AEAAJPEAW4ELoadStatus@23@@Z; SystemSettings::DataModel::CHighContrastHelper::_MakeSureHCThemesLoaded(SystemSettings::DataModel::ELoadStatus *)
0x180063222  mov     edi, eax
0x180063224  test    eax, eax
0x180063226  js      loc_1800634D8
0x18006322c  cmp     dword ptr [rbp+arg_0], 2
0x180063230  jnz     loc_1800634D8
0x180063236  xor     r14d, r14d
0x180063239  mov     [rbp+var_28], r14
0x18006323d  xor     esi, esi
0x18006323f  mov     [rbp+var_20], rsi
0x180063243  mov     [rbp+var_18], rsi
0x180063247  mov     [rbp+var_10], rsi
0x18006324b  lea     rdx, stru_18039D430
0x180063252  lea     rcx, [rbp+var_38]
0x180063256  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18006325b  nop
0x18006325c  mov     r12, cs:qword_18039D3F0
0x180063263  xor     r15d, r15d
0x180063266  cmp     r15, r12
0x180063269  jnb     short loc_1800632DE
0x18006326b  mov     rax, qword ptr cs:xmmword_18039D3E0+8
0x180063272  mov     rbx, [rax+r15*8]
0x180063276  mov     rbx, [rbx+8]
0x18006327a  mov     [rbp+arg_0], rbx
0x18006327e  lea     rcx, [rbp+arg_0]
0x180063282  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180063287  nop
0x180063288  xor     edi, edi
0x18006328a  cmp     rsi, [rbp+var_10]
0x18006328e  jnz     short loc_1800632AB
0x180063290  lea     rdx, [rsi+1]
0x180063294  lea     rcx, [rbp+var_28]
0x180063298  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@@@QEAAJ_K0@Z; CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18006329d  mov     edi, eax
0x18006329f  mov     rsi, [rbp+var_20]
0x1800632a3  mov     r14, [rbp+var_28]
0x1800632a7  test    eax, eax
0x1800632a9  js      short loc_1800632C2
0x1800632ab  inc     rsi
0x1800632ae  mov     [rbp+var_20], rsi
0x1800632b2  lea     rax, [rsi-1]
0x1800632b6  lea     rax, [r14+rax*8]
0x1800632ba  test    rax, rax
0x1800632bd  jz      short loc_1800632C2
0x1800632bf  mov     [rax], rbx
0x1800632c2  xor     eax, eax
0x1800632c4  test    edi, edi
0x1800632c6  cmovns  rbx, rax
0x1800632ca  mov     [rbp+arg_0], rbx
0x1800632ce  lea     rcx, [rbp+arg_0]
0x1800632d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800632d7  inc     r15
0x1800632da  test    edi, edi
0x1800632dc  jns     short loc_180063266
0x1800632de  lea     rcx, [rbp+var_38]; this
0x1800632e2  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800632e7  xor     r15d, r15d
0x1800632ea  test    rsi, rsi
0x1800632ed  jz      loc_180063480
0x1800632f3  mov     rcx, [r14+r15*8]
0x1800632f7  mov     [rbp+var_40], rcx
0x1800632fb  test    edi, edi
0x1800632fd  js      loc_180063468
0x180063303  mov     dword ptr [rbp+arg_0], 0
0x18006330a  lea     rdx, [rbp+arg_0]
0x18006330e  mov     rcx, r13
0x180063311  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x180063316  mov     edi, eax
0x180063318  mov     eax, dword ptr [rbp+arg_0]
0x18006331b  mov     [rbp+var_30], rax
0x18006331f  mov     r12, r15
0x180063322  test    edi, edi
0x180063324  js      loc_180063464
0x18006332a  cmp     r12, rax
0x18006332d  jnb     loc_180063427
0x180063333  mov     [rbp+arg_18], 0
0x18006333b  lea     rcx, [rbp+arg_18]
0x18006333f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063344  mov     edx, r12d
0x180063347  lea     r8, [rbp+arg_18]
0x18006334b  mov     rcx, r13
0x18006334e  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x180063353  mov     edi, eax
0x180063355  test    eax, eax
0x180063357  js      loc_1800633ED
0x18006335d  mov     [rbp+string], 0
0x180063365  mov     rdi, [rbp+arg_18]
0x180063369  mov     rax, [rdi]
0x18006336c  mov     rbx, [rax+30h]
0x180063370  xor     ecx, ecx; string
0x180063372  call    cs:__imp_WindowsDeleteString
0x180063379  nop     dword ptr [rax+rax+00h]
0x18006337e  mov     [rbp+string], 0
0x180063386  lea     rdx, [rbp+string]
0x18006338a  mov     rcx, rdi
0x18006338d  mov     rax, rbx
0x180063390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063395  mov     edi, eax
0x180063397  test    eax, eax
0x180063399  js      short loc_1800633DC
0x18006339b  xor     edx, edx; length
0x18006339d  mov     rcx, [rbp+string]; string
0x1800633a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800633a8  nop     dword ptr [rax+rax+00h]
0x1800633ad  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x1800633b5  or      ecx, 0FFFFFFFFh
0x1800633b8  mov     r9d, ecx; cchCount2
0x1800633bb  mov     r8, rax; lpString2
0x1800633be  mov     edx, ecx; cchCount1
0x1800633c0  mov     rax, [rbp+var_40]
0x1800633c4  mov     rcx, [rax+100h]; lpString1
0x1800633cb  call    cs:__imp_CompareStringOrdinal
0x1800633d2  nop     dword ptr [rax+rax+00h]
0x1800633d7  cmp     eax, 2
0x1800633da  jz      short loc_180063401
0x1800633dc  mov     rcx, [rbp+string]; string
0x1800633e0  call    cs:__imp_WindowsDeleteString
0x1800633e7  nop     dword ptr [rax+rax+00h]
0x1800633ec  nop
0x1800633ed  lea     rcx, [rbp+arg_18]
0x1800633f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800633f6  inc     r12
0x1800633f9  mov     eax, dword ptr [rbp+arg_0]
0x1800633fc  jmp     loc_180063322
0x180063401  mov     rbx, r12
0x180063404  mov     rcx, [rbp+string]; string
0x180063408  call    cs:__imp_WindowsDeleteString
0x18006340f  nop     dword ptr [rax+rax+00h]
0x180063414  mov     [rbp+string], 0
0x18006341c  lea     rcx, [rbp+arg_18]
0x180063420  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063425  jmp     short loc_18006342B
0x180063427  mov     rbx, [rbp+var_30]
0x18006342b  mov     r12, r15
0x18006342e  cmp     r15, rbx
0x180063431  jnb     short loc_180063449
0x180063433  xor     r8d, r8d
0x180063436  mov     edx, r15d
0x180063439  mov     rcx, r13
0x18006343c  call    ?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)
0x180063441  inc     r12
0x180063444  cmp     r12, rbx
0x180063447  jb      short loc_180063433
0x180063449  mov     eax, dword ptr [rbp+arg_0]
0x18006344c  cmp     rbx, rax
0x18006344f  jnz     short loc_180063464
0x180063451  mov     r9b, 1
0x180063454  mov     r8, [rbp+var_40]
0x180063458  xor     edx, edx
0x18006345a  mov     rcx, r13
0x18006345d  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x180063462  mov     edi, eax
0x180063464  mov     rcx, [rbp+var_40]
0x180063468  mov     rax, [rcx]
0x18006346b  mov     rax, [rax+10h]
0x18006346f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063474  inc     r15
0x180063477  cmp     r15, rsi
0x18006347a  jb      loc_1800632F3
0x180063480  test    edi, edi
0x180063482  js      short loc_1800634BA
0x180063484  mov     dword ptr [rbp+arg_0], 0
0x18006348b  lea     rdx, [rbp+arg_0]
0x18006348f  mov     rcx, r13
0x180063492  call    ?get_Size@?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$VectorOptions@PEAUHSTRING__@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::VectorOptions<HSTRING__ *,1,1,0>>::get_Size(uint *)
0x180063497  mov     rbx, rsi
0x18006349a  jmp     short loc_1800634B4
0x18006349c  mov     eax, dword ptr [rbp+arg_0]
0x18006349f  cmp     rbx, rax
0x1800634a2  jnb     short loc_1800634BA
0x1800634a4  mov     edx, esi
0x1800634a6  xor     r8d, r8d
0x1800634a9  mov     rcx, r13
0x1800634ac  call    ?RemoveAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::RemoveAtInternal(uint,bool)
0x1800634b1  inc     rbx
0x1800634b4  test    eax, eax
0x1800634b6  mov     edi, eax
0x1800634b8  jns     short loc_18006349C
0x1800634ba  lea     rcx, [rbp+var_38]; this
0x1800634be  call    ?InternalUnlock@SyncLockShared@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockShared::InternalUnlock(void)
0x1800634c3  nop
0x1800634c4  test    r14, r14
0x1800634c7  jz      short loc_1800634D8
0x1800634c9  mov     rcx, r14; pv
0x1800634cc  call    cs:__imp_CoTaskMemFree
0x1800634d3  nop     dword ptr [rax+rax+00h]
0x1800634d8  mov     eax, edi
0x1800634da  mov     rbx, [rsp+70h+arg_8]
0x1800634e2  add     rsp, 70h
0x1800634e6  pop     r15
0x1800634e8  pop     r14
0x1800634ea  pop     r13
0x1800634ec  pop     r12
0x1800634ee  pop     rdi
0x1800634ef  pop     rsi
0x1800634f0  pop     rbp
0x1800634f1  retn
```
