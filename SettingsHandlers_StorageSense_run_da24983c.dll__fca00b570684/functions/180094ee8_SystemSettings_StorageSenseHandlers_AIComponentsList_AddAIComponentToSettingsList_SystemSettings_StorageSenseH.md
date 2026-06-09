# SystemSettings::StorageSenseHandlers::AIComponentsList::AddAIComponentToSettingsList(SystemSettings::StorageSenseHandlers::AIComponentForLocalService *)

- ea: `0x180094ee8`
- end: `0x1800951f0`
- name: `?AddAIComponentToSettingsList@AIComponentsList@StorageSenseHandlers@SystemSettings@@AEAAJPEAVAIComponentForLocalService@23@@Z`
- size: `776`
- prototype: `int(SystemSettings::StorageSenseHandlers::AIComponentsList *__hidden this, struct SystemSettings::StorageSenseHandlers::AIComponentForLocalService *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800962d8`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001a530`
- `0x18001f230`
- `0x18001f53c`
- `0x1800248c0`
- `0x18003d36c`
- `0x180094ee8`
- `0x1800c81f0`
- `0x1800c8290`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180094f9e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800950d7`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800950d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800950ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800950fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800951a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095064`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800950ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800950fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800951a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009509c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800950ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009509c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800950ab`

## string_xrefs

- `0x180094f34`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x180094f73`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x180094fc7`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`
- `0x1800951cf`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\aicomponentslist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::StorageSenseHandlers::AIComponentsList::AddAIComponentToSettingsList(
        SystemSettings::StorageSenseHandlers::AIComponentsList *this,
        __m128i *a2)
{
  int Id; // eax
  unsigned int v5; // ebx
  int Description; // eax
  int Size; // eax
  __int64 v8; // rdx
  unsigned int v9; // esi
  unsigned int v10; // r14d
  __int64 v11; // rbx
  int v12; // eax
  const __m128i *v13; // rdi
  int (__fastcall *v14)(const __m128i *, HSTRING *); // rbx
  const __m128i *v15; // rdi
  int (__fastcall *v16)(const __m128i *, HSTRING *); // rbx
  HSTRING v17; // r8
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v19; // rax
  int lpString2; // [rsp+20h] [rbp-60h]
  HSTRING v22; // [rsp+50h] [rbp-30h] BYREF
  HSTRING v23; // [rsp+58h] [rbp-28h] BYREF
  const __m128i *v24; // [rsp+60h] [rbp-20h] BYREF
  char *v25; // [rsp+68h] [rbp-18h] BYREF
  HSTRING v26; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  unsigned int v28; // [rsp+D0h] [rbp+50h] BYREF
  HSTRING string; // [rsp+D8h] [rbp+58h] BYREF

  WindowsDeleteString(0);
  v26 = 0;
  Id = SystemSettings::StorageSenseHandlers::AIComponentForLocalService::get_Id(
         (SystemSettings::StorageSenseHandlers::AIComponentForLocalService *)a2,
         &v26);
  v5 = Id;
  if ( Id >= 0 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    Description = SystemSettings::StorageSenseHandlers::AIComponentForLocalService::get_Description(
                    (SystemSettings::StorageSenseHandlers::AIComponentForLocalService *)a2,
                    &string);
    v5 = Description;
    if ( Description < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
        (const char *)(unsigned int)Description,
        lpString2);
LABEL_5:
      WindowsDeleteString(string);
LABEL_24:
      string = 0;
      goto LABEL_25;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
    v25 = (char *)this + 272;
    v28 = 0;
    Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
             *((_QWORD *)this + 26),
             &v28);
    v5 = Size;
    if ( Size >= 0 )
    {
      v9 = v28;
      v10 = 0;
      if ( v28 )
      {
        while ( 1 )
        {
          v24 = 0;
          v11 = *((_QWORD *)this + 26);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v24);
          v12 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
                  v11,
                  v10,
                  &v24);
          v5 = v12;
          if ( v12 < 0 )
            break;
          v22 = 0;
          v13 = v24;
          v14 = *(int (__fastcall **)(const __m128i *, HSTRING *))(v24->m128i_i64[0] + 48);
          WindowsDeleteString(0);
          v22 = 0;
          if ( v14(v13, &v22) >= 0 )
          {
            v23 = 0;
            v15 = v24;
            v16 = *(int (__fastcall **)(const __m128i *, HSTRING *))(v24->m128i_i64[0] + 88);
            WindowsDeleteString(0);
            v23 = 0;
            if ( v16(v15, &v23) >= 0 )
            {
              if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                    (Microsoft::WRL::Wrappers::Details *)v22,
                                    v26,
                                    v17) )
              {
                v24[17] = _mm_add_epi64(_mm_loadu_si128(a2 + 17), _mm_loadu_si128(v24 + 17));
                WindowsDeleteString(v23);
                v23 = 0;
                WindowsDeleteString(v22);
                v22 = 0;
                Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v24);
                goto LABEL_23;
              }
              StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
              v19 = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringEx(0, 0x10u, v19, -1, StringRawBuffer, -1, 0, 0, 0) == 1 && v9 > v10 )
                v9 = v10;
            }
            WindowsDeleteString(v23);
            v23 = 0;
          }
          WindowsDeleteString(v22);
          v22 = 0;
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v24);
          if ( ++v10 >= v28 )
            goto LABEL_20;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x260,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
          (const char *)(unsigned int)v12,
          lpString2);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v24);
        goto LABEL_9;
      }
LABEL_20:
      Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
               *((_QWORD *)this + 26),
               v9,
               a2,
               0);
      v5 = Size;
      if ( Size >= 0 )
      {
LABEL_23:
        Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v25);
        WindowsDeleteString(string);
        v5 = 0;
        goto LABEL_24;
      }
      v8 = 642;
    }
    else
    {
      v8 = 602;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
      (const char *)(unsigned int)Size,
      lpString2);
LABEL_9:
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v25);
    goto LABEL_5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x253,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\aicomponentslist.cpp",
    (const char *)(unsigned int)Id,
    lpString2);
LABEL_25:
  WindowsDeleteString(v26);
  return v5;
}

```

