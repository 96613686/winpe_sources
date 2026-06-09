# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x14000db00`
- end: `0x14000db7c`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000db90`

## callees

- `0x14000a8f0`
- `0x14000d46c`
- `0x14000db00`
- `0x140012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::QueryInterface(
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
  if ( (unsigned int)InlineIsEqualGUID(v3, &GUID_beadb572_f9a3_5e93_b6ca_e311b65933fc) )
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
0x14000db00  push    rbx
0x14000db02  sub     rsp, 20h
0x14000db06  mov     r10, rdx
0x14000db09  mov     r9, rcx
0x14000db0c  mov     qword ptr [r8], 0
0x14000db13  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x14000db1a  mov     rcx, r10; struct _GUID *
0x14000db1d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000db22  test    eax, eax
0x14000db24  jnz     short loc_14000DB60
0x14000db26  lea     rdx, _GUID_beadb572_f9a3_5e93_b6ca_e311b65933fc; struct _GUID *
0x14000db2d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000db32  test    eax, eax
0x14000db34  jz      short loc_14000DB3D
0x14000db36  mov     [r8], r9
0x14000db39  xor     ebx, ebx
0x14000db3b  jmp     short loc_14000DB4F
0x14000db3d  lea     rcx, [r9+8]
0x14000db41  mov     rdx, r10
0x14000db44  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::CanCastTo(_GUID const &,void * *,bool *)
0x14000db49  mov     ebx, eax
0x14000db4b  test    eax, eax
0x14000db4d  js      short loc_14000DB74
0x14000db4f  mov     rcx, [r8]
0x14000db52  mov     rax, [rcx]
0x14000db55  mov     rax, [rax+8]
0x14000db59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db5e  jmp     short loc_14000DB74
0x14000db60  mov     [r8], r9
0x14000db63  mov     rax, [r9]
0x14000db66  mov     rcx, r9
0x14000db69  mov     rax, [rax+8]
0x14000db6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db72  xor     ebx, ebx
0x14000db74  mov     eax, ebx
0x14000db76  add     rsp, 20h
0x14000db7a  pop     rbx
0x14000db7b  retn
```
