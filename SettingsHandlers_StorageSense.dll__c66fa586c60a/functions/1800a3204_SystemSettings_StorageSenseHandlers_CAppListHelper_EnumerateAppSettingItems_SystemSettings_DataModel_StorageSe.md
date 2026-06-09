# SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateAppSettingItems(SystemSettings::DataModel::StorageSense::AppFilterFlags,SystemSettings::StorageSenseHandlers::AppListType,HSTRING__ *)

- ea: `0x1800a3204`
- end: `0x1800a372b`
- name: `?EnumerateAppSettingItems@CAppListHelper@StorageSenseHandlers@SystemSettings@@QEAAJW4AppFilterFlags@StorageSense@DataModel@3@W4AppListType@23@PEAUHSTRING__@@@Z`
- size: `1319`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003df40`
- `0x1800a0130`
- `0x1800a9f70`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001f468`
- `0x18001f53c`
- `0x180026f10`
- `0x180037628`
- `0x18003c308`
- `0x180043f48`
- `0x180044d90`
- `0x180049f18`
- `0x1800a096c`
- `0x1800a3204`
- `0x1800a3734`
- `0x1800a3c08`
- `0x1800a4234`
- `0x1800aa230`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a323a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a323a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a344c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a346a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a36ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a344c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a346a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3540`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a36ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateAppSettingItems(__int64 a1, int a2, int a3, ...)
{
  HSTRING v3; // r15
  __int64 v7; // rbx
  int v8; // r12d
  unsigned int v9; // ebx
  int v10; // eax
  __int64 *v11; // rbx
  __int64 v12; // rdi
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rbx
  int v16; // r15d
  __int64 *v17; // rdi
  __int64 *v18; // r13
  int v19; // eax
  unsigned int i; // r12d
  int (__fastcall *v21)(__int64 *, _QWORD, struct SystemSettings::DataModel::StorageSense::IPackageInfo **); // rbx
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v22; // rdi
  int (__fastcall *v23)(struct SystemSettings::DataModel::StorageSense::IPackageInfo *, HSTRING *); // rbx
  __int64 v24; // rax
  int v25; // eax
  __int64 *v26; // rbx
  __int64 *v27; // rbx
  SystemSettings::StorageSenseHandlers::CAppNotificationSink **v28; // rax
  SystemSettings::StorageSenseHandlers::CAppNotificationSink **v29; // rbx
  SystemSettings::StorageSenseHandlers::CAppNotificationSink *v30; // rcx
  HSTRING string; // [rsp+20h] [rbp-69h] BYREF
  __int64 *v33; // [rsp+28h] [rbp-61h] BYREF
  __int64 *v34; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v35; // [rsp+38h] [rbp-51h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v36; // [rsp+40h] [rbp-49h] BYREF
  __int64 v37; // [rsp+48h] [rbp-41h] BYREF
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  __int64 v39; // [rsp+58h] [rbp-31h]
  int v40; // [rsp+60h] [rbp-29h] BYREF
  struct SystemSettings::DataModel::StorageSense::IPackageInfo **v41; // [rsp+68h] [rbp-21h] BYREF
  __int64 *v42; // [rsp+70h] [rbp-19h]
  struct SystemSettings::DataModel::StorageSense::IPackageInfo *v43; // [rsp+78h] [rbp-11h] BYREF
  __int64 **v44; // [rsp+80h] [rbp-9h] BYREF
  SystemSettings::StorageSenseHandlers::CAppNotificationSink *v45; // [rsp+88h] [rbp-1h] BYREF
  __int64 v46; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v47[2]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v48[7]; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 *v50; // [rsp+F0h] [rbp+67h] BYREF
  char v51; // [rsp+F8h] [rbp+6Fh]
  HSTRING v52; // [rsp+108h] [rbp+7Fh] BYREF
  va_list va; // [rsp+108h] [rbp+7Fh]
  va_list va1; // [rsp+110h] [rbp+87h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v52 = va_arg(va1, HSTRING);
  v3 = v52;
  v7 = a1 + 344;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 344));
  v48[0] = v7;
  v8 = a2 & 4;
  if ( (a2 & 4) == 0 )
  {
    if ( !v3 )
    {
LABEL_6:
      if ( (a2 & 2) != 0 && IsDesktopSKU() )
        SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateDesktopApps((SystemSettings::StorageSenseHandlers::CAppListHelper *)a1);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl'::`2'::impl) )
      {
        if ( (a2 & 0x10) != 0 )
        {
          v10 = SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateMcpServers((SystemSettings::StorageSenseHandlers::CAppListHelper *)a1);
          v9 = v10;
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA16,
              (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
              (const char *)(unsigned int)v10,
              (int)string);
            goto LABEL_59;
          }
        }
      }
      *(_DWORD *)(a1 + 304) = a2;
      *(_DWORD *)(a1 + 308) = a3;
      v34 = 0;
      v33 = 0;
      v11 = *(__int64 **)(a1 + 288);
      v12 = *v11;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
      if ( v8 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v12 + 56))(v11, *(_QWORD *)(a1 + 296), &v33);
        v9 = v13;
        if ( v13 < 0 )
        {
          v14 = 2595;
          goto LABEL_16;
        }
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v12 + 48))(
                v11,
                *(unsigned int *)(a1 + 304),
                &v33);
        v9 = v13;
        if ( v13 < 0 )
        {
          v14 = 2599;
          goto LABEL_16;
        }
      }
      v15 = *(_QWORD *)(a1 + 288);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)(v15 + 40) + 72LL))(
              *(_QWORD *)(v15 + 40),
              &v34);
      v9 = v13;
      if ( v13 >= 0 )
      {
        LOBYTE(v50) = 0;
        v16 = 0;
        while ( 1 )
        {
          if ( v16 )
          {
            if ( !*(_QWORD *)(a1 + 312) )
              goto LABEL_42;
            v51 = 0;
            v18 = v34;
            v17 = *(__int64 **)(a1 + 320);
          }
          else
          {
            v51 = 1;
            v17 = v33;
            v18 = *(__int64 **)(a1 + 312);
          }
          v42 = v17;
          v35 = 0;
          v37 = 0;
          v38 = 0;
          v39 = 0;
          v19 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v17 + 56))(v17, &v35);
          v9 = v19;
          if ( v19 < 0 )
            break;
          LOBYTE(v39) = 0;
          LODWORD(v37) = v35;
          for ( i = 0; i < v35; ++i )
          {
            v36 = 0;
            string = 0;
            v40 = 0;
            v21 = *(int (__fastcall **)(__int64 *, _QWORD, struct SystemSettings::DataModel::StorageSense::IPackageInfo **))(*v17 + 48);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v36);
            if ( v21(v17, i, &v36) >= 0 )
            {
              v22 = v36;
              v23 = *(int (__fastcall **)(struct SystemSettings::DataModel::StorageSense::IPackageInfo *, HSTRING *))(*(_QWORD *)v36 + 80LL);
              WindowsDeleteString(string);
              string = 0;
              if ( v23(v22, &string) >= 0 )
              {
                if ( v18 && (*(int (__fastcall **)(__int64 *, HSTRING, int *))(*v18 + 48))(v18, string, &v40) >= 0 )
                {
                  LOBYTE(v50) = 1;
                }
                else
                {
                  HIDWORD(v37) = v51 == 0 ? 2 : 0;
                  if ( *(_DWORD *)(a1 + 308) )
                  {
                    v25 = SystemSettings::StorageSenseHandlers::CAppListHelper::EnumeratePackageApps(
                            (SystemSettings::StorageSenseHandlers::CAppListHelper *)a1,
                            v36,
                            (struct SystemSettings::StorageSenseHandlers::AppEnumNotification *)&v37);
                    v9 = v25;
                    if ( v25 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xA7A,
                        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
                        (const char *)(unsigned int)v25,
                        (int)string);
                      WindowsDeleteString(string);
                      string = 0;
                      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v36);
                      goto LABEL_56;
                    }
                  }
                  else
                  {
                    v43 = v36;
                    LODWORD(v41) = 0;
                    v24 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                            &v44,
                            &v41,
                            &v43);
                    Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(&v38, v24);
                    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v44);
                    if ( v38 )
                    {
                      v43 = (struct SystemSettings::DataModel::StorageSense::IPackageInfo *)&v37;
                      v41 = &v43;
                      SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(
                        a1,
                        &v41);
                    }
                  }
                }
              }
              WindowsDeleteString(string);
              string = 0;
              v17 = v42;
            }
            else
            {
              WindowsDeleteString(string);
              string = 0;
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v36);
          }
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v38);
          if ( ++v16 >= 2 )
          {
LABEL_42:
            if ( (_BYTE)v50 )
            {
              v46 = 0x100000000LL;
              v47[0] = 0;
              v47[1] = 0;
              v50 = &v46;
              v44 = &v50;
              SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(
                a1,
                &v44);
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v47);
            }
            v26 = v33;
            if ( *(__int64 **)(a1 + 320) != v33 )
            {
              v50 = v33;
              Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v50);
              v50 = *(__int64 **)(a1 + 320);
              *(_QWORD *)(a1 + 320) = v26;
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v50);
            }
            v27 = v34;
            if ( *(__int64 **)(a1 + 312) != v34 )
            {
              v50 = v34;
              Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v50);
              v50 = *(__int64 **)(a1 + 312);
              *(_QWORD *)(a1 + 312) = v27;
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v50);
            }
            if ( !*(_BYTE *)(a1 + 384) )
            {
              v28 = (SystemSettings::StorageSenseHandlers::CAppNotificationSink **)Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppNotificationSink,>(&v50);
              v29 = (SystemSettings::StorageSenseHandlers::CAppNotificationSink **)(a1 + 408);
              v30 = 0;
              if ( &v45 != v28 )
              {
                v30 = *v28;
                *v28 = 0;
              }
              v45 = *v29;
              *v29 = v30;
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v50);
              if ( *v29
                && (int)SystemSettings::StorageSenseHandlers::CAppNotificationSink::Init(
                          *v29,
                          (struct SystemSettings::StorageSenseHandlers::CAppListHelper *)a1) >= 0 )
              {
                *(_BYTE *)(a1 + 384) = 1;
              }
              else
              {
                Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(a1 + 408);
              }
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
            v9 = 0;
            goto LABEL_59;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA49,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
          (const char *)(unsigned int)v19,
          (int)string);