## disassembly

```asm
0x180094ee8  mov     [rsp-38h+arg_0], rbx
0x180094eed  push    rbp
0x180094eee  push    rsi
0x180094eef  push    rdi
0x180094ef0  push    r12
0x180094ef2  push    r13
0x180094ef4  push    r14
0x180094ef6  push    r15
0x180094ef8  mov     rbp, rsp
0x180094efb  sub     rsp, 80h
0x180094f02  mov     r15, rdx
0x180094f05  mov     r13, rcx
0x180094f08  xor     r12d, r12d
0x180094f0b  mov     [rbp+var_10], r12
0x180094f0f  xor     ecx, ecx; string
0x180094f11  call    cs:__imp_WindowsDeleteString
0x180094f17  mov     [rbp+var_10], r12
0x180094f1b  lea     rdx, [rbp+var_10]; HSTRING *
0x180094f1f  mov     rcx, r15; this
0x180094f22  call    ?get_Id@AIComponentForLocalService@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::AIComponentForLocalService::get_Id(HSTRING__ * *)
0x180094f27  mov     ebx, eax
0x180094f29  test    eax, eax
0x180094f2b  jns     short loc_180094F4A
0x180094f2d  mov     rcx, [rbp+38h]; this
0x180094f31  mov     r9d, eax; char *
0x180094f34  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094f3b  mov     edx, 253h; void *
0x180094f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094f45  jmp     loc_1800951A1
0x180094f4a  mov     [rbp+string], r12
0x180094f4e  xor     ecx, ecx; string
0x180094f50  call    cs:__imp_WindowsDeleteString
0x180094f56  mov     [rbp+string], r12
0x180094f5a  lea     rdx, [rbp+string]; HSTRING *
0x180094f5e  mov     rcx, r15; this
0x180094f61  call    ?get_Description@AIComponentForLocalService@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::AIComponentForLocalService::get_Description(HSTRING__ * *)
0x180094f66  mov     ebx, eax
0x180094f68  test    eax, eax
0x180094f6a  jns     short loc_180094F94
0x180094f6c  mov     rcx, [rbp+38h]; this
0x180094f70  mov     r9d, eax; char *
0x180094f73  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094f7a  mov     edx, 255h; void *
0x180094f7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094f84  nop
0x180094f85  mov     rcx, [rbp+string]; string
0x180094f89  call    cs:__imp_WindowsDeleteString
0x180094f8f  jmp     loc_18009519D
0x180094f94  lea     rbx, [r13+110h]
0x180094f9b  mov     rcx, rbx; lpCriticalSection
0x180094f9e  call    cs:__imp_EnterCriticalSection
0x180094fa4  mov     [rbp+var_18], rbx
0x180094fa8  mov     [rbp+arg_10], r12d
0x180094fac  lea     rdx, [rbp+arg_10]
0x180094fb0  mov     rcx, [r13+0D0h]
0x180094fb7  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x180094fbc  mov     ebx, eax
0x180094fbe  test    eax, eax
0x180094fc0  jns     short loc_180094FE6
0x180094fc2  mov     edx, 25Ah; void *
0x180094fc7  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x180094fce  mov     r9d, eax; char *
0x180094fd1  mov     rcx, [rbp+38h]; this
0x180094fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094fda  nop
0x180094fdb  lea     rcx, [rbp+var_18]; this
0x180094fdf  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180094fe4  jmp     short loc_180094F85
0x180094fe6  mov     esi, [rbp+arg_10]
0x180094fe9  mov     r14d, r12d
0x180094fec  test    esi, esi
0x180094fee  jz      loc_18009511B
0x180094ff4  mov     [rbp+var_20], r12
0x180094ff8  mov     rbx, [r13+0D0h]
0x180094fff  lea     rcx, [rbp+var_20]
0x180095003  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180095008  lea     r8, [rbp+var_20]
0x18009500c  mov     edx, r14d
0x18009500f  mov     rcx, rbx
0x180095012  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x180095017  mov     ebx, eax
0x180095019  test    eax, eax
0x18009501b  js      loc_1800951C8
0x180095021  mov     [rbp+var_30], r12
0x180095025  mov     rdi, [rbp+var_20]
0x180095029  mov     rax, [rdi]
0x18009502c  mov     rbx, [rax+30h]
0x180095030  xor     ecx, ecx; string
0x180095032  call    cs:__imp_WindowsDeleteString
0x180095038  mov     [rbp+var_30], r12
0x18009503c  lea     rdx, [rbp+var_30]
0x180095040  mov     rcx, rdi
0x180095043  mov     rax, rbx
0x180095046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009504b  test    eax, eax
0x18009504d  js      loc_1800950F7
0x180095053  mov     [rbp+var_28], r12
0x180095057  mov     rdi, [rbp+var_20]
0x18009505b  mov     rax, [rdi]
0x18009505e  mov     rbx, [rax+58h]
0x180095062  xor     ecx, ecx; string
0x180095064  call    cs:__imp_WindowsDeleteString
0x18009506a  mov     [rbp+var_28], r12
0x18009506e  lea     rdx, [rbp+var_28]
0x180095072  mov     rcx, rdi
0x180095075  mov     rax, rbx
0x180095078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009507d  test    eax, eax
0x18009507f  js      short loc_1800950E9
0x180095081  mov     rdx, [rbp+var_10]; HSTRING
0x180095085  mov     rcx, [rbp+var_30]; this
0x180095089  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18009508e  test    eax, eax
0x180095090  jz      loc_18009513F
0x180095096  xor     edx, edx; length
0x180095098  mov     rcx, [rbp+var_28]; string
0x18009509c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800950a2  mov     rbx, rax
0x1800950a5  xor     edx, edx; length
0x1800950a7  mov     rcx, [rbp+string]; string
0x1800950ab  call    cs:__imp_WindowsGetStringRawBuffer
0x1800950b1  mov     [rsp+80h+lParam], r12; lParam
0x1800950b6  mov     [rsp+80h+lpReserved], r12; lpReserved
0x1800950bb  mov     [rsp+80h+lpVersionInformation], r12; lpVersionInformation
0x1800950c0  or      edi, 0FFFFFFFFh
0x1800950c3  mov     [rsp+80h+cchCount2], edi; cchCount2
0x1800950c7  mov     [rsp+80h+lpString2], rbx; lpString2
0x1800950cc  mov     r9d, edi; cchCount1
0x1800950cf  mov     r8, rax; lpString1
0x1800950d2  lea     edx, [rdi+11h]; dwCmpFlags
0x1800950d5  xor     ecx, ecx; lpLocaleName
0x1800950d7  call    cs:__imp_CompareStringEx
0x1800950dd  cmp     eax, 1
0x1800950e0  jnz     short loc_1800950E9
0x1800950e2  cmp     esi, r14d
0x1800950e5  cmova   esi, r14d
0x1800950e9  mov     rcx, [rbp+var_28]; string
0x1800950ed  call    cs:__imp_WindowsDeleteString
0x1800950f3  mov     [rbp+var_28], r12
0x1800950f7  mov     rcx, [rbp+var_30]; string
0x1800950fb  call    cs:__imp_WindowsDeleteString
0x180095101  mov     [rbp+var_30], r12
0x180095105  lea     rcx, [rbp+var_20]
0x180095109  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18009510e  inc     r14d
0x180095111  cmp     r14d, [rbp+arg_10]
0x180095115  jb      loc_180094FF4
0x18009511b  xor     r9d, r9d
0x18009511e  mov     r8, r15
0x180095121  mov     edx, esi
0x180095123  mov     rcx, [r13+0D0h]
0x18009512a  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18009512f  mov     ebx, eax
0x180095131  test    eax, eax
0x180095133  jns     short loc_180095186
0x180095135  mov     edx, 282h
0x18009513a  jmp     loc_180094FC7
0x18009513f  mov     rax, [rbp+var_20]
0x180095143  movdqu  xmm1, xmmword ptr [r15+110h]
0x18009514c  movdqu  xmm0, xmmword ptr [rax+110h]
0x180095154  paddq   xmm1, xmm0
0x180095158  movdqu  xmmword ptr [rax+110h], xmm1
0x180095160  mov     rcx, [rbp+var_28]; string
0x180095164  call    cs:__imp_WindowsDeleteString
0x18009516a  mov     [rbp+var_28], r12
0x18009516e  mov     rcx, [rbp+var_30]; string
0x180095172  call    cs:__imp_WindowsDeleteString
0x180095178  mov     [rbp+var_30], r12
0x18009517c  lea     rcx, [rbp+var_20]
0x180095180  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180095185  nop
0x180095186  lea     rcx, [rbp+var_18]; this
0x18009518a  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18009518f  nop
0x180095190  mov     rcx, [rbp+string]; string
0x180095194  call    cs:__imp_WindowsDeleteString
0x18009519a  mov     ebx, r12d
0x18009519d  mov     [rbp+string], r12
0x1800951a1  mov     rcx, [rbp+var_10]; string
0x1800951a5  call    cs:__imp_WindowsDeleteString
0x1800951ab  mov     eax, ebx
0x1800951ad  mov     rbx, [rsp+80h+arg_0]
0x1800951b5  add     rsp, 80h
0x1800951bc  pop     r15
0x1800951be  pop     r14
0x1800951c0  pop     r13
0x1800951c2  pop     r12
0x1800951c4  pop     rdi
0x1800951c5  pop     rsi
0x1800951c6  pop     rbp
0x1800951c7  retn
0x1800951c8  mov     rcx, [rbp+38h]; this
0x1800951cc  mov     r9d, eax; char *
0x1800951cf  lea     r8, aOnecoreuapShel_23; "onecoreuap\\shell\\coresettinghandlers"...
0x1800951d6  mov     edx, 260h; void *
0x1800951db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800951e0  nop
0x1800951e1  lea     rcx, [rbp+var_20]
0x1800951e5  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800951ea  jmp     loc_180094FDB
```
