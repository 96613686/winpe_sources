# Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x18000ef98`
- end: `0x18000f02f`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012650`

## callees

- `0x18000c584`
- `0x18000ef98`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  unsigned int v3; // ebx
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  const struct _GUID *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9
  const struct _GUID *v10; // rcx
  _QWORD *v11; // r8
  __int64 v12; // r10

  v3 = 0;
  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v4, &GUID_a4ed5c81_76c9_40bd_8be6_b1d90fb20ae7) )
    {
      *v8 = v9;
    }
    else
    {
      if ( !(unsigned int)InlineIsEqualGUID(v7, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
        && !(unsigned int)InlineIsEqualGUID(v10, &GUID_00000003_0000_0000_c000_000000000046) )
      {
        return (unsigned int)-2147467262;
      }
      v9 = v12;
      *v11 = v12;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    return v3;
  }
  *v5 = v6;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x18000ef98  push    rbx
0x18000ef9a  sub     rsp, 20h
0x18000ef9e  mov     r11, rdx
0x18000efa1  mov     r9, rcx
0x18000efa4  xor     ebx, ebx
0x18000efa6  mov     [r8], rbx
0x18000efa9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000efb0  mov     rcx, r11; struct _GUID *
0x18000efb3  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000efb8  test    eax, eax
0x18000efba  jnz     short loc_18000F015
0x18000efbc  lea     rdx, _GUID_a4ed5c81_76c9_40bd_8be6_b1d90fb20ae7; struct _GUID *
0x18000efc3  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000efc8  test    eax, eax
0x18000efca  jz      short loc_18000EFD1
0x18000efcc  mov     [r8], r9
0x18000efcf  jmp     short loc_18000EFFB
0x18000efd1  lea     r10, [r9+8]
0x18000efd5  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x18000efdc  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000efe1  test    eax, eax
0x18000efe3  jnz     short loc_18000EFF5
0x18000efe5  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x18000efec  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000eff1  test    eax, eax
0x18000eff3  jz      short loc_18000F00C
0x18000eff5  mov     r9, r10
0x18000eff8  mov     [r8], r10
0x18000effb  mov     rax, [r9]
0x18000effe  mov     rcx, r9
0x18000f001  mov     rax, [rax+8]
0x18000f005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f00a  jmp     short loc_18000F011
0x18000f00c  mov     ebx, 80004002h
0x18000f011  mov     eax, ebx
0x18000f013  jmp     short loc_18000F029
0x18000f015  mov     [r8], r9
0x18000f018  mov     rax, [r9]
0x18000f01b  mov     rcx, r9
0x18000f01e  mov     rax, [rax+8]
0x18000f022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f027  xor     eax, eax
0x18000f029  add     rsp, 20h
0x18000f02d  pop     rbx
0x18000f02e  retn
```
