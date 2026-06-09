# CExtensionList::_InitializeWithFilterAndSortOptions(CCoSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>> &,ICondition *,SORTCOLUMN *,uint,uint,IObjectArray *)

- ea: `0x180231304`
- end: `0x1802317a2`
- name: `?_InitializeWithFilterAndSortOptions@CExtensionList@@AEAAJAEAV?$CCoSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@PEAUICondition@@PEAUSORTCOLUMN@@IIPEAUIObjectArray@@@Z`
- size: `1182`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, HSTRING)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18022c350`

## callees

- `0x180010e4d`
- `0x180011bb0`
- `0x18002198c`
- `0x180022b50`
- `0x18002d624`
- `0x180048868`
- `0x18005958c`
- `0x180065f28`
- `0x1800deee0`
- `0x180221a84`
- `0x1802287c0`
- `0x180228968`
- `0x180228f3c`
- `0x180228fec`
- `0x18022ca90`
- `0x1802304f4`
- `0x180231304`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802314e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231679`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023177f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802314e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231679`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180231709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18023177f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802313e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802315d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802313e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802315d1`

## pseudocode

```c
__int64 __fastcall CExtensionList::_InitializeWithFilterAndSortOptions(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        HSTRING a7)
{
  HSTRING v7; // r15
  unsigned __int64 v8; // rbx
  int ExtensionIdFromExtensionItem; // edi
  __int64 v13; // rax
  HSTRING v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // rax
  __int64 (__fastcall *v17)(HSTRING, _QWORD, GUID *, struct IExtensionListItem **); // rbx
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  const WCHAR *v23; // rbx
  const WCHAR **v24; // rdx
  unsigned int v25; // edx
  void *v26; // rcx
  unsigned __int64 i; // rsi
  __int64 v28; // rax
  HSTRING v29; // rdi
  __int64 (__fastcall *v30)(HSTRING, GUID *, struct IExtensionListItem **); // rbx
  int v31; // eax
  struct CONDITIONEVALPROPS *v32; // r8
  int DoesItemMatchCondition; // eax
  int v34; // edx
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r15
  _QWORD *v39; // rcx
  unsigned __int64 v40; // rcx
  LPVOID *v41; // rsi
  unsigned int v42; // edx
  void *v43; // rcx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // rbx
  __int64 v46; // r8
  char v48[8]; // [rsp+30h] [rbp-A1h] BYREF
  HSTRING string; // [rsp+38h] [rbp-99h] BYREF
  struct IExtensionListItem *v50; // [rsp+40h] [rbp-91h] BYREF
  PCWSTR v51; // [rsp+48h] [rbp-89h] BYREF
  LPVOID v52; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int64 v53; // [rsp+58h] [rbp-79h]
  LPVOID pv; // [rsp+60h] [rbp-71h] BYREF
  __int64 v55; // [rsp+68h] [rbp-69h]
  __int64 v56; // [rsp+70h] [rbp-61h] BYREF
  int v57; // [rsp+78h] [rbp-59h]
  _QWORD v58[4]; // [rsp+80h] [rbp-51h] BYREF
  __int128 v59; // [rsp+A0h] [rbp-31h]
  __int128 v60; // [rsp+B0h] [rbp-21h]
  __int64 v61; // [rsp+C0h] [rbp-11h]

  v7 = a7;
  v8 = 0;
  v48[0] = 0;
  v52 = 0;
  v53 = 0;
  pv = 0;
  ExtensionIdFromExtensionItem = 0;
  v55 = 0;
  if ( a7 )
  {
    v13 = *(_QWORD *)a7;
    v14 = a7;
    LODWORD(a7) = 0;
    ExtensionIdFromExtensionItem = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(v13 + 24))(v14, &a7);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v15 = 0;
      while ( 1 )
      {
        if ( v15 >= (unsigned int)a7 )
        {
          ExtensionIdFromExtensionItem = 0;
          if ( v53 > 1 )
          {
            pv = 0;
            string = 0;
            ExtensionIdFromExtensionItem = ULongLongMult(v53 >> 1, 8u, (unsigned __int64 *)&string);
            if ( ExtensionIdFromExtensionItem >= 0 )
              ExtensionIdFromExtensionItem = CTCoAllocPolicy::Realloc(v26, v25, 0, (unsigned __int64)string, &pv);
            if ( ExtensionIdFromExtensionItem >= 0 )
            {
              CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_MergeSort<CExtensionList::PWSTRCompare>(
                &v52,
                v48,
                0,
                v53);
              CoTaskMemFree(pv);
              pv = 0;
            }
          }
          goto LABEL_25;
        }
        v16 = *(_QWORD *)v7;
        v50 = 0;
        v17 = *(__int64 (__fastcall **)(HSTRING, _QWORD, GUID *, struct IExtensionListItem **))(v16 + 32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        v18 = v17(v7, v15, &GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4, &v50);
        v8 = 0;
        ExtensionIdFromExtensionItem = v18;
        if ( v18 >= 0 )
          break;
LABEL_18:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        ++v15;
        if ( ExtensionIdFromExtensionItem < 0 )
          goto LABEL_43;
      }
      string = 0;
      ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(v50, (struct Windows::Internal::String *)&string);
      if ( ExtensionIdFromExtensionItem < 0 )
      {
LABEL_17:
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_18;
      }
      v51 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      ExtensionIdFromExtensionItem = _AllocString<CTCoAllocPolicy>(v21, v20, StringRawBuffer, &v51);
      if ( ExtensionIdFromExtensionItem < 0 )
      {
LABEL_16:
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v51);
        goto LABEL_17;
      }
      v22 = v53;
      ExtensionIdFromExtensionItem = 0;
      v23 = v51;
      if ( v53 == v55 )
      {
        ExtensionIdFromExtensionItem = CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(
                                         &v52,
                                         v53 + 1);
        if ( ExtensionIdFromExtensionItem < 0 )
        {
LABEL_13:
          if ( ExtensionIdFromExtensionItem >= 0 )
            v23 = 0;
          v51 = v23;
          v8 = 0;
          goto LABEL_16;
        }
        v22 = v53;
      }
      v53 = v22 + 1;
      v24 = (const WCHAR **)((char *)v52 + 8 * v22);
      if ( v24 )
        *v24 = v23;
      goto LABEL_13;
    }
  }
LABEL_25:
  for ( i = 0; ExtensionIdFromExtensionItem >= 0 && i < a2[1]; ++i )
  {
    v28 = *a2;
    string = 0;
    ExtensionIdFromExtensionItem = Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(
                                     v28 + 8 * i,
                                     &string);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v29 = string;
      v50 = 0;
      v30 = *(__int64 (__fastcall **)(HSTRING, GUID *, struct IExtensionListItem **))(*(_QWORD *)string + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      v31 = v30(v29, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v50);
      v8 = 0;
      ExtensionIdFromExtensionItem = v31;
      if ( v31 >= 0 )
      {
        if ( !a3 )
          goto LABEL_33;
        v58[0] = v50;
        v60 = 0;
        v59 = 0;
        LODWORD(a7) = 0;
        v58[2] = 0;
        v61 = 0;
        v58[1] = a3;
        v58[3] = 0;
        DoesItemMatchCondition = GrepDoesItemMatchCondition((const struct CONDITIONEVALINFO *)v58, (int *)&a7, v32);
        v34 = (int)a7;
        if ( DoesItemMatchCondition < 0 )
          v34 = 0;
        if ( v34 )
        {
LABEL_33:
          v35 = *a2;
          a7 = 0;
          ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(
                                           *(struct IExtensionListItem **)(v35 + 8 * i),
                                           (struct Windows::Internal::String *)&a7);
          if ( ExtensionIdFromExtensionItem >= 0 )
          {
            v51 = WindowsGetStringRawBuffer(a7, 0);
            if ( (int)CTSimpleFixedArray<unsigned short *,CSimpleArrayStandardCompareHelper<unsigned short *>>::BinarySearchEx<CExtensionList::PWSTRCompare>(
                        &v52,
                        v36,
                        &v51,
                        &v56) < 0 )
            {
              v37 = *(_QWORD *)(a1 + 40);
              ExtensionIdFromExtensionItem = 0;
              v38 = *a2;
              if ( v37 != *(_QWORD *)(a1 + 56)
                || (ExtensionIdFromExtensionItem = CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(
                                                     a1 + 32,
                                                     v37 + 1),
                    ExtensionIdFromExtensionItem >= 0) )
              {
                v39 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * (*(_QWORD *)(a1 + 40))++);
                if ( v39 )
                {
                  *v39 = *(_QWORD *)(v38 + 8 * i);
                  Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef();
                }
              }
            }
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&a7);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    }
    Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&string);
  }
LABEL_43:
  if ( v53 )
  {
    do
      CoTaskMemFree(*((LPVOID *)v52 + v8++));
    while ( v8 < v53 );
  }
  if ( ExtensionIdFromExtensionItem >= 0 )
  {
    if ( a5 && (ExtensionIdFromExtensionItem = 0, v56 = a4, v40 = *(_QWORD *)(a1 + 40), v57 = a5, v40 > 1) )
    {
      v41 = (LPVOID *)(a1 + 48);
      *(_QWORD *)(a1 + 48) = 0;
      a7 = 0;
      ExtensionIdFromExtensionItem = ULongLongMult(v40 >> 1, 8u, (unsigned __int64 *)&a7);
      if ( ExtensionIdFromExtensionItem >= 0 )
        ExtensionIdFromExtensionItem = CTCoAllocPolicy::Realloc(v43, v42, 0, (unsigned __int64)a7, (void **)(a1 + 48));
      if ( ExtensionIdFromExtensionItem >= 0 )
      {
        CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::_MergeSort<CExtensionList::ExtensionCompare>(
          a1 + 32,
          &v56,
          0,
          *(_QWORD *)(a1 + 40));
        CoTaskMemFree(*v41);
        *v41 = 0;
        goto LABEL_52;
      }
    }
    else
    {
LABEL_52:
      while ( 1 )
      {
        v44 = *(_QWORD *)(a1 + 40);
        if ( v44 <= a6 )
          break;
        v45 = v44 - 1;
        if ( !v44 )
        {
          ExtensionIdFromExtensionItem = -2147316575;
          break;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(*(_QWORD *)(a1 + 32) + 8 * v45);
        v46 = *(_QWORD *)(a1 + 40);
        if ( v45 != v46 - 1 )
          memmove_0(
            (void *)(*(_QWORD *)(a1 + 32) + 8 * v45),
            (const void *)(*(_QWORD *)(a1 + 32) + 8 * v45 + 8),
            8 * (v46 - v45) - 8);
        --*(_QWORD *)(a1 + 40);
        ExtensionIdFromExtensionItem = 0;
      }
    }
  }
  if ( v52 )
    CoTaskMemFree(v52);
  return (unsigned int)ExtensionIdFromExtensionItem;
}

```

