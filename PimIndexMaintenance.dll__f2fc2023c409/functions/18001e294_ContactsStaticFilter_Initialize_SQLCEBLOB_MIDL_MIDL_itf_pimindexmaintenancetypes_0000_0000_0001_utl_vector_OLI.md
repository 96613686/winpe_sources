# ContactsStaticFilter::Initialize(_SQLCEBLOB *,__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001,utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)

- ea: `0x18001e294`
- end: `0x18001e41d`
- name: `?Initialize@ContactsStaticFilter@@IEAAJPEAU_SQLCEBLOB@@W4__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001@@PEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e008`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x180003d60`
- `0x180003f90`
- `0x18001e294`
- `0x18001e610`
- `0x18001e70c`
- `0x18001ea18`

## string_xrefs

- `0x18001e2ec`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e311`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e37f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e3f5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`

## pseudocode

```c
__int64 __fastcall ContactsStaticFilter::Initialize(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  void *v4; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  void *v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  int v16; // eax

  v4 = 0;
  if ( a4 && *a4 != a4[1] )
  {
    v9 = operator new(0x18u);
    if ( !v9
      || (v10 = utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v9),
          (v4 = v10) == 0) )
    {
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
        75);
      return 2147942414LL;
    }
    if ( !(unsigned __int8)utl::vector<OLITEMID,utl::allocator<OLITEMID>>::assign(v10, a4) )
    {
      Log_HREvent(
        2147942414LL,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
        76);
      tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(v4);
      return 2147942414LL;
    }
  }
  v12 = *(void **)(a1 + 64);
  if ( v4 != v12 )
  {
    if ( v12 )
      tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(v12);
    *(_QWORD *)(a1 + 64) = v4;
  }
  if ( a2 )
  {
    v13 = StoreFilterBlob::Set((StoreFilterBlob *)(a1 + 48), *(_DWORD *)a2, *(const unsigned __int8 *const *)(a2 + 8));
    v14 = v13;
    if ( v13 < 0 )
    {
      Log_HREvent((unsigned int)v13, 1, "onecoreuap\\private\\base\\inc\\StoreFilterBlob.h", 137);
      v15 = 83;
LABEL_16:
      Log_HREvent(
        v14,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
        v15);
      return v14;
    }
  }
  if ( (a3 & 1) != 0 )
    *(_DWORD *)(a1 + 40) |= 2u;
  if ( (a3 & 4) != 0 )
    *(_DWORD *)(a1 + 40) |= 8u;
  if ( (a3 & 8) != 0 )
    *(_DWORD *)(a1 + 40) |= 0x10u;
  if ( (a3 & 0x10) != 0 )
    *(_DWORD *)(a1 + 40) |= 0x20u;
  if ( (a3 & 0x20) != 0 )
    *(_DWORD *)(a1 + 40) |= 0x40u;
  if ( (a3 & 0x40) != 0 )
    *(_DWORD *)(a1 + 40) |= 0x80u;
  if ( (a3 & 0x100) != 0 )
    *(_DWORD *)(a1 + 40) |= 0x200u;
  v16 = ContactsStaticFilter::SetStoreBitPositions((__int64 *)a1, a3);
  v14 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
      126);
    v15 = 84;
    goto LABEL_16;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e294  push    rbx
