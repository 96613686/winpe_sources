# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000da60`
- end: `0x14000dadc`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000daf0`

## callees

- `0x14000a8f0`
- `0x14000d46c`
- `0x14000da60`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  _QWORD *v6; // r8
  __int64 v7; // r9
  __int64 v8; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_bd75eebe_e7b5_5af6_8415_a4b9c9045202) )
  {
    *v6 = v7;
    CanCastTo = 0;
LABEL_5:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    return (unsigned int)CanCastTo;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(
                v7 + 8,
                v8);
  if ( CanCastTo >= 0 )
    goto LABEL_5;
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x14000da60  push    rbx
0x14000da62  sub     rsp, 20h
0x14000da66  mov     r10, rdx
0x14000da69  mov     r9, rcx
0x14000da6c  mov     qword ptr [r8], 0
0x14000da73  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000da7a  mov     rcx, r10; struct _GUID *
0x14000da7d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000da82  test    eax, eax
0x14000da84  jnz     short loc_14000DAC0
0x14000da86  lea     rdx, _GUID_bd75eebe_e7b5_5af6_8415_a4b9c9045202; struct _GUID *
0x14000da8d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000da92  test    eax, eax
0x14000da94  jz      short loc_14000DA9D
0x14000da96  mov     [r8], r9
0x14000da99  xor     ebx, ebx
0x14000da9b  jmp     short loc_14000DAAF
0x14000da9d  lea     rcx, [r9+8]
0x14000daa1  mov     rdx, r10
0x14000daa4  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x14000daa9  mov     ebx, eax
0x14000daab  test    eax, eax
0x14000daad  js      short loc_14000DAD4
0x14000daaf  mov     rcx, [r8]
0x14000dab2  mov     rax, [rcx]
0x14000dab5  mov     rax, [rax+8]
0x14000dab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dabe  jmp     short loc_14000DAD4
0x14000dac0  mov     [r8], r9
0x14000dac3  mov     rax, [r9]
0x14000dac6  mov     rcx, r9
0x14000dac9  mov     rax, [rax+8]
0x14000dacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dad2  xor     ebx, ebx
0x14000dad4  mov     eax, ebx
0x14000dad6  add     rsp, 20h
0x14000dada  pop     rbx
0x14000dadb  retn
```
