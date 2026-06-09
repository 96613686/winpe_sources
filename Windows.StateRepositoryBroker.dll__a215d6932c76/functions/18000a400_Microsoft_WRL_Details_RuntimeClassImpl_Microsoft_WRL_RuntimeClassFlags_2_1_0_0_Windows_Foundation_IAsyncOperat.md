# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a400`
- end: `0x18000a485`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a490`

## callees

- `0x1800045dc`
- `0x18000532c`
- `0x18000a400`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9
  void **v6; // r8
  __int64 v7; // r9
  const struct _GUID *v8; // r10
  unsigned int v9; // ebx
  int CanCastTo; // eax

  *a3 = 0;
  if ( InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046) )
  {
    *v4 = v5;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    return 0;
  }
  if ( InlineIsEqualGUID(v3, &GUID_e521c894_2c26_5946_9e61_2b5e188d01ed) )
  {
    *v6 = (void *)v7;
    v9 = 0;
LABEL_6:
    (*(void (__fastcall **)(void *))(*(_QWORD *)*v6 + 8LL))(*v6);
    return v9;
  }
  CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v7 + 8), v8, v6);
  v9 = -2147467262;
  if ( CanCastTo != -2147467262 )
  {
    v9 = CanCastTo;
    if ( CanCastTo >= 0 )
      goto LABEL_6;
  }
  return v9;
}

```

## disassembly

```asm
0x18000a400  push    rbx
0x18000a402  sub     rsp, 20h
0x18000a406  mov     r10, rdx
0x18000a409  mov     qword ptr [r8], 0
0x18000a410  mov     r9, rcx
0x18000a413  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000a41a  mov     rcx, r10; struct _GUID *
0x18000a41d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000a422  test    eax, eax
0x18000a424  jnz     short loc_18000A469
0x18000a426  lea     rdx, _GUID_e521c894_2c26_5946_9e61_2b5e188d01ed; struct _GUID *
0x18000a42d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000a432  test    eax, eax
0x18000a434  jz      short loc_18000A43D
0x18000a436  mov     [r8], r9
0x18000a439  xor     ebx, ebx
0x18000a43b  jmp     short loc_18000A458
0x18000a43d  lea     rcx, [r9+8]; this
0x18000a441  mov     rdx, r10; struct _GUID *
0x18000a444  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x18000a449  mov     ebx, 80004002h
0x18000a44e  cmp     eax, ebx
0x18000a450  jz      short loc_18000A47D
0x18000a452  mov     ebx, eax
0x18000a454  test    eax, eax
0x18000a456  js      short loc_18000A47D
0x18000a458  mov     rcx, [r8]
0x18000a45b  mov     rax, [rcx]
0x18000a45e  mov     rax, [rax+8]
0x18000a462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a467  jmp     short loc_18000A47D
0x18000a469  mov     [r8], r9
0x18000a46c  mov     rcx, r9
0x18000a46f  mov     rax, [r9]
0x18000a472  mov     rax, [rax+8]
0x18000a476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a47b  xor     ebx, ebx
0x18000a47d  mov     eax, ebx
0x18000a47f  add     rsp, 20h
0x18000a483  pop     rbx
0x18000a484  retn
```
