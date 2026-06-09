# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180060a88`
- end: `0x180060bde`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `342`
- prototype: `__int64(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), DWORD, int, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180061984`

## callees

- `0x18003d8cc`
- `0x180046f7c`
- `0x180060964`
- `0x180060a88`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180060b48`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180060b48`

## string_xrefs

- `0x180060acb`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`
- `0x180060b09`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(
        __int64 (__fastcall ***a1)(__int64, GUID *, __int64 *),
        DWORD a2,
        int a3,
        ...)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rbx
  HRESULT v7; // edi
  __int64 v8; // rdx
  __int64 (__fastcall **v9)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v10)(__int64, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v17; // [rsp+70h] [rbp+30h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF
  va_list va; // [rsp+78h] [rbp+38h]
  va_list va1; // [rsp+80h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v18 = va_arg(va1, _QWORD);
  v17 = a3;
  dwindex = a2;
  v13 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVRelativePanelDirectionTracker_System_Internal_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVRelativePanelDirectionTracker_System_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVRelativePanelDirectionTracker_System_Internal_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVRelativePanelDirectionTracker_System_Internal_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVRelativePanelDirectionTracker_System_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v13);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x648,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v4,
      lpdwindex);
    goto LABEL_14;
  }
  v6 = v13;
  v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), __int64))(*a1)[6])(a1, v13);
  if ( v7 < 0 )
  {
    v8 = 1609;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
      (const char *)(unsigned int)v7,
      lpdwindex);
    v5 = v7;
    goto LABEL_14;
  }
  pHandles = *(HANDLE *)(v6 + 56);
  dwindex = 0;
  v7 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  if ( v7 < 0 )
  {
    v8 = 1621;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v6 + 48) == 1 )
  {
    v5 = 0;
  }
  else
  {
    v9 = *a1;
    v18 = 0;
    v10 = *v9;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)va);
    v5 = v10((__int64)a1, &GUID_00000036_0000_0000_c000_000000000046, (__int64 *)va);
    if ( v5 >= 0 )
    {
      v17 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 64LL))(v18, &v17);
      if ( v5 >= 0 )
        v5 = v17;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)va);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180060a88  mov     rax, rsp
0x180060a8b  mov     [rax+8], rbx
0x180060a8f  mov     [rax+20h], r9
0x180060a93  mov     [rax+18h], r8d
0x180060a97  mov     [rax+10h], edx
0x180060a9a  push    rbp
0x180060a9b  push    rsi
0x180060a9c  push    rdi
0x180060a9d  mov     rbp, rsp
0x180060aa0  sub     rsp, 40h
0x180060aa4  mov     rsi, rcx
0x180060aa7  mov     [rbp+var_10], 0
0x180060aaf  lea     rcx, [rbp+var_10]
0x180060ab3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060ab8  lea     rcx, [rbp+var_10]
0x180060abc  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::System::RelativePanelDirectionTracker *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x180060ac1  mov     ebx, eax
0x180060ac3  test    eax, eax
0x180060ac5  jns     short loc_180060AE4
0x180060ac7  mov     rcx, [rbp+18h]; this
0x180060acb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180060ad2  mov     r9d, eax; char *
0x180060ad5  mov     edx, 648h; void *
0x180060ada  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060adf  jmp     loc_180060BC6
0x180060ae4  mov     rax, [rsi]
0x180060ae7  mov     rcx, rsi
0x180060aea  mov     rbx, [rbp+var_10]
0x180060aee  mov     rdx, rbx
0x180060af1  mov     rax, [rax+30h]
0x180060af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060afa  mov     edi, eax
0x180060afc  test    eax, eax
0x180060afe  jns     short loc_180060B1F
0x180060b00  mov     edx, 649h; void *
0x180060b05  mov     rcx, [rbp+18h]; this
0x180060b09  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180060b10  mov     r9d, edi; char *
0x180060b13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060b18  mov     ebx, edi
0x180060b1a  jmp     loc_180060BC6
0x180060b1f  mov     rax, [rbx+38h]
0x180060b23  lea     r9, [rbp+pHandles]; pHandles
0x180060b27  mov     r8d, 1; cHandles
0x180060b2d  mov     [rbp+pHandles], rax
0x180060b31  lea     rax, [rbp+dwindex]
0x180060b35  mov     [rbp+dwindex], 0
0x180060b3c  or      edx, 0FFFFFFFFh; dwTimeout
0x180060b3f  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x180060b44  lea     ecx, [r8+7]; dwFlags
0x180060b48  call    cs:__imp_CoWaitForMultipleHandles
0x180060b4e  mov     edi, eax
0x180060b50  test    eax, eax
0x180060b52  jns     short loc_180060B5B
0x180060b54  mov     edx, 655h
0x180060b59  jmp     short loc_180060B05
0x180060b5b  mov     eax, [rbx+30h]
0x180060b5e  cmp     eax, 1
0x180060b61  jz      short loc_180060BC4
0x180060b63  mov     rax, [rsi]
0x180060b66  lea     rcx, [rbp+arg_18]
0x180060b6a  mov     [rbp+arg_18], 0
0x180060b72  mov     rbx, [rax]
0x180060b75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060b7a  lea     r8, [rbp+arg_18]
0x180060b7e  mov     rcx, rsi
0x180060b81  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180060b88  mov     rax, rbx
0x180060b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060b90  mov     ebx, eax
0x180060b92  test    eax, eax
0x180060b94  js      short loc_180060BB9
0x180060b96  mov     rcx, [rbp+arg_18]
0x180060b9a  lea     rdx, [rbp+arg_10]
0x180060b9e  mov     [rbp+arg_10], 8000FFFFh
0x180060ba5  mov     rax, [rcx]
0x180060ba8  mov     rax, [rax+40h]
0x180060bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060bb1  test    eax, eax
0x180060bb3  mov     ebx, eax
0x180060bb5  cmovns  ebx, [rbp+arg_10]
0x180060bb9  lea     rcx, [rbp+arg_18]
0x180060bbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060bc2  jmp     short loc_180060BC6
0x180060bc4  xor     ebx, ebx
0x180060bc6  lea     rcx, [rbp+var_10]
0x180060bca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060bcf  mov     eax, ebx
0x180060bd1  mov     rbx, [rsp+40h+arg_0]
0x180060bd6  add     rsp, 40h
0x180060bda  pop     rdi
0x180060bdb  pop     rsi
0x180060bdc  pop     rbp
0x180060bdd  retn
```
