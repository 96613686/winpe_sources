# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>(void)

- ea: `0x180006168`
- end: `0x1800061a7`
- name: `??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ`
- size: `63`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800061e0`
- `0x180006220`
- `0x18000f6b8`
- `0x18000fbb8`
- `0x18001004c`
- `0x1800100dc`
- `0x18001036c`
- `0x180011018`

## callees

- `0x180006168`
- `0x180007210`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 v4; // rcx

  v2 = *(_QWORD *)(a1 + 56);
  if ( v2 < 0 )
    result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v2);
  v4 = *(_QWORD *)(a1 + 40);
  if ( v4 )
  {
    *(_QWORD *)(a1 + 40) = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return result;
}

```

## disassembly

```asm
0x180006168  push    rbx
0x18000616a  sub     rsp, 20h
0x18000616e  mov     rbx, rcx
0x180006171  mov     rcx, [rcx+38h]
0x180006175  test    rcx, rcx
0x180006178  jns     short loc_180006183
0x18000617a  add     rcx, rcx
0x18000617d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180006182  nop
0x180006183  mov     rcx, [rbx+28h]
0x180006187  test    rcx, rcx
0x18000618a  jz      short loc_1800061A1
0x18000618c  mov     qword ptr [rbx+28h], 0
0x180006194  mov     rax, [rcx]
0x180006197  mov     rax, [rax+10h]
0x18000619b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a0  nop
0x1800061a1  add     rsp, 20h
0x1800061a5  pop     rbx
0x1800061a6  retn
```
