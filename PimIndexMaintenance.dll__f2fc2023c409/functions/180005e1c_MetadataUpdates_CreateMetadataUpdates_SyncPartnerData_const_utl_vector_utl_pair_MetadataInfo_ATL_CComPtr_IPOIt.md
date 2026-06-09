# MetadataUpdates::CreateMetadataUpdates(SyncPartnerData const &,utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>> &,tlx::auto_ptr<MetadataUpdates,&tlx::_delete<MetadataUpdates>(MetadataUpdates *)> &)

- ea: `0x180005e1c`
- end: `0x180005f17`
- name: `?CreateMetadataUpdates@MetadataUpdates@@SAJAEBUSyncPartnerData@@AEAV?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAV?$auto_ptr@UMetadataUpdates@@$1??$_delete@UMetadataUpdates@@@tlx@@YAXPEAU1@@Z@tlx@@@Z`
- size: `251`
- prototype: `__int64 __fastcall(__int64, _QWORD *, MetadataUpdates **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000568c`
- `0x180007968`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x180003900`
- `0x180003d38`
- `0x180003db0`
- `0x180004018`
- `0x180004acc`
- `0x180005e1c`

## string_xrefs

- `0x180005eb9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\PimIMService.h`
- `0x180005ef2`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\PimIMService.h`

## pseudocode

```c
__int64 __fastcall MetadataUpdates::CreateMetadataUpdates(__int64 a1, _QWORD *a2, MetadataUpdates **a3)
{
  MetadataUpdates *v6; // rax
  MetadataUpdates *v7; // rax
  __int64 *v8; // rdi
  unsigned int i; // esi
  unsigned __int64 v10; // rcx
  __int64 v11; // rbp
  __int64 v12; // rdx
  MetadataUpdates *v13; // rcx

  v6 = (MetadataUpdates *)operator new(0x38u);
  if ( v6 && (v7 = MetadataUpdates::MetadataUpdates(v6), (v8 = (__int64 *)v7) != 0) )
  {
    SyncPartnerData::operator=(v7, a1);
    for ( i = 0; ; ++i )
    {
      v10 = (__int64)(a2[1] - *a2) >> 6;
      if ( i >= v10 )
        break;
      v11 = ((unsigned __int64)i << 6) + *a2;
      v12 = v8[5];
      if ( v12 == v8[6]
        || !utl::allocator_traits<utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::construct<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(
              v10,
              v12,
              v11) )
      {
        if ( !utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_PushBackOne2<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(
                v8 + 4,
                v11) )
        {
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\PimIMService.h",
            103);
          tlx::_delete<MetadataUpdates>((MetadataUpdates *)v8);
          return 2147942414LL;
        }
      }
      else
      {
        v8[5] += 64;
      }
    }
    v13 = *a3;
    *a3 = (MetadataUpdates *)v8;
    if ( v13 )
      tlx::_delete<MetadataUpdates>(v13);
    return 0;
  }
  else
  {
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\PimIMService.h",
      98);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005e1c  push    rbx
0x180005e1e  push    rbp
0x180005e1f  push    rsi
0x180005e20  push    rdi
0x180005e21  push    r14
0x180005e23  push    r15
0x180005e25  sub     rsp, 38h
0x180005e29  mov     rbx, rcx
0x180005e2c  mov     r14, r8
0x180005e2f  mov     ecx, 38h ; '8'; Size
0x180005e34  mov     r15, rdx
0x180005e37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e3c  test    rax, rax
0x180005e3f  jz      loc_180005EED
0x180005e45  mov     rcx, rax; this
0x180005e48  call    ??0MetadataUpdates@@AEAA@XZ; MetadataUpdates::MetadataUpdates(void)
0x180005e4d  mov     rdi, rax
0x180005e50  test    rax, rax
0x180005e53  jz      loc_180005EED
0x180005e59  mov     rdx, rbx
0x180005e5c  mov     rcx, rax
0x180005e5f  call    ??4SyncPartnerData@@QEAAAEAU0@AEBU0@@Z; SyncPartnerData::operator=(SyncPartnerData const &)
0x180005e64  xor     esi, esi
0x180005e66  mov     rdx, [r15]
0x180005e69  mov     rcx, [r15+8]
0x180005e6d  sub     rcx, rdx
0x180005e70  mov     eax, esi
0x180005e72  sar     rcx, 6
0x180005e76  cmp     rax, rcx
0x180005e79  jnb     short loc_180005ED9
0x180005e7b  shl     rax, 6
0x180005e7f  lea     rbp, [rax+rdx]
0x180005e83  mov     rdx, [rdi+28h]
0x180005e87  cmp     rdx, [rdi+30h]
0x180005e8b  jz      short loc_180005EA0
0x180005e8d  mov     r8, rbp
0x180005e90  call    ??$construct@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@AEBU12@@?$allocator_traits@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@1@PEAU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@1@AEBU31@@Z; utl::allocator_traits<utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::construct<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>> &,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> *,utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &)
0x180005e95  test    al, al
0x180005e97  jz      short loc_180005EA0
0x180005e99  add     qword ptr [rdi+28h], 40h ; '@'
0x180005e9e  jmp     short loc_180005EB0
0x180005ea0  mov     rdx, rbp
0x180005ea3  lea     rcx, [rdi+20h]
0x180005ea7  call    ??$_PushBackOne2@AEBU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@AEAA_NAEBU?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@1@@Z; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::_PushBackOne2<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &>(utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>> const &)
0x180005eac  test    al, al
0x180005eae  jz      short loc_180005EB4
0x180005eb0  inc     esi
0x180005eb2  jmp     short loc_180005E66
0x180005eb4  mov     ebx, 8007000Eh
0x180005eb9  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005ec0  mov     ecx, ebx
0x180005ec2  mov     r9d, 67h ; 'g'
0x180005ec8  xor     edx, edx
0x180005eca  call    Log_HREvent
0x180005ecf  mov     rcx, rdi; Block
0x180005ed2  call    ??$_delete@UMetadataUpdates@@@tlx@@YAXPEAUMetadataUpdates@@@Z; tlx::_delete<MetadataUpdates>(MetadataUpdates *)
0x180005ed7  jmp     short loc_180005F08
0x180005ed9  mov     rcx, [r14]; Block
0x180005edc  mov     [r14], rdi
0x180005edf  test    rcx, rcx
0x180005ee2  jz      short loc_180005EE9
0x180005ee4  call    ??$_delete@UMetadataUpdates@@@tlx@@YAXPEAUMetadataUpdates@@@Z; tlx::_delete<MetadataUpdates>(MetadataUpdates *)
0x180005ee9  xor     eax, eax
0x180005eeb  jmp     short loc_180005F0A
0x180005eed  mov     ebx, 8007000Eh
0x180005ef2  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180005ef9  mov     ecx, ebx
0x180005efb  mov     r9d, 62h ; 'b'
0x180005f01  xor     edx, edx
0x180005f03  call    Log_HREvent
0x180005f08  mov     eax, ebx
0x180005f0a  add     rsp, 38h
0x180005f0e  pop     r15
0x180005f10  pop     r14
0x180005f12  pop     rdi
0x180005f13  pop     rsi
0x180005f14  pop     rbp
0x180005f15  pop     rbx
0x180005f16  retn
```
