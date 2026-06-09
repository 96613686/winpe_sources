# wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x18001726c`
- end: `0x1800173a6`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `314`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), DWORD, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017e18`

## callees

- `0x18000cfa4`
- `0x18000eacc`
- `0x180016b6c`
- `0x18001726c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180017311`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180017311`

## string_xrefs

- `0x1800172d3`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *>(
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
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVBattery_Power_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVBattery_Power_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVBattery_Power_Devices_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVBattery_Power_Devices_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVBattery_Power_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
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
0x18001726c  mov     [rsp-18h+arg_18], r9
0x180017271  mov     [rsp-18h+arg_10], r8d
0x180017276  mov     [rsp-18h+dwindex], edx
0x18001727a  push    rbp
0x18001727b  push    rbx
0x18001727c  push    rdi
0x18001727d  mov     rbp, rsp
0x180017280  sub     rsp, 40h
0x180017284  mov     rdi, rcx
0x180017287  mov     [rbp+arg_18], 0
0x18001728f  lea     rcx, [rbp+arg_18]
0x180017293  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017298  lea     rcx, [rbp+arg_18]
0x18001729c  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x1800172a1  mov     ebx, eax
0x1800172a3  test    eax, eax
0x1800172a5  jns     short loc_1800172AE
0x1800172a7  mov     edx, 648h
0x1800172ac  jmp     short loc_1800172CC
0x1800172ae  mov     rax, [rdi]
0x1800172b1  mov     rdx, [rbp+arg_18]
0x1800172b5  mov     rcx, rdi
0x1800172b8  mov     rax, [rax+30h]
0x1800172bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c1  mov     ebx, eax
0x1800172c3  test    eax, eax
0x1800172c5  jns     short loc_1800172E4
0x1800172c7  mov     edx, 649h; void *
0x1800172cc  mov     rcx, [rbp+18h]; this
0x1800172d0  mov     r9d, eax; char *
0x1800172d3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800172da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172df  jmp     loc_180017393
0x1800172e4  mov     rax, [rbp+arg_18]
0x1800172e8  mov     rcx, [rax+38h]
0x1800172ec  mov     [rbp+pHandles], rcx
0x1800172f0  mov     [rbp+dwindex], 0
0x1800172f7  lea     rax, [rbp+dwindex]
0x1800172fb  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x180017300  lea     r9, [rbp+pHandles]; pHandles
0x180017304  mov     r8d, 1; cHandles
0x18001730a  or      edx, 0FFFFFFFFh; dwTimeout
0x18001730d  lea     ecx, [r8+7]; dwFlags
0x180017311  call    cs:__imp_CoWaitForMultipleHandles
0x180017317  mov     ebx, eax
0x180017319  test    eax, eax
0x18001731b  jns     short loc_180017324
0x18001731d  mov     edx, 655h
0x180017322  jmp     short loc_1800172CC
0x180017324  mov     rax, [rbp+arg_18]
0x180017328  mov     ecx, [rax+30h]
0x18001732b  cmp     ecx, 1
0x18001732e  jz      short loc_180017391
0x180017330  mov     [rbp+var_10], 0
0x180017338  mov     rax, [rdi]
0x18001733b  mov     rbx, [rax]
0x18001733e  lea     rcx, [rbp+var_10]
0x180017342  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017347  lea     r8, [rbp+var_10]
0x18001734b  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180017352  mov     rcx, rdi
0x180017355  mov     rax, rbx
0x180017358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001735d  mov     ebx, eax
0x18001735f  test    eax, eax
0x180017361  js      short loc_180017386
0x180017363  mov     [rbp+arg_10], 8000FFFFh
0x18001736a  mov     rcx, [rbp+var_10]
0x18001736e  mov     rax, [rcx]
0x180017371  lea     rdx, [rbp+arg_10]
0x180017375  mov     rax, [rax+40h]
0x180017379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001737e  mov     ebx, eax
0x180017380  test    eax, eax
0x180017382  cmovns  ebx, [rbp+arg_10]
0x180017386  lea     rcx, [rbp+var_10]
0x18001738a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001738f  jmp     short loc_180017393
0x180017391  xor     ebx, ebx
0x180017393  lea     rcx, [rbp+arg_18]
0x180017397  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001739c  mov     eax, ebx
0x18001739e  add     rsp, 40h
0x1800173a2  pop     rdi
0x1800173a3  pop     rbx
0x1800173a4  pop     rbp
0x1800173a5  retn
```
