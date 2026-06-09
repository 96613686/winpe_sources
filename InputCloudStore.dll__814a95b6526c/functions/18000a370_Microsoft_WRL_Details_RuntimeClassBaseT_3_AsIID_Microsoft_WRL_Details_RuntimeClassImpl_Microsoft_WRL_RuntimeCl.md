# Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)

- ea: `0x18000a370`
- end: `0x18000a439`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `201`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000cce8`
- `0x180020660`

## callees

- `0x180008634`
- `0x180008ad8`
- `0x18000a370`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rcx
  void **v8; // r8
  void *v9; // r9
  int CanCastTo; // ebx
  __int64 v11; // rcx
  __int64 v12; // r9
  const struct _GUID *v13; // r10

  *a3 = 0;
  if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    && !(unsigned int)InlineIsEqualGUID(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    if ( (unsigned int)InlineIsEqualGUID(v6, &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da)
      || (unsigned int)InlineIsEqualGUID(v7, &GUID_00000038_0000_0000_c000_000000000046) )
    {
      *v8 = v9;
      CanCastTo = 0;
    }
    else
    {
      if ( (unsigned int)InlineIsEqualGUID(v11, &GUID_905a0fef_bc53_11df_8c49_001e4fc686da) )
      {
        *v8 = (void *)v12;
        CanCastTo = 0;
      }
      else
      {
        CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v12 + 8), v13, v8);
        if ( CanCastTo == -2147467262 )
          CanCastTo = -2147467262;
      }
      if ( CanCastTo < 0 )
        return (unsigned int)CanCastTo;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)*v8 + 8LL))(*v8);
    return (unsigned int)CanCastTo;
  }
  *v4 = v5;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18000a370  push    rbx
0x18000a372  sub     rsp, 20h
0x18000a376  mov     r10, rdx
0x18000a379  mov     r9, rcx
0x18000a37c  mov     qword ptr [r8], 0
0x18000a383  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a38a  mov     rcx, r10
0x18000a38d  call    InlineIsEqualGUID
0x18000a392  test    eax, eax
0x18000a394  jnz     loc_18000A41F
0x18000a39a  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18000a3a1  call    InlineIsEqualGUID
0x18000a3a6  test    eax, eax
0x18000a3a8  jnz     short loc_18000A41F
0x18000a3aa  lea     rdx, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da
0x18000a3b1  call    InlineIsEqualGUID
0x18000a3b6  test    eax, eax
0x18000a3b8  jz      short loc_18000A3C1
0x18000a3ba  mov     [r8], r9
0x18000a3bd  xor     ebx, ebx
0x18000a3bf  jmp     short loc_18000A40C
0x18000a3c1  add     r9, 8
0x18000a3c5  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x18000a3cc  call    InlineIsEqualGUID
0x18000a3d1  test    eax, eax
0x18000a3d3  jnz     short loc_18000A3BA
0x18000a3d5  add     r9, 8
0x18000a3d9  lea     rdx, _GUID_905a0fef_bc53_11df_8c49_001e4fc686da
0x18000a3e0  call    InlineIsEqualGUID
0x18000a3e5  test    eax, eax
0x18000a3e7  jz      short loc_18000A3F0
0x18000a3e9  mov     [r8], r9
0x18000a3ec  xor     ebx, ebx
0x18000a3ee  jmp     short loc_18000A408
0x18000a3f0  lea     rcx, [r9+8]; this
0x18000a3f4  mov     rdx, r10; struct _GUID *
0x18000a3f7  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x18000a3fc  mov     ebx, eax
0x18000a3fe  mov     eax, 80004002h
0x18000a403  cmp     ebx, eax
0x18000a405  cmovz   ebx, eax
0x18000a408  test    ebx, ebx
0x18000a40a  js      short loc_18000A41B
0x18000a40c  mov     rcx, [r8]
0x18000a40f  mov     rdx, [rcx]
0x18000a412  mov     rax, [rdx+8]
0x18000a416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41b  mov     eax, ebx
0x18000a41d  jmp     short loc_18000A433
0x18000a41f  mov     [r8], r9
0x18000a422  mov     rax, [r9]
0x18000a425  mov     rcx, r9
0x18000a428  mov     rax, [rax+8]
0x18000a42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a431  xor     eax, eax
0x18000a433  add     rsp, 20h
0x18000a437  pop     rbx
0x18000a438  retn
```
