# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180010678`
- end: `0x1800107b2`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017b98`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18000fa98`
- `0x180010678`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001071d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001071d`

## string_xrefs

- `0x1800106df`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v14 = a3;
  dwindex = a2;
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVFindAllAccountsResult_Core_Web_Authentication_Security_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVFindAllAccountsResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVFindAllAccountsResult_Core_Web_Authentication_Security_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVFindAllAccountsResult_Core_Web_Authentication_Security_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVFindAllAccountsResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1608;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v4,
      lpdwindex);
    goto LABEL_14;
  }
  v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1609;
    goto LABEL_5;
  }
  pHandles = *(HANDLE *)(v15 + 56);
  dwindex = 0;
  v4 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1621;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v15 + 48) == 1 )
  {
    v5 = 0;
  }
  else
  {
    v10 = 0;
    v7 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v5 = v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10);
    if ( v5 >= 0 )
    {
      v14 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v14);
      if ( v5 >= 0 )
        v5 = v14;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010678  mov     [rsp-18h+arg_18], r9
0x18001067d  mov     [rsp-18h+arg_10], r8d
0x180010682  mov     [rsp-18h+dwindex], edx
0x180010686  push    rbp
0x180010687  push    rbx
0x180010688  push    rdi
0x180010689  mov     rbp, rsp
0x18001068c  sub     rsp, 40h
0x180010690  mov     rdi, rcx
0x180010693  mov     [rbp+arg_18], 0
0x18001069b  lea     rcx, [rbp+arg_18]
0x18001069f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800106a4  lea     rcx, [rbp+arg_18]
0x1800106a8  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x1800106ad  mov     ebx, eax
0x1800106af  test    eax, eax
0x1800106b1  jns     short loc_1800106BA
0x1800106b3  mov     edx, 648h
0x1800106b8  jmp     short loc_1800106D8
0x1800106ba  mov     rax, [rdi]
0x1800106bd  mov     rdx, [rbp+arg_18]
0x1800106c1  mov     rcx, rdi
0x1800106c4  mov     rax, [rax+30h]
0x1800106c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106cd  mov     ebx, eax
0x1800106cf  test    eax, eax
0x1800106d1  jns     short loc_1800106F0
0x1800106d3  mov     edx, 649h; void *
0x1800106d8  mov     rcx, [rbp+18h]; this
0x1800106dc  mov     r9d, eax; char *
0x1800106df  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800106e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106eb  jmp     loc_18001079F
0x1800106f0  mov     rax, [rbp+arg_18]
0x1800106f4  mov     rcx, [rax+38h]
0x1800106f8  mov     [rbp+pHandles], rcx
0x1800106fc  mov     [rbp+dwindex], 0
0x180010703  lea     rax, [rbp+dwindex]
0x180010707  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18001070c  lea     r9, [rbp+pHandles]; pHandles
0x180010710  mov     r8d, 1; cHandles
0x180010716  or      edx, 0FFFFFFFFh; dwTimeout
0x180010719  lea     ecx, [r8+7]; dwFlags
0x18001071d  call    cs:__imp_CoWaitForMultipleHandles
0x180010723  mov     ebx, eax
0x180010725  test    eax, eax
0x180010727  jns     short loc_180010730
0x180010729  mov     edx, 655h
0x18001072e  jmp     short loc_1800106D8
0x180010730  mov     rax, [rbp+arg_18]
0x180010734  mov     ecx, [rax+30h]
0x180010737  cmp     ecx, 1
0x18001073a  jz      short loc_18001079D
0x18001073c  mov     [rbp+var_10], 0
0x180010744  mov     rax, [rdi]
0x180010747  mov     rbx, [rax]
0x18001074a  lea     rcx, [rbp+var_10]
0x18001074e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010753  lea     r8, [rbp+var_10]
0x180010757  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001075e  mov     rcx, rdi
0x180010761  mov     rax, rbx
0x180010764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010769  mov     ebx, eax
0x18001076b  test    eax, eax
0x18001076d  js      short loc_180010792
0x18001076f  mov     [rbp+arg_10], 8000FFFFh
0x180010776  mov     rcx, [rbp+var_10]
0x18001077a  mov     rax, [rcx]
0x18001077d  lea     rdx, [rbp+arg_10]
0x180010781  mov     rax, [rax+40h]
0x180010785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001078a  mov     ebx, eax
0x18001078c  test    eax, eax
0x18001078e  cmovns  ebx, [rbp+arg_10]
0x180010792  lea     rcx, [rbp+var_10]
0x180010796  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001079b  jmp     short loc_18001079F
0x18001079d  xor     ebx, ebx
0x18001079f  lea     rcx, [rbp+arg_18]
0x1800107a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800107a8  mov     eax, ebx
0x1800107aa  add     rsp, 40h
0x1800107ae  pop     rdi
0x1800107af  pop     rbx
0x1800107b0  pop     rbp
0x1800107b1  retn
```
