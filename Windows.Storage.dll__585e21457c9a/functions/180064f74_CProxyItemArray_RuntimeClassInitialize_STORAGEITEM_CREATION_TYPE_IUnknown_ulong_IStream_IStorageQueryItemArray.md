# CProxyItemArray::RuntimeClassInitialize(STORAGEITEM_CREATION_TYPE,IUnknown *,ulong,IStream *,IStorageQueryItemArray *,Windows::Foundation::Collections::IMap<HSTRING__ *,IWeakReference *> *)

- ea: `0x180064f74`
- end: `0x180065631`
- name: `?RuntimeClassInitialize@CProxyItemArray@@QEAAJW4STORAGEITEM_CREATION_TYPE@@PEAUIUnknown@@KPEAUIStream@@PEAUIStorageQueryItemArray@@PEAU?$IMap@PEAUHSTRING__@@PEAUIWeakReference@@@Collections@Foundation@Windows@@@Z`
- size: `1725`
- prototype: `__int64 __fastcall(int, int, int, int, IStream *pstm, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033474`

## callees

- `0x18000d354`
- `0x18000d6cc`
- `0x180011270`
- `0x180025a28`
- `0x180034e98`
- `0x1800355e4`
- `0x18006485c`
- `0x180064f74`
- `0x180065638`
- `0x18007182c`
- `0x180077530`
- `0x180195a1c`
- `0x18025ac5c`
- `0x18026cf28`
- `0x18026cfc0`
- `0x18035cff8`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x18065a010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180064fdc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180064ff5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006501f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180065035`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006504b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180065061`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180065085`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800650e7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006540a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180064fdc`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180064ff5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006501f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180065035`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006504b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180065061`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180065085`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800650e7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006540a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180065280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800652f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180065280`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800652f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065188`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CProxyItemArray::RuntimeClassInitialize(
        __int64 a1,
        unsigned int a2,
        void (__fastcall ***a3)(_QWORD, GUID *, __int64 *),
        int a4,
        IStream *pstm,
        __int64 a6,
        __int64 a7)
{
  HRESULT HSTRINGWithSpecifiedDefault; // edi
  __int64 v10; // rsi
  _QWORD *v12; // r15
  unsigned int v13; // r12d
  HSTRING v14; // rbx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  struct IPropertyStore *v17; // rcx
  __int64 (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v19; // rcx
  struct IPropertyStore *v20; // rcx
  __int64 v21; // r13
  int v22; // edi
  int v23; // r12d
  int v24; // r13d
  CPrefetchedProperties *v25; // rax
  CPrefetchedProperties *v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v31; // rcx
  void (__fastcall *v32)(_QWORD, GUID *, __int64 *); // rbx
  unsigned __int64 v33; // rdx
  int v34; // r8d
  __int64 v35; // rdx
  int v36; // [rsp+48h] [rbp-C0h]
  bool v37; // [rsp+58h] [rbp-B0h]
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  int v39; // [rsp+68h] [rbp-A0h]
  unsigned int v40; // [rsp+6Ch] [rbp-9Ch]
  __int64 v41; // [rsp+70h] [rbp-98h]
  __int64 v42; // [rsp+78h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-88h]
  __int64 v44; // [rsp+88h] [rbp-80h]
  struct IPropertyStore *v45; // [rsp+90h] [rbp-78h]
  unsigned int v46; // [rsp+98h] [rbp-70h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+A0h] [rbp-68h] BYREF
  struct IPropertyStore *v48; // [rsp+A8h] [rbp-60h] BYREF
  int pv; // [rsp+B0h] [rbp-58h] BYREF
  unsigned int pv_4; // [rsp+B4h] [rbp-54h] BYREF
  int v51; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-40h] BYREF
  struct IPropertyStore *v54; // [rsp+D0h] [rbp-38h] BYREF
  int v55; // [rsp+D8h] [rbp-30h] BYREF
  int v56; // [rsp+DCh] [rbp-2Ch] BYREF
  int v57; // [rsp+E0h] [rbp-28h] BYREF
  int v58; // [rsp+E4h] [rbp-24h] BYREF
  int v59; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v60; // [rsp+F0h] [rbp-18h] BYREF

  LODWORD(v41) = a4;
  v40 = a2;
  v43 = a6;
  v44 = a7;
  pv_4 = 0;
  HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &pv_4, 4u);
  v59 = 0;
  if ( HSTRINGWithSpecifiedDefault >= 0 )
    HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v59, 4u);
  v58 = 5;
  v51 = 0;
  v57 = 4;
  v56 = 100;
  if ( HSTRINGWithSpecifiedDefault >= 0 )
  {
    HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v58, 4u);
    if ( HSTRINGWithSpecifiedDefault >= 0 )
    {
      HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v51, 4u);
      if ( HSTRINGWithSpecifiedDefault >= 0 )
      {
        HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v57, 4u);
        if ( HSTRINGWithSpecifiedDefault >= 0 )
          HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v56, 4u);
      }
    }
  }
  v46 = 0;
  v10 = 0;
  v42 = 0;
  if ( HSTRINGWithSpecifiedDefault >= 0 )
  {
    HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &v46, 4u);
    if ( HSTRINGWithSpecifiedDefault >= 0 )
    {
      if ( !v46 )
      {
LABEL_14:
        v60 = 0;
        if ( a3 )
        {
          v32 = **a3;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
          v32(a3, &GUID_60e1feec_e458_4a19_8022_fb2471e3ec0b, &v60);
        }
        v55 = 0;
        v37 = !a7 || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)a7 + 56LL))(a7, &v55) >= 0 && !v55;
        v12 = (_QWORD *)(a1 + 48);
        CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(
          a1 + 48,
          pv_4);
        v13 = 0;
        v39 = 0;
        do
        {
          if ( v13 >= pv_4 )
            break;
          v47 = 0;
          v54 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
          HSTRINGWithSpecifiedDefault = PropertyStore_UnmarshalAdditionalData(pstm, &v54);
          if ( HSTRINGWithSpecifiedDefault >= 0 )
          {
            string = 0;
            HSTRINGWithSpecifiedDefault = IPropertyStore_GetHSTRINGWithSpecifiedDefault(
                                            v54,
                                            PKEY_FileAPI_FolderRelativeId,
                                            0,
                                            &string);
            v14 = string;
            if ( HSTRINGWithSpecifiedDefault >= 0 )
            {
              v21 = v44;
              if ( !v44
                || v37
                || WindowsIsStringEmpty(string)
                || (HSTRINGWithSpecifiedDefault = FindInWeakStringMap<Windows::Storage::IStorageItem>(v14, v21, &v47),
                    HSTRINGWithSpecifiedDefault >= 0) )
              {
                if ( !v47 )
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  HSTRINGWithSpecifiedDefault = StorageItem_CreateProxy_Private(v40, v54, v43, v13);
                  if ( HSTRINGWithSpecifiedDefault >= 0 )
                  {
                    if ( v40 != 1 )
                      goto LABEL_96;
                    v48 = 0;
                    HSTRINGWithSpecifiedDefault = Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<IStorageItemInformationInternal>(
                                                    &v47,
                                                    &v48);
                    if ( HSTRINGWithSpecifiedDefault >= 0 )
                      HSTRINGWithSpecifiedDefault = ((__int64 (__fastcall *)(struct IPropertyStore *, HSTRING, _QWORD, __int64))v48->lpVtbl->GetCount)(
                                                      v48,
                                                      v14,
                                                      v13 + (unsigned int)v41,
                                                      v60);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
                    if ( HSTRINGWithSpecifiedDefault >= 0 )
                    {
LABEL_96:
                      if ( v21 && !WindowsIsStringEmpty(v14) )
                        HSTRINGWithSpecifiedDefault = InsertInWeakStringMap(v14, v47, v21);
                    }
                  }
                }
              }
            }
            if ( v14 )
              WindowsDeleteString(v14);
            if ( HSTRINGWithSpecifiedDefault >= 0 )
            {
              HSTRINGWithSpecifiedDefault = 0;
              v15 = v12[1];
              if ( v15 != v12[3]
                || (HSTRINGWithSpecifiedDefault = CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(
                                                    v12,
                                                    v15 + 1),
                    HSTRINGWithSpecifiedDefault >= 0) )
              {
                v16 = (_QWORD *)(*v12 + 8 * v12[1]++);
                if ( v16 )
                {
                  *v16 = v47;
                  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v16);
                }
              }
              if ( HSTRINGWithSpecifiedDefault >= 0 )
              {
                v48 = 0;
                if ( !v46
                  || (pv = 0, HSTRINGWithSpecifiedDefault = IStream_Read(pstm, &pv, 4u),
                              HSTRINGWithSpecifiedDefault >= 0)
                  && (!pv
                   || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48),
                       HSTRINGWithSpecifiedDefault = PropertyStore_UnmarshalAdditionalData(pstm, &v48),
                       HSTRINGWithSpecifiedDefault >= 0)) )
                {
                  if ( v51 || v48 )
                  {
                    v53 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
                    v22 = v56;
                    v23 = v57;
                    v24 = v51;
                    pv = v58;
                    v45 = v48;
                    LODWORD(v52) = v59;
                    v53 = 0;
                    v25 = (CPrefetchedProperties *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
                    string = (HSTRING)v25;
                    if ( v25 )
                    {
                      v26 = CPrefetchedProperties::CPrefetchedProperties(v25);
                      string = 0;
                      v36 = v23;
                      v13 = v39;
                      HSTRINGWithSpecifiedDefault = CPrefetchedProperties::RuntimeClassInitialize(
                                                      (_DWORD)v26,
                                                      v43,
                                                      v39,
                                                      v10,
                                                      v52,
                                                      (__int64)v45,
                                                      pv,
                                                      v24,
                                                      v36,
                                                      v22);
                      if ( HSTRINGWithSpecifiedDefault >= 0 )
                      {
                        HSTRINGWithSpecifiedDefault = (**(__int64 (__fastcall ***)(CPrefetchedProperties *, GUID *, __int64 *))v26)(
                                                        v26,
                                                        &GUID_2b5b8d70_cd27_46d0_a04b_bf8c7fc9b5c6,
                                                        &v53);
                        (*(void (__fastcall **)(CPrefetchedProperties *))(*(_QWORD *)v26 + 16LL))(v26);
                        Microsoft::WRL::Details::MakeAllocator<CStorageItemThumbnailProxy>::~MakeAllocator<CStorageItemThumbnailProxy>(&string);
                        if ( HSTRINGWithSpecifiedDefault >= 0 )
                        {
                          v52 = 0;
                          v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
                          v30 = **v47;
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
                          HSTRINGWithSpecifiedDefault = v30(v29, &GUID_c5ab533a_1b75_4bb7_9ae6_3cee5057fac7, &v52);
                          if ( HSTRINGWithSpecifiedDefault >= 0 )
                            HSTRINGWithSpecifiedDefault = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 24LL))(
                                                            v52,
                                                            v53);
                          v31 = v52;
                          if ( v52 )
                          {
                            v52 = 0;
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                          }
                        }
                      }
                      else if ( v26 )
                      {
                        (*(void (__fastcall **)(CPrefetchedProperties *))(*(_QWORD *)v26 + 16LL))(v26);
                      }
                    }
                    else
                    {
                      Microsoft::WRL::Details::MakeAllocator<CStorageItemThumbnailProxy>::~MakeAllocator<CStorageItemThumbnailProxy>(&string);
                      HSTRINGWithSpecifiedDefault = -2147024882;
                      v13 = v39;
                    }
                    v27 = v53;
                    if ( v53 )
                    {
                      v53 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
                    }
                  }
                }
                v20 = v48;
                if ( v48 )
                {
                  v48 = 0;
                  ((void (__fastcall *)(struct IPropertyStore *))v20->lpVtbl->Release)(v20);
                }
              }
            }
          }
          v17 = v54;
          if ( v54 )
          {
            v54 = 0;
            ((void (__fastcall *)(struct IPropertyStore *))v17->lpVtbl->Release)(v17);
          }
          v18 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
          if ( v47 )
          {
            v47 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v18)[2])(v18);
          }
          v39 = ++v13;
        }
        while ( HSTRINGWithSpecifiedDefault >= 0 );
        v19 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_10;
      }
      v28 = CreateRefCountedObj<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>,>(&string);
      Microsoft::WRL::ComPtr<CRefCountedObject<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>>>::operator=(
        &v42,
        v28);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      v10 = v42;
      if ( !v42 )
      {
        HSTRINGWithSpecifiedDefault = -2147024882;
        goto LABEL_10;
      }
      HSTRINGWithSpecifiedDefault = CTSimpleArray<_tagpropertykey,4294967294,CTPolicyCoTaskMem<_tagpropertykey>,CSimpleArrayStandardCompareHelper<_tagpropertykey>,CSimpleArrayStandardMergeHelper<_tagpropertykey>>::_EnsureCapacity(
                                      v42 + 8,
                                      v46);
      if ( HSTRINGWithSpecifiedDefault >= 0 )
      {
        while ( 1 )
        {
          v33 = *(_QWORD *)(v10 + 16);
          if ( v33 >= v46 )
          {
            HSTRINGWithSpecifiedDefault = IStream_Read(pstm, *(void **)(v10 + 8), 20 * v46);
            if ( HSTRINGWithSpecifiedDefault >= 0 )
              goto LABEL_14;
            break;
          }
          v34 = 0;
          string = 0;
          HSTRINGWithSpecifiedDefault = 0;
          if ( v33 != *(_QWORD *)(v10 + 32) )
            goto LABEL_89;
          HSTRINGWithSpecifiedDefault = CTSimpleArray<_tagpropertykey,4294967294,CTPolicyCoTaskMem<_tagpropertykey>,CSimpleArrayStandardCompareHelper<_tagpropertykey>,CSimpleArrayStandardMergeHelper<_tagpropertykey>>::_EnsureCapacity(
                                          v10 + 8,
                                          v33 + 1);
          if ( HSTRINGWithSpecifiedDefault < 0 )
          {
LABEL_91:
            if ( HSTRINGWithSpecifiedDefault < 0 )
              break;
          }
          else
          {
            v34 = (int)string;
LABEL_89:
            ++*(_QWORD *)(v10 + 16);
            v35 = *(_QWORD *)(v10 + 8) + 4 * (5LL * *(_QWORD *)(v10 + 16) - 5);
            if ( v35 )
            {
              *(_OWORD *)v35 = 0;
              *(_DWORD *)(v35 + 16) = v34;
              goto LABEL_91;
            }
          }
        }
      }
    }
  }
LABEL_10:
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)HSTRINGWithSpecifiedDefault;
}

```

