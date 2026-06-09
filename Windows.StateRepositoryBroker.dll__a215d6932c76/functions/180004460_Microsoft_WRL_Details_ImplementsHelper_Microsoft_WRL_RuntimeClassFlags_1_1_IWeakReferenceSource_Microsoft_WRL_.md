# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x180004460`
- end: `0x18000449f`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `63`
- prototype: `int __fastcall(__int64, const struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005a20`
- `0x1800071d0`
- `0x180007720`

## callees

- `0x180004460`
- `0x1800045dc`
- `0x18000532c`

## pseudocode

```c
int __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(
        __int64 a1,
        const struct _GUID *a2)
{
  void **v2; // r8
  __int64 v3; // r9
  const struct _GUID *v4; // r10
  int result; // eax

  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000038_0000_0000_c000_000000000046) )
  {
    *v2 = (void *)v3;
    return 0;
  }
  else
  {
    result = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v3 + 8), v4, v2);
    if ( result == -2147467262 )
      return -2147467262;
  }
  return result;
}

```

## disassembly

```asm
0x180004460  sub     rsp, 28h
0x180004464  mov     r10, rdx
0x180004467  mov     r9, rcx
0x18000446a  mov     rcx, r10; struct _GUID *
0x18000446d  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046; struct _GUID *
0x180004474  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180004479  test    eax, eax
0x18000447b  jz      short loc_180004484
0x18000447d  mov     [r8], r9
0x180004480  xor     eax, eax
0x180004482  jmp     short loc_18000449A
0x180004484  lea     rcx, [r9+8]; this
0x180004488  mov     rdx, r10; struct _GUID *
0x18000448b  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x180004490  mov     ecx, 80004002h
0x180004495  cmp     eax, ecx
0x180004497  cmovz   eax, ecx
0x18000449a  add     rsp, 28h
0x18000449e  retn
```
