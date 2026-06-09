# CInterceptor_IWbemSyncProvider::Enumerate(IWbemServices *,long,IWbemContext *,ushort const *,IWbemObjectSink *)

- ea: `0x140012ac0`
- end: `0x14001322f`
- name: `?Enumerate@CInterceptor_IWbemSyncProvider@@UEAAJPEAUIWbemServices@@JPEAUIWbemContext@@PEBGPEAUIWbemObjectSink@@@Z`
- size: `1903`
- prototype: `__int64 __fastcall(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemServices *, int, struct IWbemContext *, OLECHAR *psz, struct IWbemObjectSink *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140012ac0`
- `0x140013b48`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140013182`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140013182`
- `wbemcomn!GetMemLogObject` at `0x1400131f2`
- `wbemcomn!GetMemLogObject` at `0x1400131f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400131fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400131fd`
- `OLEAUT32!__imp_SysAllocString` at `0x140012b5a`
- `OLEAUT32!__imp_SysAllocString` at `0x140012b5a`
- `OLEAUT32!__imp_SysFreeString` at `0x140012bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x140012bd3`
- `OLEAUT32!__imp_VariantInit` at `0x140013175`
- `OLEAUT32!__imp_VariantInit` at `0x140013175`
- `OLEAUT32!__imp_VariantClear` at `0x1400131b5`
- `OLEAUT32!__imp_VariantClear` at `0x1400131b5`

## string_xrefs

- `0x140012e78`: `ProviderOperation_CreateRefresher`
- `0x140013193`: `HostProcessIdentifier`
- `0x140012dd6`: `ProviderOperation_DeleteInstanceAsync`
- `0x14001309e`: `ProviderOperation_AccessCheck`
- `0x140012d34`: `ProviderOperation_CreateInstanceEnumAsync`
- `0x140012eae`: `ProviderOperation_CreateRefreshableObject`
- `0x140012c92`: `ProviderOperation_DeleteClassAsync`
- `0x140012cc8`: `ProviderOperation_CreateClassEnumAsync`
- `0x140012f1a`: `ProviderOperation_CreateRefreshableEnum`

## pseudocode

