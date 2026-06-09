# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::~EffectBase<Microsoft::Internal::UI::Composition::Effects::IBlendEffect>(void)

- ea: `0x180017cbc`
- end: `0x180017ce4`
- name: `??1?$EffectBase@UIBlendEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@UEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017c8c`

## callees

- `0x180017cec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017cc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017cc9`

## pseudocode

```c
__int64 __fastcall Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::~EffectBase<Microsoft::Internal::UI::Composition::Effects::IBlendEffect>(
        __int64 a1)
{
  WindowsDeleteString(*(HSTRING *)(a1 + 56));
  *(_QWORD *)(a1 + 56) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IBlendEffect>(a1);
}

```

## disassembly

```asm
0x180017cbc  push    rbx
0x180017cbe  sub     rsp, 20h
0x180017cc2  mov     rbx, rcx
0x180017cc5  mov     rcx, [rcx+38h]; string
0x180017cc9  call    cs:__imp_WindowsDeleteString
0x180017ccf  mov     rcx, rbx
0x180017cd2  mov     qword ptr [rbx+38h], 0
0x180017cda  add     rsp, 20h
0x180017cde  pop     rbx
0x180017cdf  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIGraphicsEffect@Effects@Graphics@Windows@@UIGraphicsEffectSource@567@UIGraphicsEffectD2D1Interop@567@UIBlendEffect@5Composition@UI@Internal@3@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IBlendEffect>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Graphics::Effects::IGraphicsEffect,Windows::Graphics::Effects::IGraphicsEffectSource,Windows::Graphics::Effects::IGraphicsEffectD2D1Interop,Microsoft::Internal::UI::Composition::Effects::IBlendEffect>(void)
```