## disassembly

```asm
0x180231304  mov     [rsp-8+arg_18], r9
0x180231309  push    rbp
0x18023130a  push    rbx
0x18023130b  push    rsi
0x18023130c  push    rdi
0x18023130d  push    r12
0x18023130f  push    r13
0x180231311  push    r14
0x180231313  push    r15
0x180231315  lea     rbp, [rsp-7]
0x18023131a  sub     rsp, 0D8h
0x180231321  mov     r15, [rbp+3Fh+arg_30]
0x180231325  xor     ebx, ebx
0x180231327  mov     [rsp+110h+var_E0], bl
0x18023132b  mov     r13, r8
0x18023132e  mov     [rsp+110h+var_C0], rbx
0x180231333  mov     r12, rdx
0x180231336  mov     [rbp+3Fh+var_B8], rbx
0x18023133a  mov     r14, rcx
0x18023133d  mov     [rbp+3Fh+pv], rbx
0x180231341  mov     edi, ebx
0x180231343  mov     [rbp+3Fh+var_A8], rbx
0x180231347  test    r15, r15
0x18023134a  jz      loc_1802314F3
0x180231350  mov     rax, [r15]
0x180231353  lea     rdx, [rbp+3Fh+arg_30]
0x180231357  mov     rcx, r15
0x18023135a  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x18023135d  mov     rax, [rax+18h]
0x180231361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180231366  mov     edi, eax
0x180231368  test    eax, eax
0x18023136a  js      loc_1802314F3
0x180231370  mov     esi, ebx
0x180231372  cmp     esi, dword ptr [rbp+3Fh+arg_30]
0x180231375  jnb     loc_180231480
0x18023137b  mov     rax, [r15]
0x18023137e  lea     rcx, [rsp+110h+var_D0]
0x180231383  mov     [rsp+110h+var_D0], rbx
0x180231388  mov     rbx, [rax+20h]
0x18023138c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180231391  lea     r9, [rsp+110h+var_D0]
0x180231396  mov     edx, esi
0x180231398  lea     r8, _GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4
0x18023139f  mov     rcx, r15
0x1802313a2  mov     rax, rbx
0x1802313a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802313aa  xor     ebx, ebx
0x1802313ac  mov     edi, eax
0x1802313ae  test    eax, eax
0x1802313b0  js      loc_180231467
0x1802313b6  mov     rcx, [rsp+110h+var_D0]; struct IExtensionListItem *
0x1802313bb  lea     rdx, [rsp+110h+string]; struct Windows::Internal::String *
0x1802313c0  mov     [rsp+110h+string], rbx
0x1802313c5  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x1802313ca  mov     edi, eax
0x1802313cc  test    eax, eax
0x1802313ce  js      loc_18023145D
0x1802313d4  mov     rcx, [rsp+110h+string]; string
0x1802313d9  xor     edx, edx; length
0x1802313db  mov     [rsp+110h+var_C8], rbx
0x1802313e0  call    cs:__imp_WindowsGetStringRawBuffer
0x1802313e7  nop     dword ptr [rax+rax+00h]
0x1802313ec  mov     r8, rax
0x1802313ef  lea     r9, [rsp+110h+var_C8]
0x1802313f4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1802313f9  mov     edi, eax
0x1802313fb  test    eax, eax
0x1802313fd  js      short loc_180231453
0x1802313ff  mov     rcx, [rbp+3Fh+var_B8]
0x180231403  mov     edi, ebx
0x180231405  mov     rbx, [rsp+110h+var_C8]
0x18023140a  cmp     rcx, [rbp+3Fh+var_A8]
0x18023140e  jnz     short loc_180231428
0x180231410  lea     rdx, [rcx+1]
0x180231414  lea     rcx, [rsp+110h+var_C0]
0x180231419  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@@@QEAAJ_K0@Z; CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18023141e  mov     edi, eax
0x180231420  test    eax, eax
0x180231422  js      short loc_180231444
0x180231424  mov     rcx, [rbp+3Fh+var_B8]
0x180231428  mov     rdx, [rsp+110h+var_C0]
0x18023142d  inc     rcx
0x180231430  add     rdx, 0FFFFFFFFFFFFFFF8h
0x180231434  mov     [rbp+3Fh+var_B8], rcx
0x180231438  lea     rdx, [rdx+rcx*8]
0x18023143c  test    rdx, rdx
0x18023143f  jz      short loc_180231444
0x180231441  mov     [rdx], rbx
0x180231444  xor     eax, eax
0x180231446  test    edi, edi
0x180231448  cmovns  rbx, rax
0x18023144c  mov     [rsp+110h+var_C8], rbx
0x180231451  xor     ebx, ebx
0x180231453  lea     rcx, [rsp+110h+var_C8]
0x180231458  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18023145d  lea     rcx, [rsp+110h+string]; this
0x180231462  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180231467  lea     rcx, [rsp+110h+var_D0]
0x18023146c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180231471  inc     esi
0x180231473  test    edi, edi
0x180231475  jns     loc_180231372
0x18023147b  jmp     loc_180231667
0x180231480  mov     rcx, [rbp+3Fh+var_B8]
0x180231484  mov     edi, ebx
0x180231486  cmp     rcx, 1
0x18023148a  jbe     short loc_1802314F3
0x18023148c  shr     rcx, 1; unsigned __int64
0x18023148f  lea     r8, [rsp+110h+string]; unsigned __int64 *
0x180231494  mov     edx, 8; unsigned __int64
0x180231499  mov     [rbp+3Fh+pv], rbx
0x18023149d  mov     [rsp+110h+string], rbx
0x1802314a2  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1802314a7  mov     edi, eax
0x1802314a9  test    eax, eax
0x1802314ab  js      short loc_1802314C5
0x1802314ad  mov     r9, [rsp+110h+string]; unsigned __int64
0x1802314b2  lea     rax, [rbp+3Fh+pv]
0x1802314b6  xor     r8d, r8d; void *
0x1802314b9  mov     [rsp+110h+var_F0], rax; void **
0x1802314be  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1802314c3  mov     edi, eax
0x1802314c5  test    edi, edi
0x1802314c7  js      short loc_1802314F3
0x1802314c9  mov     r9, [rbp+3Fh+var_B8]
0x1802314cd  lea     rdx, [rsp+110h+var_E0]
0x1802314d2  xor     r8d, r8d
0x1802314d5  lea     rcx, [rsp+110h+var_C0]
0x1802314da  call    ??$_MergeSort@VPWSTRCompare@CExtensionList@@@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXAEBVPWSTRCompare@CExtensionList@@_K1@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_MergeSort<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,unsigned __int64,unsigned __int64)
0x1802314df  mov     rcx, [rbp+3Fh+pv]; pv
0x1802314e3  call    cs:__imp_CoTaskMemFree
0x1802314ea  nop     dword ptr [rax+rax+00h]
0x1802314ef  mov     [rbp+3Fh+pv], rbx
0x1802314f3  mov     rsi, rbx
0x1802314f6  jmp     loc_18023165F
0x1802314fb  cmp     rsi, [r12+8]
0x180231500  jnb     loc_180231667
0x180231506  mov     rax, [r12]
0x18023150a  lea     rdx, [rsp+110h+string]
0x18023150f  mov     [rsp+110h+string], rbx
0x180231514  lea     rcx, [rax+rsi*8]
0x180231518  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x18023151d  mov     edi, eax
0x18023151f  test    eax, eax
0x180231521  js      loc_180231652
0x180231527  mov     rdi, [rsp+110h+string]
0x18023152c  lea     rcx, [rsp+110h+var_D0]
0x180231531  mov     [rsp+110h+var_D0], rbx
0x180231536  mov     rax, [rdi]
0x180231539  mov     rbx, [rax+18h]
0x18023153d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180231542  lea     r8, [rsp+110h+var_D0]
0x180231547  mov     rcx, rdi
0x18023154a  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180231551  mov     rax, rbx
0x180231554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180231559  xor     ebx, ebx
0x18023155b  mov     edi, eax
0x18023155d  test    eax, eax
0x18023155f  js      loc_180231648
0x180231565  test    r13, r13
0x180231568  jz      short loc_1802315B0
0x18023156a  mov     rax, [rsp+110h+var_D0]
0x18023156f  lea     rdx, [rbp+3Fh+arg_30]; int *
0x180231573  xorps   xmm0, xmm0
0x180231576  mov     [rbp+3Fh+var_90], rax
0x18023157a  lea     rcx, [rbp+3Fh+var_90]; struct CONDITIONEVALINFO *
0x18023157e  movdqa  [rbp+3Fh+var_60], xmm0
0x180231583  movdqa  [rbp+3Fh+var_70], xmm0
0x180231588  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x18023158b  mov     [rbp+3Fh+var_80], rbx
0x18023158f  mov     [rbp+3Fh+var_50], rbx
0x180231593  mov     [rbp+3Fh+var_88], r13
0x180231597  mov     [rbp+3Fh+var_78], rbx
0x18023159b  call    ?GrepDoesItemMatchCondition@@YAJPEBUCONDITIONEVALINFO@@PEAHPEAUCONDITIONEVALPROPS@@@Z; GrepDoesItemMatchCondition(CONDITIONEVALINFO const *,int *,CONDITIONEVALPROPS *)
0x1802315a0  mov     edx, dword ptr [rbp+3Fh+arg_30]
0x1802315a3  test    eax, eax
0x1802315a5  cmovs   edx, ebx
0x1802315a8  test    edx, edx
0x1802315aa  jz      loc_180231648
0x1802315b0  mov     rcx, [r12]
0x1802315b4  lea     rdx, [rbp+3Fh+arg_30]; struct Windows::Internal::String *
0x1802315b8  mov     [rbp+3Fh+arg_30], rbx
0x1802315bc  mov     rcx, [rcx+rsi*8]; struct IExtensionListItem *
0x1802315c0  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x1802315c5  mov     edi, eax
0x1802315c7  test    eax, eax
0x1802315c9  js      short loc_18023163F
0x1802315cb  mov     rcx, [rbp+3Fh+arg_30]; string
0x1802315cf  xor     edx, edx; length
0x1802315d1  call    cs:__imp_WindowsGetStringRawBuffer
0x1802315d8  nop     dword ptr [rax+rax+00h]
0x1802315dd  lea     r9, [rbp+3Fh+var_A0]
0x1802315e1  mov     [rsp+110h+var_C8], rax
0x1802315e6  lea     r8, [rsp+110h+var_C8]
0x1802315eb  lea     rcx, [rsp+110h+var_C0]
0x1802315f0  call    ??$BinarySearchEx@VPWSTRCompare@CExtensionList@@@?$CTSimpleFixedArray@PEAGV?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEBAJAEBVPWSTRCompare@CExtensionList@@AEBQEAGPEA_K@Z; CTSimpleFixedArray<ushort *,CSimpleArrayStandardCompareHelper<ushort *>>::BinarySearchEx<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,ushort * const &,unsigned __int64 *)
0x1802315f5  test    eax, eax
0x1802315f7  jns     short loc_18023163F
0x1802315f9  mov     rdx, [r14+28h]
0x1802315fd  xor     edi, edi
0x1802315ff  mov     r15, [r12]
0x180231603  cmp     rdx, [r14+38h]
0x180231607  jnz     short loc_18023161B
0x180231609  inc     rdx
0x18023160c  lea     rcx, [r14+20h]
0x180231610  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardCompareHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@V?$CSimpleArrayStandardMergeHelper@PEAUSlowKeysDelayItem@CSlowKeysDwordRangeSetting@DataModel@SystemSettings@@@@@@QEAAJ_K0@Z; CTSimpleArray<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *,4294967294,CTPolicyCoTaskMem<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardCompareHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>,CSimpleArrayStandardMergeHelper<SystemSettings::DataModel::CSlowKeysDwordRangeSetting::SlowKeysDelayItem *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180231615  mov     edi, eax
0x180231617  test    eax, eax
0x180231619  js      short loc_18023163F
0x18023161b  inc     qword ptr [r14+28h]
0x18023161f  mov     rcx, [r14+28h]
0x180231623  mov     rax, [r14+20h]
0x180231627  dec     rcx
0x18023162a  lea     rcx, [rax+rcx*8]
0x18023162e  test    rcx, rcx
0x180231631  jz      short loc_18023163F
0x180231633  mov     rax, [r15+rsi*8]
0x180231637  mov     [rcx], rax
0x18023163a  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18023163f  lea     rcx, [rbp+3Fh+arg_30]; this
0x180231643  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180231648  lea     rcx, [rsp+110h+var_D0]
0x18023164d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180231652  lea     rcx, [rsp+110h+string]
0x180231657  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18023165c  inc     rsi
0x18023165f  test    edi, edi
0x180231661  jns     loc_1802314FB
0x180231667  xor     r15d, r15d
0x18023166a  cmp     [rbp+3Fh+var_B8], r15
0x18023166e  jbe     short loc_18023168E
0x180231670  mov     rcx, [rsp+110h+var_C0]
0x180231675  mov     rcx, [rcx+rbx*8]; pv
0x180231679  call    cs:__imp_CoTaskMemFree
0x180231680  nop     dword ptr [rax+rax+00h]
0x180231685  inc     rbx
0x180231688  cmp     rbx, [rbp+3Fh+var_B8]
0x18023168c  jb      short loc_180231670
0x18023168e  test    edi, edi
0x180231690  js      loc_180231775
0x180231696  mov     eax, [rbp+3Fh+arg_20]
0x180231699  test    eax, eax
0x18023169b  jz      short loc_18023171C
0x18023169d  mov     rcx, [rbp+3Fh+arg_18]
0x1802316a1  mov     edi, r15d
0x1802316a4  mov     [rbp+3Fh+var_A0], rcx
0x1802316a8  mov     rcx, [r14+28h]
0x1802316ac  mov     [rbp+3Fh+var_98], eax
0x1802316af  cmp     rcx, 1
0x1802316b3  jbe     short loc_180231718
0x1802316b5  lea     rsi, [r14+30h]
0x1802316b9  shr     rcx, 1; unsigned __int64
0x1802316bc  lea     r8, [rbp+3Fh+arg_30]; unsigned __int64 *
0x1802316c0  mov     [rsi], r15
0x1802316c3  mov     edx, 8; unsigned __int64
0x1802316c8  mov     [rbp+3Fh+arg_30], r15
0x1802316cc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1802316d1  mov     edi, eax
0x1802316d3  test    eax, eax
0x1802316d5  js      short loc_1802316EA
0x1802316d7  mov     r9, [rbp+3Fh+arg_30]; unsigned __int64
0x1802316db  xor     r8d, r8d; void *
0x1802316de  mov     [rsp+110h+var_F0], rsi; void **
0x1802316e3  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1802316e8  mov     edi, eax
0x1802316ea  test    edi, edi
0x1802316ec  js      loc_180231775
0x1802316f2  mov     r9, [r14+28h]
0x1802316f6  lea     rdx, [rbp+3Fh+var_A0]
0x1802316fa  xor     r8d, r8d
0x1802316fd  lea     rcx, [r14+20h]
0x180231701  call    ??$_MergeSort@VExtensionCompare@CExtensionList@@@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXAEBVExtensionCompare@CExtensionList@@_K1@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::_MergeSort<CExtensionList::ExtensionCompare>(CExtensionList::ExtensionCompare const &,unsigned __int64,unsigned __int64)
0x180231706  mov     rcx, [rsi]; pv
0x180231709  call    cs:__imp_CoTaskMemFree
0x180231710  nop     dword ptr [rax+rax+00h]
0x180231715  mov     [rsi], r15
0x180231718  test    edi, edi
0x18023171a  js      short loc_180231775
0x18023171c  mov     esi, [rbp+3Fh+arg_28]
0x18023171f  mov     rax, [r14+28h]
0x180231723  cmp     rax, rsi
0x180231726  jbe     short loc_180231775
0x180231728  lea     rbx, [rax-1]
0x18023172c  cmp     rbx, rax
0x18023172f  jnb     short loc_180231770
0x180231731  mov     rax, [r14+20h]
0x180231735  lea     rcx, [rax+rbx*8]
0x180231739  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18023173e  mov     r8, [r14+28h]
0x180231742  lea     rax, [r8-1]
0x180231746  cmp     rbx, rax
0x180231749  jz      short loc_180231767
0x18023174b  mov     rax, [r14+20h]
0x18023174f  sub     r8, rbx
0x180231752  lea     rcx, [rax+rbx*8]; void *
0x180231756  lea     rdx, [rcx+8]; Src
0x18023175a  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x180231762  call    memmove_0
  ... truncated ...
```
