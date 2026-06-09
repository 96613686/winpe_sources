# IndexerSemanticStore::GetItemEmbedding(_GUID,winrt::hstring)

- ea: `0x18003ba74`
- end: `0x18003bec8`
- name: `?GetItemEmbedding@IndexerSemanticStore@@QEAA?AUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@U_GUID@@Uhstring@6@@Z`
- size: `1108`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, int *, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045f80`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180007f72`
- `0x18000c478`
- `0x180013d94`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a464`
- `0x18001fd14`
- `0x1800228b0`
- `0x180028c20`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x18003ba74`
- `0x180048660`
- `0x1800486c0`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bd34`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003be05`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bd34`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003be05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bbd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bbd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bba7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bda5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bda5`

## pseudocode

```c
_QWORD *__fastcall IndexerSemanticStore::GetItemEmbedding(
        __int64 a1,
        _QWORD *a2,
        int *a3,
        volatile signed __int32 **a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  char v8; // dl
  char v9; // r8
  char v10; // r9
  char v11; // r10
  char v12; // r11
  char v13; // bl
  char v14; // di
  char v15; // si
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r14
  unsigned int v20; // edi
  _DWORD *v21; // rbx
  struct _RTL_CRITICAL_SECTION *v22; // rsi
  unsigned int v23; // r13d
  int matched; // eax
  int v25; // edi
  int v26; // eax
  __int64 v27; // rax
  __int64 *v28; // rax
  volatile signed __int32 *v29; // rcx
  __int64 v30; // rdx
  const wchar_t *v31; // r9
  __int64 v32; // rax
  size_t v33; // r8
  const wchar_t *v34; // rcx
  bool v35; // r15
  void *v36; // rbx
  int v37; // eax
  HANDLE ProcessHeap; // rax
  __int64 v39; // rax
  _QWORD *v40; // rdi
  void *v41; // rbx
  volatile signed __int32 *v42; // rbx
  int v43; // esi
  HANDLE v44; // rax
  __int64 v46; // rbx
  unsigned int *v47; // rax
  __int64 v48; // rbx
  unsigned int *v49; // rax
  int i; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v51; // [rsp+28h] [rbp-D8h] BYREF
  LPVOID v52; // [rsp+30h] [rbp-D0h] BYREF
  char v53; // [rsp+38h] [rbp-C8h]
  char v54; // [rsp+39h] [rbp-C7h]
  char v55; // [rsp+3Ah] [rbp-C6h]
  char v56; // [rsp+3Bh] [rbp-C5h]
  char v57; // [rsp+3Ch] [rbp-C4h]
  char v58; // [rsp+3Dh] [rbp-C3h]
  char v59; // [rsp+3Eh] [rbp-C2h]
  char v60; // [rsp+3Fh] [rbp-C1h]
  unsigned int v61; // [rsp+50h] [rbp-B0h]
  __int64 v62; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A0h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  __int128 v65; // [rsp+70h] [rbp-90h]
  LPVOID lpMem; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v67; // [rsp+88h] [rbp-78h]
  volatile signed __int32 **v68; // [rsp+90h] [rbp-70h]
  _BYTE v69[40]; // [rsp+98h] [rbp-68h] BYREF
  char v70[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v71[48]; // [rsp+C8h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp-8h]

  v67 = a2;
  v68 = a4;
  v61 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v70);
  v7 = (struct _RTL_CRITICAL_SECTION *)pv;
  v52 = pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v7 + 5);
  ++LODWORD(v7[6].DebugInfo);
  LODWORD(v7[6].SpinCount) = 44;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v52);
  v8 = *((_BYTE *)a3 + 8);
  v9 = *((_BYTE *)a3 + 9);
  v10 = *((_BYTE *)a3 + 10);
  v11 = *((_BYTE *)a3 + 11);
  v12 = *((_BYTE *)a3 + 12);
  v13 = *((_BYTE *)a3 + 13);
  v14 = *((_BYTE *)a3 + 14);
  v15 = *((_BYTE *)a3 + 15);
  v16 = *a3;
  v62 = 0;
  v17 = *(_QWORD *)(a1 + 32);
  pExceptionObject = 0;
  v65 = 0;
  LODWORD(v52) = v16;
  HIDWORD(v52) = a3[1];
  v53 = v8;
  v54 = v9;
  v55 = v10;
  v56 = v11;
  v57 = v12;
  v58 = v13;
  v59 = v14;
  v60 = v15;
  v18 = (*(__int64 (__fastcall **)(__int64, LPVOID *, __int64 *))(*(_QWORD *)v17 + 96LL))(v17, &v52, &v62);
  if ( v18 < 0 )
    winrt::throw_hresult((unsigned int)v18, &pExceptionObject);
  v19 = v62;
  v63 = v62;
  v20 = 2;
  v21 = pv;
  v22 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v21[18] |= 0x300u;
  if ( *((_QWORD *)v21 + 31) )
    tip2::details::shared_data<0,0,0>::complete_helper(v21 + 2, 2);
  if ( v22 )
    LeaveCriticalSection(v22);
  if ( !(unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v63) )
  {
    v48 = winrt::impl::slim_source_location::current(&v52);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v69,
      L"GetItemEmbedding: No embeddings found for the given id");
    v49 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&i, -2147024809);
    winrt::hresult_error::hresult_error(&pExceptionObject, *v49, v69, v48);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  v23 = 0;
  matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v63);
  for ( i = matched; ; matched = i )
  {
    if ( v23 == matched )
    {
      v46 = winrt::impl::slim_source_location::current(&v52);
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v69,
        L"GetItemEmbedding: No embeddings found for the given region id");
      v47 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&i, -2147024809);
      winrt::hresult_error::hresult_error(&pExceptionObject, *v47, v69, v46);
      throw (winrt::hresult_error *)&pExceptionObject;
    }
    v51 = 0;
    v25 = v20 | 8;
    v61 = v25;
    pExceptionObject = 0;
    v65 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 48LL))(v19, v23, &v51);
    if ( v26 < 0 )
      winrt::throw_hresult((unsigned int)v26, &pExceptionObject);
    v61 = v25 & 0xFFFFFFF7;
    v20 = v25 & 0xFFFFFFF3 | 4;
    v27 = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(
            &v51,
            &v52);
    v28 = (__int64 *)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
                       v27,
                       &lpMem);
    v29 = *a4;
    if ( *a4 )
    {
      v30 = *((unsigned int *)v29 + 1);
      v31 = (const wchar_t *)*((_QWORD *)v29 + 2);
    }
    else
    {
      v30 = 0;
      v31 = &pszText;
    }
    v32 = *v28;
    if ( v32 )
    {
      v33 = *(unsigned int *)(v32 + 4);
      v34 = *(const wchar_t **)(v32 + 16);
    }
    else
    {
      v33 = 0;
      v34 = &pszText;
    }
    if ( v33 == v30 )
    {
      if ( v33 )
        v35 = wmemcmp(v34, v31, v33) == 0;
      else
        v35 = 1;
    }
    else
    {
      v35 = 0;
    }
    v36 = lpMem;
    if ( lpMem )
    {
      v37 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v37 )
      {
        if ( v37 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v36);
      }
      lpMem = 0;
      v19 = v62;
    }
    if ( v52 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v52);
    if ( v35 )
      break;
    if ( v51 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
    ++v23;
  }
  v39 = v51;
  v40 = v67;
  *v67 = v51;
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, size_t, const wchar_t *))(*(_QWORD *)v39 + 8LL))(
      v39,
      *(_QWORD *)(*(_QWORD *)v39 + 8LL),
      v33,
      v31);
    v39 = v51;
  }
  if ( v39 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
  if ( v19 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v63);
  v41 = pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v41);
    CoTaskMemFree(v41);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v71);
  v42 = *a4;
  if ( *a4 )
  {
    v43 = _InterlockedDecrement(v42 + 6);
    if ( v43 )
    {
      if ( v43 < 0 )
        abort();
    }
    else
    {
      v44 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v44, 0, (LPVOID)v42);
    }
    *a4 = 0;
  }
  return v40;
}

```

