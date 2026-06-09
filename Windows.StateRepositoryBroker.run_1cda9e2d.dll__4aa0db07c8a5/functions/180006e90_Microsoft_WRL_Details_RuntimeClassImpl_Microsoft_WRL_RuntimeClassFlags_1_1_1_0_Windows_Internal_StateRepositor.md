# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>(void)

- ea: `0x180006e90`
- end: `0x180006ebb`
- name: `??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIApplicationResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `43`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006ec4`
- `0x180006f60`
- `0x1800074c4`

## callees

- `0x18000539c`
- `0x180005d70`
- `0x180006e90`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>(
        __int64 a1,
        volatile int *a2)
{
  __int64 v3; // rcx

  v3 = *(_QWORD *)(a1 + 56);
  if ( v3 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(
      2 * v3,
      a2);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 40));
}

```

## disassembly

```asm
0x180006e90  push    rbx
0x180006e92  sub     rsp, 20h
0x180006e96  mov     rbx, rcx
0x180006e99  mov     rcx, [rcx+38h]
0x180006e9d  test    rcx, rcx
0x180006ea0  jns     short loc_180006EAB
0x180006ea2  add     rcx, rcx
0x180006ea5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180006eaa  nop
0x180006eab  lea     rcx, [rbx+28h]
0x180006eaf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180006eb4  nop
0x180006eb5  add     rsp, 20h
0x180006eb9  pop     rbx
0x180006eba  retn
```
