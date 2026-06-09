# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800108f8`
- end: `0x180010a32`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017144`

## callees

- `0x180009fc0`
- `0x18000c4cc`
- `0x18000fce8`
- `0x1800108f8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001099d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001099d`

## string_xrefs

- `0x18001095f`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
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
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVWebTokenRequestResult_Core_Web_Authentication_Security_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
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
0x1800108f8  mov     [rsp-18h+arg_18], r9
0x1800108fd  mov     [rsp-18h+arg_10], r8d
0x180010902  mov     [rsp-18h+dwindex], edx
0x180010906  push    rbp
0x180010907  push    rbx
0x180010908  push    rdi
0x180010909  mov     rbp, rsp
0x18001090c  sub     rsp, 40h
0x180010910  mov     rdi, rcx
0x180010913  mov     [rbp+arg_18], 0
0x18001091b  lea     rcx, [rbp+arg_18]
0x18001091f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010924  lea     rcx, [rbp+arg_18]
0x180010928  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x18001092d  mov     ebx, eax
0x18001092f  test    eax, eax
0x180010931  jns     short loc_18001093A
0x180010933  mov     edx, 648h
0x180010938  jmp     short loc_180010958
0x18001093a  mov     rax, [rdi]
0x18001093d  mov     rdx, [rbp+arg_18]
0x180010941  mov     rcx, rdi
0x180010944  mov     rax, [rax+30h]
0x180010948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001094d  mov     ebx, eax
0x18001094f  test    eax, eax
0x180010951  jns     short loc_180010970
0x180010953  mov     edx, 649h; void *
0x180010958  mov     rcx, [rbp+18h]; this
0x18001095c  mov     r9d, eax; char *
0x18001095f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001096b  jmp     loc_180010A1F
0x180010970  mov     rax, [rbp+arg_18]
0x180010974  mov     rcx, [rax+38h]
0x180010978  mov     [rbp+pHandles], rcx
0x18001097c  mov     [rbp+dwindex], 0
0x180010983  lea     rax, [rbp+dwindex]
0x180010987  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18001098c  lea     r9, [rbp+pHandles]; pHandles
0x180010990  mov     r8d, 1; cHandles
0x180010996  or      edx, 0FFFFFFFFh; dwTimeout
0x180010999  lea     ecx, [r8+7]; dwFlags
0x18001099d  call    cs:__imp_CoWaitForMultipleHandles
0x1800109a3  mov     ebx, eax
0x1800109a5  test    eax, eax
0x1800109a7  jns     short loc_1800109B0
0x1800109a9  mov     edx, 655h
0x1800109ae  jmp     short loc_180010958
0x1800109b0  mov     rax, [rbp+arg_18]
0x1800109b4  mov     ecx, [rax+30h]
0x1800109b7  cmp     ecx, 1
0x1800109ba  jz      short loc_180010A1D
0x1800109bc  mov     [rbp+var_10], 0
0x1800109c4  mov     rax, [rdi]
0x1800109c7  mov     rbx, [rax]
0x1800109ca  lea     rcx, [rbp+var_10]
0x1800109ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800109d3  lea     r8, [rbp+var_10]
0x1800109d7  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x1800109de  mov     rcx, rdi
0x1800109e1  mov     rax, rbx
0x1800109e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109e9  mov     ebx, eax
0x1800109eb  test    eax, eax
0x1800109ed  js      short loc_180010A12
0x1800109ef  mov     [rbp+arg_10], 8000FFFFh
0x1800109f6  mov     rcx, [rbp+var_10]
0x1800109fa  mov     rax, [rcx]
0x1800109fd  lea     rdx, [rbp+arg_10]
0x180010a01  mov     rax, [rax+40h]
0x180010a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a0a  mov     ebx, eax
0x180010a0c  test    eax, eax
0x180010a0e  cmovns  ebx, [rbp+arg_10]
0x180010a12  lea     rcx, [rbp+var_10]
0x180010a16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010a1b  jmp     short loc_180010A1F
0x180010a1d  xor     ebx, ebx
0x180010a1f  lea     rcx, [rbp+arg_18]
0x180010a23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010a28  mov     eax, ebx
0x180010a2a  add     rsp, 40h
0x180010a2e  pop     rdi
0x180010a2f  pop     rbx
0x180010a30  pop     rbp
0x180010a31  retn
```