## disassembly

```asm
0x180064f74  mov     rax, rsp
0x180064f77  mov     [rax+10h], rbx
0x180064f7b  push    rbp
0x180064f7c  push    rsi
0x180064f7d  push    rdi
0x180064f7e  push    r12
0x180064f80  push    r13
0x180064f82  push    r14
0x180064f84  push    r15
0x180064f86  lea     rbp, [rax-48h]
0x180064f8a  sub     rsp, 110h
0x180064f91  movaps  xmmword ptr [rax-48h], xmm6
0x180064f95  mov     rax, cs:__security_cookie
0x180064f9c  xor     rax, rsp
0x180064f9f  mov     [rbp+40h+var_50], rax
0x180064fa3  mov     dword ptr [rsp+140h+var_D8], r9d
0x180064fa8  mov     r15, r8
0x180064fab  mov     dword ptr [rsp+140h+var_E0+4], edx
0x180064faf  mov     r13, rcx
0x180064fb2  mov     r14, [rbp+40h+pstm]
0x180064fb6  mov     rax, [rbp+40h+arg_28]
0x180064fba  mov     [rsp+140h+var_C8], rax
0x180064fbf  mov     r12, [rbp+40h+arg_30]
0x180064fc6  mov     [rbp+40h+var_C0], r12
0x180064fca  xor     ebx, ebx
0x180064fcc  mov     dword ptr [rbp+40h+pv+4], ebx
0x180064fcf  lea     esi, [rbx+4]
0x180064fd2  mov     r8d, esi; cb
0x180064fd5  lea     rdx, [rbp+40h+pv+4]; pv
0x180064fd9  mov     rcx, r14; pstm
0x180064fdc  call    cs:__imp_IStream_Read
0x180064fe2  mov     edi, eax
0x180064fe4  mov     [rbp+40h+var_60], ebx
0x180064fe7  test    eax, eax
0x180064fe9  js      short loc_180064FFD
0x180064feb  mov     r8d, esi; cb
0x180064fee  lea     rdx, [rbp+40h+var_60]; pv
0x180064ff2  mov     rcx, r14; pstm
0x180064ff5  call    cs:__imp_IStream_Read
0x180064ffb  mov     edi, eax
0x180064ffd  mov     [rbp+40h+var_64], 5
0x180065004  mov     [rbp+40h+var_90], ebx
0x180065007  mov     [rbp+40h+var_68], esi
0x18006500a  mov     [rbp+40h+var_6C], 64h ; 'd'
0x180065011  test    edi, edi
0x180065013  js      short loc_180065069
0x180065015  mov     r8d, esi; cb
0x180065018  lea     rdx, [rbp+40h+var_64]; pv
0x18006501c  mov     rcx, r14; pstm
0x18006501f  call    cs:__imp_IStream_Read
0x180065025  mov     edi, eax
0x180065027  test    eax, eax
0x180065029  js      short loc_180065069
0x18006502b  mov     r8d, esi; cb
0x18006502e  lea     rdx, [rbp+40h+var_90]; pv
0x180065032  mov     rcx, r14; pstm
0x180065035  call    cs:__imp_IStream_Read
0x18006503b  mov     edi, eax
0x18006503d  test    eax, eax
0x18006503f  js      short loc_180065069
0x180065041  mov     r8d, esi; cb
0x180065044  lea     rdx, [rbp+40h+var_68]; pv
0x180065048  mov     rcx, r14; pstm
0x18006504b  call    cs:__imp_IStream_Read
0x180065051  mov     edi, eax
0x180065053  test    eax, eax
0x180065055  js      short loc_180065069
0x180065057  mov     r8d, esi; cb
0x18006505a  lea     rdx, [rbp+40h+var_6C]; pv
0x18006505e  mov     rcx, r14; pstm
0x180065061  call    cs:__imp_IStream_Read
0x180065067  mov     edi, eax
0x180065069  mov     [rbp+40h+var_B0], ebx
0x18006506c  mov     rsi, rbx
0x18006506f  mov     [rsp+140h+var_D0], rbx
0x180065074  test    edi, edi
0x180065076  js      short loc_180065095
0x180065078  mov     r8d, 4; cb
0x18006507e  lea     rdx, [rbp+40h+var_B0]; pv
0x180065082  mov     rcx, r14; pstm
0x180065085  call    cs:__imp_IStream_Read
0x18006508b  mov     edi, eax
0x18006508d  test    eax, eax
0x18006508f  jns     loc_18006545D
0x180065095  test    rsi, rsi
0x180065098  jz      short loc_1800650AA
0x18006509a  mov     rax, [rsi]
0x18006509d  mov     rcx, rsi
0x1800650a0  mov     rax, [rax+10h]
0x1800650a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650a9  nop
0x1800650aa  mov     eax, edi
0x1800650ac  mov     rcx, [rbp+40h+var_50]
0x1800650b0  xor     rcx, rsp; StackCookie
0x1800650b3  call    __security_check_cookie
0x1800650b8  lea     r11, [rsp+140h+var_30]
0x1800650c0  mov     rbx, [r11+48h]
0x1800650c4  movaps  xmm6, xmmword ptr [r11-10h]
0x1800650c9  mov     rsp, r11
0x1800650cc  pop     r15
0x1800650ce  pop     r14
0x1800650d0  pop     r13
0x1800650d2  pop     r12
0x1800650d4  pop     rdi
0x1800650d5  pop     rsi
0x1800650d6  pop     rbp
0x1800650d7  retn
0x1800650d8  lea     r8d, [rcx+rcx*4]
0x1800650dc  shl     r8d, 2; cb
0x1800650e0  mov     rdx, [rsi+8]; pv
0x1800650e4  mov     rcx, r14; pstm
0x1800650e7  call    cs:__imp_IStream_Read
0x1800650ed  mov     edi, eax
0x1800650ef  test    eax, eax
0x1800650f1  js      short loc_180065095
0x1800650f3  mov     [rbp+40h+var_58], rbx
0x1800650f7  test    r15, r15
0x1800650fa  jnz     loc_180065563
0x180065100  mov     [rbp+40h+var_70], ebx
0x180065103  test    r12, r12
0x180065106  jnz     loc_18006558F
0x18006510c  mov     byte ptr [rsp+140h+var_F0], 1
0x180065111  lea     r15, [r13+30h]
0x180065115  mov     edx, dword ptr [rbp+40h+pv+4]
0x180065118  mov     rcx, r15
0x18006511b  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@U?$IVectorView@PEAUIStorageItemInformation@BulkAccess@Storage@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVectorView<Windows::Storage::BulkAccess::IStorageItemInformation *>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180065120  mov     r12d, ebx
0x180065123  mov     dword ptr [rsp+140h+var_E0], ebx
0x180065127  cmp     r12d, dword ptr [rbp+40h+pv+4]
0x18006512b  jnb     loc_18006520F
0x180065131  mov     [rbp+40h+var_A8], rbx
0x180065135  mov     [rbp+40h+var_78], rbx
0x180065139  lea     rcx, [rbp+40h+var_78]
0x18006513d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065142  lea     rdx, [rbp+40h+var_78]; struct IPropertyStore **
0x180065146  mov     rcx, r14; pstm
0x180065149  call    ?PropertyStore_UnmarshalAdditionalData@@YAJPEAUIStream@@PEAPEAUIPropertyStore@@@Z; PropertyStore_UnmarshalAdditionalData(IStream *,IPropertyStore * *)
0x18006514e  mov     edi, eax
0x180065150  test    eax, eax
0x180065152  js      short loc_1800651CB
0x180065154  mov     [rsp+140h+string], rbx
0x180065159  lea     r9, [rsp+140h+string]
0x18006515e  xor     r8d, r8d
0x180065161  lea     rdx, PKEY_FileAPI_FolderRelativeId
0x180065168  mov     rcx, [rbp+40h+var_78]
0x18006516c  call    IPropertyStore_GetHSTRINGWithSpecifiedDefault
0x180065171  mov     edi, eax
0x180065173  mov     rbx, [rsp+140h+string]
0x180065178  test    eax, eax
0x18006517a  jns     loc_18006526D
0x180065180  test    rbx, rbx
0x180065183  jz      short loc_18006518E
0x180065185  mov     rcx, rbx; string
0x180065188  call    cs:__imp_WindowsDeleteString
0x18006518e  xor     ebx, ebx
0x180065190  test    edi, edi
0x180065192  js      short loc_1800651CB
0x180065194  mov     edi, ebx
0x180065196  mov     rdx, [r15+8]
0x18006519a  cmp     rdx, [r15+18h]
0x18006519e  jz      loc_1800655FE
0x1800651a4  inc     qword ptr [r15+8]
0x1800651a8  mov     rcx, [r15+8]
0x1800651ac  mov     rax, [r15]
0x1800651af  dec     rcx
0x1800651b2  lea     rcx, [rax+rcx*8]
0x1800651b6  test    rcx, rcx
0x1800651b9  jz      short loc_1800651C7
0x1800651bb  mov     rax, [rbp+40h+var_A8]
0x1800651bf  mov     [rcx], rax
0x1800651c2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800651c7  test    edi, edi
0x1800651c9  jns     short loc_18006522E
0x1800651cb  mov     rcx, [rbp+40h+var_78]
0x1800651cf  test    rcx, rcx
0x1800651d2  jz      short loc_1800651E5
0x1800651d4  mov     [rbp+40h+var_78], rbx
0x1800651d8  mov     rax, [rcx]
0x1800651db  mov     rax, [rax+10h]
0x1800651df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651e4  nop
0x1800651e5  mov     rcx, [rbp+40h+var_A8]
0x1800651e9  test    rcx, rcx
0x1800651ec  jz      short loc_1800651FF
0x1800651ee  mov     [rbp+40h+var_A8], rbx
0x1800651f2  mov     rax, [rcx]
0x1800651f5  mov     rax, [rax+10h]
0x1800651f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800651fe  nop
0x1800651ff  inc     r12d
0x180065202  mov     dword ptr [rsp+140h+var_E0], r12d
0x180065207  test    edi, edi
0x180065209  jns     loc_180065127
0x18006520f  mov     rcx, [rbp+40h+var_58]
0x180065213  test    rcx, rcx
0x180065216  jz      short loc_180065229
0x180065218  mov     [rbp+40h+var_58], rbx
0x18006521c  mov     rax, [rcx]
0x18006521f  mov     rax, [rax+10h]
0x180065223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065228  nop
0x180065229  jmp     loc_180065095
0x18006522e  mov     [rbp+40h+var_A0], rbx
0x180065232  cmp     [rbp+40h+var_B0], ebx
0x180065235  ja      loc_1800653FA
0x18006523b  cmp     [rbp+40h+var_90], ebx
0x18006523e  ja      loc_18006531A
0x180065244  cmp     [rbp+40h+var_A0], rbx
0x180065248  jnz     loc_18006531A
0x18006524e  mov     rcx, [rbp+40h+var_A0]
0x180065252  test    rcx, rcx
0x180065255  jz      short loc_180065268
0x180065257  mov     [rbp+40h+var_A0], rbx
0x18006525b  mov     rax, [rcx]
0x18006525e  mov     rax, [rax+10h]
0x180065262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065267  nop
0x180065268  jmp     loc_1800651CB
0x18006526d  mov     r13, [rbp+40h+var_C0]
0x180065271  test    r13, r13
0x180065274  jz      short loc_1800652A3
0x180065276  cmp     byte ptr [rsp+140h+var_F0], 0
0x18006527b  jnz     short loc_1800652A3
0x18006527d  mov     rcx, rbx; string
0x180065280  call    cs:__imp_WindowsIsStringEmpty
0x180065286  test    eax, eax
0x180065288  jnz     short loc_1800652A3
0x18006528a  lea     r8, [rbp+40h+var_A8]
0x18006528e  mov     rdx, r13
0x180065291  mov     rcx, rbx
0x180065294  call    ??$FindInWeakStringMap@UIStorageItem@Storage@Windows@@@@YAJPEAUHSTRING__@@PEAU?$IMap@PEAUHSTRING__@@PEAUIWeakReference@@@Collections@Foundation@Windows@@PEAPEAUIStorageItem@Storage@4@@Z; FindInWeakStringMap<Windows::Storage::IStorageItem>(HSTRING__ *,Windows::Foundation::Collections::IMap<HSTRING__ *,IWeakReference *> *,Windows::Storage::IStorageItem * *)
0x180065299  mov     edi, eax
0x18006529b  test    eax, eax
0x18006529d  js      loc_180065180
0x1800652a3  cmp     [rbp+40h+var_A8], 0
0x1800652a8  jnz     loc_180065180
0x1800652ae  lea     rcx, [rbp+40h+var_A8]
0x1800652b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800652b7  lea     rax, [rbp+40h+var_A8]
0x1800652bb  mov     [rsp+140h+var_118], rax
0x1800652c0  mov     r9d, r12d
0x1800652c3  mov     r8, [rsp+140h+var_C8]
0x1800652c8  mov     rdx, [rbp+40h+var_78]
0x1800652cc  mov     ecx, dword ptr [rsp+140h+var_E0+4]
0x1800652d0  call    ?StorageItem_CreateProxy_Private@@YAJW4STORAGEITEM_CREATION_TYPE@@PEAUIPropertyStore@@PEAUIStorageQueryItemArray@@IAEBU_GUID@@PEAPEAX@Z; StorageItem_CreateProxy_Private(STORAGEITEM_CREATION_TYPE,IPropertyStore *,IStorageQueryItemArray *,uint,_GUID const &,void * *)
0x1800652d5  mov     edi, eax
0x1800652d7  test    eax, eax
0x1800652d9  js      loc_180065180
0x1800652df  cmp     dword ptr [rsp+140h+var_E0+4], 1
0x1800652e4  jz      loc_1800655B9
0x1800652ea  test    r13, r13
0x1800652ed  jz      loc_180065180
0x1800652f3  mov     rcx, rbx; string
0x1800652f6  call    cs:__imp_WindowsIsStringEmpty
0x1800652fc  test    eax, eax
0x1800652fe  jnz     loc_180065180
0x180065304  mov     r8, r13
0x180065307  mov     rdx, [rbp+40h+var_A8]
0x18006530b  mov     rcx, rbx
0x18006530e  call    ?InsertInWeakStringMap@@YAJPEAUHSTRING__@@PEAUIUnknown@@PEAU?$IMap@PEAUHSTRING__@@PEAUIWeakReference@@@Collections@Foundation@Windows@@@Z; InsertInWeakStringMap(HSTRING__ *,IUnknown *,Windows::Foundation::Collections::IMap<HSTRING__ *,IWeakReference *> *)
0x180065313  mov     edi, eax
0x180065315  jmp     loc_180065180
0x18006531a  mov     [rbp+40h+var_80], rbx
0x18006531e  lea     rcx, [rbp+40h+var_80]
0x180065322  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180065327  mov     edi, [rbp+40h+var_6C]
0x18006532a  mov     r12d, [rbp+40h+var_68]
0x18006532e  mov     r13d, [rbp+40h+var_90]
0x180065332  mov     eax, [rbp+40h+var_64]
0x180065335  mov     dword ptr [rbp+40h+pv], eax
0x180065338  mov     rax, [rbp+40h+var_A0]
0x18006533c  mov     [rbp+40h+var_B8], rax
0x180065340  mov     eax, [rbp+40h+var_60]
0x180065343  mov     dword ptr [rbp+40h+var_88], eax
0x180065346  mov     [rbp+40h+var_80], rbx
0x18006534a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180065351  mov     ecx, 68h ; 'h'; unsigned __int64
0x180065356  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006535b  mov     [rsp+140h+string], rax
0x180065360  test    rax, rax
0x180065363  jz      loc_180065618
0x180065369  mov     rcx, rax; this
0x18006536c  call    ??0CPrefetchedProperties@@QEAA@XZ; CPrefetchedProperties::CPrefetchedProperties(void)
0x180065371  mov     rbx, rax
0x180065374  mov     [rsp+140h+string], 0
0x18006537d  mov     [rsp+140h+var_F8], edi
0x180065381  mov     [rsp+140h+var_100], r12d
0x180065386  mov     [rsp+140h+var_108], r13d
0x18006538b  mov     eax, dword ptr [rbp+40h+pv]
0x18006538e  mov     [rsp+140h+var_110], eax
0x180065392  mov     rax, [rbp+40h+var_B8]
0x180065396  mov     [rsp+140h+var_118], rax
0x18006539b  mov     eax, dword ptr [rbp+40h+var_88]
0x18006539e  mov     [rsp+140h+var_120], eax
0x1800653a2  mov     r9, rsi
0x1800653a5  mov     r12d, dword ptr [rsp+140h+var_E0]
0x1800653aa  mov     r8d, r12d
0x1800653ad  mov     rdx, [rsp+140h+var_C8]
0x1800653b2  mov     rcx, rbx
0x1800653b5  call    ?RuntimeClassInitialize@CPrefetchedProperties@@QEAAJPEAUIStorageQueryItemArray@@IAEAV?$CRefCountedObject@V?$CCoSimpleArray@U_tagpropertykey@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@U_tagpropertykey@@@@@@@@W4PropertyPrefetchOptions@FileProperties@Storage@Windows@@PEAUIPropertyStore@@W4ThumbnailMode@567@KW4ThumbnailOptions@567@W4DEVICE_SCALE_FACTOR@@@Z; CPrefetchedProperties::RuntimeClassInitialize(IStorageQueryItemArray *,uint,CRefCountedObject<CCoSimpleArray<_tagpropertykey,4294967294,CSimpleArrayStandardCompareHelper<_tagpropertykey>>> &,Windows::Storage::FileProperties::PropertyPrefetchOptions,IPropertyStore *,Windows::Storage::FileProperties::ThumbnailMode,ulong,Windows::Storage::FileProperties::ThumbnailOptions,DEVICE_SCALE_FACTOR)
  ... truncated ...
```