0x18001e296  push    rbp
0x18001e297  push    rsi
0x18001e298  push    rdi
0x18001e299  push    r14
0x18001e29b  sub     rsp, 30h
0x18001e29f  xor     ebx, ebx
0x18001e2a1  mov     rbp, r9
0x18001e2a4  mov     esi, r8d
0x18001e2a7  mov     r14, rdx
0x18001e2aa  mov     rdi, rcx
0x18001e2ad  test    r9, r9
0x18001e2b0  jz      short loc_18001E32E
0x18001e2b2  mov     rax, [r9+8]
0x18001e2b6  cmp     [r9], rax
0x18001e2b9  jz      short loc_18001E32E
0x18001e2bb  lea     ecx, [rbx+18h]; Size
0x18001e2be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e2c3  test    rax, rax
0x18001e2c6  jz      short loc_18001E30C
0x18001e2c8  mov     rcx, rax
0x18001e2cb  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18001e2d0  mov     rbx, rax
0x18001e2d3  test    rax, rax
0x18001e2d6  jz      short loc_18001E30C
0x18001e2d8  mov     rdx, rbp
0x18001e2db  mov     rcx, rax
0x18001e2de  call    ?assign@?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<OLITEMID,utl::allocator<OLITEMID>>::assign(utl::vector<OLITEMID,utl::allocator<OLITEMID>> const &)
0x18001e2e3  test    al, al
0x18001e2e5  jnz     short loc_18001E32E
0x18001e2e7  mov     edi, 8007000Eh
0x18001e2ec  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e2f3  mov     ecx, edi
0x18001e2f5  mov     r9d, 4Ch ; 'L'
0x18001e2fb  xor     edx, edx
0x18001e2fd  call    Log_HREvent
0x18001e302  mov     rcx, rbx; Block
0x18001e305  call    ??$_delete@V?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@tlx@@YAXPEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x18001e30a  jmp     short loc_18001E327
0x18001e30c  mov     edi, 8007000Eh
0x18001e311  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e318  mov     ecx, edi
0x18001e31a  mov     r9d, 4Bh ; 'K'
0x18001e320  xor     edx, edx
0x18001e322  call    Log_HREvent
0x18001e327  mov     eax, edi
0x18001e329  jmp     loc_18001E412
0x18001e32e  mov     rcx, [rdi+40h]; Block
0x18001e332  cmp     rbx, rcx
0x18001e335  jz      short loc_18001E345
0x18001e337  test    rcx, rcx
0x18001e33a  jz      short loc_18001E341
0x18001e33c  call    ??$_delete@V?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@tlx@@YAXPEAV?$vector@UOLITEMID@@V?$allocator@UOLITEMID@@@utl@@@utl@@@Z; tlx::_delete<utl::vector<OLITEMID,utl::allocator<OLITEMID>>>(utl::vector<OLITEMID,utl::allocator<OLITEMID>> *)
0x18001e341  mov     [rdi+40h], rbx
0x18001e345  test    r14, r14
0x18001e348  jz      short loc_18001E393
0x18001e34a  mov     r8, [r14+8]; unsigned __int8 *
0x18001e34e  lea     rcx, [rdi+30h]; this
0x18001e352  mov     edx, [r14]; unsigned int
0x18001e355  call    ?Set@StoreFilterBlob@@QEAAJKQEBE@Z; StoreFilterBlob::Set(ulong,uchar const * const)
0x18001e35a  mov     ebx, eax
0x18001e35c  test    eax, eax
0x18001e35e  jns     short loc_18001E393
0x18001e360  mov     ebp, 1
0x18001e365  lea     r8, aOnecoreuapPriv_0; "onecoreuap\\private\\base\\inc\\StoreFi"...
0x18001e36c  mov     edx, ebp
0x18001e36e  mov     r9d, 89h
0x18001e374  mov     ecx, eax
0x18001e376  call    Log_HREvent
0x18001e37b  lea     r9d, [rbp+52h]
0x18001e37f  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e386  mov     edx, ebp
0x18001e388  mov     ecx, ebx
0x18001e38a  call    Log_HREvent
0x18001e38f  mov     eax, ebx
0x18001e391  jmp     short loc_18001E412
0x18001e393  mov     ebp, 1
0x18001e398  test    bpl, sil
0x18001e39b  jz      short loc_18001E3A1
0x18001e39d  or      dword ptr [rdi+28h], 2
0x18001e3a1  test    sil, 4
0x18001e3a5  jz      short loc_18001E3AB
0x18001e3a7  or      dword ptr [rdi+28h], 8
0x18001e3ab  test    sil, 8
0x18001e3af  jz      short loc_18001E3B5
0x18001e3b1  or      dword ptr [rdi+28h], 10h
0x18001e3b5  test    sil, 10h
0x18001e3b9  jz      short loc_18001E3BF
0x18001e3bb  or      dword ptr [rdi+28h], 20h
0x18001e3bf  test    sil, 20h
0x18001e3c3  jz      short loc_18001E3C9
0x18001e3c5  or      dword ptr [rdi+28h], 40h
0x18001e3c9  test    sil, 40h
0x18001e3cd  jz      short loc_18001E3D4
0x18001e3cf  bts     dword ptr [rdi+28h], 7
0x18001e3d4  bt      esi, 8
0x18001e3d8  jnb     short loc_18001E3DF
0x18001e3da  bts     dword ptr [rdi+28h], 9
0x18001e3df  mov     edx, esi
0x18001e3e1  mov     rcx, rdi
0x18001e3e4  call    ?SetStoreBitPositions@ContactsStaticFilter@@AEAAJW4__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001@@@Z; ContactsStaticFilter::SetStoreBitPositions(__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001)
0x18001e3e9  mov     ebx, eax
0x18001e3eb  test    eax, eax
0x18001e3ed  jns     short loc_18001E410
0x18001e3ef  mov     r9d, 7Eh ; '~'
0x18001e3f5  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e3fc  mov     edx, ebp
0x18001e3fe  mov     ecx, eax
0x18001e400  call    Log_HREvent
0x18001e405  mov     r9d, 54h ; 'T'
0x18001e40b  jmp     loc_18001E37F
0x18001e410  xor     eax, eax
0x18001e412  add     rsp, 30h
0x18001e416  pop     r14
0x18001e418  pop     rdi
0x18001e419  pop     rsi
0x18001e41a  pop     rbp
0x18001e41b  pop     rbx
0x18001e41c  retn
```
