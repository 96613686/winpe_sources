# SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateDesktopApps(void)

- ea: `0x1800a3734`
- end: `0x1800a3c02`
- name: `?EnumerateDesktopApps@CAppListHelper@StorageSenseHandlers@SystemSettings@@IEAAJXZ`
- size: `1230`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppListHelper *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3204`

## callees

- `0x18000733c`
- `0x18000c964`
- `0x18000e6cc`
- `0x180026f10`
- `0x180037628`
- `0x1800379c8`
- `0x18003c308`
- `0x1800a0770`
- `0x1800a3734`
- `0x1800a62fc`
- `0x1800be49c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3b21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3884`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3b21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a3a75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a3a75`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateDesktopApps(
        SystemSettings::StorageSenseHandlers::CAppListHelper *this)
{
  __int64 **v2; // rbx
  __int64 **v3; // rdi
  __int64 *v4; // rax
  int v5; // edi
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  int DesktopAppGuids; // eax
  __int64 v9; // rdi
  int v10; // eax
  int v11; // esi
  unsigned int i; // r15d
  int (__fastcall *v13)(__int64 *, HSTRING *); // rsi
  __int64 v14; // rax
  int j; // eax
  void (__fastcall *v16)(__int64 **, HSTRING *); // rbx
  __int64 *v17; // rbx
  __int64 v18; // rax
  unsigned int k; // esi
  int (__fastcall *v20)(__int64 *, HSTRING *); // rbx
  int v22; // [rsp+20h] [rbp-69h]
  unsigned int v23; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  __int64 **v25; // [rsp+40h] [rbp-49h] BYREF
  int v26; // [rsp+48h] [rbp-41h] BYREF
  __int64 *v27; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v28; // [rsp+58h] [rbp-31h] BYREF
  __int64 v29; // [rsp+60h] [rbp-29h] BYREF
  __int64 v30; // [rsp+68h] [rbp-21h] BYREF
  __int64 v31; // [rsp+70h] [rbp-19h]
  PCWSTR StringRawBuffer; // [rsp+78h] [rbp-11h] BYREF
  HSTRING v33; // [rsp+80h] [rbp-9h] BYREF
  __int64 v34; // [rsp+88h] [rbp-1h] BYREF
  __int64 *v35; // [rsp+90h] [rbp+7h] BYREF
  __int64 v36; // [rsp+98h] [rbp+Fh] BYREF
  __int64 **v37; // [rsp+A0h] [rbp+17h] BYREF
  _BYTE v38[56]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  char v40; // [rsp+F8h] [rbp+6Fh] BYREF
  char v41; // [rsp+100h] [rbp+77h] BYREF
  char v42; // [rsp+108h] [rbp+7Fh] BYREF

  v23 = 0;
  v28 = 0;
  string = 0;
  v40 = 0;
  v42 = 0;
  v36 = 0;
  v2 = 0;
  v37 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(&v25);
  v3 = v25;
  if ( v25 )
  {
    v4 = (__int64 *)operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v4 )
    {
      *(_DWORD *)v4 = 1;
      v3[18] = v4;
      *((_BYTE *)v3 + 152) = 1;
      v25 = 0;
      v2 = v3;
      v37 = v3;
      v5 = 0;
      goto LABEL_6;
    }
    v3[18] = 0;
  }
  v5 = -2147024882;
