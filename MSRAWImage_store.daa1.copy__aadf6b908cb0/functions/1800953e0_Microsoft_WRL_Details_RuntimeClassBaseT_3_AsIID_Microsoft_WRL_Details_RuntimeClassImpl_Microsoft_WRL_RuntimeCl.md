# Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x1800953e0`
- end: `0x18009547a`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWICBitmapDecoder@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWICBitmapDecoder@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `154`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009583c`
- `0x180096960`

## callees

- `0x1800953e0`
- `0x180095f30`
- `0x1800970ec`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,IWICBitmapDecoder,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // r8
  __int64 v10; // r9
  int CanCastTo; // ebx
  __int64 v12; // r10

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    && !(unsigned int)InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v7, v6)
      || (unsigned int)InlineIsEqualGUID(v8, &GUID_9edde9e7_8dee_47ea_99df_e6faf2ed44bf) )
    {
      *v9 = v10;
      CanCastTo = 0;
    }
    else
    {
      CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::CanCastTo(
                    v10 + 8,
                    v12);
      if ( CanCastTo < 0 )
        return (unsigned int)CanCastTo;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
    return (unsigned int)CanCastTo;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x1800953e0  push    rbx
0x1800953e2  sub     rsp, 20h
0x1800953e6  mov     r10, rdx
0x1800953e9  mov     qword ptr [r8], 0
0x1800953f0  mov     r9, rcx
0x1800953f3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800953fa  mov     rcx, r10
0x1800953fd  call    InlineIsEqualGUID
0x180095402  test    eax, eax
0x180095404  jnz     short loc_18009545F
0x180095406  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18009540d  call    InlineIsEqualGUID
0x180095412  test    eax, eax
0x180095414  jnz     short loc_18009545F
0x180095416  call    InlineIsEqualGUID
0x18009541b  test    eax, eax
0x18009541d  jz      short loc_180095426
0x18009541f  mov     [r8], r9
0x180095422  xor     ebx, ebx
0x180095424  jmp     short loc_18009544C
0x180095426  lea     rdx, _GUID_9edde9e7_8dee_47ea_99df_e6faf2ed44bf
0x18009542d  add     r9, 8
0x180095431  call    InlineIsEqualGUID
0x180095436  test    eax, eax
0x180095438  jnz     short loc_18009541F
0x18009543a  lea     rcx, [r9+8]
0x18009543e  mov     rdx, r10
0x180095441  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180095446  mov     ebx, eax
0x180095448  test    eax, eax
0x18009544a  js      short loc_18009545B
0x18009544c  mov     rcx, [r8]
0x18009544f  mov     rdx, [rcx]
0x180095452  mov     rax, [rdx+8]
0x180095456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009545b  mov     eax, ebx
0x18009545d  jmp     short loc_180095473
0x18009545f  mov     [r8], r9
0x180095462  mov     rcx, r9
0x180095465  mov     rax, [r9]
0x180095468  mov     rax, [rax+8]
0x18009546c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095471  xor     eax, eax
0x180095473  add     rsp, 20h
0x180095477  pop     rbx
0x180095478  retn
```
