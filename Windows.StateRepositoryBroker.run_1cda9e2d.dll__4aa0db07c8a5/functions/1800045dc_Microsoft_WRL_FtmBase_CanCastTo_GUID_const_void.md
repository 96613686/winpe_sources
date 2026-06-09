# Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)

- ea: `0x1800045dc`
- end: `0x18000461a`
- name: `?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `62`
- prototype: `int(Microsoft::WRL::FtmBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004460`
- `0x1800044a8`
- `0x180004528`
- `0x18000a400`

## callees

- `0x1800045dc`
- `0x18000532c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::FtmBase::CanCastTo(Microsoft::WRL::FtmBase *this, const struct _GUID *a2, void **a3)
{
  const struct _GUID *v3; // rcx
  _QWORD *v4; // r8
  __int64 v5; // r9

  if ( !InlineIsEqualGUID(a2, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90)
    && !InlineIsEqualGUID(v3, &GUID_00000003_0000_0000_c000_000000000046) )
  {
    return 2147500034LL;
  }
  *v4 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800045dc  sub     rsp, 28h
0x1800045e0  mov     r10, rdx
0x1800045e3  mov     r9, rcx
0x1800045e6  mov     rcx, r10; struct _GUID *
0x1800045e9  lea     rdx, _GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90; struct _GUID *
0x1800045f0  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800045f5  test    eax, eax
0x1800045f7  jnz     short loc_180004609
0x1800045f9  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046; struct _GUID *
0x180004600  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004605  test    eax, eax
0x180004607  jz      short loc_180004610
0x180004609  mov     [r8], r9
0x18000460c  xor     eax, eax
0x18000460e  jmp     short loc_180004615
0x180004610  mov     eax, 80004002h
0x180004615  add     rsp, 28h
0x180004619  retn
```
