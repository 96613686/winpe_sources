# CExtensionList::_Initialize(ushort const *,ushort const *)

- ea: `0x180049e48`
- end: `0x18004a1da`
- name: `?_Initialize@CExtensionList@@AEAAJPEBG0@Z`
- size: `914`
- prototype: `__int64 __fastcall(struct _FILETIME *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180044914`

## callees

- `0x180007b3c`
- `0x180013db4`
- `0x180015ab8`
- `0x18002a170`
- `0x18002d408`
- `0x18002e7c0`
- `0x18003e0d4`
- `0x18003ed0c`
- `0x180042f74`
- `0x180043e64`
- `0x1800449f8`
- `0x180044a84`
- `0x180048700`
- `0x1800498dc`
- `0x180049b78`
- `0x180049e48`
- `0x18004b120`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004a0df`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18004a0df`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049f58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a09f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049f58`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a09f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a0b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a0b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a1a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a1a4`

## string_xrefs

- `0x18004a0d4`: `__EXTENSION_POINTS_STATE_MUTEX__`
- `0x180049ee6`: `Windows.Foundation.ExtensionCatalog`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CExtensionList::_Initialize(
        struct _FILETIME *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct _FILETIME *v3; // r15
  int Instance; // ebx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, HSTRING, __int64 **); // rdi
  int v8; // ecx
  char *Reserved1; // rsi
  HSTRING v10; // r14
  __int64 v11; // rax
  __int64 *v12; // rdi
  int (__fastcall *v13)(__int64 *, UINT32 *); // rbx
  int v14; // eax
  _QWORD *v15; // rcx
  int v16; // ebx
  int v17; // ecx
  const unsigned __int16 *v18; // rcx
  const struct _GUID *v19; // r8
  unsigned __int64 v20; // rdi
  const struct _GUID *v21; // r8
  struct _FILETIME v22; // rdx
  _QWORD *v23; // rcx
  unsigned __int64 v24; // rdi
  char v26[8]; // [rsp+30h] [rbp-59h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-49h] BYREF
  struct IExtensionStateManager *v29; // [rsp+48h] [rbp-41h] BYREF
  __int64 v30; // [rsp+50h] [rbp-39h] BYREF
  HANDLE MutexW; // [rsp+58h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-21h] BYREF
  HSTRING v34; // [rsp+80h] [rbp-9h] BYREF

  v3 = this + 4;
  CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(
    &this[4],
    a2,
    a3);
  Instance = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
               &this[9],
               L"Windows.Search",
               -1);
  if ( Instance >= 0 )
  {
    Instance = CExtensionList::_GetLastExtensionCatalogWriteTime((CExtensionList *)this, this + 12);
    if ( Instance >= 0 )
    {
      Instance = _GetRegKeyLastWriteTime(
                   -2147483647,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AppContract",
                   *(_QWORD *)&this[9],
                   1,
                   &this[13]);
      if ( Instance >= 0 )
      {
        CExtensionList::_RecordUsageDataLastWriteTime((CExtensionList *)this);
        v30 = 0;
        Windows::Internal::StringReference::StringReference(&v34, L"Windows.Foundation.ExtensionCatalog");
        Instance = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(
                     v34,
                     &v30);
        if ( Instance >= 0 )
        {
          v6 = v30;
          v28 = 0;
          v7 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 **))(*(_QWORD *)v30 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v28);
          length[0] = 0;
          if ( (int)ULongLongToULong(0xEu, length) < 0 )
            RaiseException(0xC000000D, v8 - 13, 0, 0);
          WindowsCreateStringReference(L"Windows.Search", length[0], &hstringHeader, &string);
          Instance = v7(v6, string, &v28);
          if ( Instance >= 0 )
          {
            Reserved1 = 0;
            v10 = 0;
            v26[0] = 0;
            string = 0;
            v11 = *v28;
            memset(&hstringHeader, 0, sizeof(hstringHeader));
            if ( (*(int (__fastcall **)(__int64 *, char *))(v11 + 56))(v28, v26) >= 0 )
            {
              do
              {
                if ( !v26[0] )
                  break;
                v12 = v28;
                *(_QWORD *)length = 0;
                v13 = *(int (__fastcall **)(__int64 *, UINT32 *))(*v28 + 48);
                Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(length);
                if ( v13(v12, length) >= 0 )
                {
                  if ( Reserved1 != *(char **)&hstringHeader.Reserved.Reserved2[16]
                    || (v14 = CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(
                                &string,
                                Reserved1 + 1),
                        Reserved1 = (char *)hstringHeader.Reserved.Reserved1,
                        v10 = string,
                        v14 >= 0) )
                  {
                    hstringHeader.Reserved.Reserved1 = ++Reserved1;
                    v15 = v10 + 2 * (_QWORD)(Reserved1 - 1);
                    if ( v15 )
                    {
                      *v15 = *(_QWORD *)length;
                      Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef();
                    }
                  }
                }
                v16 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v28 + 64))(v28, v26);
                Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(length);
              }
              while ( v16 >= 0 );
            }
            v29 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v29);
            length[0] = 0;
            if ( (int)ULongLongToULong(0xEu, length) < 0 )
              RaiseException(0xC000000D, v17 - 13, 0, 0);
            WindowsCreateStringReference(L"Windows.Search", length[0], &hstringHeader, &string);
            Instance = CExtensionStateManager::CreateInstance(v18, string, v19, (void **)&v29);
            if ( Instance >= 0 )
            {
              MutexW = CreateMutexW(0, 0, L"__EXTENSION_POINTS_STATE_MUTEX__");
              Instance = CExtensionStateLock::TryLock((CExtensionStateLock *)&MutexW);
              if ( Instance >= 0 )
              {
                v20 = 0;
                if ( Reserved1 )
                {
                  do
                  {
                    *(_QWORD *)length = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(length);
                    if ( (int)CExtensionListItem::CreateInstance(
                                *((struct Windows::Foundation::IExtensionRegistration **)v10 + v20),
                                v29,
                                v21,
                                (void **)length) >= 0 )
                    {
                      v22 = v3[1];
                      if ( v22 != *(_QWORD *)&v3[3]
                        || (int)CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(
                                  v3,
                                  *(_QWORD *)&v22 + 1LL) >= 0 )
                      {
                        v23 = (_QWORD *)(*(_QWORD *)v3 + 8 * (*(_QWORD *)&v3[1])++);
                        if ( v23 )
                        {
                          *v23 = *(_QWORD *)length;
                          Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef();
                        }
                      }
                    }
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(length);
                    ++v20;
                  }
                  while ( v20 < (unsigned __int64)Reserved1 );
                }
              }
              CExtensionStateLock::~CExtensionStateLock((CExtensionStateLock *)&MutexW);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v29);
            if ( v10 )
            {
              v24 = 0;
              if ( Reserved1 )
              {
                do
                  Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(v10 + 2 * v24++);
                while ( v24 < (unsigned __int64)Reserved1 );
              }
              CoTaskMemFree(v10);
            }
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v28);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&v30);
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180049e48  push    rbp
0x180049e4a  push    rbx
0x180049e4b  push    rsi
0x180049e4c  push    rdi
0x180049e4d  push    r14
0x180049e4f  push    r15
0x180049e51  lea     rbp, [rsp-2Fh]
0x180049e56  sub     rsp, 0B8h
0x180049e5d  mov     rax, cs:__security_cookie
0x180049e64  xor     rax, rsp
0x180049e67  mov     [rbp+57h+var_40], rax
0x180049e6b  lea     r15, [rcx+20h]
0x180049e6f  mov     rdi, rcx
0x180049e72  mov     rcx, r15
0x180049e75  call    ?RemoveAll@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXXZ; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(void)
0x180049e7a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180049e7e  lea     rdx, sourceString; "Windows.Search"
0x180049e85  lea     rcx, [rdi+48h]
0x180049e89  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180049e8e  mov     ebx, eax
0x180049e90  test    eax, eax
0x180049e92  js      loc_18004A1BC
0x180049e98  lea     rdx, [rdi+60h]; struct _FILETIME *
0x180049e9c  mov     rcx, rdi; this
0x180049e9f  call    ?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z; CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)
0x180049ea4  mov     ebx, eax
0x180049ea6  test    eax, eax
0x180049ea8  js      loc_18004A1BC
0x180049eae  mov     r8, [rdi+48h]
0x180049eb2  lea     rax, [rdi+68h]
0x180049eb6  mov     r9d, 1
0x180049ebc  mov     [rsp+0E0h+var_C0], rax
0x180049ec1  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180049ec8  mov     rcx, 0FFFFFFFF80000001h
0x180049ecf  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x180049ed4  mov     ebx, eax
0x180049ed6  test    eax, eax
0x180049ed8  js      loc_18004A1BC
0x180049ede  mov     rcx, rdi; this
0x180049ee1  call    ?_RecordUsageDataLastWriteTime@CExtensionList@@AEAAJXZ; CExtensionList::_RecordUsageDataLastWriteTime(void)
0x180049ee6  lea     rdx, aWindowsFoundat_9; "Windows.Foundation.ExtensionCatalog"
0x180049eed  mov     [rbp+57h+var_90], 0
0x180049ef5  lea     rcx, [rbp+57h+var_60]; string
0x180049ef9  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x180049efe  mov     rcx, [rbp+57h+var_60]
0x180049f02  lea     rdx, [rbp+57h+var_90]
0x180049f06  call    ??$ActivateInstance@V?$ComPtr@UIExtensionCatalog@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIExtensionCatalog@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>)
0x180049f0b  mov     ebx, eax
0x180049f0d  test    eax, eax
0x180049f0f  js      loc_18004A1B3
0x180049f15  mov     rbx, [rbp+57h+var_90]
0x180049f19  lea     rcx, [rbp+57h+var_A0]
0x180049f1d  mov     [rbp+57h+var_A0], 0
0x180049f25  mov     rax, [rbx]
0x180049f28  mov     rdi, [rax+30h]
0x180049f2c  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180049f31  lea     rdx, [rbp+57h+length]; unsigned int *
0x180049f35  mov     [rbp+57h+length], 0
0x180049f3c  mov     ecx, 0Eh; unsigned __int64
0x180049f41  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180049f46  test    eax, eax
0x180049f48  jns     short loc_180049F5E
0x180049f4a  lea     edx, [rcx-0Dh]; dwExceptionFlags
0x180049f4d  xor     r9d, r9d; lpArguments
0x180049f50  mov     ecx, 0C000000Dh; dwExceptionCode
0x180049f55  xor     r8d, r8d; nNumberOfArguments
0x180049f58  call    cs:__imp_RaiseException
0x180049f5e  mov     edx, [rbp+57h+length]; length
0x180049f61  lea     r9, [rbp+57h+string]; string
0x180049f65  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180049f69  lea     rcx, sourceString; "Windows.Search"
0x180049f70  call    cs:__imp_WindowsCreateStringReference
0x180049f76  mov     rdx, [rbp+57h+string]
0x180049f7a  lea     r8, [rbp+57h+var_A0]
0x180049f7e  mov     rcx, rbx
0x180049f81  mov     rax, rdi
0x180049f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f89  mov     ebx, eax
0x180049f8b  test    eax, eax
0x180049f8d  js      loc_18004A1AA
0x180049f93  mov     rcx, [rbp+57h+var_A0]
0x180049f97  lea     rdx, [rbp+57h+var_B0]
0x180049f9b  xor     esi, esi
0x180049f9d  xor     r14d, r14d
0x180049fa0  mov     [rbp+57h+var_B0], sil
0x180049fa4  mov     [rbp+57h+string], r14
0x180049fa8  mov     rax, [rcx]
0x180049fab  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rsi
0x180049faf  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x180049fb3  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], rsi
0x180049fb7  mov     rax, [rax+38h]
0x180049fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fc0  test    eax, eax
0x180049fc2  js      loc_18004A067
0x180049fc8  cmp     [rbp+57h+var_B0], 0
0x180049fcc  jz      loc_18004A067
0x180049fd2  mov     rdi, [rbp+57h+var_A0]
0x180049fd6  lea     rcx, [rbp+57h+length]
0x180049fda  mov     qword ptr [rbp+57h+length], 0
0x180049fe2  mov     rax, [rdi]
0x180049fe5  mov     rbx, [rax+30h]
0x180049fe9  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180049fee  lea     rdx, [rbp+57h+length]
0x180049ff2  mov     rcx, rdi
0x180049ff5  mov     rax, rbx
0x180049ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ffd  test    eax, eax
0x180049fff  js      short loc_18004A040
0x18004a001  cmp     rsi, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18004a005  jnz     short loc_18004A020
0x18004a007  lea     rdx, [rsi+1]
0x18004a00b  lea     rcx, [rbp+57h+string]
0x18004a00f  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardCompareHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardMergeHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@@@QEAAJ_K0@Z; CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004a014  mov     rsi, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18004a018  mov     r14, [rbp+57h+string]
0x18004a01c  test    eax, eax
0x18004a01e  js      short loc_18004A040
0x18004a020  inc     rsi
0x18004a023  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rsi
0x18004a027  lea     rcx, [rsi-1]
0x18004a02b  lea     rcx, [r14+rcx*8]
0x18004a02f  test    rcx, rcx
0x18004a032  jz      short loc_18004A040
0x18004a034  mov     rax, qword ptr [rbp+57h+length]
0x18004a038  mov     [rcx], rax
0x18004a03b  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18004a040  mov     rcx, [rbp+57h+var_A0]
0x18004a044  lea     rdx, [rbp+57h+var_B0]
0x18004a048  mov     rax, [rcx]
0x18004a04b  mov     rax, [rax+40h]
0x18004a04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a054  lea     rcx, [rbp+57h+length]
0x18004a058  mov     ebx, eax
0x18004a05a  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a05f  test    ebx, ebx
0x18004a061  jns     loc_180049FC8
0x18004a067  lea     rcx, [rbp+57h+var_98]
0x18004a06b  mov     [rbp+57h+var_98], 0
0x18004a073  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a078  lea     rdx, [rbp+57h+length]; unsigned int *
0x18004a07c  mov     [rbp+57h+length], 0
0x18004a083  mov     ecx, 0Eh; unsigned __int64
0x18004a088  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004a08d  test    eax, eax
0x18004a08f  jns     short loc_18004A0A5
0x18004a091  lea     edx, [rcx-0Dh]; dwExceptionFlags
0x18004a094  xor     r9d, r9d; lpArguments
0x18004a097  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004a09c  xor     r8d, r8d; nNumberOfArguments
0x18004a09f  call    cs:__imp_RaiseException
0x18004a0a5  mov     edx, [rbp+57h+length]; length
0x18004a0a8  lea     r9, [rbp+57h+string]; string
0x18004a0ac  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004a0b0  lea     rcx, sourceString; "Windows.Search"
0x18004a0b7  call    cs:__imp_WindowsCreateStringReference
0x18004a0bd  mov     rdx, [rbp+57h+string]; HSTRING
0x18004a0c1  lea     r9, [rbp+57h+var_98]; void **
0x18004a0c5  call    ?CreateInstance@CExtensionStateManager@@SAJPEBGPEAUHSTRING__@@AEBU_GUID@@PEAPEAX@Z; CExtensionStateManager::CreateInstance(ushort const *,HSTRING__ *,_GUID const &,void * *)
0x18004a0ca  mov     ebx, eax
0x18004a0cc  test    eax, eax
0x18004a0ce  js      loc_18004A17B
0x18004a0d4  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x18004a0db  xor     edx, edx; bInitialOwner
0x18004a0dd  xor     ecx, ecx; lpMutexAttributes
0x18004a0df  call    cs:__imp_CreateMutexW
0x18004a0e5  lea     rcx, [rbp+57h+var_88]; this
0x18004a0e9  mov     [rbp+57h+var_88], rax
0x18004a0ed  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x18004a0f2  mov     ebx, eax
0x18004a0f4  test    eax, eax
0x18004a0f6  js      short loc_18004A172
0x18004a0f8  xor     edi, edi
0x18004a0fa  test    rsi, rsi
0x18004a0fd  jz      short loc_18004A172
0x18004a0ff  lea     rcx, [rbp+57h+length]
0x18004a103  mov     qword ptr [rbp+57h+length], 0
0x18004a10b  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a110  mov     rdx, [rbp+57h+var_98]; struct IExtensionStateManager *
0x18004a114  lea     r9, [rbp+57h+length]; void **
0x18004a118  mov     rcx, [r14+rdi*8]; struct Windows::Foundation::IExtensionRegistration *
0x18004a11c  call    ?CreateInstance@CExtensionListItem@@SAJPEAUIExtensionRegistration@Foundation@Windows@@PEAUIExtensionStateManager@@AEBU_GUID@@PEAPEAX@Z; CExtensionListItem::CreateInstance(Windows::Foundation::IExtensionRegistration *,IExtensionStateManager *,_GUID const &,void * *)
0x18004a121  test    eax, eax
0x18004a123  js      short loc_18004A161
0x18004a125  mov     rdx, [r15+8]
0x18004a129  cmp     rdx, [r15+18h]
0x18004a12d  jnz     short loc_18004A13E
0x18004a12f  inc     rdx
0x18004a132  mov     rcx, r15
0x18004a135  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardCompareHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardMergeHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@@@QEAAJ_K0@Z; CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004a13a  test    eax, eax
0x18004a13c  js      short loc_18004A161
0x18004a13e  inc     qword ptr [r15+8]
0x18004a142  mov     rcx, [r15+8]
0x18004a146  mov     rax, [r15]
0x18004a149  dec     rcx
0x18004a14c  lea     rcx, [rax+rcx*8]
0x18004a150  test    rcx, rcx
0x18004a153  jz      short loc_18004A161
0x18004a155  mov     rax, qword ptr [rbp+57h+length]
0x18004a159  mov     [rcx], rax
0x18004a15c  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18004a161  lea     rcx, [rbp+57h+length]
0x18004a165  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a16a  inc     rdi
0x18004a16d  cmp     rdi, rsi
0x18004a170  jb      short loc_18004A0FF
0x18004a172  lea     rcx, [rbp+57h+var_88]; this
0x18004a176  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x18004a17b  lea     rcx, [rbp+57h+var_98]
0x18004a17f  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a184  test    r14, r14
0x18004a187  jz      short loc_18004A1AA
0x18004a189  xor     edi, edi
0x18004a18b  test    rsi, rsi
0x18004a18e  jz      short loc_18004A1A1
0x18004a190  lea     rcx, [r14+rdi*8]
0x18004a194  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a199  inc     rdi
0x18004a19c  cmp     rdi, rsi
0x18004a19f  jb      short loc_18004A190
0x18004a1a1  mov     rcx, r14; pv
0x18004a1a4  call    cs:__imp_CoTaskMemFree
0x18004a1aa  lea     rcx, [rbp+57h+var_A0]
0x18004a1ae  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a1b3  lea     rcx, [rbp+57h+var_90]
0x18004a1b7  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a1bc  mov     eax, ebx
0x18004a1be  mov     rcx, [rbp+57h+var_40]
0x18004a1c2  xor     rcx, rsp; StackCookie
0x18004a1c5  call    __security_check_cookie
0x18004a1ca  add     rsp, 0B8h
0x18004a1d1  pop     r15
0x18004a1d3  pop     r14
0x18004a1d5  pop     rdi
0x18004a1d6  pop     rsi
0x18004a1d7  pop     rbx
0x18004a1d8  pop     rbp
0x18004a1d9  retn
```