## disassembly

```asm
0x18003ba74  mov     [rsp-8+arg_10], rbx
0x18003ba79  push    rbp
0x18003ba7a  push    rsi
0x18003ba7b  push    rdi
0x18003ba7c  push    r12
0x18003ba7e  push    r13
0x18003ba80  push    r14
0x18003ba82  push    r15
0x18003ba84  lea     rbp, [rsp-10h]
0x18003ba89  sub     rsp, 110h
0x18003ba90  mov     r12, r9
0x18003ba93  mov     r14, r8
0x18003ba96  mov     [rbp+40h+var_B8], rdx
0x18003ba9a  mov     r15, rcx
0x18003ba9d  mov     [rsp+140h+var_110], rdx
0x18003baa2  mov     [rbp+40h+var_B0], r9
0x18003baa6  xor     r13d, r13d
0x18003baa9  mov     [rsp+140h+var_F0], r13d
0x18003baae  lea     rcx, [rbp+40h+var_80]
0x18003bab2  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003bab7  nop
0x18003bab8  mov     rbx, [rbp+40h+pv]
0x18003babc  mov     [rsp+140h+var_110], rbx
0x18003bac1  test    rbx, rbx
0x18003bac4  jz      short loc_18003BACD
0x18003bac6  lock inc dword ptr [rbx+120h]
0x18003bacd  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003bad4  call    cs:__imp_EnterCriticalSection
0x18003bada  inc     dword ptr [rbx+0F0h]
0x18003bae0  mov     dword ptr [rbx+110h], 2Ch ; ','
0x18003baea  lea     rcx, [rsp+140h+var_110]
0x18003baef  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003baf4  mov     dl, [r14+8]
0x18003baf8  mov     r8b, [r14+9]
0x18003bafc  mov     r9b, [r14+0Ah]
0x18003bb00  mov     r10b, [r14+0Bh]
0x18003bb04  mov     r11b, [r14+0Ch]
0x18003bb08  mov     bl, [r14+0Dh]
0x18003bb0c  mov     dil, [r14+0Eh]
0x18003bb10  mov     sil, [r14+0Fh]
0x18003bb14  mov     eax, [r14]
0x18003bb17  mov     [rsp+140h+var_E8], r13
0x18003bb1c  mov     rcx, [r15+20h]
0x18003bb20  mov     [rsp+140h+pExceptionObject], r13d
0x18003bb25  xorps   xmm0, xmm0
0x18003bb28  movdqu  [rsp+140h+var_D0], xmm0
0x18003bb2e  mov     dword ptr [rsp+140h+var_110], eax
0x18003bb32  movzx   eax, word ptr [r14+4]
0x18003bb37  mov     word ptr [rsp+140h+var_110+4], ax
0x18003bb3c  movzx   eax, word ptr [r14+6]
0x18003bb41  mov     word ptr [rsp+140h+var_110+6], ax
0x18003bb46  mov     [rsp+140h+var_108], dl
0x18003bb4a  mov     [rsp+140h+var_107], r8b
0x18003bb4f  mov     [rsp+140h+var_106], r9b
0x18003bb54  mov     [rsp+140h+var_105], r10b
0x18003bb59  mov     [rsp+140h+var_104], r11b
0x18003bb5e  mov     [rsp+140h+var_103], bl
0x18003bb62  mov     [rsp+140h+var_102], dil
0x18003bb67  mov     [rsp+140h+var_101], sil
0x18003bb6c  mov     rax, [rcx]
0x18003bb6f  lea     r8, [rsp+140h+var_E8]
0x18003bb74  lea     rdx, [rsp+140h+var_110]
0x18003bb79  mov     rax, [rax+60h]
0x18003bb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb82  test    eax, eax
0x18003bb84  js      loc_18003BE6A
0x18003bb8a  mov     r14, [rsp+140h+var_E8]
0x18003bb8f  mov     [rsp+140h+var_E0], r14
0x18003bb94  mov     edi, 2
0x18003bb99  mov     rbx, [rbp+40h+pv]
0x18003bb9d  lea     rsi, [rbx+0C8h]
0x18003bba4  mov     rcx, rsi; lpCriticalSection
0x18003bba7  call    cs:__imp_EnterCriticalSection
0x18003bbad  or      dword ptr [rbx+48h], 300h
0x18003bbb4  cmp     [rbx+0F8h], r13
0x18003bbbb  jz      short loc_18003BBC8
0x18003bbbd  mov     edx, edi
0x18003bbbf  lea     rcx, [rbx+8]
0x18003bbc3  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003bbc8  test    rsi, rsi
0x18003bbcb  jz      short loc_18003BBD6
0x18003bbcd  mov     rcx, rsi; lpCriticalSection
0x18003bbd0  call    cs:__imp_LeaveCriticalSection
0x18003bbd6  lea     rcx, [rsp+140h+var_E0]
0x18003bbdb  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18003bbe0  test    eax, eax
0x18003bbe2  jz      loc_18003BE77
0x18003bbe8  xor     r13d, r13d
0x18003bbeb  lea     rcx, [rsp+140h+var_E0]
0x18003bbf0  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18003bbf5  mov     [rsp+140h+var_120], eax
0x18003bbf9  or      esi, 0FFFFFFFFh
0x18003bbfc  cmp     r13d, eax
0x18003bbff  jz      loc_18003BE19
0x18003bc05  mov     [rsp+140h+var_118], 0
0x18003bc0e  or      edi, 8
0x18003bc11  mov     [rsp+140h+var_F0], edi
0x18003bc15  mov     [rsp+140h+pExceptionObject], 0
0x18003bc1d  xorps   xmm0, xmm0
0x18003bc20  movdqu  [rsp+140h+var_D0], xmm0
0x18003bc26  mov     rax, [r14]
0x18003bc29  lea     r8, [rsp+140h+var_118]
0x18003bc2e  mov     edx, r13d
0x18003bc31  mov     rcx, r14
0x18003bc34  mov     rax, [rax+30h]
0x18003bc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc3d  test    eax, eax
0x18003bc3f  js      loc_18003BE0C
0x18003bc45  and     edi, 0FFFFFFF7h
0x18003bc48  mov     [rsp+140h+var_F0], edi
0x18003bc4c  or      edi, 4
0x18003bc4f  lea     rdx, [rsp+140h+var_110]
0x18003bc54  lea     rcx, [rsp+140h+var_118]
0x18003bc59  call    ?PackageFamilyName@?$consume_Microsoft_Windows_Management_Deployment_IPackageSetItem@UIPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageFamilyName(void)
0x18003bc5e  nop
0x18003bc5f  lea     rdx, [rbp+40h+lpMem]
0x18003bc63  mov     rcx, rax
0x18003bc66  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x18003bc6b  mov     rcx, [r12]
0x18003bc6f  test    rcx, rcx
0x18003bc72  jz      short loc_18003BC7D
0x18003bc74  mov     edx, [rcx+4]
0x18003bc77  mov     r9, [rcx+10h]
0x18003bc7b  jmp     short loc_18003BC86
0x18003bc7d  xor     edx, edx
0x18003bc7f  lea     r9, pszText
0x18003bc86  mov     rax, [rax]
0x18003bc89  test    rax, rax
0x18003bc8c  jz      short loc_18003BC98
0x18003bc8e  mov     r8d, [rax+4]
0x18003bc92  mov     rcx, [rax+10h]
0x18003bc96  jmp     short loc_18003BCA2
0x18003bc98  xor     r8d, r8d; N
0x18003bc9b  lea     rcx, pszText; S1
0x18003bca2  cmp     r8, rdx
0x18003bca5  jz      short loc_18003BCAC
0x18003bca7  xor     r15b, r15b
0x18003bcaa  jmp     short loc_18003BCC4
0x18003bcac  test    r8, r8
0x18003bcaf  jnz     short loc_18003BCB6
0x18003bcb1  mov     r15b, 1
0x18003bcb4  jmp     short loc_18003BCC4
0x18003bcb6  mov     rdx, r9; S2
0x18003bcb9  call    wmemcmp
0x18003bcbe  test    eax, eax
0x18003bcc0  setz    r15b
0x18003bcc4  mov     rbx, [rbp+40h+lpMem]
0x18003bcc8  test    rbx, rbx
0x18003bccb  jz      short loc_18003BCFF
0x18003bccd  mov     eax, esi
0x18003bccf  lock xadd [rbx+18h], eax
0x18003bcd4  sub     eax, 1
0x18003bcd7  jnz     short loc_18003BCEE
0x18003bcd9  nop
0x18003bcda  call    WINRT_IMPL_GetProcessHeap
0x18003bcdf  mov     rcx, rax; hHeap
0x18003bce2  mov     r8, rbx; lpMem
0x18003bce5  xor     edx, edx; dwFlags
0x18003bce7  call    WINRT_IMPL_HeapFree
0x18003bcec  jmp     short loc_18003BCF2
0x18003bcee  test    eax, eax
0x18003bcf0  js      short loc_18003BD34
0x18003bcf2  mov     [rbp+40h+lpMem], 0
0x18003bcfa  mov     r14, [rsp+140h+var_E8]
0x18003bcff  cmp     [rsp+140h+var_110], 0
0x18003bd05  jz      short loc_18003BD11
0x18003bd07  lea     rcx, [rsp+140h+var_110]
0x18003bd0c  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003bd11  test    r15b, r15b
0x18003bd14  jnz     short loc_18003BD3B
0x18003bd16  cmp     [rsp+140h+var_118], 0
0x18003bd1c  jz      short loc_18003BD28
0x18003bd1e  lea     rcx, [rsp+140h+var_118]
0x18003bd23  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003bd28  inc     r13d
0x18003bd2b  mov     eax, [rsp+140h+var_120]
0x18003bd2f  jmp     loc_18003BBFC
0x18003bd34  call    cs:__imp_abort
0x18003bd3b  mov     rax, [rsp+140h+var_118]
0x18003bd40  mov     rdi, [rbp+40h+var_B8]
0x18003bd44  mov     [rdi], rax
0x18003bd47  test    rax, rax
0x18003bd4a  jz      short loc_18003BD63
0x18003bd4c  mov     rcx, [rax]
0x18003bd4f  mov     rdx, [rcx+8]
0x18003bd53  mov     rcx, rax
0x18003bd56  mov     rax, rdx
0x18003bd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd5e  mov     rax, [rsp+140h+var_118]
0x18003bd63  test    rax, rax
0x18003bd66  jz      short loc_18003BD73
0x18003bd68  lea     rcx, [rsp+140h+var_118]
0x18003bd6d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003bd72  nop
0x18003bd73  test    r14, r14
0x18003bd76  jz      short loc_18003BD83
0x18003bd78  lea     rcx, [rsp+140h+var_E0]
0x18003bd7d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003bd82  nop
0x18003bd83  mov     rbx, [rbp+40h+pv]
0x18003bd87  test    rbx, rbx
0x18003bd8a  jz      short loc_18003BDAB
0x18003bd8c  mov     eax, esi
0x18003bd8e  lock xadd [rbx+120h], eax
0x18003bd96  add     eax, esi
0x18003bd98  jnz     short loc_18003BDAB
0x18003bd9a  mov     rcx, rbx
0x18003bd9d  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003bda2  mov     rcx, rbx; pv
0x18003bda5  call    cs:__imp_CoTaskMemFree
0x18003bdab  lea     rcx, [rbp+40h+var_78]; this
0x18003bdaf  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003bdb4  nop
0x18003bdb5  mov     rbx, [r12]
0x18003bdb9  test    rbx, rbx
0x18003bdbc  jz      short loc_18003BDE3
0x18003bdbe  lock xadd [rbx+18h], esi
0x18003bdc3  sub     esi, 1
0x18003bdc6  jnz     short loc_18003BE01
0x18003bdc8  nop
0x18003bdc9  call    WINRT_IMPL_GetProcessHeap
0x18003bdce  mov     rcx, rax; hHeap
0x18003bdd1  mov     r8, rbx; lpMem
0x18003bdd4  xor     edx, edx; dwFlags
0x18003bdd6  call    WINRT_IMPL_HeapFree
0x18003bddb  mov     qword ptr [r12], 0
0x18003bde3  mov     rax, rdi
0x18003bde6  mov     rbx, [rsp+140h+arg_10]
0x18003bdee  add     rsp, 110h
0x18003bdf5  pop     r15
0x18003bdf7  pop     r14
0x18003bdf9  pop     r13
0x18003bdfb  pop     r12
0x18003bdfd  pop     rdi
0x18003bdfe  pop     rsi
0x18003bdff  pop     rbp
0x18003be00  retn
0x18003be01  test    esi, esi
0x18003be03  jns     short loc_18003BDDB
0x18003be05  call    cs:__imp_abort
0x18003be0c  lea     rdx, [rsp+140h+pExceptionObject]
0x18003be11  mov     ecx, eax
0x18003be13  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003be19  lea     rcx, [rsp+140h+var_110]
0x18003be1e  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18003be23  mov     rbx, rax
0x18003be26  lea     rdx, aGetitemembeddi; "GetItemEmbedding: No embeddings found f"...
0x18003be2d  lea     rcx, [rbp+40h+var_A8]; this
0x18003be31  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003be36  mov     edx, 80070057h; int
0x18003be3b  lea     rcx, [rsp+140h+var_120]; this
0x18003be40  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003be45  mov     r9, rbx
0x18003be48  lea     r8, [rbp+40h+var_A8]
0x18003be4c  mov     edx, [rax]
0x18003be4e  lea     rcx, [rsp+140h+pExceptionObject]
0x18003be53  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003be58  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003be5f  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18003be64  call    _CxxThrowException_0
0x18003be6a  lea     rdx, [rsp+140h+pExceptionObject]
0x18003be6f  mov     ecx, eax
0x18003be71  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003be77  lea     rcx, [rsp+140h+var_110]
0x18003be7c  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18003be81  mov     rbx, rax
0x18003be84  lea     rdx, aGetitemembeddi_0; "GetItemEmbedding: No embeddings found f"...
0x18003be8b  lea     rcx, [rbp+40h+var_A8]; this
0x18003be8f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18003be94  mov     edx, 80070057h; int
0x18003be99  lea     rcx, [rsp+140h+var_120]; this
0x18003be9e  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18003bea3  mov     r9, rbx
0x18003bea6  lea     r8, [rbp+40h+var_A8]
0x18003beaa  mov     edx, [rax]
0x18003beac  lea     rcx, [rsp+140h+pExceptionObject]
0x18003beb1  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18003beb6  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18003bebd  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18003bec2  call    _CxxThrowException_0
```
