# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x180095f30`
- end: `0x180095fd0`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIWICComponentInternal@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFTelemetryComponent@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800953e0`

## callees

- `0x180095f30`
- `0x180096010`
- `0x1800970ec`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IWICComponentInternal,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFTelemetryComponent>,Microsoft::WRL::FtmBase>::CanCastTo(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx
  _QWORD *v3; // r8
  __int64 v4; // r11
  __int64 v6; // rcx
  void **v7; // r8
  unsigned int CanCastTo; // r9d
  __int64 v9; // r11
  __int64 v10; // rcx
  __int64 v11; // rcx
  const struct _GUID *v12; // r10

  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000038_0000_0000_c000_000000000046) )
  {
    *v3 = v4;
    return 0;
  }
  else
  {
    if ( (unsigned int)InlineIsEqualGUID(v2, &GUID_6e740908_a17a_4e4c_b1d8_84255e26c971)
      || (unsigned int)InlineIsEqualGUID(v6, &GUID_07915118_45df_442b_8a3f_f7826a6370ab)
      || (unsigned int)InlineIsEqualGUID(v10, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d)
      || (unsigned int)InlineIsEqualGUID(v11, &GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803) )
    {
      *v7 = (void *)v9;
    }
    else
    {
      CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v9 + 8), v12, v7);
      if ( CanCastTo == -2147467262 )
        return (unsigned int)-2147467262;
    }
    return CanCastTo;
  }
}

```

## disassembly

```asm
0x180095f30  sub     rsp, 28h
0x180095f34  mov     r10, rdx
0x180095f37  mov     r11, rcx
0x180095f3a  mov     rcx, r10
0x180095f3d  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x180095f44  call    InlineIsEqualGUID
0x180095f49  xor     r9d, r9d
0x180095f4c  test    eax, eax
0x180095f4e  jz      short loc_180095F57
0x180095f50  mov     [r8], r11
0x180095f53  xor     eax, eax
0x180095f55  jmp     short loc_180095FCA
0x180095f57  lea     rdx, _GUID_6e740908_a17a_4e4c_b1d8_84255e26c971
0x180095f5e  add     r11, 8
0x180095f62  call    InlineIsEqualGUID
0x180095f67  test    eax, eax
0x180095f69  jz      short loc_180095F70
0x180095f6b  mov     [r8], r11
0x180095f6e  jmp     short loc_180095FC7
0x180095f70  lea     rdx, _GUID_07915118_45df_442b_8a3f_f7826a6370ab
0x180095f77  add     r11, 8
0x180095f7b  call    InlineIsEqualGUID
0x180095f80  test    eax, eax
0x180095f82  jnz     short loc_180095F6B
0x180095f84  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x180095f8b  add     r11, 8
0x180095f8f  call    InlineIsEqualGUID
0x180095f94  test    eax, eax
0x180095f96  jnz     short loc_180095F6B
0x180095f98  lea     rdx, _GUID_0b5e1c7e_bd76_46bc_896c_b2edb40dd803
0x180095f9f  add     r11, 8
0x180095fa3  call    InlineIsEqualGUID
0x180095fa8  test    eax, eax
0x180095faa  jnz     short loc_180095F6B
0x180095fac  lea     rcx, [r11+8]; this
0x180095fb0  mov     rdx, r10; struct _GUID *
0x180095fb3  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x180095fb8  mov     r9d, eax
0x180095fbb  mov     eax, 80004002h
0x180095fc0  cmp     r9d, eax
0x180095fc3  cmovz   r9d, eax
0x180095fc7  mov     eax, r9d
0x180095fca  add     rsp, 28h
0x180095fce  retn
```
