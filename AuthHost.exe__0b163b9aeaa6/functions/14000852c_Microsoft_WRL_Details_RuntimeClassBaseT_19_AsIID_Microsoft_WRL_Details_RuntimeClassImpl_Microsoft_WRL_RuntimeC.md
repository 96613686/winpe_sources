# Microsoft::WRL::Details::RuntimeClassBaseT<19>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x14000852c`
- end: `0x14000861e`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$0BD@@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b3d0`

## callees

- `0x140005590`
- `0x14000852c`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<19>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r10
  const struct _GUID *v6; // rcx
  const struct _GUID *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r10
  int v10; // ebx
  const struct _GUID *v11; // rcx
  const struct _GUID *v12; // rcx
  __int64 v13; // r10
  const struct _GUID *v14; // rcx
  const struct _GUID *v15; // rcx

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    && !(unsigned int)InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v6, &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da)
      || (unsigned int)InlineIsEqualGUID(v7, &GUID_00000038_0000_0000_c000_000000000046) )
    {
      *v8 = v9;
      v10 = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v11, &GUID_905a0fef_bc53_11df_8c49_001e4fc686da)
        || (unsigned int)InlineIsEqualGUID(v12, &GUID_00000003_0000_0000_c000_000000000046)
        || (unsigned int)InlineIsEqualGUID(v14, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
        || (unsigned int)InlineIsEqualGUID(v15, &GUID_00000003_0000_0000_c000_000000000046) )
      {
        *v8 = v13;
        v10 = 0;
      }
      else
      {
        v10 = -2147467262;
      }
      if ( v10 < 0 )
        return (unsigned int)v10;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
    return (unsigned int)v10;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x14000852c  push    rbx
0x14000852e  sub     rsp, 20h
0x140008532  mov     r9, rdx
0x140008535  mov     r10, rcx
0x140008538  mov     qword ptr [r8], 0
0x14000853f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x140008546  mov     rcx, r9; struct _GUID *
0x140008549  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x14000854e  test    eax, eax
0x140008550  jnz     loc_140008604
0x140008556  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x14000855d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140008562  test    eax, eax
0x140008564  jnz     loc_140008604
0x14000856a  lea     rdx, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da; struct _GUID *
0x140008571  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140008576  test    eax, eax
0x140008578  jz      short loc_140008581
0x14000857a  mov     [r8], r10
0x14000857d  xor     ebx, ebx
0x14000857f  jmp     short loc_1400085F1
0x140008581  add     r10, 8
0x140008585  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046; struct _GUID *
0x14000858c  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140008591  test    eax, eax
0x140008593  jnz     short loc_14000857A
0x140008595  add     r10, 8
0x140008599  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da; struct _GUID *
0x1400085a0  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400085a5  test    eax, eax
0x1400085a7  jz      short loc_1400085B0
0x1400085a9  mov     [r8], r10
0x1400085ac  xor     ebx, ebx
0x1400085ae  jmp     short loc_1400085ED
0x1400085b0  add     r10, 8
0x1400085b4  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x1400085bb  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400085c0  test    eax, eax
0x1400085c2  jnz     short loc_1400085A9
0x1400085c4  add     r10, 8
0x1400085c8  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x1400085cf  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400085d4  test    eax, eax
0x1400085d6  jnz     short loc_1400085A9
0x1400085d8  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x1400085df  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400085e4  test    eax, eax
0x1400085e6  jnz     short loc_1400085A9
0x1400085e8  mov     ebx, 80004002h
0x1400085ed  test    ebx, ebx
0x1400085ef  js      short loc_140008600
0x1400085f1  mov     rcx, [r8]
0x1400085f4  mov     rdx, [rcx]
0x1400085f7  mov     rax, [rdx+8]
0x1400085fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008600  mov     eax, ebx
0x140008602  jmp     short loc_140008618
0x140008604  mov     [r8], r10
0x140008607  mov     rax, [r10]
0x14000860a  mov     rcx, r10
0x14000860d  mov     rax, [rax+8]
0x140008611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008616  xor     eax, eax
0x140008618  add     rsp, 20h
0x14000861c  pop     rbx
0x14000861d  retn
```
