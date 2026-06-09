# Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)

- ea: `0x180015b14`
- end: `0x180015bac`
- name: `??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(HSTRING__ *activatableClassId, Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> > instance)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800054bc`

## callees

- `0x180006060`
- `0x180015b14`
- `0x1800204d6`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015b44`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015b44`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
        HSTRING__ *activatableClassId,
        Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet> > instance)
{
  int v4; // edi
  Windows::Foundation::Collections::IPropertySet *v6; // [rsp+38h] [rbp+10h] BYREF

  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> >'::`2'::FTMEventDelegate> *)instance.ptr_);
  instance.ptr_->ptr_ = 0;
  v6 = 0;
  v4 = RoActivateInstance(activatableClassId, &v6);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      instance.ptr_->ptr_ = v6;
    }
    else
    {
      v4 = v6->QueryInterface(v6, &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, (void **)&instance.ptr_->ptr_);
      v6->Release(v6);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015b14  mov     [rsp+arg_0], rbx
0x180015b19  push    rdi
0x180015b1a  sub     rsp, 20h
0x180015b1e  mov     rdi, activatableClassId
0x180015b21  mov     rbx, instance
0x180015b24  mov     activatableClassId, instance; this
0x180015b27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180015b2c  lea     instance, [rsp+28h+arg_8]
0x180015b31  mov     qword ptr [rbx], 0
0x180015b38  mov     activatableClassId, rdi
0x180015b3b  mov     [rsp+28h+arg_8], 0
0x180015b44  call    cs:__imp_RoActivateInstance
0x180015b4a  mov     edi, eax
0x180015b4c  test    eax, eax
0x180015b4e  js      short loc_180015B9F
0x180015b50  mov     r8d, 10h; Size
0x180015b56  lea     instance, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180015b5d  lea     activatableClassId, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x180015b64  call    memcmp_0
0x180015b69  mov     activatableClassId, [rsp+28h+arg_8]
0x180015b6e  test    eax, eax
0x180015b70  jnz     short loc_180015B77
0x180015b72  mov     [rbx], activatableClassId
0x180015b75  jmp     short loc_180015B9F
0x180015b77  mov     rax, [activatableClassId]
0x180015b7a  lea     instance, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x180015b81  mov     r8, rbx
0x180015b84  mov     rax, [rax]
0x180015b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b8c  mov     activatableClassId, [rsp+28h+arg_8]
0x180015b91  mov     edi, eax
0x180015b93  mov     rax, [activatableClassId]
0x180015b96  mov     rax, [rax+10h]
0x180015b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b9f  mov     rbx, [rsp+28h+arg_0]
0x180015ba4  mov     eax, edi
0x180015ba6  add     rsp, 20h
0x180015baa  pop     rdi
0x180015bab  retn
```
