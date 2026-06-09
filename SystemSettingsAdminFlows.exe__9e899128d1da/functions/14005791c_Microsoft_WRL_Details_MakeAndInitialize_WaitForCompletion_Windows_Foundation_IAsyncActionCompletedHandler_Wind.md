# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x14005791c`
- end: `0x140057a4a`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `302`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140057c74`

## callees

- `0x140005f60`
- `0x14000e710`
- `0x14001a2a0`
- `0x140031b5c`
- `0x14005791c`
- `0x14007d010`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x1400579db`
- `KERNEL32!CreateEventExW` at `0x1400579db`
- `KERNEL32!GetLastError` at `0x1400579ea`
- `KERNEL32!GetLastError` at `0x1400579ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        char **a1)
{
  char *v2; // rax
  char *v3; // rbx
  signed int v4; // edi
  _QWORD *v5; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  char *v9; // [rsp+30h] [rbp+8h] BYREF
  char *v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (char *)operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  v10 = v2;
  if ( v2 )
  {
    v5 = v2 + 8;
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 8));
    *((_DWORD *)v3 + 11) = 1;
    *(_QWORD *)v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'};
    *v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v3 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *v5 = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v3 + 12) = 0;
    *((_QWORD *)v3 + 7) = 0;
    v9 = v3;
    v10 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v3 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<CStorageAdminHelper>::~MakeAllocator<CStorageAdminHelper>(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14005791c  mov     [rsp+arg_10], rbx
0x140057921  mov     [rsp+arg_18], rsi
0x140057926  push    rdi
0x140057927  sub     rsp, 20h
0x14005792b  mov     rsi, rcx
0x14005792e  mov     qword ptr [rcx], 0
0x140057935  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005793c  mov     ecx, 40h ; '@'; unsigned __int64
0x140057941  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140057946  mov     rbx, rax
0x140057949  mov     [rsp+28h+arg_8], rax
0x14005794e  test    rax, rax
0x140057951  jnz     short loc_14005795D
0x140057953  mov     edi, 8007000Eh
0x140057958  jmp     loc_140057A2E
0x14005795d  lea     rdi, [rax+8]
0x140057961  mov     rcx, rdi; this
0x140057964  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x140057969  mov     dword ptr [rbx+2Ch], 1
0x140057970  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIAsyncActionCompletedHandler@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x140057977  mov     [rbx], rax
0x14005797a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140057981  mov     [rdi], rax
0x140057984  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14005798b  test    rcx, rcx
0x14005798e  jz      short loc_14005799D
0x140057990  mov     rax, [rcx]
0x140057993  mov     rax, [rax+8]
0x140057997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005799c  nop
0x14005799d  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x1400579a4  mov     [rbx], rax
0x1400579a7  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1400579ae  mov     [rdi], rax
0x1400579b1  mov     dword ptr [rbx+30h], 0
0x1400579b8  mov     qword ptr [rbx+38h], 0
0x1400579c0  mov     [rsp+28h+arg_0], rbx
0x1400579c5  mov     [rsp+28h+arg_8], 0
0x1400579ce  mov     r9d, 1F0003h; dwDesiredAccess
0x1400579d4  xor     r8d, r8d; dwFlags
0x1400579d7  xor     edx, edx; lpName
0x1400579d9  xor     ecx, ecx; lpEventAttributes
0x1400579db  call    cs:__imp_CreateEventExW
0x1400579e1  mov     [rbx+38h], rax
0x1400579e5  test    rax, rax
0x1400579e8  jnz     short loc_140057A0F
0x1400579ea  call    cs:__imp_GetLastError
0x1400579f0  mov     edi, eax
0x1400579f2  test    eax, eax
0x1400579f4  jle     short loc_1400579FF
0x1400579f6  movzx   edi, ax
0x1400579f9  or      edi, 80070000h
0x1400579ff  test    edi, edi
0x140057a01  jns     short loc_140057A0F
0x140057a03  lea     rcx, [rsp+28h+arg_0]
0x140057a08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140057a0d  jmp     short loc_140057A2E
0x140057a0f  mov     rax, [rbx]
0x140057a12  mov     rcx, rbx
0x140057a15  mov     rax, [rax+8]
0x140057a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057a1e  nop
0x140057a1f  mov     [rsi], rbx
0x140057a22  lea     rcx, [rsp+28h+arg_0]
0x140057a27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140057a2c  xor     edi, edi
0x140057a2e  lea     rcx, [rsp+28h+arg_8]
0x140057a33  call    ??1?$MakeAllocator@VCStorageAdminHelper@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CStorageAdminHelper>::~MakeAllocator<CStorageAdminHelper>(void)
0x140057a38  mov     eax, edi
0x140057a3a  mov     rbx, [rsp+28h+arg_10]
0x140057a3f  mov     rsi, [rsp+28h+arg_18]
0x140057a44  add     rsp, 20h
0x140057a48  pop     rdi
0x140057a49  retn
```
