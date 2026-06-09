# RegistryRegRow::GetValue(uint,tagPROPVARIANT *)

- ea: `0x180028a80`
- end: `0x180028c7f`
- name: `?GetValue@RegistryRegRow@@UEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `511`
- prototype: `int(RegistryRegRow *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008a30`
- `0x180028a80`
- `0x18002b570`
- `0x18002c234`
- `0x18003bfa4`
- `0x18003bfc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028b75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028b75`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180028b8f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180028c3a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180028c54`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180028b8f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180028c3a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180028c54`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028c2c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028c2c`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::GetValue(RegistryRegRow *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int64 v3; // rbx
  __int64 v7; // rsi
  __int64 v8; // rdx
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  const PROPVARIANT *v11; // rdx
  unsigned int Field; // r14d
  __int64 v13; // rax
  HRESULT v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char *v19; // [rsp+50h] [rbp+18h] BYREF

  v3 = a2;
  if ( !a3 )
    return 2147500035LL;
  if ( a2 >= *((_DWORD *)this + 16) )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 7) )
    return 2147807233LL;
  v7 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl'::`2'::impl) )
  {
    v8 = *((_QWORD *)this + 10);
    _m_prefetchw((const void *)(v8 + 4 * v3));
    v9 = *(_DWORD *)(v8 + 4 * v3);
    do
    {
      v10 = v9;
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 4 * v3), v9, v9);
    }
    while ( v10 != v9 );
    if ( v9 )
      goto LABEL_11;
    Field = ReadField(
              *((HKEY *)this + 16),
              *((const unsigned __int16 **)this + 15),
              (const struct tagFieldInfo *)(*(_QWORD *)(*((_QWORD *)this + 7) + 552LL) + 16 * v3),
              a3);
    if ( !Field )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 7) + 540LL) != 2
        || (_DWORD)v3 != 6
        || *((_BYTE *)this + 136) == (_BYTE)Field
        || a3->iVal == -1 )
      {
        AcquireSRWLockExclusive((PSRWLOCK)this + 12);
        v13 = *((_QWORD *)this + 13);
        v19 = (char *)this + 96;
        v14 = PropVariantCopy((PROPVARIANT *)(v13 + 24 * v7), (const PROPVARIANT *)a3);
        if ( v14 >= 0 )
          std::_Atomic_store_4(*((_QWORD *)this + 10) + 4 * v7, 1, 3);
        else
          wil::details::in1diag3::_Log_Hr(retaddr, v15, v16, (const char *)(unsigned int)v14, v17);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
        return Field;
      }
LABEL_28:
      PropVariantClear((PROPVARIANT *)a3);
      return 2147807233LL;
    }
  }
  else
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 9) + 4 * v3) == 1 )
    {
LABEL_11:
      v11 = (const PROPVARIANT *)(*((_QWORD *)this + 13) + 24 * v3);
      if ( *(_WORD *)v11 )
        return (unsigned int)PropVariantCopy((PROPVARIANT *)a3, v11);
      else
        return 1;
    }
    Field = ReadField(
              *((HKEY *)this + 16),
              *((const unsigned __int16 **)this + 15),
              (const struct tagFieldInfo *)(*(_QWORD *)(*((_QWORD *)this + 7) + 552LL) + 16 * v3),
              a3);
    if ( !Field )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 7) + 540LL) != 2
        || (_DWORD)v3 != 6
        || !*((_BYTE *)this + 136)
        || a3->iVal == -1 )
      {
        if ( PropVariantCopy((PROPVARIANT *)(*((_QWORD *)this + 13) + 24 * v3), (const PROPVARIANT *)a3) >= 0 )
          *(_DWORD *)(*((_QWORD *)this + 9) + 4 * v3) = 1;
        return Field;
      }
      goto LABEL_28;
    }
  }
  return Field;
}

