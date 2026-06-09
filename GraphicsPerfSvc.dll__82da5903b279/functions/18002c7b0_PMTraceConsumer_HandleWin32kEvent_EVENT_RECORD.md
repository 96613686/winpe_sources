# PMTraceConsumer::HandleWin32kEvent(_EVENT_RECORD *)

- ea: `0x18002c7b0`
- end: `0x18002ccfe`
- name: `?HandleWin32kEvent@PMTraceConsumer@@QEAAXPEAU_EVENT_RECORD@@@Z`
- size: `1358`
- prototype: `void __fastcall(PMTraceConsumer *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18001a580`

## callees

- `0x180003ab0`
- `0x180004b35`
- `0x18000bcc0`
- `0x18000d67c`
- `0x18000e3e4`
- `0x18000fcec`
- `0x180027398`
- `0x18002802c`
- `0x1800284f0`
- `0x180028654`
- `0x180029018`
- `0x18002905c`
- `0x180029130`
- `0x180029764`
- `0x18002c7b0`
- `0x18002cd04`
- `0x18002cd94`
- `0x18002df04`
- `0x18002e250`
- `0x18002e664`

## string_xrefs

- `0x18002c7f9`: `CompositionSurfaceLuid`
- `0x18002cad2`: `CompositionSurfaceLuid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PMTraceConsumer::HandleWin32kEvent(PMTraceConsumer *this, struct _EVENT_RECORD *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rbx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rax
  std::_Ref_count_base *v21; // rcx
  __int64 v22; // rbx
  _QWORD *v23; // rax
  __int64 *Present; // rax
  __int64 v25; // rdi
  __int64 v26; // r12
  __int64 v27; // r13
  _QWORD *v28; // rax
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+68h] [rbp-98h]
  _QWORD v38[4]; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v39; // [rsp+90h] [rbp-70h] BYREF
  void *Src[2]; // [rsp+98h] [rbp-68h]
  size_t Size; // [rsp+A8h] [rbp-58h]
  const wchar_t *v42; // [rsp+B0h] [rbp-50h]
  void *v43[2]; // [rsp+B8h] [rbp-48h]
  size_t v44; // [rsp+C8h] [rbp-38h]
  const wchar_t *v45; // [rsp+D0h] [rbp-30h]
  void *v46[2]; // [rsp+D8h] [rbp-28h]
  size_t v47; // [rsp+E8h] [rbp-18h]
  const wchar_t *v48; // [rsp+F0h] [rbp-10h]
  void *v49[2]; // [rsp+F8h] [rbp-8h]
  size_t v50; // [rsp+108h] [rbp+8h]
  const wchar_t *v51; // [rsp+110h] [rbp+10h]
  void *v52[2]; // [rsp+118h] [rbp+18h]
  size_t v53; // [rsp+128h] [rbp+28h]

  if ( a2->EventHeader.EventDescriptor.Id == 201 )
  {
    v39 = L"CompositionSurfaceLuid";
    *(_OWORD *)Src = 0;
    Size = 0;
    v42 = L"PresentCount";
    *(_OWORD *)v43 = 0;
    v44 = 0;
    v45 = L"BindId";
    *(_OWORD *)v46 = 0;
    v47 = 0;
    v48 = L"DestWidth";
    *(_OWORD *)v49 = 0;
    v50 = 0;
    v51 = L"DestHeight";
    *(_OWORD *)v52 = 0;
    v53 = 0;
    EventMetadata::GetEventData(
      this,
      a2,
      (struct EventDataDesc *)&v39,
      a2->EventHeader.EventDescriptor.Version != 0 ? 5 : 3,
      v29);
    v30 = 0;
    memcpy_0(&v30, Src[1], (unsigned int)Size);
    v34 = 0;
    memcpy_0(&v34, v43[1], (unsigned int)v44);
    v31 = 0;
    memcpy_0(&v31, v46[1], (unsigned int)v47);
    PMTraceConsumer::FindOrCreatePresent(this);
    v22 = v35;
    if ( v35 )
    {
      if ( !*(_BYTE *)(v35 + 167) )
        goto LABEL_39;
      v23 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v32, &v35);
      PMTraceConsumer::RemoveLostPresent(this, v23);
      Present = (__int64 *)PMTraceConsumer::FindOrCreatePresent(this);
      std::shared_ptr<PresentEvent>::operator=(&v35, Present);
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      v22 = v35;
      if ( v35 )
      {
LABEL_39:
        v25 = v30;
        v26 = v34;
        v27 = v31;
        *(_DWORD *)(v22 + 156) = 4;
        *(_BYTE *)(v22 + 167) = 1;
        if ( a2->EventHeader.EventDescriptor.Version )
        {
          LODWORD(v30) = 0;
          memcpy_0(&v30, v49[1], (unsigned int)v50);
          *(_DWORD *)(v22 + 140) = v30;
          LODWORD(v30) = 0;
          memcpy_0(&v30, v52[1], (unsigned int)v53);
          *(_DWORD *)(v22 + 144) = v30;
        }
        v38[0] = v27;
        v38[1] = v26;
        v38[2] = v25;
        v28 = (_QWORD *)std::map<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>>::_Try_emplace<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const &,>(
                          (char *)this + 464,
                          &v32,
                          v38);
        std::shared_ptr<PresentEvent>::operator=(*v28 + 56LL, &v35);
        *(_QWORD *)(v22 + 128) = v25;
        *(_QWORD *)(v22 + 80) = v26;
        *(_QWORD *)(v22 + 88) = v27;
      }
    }
    v21 = v36;
    goto LABEL_43;
  }
  if ( a2->EventHeader.EventDescriptor.Id == 301 )
  {
    v39 = L"CompositionSurfaceLuid";
    *(_OWORD *)Src = 0;
    Size = 0;
    v42 = L"PresentCount";
    *(_OWORD *)v43 = 0;
    v44 = 0;
    v45 = L"BindId";
    *(_OWORD *)v46 = 0;
    v47 = 0;
    v48 = L"NewState";
    *(_OWORD *)v49 = 0;
    v50 = 0;
    EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v39, 4u, v29);
    v30 = 0;
    memcpy_0(&v30, Src[1], (unsigned int)Size);
    v4 = v30;
    LODWORD(v34) = 0;
    memcpy_0(&v34, v43[1], (unsigned int)v44);
    v30 = 0;
    memcpy_0(&v30, v46[1], (unsigned int)v47);
    v5 = v30;
    LODWORD(v30) = 0;
    memcpy_0(&v30, v49[1], (unsigned int)v50);
    v35 = v5;
    v36 = (std::_Ref_count_base *)(unsigned int)v34;
    v37 = v4;
    std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::find(
      (char *)this + 464,
      &v31,
      &v35);
    v6 = v31;
    if ( v31 != *((_QWORD *)this + 58) )
    {
      std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v32, (_QWORD *)(v31 + 56));
      v9 = v8 - 3;
      if ( !v9 )
      {
        v17 = v32;
        if ( *(_QWORD *)(v32 + 112) )
        {
          std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(
            (char *)this + 512,
            &v31);
          if ( v31 == *((_QWORD *)this + 64) )
          {
            std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned __int64 &,std::shared_ptr<PresentEvent> &>(
              (char *)this + 512,
              &v35,
              v18,
              &v32);
            v17 = v32;
          }
          else
          {
            v19 = v31 + 40;
            v20 = *(_QWORD *)(v31 + 40);
            if ( v20 != v17 )
            {
              *(_DWORD *)(v20 + 160) = 2;
              std::shared_ptr<PresentEvent>::operator=(v19, &v32);
            }
          }
        }
        *(_BYTE *)(v17 + 169) = 1;
        if ( (unsigned int)EventMetadata::GetEventData<int>(this, a2) && *(_DWORD *)(v17 + 156) == 4 )
          *(_DWORD *)(v17 + 156) = 3;
        goto LABEL_33;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        v16 = v32;
        if ( !*(_DWORD *)(v32 + 160) && (*(_BYTE *)(v32 + 60) & 2) != 0 )
          *(_DWORD *)(v32 + 160) = 2;
        if ( *(_QWORD *)(v16 + 112) )
          std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::erase((char *)this + 512);
        goto LABEL_33;
      }
      if ( v10 == 2 )
      {
        if ( *((_BYTE *)this + 608) )
        {
          LOBYTE(v7) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
            v7);
        }
        else
        {
          std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(
            (char *)this + 464,
            &v31,
            v6);
        }
        v13 = v32;
        if ( !*(_BYTE *)(v32 + 169) && (!*(_DWORD *)(v32 + 160) || !*(_QWORD *)(v32 + 40)) )
        {
          if ( *((_BYTE *)this + 608) )
          {
            LOBYTE(v11) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
              v11);
            std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(
              (char *)this + 464,
              &v31,
              v6);
          }
          *(_DWORD *)(v13 + 160) = 2;
LABEL_19:
          v15 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v35, &v32);
          PMTraceConsumer::CompletePresent((__int64)this, v15);
          goto LABEL_33;
        }
        if ( !(unsigned __int8)PMTraceConsumer::IsComposedFlipMode(v12, *(unsigned int *)(v32 + 156)) )
        {
          if ( *((_BYTE *)this + 608) )
          {
            LOBYTE(v14) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl'::`2'::impl,
              v14);
            std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(
              (char *)this + 464,
              &v31,
              v6);
          }
          goto LABEL_19;
        }
      }