LABEL_6:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v25);
  if ( v5 < 0 )
  {
    v6 = (unsigned int)v5;
    v7 = 2458;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)v6,
      v22);
    goto LABEL_40;
  }
  DesktopAppGuids = SystemSettings::StorageSenseHandlers::CAppListHelper::GetDesktopAppGuids(this, &v36);
  v5 = DesktopAppGuids;
  if ( DesktopAppGuids < 0 )
  {
    v6 = (unsigned int)DesktopAppGuids;
    v7 = 2459;
    goto LABEL_10;
  }
  v9 = v36;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 56LL))(v36, &v23);
  v11 = v10;
  if ( v10 >= 0 )
  {
    for ( i = 0; i < v23; ++i )
    {
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v9 + 48LL))(v9, i, &v28) >= 0 )
      {
        v13 = *(int (__fastcall **)(__int64 *, HSTRING *))(*v28 + 72);
        WindowsDeleteString(string);
        string = 0;
        if ( v13(v28, &string) >= 0
          && (*(int (__fastcall **)(_QWORD, HSTRING, char *))(**((_QWORD **)this + 41) + 64LL))(
               *((_QWORD *)this + 41),
               string,
               &v40) >= 0 )
        {
          if ( v40 )
          {
            (*(void (__fastcall **)(_QWORD, HSTRING, _QWORD, char *))(**((_QWORD **)this + 41) + 80LL))(
              *((_QWORD *)this + 41),
              string,
              0,
              &v42);
          }
          else if ( ((int (__fastcall *)(__int64 **, HSTRING, char *))(*v2)[8])(v2, string, &v40) >= 0 && !v40 )
          {
            v30 = 0;
            v31 = 1;
            v29 = v23;
            v27 = v28;
            v26 = 2;
            v14 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                    &v35,
                    &v26,
                    &v27);
            Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(&v30, v14);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v35);
            v27 = &v29;
            v25 = &v27;
            SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(
              this,
              &v25);
            ((void (__fastcall *)(__int64 **, HSTRING, __int64, char *))(*v2)[10])(v2, string, 1, &v42);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
          }
        }
      }
    }
    v34 = 0;
    v41 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*((_QWORD *)this + 41) + 16LL) + 48LL))(
           *((_QWORD *)this + 41) + 16LL,
           &v34) >= 0 )
    {
      for ( j = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v34 + 56LL))(v34, &v41);
            j >= 0 && v41;
            j = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v34 + 64LL))(v34, &v41) )
      {
        v25 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 ***))(*(_QWORD *)v34 + 48LL))(v34, &v25) >= 0 )
        {
          v33 = 0;
          v26 = 1;
          ((void (__fastcall *)(__int64 **, int *))(*v25)[7])(v25, &v26);
          if ( v26 )
          {
            v16 = (void (__fastcall *)(__int64 **, HSTRING *))(*v25)[6];
            WindowsDeleteString(v33);
            v33 = 0;
            v16(v25, &v33);
            StringRawBuffer = WindowsGetStringRawBuffer(v33, 0);
            v27 = 0;
            Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CDesktopAppInfo,>(&v35);
            v17 = v35;
            if ( v35 )
            {
              Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(v35 + 5, &StringRawBuffer);
              v35 = 0;
              v27 = v17;
            }
            v30 = 0;
            v31 = 1;
            v29 = v23 | 0x200000000LL;
            LODWORD(StringRawBuffer) = 2;
            v18 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                    v38,
                    &StringRawBuffer,
                    &v27);
            Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(&v30, v18);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v38);
            v27 = &v29;
            StringRawBuffer = (PCWSTR)&v27;
            SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(
              this,
              &StringRawBuffer);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
          }
          WindowsDeleteString(v33);
        }
      }
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 41) + 96LL))(*((_QWORD *)this + 41));
    for ( k = 0; k < v23; ++k )
    {
      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v9 + 48LL))(v9, k, &v28) >= 0 )
      {
        v20 = *(int (__fastcall **)(__int64 *, HSTRING *))(*v28 + 72);
        WindowsDeleteString(string);
        string = 0;
        if ( v20(v28, &string) >= 0 )
          (*(void (__fastcall **)(_QWORD, HSTRING, __int64, char *))(**((_QWORD **)this + 41) + 80LL))(
            *((_QWORD *)this + 41),
            string,
            1,
            &v42);
      }
    }
    v5 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99C,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v10,
      v22);
    v5 = v11;
  }
LABEL_40:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v37);
  WindowsDeleteString(string);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800a3734  push    rbp
