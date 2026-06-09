# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate * *)

- ea: `0x18002e8f0`
- end: `0x18002e9c4`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJ012K@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e714`

## callees

- `0x180004738`
- `0x18002e8f0`
- `0x18002e9cc`
- `0x18003c27c`
- `0x18007633c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e94f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002e94f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e95e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e95e`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___23___YAJ012K_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__U__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___23___YAJPEAU__IAsyncOperation_PEAVUserHostIdentity_WebAuthentication_Security_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAXK_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v2 )
    return 2147942414LL;
  v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
  v8 = v4;
  v9 = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  v4[7] = Event;
  if ( Event )
    goto LABEL_8;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_8:
    (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
    *a1 = v4;
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
    return 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
    Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(&v9);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x18002e8f0  mov     [rsp+arg_10], rbx
0x18002e8f5  mov     [rsp+arg_18], rsi
0x18002e8fa  push    rdi
0x18002e8fb  sub     rsp, 20h
0x18002e8ff  mov     rsi, rcx
0x18002e902  mov     qword ptr [rcx], 0
0x18002e909  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e910  mov     ecx, 40h ; '@'; unsigned __int64
0x18002e915  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002e91a  test    rax, rax
0x18002e91d  jnz     short loc_18002E929
0x18002e91f  mov     eax, 8007000Eh
0x18002e924  jmp     loc_18002E9B4
0x18002e929  mov     rcx, rax
0x18002e92c  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAXK@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *> *,tagCOWAIT_FLAGS,void *,ulong)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18002e931  mov     rdi, rax
0x18002e934  mov     [rsp+28h+arg_0], rax
0x18002e939  mov     [rsp+28h+arg_8], 0
0x18002e942  mov     r9d, 1F0003h; dwDesiredAccess
0x18002e948  xor     r8d, r8d; dwFlags
0x18002e94b  xor     edx, edx; lpName
0x18002e94d  xor     ecx, ecx; lpEventAttributes
0x18002e94f  call    cs:__imp_CreateEventExW
0x18002e955  mov     [rdi+38h], rax
0x18002e959  test    rax, rax
0x18002e95c  jnz     short loc_18002E98F
0x18002e95e  call    cs:__imp_GetLastError
0x18002e964  mov     ebx, eax
0x18002e966  test    eax, eax
0x18002e968  jle     short loc_18002E973
0x18002e96a  movzx   ebx, ax
0x18002e96d  or      ebx, 80070000h
0x18002e973  test    ebx, ebx
0x18002e975  jns     short loc_18002E98F
0x18002e977  lea     rcx, [rsp+28h+arg_0]
0x18002e97c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002e981  lea     rcx, [rsp+28h+arg_8]
0x18002e986  call    ??1?$MakeAllocator@VUserSigninChangeWatcher@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<UserSigninChangeWatcher>::~MakeAllocator<UserSigninChangeWatcher>(void)
0x18002e98b  mov     eax, ebx
0x18002e98d  jmp     short loc_18002E9B4
0x18002e98f  mov     rax, [rdi]
0x18002e992  mov     rcx, rdi
0x18002e995  mov     rax, [rax+8]
0x18002e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e99e  nop
0x18002e99f  mov     [rsi], rdi
0x18002e9a2  mov     rax, [rdi]
0x18002e9a5  mov     rcx, rdi
0x18002e9a8  mov     rax, [rax+10h]
0x18002e9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9b1  nop
0x18002e9b2  xor     eax, eax
0x18002e9b4  mov     rbx, [rsp+28h+arg_10]
0x18002e9b9  mov     rsi, [rsp+28h+arg_18]
0x18002e9be  add     rsp, 20h
0x18002e9c2  pop     rdi
0x18002e9c3  retn
```
