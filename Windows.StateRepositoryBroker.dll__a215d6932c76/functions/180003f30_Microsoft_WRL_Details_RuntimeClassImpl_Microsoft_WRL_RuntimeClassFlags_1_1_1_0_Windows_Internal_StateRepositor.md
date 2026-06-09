# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>(void)

- ea: `0x180003f30`
- end: `0x180003f58`
- name: `??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `40`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004150`

## callees

- `0x180003f30`
- `0x18000539c`
- `0x180005d70`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 56);
  if ( v2 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v2);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 40);
}

```

## disassembly

```asm
0x180003f30  push    rbx
0x180003f32  sub     rsp, 20h
0x180003f36  mov     rbx, rcx
0x180003f39  mov     rcx, [rcx+38h]
0x180003f3d  test    rcx, rcx
0x180003f40  jns     short loc_180003F4A
0x180003f42  add     rcx, rcx
0x180003f45  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180003f4a  lea     rcx, [rbx+28h]
0x180003f4e  add     rsp, 20h
0x180003f52  pop     rbx
0x180003f53  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
