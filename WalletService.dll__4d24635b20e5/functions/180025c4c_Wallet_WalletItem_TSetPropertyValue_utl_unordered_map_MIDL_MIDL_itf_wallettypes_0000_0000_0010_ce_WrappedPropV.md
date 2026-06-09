# Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT const *)

- ea: `0x180025c4c`
- end: `0x180025d21`
- name: `??$TSetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEAAJAEAV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBUtagPROPVARIANT@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, __int64, int, const PROPVARIANT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027038`
- `0x1800283c4`
- `0x180028ba0`

## callees

- `0x1800172b0`
- `0x1800210d4`
- `0x180025c4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025cab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025d0c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025cab`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025d0c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025cb7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025cfc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025cb7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025cfc`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
        __int64 a1,
        __int64 a2,
        int a3,
        const PROPVARIANT *a4)
{
  unsigned int v6; // edi
  PROPVARIANT *v7; // rbx
  HRESULT v8; // eax
  __int64 v9; // rcx
  HRESULT v10; // eax
  _BYTE v12[16]; // [rsp+20h] [rbp-30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h]
  __int64 v15; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF

  v16 = a3;
  v15 = a1;
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(
    a2,
    &v15,
    &v16);
  if ( a4 )
  {
    v6 = 0;
    if ( (*(_WORD *)a4 & 0x4000) != 0 )
      __fastfail(5u);
    if ( v15 == a2 )
    {
      v14 = 0;
      *(_OWORD *)pvar = 0;
      v9 = *(_QWORD *)utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::emplace<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 &,ce::WrappedPropVariant &,0>(
                        a2,
                        v12,
                        &v16,
                        pvar);
      if ( v9 )
      {
        v10 = PropVariantCopy((PROPVARIANT *)(v9 + 32), a4);
        if ( v10 < 0 )
          v6 = v10;
      }
      else
      {
        v6 = -2147024882;
      }
      PropVariantClear(pvar);
    }
    else
    {
      v7 = (PROPVARIANT *)(v15 + 32);
      PropVariantClear((PROPVARIANT *)(v15 + 32));
      v8 = PropVariantCopy(v7, a4);
      if ( v8 < 0 )
        return (unsigned int)v8;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v6;
}

```

## disassembly

```asm
0x180025c4c  mov     [rsp-18h+arg_8], rbx
0x180025c51  mov     [rsp-18h+arg_10], r8d
0x180025c56  mov     [rsp-18h+arg_0], rcx
0x180025c5b  push    rbp
0x180025c5c  push    rsi
0x180025c5d  push    rdi
0x180025c5e  mov     rbp, rsp
0x180025c61  sub     rsp, 50h
0x180025c65  mov     rbx, rdx
0x180025c68  lea     r8, [rbp+arg_10]
0x180025c6c  mov     rcx, rbx
0x180025c6f  lea     rdx, [rbp+arg_0]
0x180025c73  mov     rsi, r9
0x180025c76  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x180025c7b  test    rsi, rsi
0x180025c7e  jnz     short loc_180025C8A
0x180025c80  mov     edi, 80004003h
0x180025c85  jmp     loc_180025D12
0x180025c8a  xor     edi, edi
0x180025c8c  mov     eax, 4000h
0x180025c91  test    [rsi], ax
0x180025c94  jz      short loc_180025C9B
0x180025c96  lea     ecx, [rdi+5]
0x180025c99  int     29h; Win8: RtlFailFast(ecx)
0x180025c9b  mov     rax, [rbp+arg_0]
0x180025c9f  cmp     rax, rbx
0x180025ca2  jz      short loc_180025CC5
0x180025ca4  lea     rbx, [rax+20h]
0x180025ca8  mov     rcx, rbx; pvar
0x180025cab  call    cs:__imp_PropVariantClear
0x180025cb1  mov     rdx, rsi; pvarSrc
0x180025cb4  mov     rcx, rbx; pvarDest
0x180025cb7  call    cs:__imp_PropVariantCopy
0x180025cbd  test    eax, eax
0x180025cbf  jns     short loc_180025D12
0x180025cc1  mov     edi, eax
0x180025cc3  jmp     short loc_180025D12
0x180025cc5  xorps   xmm0, xmm0
0x180025cc8  lea     r9, [rbp+pvar]
0x180025ccc  xor     eax, eax
0x180025cce  lea     r8, [rbp+arg_10]
0x180025cd2  lea     rdx, [rbp+var_30]
0x180025cd6  mov     [rbp+var_10], rax
0x180025cda  mov     rcx, rbx
0x180025cdd  movups  xmmword ptr [rbp+pvar], xmm0
0x180025ce1  call    ??$emplace@AEAW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAVWrappedPropVariant@ce@@$0A@@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@utl@@_N@1@AEAW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAVWrappedPropVariant@ce@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::emplace<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 &,ce::WrappedPropVariant &,0>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 &,ce::WrappedPropVariant &)
0x180025ce6  mov     rcx, [rax]
0x180025ce9  test    rcx, rcx
0x180025cec  jnz     short loc_180025CF5
0x180025cee  mov     edi, 8007000Eh
0x180025cf3  jmp     short loc_180025D08
0x180025cf5  add     rcx, 20h ; ' '; pvarDest
0x180025cf9  mov     rdx, rsi; pvarSrc
0x180025cfc  call    cs:__imp_PropVariantCopy
0x180025d02  test    eax, eax
0x180025d04  jns     short loc_180025D08
0x180025d06  mov     edi, eax
0x180025d08  lea     rcx, [rbp+pvar]; pvar
0x180025d0c  call    cs:__imp_PropVariantClear
0x180025d12  mov     rbx, [rsp+50h+arg_8]
0x180025d17  mov     eax, edi
0x180025d19  add     rsp, 50h
0x180025d1d  pop     rdi
0x180025d1e  pop     rsi
0x180025d1f  pop     rbp
0x180025d20  retn
```
