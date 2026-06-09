# `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vector deleting destructor'(uint)

- ea: `0x18000f0a0`
- end: `0x18000f113`
- name: `??_EFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@EEAAPEAXI@Z`
- size: `115`
- prototype: `void *__fastcall(void *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000f0a0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f0c8`

## pseudocode

```c
void *__fastcall `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vector deleting destructor'(
        void *a1,
        char a2)
{
  __int64 v4; // rcx

  *(_QWORD *)a1 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>'::`2'::FTMEventDelegate::`vftable';
  *((_QWORD *)a1 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x18000f0a0  mov     [rsp+arg_0], rbx
0x18000f0a5  push    rdi
0x18000f0a6  sub     rsp, 20h
0x18000f0aa  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>'}
0x18000f0b1  mov     rbx, rcx
0x18000f0b4  mov     [rcx], rax
0x18000f0b7  mov     edi, edx
0x18000f0b9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Credentials::WebAccountProvider *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000f0c0  mov     [rcx+8], rax
0x18000f0c4  mov     rcx, [rcx+38h]; hObject
0x18000f0c8  call    cs:__imp_CloseHandle
0x18000f0ce  mov     dword ptr [rbx+2Ch], 0C0000001h
0x18000f0d5  mov     rcx, [rbx+20h]
0x18000f0d9  test    rcx, rcx
0x18000f0dc  jz      short loc_18000F0F2
0x18000f0de  mov     qword ptr [rbx+20h], 0
0x18000f0e6  mov     rax, [rcx]
0x18000f0e9  mov     rax, [rax+10h]
0x18000f0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0f2  test    dil, 1
0x18000f0f6  jz      short loc_18000F105
0x18000f0f8  mov     edx, 40h ; '@'; unsigned __int64
0x18000f0fd  mov     rcx, rbx; void *
0x18000f100  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f105  mov     rax, rbx
0x18000f108  mov     rbx, [rsp+28h+arg_0]
0x18000f10d  add     rsp, 20h
0x18000f111  pop     rdi
0x18000f112  retn
```