```c
__int64 __fastcall CInterceptor_IWbemSyncProvider::Enumerate(
        CInterceptor_IWbemSyncProvider *this,
        struct IWbemServices *a2,
        __int64 a3,
        struct IWbemContext *a4,
        OLECHAR *psz,
        struct IWbemObjectSink *a6)
{
  int v9; // eax
  struct IWbemObjectSink *v10; // rsi
  int v11; // ebx
  BSTR v13; // rax
  OLECHAR *v14; // rdi
  CMemoryLog *MemLogObject; // rax
  __int64 v16; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+48h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF

  v9 = wbem_wcsicmp(psz, L"Msft_Providers");
  v10 = a6;
  if ( v9 )
  {
    v11 = -2147217392;
  }
  else
  {
    v17 = 0;
    v13 = SysAllocString(psz);
    v14 = v13;
    if ( v13 )
    {
      v11 = ((__int64 (__fastcall *)(struct IWbemServices *, BSTR, _QWORD, struct IWbemContext *, __int64 *, _QWORD))a2->lpVtbl->GetObjectA)(
              a2,
              v13,
              0,
              a4,
              &v17,
              0);
      if ( v11 >= 0 )
      {
        v16 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 120LL))(v17, 0, &v16);
        if ( v11 >= 0 )
        {
          a6 = 0;
          (**(void (__fastcall ***)(__int64, GUID *, struct IWbemObjectSink **))v16)(v16, &IID__IWmiObject, &a6);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_GetObjectAsync",
            0,
            8,
            1,
            21,
            (char *)this + 480);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_PutClassAsync",
            0,
            8,
            1,
            21,
            (char *)this + 488);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_DeleteClassAsync",
            0,
            8,
            1,
            21,
            (char *)this + 496);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_CreateClassEnumAsync",
            0,
            8,
            1,
            21,
            (char *)this + 504);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_PutInstanceAsync",
            0,
            8,
            1,
            21,
            (char *)this + 512);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_CreateInstanceEnumAsync",
            0,
            8,
            1,
            21,
            (char *)this + 528);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_ExecQueryAsync",
            0,
            8,
            1,
            21,
            (char *)this + 536);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_ExecNotificationQueryAsync",
            0,
            8,
            1,
            21,
            (char *)this + 544);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_DeleteInstanceAsync",
            0,
            8,
            1,
            21,
            (char *)this + 520);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_ExecMethodAsync",
            0,
            8,
            1,
            21,
            (char *)this + 552);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_QueryInstances",
            0,
            8,
            1,
            21,
            (char *)this + 592);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_CreateRefresher",
            0,
            8,
            1,
            21,
            (char *)this + 600);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_CreateRefreshableObject",
            0,
            8,
            1,
            21,
            (char *)this + 608);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_StopRefreshing",
            0,
            8,
            1,
            21,
            (char *)this + 616);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_CreateRefreshableEnum",
            0,
            8,
            1,
            21,
            (char *)this + 624);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_GetObjects",
            0,
            8,
            1,
            21,
            (char *)this + 632);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_GetProperty",
            0,
            8,
            1,
            21,
            (char *)this + 640);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_PutProperty",
            0,
            8,
            1,
            21,
            (char *)this + 648);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_ProvideEvents",
            0,
            8,
            1,
            21,
            (char *)this + 656);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_NewQuery",
            0,
            8,
            1,
            21,
            (char *)this + 664);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_CancelQuery",
            0,
            8,
            1,
            21,
            (char *)this + 672);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_AccessCheck",
            0,
            8,
            1,
            21,
            (char *)this + 680);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_SetRegistrationObject",
            0,
            8,
            1,
            21,
            (char *)this + 688);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_FindConsumer",
            0,
            8,
            1,
            21,
            (char *)this + 696);
          ((void (__fastcall *)(struct IWbemObjectSink *, const wchar_t *, _QWORD, __int64, int, int, char *))a6->lpVtbl[10].QueryInterface)(
            a6,
            L"ProviderOperation_ValidateSubscription",
            0,
            8,
            1,
            21,
            (char *)this + 704);
          ((void (__fastcall *)(struct IWbemObjectSink *))a6->lpVtbl->Release)(a6);
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pvarg.vt = 3;
          pvarg.lVal = GetCurrentProcessId();
          (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v16 + 40LL))(
            v16,
            L"HostProcessIdentifier",
            0,
            &pvarg,
            0);
          VariantClear(&pvarg);
          v11 = ((__int64 (__fastcall *)(struct IWbemObjectSink *, __int64, __int64 *))v10->lpVtbl->Indicate)(
                  v10,
                  1,
                  &v16);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      SysFreeString(v14);
    }
    else
    {
      v11 = -2147217402;
    }
  }
  ((void (__fastcall *)(struct IWbemObjectSink *, _QWORD, _QWORD, _QWORD, _QWORD))v10->lpVtbl->SetStatus)(
    v10,
    0,
    (unsigned int)v11,
    0,
    0);
  if ( v11 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v11);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      170,
      WPP_8fe8ac2c7c0037f5bee7c55b6a976ec1_Traceguids,
      (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140012ac0  push    rbp
0x140012ac2  push    rbx
0x140012ac3  push    rsi
0x140012ac4  push    rdi
0x140012ac5  push    r12
0x140012ac7  push    r14
0x140012ac9  push    r15
0x140012acb  mov     rbp, rsp
0x140012ace  sub     rsp, 70h
0x140012ad2  mov     rbx, rdx
0x140012ad5  mov     r15, rcx
0x140012ad8  mov     rcx, [rbp+psz]; unsigned __int16 *
0x140012adc  lea     rdx, aMsftProviders; "Msft_Providers"
0x140012ae3  mov     r14, r9
0x140012ae6  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x140012aeb  mov     rsi, [rbp+arg_28]
0x140012aef  test    eax, eax
0x140012af1  jz      short loc_140012B4E
0x140012af3  mov     ebx, 80041010h
0x140012af8  mov     rax, [rsi]
0x140012afb  xor     r9d, r9d
0x140012afe  mov     r8d, ebx
0x140012b01  mov     [rsp+70h+var_50], 0
0x140012b0a  xor     edx, edx
0x140012b0c  mov     rcx, rsi
0x140012b0f  mov     rax, [rax+20h]
0x140012b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b18  test    ebx, ebx
0x140012b1a  js      loc_1400131F2
0x140012b20  mov     rcx, cs:WPP_GLOBAL_Control
0x140012b27  lea     rax, WPP_GLOBAL_Control
0x140012b2e  cmp     rcx, rax
0x140012b31  jz      short loc_140012B3D
0x140012b33  test    byte ptr [rcx+1Ch], 4
0x140012b37  jnz     loc_140013208
0x140012b3d  mov     eax, ebx
0x140012b3f  add     rsp, 70h
0x140012b43  pop     r15
0x140012b45  pop     r14
0x140012b47  pop     r12
0x140012b49  pop     rdi
0x140012b4a  pop     rsi
0x140012b4b  pop     rbx
0x140012b4c  pop     rbp
0x140012b4d  retn
0x140012b4e  mov     rcx, [rbp+psz]; psz
0x140012b52  mov     [rbp+var_28], 0
0x140012b5a  call    cs:__imp_SysAllocString
0x140012b60  mov     rdi, rax
0x140012b63  test    rax, rax
0x140012b66  jz      loc_1400131E8
0x140012b6c  mov     rcx, [rbx]
0x140012b6f  mov     r9, r14
0x140012b72  mov     [rsp+70h+var_48], 0
0x140012b7b  xor     r8d, r8d
0x140012b7e  mov     rdx, rdi
0x140012b81  mov     rax, [rcx+30h]
0x140012b85  lea     rcx, [rbp+var_28]
0x140012b89  mov     [rsp+70h+var_50], rcx
0x140012b8e  mov     rcx, rbx
0x140012b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012b96  mov     ebx, eax
0x140012b98  test    eax, eax
0x140012b9a  js      short loc_140012BD0
0x140012b9c  mov     rcx, [rbp+var_28]
0x140012ba0  lea     r8, [rbp+var_30]
0x140012ba4  mov     [rbp+var_30], 0
0x140012bac  xor     edx, edx
0x140012bae  mov     rax, [rcx]
0x140012bb1  mov     rax, [rax+78h]
0x140012bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bba  mov     ebx, eax
0x140012bbc  test    eax, eax
0x140012bbe  jns     short loc_140012BDE
0x140012bc0  mov     rcx, [rbp+var_28]
0x140012bc4  mov     rax, [rcx]
0x140012bc7  mov     rax, [rax+10h]
0x140012bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012bd0  mov     rcx, rdi; bstrString
0x140012bd3  call    cs:__imp_SysFreeString
0x140012bd9  jmp     loc_140012AF8
0x140012bde  mov     rcx, [rbp+var_30]
0x140012be2  lea     r8, [rbp+arg_28]
0x140012be6  mov     [rbp+arg_28], 0
0x140012bee  lea     rdx, IID__IWmiObject
0x140012bf5  mov     rax, [rcx]
0x140012bf8  mov     rax, [rax]
0x140012bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c00  mov     rcx, [rbp+arg_28]
0x140012c04  lea     rdx, [r15+1E0h]
0x140012c0b  mov     [rsp+70h+var_40], rdx
0x140012c10  mov     r14d, 15h
0x140012c16  mov     dword ptr [rsp+70h+var_48], r14d
0x140012c1b  lea     rdx, aProvideroperat_12; "ProviderOperation_GetObjectAsync"
0x140012c22  xor     r8d, r8d
0x140012c25  mov     rax, [rcx]
0x140012c28  lea     ebx, [r14-0Dh]
0x140012c2c  lea     r12d, [r14-14h]
0x140012c30  mov     r9d, ebx
0x140012c33  mov     dword ptr [rsp+70h+var_50], r12d
0x140012c38  mov     rax, [rax+190h]
0x140012c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c44  mov     rcx, [rbp+arg_28]
0x140012c48  lea     rdx, [r15+1E8h]
0x140012c4f  mov     [rsp+70h+var_40], rdx
0x140012c54  mov     r9d, ebx
0x140012c57  mov     dword ptr [rsp+70h+var_48], r14d
0x140012c5c  lea     rdx, aProvideroperat_11; "ProviderOperation_PutClassAsync"
0x140012c63  xor     r8d, r8d
0x140012c66  mov     dword ptr [rsp+70h+var_50], r12d
0x140012c6b  mov     rax, [rcx]
0x140012c6e  mov     rax, [rax+190h]
0x140012c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012c7a  mov     rcx, [rbp+arg_28]
0x140012c7e  lea     rdx, [r15+1F0h]
0x140012c85  mov     [rsp+70h+var_40], rdx
0x140012c8a  mov     r9d, ebx
0x140012c8d  mov     dword ptr [rsp+70h+var_48], r14d
0x140012c92  lea     rdx, aProvideroperat_15; "ProviderOperation_DeleteClassAsync"
0x140012c99  xor     r8d, r8d
0x140012c9c  mov     dword ptr [rsp+70h+var_50], r12d
0x140012ca1  mov     rax, [rcx]
0x140012ca4  mov     rax, [rax+190h]
0x140012cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012cb0  mov     rcx, [rbp+arg_28]
0x140012cb4  lea     rdx, [r15+1F8h]
0x140012cbb  mov     [rsp+70h+var_40], rdx
0x140012cc0  mov     r9d, ebx
0x140012cc3  mov     dword ptr [rsp+70h+var_48], r14d
0x140012cc8  lea     rdx, aProvideroperat_17; "ProviderOperation_CreateClassEnumAsync"
0x140012ccf  xor     r8d, r8d
0x140012cd2  mov     dword ptr [rsp+70h+var_50], r12d
0x140012cd7  mov     rax, [rcx]
0x140012cda  mov     rax, [rax+190h]
0x140012ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ce6  mov     rcx, [rbp+arg_28]
0x140012cea  lea     rdx, [r15+200h]
0x140012cf1  mov     [rsp+70h+var_40], rdx
0x140012cf6  mov     r9d, ebx
0x140012cf9  mov     dword ptr [rsp+70h+var_48], r14d
0x140012cfe  lea     rdx, aProvideroperat_10; "ProviderOperation_PutInstanceAsync"
0x140012d05  xor     r8d, r8d
0x140012d08  mov     dword ptr [rsp+70h+var_50], r12d
0x140012d0d  mov     rax, [rcx]
0x140012d10  mov     rax, [rax+190h]
0x140012d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d1c  mov     rcx, [rbp+arg_28]
0x140012d20  lea     rdx, [r15+210h]
0x140012d27  mov     [rsp+70h+var_40], rdx
0x140012d2c  mov     r9d, ebx
0x140012d2f  mov     dword ptr [rsp+70h+var_48], r14d
0x140012d34  lea     rdx, aProvideroperat_14; "ProviderOperation_CreateInstanceEnumAsy"...
0x140012d3b  xor     r8d, r8d
0x140012d3e  mov     dword ptr [rsp+70h+var_50], r12d
0x140012d43  mov     rax, [rcx]
0x140012d46  mov     rax, [rax+190h]
0x140012d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d52  mov     rcx, [rbp+arg_28]
0x140012d56  lea     rdx, [r15+218h]
0x140012d5d  mov     [rsp+70h+var_40], rdx
0x140012d62  mov     dword ptr [rsp+70h+var_48], r14d
0x140012d67  mov     rax, [rcx]
0x140012d6a  mov     rax, [rax+190h]
0x140012d71  lea     rdx, aProvideroperat_5; "ProviderOperation_ExecQueryAsync"
0x140012d78  mov     r9d, ebx
0x140012d7b  mov     dword ptr [rsp+70h+var_50], r12d
0x140012d80  xor     r8d, r8d
0x140012d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012d88  mov     rcx, [rbp+arg_28]
0x140012d8c  lea     rdx, [r15+220h]
0x140012d93  mov     [rsp+70h+var_40], rdx
0x140012d98  mov     r9d, ebx
0x140012d9b  mov     dword ptr [rsp+70h+var_48], r14d
0x140012da0  lea     rdx, aProvideroperat_21; "ProviderOperation_ExecNotificationQuery"...
0x140012da7  xor     r8d, r8d
0x140012daa  mov     dword ptr [rsp+70h+var_50], r12d
0x140012daf  mov     rax, [rcx]
0x140012db2  mov     rax, [rax+190h]
0x140012db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012dbe  mov     rcx, [rbp+arg_28]
0x140012dc2  lea     rdx, [r15+208h]
0x140012dc9  mov     [rsp+70h+var_40], rdx
0x140012dce  mov     r9d, ebx
0x140012dd1  mov     dword ptr [rsp+70h+var_48], r14d
0x140012dd6  lea     rdx, aProvideroperat_22; "ProviderOperation_DeleteInstanceAsync"
0x140012ddd  xor     r8d, r8d
0x140012de0  mov     dword ptr [rsp+70h+var_50], r12d
0x140012de5  mov     rax, [rcx]
0x140012de8  mov     rax, [rax+190h]
0x140012def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012df4  mov     rcx, [rbp+arg_28]
0x140012df8  lea     rdx, [r15+228h]
0x140012dff  mov     [rsp+70h+var_40], rdx
0x140012e04  mov     r9d, ebx
0x140012e07  mov     dword ptr [rsp+70h+var_48], r14d
0x140012e0c  lea     rdx, aProvideroperat_13; "ProviderOperation_ExecMethodAsync"
0x140012e13  xor     r8d, r8d
0x140012e16  mov     dword ptr [rsp+70h+var_50], r12d
0x140012e1b  mov     rax, [rcx]
0x140012e1e  mov     rax, [rax+190h]
0x140012e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e2a  mov     rcx, [rbp+arg_28]
0x140012e2e  lea     rdx, [r15+250h]
0x140012e35  mov     [rsp+70h+var_40], rdx
0x140012e3a  mov     r9d, ebx
0x140012e3d  mov     dword ptr [rsp+70h+var_48], r14d
0x140012e42  lea     rdx, aProvideroperat_8; "ProviderOperation_QueryInstances"
0x140012e49  xor     r8d, r8d
0x140012e4c  mov     dword ptr [rsp+70h+var_50], r12d
0x140012e51  mov     rax, [rcx]
0x140012e54  mov     rax, [rax+190h]
0x140012e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e60  mov     rcx, [rbp+arg_28]
0x140012e64  lea     rdx, [r15+258h]
0x140012e6b  mov     [rsp+70h+var_40], rdx
0x140012e70  mov     r9d, ebx
0x140012e73  mov     dword ptr [rsp+70h+var_48], r14d
0x140012e78  lea     rdx, aProvideroperat_1; "ProviderOperation_CreateRefresher"
0x140012e7f  xor     r8d, r8d
0x140012e82  mov     dword ptr [rsp+70h+var_50], r12d
0x140012e87  mov     rax, [rcx]
0x140012e8a  mov     rax, [rax+190h]
0x140012e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012e96  mov     rcx, [rbp+arg_28]
0x140012e9a  lea     rdx, [r15+260h]
0x140012ea1  mov     [rsp+70h+var_40], rdx
0x140012ea6  mov     r9d, ebx
0x140012ea9  mov     dword ptr [rsp+70h+var_48], r14d
0x140012eae  lea     rdx, aProvideroperat_23; "ProviderOperation_CreateRefreshableObje"...
0x140012eb5  xor     r8d, r8d
0x140012eb8  mov     dword ptr [rsp+70h+var_50], r12d
0x140012ebd  mov     rax, [rcx]
0x140012ec0  mov     rax, [rax+190h]
0x140012ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ecc  mov     rcx, [rbp+arg_28]
0x140012ed0  lea     rdx, [r15+268h]
0x140012ed7  mov     [rsp+70h+var_40], rdx
0x140012edc  mov     r9d, ebx
0x140012edf  mov     dword ptr [rsp+70h+var_48], r14d
0x140012ee4  lea     rdx, aProvideroperat_3; "ProviderOperation_StopRefreshing"
0x140012eeb  mov     dword ptr [rsp+70h+var_50], r12d
0x140012ef0  xor     r8d, r8d
0x140012ef3  mov     rax, [rcx]
0x140012ef6  mov     rax, [rax+190h]
0x140012efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f02  mov     rcx, [rbp+arg_28]
0x140012f06  lea     rdx, [r15+270h]
0x140012f0d  mov     [rsp+70h+var_40], rdx
0x140012f12  mov     r9d, ebx
0x140012f15  mov     dword ptr [rsp+70h+var_48], r14d
0x140012f1a  lea     rdx, aProvideroperat_7; "ProviderOperation_CreateRefreshableEnum"
0x140012f21  xor     r8d, r8d
0x140012f24  mov     dword ptr [rsp+70h+var_50], r12d
0x140012f29  mov     rax, [rcx]
0x140012f2c  mov     rax, [rax+190h]
0x140012f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f38  mov     rcx, [rbp+arg_28]
0x140012f3c  lea     rdx, [r15+278h]
0x140012f43  mov     [rsp+70h+var_40], rdx
0x140012f48  mov     r9d, ebx
0x140012f4b  mov     dword ptr [rsp+70h+var_48], r14d
0x140012f50  lea     rdx, aProvideroperat_19; "ProviderOperation_GetObjects"
0x140012f57  xor     r8d, r8d
0x140012f5a  mov     dword ptr [rsp+70h+var_50], r12d
0x140012f5f  mov     rax, [rcx]
0x140012f62  mov     rax, [rax+190h]
0x140012f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012f6e  mov     rcx, [rbp+arg_28]
0x140012f72  lea     rdx, [r15+280h]
0x140012f79  mov     [rsp+70h+var_40], rdx
0x140012f7e  mov     r9d, ebx
0x140012f81  mov     dword ptr [rsp+70h+var_48], r14d
0x140012f86  lea     rdx, aProvideroperat_0; "ProviderOperation_GetProperty"
0x140012f8d  xor     r8d, r8d
0x140012f90  mov     dword ptr [rsp+70h+var_50], r12d
0x140012f95  mov     rax, [rcx]
0x140012f98  mov     rax, [rax+190h]
0x140012f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fa4  mov     rcx, [rbp+arg_28]
0x140012fa8  lea     rdx, [r15+288h]
0x140012faf  mov     [rsp+70h+var_40], rdx
0x140012fb4  mov     r9d, ebx
0x140012fb7  mov     dword ptr [rsp+70h+var_48], r14d
0x140012fbc  lea     rdx, aProvideroperat_2; "ProviderOperation_PutProperty"
0x140012fc3  xor     r8d, r8d
0x140012fc6  mov     dword ptr [rsp+70h+var_50], r12d
0x140012fcb  mov     rax, [rcx]
0x140012fce  mov     rax, [rax+190h]
0x140012fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012fda  mov     rcx, [rbp+arg_28]
0x140012fde  lea     rdx, [r15+290h]
0x140012fe5  mov     [rsp+70h+var_40], rdx
0x140012fea  mov     r9d, ebx
0x140012fed  mov     dword ptr [rsp+70h+var_48], r14d
0x140012ff2  lea     rdx, aProvideroperat_18; "ProviderOperation_ProvideEvents"
0x140012ff9  xor     r8d, r8d
0x140012ffc  mov     dword ptr [rsp+70h+var_50], r12d
0x140013001  mov     rax, [rcx]
0x140013004  mov     rax, [rax+190h]
0x14001300b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