LABEL_56:
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v38);
        goto LABEL_17;
      }
      v14 = 2602;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)v13,
        (int)string);
LABEL_17:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v34);
      goto LABEL_59;
    }
LABEL_5:
    Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 296), (HSTRING *)va);
    goto LABEL_6;
  }
  if ( v3 )
    goto LABEL_5;
  v9 = -2147024809;
LABEL_59:
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v48);
  return v9;
}

```

## disassembly

```asm
0x1800a3204  mov     [rsp-8+arg_10], rbx
0x1800a3209  mov     [rsp-8+arg_18], r9
0x1800a320e  push    rbp
0x1800a320f  push    rsi
0x1800a3210  push    rdi
0x1800a3211  push    r12
0x1800a3213  push    r13
0x1800a3215  push    r14
0x1800a3217  push    r15
0x1800a3219  lea     rbp, [rsp-27h]
0x1800a321e  sub     rsp, 0B0h
0x1800a3225  mov     r15, r9
0x1800a3228  mov     r13d, r8d
0x1800a322b  mov     edi, edx
0x1800a322d  mov     r14, rcx
0x1800a3230  lea     rbx, [rcx+158h]
0x1800a3237  mov     rcx, rbx; lpCriticalSection
0x1800a323a  call    cs:__imp_EnterCriticalSection
0x1800a3240  mov     [rbp+57h+var_38], rbx
0x1800a3244  mov     r12d, edi
0x1800a3247  and     r12d, 4
0x1800a324b  jz      short loc_1800A325E
0x1800a324d  xor     esi, esi
0x1800a324f  test    r15, r15
0x1800a3252  jnz     short loc_1800A3265
0x1800a3254  mov     ebx, 80070057h
0x1800a3259  jmp     loc_1800A3705
0x1800a325e  xor     esi, esi
0x1800a3260  test    r15, r15
0x1800a3263  jz      short loc_1800A3275
0x1800a3265  lea     rcx, [r14+128h]; newString
0x1800a326c  lea     rdx, [rbp+57h+arg_18]; HSTRING *
0x1800a3270  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800a3275  test    dil, 2
0x1800a3279  jz      short loc_1800A328C
0x1800a327b  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x1800a3280  cmp     al, 1
0x1800a3282  jnz     short loc_1800A328C
0x1800a3284  mov     rcx, r14; this
0x1800a3287  call    ?EnumerateDesktopApps@CAppListHelper@StorageSenseHandlers@SystemSettings@@IEAAJXZ; SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateDesktopApps(void)
0x1800a328c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59787121@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121> `wil::Feature<__WilFeatureTraits_Feature_ID59787121>::GetImpl(void)'::`2'::impl
0x1800a3293  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59787121@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59787121>::__private_IsEnabled(void)
0x1800a3298  test    al, al
0x1800a329a  jz      short loc_1800A32CD
0x1800a329c  test    dil, 10h
0x1800a32a0  jz      short loc_1800A32CD
0x1800a32a2  mov     rcx, r14; this
0x1800a32a5  call    ?EnumerateMcpServers@CAppListHelper@StorageSenseHandlers@SystemSettings@@IEAAJXZ; SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateMcpServers(void)
0x1800a32aa  mov     ebx, eax
0x1800a32ac  test    eax, eax
0x1800a32ae  jns     short loc_1800A32CD
0x1800a32b0  mov     rcx, [rbp+5Fh]; this
0x1800a32b4  mov     r9d, eax; char *
0x1800a32b7  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a32be  mov     edx, 0A16h; void *
0x1800a32c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a32c8  jmp     loc_1800A3705
0x1800a32cd  mov     [r14+130h], edi
0x1800a32d4  mov     [r14+134h], r13d
0x1800a32db  mov     [rbp+57h+var_B0], rsi
0x1800a32df  mov     [rbp+57h+var_B8], rsi
0x1800a32e3  mov     rbx, [r14+120h]
0x1800a32ea  mov     rdi, [rbx]
0x1800a32ed  lea     rcx, [rbp+57h+var_B8]
0x1800a32f1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a32f6  lea     r8, [rbp+57h+var_B8]
0x1800a32fa  mov     rcx, rbx
0x1800a32fd  test    r12d, r12d
0x1800a3300  jz      short loc_1800A3349
0x1800a3302  mov     rdx, [r14+128h]
0x1800a3309  mov     rax, [rdi+38h]
0x1800a330d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3312  mov     ebx, eax
0x1800a3314  test    eax, eax
0x1800a3316  jns     short loc_1800A3366
0x1800a3318  mov     edx, 0A23h; void *
0x1800a331d  mov     rcx, [rbp+5Fh]; this
0x1800a3321  mov     r9d, eax; char *
0x1800a3324  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a332b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3330  nop
0x1800a3331  lea     rcx, [rbp+57h+var_B8]
0x1800a3335  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a333a  nop
0x1800a333b  lea     rcx, [rbp+57h+var_B0]
0x1800a333f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3344  jmp     loc_1800A3705
0x1800a3349  mov     edx, [r14+130h]
0x1800a3350  mov     rax, [rdi+30h]
0x1800a3354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3359  mov     ebx, eax
0x1800a335b  test    eax, eax
0x1800a335d  jns     short loc_1800A3366
0x1800a335f  mov     edx, 0A27h
0x1800a3364  jmp     short loc_1800A331D
0x1800a3366  mov     rbx, [r14+120h]
0x1800a336d  lea     rcx, [rbp+57h+var_B0]
0x1800a3371  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3376  mov     rcx, [rbx+28h]
0x1800a337a  mov     rax, [rcx]
0x1800a337d  lea     rdx, [rbp+57h+var_B0]
0x1800a3381  mov     rax, [rax+48h]
0x1800a3385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a338a  mov     ebx, eax
0x1800a338c  test    eax, eax
0x1800a338e  jns     short loc_1800A3397
0x1800a3390  mov     edx, 0A2Ah
0x1800a3395  jmp     short loc_1800A331D
0x1800a3397  mov     byte ptr [rbp+57h+arg_0], sil
0x1800a339b  mov     r15d, esi
0x1800a339e  test    r15d, r15d
0x1800a33a1  jnz     short loc_1800A33B4
0x1800a33a3  mov     [rbp+57h+arg_8], 1
0x1800a33a7  mov     rdi, [rbp+57h+var_B8]
0x1800a33ab  mov     r13, [r14+138h]
0x1800a33b2  jmp     short loc_1800A33D0
0x1800a33b4  cmp     [r14+138h], rsi
0x1800a33bb  jz      loc_1800A357A
0x1800a33c1  mov     [rbp+57h+arg_8], sil
0x1800a33c5  mov     r13, [rbp+57h+var_B0]
0x1800a33c9  mov     rdi, [r14+140h]
0x1800a33d0  mov     [rbp+57h+var_70], rdi
0x1800a33d4  mov     [rbp+57h+var_A8], esi
0x1800a33d7  xor     eax, eax
0x1800a33d9  mov     [rbp+57h+var_98], rax
0x1800a33dd  mov     [rbp+57h+var_90], rsi
0x1800a33e1  mov     [rbp+57h+var_88], rax
0x1800a33e5  mov     rax, [rdi]
0x1800a33e8  lea     rdx, [rbp+57h+var_A8]
0x1800a33ec  mov     rcx, rdi
0x1800a33ef  mov     rax, [rax+38h]
0x1800a33f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a33f8  mov     ebx, eax
0x1800a33fa  test    eax, eax
0x1800a33fc  js      loc_1800A36C0
0x1800a3402  mov     byte ptr [rbp+57h+var_88], sil
0x1800a3406  mov     eax, [rbp+57h+var_A8]
0x1800a3409  mov     dword ptr [rbp+57h+var_98], eax
0x1800a340c  mov     r12d, esi
0x1800a340f  test    eax, eax
0x1800a3411  jz      loc_1800A3564
0x1800a3417  mov     [rbp+57h+var_A0], rsi
0x1800a341b  mov     [rbp+57h+string], rsi
0x1800a341f  mov     [rbp+57h+var_80], esi
0x1800a3422  mov     rax, [rdi]
0x1800a3425  mov     rbx, [rax+30h]
0x1800a3429  lea     rcx, [rbp+57h+var_A0]
0x1800a342d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3432  lea     r8, [rbp+57h+var_A0]
0x1800a3436  mov     edx, r12d
0x1800a3439  mov     rcx, rdi
0x1800a343c  mov     rax, rbx
0x1800a343f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3444  test    eax, eax
0x1800a3446  jns     short loc_1800A345B
0x1800a3448  mov     rcx, [rbp+57h+string]; string
0x1800a344c  call    cs:__imp_WindowsDeleteString
0x1800a3452  mov     [rbp+57h+string], rsi
0x1800a3456  jmp     loc_1800A354E
0x1800a345b  mov     rdi, [rbp+57h+var_A0]
0x1800a345f  mov     rax, [rdi]
0x1800a3462  mov     rbx, [rax+50h]
0x1800a3466  mov     rcx, [rbp+57h+string]; string
0x1800a346a  call    cs:__imp_WindowsDeleteString
0x1800a3470  mov     [rbp+57h+string], rsi
0x1800a3474  lea     rdx, [rbp+57h+string]
0x1800a3478  mov     rcx, rdi
0x1800a347b  mov     rax, rbx
0x1800a347e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3483  test    eax, eax
0x1800a3485  js      loc_1800A353C
0x1800a348b  test    r13, r13
0x1800a348e  jz      short loc_1800A34B5
0x1800a3490  mov     rax, [r13+0]
0x1800a3494  lea     r8, [rbp+57h+var_80]
0x1800a3498  mov     rdx, [rbp+57h+string]
0x1800a349c  mov     rcx, r13
0x1800a349f  mov     rax, [rax+30h]
0x1800a34a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a34a8  test    eax, eax
0x1800a34aa  js      short loc_1800A34B5
0x1800a34ac  mov     byte ptr [rbp+57h+arg_0], 1
0x1800a34b0  jmp     loc_1800A353C
0x1800a34b5  mov     al, [rbp+57h+arg_8]
0x1800a34b8  neg     al
0x1800a34ba  sbb     ecx, ecx
0x1800a34bc  not     ecx
0x1800a34be  and     ecx, 2
0x1800a34c1  mov     dword ptr [rbp+57h+var_98+4], ecx
0x1800a34c4  cmp     [r14+134h], esi
0x1800a34cb  jnz     short loc_1800A3522
0x1800a34cd  mov     rax, [rbp+57h+var_A0]
0x1800a34d1  mov     [rbp+57h+var_68], rax
0x1800a34d5  mov     dword ptr [rbp+57h+var_78], esi
0x1800a34d8  lea     r8, [rbp+57h+var_68]
0x1800a34dc  lea     rdx, [rbp+57h+var_78]
0x1800a34e0  lea     rcx, [rbp+57h+var_60]
0x1800a34e4  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAVCMcpServerPackageInfo@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAVCMcpServerPackageInfo@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(SystemSettings::StorageSenseHandlers::AppListType &&,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * &&)
0x1800a34e9  mov     rdx, rax
0x1800a34ec  lea     rcx, [rbp+57h+var_90]
0x1800a34f0  call    ??4?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &&)
0x1800a34f5  lea     rcx, [rbp+57h+var_60]
0x1800a34f9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a34fe  cmp     [rbp+57h+var_90], rsi
0x1800a3502  jz      short loc_1800A353C
0x1800a3504  lea     rax, [rbp+57h+var_98]
0x1800a3508  mov     [rbp+57h+var_68], rax
0x1800a350c  lea     rax, [rbp+57h+var_68]
0x1800a3510  mov     [rbp+57h+var_78], rax
0x1800a3514  lea     rdx, [rbp+57h+var_78]
0x1800a3518  mov     rcx, r14
0x1800a351b  call    ??$_Notify@V_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(_lambda_42ded661f5f033fea7c28cd183b3a6a8_ const &)
0x1800a3520  jmp     short loc_1800A353C
0x1800a3522  lea     r8, [rbp+57h+var_98]; struct SystemSettings::StorageSenseHandlers::AppEnumNotification *
0x1800a3526  mov     rdx, [rbp+57h+var_A0]; struct SystemSettings::DataModel::StorageSense::IPackageInfo *
0x1800a352a  mov     rcx, r14; this
0x1800a352d  call    ?EnumeratePackageApps@CAppListHelper@StorageSenseHandlers@SystemSettings@@IEAAJPEAUIPackageInfo@StorageSense@DataModel@3@PEAUAppEnumNotification@23@@Z; SystemSettings::StorageSenseHandlers::CAppListHelper::EnumeratePackageApps(SystemSettings::DataModel::StorageSense::IPackageInfo *,SystemSettings::StorageSenseHandlers::AppEnumNotification *)
0x1800a3532  mov     ebx, eax
0x1800a3534  test    eax, eax
0x1800a3536  js      loc_1800A368E
0x1800a353c  mov     rcx, [rbp+57h+string]; string
0x1800a3540  call    cs:__imp_WindowsDeleteString
0x1800a3546  mov     [rbp+57h+string], rsi
0x1800a354a  mov     rdi, [rbp+57h+var_70]
0x1800a354e  lea     rcx, [rbp+57h+var_A0]
0x1800a3552  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3557  inc     r12d
0x1800a355a  cmp     r12d, [rbp+57h+var_A8]
0x1800a355e  jb      loc_1800A3417
0x1800a3564  lea     rcx, [rbp+57h+var_90]
0x1800a3568  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a356d  inc     r15d
0x1800a3570  cmp     r15d, 2
0x1800a3574  jl      loc_1800A339E
0x1800a357a  cmp     byte ptr [rbp+57h+arg_0], 0
0x1800a357e  jz      short loc_1800A35BB
0x1800a3580  xor     eax, eax
0x1800a3582  mov     [rbp+57h+var_50], rax
0x1800a3586  mov     [rbp+57h+var_48], rsi
0x1800a358a  mov     [rbp+57h+var_40], rax
0x1800a358e  mov     dword ptr [rbp+57h+var_50+4], 1
0x1800a3595  lea     rax, [rbp+57h+var_50]
0x1800a3599  mov     [rbp+57h+arg_0], rax
0x1800a359d  lea     rax, [rbp+57h+arg_0]
0x1800a35a1  mov     [rbp+57h+var_60], rax
0x1800a35a5  lea     rdx, [rbp+57h+var_60]
0x1800a35a9  mov     rcx, r14
0x1800a35ac  call    ??$_Notify@V_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(_lambda_42ded661f5f033fea7c28cd183b3a6a8_ const &)
0x1800a35b1  nop
0x1800a35b2  lea     rcx, [rbp+57h+var_48]
0x1800a35b6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a35bb  mov     rbx, [rbp+57h+var_B8]
0x1800a35bf  cmp     [r14+140h], rbx
0x1800a35c6  jz      short loc_1800A35F0
0x1800a35c8  mov     [rbp+57h+arg_0], rbx
0x1800a35cc  lea     rcx, [rbp+57h+arg_0]
0x1800a35d0  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800a35d5  mov     rax, [r14+140h]
0x1800a35dc  mov     [rbp+57h+arg_0], rax
0x1800a35e0  mov     [r14+140h], rbx
0x1800a35e7  lea     rcx, [rbp+57h+arg_0]
0x1800a35eb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a35f0  mov     rbx, [rbp+57h+var_B0]
0x1800a35f4  cmp     [r14+138h], rbx
0x1800a35fb  jz      short loc_1800A3625
0x1800a35fd  mov     [rbp+57h+arg_0], rbx
0x1800a3601  lea     rcx, [rbp+57h+arg_0]
0x1800a3605  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800a360a  mov     rax, [r14+138h]
0x1800a3611  mov     [rbp+57h+arg_0], rax
0x1800a3615  mov     [r14+138h], rbx
0x1800a361c  lea     rcx, [rbp+57h+arg_0]
0x1800a3620  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3625  cmp     [r14+180h], sil
0x1800a362c  jnz     loc_1800A36F0
0x1800a3632  lea     rcx, [rbp+57h+arg_0]
0x1800a3636  call    ??$Make@VCAppNotificationSink@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppNotificationSink@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppNotificationSink,>(void)
0x1800a363b  lea     rbx, [r14+198h]
0x1800a3642  mov     rcx, rsi
0x1800a3645  lea     rdx, [rbp+57h+var_58]
0x1800a3649  cmp     rdx, rax
0x1800a364c  jz      short loc_1800A3654
0x1800a364e  mov     rcx, [rax]
0x1800a3651  mov     [rax], rsi
0x1800a3654  mov     rax, [rbx]
0x1800a3657  mov     [rbp+57h+var_58], rax
0x1800a365b  mov     [rbx], rcx
0x1800a365e  lea     rcx, [rbp+57h+var_58]
0x1800a3662  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3667  lea     rcx, [rbp+57h+arg_0]
0x1800a366b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3670  cmp     [rbx], rsi
0x1800a3673  jz      short loc_1800A36E7
0x1800a3675  mov     rdx, r14; struct SystemSettings::StorageSenseHandlers::CAppListHelper *
0x1800a3678  mov     rcx, [rbx]; this
0x1800a367b  call    ?Init@CAppNotificationSink@StorageSenseHandlers@SystemSettings@@QEAAJPEAVCAppListHelper@23@@Z; SystemSettings::StorageSenseHandlers::CAppNotificationSink::Init(SystemSettings::StorageSenseHandlers::CAppListHelper *)
0x1800a3680  test    eax, eax
0x1800a3682  js      short loc_1800A36E7
0x1800a3684  mov     byte ptr [r14+180h], 1
0x1800a368c  jmp     short loc_1800A36F0
  ... truncated ...
```
