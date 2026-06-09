# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate * *)

- ea: `0x180068830`
- end: `0x180068916`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012K@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068668`

## callees

- `0x180004738`
- `0x18003c27c`
- `0x18006820c`
- `0x180068830`
- `0x18007633c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800688b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800688b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012K_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // edi
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(v2);
  *v3 = &`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  v3[1] = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
  *((_DWORD *)v3 + 12) = 0;
  v3[7] = 0;
  v8 = v3;
  v9 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v3[7] = Event;
  if ( Event )
    goto LABEL_7;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_7:
    (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
    *a1 = v3;
    v7 = 0;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
  Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180068830  mov     [rsp+arg_10], rbx
0x180068835  mov     [rsp+arg_18], rsi
0x18006883a  push    rdi
0x18006883b  sub     rsp, 20h
0x18006883f  mov     rsi, rcx
0x180068842  mov     qword ptr [rcx], 0
0x180068849  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180068850  mov     ecx, 40h ; '@'; unsigned __int64
0x180068855  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006885a  mov     rbx, rax
0x18006885d  test    rax, rax
0x180068860  jnz     short loc_18006886C
0x180068862  mov     eax, 8007000Eh
0x180068867  jmp     loc_180068906
0x18006886c  mov     rcx, rbx
0x18006886f  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(void)
0x180068874  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18006887b  mov     [rbx], rax
0x18006887e  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180068885  mov     [rbx+8], rax
0x180068889  mov     dword ptr [rbx+30h], 0
0x180068890  mov     qword ptr [rbx+38h], 0
0x180068898  mov     [rsp+28h+arg_0], rbx
0x18006889d  mov     [rsp+28h+arg_8], 0
0x1800688a6  mov     r9d, 1F0003h; dwDesiredAccess
0x1800688ac  xor     r8d, r8d; dwFlags
0x1800688af  xor     edx, edx; lpName
0x1800688b1  xor     ecx, ecx; lpEventAttributes
0x1800688b3  call    cs:__imp_CreateEventExW
0x1800688b9  mov     [rbx+38h], rax
0x1800688bd  test    rax, rax
0x1800688c0  jnz     short loc_1800688DB
0x1800688c2  call    cs:__imp_GetLastError
0x1800688c8  mov     edi, eax
0x1800688ca  test    eax, eax
0x1800688cc  jle     short loc_1800688D7
0x1800688ce  movzx   edi, ax
0x1800688d1  or      edi, 80070000h
0x1800688d7  test    edi, edi
0x1800688d9  js      short loc_1800688F0
0x1800688db  mov     rax, [rbx]
0x1800688de  mov     rcx, rbx
0x1800688e1  mov     rax, [rax+8]
0x1800688e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688ea  nop
0x1800688eb  mov     [rsi], rbx
0x1800688ee  xor     edi, edi
0x1800688f0  lea     rcx, [rsp+28h+arg_0]
0x1800688f5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800688fa  lea     rcx, [rsp+28h+arg_8]
0x1800688ff  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x180068904  mov     eax, edi
0x180068906  mov     rbx, [rsp+28h+arg_10]
0x18006890b  mov     rsi, [rsp+28h+arg_18]
0x180068910  add     rsp, 20h
0x180068914  pop     rdi
0x180068915  retn
```