0x1800a3736  push    rbx
0x1800a3737  push    rsi
0x1800a3738  push    rdi
0x1800a3739  push    r12
0x1800a373b  push    r14
0x1800a373d  push    r15
0x1800a373f  lea     rbp, [rsp-27h]
0x1800a3744  sub     rsp, 0B0h
0x1800a374b  mov     r14, rcx
0x1800a374e  xor     r12d, r12d
0x1800a3751  mov     [rbp+57h+var_B0], r12d
0x1800a3755  mov     [rbp+57h+var_88], r12
0x1800a3759  mov     [rbp+57h+string], r12
0x1800a375d  mov     [rbp+57h+arg_8], r12b
0x1800a3761  mov     [rbp+57h+arg_18], r12b
0x1800a3765  mov     [rbp+57h+var_48], r12
0x1800a3769  mov     ebx, r12d
0x1800a376c  mov     [rbp+57h+var_40], rbx
0x1800a3770  lea     rcx, [rbp+57h+var_A0]
0x1800a3774  call    ??$Make@V?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@12@AEBU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@5678@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@5678@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x1800a3779  mov     rdi, [rbp+57h+var_A0]
0x1800a377d  test    rdi, rdi
0x1800a3780  jz      short loc_1800A37C3
0x1800a3782  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a3789  lea     ecx, [r12+4]; unsigned __int64
0x1800a378e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a3793  test    rax, rax
0x1800a3796  jz      short loc_1800A37BC
0x1800a3798  mov     dword ptr [rax], 1
0x1800a379e  mov     [rdi+90h], rax
0x1800a37a5  mov     byte ptr [rdi+98h], 1
0x1800a37ac  mov     [rbp+57h+var_A0], r12
0x1800a37b0  mov     rbx, rdi
0x1800a37b3  mov     [rbp+57h+var_40], rbx
0x1800a37b7  mov     edi, r12d
0x1800a37ba  jmp     short loc_1800A37C8
0x1800a37bc  mov     [rdi+90h], r12
0x1800a37c3  mov     edi, 8007000Eh
0x1800a37c8  lea     rcx, [rbp+57h+var_A0]
0x1800a37cc  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a37d1  test    edi, edi
0x1800a37d3  jns     short loc_1800A37DF
0x1800a37d5  mov     r9d, edi
0x1800a37d8  mov     edx, 99Ah
0x1800a37dd  jmp     short loc_1800A37F9
0x1800a37df  lea     rdx, [rbp+57h+var_48]
0x1800a37e3  mov     rcx, r14; this
0x1800a37e6  call    ?GetDesktopAppGuids@CAppListHelper@StorageSenseHandlers@SystemSettings@@IEAAJPEAPEAV?$Vector@PEAUIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@6789@U?$DefaultVectorOptions@PEAUIDesktopAppInfo@StorageSense@DataModel@SystemSettings@@@6789@@Internal@Collections@Foundation@Windows@@@Z; SystemSettings::StorageSenseHandlers::CAppListHelper::GetDesktopAppGuids(Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::StorageSense::IDesktopAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::StorageSense::IDesktopAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::StorageSense::IDesktopAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<SystemSettings::DataModel::StorageSense::IDesktopAppInfo *>> * *)
0x1800a37eb  mov     edi, eax
0x1800a37ed  test    eax, eax
0x1800a37ef  jns     short loc_1800A380E
0x1800a37f1  mov     r9d, eax; char *
0x1800a37f4  mov     edx, 99Bh; void *
0x1800a37f9  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a3800  mov     rcx, [rbp+5Fh]; this
0x1800a3804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3809  jmp     loc_1800A3BD0
0x1800a380e  mov     rdi, [rbp+57h+var_48]
0x1800a3812  mov     rax, [rdi]
0x1800a3815  lea     rdx, [rbp+57h+var_B0]
0x1800a3819  mov     rcx, rdi
0x1800a381c  mov     rax, [rax+38h]
0x1800a3820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3825  mov     esi, eax
0x1800a3827  test    eax, eax
0x1800a3829  jns     short loc_1800A384A
0x1800a382b  mov     rcx, [rbp+5Fh]; this
0x1800a382f  mov     r9d, eax; char *
0x1800a3832  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a3839  mov     edx, 99Ch; void *
0x1800a383e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3843  mov     edi, esi
0x1800a3845  jmp     loc_1800A3BD0
0x1800a384a  mov     r15d, r12d
0x1800a384d  cmp     [rbp+57h+var_B0], r12d
0x1800a3851  jbe     loc_1800A39B8
0x1800a3857  mov     rax, [rdi]
0x1800a385a  lea     r8, [rbp+57h+var_88]
0x1800a385e  mov     edx, r15d
0x1800a3861  mov     rcx, rdi
0x1800a3864  mov     rax, [rax+30h]
0x1800a3868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a386d  test    eax, eax
0x1800a386f  js      loc_1800A39AB
0x1800a3875  mov     rax, [rbp+57h+var_88]
0x1800a3879  mov     rcx, [rax]
0x1800a387c  mov     rsi, [rcx+48h]
0x1800a3880  mov     rcx, [rbp+57h+string]; string
0x1800a3884  call    cs:__imp_WindowsDeleteString
0x1800a388a  mov     [rbp+57h+string], r12
0x1800a388e  lea     rdx, [rbp+57h+string]
0x1800a3892  mov     rcx, [rbp+57h+var_88]
0x1800a3896  mov     rax, rsi
0x1800a3899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a389e  test    eax, eax
0x1800a38a0  js      loc_1800A39AB
0x1800a38a6  mov     rcx, [r14+148h]
0x1800a38ad  mov     rax, [rcx]
0x1800a38b0  lea     r8, [rbp+57h+arg_8]
0x1800a38b4  mov     rdx, [rbp+57h+string]
0x1800a38b8  mov     rax, [rax+40h]
0x1800a38bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a38c1  test    eax, eax
0x1800a38c3  js      loc_1800A39AB
0x1800a38c9  mov     rdx, [rbp+57h+string]
0x1800a38cd  cmp     [rbp+57h+arg_8], r12b
0x1800a38d1  jz      short loc_1800A38F2
0x1800a38d3  mov     rcx, [r14+148h]
0x1800a38da  mov     rax, [rcx]
0x1800a38dd  lea     r9, [rbp+57h+arg_18]
0x1800a38e1  xor     r8d, r8d
0x1800a38e4  mov     rax, [rax+50h]
0x1800a38e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a38ed  jmp     loc_1800A39AB
0x1800a38f2  mov     rax, [rbx]
0x1800a38f5  lea     r8, [rbp+57h+arg_8]
0x1800a38f9  mov     rcx, rbx
0x1800a38fc  mov     rax, [rax+40h]
0x1800a3900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3905  test    eax, eax
0x1800a3907  js      loc_1800A39AB
0x1800a390d  cmp     [rbp+57h+arg_8], r12b
0x1800a3911  jnz     loc_1800A39AB
0x1800a3917  xor     eax, eax
0x1800a3919  mov     [rbp+57h+var_80], rax
0x1800a391d  mov     [rbp+57h+var_78], r12
0x1800a3921  mov     [rbp+57h+var_70], rax
0x1800a3925  mov     eax, [rbp+57h+var_B0]
0x1800a3928  mov     dword ptr [rbp+57h+var_80], eax
0x1800a392b  mov     byte ptr [rbp+57h+var_70], 1
0x1800a392f  mov     dword ptr [rbp+57h+var_80+4], r12d
0x1800a3933  mov     rax, [rbp+57h+var_88]
0x1800a3937  mov     [rbp+57h+var_90], rax
0x1800a393b  mov     [rbp+57h+var_98], 2
0x1800a3942  lea     r8, [rbp+57h+var_90]
0x1800a3946  lea     rdx, [rbp+57h+var_98]
0x1800a394a  lea     rcx, [rbp+57h+var_50]
0x1800a394e  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAVCMcpServerPackageInfo@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAVCMcpServerPackageInfo@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(SystemSettings::StorageSenseHandlers::AppListType &&,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * &&)
0x1800a3953  mov     rdx, rax
0x1800a3956  lea     rcx, [rbp+57h+var_78]
0x1800a395a  call    ??4?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &&)
0x1800a395f  lea     rcx, [rbp+57h+var_50]
0x1800a3963  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3968  lea     rax, [rbp+57h+var_80]
0x1800a396c  mov     [rbp+57h+var_90], rax
0x1800a3970  lea     rax, [rbp+57h+var_90]
0x1800a3974  mov     [rbp+57h+var_A0], rax
0x1800a3978  lea     rdx, [rbp+57h+var_A0]
0x1800a397c  mov     rcx, r14
0x1800a397f  call    ??$_Notify@V_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(_lambda_42ded661f5f033fea7c28cd183b3a6a8_ const &)
0x1800a3984  mov     rax, [rbx]
0x1800a3987  lea     r9, [rbp+57h+arg_18]
0x1800a398b  mov     r8d, 1
0x1800a3991  mov     rdx, [rbp+57h+string]
0x1800a3995  mov     rcx, rbx
0x1800a3998  mov     rax, [rax+50h]
0x1800a399c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a39a1  nop
0x1800a39a2  lea     rcx, [rbp+57h+var_78]
0x1800a39a6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a39ab  inc     r15d
0x1800a39ae  cmp     r15d, [rbp+57h+var_B0]
0x1800a39b2  jb      loc_1800A3857
0x1800a39b8  mov     [rbp+57h+var_58], r12
0x1800a39bc  mov     [rbp+57h+arg_10], r12b
0x1800a39c0  mov     rcx, [r14+148h]
0x1800a39c7  add     rcx, 10h
0x1800a39cb  mov     rax, [rcx]
0x1800a39ce  lea     rdx, [rbp+57h+var_58]
0x1800a39d2  mov     rax, [rax+30h]
0x1800a39d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a39db  test    eax, eax
0x1800a39dd  js      loc_1800A3B43
0x1800a39e3  mov     rcx, [rbp+57h+var_58]
0x1800a39e7  mov     rax, [rcx]
0x1800a39ea  mov     rax, [rax+38h]
0x1800a39ee  jmp     loc_1800A3B32
0x1800a39f3  cmp     [rbp+57h+arg_10], r12b
0x1800a39f7  jz      loc_1800A3B43
0x1800a39fd  mov     [rbp+57h+var_A0], r12
0x1800a3a01  mov     rcx, [rbp+57h+var_58]
0x1800a3a05  mov     rax, [rcx]
0x1800a3a08  lea     rdx, [rbp+57h+var_A0]
0x1800a3a0c  mov     rax, [rax+30h]
0x1800a3a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a15  test    eax, eax
0x1800a3a17  js      loc_1800A3B27
0x1800a3a1d  mov     [rbp+57h+var_60], r12
0x1800a3a21  mov     [rbp+57h+var_98], 1
0x1800a3a28  mov     rcx, [rbp+57h+var_A0]
0x1800a3a2c  mov     rax, [rcx]
0x1800a3a2f  lea     rdx, [rbp+57h+var_98]
0x1800a3a33  mov     rax, [rax+38h]
0x1800a3a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a3c  cmp     [rbp+57h+var_98], r12d
0x1800a3a40  jz      loc_1800A3B1D
0x1800a3a46  mov     rax, [rbp+57h+var_A0]
0x1800a3a4a  mov     rcx, [rax]
0x1800a3a4d  mov     rbx, [rcx+30h]
0x1800a3a51  mov     rcx, [rbp+57h+var_60]; string
0x1800a3a55  call    cs:__imp_WindowsDeleteString
0x1800a3a5b  mov     [rbp+57h+var_60], r12
0x1800a3a5f  lea     rdx, [rbp+57h+var_60]
0x1800a3a63  mov     rcx, [rbp+57h+var_A0]
0x1800a3a67  mov     rax, rbx
0x1800a3a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a6f  xor     edx, edx; length
0x1800a3a71  mov     rcx, [rbp+57h+var_60]; string
0x1800a3a75  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a3a7b  mov     [rbp+57h+var_68], rax
0x1800a3a7f  mov     [rbp+57h+var_90], r12
0x1800a3a83  lea     rcx, [rbp+57h+var_50]
0x1800a3a87  call    ??$Make@VCDesktopAppInfo@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCDesktopAppInfo@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CDesktopAppInfo,>(void)
0x1800a3a8c  mov     rbx, [rbp+57h+var_50]
0x1800a3a90  test    rbx, rbx
0x1800a3a93  jz      short loc_1800A3AAA
0x1800a3a95  lea     rcx, [rbx+28h]
0x1800a3a99  lea     rdx, [rbp+57h+var_68]
0x1800a3a9d  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800a3aa2  mov     [rbp+57h+var_50], r12
0x1800a3aa6  mov     [rbp+57h+var_90], rbx
0x1800a3aaa  xor     eax, eax
0x1800a3aac  mov     [rbp+57h+var_80], rax
0x1800a3ab0  mov     [rbp+57h+var_78], r12
0x1800a3ab4  mov     [rbp+57h+var_70], rax
0x1800a3ab8  mov     eax, [rbp+57h+var_B0]
0x1800a3abb  mov     dword ptr [rbp+57h+var_80], eax
0x1800a3abe  mov     byte ptr [rbp+57h+var_70], 1
0x1800a3ac2  mov     dword ptr [rbp+57h+var_80+4], 2
0x1800a3ac9  mov     dword ptr [rbp+57h+var_68], 2
0x1800a3ad0  lea     r8, [rbp+57h+var_90]
0x1800a3ad4  lea     rdx, [rbp+57h+var_68]
0x1800a3ad8  lea     rcx, [rbp+57h+var_38]
0x1800a3adc  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAVCMcpServerPackageInfo@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAVCMcpServerPackageInfo@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(SystemSettings::StorageSenseHandlers::AppListType &&,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * &&)
0x1800a3ae1  mov     rdx, rax
0x1800a3ae4  lea     rcx, [rbp+57h+var_78]
0x1800a3ae8  call    ??4?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &&)
0x1800a3aed  lea     rcx, [rbp+57h+var_38]
0x1800a3af1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3af6  lea     rax, [rbp+57h+var_80]
0x1800a3afa  mov     [rbp+57h+var_90], rax
0x1800a3afe  lea     rax, [rbp+57h+var_90]
0x1800a3b02  mov     [rbp+57h+var_68], rax
0x1800a3b06  lea     rdx, [rbp+57h+var_68]
0x1800a3b0a  mov     rcx, r14
0x1800a3b0d  call    ??$_Notify@V_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(_lambda_42ded661f5f033fea7c28cd183b3a6a8_ const &)
0x1800a3b12  nop
0x1800a3b13  lea     rcx, [rbp+57h+var_78]
0x1800a3b17  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3b1c  nop
0x1800a3b1d  mov     rcx, [rbp+57h+var_60]; string
0x1800a3b21  call    cs:__imp_WindowsDeleteString
0x1800a3b27  mov     rcx, [rbp+57h+var_58]
0x1800a3b2b  mov     rax, [rcx]
0x1800a3b2e  mov     rax, [rax+40h]
0x1800a3b32  lea     rdx, [rbp+57h+arg_10]
0x1800a3b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3b3b  test    eax, eax
0x1800a3b3d  jns     loc_1800A39F3
0x1800a3b43  mov     rcx, [r14+148h]
0x1800a3b4a  mov     rax, [rcx]
0x1800a3b4d  mov     rax, [rax+60h]
0x1800a3b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3b56  mov     esi, r12d
0x1800a3b59  cmp     [rbp+57h+var_B0], r12d
0x1800a3b5d  jbe     short loc_1800A3BCD
0x1800a3b5f  mov     rax, [rdi]
0x1800a3b62  lea     r8, [rbp+57h+var_88]
0x1800a3b66  mov     edx, esi
0x1800a3b68  mov     rcx, rdi
0x1800a3b6b  mov     rax, [rax+30h]
0x1800a3b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3b74  test    eax, eax
0x1800a3b76  js      short loc_1800A3BC6
0x1800a3b78  mov     rax, [rbp+57h+var_88]
0x1800a3b7c  mov     rcx, [rax]
0x1800a3b7f  mov     rbx, [rcx+48h]
0x1800a3b83  mov     rcx, [rbp+57h+string]; string
0x1800a3b87  call    cs:__imp_WindowsDeleteString
0x1800a3b8d  mov     [rbp+57h+string], r12
0x1800a3b91  lea     rdx, [rbp+57h+string]
0x1800a3b95  mov     rcx, [rbp+57h+var_88]
0x1800a3b99  mov     rax, rbx
0x1800a3b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ba1  test    eax, eax
0x1800a3ba3  js      short loc_1800A3BC6
0x1800a3ba5  mov     rcx, [r14+148h]
0x1800a3bac  mov     rax, [rcx]
0x1800a3baf  lea     r9, [rbp+57h+arg_18]
0x1800a3bb3  mov     r8d, 1
0x1800a3bb9  mov     rdx, [rbp+57h+string]
0x1800a3bbd  mov     rax, [rax+50h]
0x1800a3bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3bc6  inc     esi
0x1800a3bc8  cmp     esi, [rbp+57h+var_B0]
0x1800a3bcb  jb      short loc_1800A3B5F
0x1800a3bcd  mov     edi, r12d
0x1800a3bd0  lea     rcx, [rbp+57h+var_48]
0x1800a3bd4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
  ... truncated ...
```
