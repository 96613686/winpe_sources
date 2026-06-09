# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`scalar deleting destructor'(uint)

- ea: `0x18000f120`
- end: `0x18000f193`
- name: `??_GFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `115`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000f120`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f148`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)a1 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)a1 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>'::`2'::FTMEventDelegate::`vftable';
  CloseHandle(*((HANDLE *)a1 + 7));
  *((_DWORD *)a1 + 11) = -1073741823;
  v4 = *((_QWORD *)a1 + 4);
  if ( v4 )
  {
    *((_QWORD *)a1 + 4) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000f120  mov     [rsp+arg_0], rbx
0x18000f125  push    rdi
0x18000f126  sub     rsp, 20h
0x18000f12a  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>'}
0x18000f131  mov     rbx, rcx
0x18000f134  mov     [rcx], rax
0x18000f137  mov     edi, edx
0x18000f139  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f140  mov     [rcx+8], rax
0x18000f144  mov     rcx, [rcx+38h]; hObject
0x18000f148  call    cs:__imp_CloseHandle
0x18000f14e  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000f155  mov     rcx, [rbx+20h]
0x18000f159  test    rcx, rcx
0x18000f15c  jz      short loc_18000F172
0x18000f15e  mov     qword ptr [rbx+20h], 0
0x18000f166  mov     rax, [rcx]
0x18000f169  mov     rax, [rax+10h]
0x18000f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f172  test    dil, 1
0x18000f176  jz      short loc_18000F185
0x18000f178  mov     edx, 40h ; '@'; unsigned __int64
0x18000f17d  mov     rcx, rbx; void *
0x18000f180  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f185  mov     rax, rbx
0x18000f188  mov     rbx, [rsp+28h+arg_0]
0x18000f18d  add     rsp, 20h
0x18000f191  pop     rdi
0x18000f192  retn
```
