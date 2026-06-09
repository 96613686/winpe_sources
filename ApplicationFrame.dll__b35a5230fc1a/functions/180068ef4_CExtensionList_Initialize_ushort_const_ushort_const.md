# CExtensionList::_Initialize(ushort const *,ushort const *)

- ea: `0x180068ef4`
- end: `0x1800692a8`
- name: `?_Initialize@CExtensionList@@AEAAJPEBG0@Z`
- size: `948`
- prototype: `__int64 __fastcall(CExtensionList *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800637e4`

## callees

- `0x180004c98`
- `0x1800116c0`
- `0x18003f150`
- `0x180041764`
- `0x180043c30`
- `0x180061bcc`
- `0x180062b64`
- `0x1800638bc`
- `0x180063948`
- `0x180066100`
- `0x180066d74`
- `0x180067400`
- `0x180067c88`
- `0x180068988`
- `0x180068c24`
- `0x180068ef4`
- `0x180069d44`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800691ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800691ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068fc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069026`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006916d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068fc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069026`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006916d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006903e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180068fae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006903e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069185`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069272`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069272`

## string_xrefs

- `0x1800691a2`: `__EXTENSION_POINTS_STATE_MUTEX__`
- `0x180068fa7`: `Windows.Foundation.ExtensionCatalog`

## pseudocode

```c
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
  HSTRING v32; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER v33; // [rsp+68h] [rbp-21h] BYREF
  HSTRING string; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-1h] BYREF

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
        if ( WindowsCreateStringReference(L"Windows.Foundation.ExtensionCatalog", 0x23u, &hstringHeader, &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        Instance = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(
                     string,
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
          WindowsCreateStringReference(L"Windows.Search", length[0], &v33, &v32);
          Instance = v7(v6, v32, &v28);
          if ( Instance >= 0 )
          {
            Reserved1 = 0;
            v10 = 0;
            v26[0] = 0;
            v32 = 0;
            v11 = *v28;
            memset(&v33, 0, sizeof(v33));
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
                  if ( Reserved1 != *(char **)&v33.Reserved.Reserved2[16]
                    || (v14 = CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_EnsureCapacity(
                                &v32,
                                Reserved1 + 1),
                        Reserved1 = (char *)v33.Reserved.Reserved1,
                        v10 = v32,
                        v14 >= 0) )
                  {
                    v33.Reserved.Reserved1 = ++Reserved1;
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
            WindowsCreateStringReference(L"Windows.Search", length[0], &v33, &v32);
            Instance = CExtensionStateManager::CreateInstance(v18, v32, v19, (void **)&v29);
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
                    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(length);
                    if ( (int)CExtensionListItem::CreateInstance(
                                *((struct Windows::Foundation::IExtensionRegistration **)v10 + v20),
                                v29,
                                v21,
                                (void **)length) >= 0 )
                    {
                      v22 = v3[1];
                      if ( v22 != *(_QWORD *)&v3[3]
                        || (int)CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_EnsureCapacity(
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
                    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(length);
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
0x180068ef4  push    rbp
0x180068ef6  push    rbx
0x180068ef7  push    rsi
0x180068ef8  push    rdi
0x180068ef9  push    r14
0x180068efb  push    r15
0x180068efd  lea     rbp, [rsp-2Fh]
0x180068f02  sub     rsp, 0B8h
0x180068f09  mov     rax, cs:__security_cookie
0x180068f10  xor     rax, rsp
0x180068f13  mov     [rbp+57h+var_40], rax
0x180068f17  lea     r15, [rcx+20h]
0x180068f1b  mov     rdi, rcx
0x180068f1e  mov     rcx, r15
0x180068f21  call    ?RemoveAll@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXXZ; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::RemoveAll(void)
0x180068f26  or      r8, 0FFFFFFFFFFFFFFFFh
0x180068f2a  lea     rdx, aWindowsSearch; "Windows.Search"
0x180068f31  lea     rcx, [rdi+48h]
0x180068f35  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180068f3a  mov     ebx, eax
0x180068f3c  test    eax, eax
0x180068f3e  js      loc_18006928A
0x180068f44  lea     rdx, [rdi+60h]; struct _FILETIME *
0x180068f48  mov     rcx, rdi; this
0x180068f4b  call    ?_GetLastExtensionCatalogWriteTime@CExtensionList@@AEAAJPEAU_FILETIME@@@Z; CExtensionList::_GetLastExtensionCatalogWriteTime(_FILETIME *)
0x180068f50  mov     ebx, eax
0x180068f52  test    eax, eax
0x180068f54  js      loc_18006928A
0x180068f5a  mov     r8, [rdi+48h]
0x180068f5e  lea     rax, [rdi+68h]
0x180068f62  mov     r9d, 1
0x180068f68  mov     [rsp+0E0h+var_C0], rax
0x180068f6d  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180068f74  mov     rcx, 0FFFFFFFF80000001h
0x180068f7b  call    ?_GetRegKeyLastWriteTime@@YAJPEAUHKEY__@@PEBG1W4REG_LAST_WRITE_OPTION@@PEAU_FILETIME@@@Z; _GetRegKeyLastWriteTime(HKEY__ *,ushort const *,ushort const *,REG_LAST_WRITE_OPTION,_FILETIME *)
0x180068f80  mov     ebx, eax
0x180068f82  test    eax, eax
0x180068f84  js      loc_18006928A
0x180068f8a  mov     rcx, rdi; this
0x180068f8d  call    ?_RecordUsageDataLastWriteTime@CExtensionList@@AEAAJXZ; CExtensionList::_RecordUsageDataLastWriteTime(void)
0x180068f92  lea     r9, [rbp+57h+string]; string
0x180068f96  mov     [rbp+57h+var_90], 0
0x180068f9e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180068fa2  mov     edx, 23h ; '#'; length
0x180068fa7  lea     rcx, sourceString; "Windows.Foundation.ExtensionCatalog"
0x180068fae  call    cs:__imp_WindowsCreateStringReference
0x180068fb4  mov     esi, 0C000000Dh
0x180068fb9  test    eax, eax
0x180068fbb  jns     short loc_180068FCF
0x180068fbd  xor     r9d, r9d; lpArguments
0x180068fc0  xor     r8d, r8d; nNumberOfArguments
0x180068fc3  mov     ecx, esi; dwExceptionCode
0x180068fc5  lea     edx, [r9+1]; dwExceptionFlags
0x180068fc9  call    cs:__imp_RaiseException
0x180068fcf  mov     rcx, [rbp+57h+string]
0x180068fd3  lea     rdx, [rbp+57h+var_90]
0x180068fd7  call    ??$ActivateInstance@V?$ComPtr@UIExtensionCatalog@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIExtensionCatalog@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionCatalog>>)
0x180068fdc  mov     ebx, eax
0x180068fde  test    eax, eax
0x180068fe0  js      loc_180069281
0x180068fe6  mov     rbx, [rbp+57h+var_90]
0x180068fea  lea     rcx, [rbp+57h+var_A0]
0x180068fee  mov     [rbp+57h+var_A0], 0
0x180068ff6  mov     rax, [rbx]
0x180068ff9  mov     rdi, [rax+30h]
0x180068ffd  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180069002  lea     rdx, [rbp+57h+length]; unsigned int *
0x180069006  mov     [rbp+57h+length], 0
0x18006900d  mov     ecx, 0Eh; unsigned __int64
0x180069012  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180069017  test    eax, eax
0x180069019  jns     short loc_18006902C
0x18006901b  lea     edx, [rcx-0Dh]; dwExceptionFlags
0x18006901e  xor     r9d, r9d; lpArguments
0x180069021  mov     ecx, esi; dwExceptionCode
0x180069023  xor     r8d, r8d; nNumberOfArguments
0x180069026  call    cs:__imp_RaiseException
0x18006902c  mov     edx, [rbp+57h+length]; length
0x18006902f  lea     r9, [rbp+57h+var_80]; string
0x180069033  lea     r8, [rbp+57h+var_78]; hstringHeader
0x180069037  lea     rcx, aWindowsSearch; "Windows.Search"
0x18006903e  call    cs:__imp_WindowsCreateStringReference
0x180069044  mov     rdx, [rbp+57h+var_80]
0x180069048  lea     r8, [rbp+57h+var_A0]
0x18006904c  mov     rcx, rbx
0x18006904f  mov     rax, rdi
0x180069052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069057  mov     ebx, eax
0x180069059  test    eax, eax
0x18006905b  js      loc_180069278
0x180069061  mov     rcx, [rbp+57h+var_A0]
0x180069065  lea     rdx, [rbp+57h+var_B0]
0x180069069  xor     esi, esi
0x18006906b  xor     r14d, r14d
0x18006906e  mov     [rbp+57h+var_B0], sil
0x180069072  mov     [rbp+57h+var_80], r14
0x180069076  mov     rax, [rcx]
0x180069079  mov     qword ptr [rbp+57h+var_78.Reserved], rsi
0x18006907d  mov     qword ptr [rbp+57h+var_78.Reserved+8], rsi
0x180069081  mov     qword ptr [rbp+57h+var_78.Reserved+10h], rsi
0x180069085  mov     rax, [rax+38h]
0x180069089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006908e  test    eax, eax
0x180069090  js      loc_180069135
0x180069096  cmp     [rbp+57h+var_B0], 0
0x18006909a  jz      loc_180069135
0x1800690a0  mov     rdi, [rbp+57h+var_A0]
0x1800690a4  lea     rcx, [rbp+57h+length]
0x1800690a8  mov     qword ptr [rbp+57h+length], 0
0x1800690b0  mov     rax, [rdi]
0x1800690b3  mov     rbx, [rax+30h]
0x1800690b7  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x1800690bc  lea     rdx, [rbp+57h+length]
0x1800690c0  mov     rcx, rdi
0x1800690c3  mov     rax, rbx
0x1800690c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690cb  test    eax, eax
0x1800690cd  js      short loc_18006910E
0x1800690cf  cmp     rsi, qword ptr [rbp+57h+var_78.Reserved+10h]
0x1800690d3  jnz     short loc_1800690EE
0x1800690d5  lea     rdx, [rsi+1]
0x1800690d9  lea     rcx, [rbp+57h+var_80]
0x1800690dd  call    ?_EnsureCapacity@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAJ_K0@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800690e2  mov     rsi, qword ptr [rbp+57h+var_78.Reserved]
0x1800690e6  mov     r14, [rbp+57h+var_80]
0x1800690ea  test    eax, eax
0x1800690ec  js      short loc_18006910E
0x1800690ee  inc     rsi
0x1800690f1  mov     qword ptr [rbp+57h+var_78.Reserved], rsi
0x1800690f5  lea     rcx, [rsi-1]
0x1800690f9  lea     rcx, [r14+rcx*8]
0x1800690fd  test    rcx, rcx
0x180069100  jz      short loc_18006910E
0x180069102  mov     rax, qword ptr [rbp+57h+length]
0x180069106  mov     [rcx], rax
0x180069109  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18006910e  mov     rcx, [rbp+57h+var_A0]
0x180069112  lea     rdx, [rbp+57h+var_B0]
0x180069116  mov     rax, [rcx]
0x180069119  mov     rax, [rax+40h]
0x18006911d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069122  lea     rcx, [rbp+57h+length]
0x180069126  mov     ebx, eax
0x180069128  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18006912d  test    ebx, ebx
0x18006912f  jns     loc_180069096
0x180069135  lea     rcx, [rbp+57h+var_98]
0x180069139  mov     [rbp+57h+var_98], 0
0x180069141  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180069146  lea     rdx, [rbp+57h+length]; unsigned int *
0x18006914a  mov     [rbp+57h+length], 0
0x180069151  mov     ecx, 0Eh; unsigned __int64
0x180069156  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18006915b  test    eax, eax
0x18006915d  jns     short loc_180069173
0x18006915f  lea     edx, [rcx-0Dh]; dwExceptionFlags
0x180069162  xor     r9d, r9d; lpArguments
0x180069165  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006916a  xor     r8d, r8d; nNumberOfArguments
0x18006916d  call    cs:__imp_RaiseException
0x180069173  mov     edx, [rbp+57h+length]; length
0x180069176  lea     r9, [rbp+57h+var_80]; string
0x18006917a  lea     r8, [rbp+57h+var_78]; hstringHeader
0x18006917e  lea     rcx, aWindowsSearch; "Windows.Search"
0x180069185  call    cs:__imp_WindowsCreateStringReference
0x18006918b  mov     rdx, [rbp+57h+var_80]; HSTRING
0x18006918f  lea     r9, [rbp+57h+var_98]; void **
0x180069193  call    ?CreateInstance@CExtensionStateManager@@SAJPEBGPEAUHSTRING__@@AEBU_GUID@@PEAPEAX@Z; CExtensionStateManager::CreateInstance(ushort const *,HSTRING__ *,_GUID const &,void * *)
0x180069198  mov     ebx, eax
0x18006919a  test    eax, eax
0x18006919c  js      loc_180069249
0x1800691a2  lea     r8, Name; "__EXTENSION_POINTS_STATE_MUTEX__"
0x1800691a9  xor     edx, edx; bInitialOwner
0x1800691ab  xor     ecx, ecx; lpMutexAttributes
0x1800691ad  call    cs:__imp_CreateMutexW
0x1800691b3  lea     rcx, [rbp+57h+var_88]; this
0x1800691b7  mov     [rbp+57h+var_88], rax
0x1800691bb  call    ?TryLock@CExtensionStateLock@@QEAAJXZ; CExtensionStateLock::TryLock(void)
0x1800691c0  mov     ebx, eax
0x1800691c2  test    eax, eax
0x1800691c4  js      short loc_180069240
0x1800691c6  xor     edi, edi
0x1800691c8  test    rsi, rsi
0x1800691cb  jz      short loc_180069240
0x1800691cd  lea     rcx, [rbp+57h+length]
0x1800691d1  mov     qword ptr [rbp+57h+length], 0
0x1800691d9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800691de  mov     rdx, [rbp+57h+var_98]; struct IExtensionStateManager *
0x1800691e2  lea     r9, [rbp+57h+length]; void **
0x1800691e6  mov     rcx, [r14+rdi*8]; struct Windows::Foundation::IExtensionRegistration *
0x1800691ea  call    ?CreateInstance@CExtensionListItem@@SAJPEAUIExtensionRegistration@Foundation@Windows@@PEAUIExtensionStateManager@@AEBU_GUID@@PEAPEAX@Z; CExtensionListItem::CreateInstance(Windows::Foundation::IExtensionRegistration *,IExtensionStateManager *,_GUID const &,void * *)
0x1800691ef  test    eax, eax
0x1800691f1  js      short loc_18006922F
0x1800691f3  mov     rdx, [r15+8]
0x1800691f7  cmp     rdx, [r15+18h]
0x1800691fb  jnz     short loc_18006920C
0x1800691fd  inc     rdx
0x180069200  mov     rcx, r15
0x180069203  call    ?_EnsureCapacity@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAJ_K0@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180069208  test    eax, eax
0x18006920a  js      short loc_18006922F
0x18006920c  inc     qword ptr [r15+8]
0x180069210  mov     rcx, [r15+8]
0x180069214  mov     rax, [r15]
0x180069217  dec     rcx
0x18006921a  lea     rcx, [rax+rcx*8]
0x18006921e  test    rcx, rcx
0x180069221  jz      short loc_18006922F
0x180069223  mov     rax, qword ptr [rbp+57h+length]
0x180069227  mov     [rcx], rax
0x18006922a  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18006922f  lea     rcx, [rbp+57h+length]
0x180069233  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180069238  inc     rdi
0x18006923b  cmp     rdi, rsi
0x18006923e  jb      short loc_1800691CD
0x180069240  lea     rcx, [rbp+57h+var_88]; this
0x180069244  call    ??1CExtensionStateLock@@QEAA@XZ; CExtensionStateLock::~CExtensionStateLock(void)
0x180069249  lea     rcx, [rbp+57h+var_98]
0x18006924d  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180069252  test    r14, r14
0x180069255  jz      short loc_180069278
0x180069257  xor     edi, edi
0x180069259  test    rsi, rsi
0x18006925c  jz      short loc_18006926F
0x18006925e  lea     rcx, [r14+rdi*8]
0x180069262  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180069267  inc     rdi
0x18006926a  cmp     rdi, rsi
0x18006926d  jb      short loc_18006925E
0x18006926f  mov     rcx, r14; pv
0x180069272  call    cs:__imp_CoTaskMemFree
0x180069278  lea     rcx, [rbp+57h+var_A0]
0x18006927c  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180069281  lea     rcx, [rbp+57h+var_90]
0x180069285  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18006928a  mov     eax, ebx
0x18006928c  mov     rcx, [rbp+57h+var_40]
0x180069290  xor     rcx, rsp; StackCookie
0x180069293  call    __security_check_cookie
0x180069298  add     rsp, 0B8h
0x18006929f  pop     r15
0x1800692a1  pop     r14
0x1800692a3  pop     rdi
0x1800692a4  pop     rsi
0x1800692a5  pop     rbx
0x1800692a6  pop     rbp
0x1800692a7  retn
```
