# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800107b8`
- end: `0x1800108f2`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
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
- `0x18000fbc0`
- `0x1800107b8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001085d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001085d`

## string_xrefs

- `0x18001081f`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(
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
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVWebAccountProvider_Credentials_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
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
0x1800107b8  mov     [rsp-18h+arg_18], r9
0x1800107bd  mov     [rsp-18h+arg_10], r8d
0x1800107c2  mov     [rsp-18h+dwindex], edx
0x1800107c6  push    rbp
0x1800107c7  push    rbx
0x1800107c8  push    rdi
0x1800107c9  mov     rbp, rsp
0x1800107cc  sub     rsp, 40h
0x1800107d0  mov     rdi, rcx
0x1800107d3  mov     [rbp+arg_18], 0
0x1800107db  lea     rcx, [rbp+arg_18]
0x1800107df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800107e4  lea     rcx, [rbp+arg_18]
0x1800107e8  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x1800107ed  mov     ebx, eax
0x1800107ef  test    eax, eax
0x1800107f1  jns     short loc_1800107FA
0x1800107f3  mov     edx, 648h
0x1800107f8  jmp     short loc_180010818
0x1800107fa  mov     rax, [rdi]
0x1800107fd  mov     rdx, [rbp+arg_18]
0x180010801  mov     rcx, rdi
0x180010804  mov     rax, [rax+30h]
0x180010808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080d  mov     ebx, eax
0x18001080f  test    eax, eax
0x180010811  jns     short loc_180010830
0x180010813  mov     edx, 649h; void *
0x180010818  mov     rcx, [rbp+18h]; this
0x18001081c  mov     r9d, eax; char *
0x18001081f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001082b  jmp     loc_1800108DF
0x180010830  mov     rax, [rbp+arg_18]
0x180010834  mov     rcx, [rax+38h]
0x180010838  mov     [rbp+pHandles], rcx
0x18001083c  mov     [rbp+dwindex], 0
0x180010843  lea     rax, [rbp+dwindex]
0x180010847  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18001084c  lea     r9, [rbp+pHandles]; pHandles
0x180010850  mov     r8d, 1; cHandles
0x180010856  or      edx, 0FFFFFFFFh; dwTimeout
0x180010859  lea     ecx, [r8+7]; dwFlags
0x18001085d  call    cs:__imp_CoWaitForMultipleHandles
0x180010863  mov     ebx, eax
0x180010865  test    eax, eax
0x180010867  jns     short loc_180010870
0x180010869  mov     edx, 655h
0x18001086e  jmp     short loc_180010818
0x180010870  mov     rax, [rbp+arg_18]
0x180010874  mov     ecx, [rax+30h]
0x180010877  cmp     ecx, 1
0x18001087a  jz      short loc_1800108DD
0x18001087c  mov     [rbp+var_10], 0
0x180010884  mov     rax, [rdi]
0x180010887  mov     rbx, [rax]
0x18001088a  lea     rcx, [rbp+var_10]
0x18001088e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010893  lea     r8, [rbp+var_10]
0x180010897  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001089e  mov     rcx, rdi
0x1800108a1  mov     rax, rbx
0x1800108a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a9  mov     ebx, eax
0x1800108ab  test    eax, eax
0x1800108ad  js      short loc_1800108D2
0x1800108af  mov     [rbp+arg_10], 8000FFFFh
0x1800108b6  mov     rcx, [rbp+var_10]
0x1800108ba  mov     rax, [rcx]
0x1800108bd  lea     rdx, [rbp+arg_10]
0x1800108c1  mov     rax, [rax+40h]
0x1800108c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ca  mov     ebx, eax
0x1800108cc  test    eax, eax
0x1800108ce  cmovns  ebx, [rbp+arg_10]
0x1800108d2  lea     rcx, [rbp+var_10]
0x1800108d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800108db  jmp     short loc_1800108DF
0x1800108dd  xor     ebx, ebx
0x1800108df  lea     rcx, [rbp+arg_18]
0x1800108e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800108e8  mov     eax, ebx
0x1800108ea  add     rsp, 40h
0x1800108ee  pop     rdi
0x1800108ef  pop     rbx
0x1800108f0  pop     rbp
0x1800108f1  retn
```
