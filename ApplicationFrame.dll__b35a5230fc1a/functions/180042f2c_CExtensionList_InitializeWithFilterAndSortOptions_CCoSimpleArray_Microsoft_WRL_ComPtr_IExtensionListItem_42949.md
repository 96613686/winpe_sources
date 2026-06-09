# CExtensionList::_InitializeWithFilterAndSortOptions(CCoSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>> &,ICondition *,SORTCOLUMN *,uint,uint,IObjectArray *)

- ea: `0x180042f2c`
- end: `0x1800433a1`
- name: `?_InitializeWithFilterAndSortOptions@CExtensionList@@AEAAJAEAV?$CCoSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@PEAUICondition@@PEAUSORTCOLUMN@@IIPEAUIObjectArray@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, HSTRING)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180042dd0`

## callees

- `0x180004c98`
- `0x18002dc90`
- `0x18002e020`
- `0x180032c3c`
- `0x18003f150`
- `0x180042f2c`
- `0x180046f7a`
- `0x180061b4c`
- `0x180061ce4`
- `0x180061e8c`
- `0x18006229c`
- `0x18006234c`
- `0x180062ccc`
- `0x180065114`
- `0x180066100`
- `0x180067c88`
- `0x1800687a0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800431ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800431ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004328f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004328f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043315`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043385`

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
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v50);
        v18 = v17(v7, v15, &GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4, &v50);
        v8 = 0;
        ExtensionIdFromExtensionItem = v18;
        if ( v18 >= 0 )
          break;
LABEL_18:
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v50);
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
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v51);
        goto LABEL_17;
      }
      v22 = v53;
      ExtensionIdFromExtensionItem = 0;
      v23 = v51;
      if ( v53 == v55 )
      {
        ExtensionIdFromExtensionItem = CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_EnsureCapacity(
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
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v50);
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
                || (ExtensionIdFromExtensionItem = CTSimpleArray<unsigned short *,4294967294,CTPolicyCoTaskMem<unsigned short *>,CSimpleArrayStandardCompareHelper<unsigned short *>,CSimpleArrayStandardMergeHelper<unsigned short *>>::_EnsureCapacity(
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
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v50);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(&string);
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
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(*(_QWORD *)(a1 + 32) + 8 * v45);
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
0x180042f2c  mov     [rsp-8+arg_18], r9
0x180042f31  push    rbp
0x180042f32  push    rbx
0x180042f33  push    rsi
0x180042f34  push    rdi
0x180042f35  push    r12
0x180042f37  push    r13
0x180042f39  push    r14
0x180042f3b  push    r15
0x180042f3d  lea     rbp, [rsp-7]
0x180042f42  sub     rsp, 0D8h
0x180042f49  mov     r15, [rbp+3Fh+arg_30]
0x180042f4d  xor     ebx, ebx
0x180042f4f  mov     [rsp+110h+var_E0], bl
0x180042f53  mov     r13, r8
0x180042f56  mov     [rsp+110h+var_C0], rbx
0x180042f5b  mov     r12, rdx
0x180042f5e  mov     [rbp+3Fh+var_B8], rbx
0x180042f62  mov     r14, rcx
0x180042f65  mov     [rbp+3Fh+pv], rbx
0x180042f69  mov     edi, ebx
0x180042f6b  mov     [rbp+3Fh+var_A8], rbx
0x180042f6f  test    r15, r15
0x180042f72  jz      loc_18004310F
0x180042f78  mov     rax, [r15]
0x180042f7b  lea     rdx, [rbp+3Fh+arg_30]
0x180042f7f  mov     rcx, r15
0x180042f82  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x180042f85  mov     rax, [rax+18h]
0x180042f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f8e  mov     edi, eax
0x180042f90  test    eax, eax
0x180042f92  js      loc_18004310F
0x180042f98  mov     esi, ebx
0x180042f9a  cmp     esi, dword ptr [rbp+3Fh+arg_30]
0x180042f9d  jnb     loc_1800430A2
0x180042fa3  mov     rax, [r15]
0x180042fa6  lea     rcx, [rsp+110h+var_D0]
0x180042fab  mov     [rsp+110h+var_D0], rbx
0x180042fb0  mov     rbx, [rax+20h]
0x180042fb4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180042fb9  lea     r9, [rsp+110h+var_D0]
0x180042fbe  mov     edx, esi
0x180042fc0  lea     r8, _GUID_51c82e0a_1438_4979_8d15_cc7ce56e52e4
0x180042fc7  mov     rcx, r15
0x180042fca  mov     rax, rbx
0x180042fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fd2  xor     ebx, ebx
0x180042fd4  mov     edi, eax
0x180042fd6  test    eax, eax
0x180042fd8  js      loc_180043089
0x180042fde  mov     rcx, [rsp+110h+var_D0]; struct IExtensionListItem *
0x180042fe3  lea     rdx, [rsp+110h+string]; struct Windows::Internal::String *
0x180042fe8  mov     [rsp+110h+string], rbx
0x180042fed  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x180042ff2  mov     edi, eax
0x180042ff4  test    eax, eax
0x180042ff6  js      loc_18004307F
0x180042ffc  mov     rcx, [rsp+110h+string]; string
0x180043001  xor     edx, edx; length
0x180043003  mov     [rsp+110h+var_C8], rbx
0x180043008  call    cs:__imp_WindowsGetStringRawBuffer
0x18004300e  mov     r8, rax
0x180043011  lea     r9, [rsp+110h+var_C8]
0x180043016  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18004301b  mov     edi, eax
0x18004301d  test    eax, eax
0x18004301f  js      short loc_180043075
0x180043021  mov     rcx, [rbp+3Fh+var_B8]
0x180043025  mov     edi, ebx
0x180043027  mov     rbx, [rsp+110h+var_C8]
0x18004302c  cmp     rcx, [rbp+3Fh+var_A8]
0x180043030  jnz     short loc_18004304A
0x180043032  lea     rdx, [rcx+1]
0x180043036  lea     rcx, [rsp+110h+var_C0]
0x18004303b  call    ?_EnsureCapacity@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAJ_K0@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180043040  mov     edi, eax
0x180043042  test    eax, eax
0x180043044  js      short loc_180043066
0x180043046  mov     rcx, [rbp+3Fh+var_B8]
0x18004304a  mov     rdx, [rsp+110h+var_C0]
0x18004304f  inc     rcx
0x180043052  add     rdx, 0FFFFFFFFFFFFFFF8h
0x180043056  mov     [rbp+3Fh+var_B8], rcx
0x18004305a  lea     rdx, [rdx+rcx*8]
0x18004305e  test    rdx, rdx
0x180043061  jz      short loc_180043066
0x180043063  mov     [rdx], rbx
0x180043066  xor     eax, eax
0x180043068  test    edi, edi
0x18004306a  cmovns  rbx, rax
0x18004306e  mov     [rsp+110h+var_C8], rbx
0x180043073  xor     ebx, ebx
0x180043075  lea     rcx, [rsp+110h+var_C8]
0x18004307a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18004307f  lea     rcx, [rsp+110h+string]; this
0x180043084  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180043089  lea     rcx, [rsp+110h+var_D0]
0x18004308e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180043093  inc     esi
0x180043095  test    edi, edi
0x180043097  jns     loc_180042F9A
0x18004309d  jmp     loc_18004327D
0x1800430a2  mov     rcx, [rbp+3Fh+var_B8]
0x1800430a6  mov     edi, ebx
0x1800430a8  cmp     rcx, 1
0x1800430ac  jbe     short loc_18004310F
0x1800430ae  shr     rcx, 1; unsigned __int64
0x1800430b1  lea     r8, [rsp+110h+string]; unsigned __int64 *
0x1800430b6  mov     edx, 8; unsigned __int64
0x1800430bb  mov     [rbp+3Fh+pv], rbx
0x1800430bf  mov     [rsp+110h+string], rbx
0x1800430c4  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800430c9  mov     edi, eax
0x1800430cb  test    eax, eax
0x1800430cd  js      short loc_1800430E7
0x1800430cf  mov     r9, [rsp+110h+string]; unsigned __int64
0x1800430d4  lea     rax, [rbp+3Fh+pv]
0x1800430d8  xor     r8d, r8d; void *
0x1800430db  mov     [rsp+110h+var_F0], rax; void **
0x1800430e0  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800430e5  mov     edi, eax
0x1800430e7  test    edi, edi
0x1800430e9  js      short loc_18004310F
0x1800430eb  mov     r9, [rbp+3Fh+var_B8]
0x1800430ef  lea     rdx, [rsp+110h+var_E0]
0x1800430f4  xor     r8d, r8d
0x1800430f7  lea     rcx, [rsp+110h+var_C0]
0x1800430fc  call    ??$_MergeSort@VPWSTRCompare@CExtensionList@@@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAXAEBVPWSTRCompare@CExtensionList@@_K1@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_MergeSort<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,unsigned __int64,unsigned __int64)
0x180043101  mov     rcx, [rbp+3Fh+pv]; pv
0x180043105  call    cs:__imp_CoTaskMemFree
0x18004310b  mov     [rbp+3Fh+pv], rbx
0x18004310f  mov     rsi, rbx
0x180043112  jmp     loc_180043275
0x180043117  cmp     rsi, [r12+8]
0x18004311c  jnb     loc_18004327D
0x180043122  mov     rax, [r12]
0x180043126  lea     rdx, [rsp+110h+string]
0x18004312b  mov     [rsp+110h+string], rbx
0x180043130  lea     rcx, [rax+rsi*8]
0x180043134  call    ??$As@UIObjectWithPropertyStore@@@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIObjectWithPropertyStore@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IExtensionListItem>::As<IObjectWithPropertyStore>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IObjectWithPropertyStore>>)
0x180043139  mov     edi, eax
0x18004313b  test    eax, eax
0x18004313d  js      loc_180043268
0x180043143  mov     rdi, [rsp+110h+string]
0x180043148  lea     rcx, [rsp+110h+var_D0]
0x18004314d  mov     [rsp+110h+var_D0], rbx
0x180043152  mov     rax, [rdi]
0x180043155  mov     rbx, [rax+18h]
0x180043159  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18004315e  lea     r8, [rsp+110h+var_D0]
0x180043163  mov     rcx, rdi
0x180043166  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18004316d  mov     rax, rbx
0x180043170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043175  xor     ebx, ebx
0x180043177  mov     edi, eax
0x180043179  test    eax, eax
0x18004317b  js      loc_18004325E
0x180043181  test    r13, r13
0x180043184  jz      short loc_1800431CC
0x180043186  mov     rax, [rsp+110h+var_D0]
0x18004318b  lea     rdx, [rbp+3Fh+arg_30]; int *
0x18004318f  xorps   xmm0, xmm0
0x180043192  mov     [rbp+3Fh+var_90], rax
0x180043196  lea     rcx, [rbp+3Fh+var_90]; struct CONDITIONEVALINFO *
0x18004319a  movdqa  [rbp+3Fh+var_60], xmm0
0x18004319f  movdqa  [rbp+3Fh+var_70], xmm0
0x1800431a4  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x1800431a7  mov     [rbp+3Fh+var_80], rbx
0x1800431ab  mov     [rbp+3Fh+var_50], rbx
0x1800431af  mov     [rbp+3Fh+var_88], r13
0x1800431b3  mov     [rbp+3Fh+var_78], rbx
0x1800431b7  call    ?GrepDoesItemMatchCondition@@YAJPEBUCONDITIONEVALINFO@@PEAHPEAUCONDITIONEVALPROPS@@@Z; GrepDoesItemMatchCondition(CONDITIONEVALINFO const *,int *,CONDITIONEVALPROPS *)
0x1800431bc  mov     edx, dword ptr [rbp+3Fh+arg_30]
0x1800431bf  test    eax, eax
0x1800431c1  cmovs   edx, ebx
0x1800431c4  test    edx, edx
0x1800431c6  jz      loc_18004325E
0x1800431cc  mov     rcx, [r12]
0x1800431d0  lea     rdx, [rbp+3Fh+arg_30]; struct Windows::Internal::String *
0x1800431d4  mov     [rbp+3Fh+arg_30], rbx
0x1800431d8  mov     rcx, [rcx+rsi*8]; struct IExtensionListItem *
0x1800431dc  call    ?_GetExtensionIdFromExtensionItem@@YAJPEAUIExtensionListItem@@PEAVString@Internal@Windows@@@Z; _GetExtensionIdFromExtensionItem(IExtensionListItem *,Windows::Internal::String *)
0x1800431e1  mov     edi, eax
0x1800431e3  test    eax, eax
0x1800431e5  js      short loc_180043255
0x1800431e7  mov     rcx, [rbp+3Fh+arg_30]; string
0x1800431eb  xor     edx, edx; length
0x1800431ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800431f3  lea     r9, [rbp+3Fh+var_A0]
0x1800431f7  mov     [rsp+110h+var_C8], rax
0x1800431fc  lea     r8, [rsp+110h+var_C8]
0x180043201  lea     rcx, [rsp+110h+var_C0]
0x180043206  call    ??$BinarySearchEx@VPWSTRCompare@CExtensionList@@@?$CTSimpleFixedArray@PEAGV?$CSimpleArrayStandardCompareHelper@PEAG@@@@QEBAJAEBVPWSTRCompare@CExtensionList@@AEBQEAGPEA_K@Z; CTSimpleFixedArray<ushort *,CSimpleArrayStandardCompareHelper<ushort *>>::BinarySearchEx<CExtensionList::PWSTRCompare>(CExtensionList::PWSTRCompare const &,ushort * const &,unsigned __int64 *)
0x18004320b  test    eax, eax
0x18004320d  jns     short loc_180043255
0x18004320f  mov     rdx, [r14+28h]
0x180043213  xor     edi, edi
0x180043215  mov     r15, [r12]
0x180043219  cmp     rdx, [r14+38h]
0x18004321d  jnz     short loc_180043231
0x18004321f  inc     rdx
0x180043222  lea     rcx, [r14+20h]
0x180043226  call    ?_EnsureCapacity@?$CTSimpleArray@PEAG$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAG@@V?$CSimpleArrayStandardCompareHelper@PEAG@@V?$CSimpleArrayStandardMergeHelper@PEAG@@@@QEAAJ_K0@Z; CTSimpleArray<ushort *,4294967294,CTPolicyCoTaskMem<ushort *>,CSimpleArrayStandardCompareHelper<ushort *>,CSimpleArrayStandardMergeHelper<ushort *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18004322b  mov     edi, eax
0x18004322d  test    eax, eax
0x18004322f  js      short loc_180043255
0x180043231  inc     qword ptr [r14+28h]
0x180043235  mov     rcx, [r14+28h]
0x180043239  mov     rax, [r14+20h]
0x18004323d  dec     rcx
0x180043240  lea     rcx, [rax+rcx*8]
0x180043244  test    rcx, rcx
0x180043247  jz      short loc_180043255
0x180043249  mov     rax, [r15+rsi*8]
0x18004324d  mov     [rcx], rax
0x180043250  call    ?InternalAddRef@?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IExtensionListItem>::InternalAddRef(void)
0x180043255  lea     rcx, [rbp+3Fh+arg_30]; this
0x180043259  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004325e  lea     rcx, [rsp+110h+var_D0]
0x180043263  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180043268  lea     rcx, [rsp+110h+string]
0x18004326d  call    ?InternalRelease@?$ComPtr@UIExtensionRegistration@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IExtensionRegistration>::InternalRelease(void)
0x180043272  inc     rsi
0x180043275  test    edi, edi
0x180043277  jns     loc_180043117
0x18004327d  xor     r15d, r15d
0x180043280  cmp     [rbp+3Fh+var_B8], r15
0x180043284  jbe     short loc_18004329E
0x180043286  mov     rcx, [rsp+110h+var_C0]
0x18004328b  mov     rcx, [rcx+rbx*8]; pv
0x18004328f  call    cs:__imp_CoTaskMemFree
0x180043295  inc     rbx
0x180043298  cmp     rbx, [rbp+3Fh+var_B8]
0x18004329c  jb      short loc_180043286
0x18004329e  test    edi, edi
0x1800432a0  js      loc_18004337B
0x1800432a6  mov     eax, [rbp+3Fh+arg_20]
0x1800432a9  test    eax, eax
0x1800432ab  jz      short loc_180043322
0x1800432ad  mov     rcx, [rbp+3Fh+arg_18]
0x1800432b1  mov     edi, r15d
0x1800432b4  mov     [rbp+3Fh+var_A0], rcx
0x1800432b8  mov     rcx, [r14+28h]
0x1800432bc  mov     [rbp+3Fh+var_98], eax
0x1800432bf  cmp     rcx, 1
0x1800432c3  jbe     short loc_18004331E
0x1800432c5  lea     rsi, [r14+30h]
0x1800432c9  shr     rcx, 1; unsigned __int64
0x1800432cc  lea     r8, [rbp+3Fh+arg_30]; unsigned __int64 *
0x1800432d0  mov     [rsi], r15
0x1800432d3  mov     edx, 8; unsigned __int64
0x1800432d8  mov     [rbp+3Fh+arg_30], r15
0x1800432dc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800432e1  mov     edi, eax
0x1800432e3  test    eax, eax
0x1800432e5  js      short loc_1800432FA
0x1800432e7  mov     r9, [rbp+3Fh+arg_30]; unsigned __int64
0x1800432eb  xor     r8d, r8d; void *
0x1800432ee  mov     [rsp+110h+var_F0], rsi; void **
0x1800432f3  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800432f8  mov     edi, eax
0x1800432fa  test    edi, edi
0x1800432fc  js      short loc_18004337B
0x1800432fe  mov     r9, [r14+28h]
0x180043302  lea     rdx, [rbp+3Fh+var_A0]
0x180043306  xor     r8d, r8d
0x180043309  lea     rcx, [r14+20h]
0x18004330d  call    ??$_MergeSort@VExtensionCompare@CExtensionList@@@?$CTSimpleArray@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIExtensionListItem@@@WRL@Microsoft@@@@@@QEAAXAEBVExtensionCompare@CExtensionList@@_K1@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IExtensionListItem>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IExtensionListItem>>>::_MergeSort<CExtensionList::ExtensionCompare>(CExtensionList::ExtensionCompare const &,unsigned __int64,unsigned __int64)
0x180043312  mov     rcx, [rsi]; pv
0x180043315  call    cs:__imp_CoTaskMemFree
0x18004331b  mov     [rsi], r15
0x18004331e  test    edi, edi
0x180043320  js      short loc_18004337B
0x180043322  mov     esi, [rbp+3Fh+arg_28]
0x180043325  mov     rax, [r14+28h]
0x180043329  cmp     rax, rsi
0x18004332c  jbe     short loc_18004337B
0x18004332e  lea     rbx, [rax-1]
0x180043332  cmp     rbx, rax
0x180043335  jnb     short loc_180043376
0x180043337  mov     rax, [r14+20h]
0x18004333b  lea     rcx, [rax+rbx*8]
0x18004333f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180043344  mov     r8, [r14+28h]
0x180043348  lea     rax, [r8-1]
0x18004334c  cmp     rbx, rax
0x18004334f  jz      short loc_18004336D
0x180043351  mov     rax, [r14+20h]
0x180043355  sub     r8, rbx
0x180043358  lea     rcx, [rax+rbx*8]; void *
0x18004335c  lea     rdx, [rcx+8]; Src
0x180043360  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x180043368  call    memmove_0
0x18004336d  dec     qword ptr [r14+28h]
0x180043371  mov     edi, r15d
0x180043374  jmp     short loc_180043325
0x180043376  mov     edi, 80028CA1h
0x18004337b  mov     rcx, [rsp+110h+var_C0]; pv
  ... truncated ...
```
