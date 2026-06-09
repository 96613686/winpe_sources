# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x18000f038`
- end: `0x18000f146`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f2cc`

## callees

- `0x180003050`
- `0x180005c28`
- `0x180006324`
- `0x180007f3c`
- `0x180009aa0`
- `0x18000b464`
- `0x18000f038`
- `0x180010360`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f0bd`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0cb`

## string_xrefs

- `0x18000f129`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___details_wil__YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAUIAsyncAction_Foundation_Windows___details_wil__YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  unsigned int v4; // edi
  wil::details *v5; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _QWORD *v11; // [rsp+40h] [rbp+8h] BYREF
  void *v12; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v12 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(v2);
    *v3 = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    v3[1] = `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    v3[7] = 0;
    v11 = v3;
    v12 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v3 + 7,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
      v4 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v9);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
        goto LABEL_6;
      }
    }
    (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
    *a1 = v3;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
    v4 = 0;
  }
  else
  {
    v4 = -2147024882;
  }
LABEL_6:
  Z::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,unsigned long,bool *>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>'::`2'::CompletionDelegate,Windows::Foundation::AJPEAUIAsyncAction,enum tagCOWAIT_FLAGS,unsigned long,bool *>(&v12);
  return v4;
}

```

## disassembly

```asm
0x18000f038  mov     [rsp+arg_10], rbx
0x18000f03d  push    rbp
0x18000f03e  push    rsi
0x18000f03f  push    rdi; int
0x18000f040  sub     rsp, 20h
0x18000f044  mov     rsi, rcx
0x18000f047  mov     qword ptr [rcx], 0
0x18000f04e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f055  mov     ecx, 40h ; '@'; unsigned __int64
0x18000f05a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f05f  mov     rbx, rax
0x18000f062  mov     [rsp+38h+arg_8], rax
0x18000f067  test    rax, rax
0x18000f06a  jnz     short loc_18000F076
0x18000f06c  mov     edi, 8007000Eh
0x18000f071  jmp     loc_18000F0FD
0x18000f076  mov     rcx, rbx
0x18000f079  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(void)
0x18000f07e  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6BIAsyncActionCompletedHandler@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18000f085  mov     [rbx], rax
0x18000f088  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f08f  mov     [rbx+8], rax
0x18000f093  mov     dword ptr [rbx+30h], 0
0x18000f09a  mov     qword ptr [rbx+38h], 0
0x18000f0a2  mov     [rsp+38h+arg_0], rbx
0x18000f0a7  mov     [rsp+38h+arg_8], 0
0x18000f0b0  mov     r9d, 1F0003h; dwDesiredAccess
0x18000f0b6  xor     r8d, r8d; dwFlags
0x18000f0b9  xor     edx, edx; lpName
0x18000f0bb  xor     ecx, ecx; lpEventAttributes
0x18000f0bd  call    cs:__imp_CreateEventExW
0x18000f0c3  mov     rbp, rax
0x18000f0c6  test    rax, rax
0x18000f0c9  jz      short loc_18000F116
0x18000f0cb  call    cs:__imp_GetLastError
0x18000f0d1  mov     rdx, rbp
0x18000f0d4  lea     rcx, [rbx+38h]
0x18000f0d8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000f0dd  nop
0x18000f0de  mov     rax, [rbx]
0x18000f0e1  mov     rcx, rbx
0x18000f0e4  mov     rax, [rax+8]
0x18000f0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ed  nop
0x18000f0ee  mov     [rsi], rbx
0x18000f0f1  lea     rcx, [rsp+38h+arg_0]
0x18000f0f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f0fb  xor     edi, edi
0x18000f0fd  lea     rcx, [rsp+38h+arg_8]
0x18000f102  call    ??1?$MakeAllocator@VCompletionDelegate@?1???$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>::~MakeAllocator<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate>(void)
0x18000f107  mov     eax, edi
0x18000f109  mov     rbx, [rsp+38h+arg_10]
0x18000f10e  add     rsp, 20h
0x18000f112  pop     rdi
0x18000f113  pop     rsi
0x18000f114  pop     rbp
0x18000f115  retn
0x18000f116  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f11b  mov     edi, eax
0x18000f11d  test    eax, eax
0x18000f11f  jns     short loc_18000F0DE
0x18000f121  mov     rcx, [rsp+38h]; this
0x18000f126  mov     r9d, eax; char *
0x18000f129  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f130  mov     edx, 62Bh; void *
0x18000f135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f13a  lea     rcx, [rsp+38h+arg_0]
0x18000f13f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f144  jmp     short loc_18000F0FD
```
