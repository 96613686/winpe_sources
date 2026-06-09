# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18000cd90`
- end: `0x18000ceca`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b9a4`

## callees

- `0x180007630`
- `0x18000907c`
- `0x18000c5bc`
- `0x18000cd90`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000ce35`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18000ce35`

## string_xrefs

- `0x18000cdf7`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(
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
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1608;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
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
0x18000cd90  mov     [rsp-18h+arg_18], r9
0x18000cd95  mov     [rsp-18h+arg_10], r8d
0x18000cd9a  mov     [rsp-18h+dwindex], edx
0x18000cd9e  push    rbp
0x18000cd9f  push    rbx
0x18000cda0  push    rdi
0x18000cda1  mov     rbp, rsp
0x18000cda4  sub     rsp, 40h
0x18000cda8  mov     rdi, rcx
0x18000cdab  mov     [rbp+arg_18], 0
0x18000cdb3  lea     rcx, [rbp+arg_18]
0x18000cdb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cdbc  lea     rcx, [rbp+arg_18]
0x18000cdc0  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x18000cdc5  mov     ebx, eax
0x18000cdc7  test    eax, eax
0x18000cdc9  jns     short loc_18000CDD2
0x18000cdcb  mov     edx, 648h
0x18000cdd0  jmp     short loc_18000CDF0
0x18000cdd2  mov     rax, [rdi]
0x18000cdd5  mov     rdx, [rbp+arg_18]
0x18000cdd9  mov     rcx, rdi
0x18000cddc  mov     rax, [rax+30h]
0x18000cde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cde5  mov     ebx, eax
0x18000cde7  test    eax, eax
0x18000cde9  jns     short loc_18000CE08
0x18000cdeb  mov     edx, 649h; void *
0x18000cdf0  mov     rcx, [rbp+18h]; this
0x18000cdf4  mov     r9d, eax; char *
0x18000cdf7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000cdfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce03  jmp     loc_18000CEB7
0x18000ce08  mov     rax, [rbp+arg_18]
0x18000ce0c  mov     rcx, [rax+38h]
0x18000ce10  mov     [rbp+pHandles], rcx
0x18000ce14  mov     [rbp+dwindex], 0
0x18000ce1b  lea     rax, [rbp+dwindex]
0x18000ce1f  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x18000ce24  lea     r9, [rbp+pHandles]; pHandles
0x18000ce28  mov     r8d, 1; cHandles
0x18000ce2e  or      edx, 0FFFFFFFFh; dwTimeout
0x18000ce31  lea     ecx, [r8+7]; dwFlags
0x18000ce35  call    cs:__imp_CoWaitForMultipleHandles
0x18000ce3b  mov     ebx, eax
0x18000ce3d  test    eax, eax
0x18000ce3f  jns     short loc_18000CE48
0x18000ce41  mov     edx, 655h
0x18000ce46  jmp     short loc_18000CDF0
0x18000ce48  mov     rax, [rbp+arg_18]
0x18000ce4c  mov     ecx, [rax+30h]
0x18000ce4f  cmp     ecx, 1
0x18000ce52  jz      short loc_18000CEB5
0x18000ce54  mov     [rbp+var_10], 0
0x18000ce5c  mov     rax, [rdi]
0x18000ce5f  mov     rbx, [rax]
0x18000ce62  lea     rcx, [rbp+var_10]
0x18000ce66  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ce6b  lea     r8, [rbp+var_10]
0x18000ce6f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18000ce76  mov     rcx, rdi
0x18000ce79  mov     rax, rbx
0x18000ce7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce81  mov     ebx, eax
0x18000ce83  test    eax, eax
0x18000ce85  js      short loc_18000CEAA
0x18000ce87  mov     [rbp+arg_10], 8000FFFFh
0x18000ce8e  mov     rcx, [rbp+var_10]
0x18000ce92  mov     rax, [rcx]
0x18000ce95  lea     rdx, [rbp+arg_10]
0x18000ce99  mov     rax, [rax+40h]
0x18000ce9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea2  mov     ebx, eax
0x18000cea4  test    eax, eax
0x18000cea6  cmovns  ebx, [rbp+arg_10]
0x18000ceaa  lea     rcx, [rbp+var_10]
0x18000ceae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ceb3  jmp     short loc_18000CEB7
0x18000ceb5  xor     ebx, ebx
0x18000ceb7  lea     rcx, [rbp+arg_18]
0x18000cebb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cec0  mov     eax, ebx
0x18000cec2  add     rsp, 40h
0x18000cec6  pop     rdi
0x18000cec7  pop     rbx
0x18000cec8  pop     rbp
0x18000cec9  retn
```
