# Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,ce::WrappedPropVariant,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &>(utl::unordered_map<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,ce::WrappedPropVariant,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,tagPROPVARIANT const *)

- ea: `0x180025b34`
- end: `0x180025c43`
- name: `??$TSetPropertyValue@V?$unordered_map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@@utl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@WalletItem@Wallet@@QEAAJAEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@@utl@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@PEBUtagPROPVARIANT@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const PROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180028720`

## callees

- `0x18000d620`
- `0x180012e78`
- `0x1800136dc`
- `0x180025b34`
- `0x180025d28`
- `0x180025d54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025b8a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025c2e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025b8a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180025c2e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025b97`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025c1e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025b97`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180025c1e`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::TSetPropertyValue<utl::unordered_map<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,ce::WrappedPropVariant,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> &>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const PROPVARIANT *a4)
{
  __int64 *v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // rbx
  HRESULT v11; // eax
  __int64 v12; // rax
  char *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  HRESULT v16; // eax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v19; // [rsp+30h] [rbp-28h]
  _QWORD v20[2]; // [rsp+38h] [rbp-20h] BYREF
  char v21; // [rsp+48h] [rbp-10h]
  __int64 v22; // [rsp+90h] [rbp+38h] BYREF

  v22 = a1;
  v7 = (__int64 *)utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_FindFirstFind,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
                    a2,
                    &v22,
                    a3);
  if ( a4 )
  {
    v10 = *v7;
    v9 = 0;
    if ( (*(_WORD *)a4 & 0x4000) != 0 )
      __fastfail(5u);
    if ( v10 == a2 )
    {
      *(_OWORD *)pvar = 0;
      v19 = 0;
      v12 = utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>,0>::_NewNodeConstruct<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> &,ce::WrappedPropVariant &>(
              v8,
              a3,
              pvar);
      v13 = (char *)v12;
      if ( v12 )
      {
        utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>,0>::_FindInsertPos(
          a2,
          v20,
          v12 + 24);
        if ( v21 )
        {
          utl::_ContainerBase<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>>::_DeleteNode<utl::_HashNode<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>>(
            v15,
            v13);
          v14 = v20[0];
        }
        else
        {
          v14 = *(_QWORD *)utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::_InsertAt(
                             a2,
                             &v22,
                             v20,
                             v13);
        }
      }
      else
      {
        v14 = 0;
      }
      if ( v14 )
      {
        v16 = PropVariantCopy((PROPVARIANT *)(v14 + 56), a4);
        if ( v16 < 0 )
          v9 = v16;
      }
      else
      {
        v9 = -2147024882;
      }
      PropVariantClear(pvar);
    }
    else
    {
      PropVariantClear((PROPVARIANT *)(v10 + 56));
      v11 = PropVariantCopy((PROPVARIANT *)(v10 + 56), a4);
      if ( v11 < 0 )
        return (unsigned int)v11;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v9;
}

```

## disassembly

```asm
0x180025b34  mov     [rsp-30h+arg_0], rcx
0x180025b39  push    rbp
0x180025b3a  push    rbx
0x180025b3b  push    rsi
0x180025b3c  push    rdi
0x180025b3d  push    r14
0x180025b3f  push    r15
0x180025b41  mov     rbp, rsp
0x180025b44  sub     rsp, 58h
0x180025b48  mov     rsi, rdx
0x180025b4b  mov     r14, r9
0x180025b4e  mov     rcx, rsi
0x180025b51  lea     rdx, [rbp+arg_0]
0x180025b55  mov     r15, r8
0x180025b58  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_FindFirstFind,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180025b5d  test    r14, r14
0x180025b60  jnz     short loc_180025B6C
0x180025b62  mov     edi, 80004003h
0x180025b67  jmp     loc_180025C34
0x180025b6c  mov     rbx, [rax]
0x180025b6f  xor     edi, edi
0x180025b71  mov     eax, 4000h
0x180025b76  test    [r14], ax
0x180025b7a  jz      short loc_180025B81
0x180025b7c  lea     ecx, [rdi+5]
0x180025b7f  int     29h; Win8: RtlFailFast(ecx)
0x180025b81  cmp     rbx, rsi
0x180025b84  jz      short loc_180025BAC
0x180025b86  lea     rcx, [rbx+38h]; pvar
0x180025b8a  call    cs:__imp_PropVariantClear
0x180025b90  mov     rdx, r14; pvarSrc
0x180025b93  lea     rcx, [rbx+38h]; pvarDest
0x180025b97  call    cs:__imp_PropVariantCopy
0x180025b9d  test    eax, eax
0x180025b9f  jns     loc_180025C34
0x180025ba5  mov     edi, eax
0x180025ba7  jmp     loc_180025C34
0x180025bac  xorps   xmm0, xmm0
0x180025baf  lea     r8, [rbp+pvar]
0x180025bb3  xor     eax, eax
0x180025bb5  mov     rdx, r15
0x180025bb8  movups  xmmword ptr [rbp+pvar], xmm0
0x180025bbc  mov     [rbp+var_28], rax
0x180025bc0  call    ??$_NewNodeConstruct@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAVWrappedPropVariant@ce@@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@$0A@@utl@@AEAAPEAU?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@1@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@AEAVWrappedPropVariant@ce@@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>,0>::_NewNodeConstruct<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ce::WrappedPropVariant &>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ce::WrappedPropVariant &)
0x180025bc5  mov     rbx, rax
0x180025bc8  test    rax, rax
0x180025bcb  jnz     short loc_180025BD1
0x180025bcd  xor     ecx, ecx
0x180025bcf  jmp     short loc_180025C0B
0x180025bd1  lea     r8, [rax+18h]
0x180025bd5  mov     rcx, rsi
0x180025bd8  lea     rdx, [rbp+var_20]
0x180025bdc  call    ?_FindInsertPos@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@$0A@@utl@@AEAA?AU_InsertPosResult@12@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>,0>::_FindInsertPos(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180025be1  cmp     [rbp+var_10], dil
0x180025be5  jz      short loc_180025BF5
0x180025be7  mov     rdx, rbx
0x180025bea  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>>::_DeleteNode<utl::_HashNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>>(utl::_HashNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>> *)
0x180025bef  mov     rcx, [rbp+var_20]
0x180025bf3  jmp     short loc_180025C0B
0x180025bf5  mov     r9, rbx
0x180025bf8  lea     r8, [rbp+var_20]
0x180025bfc  lea     rdx, [rbp+arg_0]
0x180025c00  mov     rcx, rsi
0x180025c03  call    ?_InsertAt@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@AEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@@2@AEBU_InsertPosResult@12@PEAU?$_HashNode@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_InsertAt(utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::_InsertPosResult const &,utl::_HashNode<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *)
0x180025c08  mov     rcx, [rax]
0x180025c0b  test    rcx, rcx
0x180025c0e  jnz     short loc_180025C17
0x180025c10  mov     edi, 8007000Eh
0x180025c15  jmp     short loc_180025C2A
0x180025c17  add     rcx, 38h ; '8'; pvarDest
0x180025c1b  mov     rdx, r14; pvarSrc
0x180025c1e  call    cs:__imp_PropVariantCopy
0x180025c24  test    eax, eax
0x180025c26  jns     short loc_180025C2A
0x180025c28  mov     edi, eax
0x180025c2a  lea     rcx, [rbp+pvar]; pvar
0x180025c2e  call    cs:__imp_PropVariantClear
0x180025c34  mov     eax, edi
0x180025c36  add     rsp, 58h
0x180025c3a  pop     r15
0x180025c3c  pop     r14
0x180025c3e  pop     rdi
0x180025c3f  pop     rsi
0x180025c40  pop     rbx
0x180025c41  pop     rbp
0x180025c42  retn
```