```

## disassembly

```asm
0x180028a80  mov     [rsp+arg_0], rbx
0x180028a85  mov     [rsp+arg_8], rbp
0x180028a8a  push    rsi
0x180028a8b  push    rdi
0x180028a8c  push    r14; int
0x180028a8e  sub     rsp, 20h
0x180028a92  mov     ebx, edx
0x180028a94  mov     rbp, r8
0x180028a97  mov     rdi, rcx
0x180028a9a  test    r8, r8
0x180028a9d  jnz     short loc_180028AA9
0x180028a9f  mov     eax, 80004003h
0x180028aa4  jmp     loc_180028C6C
0x180028aa9  cmp     ebx, [rcx+40h]
0x180028aac  jb      short loc_180028AB8
0x180028aae  mov     eax, 80070057h
0x180028ab3  jmp     loc_180028C6C
0x180028ab8  cmp     qword ptr [rcx+38h], 0
0x180028abd  jnz     short loc_180028AC9
0x180028abf  mov     eax, 8004F001h
0x180028ac4  jmp     loc_180028C6C
0x180028ac9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl(void)'::`2'::impl
0x180028ad0  mov     rsi, rbx
0x180028ad3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(void)
0x180028ad8  test    al, al
0x180028ada  jz      loc_180028BCD
0x180028ae0  mov     rdx, [rdi+50h]
0x180028ae4  prefetchw byte ptr [rdx+rbx*4]
0x180028ae8  mov     eax, [rdx+rbx*4]
0x180028aeb  mov     ecx, eax
0x180028aed  lock cmpxchg [rdx+rbx*4], ecx
0x180028af2  jnz     short loc_180028AEB
0x180028af4  test    eax, eax
0x180028af6  jz      short loc_180028B18
0x180028af8  mov     rax, [rdi+68h]
0x180028afc  lea     rcx, [rbx+rbx*2]
0x180028b00  lea     rdx, [rax+rcx*8]; pvarSrc
0x180028b04  xor     eax, eax
0x180028b06  cmp     ax, [rdx]
0x180028b09  jnz     loc_180028C37
0x180028b0f  lea     r14d, [rax+1]
0x180028b13  jmp     loc_180028C69
0x180028b18  mov     rax, [rdi+38h]
0x180028b1c  mov     r8, rsi
0x180028b1f  mov     rdx, [rdi+78h]; unsigned __int16 *
0x180028b23  mov     r9, rbp; struct tagPROPVARIANT *
0x180028b26  mov     rcx, [rdi+80h]; HKEY
0x180028b2d  shl     r8, 4
0x180028b31  add     r8, [rax+228h]; struct tagFieldInfo *
0x180028b38  call    ?ReadField@@YAJPEAUHKEY__@@PEBGAEBUtagFieldInfo@@AEAUtagPROPVARIANT@@@Z; ReadField(HKEY__ *,ushort const *,tagFieldInfo const &,tagPROPVARIANT &)
0x180028b3d  mov     r14d, eax
0x180028b40  test    eax, eax
0x180028b42  jnz     loc_180028C69
0x180028b48  mov     rax, [rdi+38h]
0x180028b4c  cmp     dword ptr [rax+21Ch], 2
0x180028b53  jnz     short loc_180028B6E
0x180028b55  cmp     ebx, 6
0x180028b58  jnz     short loc_180028B6E
0x180028b5a  cmp     [rdi+88h], r14b
0x180028b61  jz      short loc_180028B6E
0x180028b63  cmp     word ptr [rbp+8], 0FFFFh
0x180028b68  jnz     loc_180028C29
0x180028b6e  lea     rbx, [rdi+60h]
0x180028b72  mov     rcx, rbx; SRWLock
0x180028b75  call    cs:__imp_AcquireSRWLockExclusive
0x180028b7b  mov     rax, [rdi+68h]
0x180028b7f  lea     rcx, [rsi+rsi*2]
0x180028b83  mov     rdx, rbp; pvarSrc
0x180028b86  mov     [rsp+38h+arg_10], rbx
0x180028b8b  lea     rcx, [rax+rcx*8]; pvarDest
0x180028b8f  call    cs:__imp_PropVariantCopy
0x180028b95  test    eax, eax
0x180028b97  jns     short loc_180028BA8
0x180028b99  mov     rcx, [rsp+38h]; this
0x180028b9e  mov     r9d, eax; char *
0x180028ba1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028ba6  jmp     short loc_180028BBE
0x180028ba8  mov     rax, [rdi+50h]
0x180028bac  mov     edx, 1
0x180028bb1  lea     rcx, [rax+rsi*4]
0x180028bb5  lea     r8d, [rdx+2]
0x180028bb9  call    ?_Atomic_store_4@std@@YAXPECKKW4memory_order@1@@Z; std::_Atomic_store_4(ulong volatile *,ulong,std::memory_order)
0x180028bbe  lea     rcx, [rsp+38h+arg_10]
0x180028bc3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028bc8  jmp     loc_180028C69
0x180028bcd  mov     rax, [rdi+48h]
0x180028bd1  cmp     dword ptr [rax+rbx*4], 1
0x180028bd5  jz      loc_180028AF8
0x180028bdb  mov     rax, [rdi+38h]
0x180028bdf  mov     r8, rsi
0x180028be2  mov     rdx, [rdi+78h]; unsigned __int16 *
0x180028be6  mov     r9, rbp; struct tagPROPVARIANT *
0x180028be9  mov     rcx, [rdi+80h]; HKEY
0x180028bf0  shl     r8, 4
0x180028bf4  add     r8, [rax+228h]; struct tagFieldInfo *
0x180028bfb  call    ?ReadField@@YAJPEAUHKEY__@@PEBGAEBUtagFieldInfo@@AEAUtagPROPVARIANT@@@Z; ReadField(HKEY__ *,ushort const *,tagFieldInfo const &,tagPROPVARIANT &)
0x180028c00  mov     r14d, eax
0x180028c03  test    eax, eax
0x180028c05  jnz     short loc_180028C69
0x180028c07  mov     rax, [rdi+38h]
0x180028c0b  cmp     dword ptr [rax+21Ch], 2
0x180028c12  jnz     short loc_180028C45
0x180028c14  cmp     ebx, 6
0x180028c17  jnz     short loc_180028C45
0x180028c19  cmp     [rdi+88h], r14b
0x180028c20  jz      short loc_180028C45
0x180028c22  cmp     word ptr [rbp+8], 0FFFFh
0x180028c27  jz      short loc_180028C45
0x180028c29  mov     rcx, rbp; pvar
0x180028c2c  call    cs:__imp_PropVariantClear
0x180028c32  jmp     loc_180028ABF
0x180028c37  mov     rcx, rbp; pvarDest
0x180028c3a  call    cs:__imp_PropVariantCopy
0x180028c40  mov     r14d, eax
0x180028c43  jmp     short loc_180028C69
0x180028c45  mov     rax, [rdi+68h]
0x180028c49  lea     rcx, [rbx+rbx*2]
0x180028c4d  mov     rdx, rbp; pvarSrc
0x180028c50  lea     rcx, [rax+rcx*8]; pvarDest
0x180028c54  call    cs:__imp_PropVariantCopy
0x180028c5a  test    eax, eax
0x180028c5c  js      short loc_180028C69
0x180028c5e  mov     rax, [rdi+48h]
0x180028c62  mov     dword ptr [rax+rbx*4], 1
0x180028c69  mov     eax, r14d
0x180028c6c  mov     rbx, [rsp+38h+arg_0]
0x180028c71  mov     rbp, [rsp+38h+arg_8]
0x180028c76  add     rsp, 20h
0x180028c7a  pop     r14
0x180028c7c  pop     rdi
0x180028c7d  pop     rsi
0x180028c7e  retn
```
