# Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> const &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)

- ea: `0x180025ad4`
- end: `0x180025b2e`
- name: `??$TGetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEBAJAEBV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, __int64, int, PROPVARIANT *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026150`
- `0x180027038`
- `0x180027140`
- `0x180027870`
- `0x180028040`
- `0x1800283c4`

## callees

- `0x180017098`
- `0x180025ad4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025b0d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025b0d`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
        __int64 a1,
        __int64 a2,
        int a3,
        PROPVARIANT *a4)
{
  __int64 v6; // rdx
  HRESULT v7; // eax
  unsigned int v8; // ecx
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF
  int v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = a3;
  v10 = a1;
  v6 = *(_QWORD *)utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_FindFirst<utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_FindFirstFind,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                    a2,
                    &v10,
                    &v11);
  if ( v6 == a2 )
  {
    return (unsigned int)-2143682560;
  }
  else
  {
    v7 = PropVariantCopy(a4, (const PROPVARIANT *)(v6 + 32));
    v8 = 0;
    if ( v7 < 0 )
      return (unsigned int)v7;
  }
  return v8;
}

```

## disassembly

```asm
0x180025ad4  mov     rax, rsp
0x180025ad7  mov     [rax+10h], rbx
0x180025adb  mov     [rax+18h], r8d
0x180025adf  mov     [rax+8], rcx
0x180025ae3  push    rdi
0x180025ae4  sub     rsp, 20h
0x180025ae8  mov     rbx, rdx
0x180025aeb  lea     r8, [rax+18h]
0x180025aef  mov     rcx, rbx
0x180025af2  lea     rdx, [rax+8]
0x180025af6  mov     rdi, r9
0x180025af9  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_FindFirst<utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_FindFirstFind,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x180025afe  mov     rdx, [rax]
0x180025b01  cmp     rdx, rbx
0x180025b04  jz      short loc_180025B1C
0x180025b06  add     rdx, 20h ; ' '; pvarSrc
0x180025b0a  mov     rcx, rdi; pvarDest
0x180025b0d  call    cs:__imp_PropVariantCopy
0x180025b13  xor     ecx, ecx
0x180025b15  test    eax, eax
0x180025b17  cmovs   ecx, eax
0x180025b1a  jmp     short loc_180025B21
0x180025b1c  mov     ecx, 803A0000h
0x180025b21  mov     rbx, [rsp+28h+arg_8]
0x180025b26  mov     eax, ecx
0x180025b28  add     rsp, 20h
0x180025b2c  pop     rdi
0x180025b2d  retn
```
