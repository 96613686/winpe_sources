# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection>>)

- ea: `0x180015a74`
- end: `0x180015b0c`
- name: `??$ActivateInstance@V?$ComPtr@UIAppServiceConnection@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppServiceConnection@AppService@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(HSTRING__ *activatableClassId, Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection> > instance)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800054bc`

## callees

- `0x180006060`
- `0x180015a74`
- `0x1800204d6`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015aa4`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015aa4`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection>>(
        HSTRING__ *activatableClassId,
        Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::AppService::IAppServiceConnection> > instance)
{
  int v4; // edi
  Windows::ApplicationModel::AppService::IAppServiceConnection *v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)instance.ptr_);
  instance.ptr_->ptr_ = 0;
  v6 = 0;
  v4 = RoActivateInstance(activatableClassId, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_9dd474a2_871f_4d52_89a9_9e090531bd27, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      instance.ptr_->ptr_ = v6;
    }
    else
    {
      v4 = v6->QueryInterface(v6, &GUID_9dd474a2_871f_4d52_89a9_9e090531bd27, (void **)&instance.ptr_->ptr_);
      v6->Release(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015a74  mov     [rsp+arg_0], rbx
0x180015a79  push    rdi
0x180015a7a  sub     rsp, 20h
0x180015a7e  mov     rdi, activatableClassId
0x180015a81  mov     rbx, instance
0x180015a84  mov     activatableClassId, instance; this
0x180015a87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015a8c  lea     instance, [rsp+28h+arg_8]
0x180015a91  mov     qword ptr [rbx], 0
0x180015a98  mov     activatableClassId, rdi
0x180015a9b  mov     [rsp+28h+arg_8], 0
0x180015aa4  call    cs:__imp_RoActivateInstance
0x180015aaa  mov     edi, eax
0x180015aac  test    eax, eax
0x180015aae  js      short loc_180015AFF
0x180015ab0  mov     r8d, 10h; Size
0x180015ab6  lea     instance, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180015abd  lea     activatableClassId, _GUID_9dd474a2_871f_4d52_89a9_9e090531bd27; Buf1
0x180015ac4  call    memcmp_0
0x180015ac9  mov     activatableClassId, [rsp+28h+arg_8]
0x180015ace  test    eax, eax
0x180015ad0  jnz     short loc_180015AD7
0x180015ad2  mov     [rbx], activatableClassId
0x180015ad5  jmp     short loc_180015AFF
0x180015ad7  mov     rax, [activatableClassId]
0x180015ada  lea     instance, _GUID_9dd474a2_871f_4d52_89a9_9e090531bd27
0x180015ae1  mov     r8, rbx
0x180015ae4  mov     rax, [rax]
0x180015ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aec  mov     activatableClassId, [rsp+28h+arg_8]
0x180015af1  mov     edi, eax
0x180015af3  mov     rax, [activatableClassId]
0x180015af6  mov     rax, [rax+10h]
0x180015afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aff  mov     rbx, [rsp+28h+arg_0]
0x180015b04  mov     eax, edi
0x180015b06  add     rsp, 20h
0x180015b0a  pop     rdi
0x180015b0b  retn
```