LABEL_33:
      v21 = v33;
LABEL_43:
      if ( v21 )
        std::_Ref_count_base::_Decref(v21);
    }
  }
}

```

## disassembly

```asm
0x18002c7b0  mov     [rsp-8+arg_10], rbx
0x18002c7b5  push    rbp
0x18002c7b6  push    rsi
0x18002c7b7  push    rdi
0x18002c7b8  push    r12
0x18002c7ba  push    r13
0x18002c7bc  push    r14
0x18002c7be  push    r15
0x18002c7c0  lea     rbp, [rsp-40h]
0x18002c7c5  sub     rsp, 140h
0x18002c7cc  mov     rax, cs:__security_cookie
0x18002c7d3  xor     rax, rsp
0x18002c7d6  mov     [rbp+70h+var_40], rax
0x18002c7da  mov     r15, rdx
0x18002c7dd  mov     r14, rcx
0x18002c7e0  movzx   ecx, word ptr [rdx+28h]
0x18002c7e4  sub     ecx, 0C9h
0x18002c7ea  jz      loc_18002CAD2
0x18002c7f0  cmp     ecx, 64h ; 'd'
0x18002c7f3  jnz     loc_18002CCD7
0x18002c7f9  lea     rax, aCompositionsur; "CompositionSurfaceLuid"
0x18002c800  mov     [rbp+70h+var_E0], rax
0x18002c804  xorps   xmm0, xmm0
0x18002c807  xor     eax, eax
0x18002c809  movups  xmmword ptr [rbp+70h+Src], xmm0
0x18002c80d  mov     [rbp+70h+Size], rax
0x18002c811  lea     rax, aPresentcount; "PresentCount"
0x18002c818  mov     [rbp+70h+var_C0], rax
0x18002c81c  xor     eax, eax
0x18002c81e  movups  xmmword ptr [rbp+70h+var_B8], xmm0
0x18002c822  mov     [rbp+70h+var_A8], rax
0x18002c826  lea     rax, aBindid_0; "BindId"
0x18002c82d  mov     [rbp+70h+var_A0], rax
0x18002c831  xor     eax, eax
0x18002c833  movups  xmmword ptr [rbp+70h+var_98], xmm0
0x18002c837  mov     [rbp+70h+var_88], rax
0x18002c83b  lea     rax, aNewstate; "NewState"
0x18002c842  mov     [rbp+70h+var_80], rax
0x18002c846  xor     eax, eax
0x18002c848  movups  xmmword ptr [rbp+70h+var_78], xmm0
0x18002c84c  mov     [rbp+70h+var_68], rax
0x18002c850  lea     r9d, [rcx-60h]; unsigned int
0x18002c854  lea     r8, [rbp+70h+var_E0]; struct EventDataDesc *
0x18002c858  mov     rcx, r14; this
0x18002c85b  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002c860  xor     esi, esi
0x18002c862  mov     [rsp+170h+var_140], rsi
0x18002c867  mov     r8d, dword ptr [rbp+70h+Size]; Size
0x18002c86b  mov     rdx, [rbp+70h+Src+8]; Src
0x18002c86f  lea     rcx, [rsp+170h+var_140]; void *
0x18002c874  call    memcpy_0
0x18002c879  mov     rdi, [rsp+170h+var_140]
0x18002c87e  mov     dword ptr [rsp+170h+var_120], esi
0x18002c882  mov     r8d, dword ptr [rbp+70h+var_A8]; Size
0x18002c886  mov     rdx, [rbp+70h+var_B8+8]; Src
0x18002c88a  lea     rcx, [rsp+170h+var_120]; void *
0x18002c88f  call    memcpy_0
0x18002c894  mov     [rsp+170h+var_140], rsi
0x18002c899  mov     r8d, dword ptr [rbp+70h+var_88]; Size
0x18002c89d  mov     rdx, [rbp+70h+var_98+8]; Src
0x18002c8a1  lea     rcx, [rsp+170h+var_140]; void *
0x18002c8a6  call    memcpy_0
0x18002c8ab  mov     rbx, [rsp+170h+var_140]
0x18002c8b0  mov     dword ptr [rsp+170h+var_140], esi
0x18002c8b4  mov     r8d, dword ptr [rbp+70h+var_68]; Size
0x18002c8b8  mov     rdx, [rbp+70h+var_78+8]; Src
0x18002c8bc  lea     rcx, [rsp+170h+var_140]; void *
0x18002c8c1  call    memcpy_0
0x18002c8c6  mov     [rsp+170h+var_118], rbx
0x18002c8cb  mov     eax, dword ptr [rsp+170h+var_120]
0x18002c8cf  mov     [rsp+170h+var_110], rax
0x18002c8d4  mov     [rsp+170h+var_108], rdi
0x18002c8d9  lea     r12, [r14+1D0h]
0x18002c8e0  lea     r8, [rsp+170h+var_118]
0x18002c8e5  lea     rdx, [rsp+170h+var_138]
0x18002c8ea  mov     rcx, r12
0x18002c8ed  call    ?find@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@2@AEBV?$tuple@_K_K_K@2@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::find(std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const &)
0x18002c8f2  mov     rbx, [rsp+170h+var_138]
0x18002c8f7  cmp     rbx, [r12]
0x18002c8fb  jz      loc_18002CCD7
0x18002c901  mov     r8d, dword ptr [rsp+170h+var_140]
0x18002c906  lea     rdx, [rbx+38h]
0x18002c90a  lea     rcx, [rsp+170h+var_130]
0x18002c90f  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002c914  nop
0x18002c915  sub     r8d, 3
0x18002c919  jz      loc_18002CA3A
0x18002c91f  sub     r8d, 1
0x18002c923  jz      loc_18002C9FF
0x18002c929  cmp     r8d, 2
0x18002c92d  jnz     loc_18002CAC8
0x18002c933  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_MultiMon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon> `wil::Feature<__WilFeatureTraits_Feature_GPM_MultiMon>::GetImpl(void)'::`2'::impl
0x18002c93a  cmp     [r14+260h], sil
0x18002c941  jz      short loc_18002C94F
0x18002c943  mov     dl, 1
0x18002c945  mov     rcx, r15
0x18002c948  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002c94d  jmp     short loc_18002C95F
0x18002c94f  mov     r8, rbx
0x18002c952  lea     rdx, [rsp+170h+var_138]
0x18002c957  mov     rcx, r12
0x18002c95a  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>)
0x18002c95f  mov     rdi, [rsp+170h+var_130]
0x18002c964  cmp     [rdi+0A9h], sil
0x18002c96b  jnz     short loc_18002C9AA
0x18002c96d  cmp     [rdi+0A0h], esi
0x18002c973  jz      short loc_18002C97B
0x18002c975  cmp     [rdi+28h], rsi
0x18002c979  jnz     short loc_18002C9AA
0x18002c97b  cmp     [r14+260h], sil
0x18002c982  jz      short loc_18002C99E
0x18002c984  mov     dl, 1
0x18002c986  mov     rcx, r15
0x18002c989  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002c98e  mov     r8, rbx
0x18002c991  lea     rdx, [rsp+170h+var_138]
0x18002c996  mov     rcx, r12
0x18002c999  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>)
0x18002c99e  mov     dword ptr [rdi+0A0h], 2
0x18002c9a8  jmp     short loc_18002C9E0
0x18002c9aa  mov     edx, [rdi+9Ch]
0x18002c9b0  call    ?IsComposedFlipMode@PMTraceConsumer@@QEAA_NW4PresentMode@@@Z; PMTraceConsumer::IsComposedFlipMode(PresentMode)
0x18002c9b5  test    al, al
0x18002c9b7  jnz     loc_18002CAC8
0x18002c9bd  cmp     [r14+260h], sil
0x18002c9c4  jz      short loc_18002C9E0
0x18002c9c6  mov     dl, 1
0x18002c9c8  mov     rcx, r15
0x18002c9cb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002c9d0  mov     r8, rbx
0x18002c9d3  lea     rdx, [rsp+170h+var_138]
0x18002c9d8  mov     rcx, r12
0x18002c9db  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const,std::shared_ptr<PresentEvent>>>>>)
0x18002c9e0  lea     rdx, [rsp+170h+var_130]
0x18002c9e5  lea     rcx, [rsp+170h+var_118]
0x18002c9ea  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002c9ef  mov     rdx, rax
0x18002c9f2  mov     rcx, r14
0x18002c9f5  call    ?CompletePresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::CompletePresent(std::shared_ptr<PresentEvent>)
0x18002c9fa  jmp     loc_18002CAC8
0x18002c9ff  mov     rax, [rsp+170h+var_130]
0x18002ca04  cmp     [rax+0A0h], esi
0x18002ca0a  jnz     short loc_18002CA1C
0x18002ca0c  test    byte ptr [rax+3Ch], 2
0x18002ca10  jz      short loc_18002CA1C
0x18002ca12  mov     dword ptr [rax+0A0h], 2
0x18002ca1c  lea     rdx, [rax+70h]
0x18002ca20  cmp     [rdx], rsi
0x18002ca23  jz      loc_18002CAC8
0x18002ca29  lea     rcx, [r14+200h]
0x18002ca30  call    ?erase@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::erase(unsigned __int64 const &)
0x18002ca35  jmp     loc_18002CAC8
0x18002ca3a  mov     rbx, [rsp+170h+var_130]
0x18002ca3f  lea     r8, [rbx+70h]
0x18002ca43  cmp     [r8], rsi
0x18002ca46  jz      short loc_18002CA9F
0x18002ca48  lea     rdi, [r14+200h]
0x18002ca4f  lea     rdx, [rsp+170h+var_138]
0x18002ca54  mov     rcx, rdi
0x18002ca57  call    ?find@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::find(unsigned __int64 const &)
0x18002ca5c  mov     rax, [rsp+170h+var_138]
0x18002ca61  cmp     rax, [rdi]
0x18002ca64  jnz     short loc_18002CA7F
0x18002ca66  lea     r9, [rsp+170h+var_130]
0x18002ca6b  lea     rdx, [rsp+170h+var_118]
0x18002ca70  mov     rcx, rdi
0x18002ca73  call    ??$emplace@AEA_KAEAV?$shared_ptr@UPresentEvent@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@std@@@std@@@std@@_N@1@AEA_KAEAV?$shared_ptr@UPresentEvent@@@1@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned __int64 &,std::shared_ptr<PresentEvent> &>(unsigned __int64 &,std::shared_ptr<PresentEvent> &)
0x18002ca78  mov     rbx, [rsp+170h+var_130]
0x18002ca7d  jmp     short loc_18002CA9F
0x18002ca7f  lea     rcx, [rax+28h]
0x18002ca83  mov     rax, [rcx]
0x18002ca86  cmp     rax, rbx
0x18002ca89  jz      short loc_18002CA9F
0x18002ca8b  mov     dword ptr [rax+0A0h], 2
0x18002ca95  lea     rdx, [rsp+170h+var_130]
0x18002ca9a  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> const &)
0x18002ca9f  mov     byte ptr [rbx+0A9h], 1
0x18002caa6  mov     rdx, r15
0x18002caa9  mov     rcx, r14
0x18002caac  call    ??$GetEventData@H@EventMetadata@@QEAAHPEAU_EVENT_RECORD@@PEBGI@Z; EventMetadata::GetEventData<int>(_EVENT_RECORD *,ushort const *,uint)
0x18002cab1  test    eax, eax
0x18002cab3  jz      short loc_18002CAC8
0x18002cab5  cmp     dword ptr [rbx+9Ch], 4
0x18002cabc  jnz     short loc_18002CAC8
0x18002cabe  mov     dword ptr [rbx+9Ch], 3
0x18002cac8  mov     rcx, [rsp+170h+var_128]
0x18002cacd  jmp     loc_18002CCCD
0x18002cad2  lea     rax, aCompositionsur; "CompositionSurfaceLuid"
0x18002cad9  mov     [rbp+70h+var_E0], rax
0x18002cadd  xorps   xmm0, xmm0
0x18002cae0  xor     eax, eax
0x18002cae2  movups  xmmword ptr [rbp+70h+Src], xmm0
0x18002cae6  mov     [rbp+70h+Size], rax
0x18002caea  lea     rax, aPresentcount; "PresentCount"
0x18002caf1  mov     [rbp+70h+var_C0], rax
0x18002caf5  xor     eax, eax
0x18002caf7  movups  xmmword ptr [rbp+70h+var_B8], xmm0
0x18002cafb  mov     [rbp+70h+var_A8], rax
0x18002caff  lea     rax, aBindid_0; "BindId"
0x18002cb06  mov     [rbp+70h+var_A0], rax
0x18002cb0a  xor     eax, eax
0x18002cb0c  movups  xmmword ptr [rbp+70h+var_98], xmm0
0x18002cb10  mov     [rbp+70h+var_88], rax
0x18002cb14  lea     rax, aDestwidth; "DestWidth"
0x18002cb1b  mov     [rbp+70h+var_80], rax
0x18002cb1f  xor     eax, eax
0x18002cb21  movups  xmmword ptr [rbp+70h+var_78], xmm0
0x18002cb25  mov     [rbp+70h+var_68], rax
0x18002cb29  lea     rax, aDestheight; "DestHeight"
0x18002cb30  mov     [rbp+70h+var_60], rax
0x18002cb34  xor     eax, eax
0x18002cb36  movups  xmmword ptr [rbp+70h+var_58], xmm0
0x18002cb3a  mov     [rbp+70h+var_48], rax
0x18002cb3e  mov     al, [rdx+2Ah]
0x18002cb41  neg     al
0x18002cb43  sbb     r9d, r9d
0x18002cb46  and     r9d, 2
0x18002cb4a  add     r9d, 3; unsigned int
0x18002cb4e  lea     r8, [rbp+70h+var_E0]; struct EventDataDesc *
0x18002cb52  mov     rcx, r14; this
0x18002cb55  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002cb5a  xor     esi, esi
0x18002cb5c  mov     [rsp+170h+var_140], rsi
0x18002cb61  mov     r8d, dword ptr [rbp+70h+Size]; Size
0x18002cb65  mov     rdx, [rbp+70h+Src+8]; Src
0x18002cb69  lea     rcx, [rsp+170h+var_140]; void *
0x18002cb6e  call    memcpy_0
0x18002cb73  mov     [rsp+170h+var_120], rsi
0x18002cb78  mov     r8d, dword ptr [rbp+70h+var_A8]; Size
0x18002cb7c  mov     rdx, [rbp+70h+var_B8+8]; Src
0x18002cb80  lea     rcx, [rsp+170h+var_120]; void *
0x18002cb85  call    memcpy_0
0x18002cb8a  mov     [rsp+170h+var_138], rsi
0x18002cb8f  mov     r8d, dword ptr [rbp+70h+var_88]; Size
0x18002cb93  mov     rdx, [rbp+70h+var_98+8]; Src
0x18002cb97  lea     rcx, [rsp+170h+var_138]; void *
0x18002cb9c  call    memcpy_0
0x18002cba1  mov     r8, r15
0x18002cba4  lea     rdx, [rsp+170h+var_118]
0x18002cba9  mov     rcx, r14; this
0x18002cbac  call    ?FindOrCreatePresent@PMTraceConsumer@@QEAA?AV?$shared_ptr@UPresentEvent@@@std@@AEBU_EVENT_HEADER@@@Z; PMTraceConsumer::FindOrCreatePresent(_EVENT_HEADER const &)
0x18002cbb1  nop
0x18002cbb2  mov     rbx, [rsp+170h+var_118]
0x18002cbb7  test    rbx, rbx
0x18002cbba  jz      loc_18002CCC8
0x18002cbc0  cmp     [rbx+0A7h], sil
0x18002cbc7  jz      short loc_18002CC1D
0x18002cbc9  lea     rdx, [rsp+170h+var_118]
0x18002cbce  lea     rcx, [rsp+170h+var_130]
0x18002cbd3  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002cbd8  mov     rdx, rax
0x18002cbdb  mov     rcx, r14
0x18002cbde  call    ?RemoveLostPresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::RemoveLostPresent(std::shared_ptr<PresentEvent>)
0x18002cbe3  mov     r8, r15
0x18002cbe6  lea     rdx, [rsp+170h+var_130]
0x18002cbeb  mov     rcx, r14; this
0x18002cbee  call    ?FindOrCreatePresent@PMTraceConsumer@@QEAA?AV?$shared_ptr@UPresentEvent@@@std@@AEBU_EVENT_HEADER@@@Z; PMTraceConsumer::FindOrCreatePresent(_EVENT_HEADER const &)
0x18002cbf3  mov     rdx, rax
0x18002cbf6  lea     rcx, [rsp+170h+var_118]
0x18002cbfb  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> &&)
0x18002cc00  mov     rcx, [rsp+170h+var_128]; this
0x18002cc05  test    rcx, rcx
0x18002cc08  jz      short loc_18002CC0F
0x18002cc0a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cc0f  mov     rbx, [rsp+170h+var_118]
0x18002cc14  test    rbx, rbx
0x18002cc17  jz      loc_18002CCC8
0x18002cc1d  mov     rdi, [rsp+170h+var_140]
0x18002cc22  mov     r12, [rsp+170h+var_120]
0x18002cc27  mov     r13, [rsp+170h+var_138]
0x18002cc2c  mov     dword ptr [rbx+9Ch], 4
0x18002cc36  mov     byte ptr [rbx+0A7h], 1
0x18002cc3d  cmp     byte ptr [r15+2Ah], 1
0x18002cc42  jb      short loc_18002CC84
0x18002cc44  mov     dword ptr [rsp+170h+var_140], esi
0x18002cc48  mov     r8d, dword ptr [rbp+70h+var_68]; Size
0x18002cc4c  mov     rdx, [rbp+70h+var_78+8]; Src
0x18002cc50  lea     rcx, [rsp+170h+var_140]; void *
0x18002cc55  call    memcpy_0
0x18002cc5a  mov     eax, dword ptr [rsp+170h+var_140]
0x18002cc5e  mov     [rbx+8Ch], eax
0x18002cc64  mov     dword ptr [rsp+170h+var_140], esi
0x18002cc68  mov     r8d, dword ptr [rbp+70h+var_48]; Size
0x18002cc6c  mov     rdx, [rbp+70h+var_58+8]; Src
0x18002cc70  lea     rcx, [rsp+170h+var_140]; void *
0x18002cc75  call    memcpy_0
0x18002cc7a  mov     eax, dword ptr [rsp+170h+var_140]
0x18002cc7e  mov     [rbx+90h], eax
0x18002cc84  mov     [rsp+170h+var_100], r13
0x18002cc89  mov     [rsp+170h+var_F8], r12
0x18002cc8e  mov     [rbp+70h+var_F0], rdi
0x18002cc92  lea     rcx, [r14+1D0h]
0x18002cc99  lea     r8, [rsp+170h+var_100]
0x18002cc9e  lea     rdx, [rsp+170h+var_130]
0x18002cca3  call    ??$_Try_emplace@AEBV?$tuple@_K_K_K@std@@$$V@?$map@V?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@U?$less@V?$tuple@_K_K_K@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$tuple@_K_K_K@std@@V?$shared_ptr@UPresentEvent@@@2@@std@@PEAX@std@@_N@1@AEBV?$tuple@_K_K_K@1@@Z; std::map<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64>,std::shared_ptr<PresentEvent>>::_Try_emplace<std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const &,>(std::tuple<unsigned __int64,unsigned __int64,unsigned __int64> const &)
0x18002cca8  mov     rcx, [rax]
0x18002ccab  add     rcx, 38h ; '8'
0x18002ccaf  lea     rdx, [rsp+170h+var_118]
0x18002ccb4  call    ??4?$shared_ptr@UPresentEvent@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<PresentEvent>::operator=(std::shared_ptr<PresentEvent> const &)
0x18002ccb9  mov     [rbx+80h], rdi
  ... truncated ...
```
