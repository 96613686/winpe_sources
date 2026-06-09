# CExtensionList::_InitializeWithFilterAndSortOptions(CCoSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>> &,ICondition *,SORTCOLUMN *,uint,uint,IObjectArray *)

- ea: `0x18004a4dc`
- end: `0x18004a964`
- name: `?_InitializeWithFilterAndSortOptions@CExtensionList@@AEAAJAEAV?$CCoSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@PEAUICondition@@PEAUSORTCOLUMN@@IIPEAUIObjectArray@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, HSTRING)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045e50`

## callees

- `0x180003118`
- `0x180007b3c`
- `0x1800107a0`
- `0x180011724`
- `0x18001f424`
- `0x18002b230`
- `0x18002e7c0`
- `0x18003e0d4`
- `0x18003e3a8`
- `0x18003ed0c`
- `0x180043014`
- `0x1800431bc`
- `0x180043704`
- `0x1800437b4`
- `0x1800463a4`
- `0x180049834`
- `0x18004a4dc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a5b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a7b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a5b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004a7b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a6c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a852`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a6c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a852`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a8d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a948`

## pseudocode

```c
__int64 __fastcall CExtensionList::_InitializeWithFilterAndSortOptions(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned __int64 a4,
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
  __int64 v21; // r9
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
  unsigned __int64 v56; // [rsp+70h] [rbp-61h] BYREF
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
                (__int64)&v52,
                (__int64)v48,
                0,
                v53);
              CoTaskMemFree(pv);
              pv = 0;
            }
          }
          goto LABEL_27;
        }
        v16 = *(_QWORD *)v7;
        v50 = 0;
        v17 = *(__int64 (__fastcall **)(HSTRING, _QWORD, GUID *, struct IExtensionListItem **))(v16 + 32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v50);
        v18 = v17(v7, v15, &GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4, &v50);
        v8 = 0;
        ExtensionIdFromExtensionItem = v18;
        if ( v18 >= 0 )
          break;
LABEL_20:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v50);
        ++v15;
        if ( ExtensionIdFromExtensionItem < 0 )
          goto LABEL_45;
      }
      string = 0;
      ExtensionIdFromExtensionItem = _GetExtensionIdFromExtensionItem(v50, (struct Windows::Internal::String *)&string);
      if ( ExtensionIdFromExtensionItem < 0 )
      {
LABEL_19:
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        goto LABEL_20;
      }
      v51 = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v21 = -1;
      do
        ++v21;
      while ( StringRawBuffer[v21] );
      ExtensionIdFromExtensionItem = _AllocStringWorker<CTCoAllocPolicy>(&v51, v20, StringRawBuffer);
      if ( ExtensionIdFromExtensionItem < 0 )
      {
LABEL_18:
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>((void **)&v51);
        goto LABEL_19;
      }
      v22 = v53;
      ExtensionIdFromExtensionItem = 0;
      v23 = v51;
      if ( v53 == v55 )
      {
        ExtensionIdFromExtensionItem = CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(
                                         &v52,
                                         v53 + 1);
        if ( ExtensionIdFromExtensionItem < 0 )
        {
LABEL_15:
          if ( ExtensionIdFromExtensionItem >= 0 )
            v23 = 0;
          v51 = v23;
          v8 = 0;
          goto LABEL_18;
        }
        v22 = v53;
      }
      v53 = v22 + 1;
      v24 = (const WCHAR **)((char *)v52 + 8 * v22);
      if ( v24 )
        *v24 = v23;
      goto LABEL_15;
    }
  }
LABEL_27:
  for ( i = 0; ExtensionIdFromExtensionItem >= 0 && i < a2[1]; ++i )
  {
    v28 = *a2;
    string = 0;
    ExtensionIdFromExtensionItem = Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(
                                     (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(v28 + 8 * i),
                                     (__int64)&string);
    if ( ExtensionIdFromExtensionItem >= 0 )
    {
      v29 = string;
      v50 = 0;
      v30 = *(__int64 (__fastcall **)(HSTRING, GUID *, struct IExtensionListItem **))(*(_QWORD *)string + 24LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v50);
      v31 = v30(v29, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v50);
      v8 = 0;
      ExtensionIdFromExtensionItem = v31;
      if ( v31 >= 0 )
      {
        if ( !a3 )
          goto LABEL_35;
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
LABEL_35:
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
                || (ExtensionIdFromExtensionItem = CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(
                                                     a1 + 32,
                                                     v37 + 1),
                    ExtensionIdFromExtensionItem >= 0) )
              {
                v39 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 8 * (*(_QWORD *)(a1 + 40))++);
                if ( v39 )
                {
                  *v39 = *(_QWORD *)(v38 + 8 * i);
                  Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(v39);
                }
              }
            }
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&a7);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v50);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&string);
  }
LABEL_45:
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
          (__int64)&v56,
          0,
          *(_QWORD *)(a1 + 40));
        CoTaskMemFree(*v41);
        *v41 = 0;
        goto LABEL_54;
      }
    }
    else
    {
LABEL_54:
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
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(*(_QWORD *)(a1 + 32) + 8 * v45);
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
0x18004a4dc  mov     [rsp-8+arg_18], r9
0x18004a4e1  push    rbp
0x18004a4e2  push    rbx
0x18004a4e3  push    rsi
0x18004a4e4  push    rdi
0x18004a4e5  push    r12
0x18004a4e7  push    r13
0x18004a4e9  push    r14
0x18004a4eb  push    r15
0x18004a4ed  lea     rbp, [rsp-7]
0x18004a4f2  sub     rsp, 0D8h
0x18004a4f9  mov     r15, [rbp+3Fh+arg_30]
0x18004a4fd  xor     ebx, ebx
0x18004a4ff  mov     [rsp+110h+var_E0], bl
0x18004a503  mov     r13, r8
0x18004a506  mov     [rsp+110h+var_C0], rbx
0x18004a50b  mov     r12, rdx
0x18004a50e  mov     [rbp+3Fh+var_B8], rbx
0x18004a512  mov     r14, rcx
0x18004a515  mov     [rbp+3Fh+pv], rbx
0x18004a519  mov     edi, ebx
0x18004a51b  mov     [rbp+3Fh+var_A8], rbx
0x18004a51f  test    r15, r15
0x18004a522  jz      loc_18004A6D2
0x18004a528  mov     rax, [r15]
0x18004a52b  lea     rdx, [rbp+3Fh+arg_30]
0x18004a52f  mov     rcx, r15
0x18004a532  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x18004a535  mov     rax, [rax+18h]
0x18004a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a53e  mov     edi, eax
0x18004a540  test    eax, eax
0x18004a542  js      loc_18004A6D2
0x18004a548  mov     esi, ebx
0x18004a54a  cmp     esi, dword ptr [rbp+3Fh+arg_30]
0x18004a54d  jnb     loc_18004A665
0x18004a553  mov     rax, [r15]
0x18004a556  lea     rcx, [rsp+110h+var_D0]
0x18004a55b  mov     [rsp+110h+var_D0], rbx
0x18004a560  mov     rbx, [rax+20h]
0x18004a564  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a569  lea     r9, [rsp+110h+var_D0]
0x18004a56e  mov     edx, esi
0x18004a570  lea     r8, _GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4
0x18004a577  mov     rcx, r15
0x18004a57a  mov     rax, rbx
0x18004a57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a582  xor     ebx, ebx
0x18004a584  mov     edi, eax
0x18004a586  test    eax, eax
0x18004a588  js      loc_18004A64C
0x18004a58e  mov     rcx, [rsp+110h+var_D0]; struct IExtensionListItem *
0x18004a593  lea     rdx, [rsp+110h+string]; struct Windows::Internal::String *
0x18004a598  mov     [rsp+110h+string], rbx
0x18004a59d  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x18004a5a2  mov     edi, eax
0x18004a5a4  test    eax, eax
0x18004a5a6  js      loc_18004A642
0x18004a5ac  mov     rcx, [rsp+110h+string]; string
0x18004a5b1  xor     edx, edx; length
0x18004a5b3  mov     [rsp+110h+var_C8], rbx
0x18004a5b8  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a5be  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004a5c2  inc     r9
0x18004a5c5  cmp     [rax+r9*2], bx
0x18004a5ca  jnz     short loc_18004A5C2
0x18004a5cc  lea     rcx, [rsp+110h+var_C8]
0x18004a5d1  mov     r8, rax
0x18004a5d4  mov     [rsp+110h+var_E8], rcx
0x18004a5d9  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18004a5de  mov     edi, eax
0x18004a5e0  test    eax, eax
0x18004a5e2  js      short loc_18004A638
0x18004a5e4  mov     rcx, [rbp+3Fh+var_B8]
0x18004a5e8  mov     edi, ebx
0x18004a5ea  mov     rbx, [rsp+110h+var_C8]
0x18004a5ef  cmp     rcx, [rbp+3Fh+var_A8]
0x18004a5f3  jnz     short loc_18004A60D
0x18004a5f5  lea     rdx, [rcx+1]
0x18004a5f9  lea     rcx, [rsp+110h+var_C0]
0x18004a5fe  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardCompareHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardMergeHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@@@QEAAJ_K0@Z; CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004a603  mov     edi, eax
0x18004a605  test    eax, eax
0x18004a607  js      short loc_18004A629
0x18004a609  mov     rcx, [rbp+3Fh+var_B8]
0x18004a60d  mov     rdx, [rsp+110h+var_C0]
0x18004a612  inc     rcx
0x18004a615  add     rdx, 0FFFFFFFFFFFFFFF8h
0x18004a619  mov     [rbp+3Fh+var_B8], rcx
0x18004a61d  lea     rdx, [rdx+rcx*8]
0x18004a621  test    rdx, rdx
0x18004a624  jz      short loc_18004A629
0x18004a626  mov     [rdx], rbx
0x18004a629  xor     eax, eax
0x18004a62b  test    edi, edi
0x18004a62d  cmovns  rbx, rax
0x18004a631  mov     [rsp+110h+var_C8], rbx
0x18004a636  xor     ebx, ebx
0x18004a638  lea     rcx, [rsp+110h+var_C8]
0x18004a63d  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18004a642  lea     rcx, [rsp+110h+string]; this
0x18004a647  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004a64c  lea     rcx, [rsp+110h+var_D0]
0x18004a651  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a656  inc     esi
0x18004a658  test    edi, edi
0x18004a65a  jns     loc_18004A54A
0x18004a660  jmp     loc_18004A840
0x18004a665  mov     rcx, [rbp+3Fh+var_B8]
0x18004a669  mov     edi, ebx
0x18004a66b  cmp     rcx, 1
0x18004a66f  jbe     short loc_18004A6D2
0x18004a671  shr     rcx, 1; unsigned __int64
0x18004a674  lea     r8, [rsp+110h+string]; unsigned __int64 *
0x18004a679  mov     edx, 8; unsigned __int64
0x18004a67e  mov     [rbp+3Fh+pv], rbx
0x18004a682  mov     [rsp+110h+string], rbx
0x18004a687  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004a68c  mov     edi, eax
0x18004a68e  test    eax, eax
0x18004a690  js      short loc_18004A6AA
0x18004a692  mov     r9, [rsp+110h+string]; unsigned __int64
0x18004a697  lea     rax, [rbp+3Fh+pv]
0x18004a69b  xor     r8d, r8d; void *
0x18004a69e  mov     [rsp+110h+var_F0], rax; void **
0x18004a6a3  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18004a6a8  mov     edi, eax
0x18004a6aa  test    edi, edi
0x18004a6ac  js      short loc_18004A6D2
0x18004a6ae  mov     r9, [rbp+3Fh+var_B8]
0x18004a6b2  lea     rdx, [rsp+110h+var_E0]
0x18004a6b7  xor     r8d, r8d
0x18004a6ba  lea     rcx, [rsp+110h+var_C0]
0x18004a6bf  call    ??$_MergeSort@VPWSTRCompare@CExtensionList@@@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXAEBVPWSTRCompare@CExtensionList@@_K1@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_MergeSort<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,unsigned __int64,unsigned __int64)
0x18004a6c4  mov     rcx, [rbp+3Fh+pv]; pv
0x18004a6c8  call    cs:__imp_CoTaskMemFree
0x18004a6ce  mov     [rbp+3Fh+pv], rbx
0x18004a6d2  mov     rsi, rbx
0x18004a6d5  jmp     loc_18004A838
0x18004a6da  cmp     rsi, [r12+8]
0x18004a6df  jnb     loc_18004A840
0x18004a6e5  mov     rax, [r12]
0x18004a6e9  lea     rdx, [rsp+110h+string]
0x18004a6ee  mov     [rsp+110h+string], rbx
0x18004a6f3  lea     rcx, [rax+rsi*8]
0x18004a6f7  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x18004a6fc  mov     edi, eax
0x18004a6fe  test    eax, eax
0x18004a700  js      loc_18004A82B
0x18004a706  mov     rdi, [rsp+110h+string]
0x18004a70b  lea     rcx, [rsp+110h+var_D0]
0x18004a710  mov     [rsp+110h+var_D0], rbx
0x18004a715  mov     rax, [rdi]
0x18004a718  mov     rbx, [rax+18h]
0x18004a71c  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a721  lea     r8, [rsp+110h+var_D0]
0x18004a726  mov     rcx, rdi
0x18004a729  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18004a730  mov     rax, rbx
0x18004a733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a738  xor     ebx, ebx
0x18004a73a  mov     edi, eax
0x18004a73c  test    eax, eax
0x18004a73e  js      loc_18004A821
0x18004a744  test    r13, r13
0x18004a747  jz      short loc_18004A78F
0x18004a749  mov     rax, [rsp+110h+var_D0]
0x18004a74e  lea     rdx, [rbp+3Fh+arg_30]; int *
0x18004a752  xorps   xmm0, xmm0
0x18004a755  mov     [rbp+3Fh+var_90], rax
0x18004a759  lea     rcx, [rbp+3Fh+var_90]; struct CONDITIONEVALINFO *
0x18004a75d  movdqa  [rbp+3Fh+var_60], xmm0
0x18004a762  movdqa  [rbp+3Fh+var_70], xmm0
0x18004a767  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x18004a76a  mov     [rbp+3Fh+var_80], rbx
0x18004a76e  mov     [rbp+3Fh+var_50], rbx
0x18004a772  mov     [rbp+3Fh+var_88], r13
0x18004a776  mov     [rbp+3Fh+var_78], rbx
0x18004a77a  call    ?GrepDoesItemMatchCondition@@YAJPEBUCONDITIONEVALINFO@@PEAHPEAUCONDITIONEVALPROPS@@@Z; GrepDoesItemMatchCondition(CONDITIONEVALINFO const *,int *,CONDITIONEVALPROPS *)
0x18004a77f  mov     edx, dword ptr [rbp+3Fh+arg_30]
0x18004a782  test    eax, eax
0x18004a784  cmovs   edx, ebx
0x18004a787  test    edx, edx
0x18004a789  jz      loc_18004A821
0x18004a78f  mov     rcx, [r12]
0x18004a793  lea     rdx, [rbp+3Fh+arg_30]; struct Windows::Internal::String *
0x18004a797  mov     [rbp+3Fh+arg_30], rbx
0x18004a79b  mov     rcx, [rcx+rsi*8]; struct IExtensionListItem *
0x18004a79f  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x18004a7a4  mov     edi, eax
0x18004a7a6  test    eax, eax
0x18004a7a8  js      short loc_18004A818
0x18004a7aa  mov     rcx, [rbp+3Fh+arg_30]; string
0x18004a7ae  xor     edx, edx; length
0x18004a7b0  call    cs:__imp_WindowsGetStringRawBuffer
0x18004a7b6  lea     r9, [rbp+3Fh+var_A0]
0x18004a7ba  mov     [rsp+110h+var_C8], rax
0x18004a7bf  lea     r8, [rsp+110h+var_C8]
0x18004a7c4  lea     rcx, [rsp+110h+var_C0]
0x18004a7c9  call    ??$BinarySearchEx@VPWSTRCompare@CExtensionList@@@?$CTSimpleFixedArray@PEAGV?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEBAJAEBVPWSTRCompare@CExtensionList@@AEBQEAGPEA_K@Z; CTSimpleFixedArray<ushort *,CSimpleArrayStandardCompareHelper<ushort *>>::BinarySearchEx<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,ushort * const &,unsigned __int64 *)
0x18004a7ce  test    eax, eax
0x18004a7d0  jns     short loc_18004A818
0x18004a7d2  mov     rdx, [r14+28h]
0x18004a7d6  xor     edi, edi
0x18004a7d8  mov     r15, [r12]
0x18004a7dc  cmp     rdx, [r14+38h]
0x18004a7e0  jnz     short loc_18004A7F4
0x18004a7e2  inc     rdx
0x18004a7e5  lea     rcx, [r14+20h]
0x18004a7e9  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardCompareHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@V?$CSimpleArrayStandardMergeHelper@PEAUISearchSuggestion@Core@Search@ApplicationModel@Windows@@@@@@QEAAJ_K0@Z; CTSimpleArray<Windows::ApplicationModel::Search::Core::ISearchSuggestion *,4294967294,CTPolicyCoTaskMem<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardCompareHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>,CSimpleArrayStandardMergeHelper<Windows::ApplicationModel::Search::Core::ISearchSuggestion *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004a7ee  mov     edi, eax
0x18004a7f0  test    eax, eax
0x18004a7f2  js      short loc_18004A818
0x18004a7f4  inc     qword ptr [r14+28h]
0x18004a7f8  mov     rcx, [r14+28h]
0x18004a7fc  mov     rax, [r14+20h]
0x18004a800  dec     rcx
0x18004a803  lea     rcx, [rax+rcx*8]
0x18004a807  test    rcx, rcx
0x18004a80a  jz      short loc_18004A818
0x18004a80c  mov     rax, [r15+rsi*8]
0x18004a810  mov     [rcx], rax
0x18004a813  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x18004a818  lea     rcx, [rbp+3Fh+arg_30]; this
0x18004a81c  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004a821  lea     rcx, [rsp+110h+var_D0]
0x18004a826  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a82b  lea     rcx, [rsp+110h+string]
0x18004a830  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x18004a835  inc     rsi
0x18004a838  test    edi, edi
0x18004a83a  jns     loc_18004A6DA
0x18004a840  xor     r15d, r15d
0x18004a843  cmp     [rbp+3Fh+var_B8], r15
0x18004a847  jbe     short loc_18004A861
0x18004a849  mov     rcx, [rsp+110h+var_C0]
0x18004a84e  mov     rcx, [rcx+rbx*8]; pv
0x18004a852  call    cs:__imp_CoTaskMemFree
0x18004a858  inc     rbx
0x18004a85b  cmp     rbx, [rbp+3Fh+var_B8]
0x18004a85f  jb      short loc_18004A849
0x18004a861  test    edi, edi
0x18004a863  js      loc_18004A93E
0x18004a869  mov     eax, [rbp+3Fh+arg_20]
0x18004a86c  test    eax, eax
0x18004a86e  jz      short loc_18004A8E5
0x18004a870  mov     rcx, [rbp+3Fh+arg_18]
0x18004a874  mov     edi, r15d
0x18004a877  mov     [rbp+3Fh+var_A0], rcx
0x18004a87b  mov     rcx, [r14+28h]
0x18004a87f  mov     [rbp+3Fh+var_98], eax
0x18004a882  cmp     rcx, 1
0x18004a886  jbe     short loc_18004A8E1
0x18004a888  lea     rsi, [r14+30h]
0x18004a88c  shr     rcx, 1; unsigned __int64
0x18004a88f  lea     r8, [rbp+3Fh+arg_30]; unsigned __int64 *
0x18004a893  mov     [rsi], r15
0x18004a896  mov     edx, 8; unsigned __int64
0x18004a89b  mov     [rbp+3Fh+arg_30], r15
0x18004a89f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004a8a4  mov     edi, eax
0x18004a8a6  test    eax, eax
0x18004a8a8  js      short loc_18004A8BD
0x18004a8aa  mov     r9, [rbp+3Fh+arg_30]; unsigned __int64
0x18004a8ae  xor     r8d, r8d; void *
0x18004a8b1  mov     [rsp+110h+var_F0], rsi; void **
0x18004a8b6  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x18004a8bb  mov     edi, eax
0x18004a8bd  test    edi, edi
0x18004a8bf  js      short loc_18004A93E
0x18004a8c1  mov     r9, [r14+28h]
0x18004a8c5  lea     rdx, [rbp+3Fh+var_A0]
0x18004a8c9  xor     r8d, r8d
0x18004a8cc  lea     rcx, [r14+20h]
0x18004a8d0  call    ??$_MergeSort@VExtensionCompare@CExtensionList@@@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXAEBVExtensionCompare@CExtensionList@@_K1@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::_MergeSort<CExtensionList::ExtensionCompare>(CExtensionList::ExtensionCompare const &,unsigned __int64,unsigned __int64)
0x18004a8d5  mov     rcx, [rsi]; pv
0x18004a8d8  call    cs:__imp_CoTaskMemFree
0x18004a8de  mov     [rsi], r15
0x18004a8e1  test    edi, edi
0x18004a8e3  js      short loc_18004A93E
0x18004a8e5  mov     esi, [rbp+3Fh+arg_28]
0x18004a8e8  mov     rax, [r14+28h]
0x18004a8ec  cmp     rax, rsi
0x18004a8ef  jbe     short loc_18004A93E
0x18004a8f1  lea     rbx, [rax-1]
0x18004a8f5  cmp     rbx, rax
0x18004a8f8  jnb     short loc_18004A939
0x18004a8fa  mov     rax, [r14+20h]
0x18004a8fe  lea     rcx, [rax+rbx*8]
0x18004a902  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18004a907  mov     r8, [r14+28h]
0x18004a90b  lea     rax, [r8-1]
0x18004a90f  cmp     rbx, rax
0x18004a912  jz      short loc_18004A930
0x18004a914  mov     rax, [r14+20h]
0x18004a918  sub     r8, rbx
0x18004a91b  lea     rcx, [rax+rbx*8]; void *
0x18004a91f  lea     rdx, [rcx+8]; Src
0x18004a923  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x18004a92b  call    memmove_0
  ... truncated ...
```
