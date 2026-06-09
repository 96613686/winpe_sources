# CInterceptor_IWbemSyncProvider::Get(IWbemServices *,long,IWbemContext *,ushort const *,ushort const *,IWbemObjectSink *)

- ea: `0x140037390`
- end: `0x140037aea`
- name: `?Get@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@JPEAUIWbemContext@@PEBG2PEAUIWbemObjectSink@@@Z`
- size: `1882`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemServices *, int, struct IWbemContext *, OLECHAR *psz, const unsigned __int16 *, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140013b48`
- `0x1400234b8`
- `0x140037390`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400379e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400379e5`
- `wbemcomn!GetMemLogObject` at `0x140037a91`
- `wbemcomn!GetMemLogObject` at `0x140037a91`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037a9c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140037a9c`
- `OLEAUT32!__imp_SysAllocString` at `0x1400373d3`
- `OLEAUT32!__imp_SysAllocString` at `0x1400373d3`
- `OLEAUT32!__imp_SysFreeString` at `0x140037a59`
- `OLEAUT32!__imp_SysFreeString` at `0x140037a59`
- `OLEAUT32!__imp_VariantInit` at `0x1400379d8`
- `OLEAUT32!__imp_VariantInit` at `0x1400379d8`
- `OLEAUT32!__imp_VariantClear` at `0x140037a18`
- `OLEAUT32!__imp_VariantClear` at `0x140037a18`

## string_xrefs

- `0x1400376db`: `ProviderOperation_CreateRefresher`
- `0x1400379f6`: `HostProcessIdentifier`
- `0x140037639`: `ProviderOperation_DeleteInstanceAsync`
- `0x140037901`: `ProviderOperation_AccessCheck`
- `0x140037597`: `ProviderOperation_CreateInstanceEnumAsync`
- `0x140037711`: `ProviderOperation_CreateRefreshableObject`
- `0x1400374f5`: `ProviderOperation_DeleteClassAsync`
- `0x14003752b`: `ProviderOperation_CreateClassEnumAsync`
- `0x14003777d`: `ProviderOperation_CreateRefreshableEnum`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Get(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        __int64 a3,
        struct IWbemContext *a4,
        OLECHAR *psz,
        const unsigned __int16 *a6,
        struct IWbemObjectSink *a7)
{
  int v10; // eax
  struct IWbemObjectSink *v11; // rsi
  BSTR v12; // rax
  OLECHAR *v13; // rdi
  int v14; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v17; // [rsp+40h] [rbp-30h] BYREF
  __int64 v18; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF

  v10 = wbem_wcsicmp(psz, L"Msft_Providers");
  v11 = a7;
  if ( v10 )
  {
    v14 = -2147217392;
  }
  else
  {
    v18 = 0;
    v12 = SysAllocString(psz);
    v13 = v12;
    if ( v12 )
    {
      v14 = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, struct IWbemContext *, __int64 *, _QWORD))a2->lpVtbl->GetObjectA)(
              a2,
              v12,
              0,
              a4,
              &v18,
              0);
      if ( v14 >= 0 )
      {
        v17 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 120LL))(v18, 0, &v17);
        if ( v14 >= 0 )
        {
          a7 = 0;
          (**(void (__fastcall ***)(__int64, GUID *, struct IWbemObjectSink **))v17)(v17, &IID__IWmiObject, &a7);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_GetObjectAsync",
            0,
            8,
            1,
            21,
            (char *)this + 480);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_PutClassAsync",
            0,
            8,
            1,
            21,
            (char *)this + 488);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_DeleteClassAsync",
            0,
            8,
            1,
            21,
            (char *)this + 496);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_CreateClassEnumAsync",
            0,
            8,
            1,
            21,
            (char *)this + 504);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_PutInstanceAsync",
            0,
            8,
            1,
            21,
            (char *)this + 512);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_CreateInstanceEnumAsync",
            0,
            8,
            1,
            21,
            (char *)this + 528);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_ExecQueryAsync",
            0,
            8,
            1,
            21,
            (char *)this + 536);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_ExecNotificationQueryAsync",
            0,
            8,
            1,
            21,
            (char *)this + 544);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_DeleteInstanceAsync",
            0,
            8,
            1,
            21,
            (char *)this + 520);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_ExecMethodAsync",
            0,
            8,
            1,
            21,
            (char *)this + 552);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_QueryInstances",
            0,
            8,
            1,
            21,
            (char *)this + 592);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_CreateRefresher",
            0,
            8,
            1,
            21,
            (char *)this + 600);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_CreateRefreshableObject",
            0,
            8,
            1,
            21,
            (char *)this + 608);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_StopRefreshing",
            0,
            8,
            1,
            21,
            (char *)this + 616);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_CreateRefreshableEnum",
            0,
            8,
            1,
            21,
            (char *)this + 624);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_GetObjects",
            0,
            8,
            1,
            21,
            (char *)this + 632);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_GetProperty",
            0,
            8,
            1,
            21,
            (char *)this + 640);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_PutProperty",
            0,
            8,
            1,
            21,
            (char *)this + 648);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_ProvideEvents",
            0,
            8,
            1,
            21,
            (char *)this + 656);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_NewQuery",
            0,
            8,
            1,
            21,
            (char *)this + 664);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_CancelQuery",
            0,
            8,
            1,
            21,
            (char *)this + 672);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_AccessCheck",
            0,
            8,
            1,
            21,
            (char *)this + 680);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_SetRegistrationObject",
            0,
            8,
            1,
            21,
            (char *)this + 688);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_FindConsumer",
            0,
            8,
            1,
            21,
            (char *)this + 696);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a7->lpVtbl[10].QueryInterface)(
            a7,
            L"ProviderOperation_ValidateSubscription",
            0,
            8,
            1,
            21,
            (char *)this + 704);
          ((void (__fastcall *)(struct IWbemObjectSink *))a7->lpVtbl->Release)(a7);
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = GetCurrentProcessId();
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v17 + 40LL))(
            v17,
            L"HostProcessIdentifier",
            0,
            &pvarg,
            0);
          VariantClear(&pvarg);
          v14 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, __int64 *))v11->lpVtbl->Indicate)(
                  v11,
                  1,
                  &v17);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      SysFreeString(v13);
    }
    else
    {
      v14 = -2147217402;
    }
  }
  ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))v11->lpVtbl->SetStatus)(
    v11,
    0,
    (unsigned int)v14,
    0,
    0);
  if ( v14 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      169,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140037390  push    rbp
0x140037392  push    rbx
0x140037393  push    rsi
0x140037394  push    rdi
0x140037395  push    r12
0x140037397  push    r14
0x140037399  push    r15
0x14003739b  mov     rbp, rsp
0x14003739e  sub     rsp, 70h
0x1400373a2  mov     rbx, rdx
0x1400373a5  mov     r15, rcx
0x1400373a8  mov     rcx, [rbp+psz]; unsigned __int16 *
0x1400373ac  lea     rdx, aMsftProviders; "Msft_Providers"
0x1400373b3  mov     r14, r9
0x1400373b6  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1400373bb  mov     rsi, [rbp+arg_30]
0x1400373bf  test    eax, eax
0x1400373c1  jnz     loc_140037A68
0x1400373c7  mov     rcx, [rbp+psz]; psz
0x1400373cb  mov     [rbp+var_28], 0
0x1400373d3  call    cs:__imp_SysAllocString
0x1400373d9  mov     rdi, rax
0x1400373dc  test    rax, rax
0x1400373df  jz      loc_140037A61
0x1400373e5  mov     rcx, [rbx]
0x1400373e8  mov     r9, r14
0x1400373eb  mov     [rsp+70h+var_48], 0
0x1400373f4  xor     r8d, r8d
0x1400373f7  mov     rdx, rdi
0x1400373fa  mov     rax, [rcx+30h]
0x1400373fe  lea     rcx, [rbp+var_28]
0x140037402  mov     [rsp+70h+var_50], rcx
0x140037407  mov     rcx, rbx
0x14003740a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003740f  mov     ebx, eax
0x140037411  test    eax, eax
0x140037413  js      loc_140037A56
0x140037419  mov     rcx, [rbp+var_28]
0x14003741d  lea     r8, [rbp+var_30]
0x140037421  mov     [rbp+var_30], 0
0x140037429  xor     edx, edx
0x14003742b  mov     rax, [rcx]
0x14003742e  mov     rax, [rax+78h]
0x140037432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037437  mov     ebx, eax
0x140037439  test    eax, eax
0x14003743b  js      loc_140037A46
0x140037441  mov     rcx, [rbp+var_30]
0x140037445  lea     r8, [rbp+arg_30]
0x140037449  mov     [rbp+arg_30], 0
0x140037451  lea     rdx, IID__IWmiObject
0x140037458  mov     rax, [rcx]
0x14003745b  mov     rax, [rax]
0x14003745e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037463  mov     rcx, [rbp+arg_30]
0x140037467  lea     rdx, [r15+1E0h]
0x14003746e  mov     [rsp+70h+var_40], rdx
0x140037473  mov     r14d, 15h
0x140037479  mov     dword ptr [rsp+70h+var_48], r14d
0x14003747e  lea     rdx, aProvideroperat_12; "ProviderOperation_GetObjectAsync"
0x140037485  xor     r8d, r8d
0x140037488  mov     rax, [rcx]
0x14003748b  lea     ebx, [r14-0Dh]
0x14003748f  lea     r12d, [r14-14h]
0x140037493  mov     r9d, ebx
0x140037496  mov     dword ptr [rsp+70h+var_50], r12d
0x14003749b  mov     rax, [rax+190h]
0x1400374a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400374a7  mov     rcx, [rbp+arg_30]
0x1400374ab  lea     rdx, [r15+1E8h]
0x1400374b2  mov     [rsp+70h+var_40], rdx
0x1400374b7  mov     r9d, ebx
0x1400374ba  mov     dword ptr [rsp+70h+var_48], r14d
0x1400374bf  lea     rdx, aProvideroperat_11; "ProviderOperation_PutClassAsync"
0x1400374c6  xor     r8d, r8d
0x1400374c9  mov     dword ptr [rsp+70h+var_50], r12d
0x1400374ce  mov     rax, [rcx]
0x1400374d1  mov     rax, [rax+190h]
0x1400374d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400374dd  mov     rcx, [rbp+arg_30]
0x1400374e1  lea     rdx, [r15+1F0h]
0x1400374e8  mov     [rsp+70h+var_40], rdx
0x1400374ed  mov     r9d, ebx
0x1400374f0  mov     dword ptr [rsp+70h+var_48], r14d
0x1400374f5  lea     rdx, aProvideroperat_15; "ProviderOperation_DeleteClassAsync"
0x1400374fc  xor     r8d, r8d
0x1400374ff  mov     dword ptr [rsp+70h+var_50], r12d
0x140037504  mov     rax, [rcx]
0x140037507  mov     rax, [rax+190h]
0x14003750e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037513  mov     rcx, [rbp+arg_30]
0x140037517  lea     rdx, [r15+1F8h]
0x14003751e  mov     [rsp+70h+var_40], rdx
0x140037523  mov     r9d, ebx
0x140037526  mov     dword ptr [rsp+70h+var_48], r14d
0x14003752b  lea     rdx, aProvideroperat_17; "ProviderOperation_CreateClassEnumAsync"
0x140037532  xor     r8d, r8d
0x140037535  mov     dword ptr [rsp+70h+var_50], r12d
0x14003753a  mov     rax, [rcx]
0x14003753d  mov     rax, [rax+190h]
0x140037544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037549  mov     rcx, [rbp+arg_30]
0x14003754d  lea     rdx, [r15+200h]
0x140037554  mov     [rsp+70h+var_40], rdx
0x140037559  mov     r9d, ebx
0x14003755c  mov     dword ptr [rsp+70h+var_48], r14d
0x140037561  lea     rdx, aProvideroperat_10; "ProviderOperation_PutInstanceAsync"
0x140037568  xor     r8d, r8d
0x14003756b  mov     dword ptr [rsp+70h+var_50], r12d
0x140037570  mov     rax, [rcx]
0x140037573  mov     rax, [rax+190h]
0x14003757a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003757f  mov     rcx, [rbp+arg_30]
0x140037583  lea     rdx, [r15+210h]
0x14003758a  mov     [rsp+70h+var_40], rdx
0x14003758f  mov     r9d, ebx
0x140037592  mov     dword ptr [rsp+70h+var_48], r14d
0x140037597  lea     rdx, aProvideroperat_14; "ProviderOperation_CreateInstanceEnumAsy"...
0x14003759e  xor     r8d, r8d
0x1400375a1  mov     dword ptr [rsp+70h+var_50], r12d
0x1400375a6  mov     rax, [rcx]
0x1400375a9  mov     rax, [rax+190h]
0x1400375b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400375b5  mov     rcx, [rbp+arg_30]
0x1400375b9  lea     rdx, [r15+218h]
0x1400375c0  mov     [rsp+70h+var_40], rdx
0x1400375c5  mov     dword ptr [rsp+70h+var_48], r14d
0x1400375ca  mov     rax, [rcx]
0x1400375cd  mov     rax, [rax+190h]
0x1400375d4  lea     rdx, aProvideroperat_5; "ProviderOperation_ExecQueryAsync"
0x1400375db  mov     r9d, ebx
0x1400375de  mov     dword ptr [rsp+70h+var_50], r12d
0x1400375e3  xor     r8d, r8d
0x1400375e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400375eb  mov     rcx, [rbp+arg_30]
0x1400375ef  lea     rdx, [r15+220h]
0x1400375f6  mov     [rsp+70h+var_40], rdx
0x1400375fb  mov     r9d, ebx
0x1400375fe  mov     dword ptr [rsp+70h+var_48], r14d
0x140037603  lea     rdx, aProvideroperat_21; "ProviderOperation_ExecNotificationQuery"...
0x14003760a  xor     r8d, r8d
0x14003760d  mov     dword ptr [rsp+70h+var_50], r12d
0x140037612  mov     rax, [rcx]
0x140037615  mov     rax, [rax+190h]
0x14003761c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037621  mov     rcx, [rbp+arg_30]
0x140037625  lea     rdx, [r15+208h]
0x14003762c  mov     [rsp+70h+var_40], rdx
0x140037631  mov     r9d, ebx
0x140037634  mov     dword ptr [rsp+70h+var_48], r14d
0x140037639  lea     rdx, aProvideroperat_22; "ProviderOperation_DeleteInstanceAsync"
0x140037640  xor     r8d, r8d
0x140037643  mov     dword ptr [rsp+70h+var_50], r12d
0x140037648  mov     rax, [rcx]
0x14003764b  mov     rax, [rax+190h]
0x140037652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037657  mov     rcx, [rbp+arg_30]
0x14003765b  lea     rdx, [r15+228h]
0x140037662  mov     [rsp+70h+var_40], rdx
0x140037667  mov     r9d, ebx
0x14003766a  mov     dword ptr [rsp+70h+var_48], r14d
0x14003766f  lea     rdx, aProvideroperat_13; "ProviderOperation_ExecMethodAsync"
0x140037676  xor     r8d, r8d
0x140037679  mov     dword ptr [rsp+70h+var_50], r12d
0x14003767e  mov     rax, [rcx]
0x140037681  mov     rax, [rax+190h]
0x140037688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003768d  mov     rcx, [rbp+arg_30]
0x140037691  lea     rdx, [r15+250h]
0x140037698  mov     [rsp+70h+var_40], rdx
0x14003769d  mov     r9d, ebx
0x1400376a0  mov     dword ptr [rsp+70h+var_48], r14d
0x1400376a5  lea     rdx, aProvideroperat_8; "ProviderOperation_QueryInstances"
0x1400376ac  xor     r8d, r8d
0x1400376af  mov     dword ptr [rsp+70h+var_50], r12d
0x1400376b4  mov     rax, [rcx]
0x1400376b7  mov     rax, [rax+190h]
0x1400376be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400376c3  mov     rcx, [rbp+arg_30]
0x1400376c7  lea     rdx, [r15+258h]
0x1400376ce  mov     [rsp+70h+var_40], rdx
0x1400376d3  mov     r9d, ebx
0x1400376d6  mov     dword ptr [rsp+70h+var_48], r14d
0x1400376db  lea     rdx, aProvideroperat_1; "ProviderOperation_CreateRefresher"
0x1400376e2  xor     r8d, r8d
0x1400376e5  mov     dword ptr [rsp+70h+var_50], r12d
0x1400376ea  mov     rax, [rcx]
0x1400376ed  mov     rax, [rax+190h]
0x1400376f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400376f9  mov     rcx, [rbp+arg_30]
0x1400376fd  lea     rdx, [r15+260h]
0x140037704  mov     [rsp+70h+var_40], rdx
0x140037709  mov     r9d, ebx
0x14003770c  mov     dword ptr [rsp+70h+var_48], r14d
0x140037711  lea     rdx, aProvideroperat_23; "ProviderOperation_CreateRefreshableObje"...
0x140037718  xor     r8d, r8d
0x14003771b  mov     dword ptr [rsp+70h+var_50], r12d
0x140037720  mov     rax, [rcx]
0x140037723  mov     rax, [rax+190h]
0x14003772a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003772f  mov     rcx, [rbp+arg_30]
0x140037733  lea     rdx, [r15+268h]
0x14003773a  mov     [rsp+70h+var_40], rdx
0x14003773f  mov     r9d, ebx
0x140037742  mov     dword ptr [rsp+70h+var_48], r14d
0x140037747  lea     rdx, aProvideroperat_3; "ProviderOperation_StopRefreshing"
0x14003774e  mov     dword ptr [rsp+70h+var_50], r12d
0x140037753  xor     r8d, r8d
0x140037756  mov     rax, [rcx]
0x140037759  mov     rax, [rax+190h]
0x140037760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037765  mov     rcx, [rbp+arg_30]
0x140037769  lea     rdx, [r15+270h]
0x140037770  mov     [rsp+70h+var_40], rdx
0x140037775  mov     r9d, ebx
0x140037778  mov     dword ptr [rsp+70h+var_48], r14d
0x14003777d  lea     rdx, aProvideroperat_7; "ProviderOperation_CreateRefreshableEnum"
0x140037784  xor     r8d, r8d
0x140037787  mov     dword ptr [rsp+70h+var_50], r12d
0x14003778c  mov     rax, [rcx]
0x14003778f  mov     rax, [rax+190h]
0x140037796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003779b  mov     rcx, [rbp+arg_30]
0x14003779f  lea     rdx, [r15+278h]
0x1400377a6  mov     [rsp+70h+var_40], rdx
0x1400377ab  mov     r9d, ebx
0x1400377ae  mov     dword ptr [rsp+70h+var_48], r14d
0x1400377b3  lea     rdx, aProvideroperat_19; "ProviderOperation_GetObjects"
0x1400377ba  xor     r8d, r8d
0x1400377bd  mov     dword ptr [rsp+70h+var_50], r12d
0x1400377c2  mov     rax, [rcx]
0x1400377c5  mov     rax, [rax+190h]
0x1400377cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400377d1  mov     rcx, [rbp+arg_30]
0x1400377d5  lea     rdx, [r15+280h]
0x1400377dc  mov     [rsp+70h+var_40], rdx
0x1400377e1  mov     r9d, ebx
0x1400377e4  mov     dword ptr [rsp+70h+var_48], r14d
0x1400377e9  lea     rdx, aProvideroperat_0; "ProviderOperation_GetProperty"
0x1400377f0  xor     r8d, r8d
0x1400377f3  mov     dword ptr [rsp+70h+var_50], r12d
0x1400377f8  mov     rax, [rcx]
0x1400377fb  mov     rax, [rax+190h]
0x140037802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037807  mov     rcx, [rbp+arg_30]
0x14003780b  lea     rdx, [r15+288h]
0x140037812  mov     [rsp+70h+var_40], rdx
0x140037817  mov     r9d, ebx
0x14003781a  mov     dword ptr [rsp+70h+var_48], r14d
0x14003781f  lea     rdx, aProvideroperat_2; "ProviderOperation_PutProperty"
0x140037826  xor     r8d, r8d
0x140037829  mov     dword ptr [rsp+70h+var_50], r12d
0x14003782e  mov     rax, [rcx]
0x140037831  mov     rax, [rax+190h]
0x140037838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003783d  mov     rcx, [rbp+arg_30]
0x140037841  lea     rdx, [r15+290h]
0x140037848  mov     [rsp+70h+var_40], rdx
0x14003784d  mov     r9d, ebx
0x140037850  mov     dword ptr [rsp+70h+var_48], r14d
0x140037855  lea     rdx, aProvideroperat_18; "ProviderOperation_ProvideEvents"
0x14003785c  xor     r8d, r8d
0x14003785f  mov     dword ptr [rsp+70h+var_50], r12d
0x140037864  mov     rax, [rcx]
0x140037867  mov     rax, [rax+190h]
0x14003786e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037873  mov     rcx, [rbp+arg_30]
0x140037877  lea     rdx, [r15+298h]
0x14003787e  mov     [rsp+70h+var_40], rdx
0x140037883  mov     r9d, ebx
0x140037886  mov     dword ptr [rsp+70h+var_48], r14d
0x14003788b  lea     rdx, aProvideroperat_4; "ProviderOperation_NewQuery"
0x140037892  xor     r8d, r8d
0x140037895  mov     dword ptr [rsp+70h+var_50], r12d
0x14003789a  mov     rax, [rcx]
0x14003789d  mov     rax, [rax+190h]
0x1400378a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400378a9  mov     rcx, [rbp+arg_30]
0x1400378ad  lea     rdx, [r15+2A0h]
0x1400378b4  mov     [rsp+70h+var_40], rdx
0x1400378b9  mov     r9d, ebx
0x1400378bc  mov     dword ptr [rsp+70h+var_48], r14d
0x1400378c1  lea     rdx, aProvideroperat_20; "ProviderOperation_CancelQuery"
0x1400378c8  xor     r8d, r8d
0x1400378cb  mov     dword ptr [rsp+70h+var_50], r12d
0x1400378d0  mov     rax, [rcx]
0x1400378d3  mov     rax, [rax+190h]
0x1400378da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400378df  mov     rcx, [rbp+arg_30]
0x1400378e3  mov     rax, [rcx]
0x1400378e6  mov     rax, [rax+190h]
0x1400378ed  lea     rdx, [r15+2A8h]
0x1400378f4  mov     [rsp+70h+var_40], rdx
0x1400378f9  mov     r9d, ebx
0x1400378fc  mov     dword ptr [rsp+70h+var_48], r14d
0x140037901  lea     rdx, aProvideroperat; "ProviderOperation_AccessCheck"
0x140037908  xor     r8d, r8d
0x14003790b  mov     dword ptr [rsp+70h+var_50], r12d
0x140037910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037915  mov     rcx, [rbp+arg_30]
  ... truncated ...
```
