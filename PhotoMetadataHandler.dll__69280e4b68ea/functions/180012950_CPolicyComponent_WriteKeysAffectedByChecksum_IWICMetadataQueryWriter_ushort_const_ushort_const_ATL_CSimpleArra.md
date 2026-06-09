# CPolicyComponent::WriteKeysAffectedByChecksum(IWICMetadataQueryWriter *,ushort const *,ushort const *,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)

- ea: `0x180012950`
- end: `0x180012bda`
- name: `?WriteKeysAffectedByChecksum@CPolicyComponent@@AEAAJPEAUIWICMetadataQueryWriter@@PEBG1PEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `650`
- prototype: `__int64 __usercall@<rax>(CPolicyComponent *this@<rcx>, struct IWICMetadataQueryReader *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012050`

## callees

- `0x18000170c`
- `0x180001a20`
- `0x180012950`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012adc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012b46`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012adc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012b46`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800129a6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800129a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyComponent::WriteKeysAffectedByChecksum(
        CPolicyComponent *this,
        struct IWICMetadataQueryReader *a2,
        __int64 a3,
        const WCHAR *a4,
        __int64 a5)
{
  int v7; // edi
  __int64 v8; // r14
  const struct KEY_LIST_ENTRY near *const *v9; // r15
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v16; // [rsp+20h] [rbp-88h]
  int v17; // [rsp+50h] [rbp-58h] BYREF
  struct CRuleReader *v18; // [rsp+58h] [rbp-50h] BYREF
  __int64 v19; // [rsp+60h] [rbp-48h] BYREF
  const ATL::CAtlException *v20; // [rsp+68h] [rbp-40h] BYREF
  PROPVARIANT pvar; // [rsp+70h] [rbp-38h] BYREF
  const WCHAR *v23; // [rsp+C8h] [rbp+20h]

  v23 = a4;
  v7 = 0;
  v18 = 0;
  v19 = 0;
  v8 = 0;
  try
  {
    while ( (unsigned int)v8 < 0x9E )
    {
      v9 = &gc_rgKeyList + 3 * v8;
      if ( lstrcmpW(a4, *((LPCWSTR *)v9 + 1)) )
      {
        v10 = CPolicyComponent::CreateAndInitializeRuleReader(
                this,
                (const struct KEY_LIST_ENTRY *)(&gc_rgKeyList + 3 * v8),
                a2,
                &v18);
        v7 = v10;
        if ( v10 < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(v10);
          if ( v7 < 0 )
            goto LABEL_42;
        }
        v17 = 0;
        v11 = (*(__int64 (__fastcall **)(struct CRuleReader *, __int64, int *))(*(_QWORD *)v18 + 32LL))(v18, a3, &v17);
        v7 = v11;
        if ( v11 < 0 )
        {
          if ( g_doStackCaptures )
            DoStackCapture(v11);
          if ( v7 < 0 )
            goto LABEL_42;
        }
        if ( v17 )
        {
          v12 = CPolicyComponent::CreateAndInitializeRuleWriter(
                  (int)this,
                  *((_QWORD *)v9 + 1),
                  (int)a2,
                  (int)&gc_rgWritePathList,
                  v16,
                  (struct RULE_LIST_INDEX_ENTRY *)&gc_rgWritePathIndex,
                  0x2DBu,
                  a5,
                  (__int64)&v19);
          v7 = v12;
          if ( v12 < 0 )
          {
            if ( g_doStackCaptures )
              DoStackCapture(v12);
            if ( v7 < 0 )
              goto LABEL_42;
          }
          memset(&pvar, 0, sizeof(pvar));
          v13 = (*(__int64 (__fastcall **)(struct CRuleReader *, PROPVARIANT *))(*(_QWORD *)v18 + 24LL))(v18, &pvar);
          v7 = v13;
          if ( v13 < 0 )
          {
            if ( g_doStackCaptures )
              DoStackCapture(v13);
            if ( v7 < 0 )
              goto LABEL_21;
          }
          v14 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *))(*(_QWORD *)v19 + 24LL))(v19, &pvar);
          v7 = v14;
          if ( v14 < 0 )
          {
            if ( g_doStackCaptures )
              DoStackCapture(v14);
            if ( v7 < 0 )
            {
LABEL_21:
              PropVariantClear(&pvar);
              goto LABEL_42;
            }
          }
          if ( v19 )
            (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
          v19 = 0;
          PropVariantClear(&pvar);
        }
        if ( v18 )
          (**(void (__fastcall ***)(struct CRuleReader *, __int64))v18)(v18, 1);
        v18 = 0;
      }
      v8 = (unsigned int)(v8 + 1);
      a4 = v23;
    }
  }
  catch ( const ATL::CAtlException *v20 )
  {
    v17 = *(_DWORD *)v20;
    v7 = v17;
  }
LABEL_42:
  if ( v18 )
    (**(void (__fastcall ***)(struct CRuleReader *, __int64))v18)(v18, 1);
  if ( v19 )
    (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012950  mov     rax, rsp
0x180012953  mov     [rax+8], rdi
0x180012957  mov     [rax+10h], r12
0x18001295b  mov     [rax+20h], r9
0x18001295f  mov     [rax+18h], r8
0x180012963  push    r13
0x180012965  push    r14
0x180012967  push    r15
0x180012969  sub     rsp, 90h
0x180012970  mov     r12, rdx
0x180012973  mov     r13, rcx
0x180012976  xor     edi, edi
0x180012978  mov     [rax-50h], rdi
0x18001297c  mov     [rax-48h], rdi
0x180012980  xor     r14d, r14d
0x180012983  cmp     r14d, 9Eh
0x18001298a  jnb     loc_180012AE9
0x180012990  lea     rcx, [r14+r14*2]
0x180012994  lea     rax, ?gc_rgKeyList@@3QBUKEY_LIST_ENTRY@@B; KEY_LIST_ENTRY const near * const gc_rgKeyList
0x18001299b  lea     r15, [rax+rcx*8]
0x18001299f  mov     rdx, [r15+8]; lpString2
0x1800129a3  mov     rcx, r9; lpString1
0x1800129a6  call    cs:__imp_lstrcmpW
0x1800129ad  nop     dword ptr [rax+rax+00h]
0x1800129b2  test    eax, eax
0x1800129b4  jz      loc_180012B75
0x1800129ba  lea     r9, [rsp+0A8h+var_50]; struct CRuleReader **
0x1800129bf  mov     r8, r12; struct IWICMetadataQueryReader *
0x1800129c2  mov     rdx, r15; struct KEY_LIST_ENTRY *
0x1800129c5  mov     rcx, r13; this
0x1800129c8  call    ?CreateAndInitializeRuleReader@CPolicyComponent@@AEAAJPEBUKEY_LIST_ENTRY@@PEAUIWICMetadataQueryReader@@PEAPEAVCRuleReader@@@Z; CPolicyComponent::CreateAndInitializeRuleReader(KEY_LIST_ENTRY const *,IWICMetadataQueryReader *,CRuleReader * *)
0x1800129cd  mov     edi, eax
0x1800129cf  test    eax, eax
0x1800129d1  jns     short loc_1800129EB
0x1800129d3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800129da  jz      short loc_1800129E3
0x1800129dc  mov     ecx, eax; int
0x1800129de  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800129e3  test    edi, edi
0x1800129e5  js      loc_180012AE9
0x1800129eb  mov     [rsp+0A8h+var_58], 0
0x1800129f3  mov     rcx, [rsp+0A8h+var_50]
0x1800129f8  mov     rax, [rcx]
0x1800129fb  lea     r8, [rsp+0A8h+var_58]
0x180012a00  mov     rdx, [rsp+0A8h+arg_10]
0x180012a08  mov     rax, [rax+20h]
0x180012a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a11  mov     edi, eax
0x180012a13  test    eax, eax
0x180012a15  jns     short loc_180012A2F
0x180012a17  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012a1e  jz      short loc_180012A27
0x180012a20  mov     ecx, eax; int
0x180012a22  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012a27  test    edi, edi
0x180012a29  js      loc_180012AE9
0x180012a2f  cmp     [rsp+0A8h+var_58], 0
0x180012a34  jz      loc_180012B52
0x180012a3a  lea     rax, [rsp+0A8h+var_48]
0x180012a3f  mov     [rsp+0A8h+var_68], rax; __int64
0x180012a44  mov     rax, [rsp+0A8h+arg_20]
0x180012a4c  mov     [rsp+0A8h+var_70], rax; __int64
0x180012a51  mov     [rsp+0A8h+var_78], 2DBh; unsigned int
0x180012a59  lea     rax, ?gc_rgWritePathIndex@@3QBURULE_LIST_INDEX_ENTRY@@B; RULE_LIST_INDEX_ENTRY const near * const gc_rgWritePathIndex
0x180012a60  mov     [rsp+0A8h+var_80], rax; struct RULE_LIST_INDEX_ENTRY *
0x180012a65  lea     r9, ?gc_rgWritePathList@@3QBURULE_PATH_INFO@@B; int
0x180012a6c  mov     r8, r12; int
0x180012a6f  mov     rdx, [r15+8]; int
0x180012a73  mov     rcx, r13; int
0x180012a76  call    ?CreateAndInitializeRuleWriter@CPolicyComponent@@AEAAJPEBGPEAUIWICMetadataQueryWriter@@PEBURULE_PATH_INFO@@IPEBURULE_LIST_INDEX_ENTRY@@IPEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAVCRuleWriter@@@Z; CPolicyComponent::CreateAndInitializeRuleWriter(ushort const *,IWICMetadataQueryWriter *,RULE_PATH_INFO const *,uint,RULE_LIST_INDEX_ENTRY const *,uint,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,CRuleWriter * *)
0x180012a7b  mov     edi, eax
0x180012a7d  test    eax, eax
0x180012a7f  jns     short loc_180012A95
0x180012a81  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012a88  jz      short loc_180012A91
0x180012a8a  mov     ecx, eax; int
0x180012a8c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012a91  test    edi, edi
0x180012a93  js      short loc_180012AE9
0x180012a95  xorps   xmm0, xmm0
0x180012a98  xor     eax, eax
0x180012a9a  movups  xmmword ptr [rsp+0A8h+pvar], xmm0
0x180012a9f  mov     qword ptr [rsp+0A8h+pvar+10h], rax
0x180012aa7  mov     rcx, [rsp+0A8h+var_50]
0x180012aac  mov     rax, [rcx]
0x180012aaf  lea     rdx, [rsp+0A8h+pvar]
0x180012ab4  mov     rax, [rax+18h]
0x180012ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abd  mov     edi, eax
0x180012abf  test    eax, eax
0x180012ac1  jns     short loc_180012AEE
0x180012ac3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012aca  jz      short loc_180012AD3
0x180012acc  mov     ecx, eax; int
0x180012ace  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012ad3  test    edi, edi
0x180012ad5  jns     short loc_180012AEE
0x180012ad7  lea     rcx, [rsp+0A8h+pvar]; pvar
0x180012adc  call    cs:__imp_PropVariantClear
0x180012ae3  nop     dword ptr [rax+rax+00h]
0x180012ae8  nop
0x180012ae9  jmp     loc_180012B89
0x180012aee  mov     rcx, [rsp+0A8h+var_48]
0x180012af3  mov     rax, [rcx]
0x180012af6  lea     rdx, [rsp+0A8h+pvar]
0x180012afb  mov     rax, [rax+18h]
0x180012aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b04  mov     edi, eax
0x180012b06  test    eax, eax
0x180012b08  jns     short loc_180012B1E
0x180012b0a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012b11  jz      short loc_180012B1A
0x180012b13  mov     ecx, eax; int
0x180012b15  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012b1a  test    edi, edi
0x180012b1c  js      short loc_180012AD7
0x180012b1e  mov     rcx, [rsp+0A8h+var_48]
0x180012b23  test    rcx, rcx
0x180012b26  jz      short loc_180012B38
0x180012b28  mov     rax, [rcx]
0x180012b2b  mov     edx, 1
0x180012b30  mov     rax, [rax]
0x180012b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b38  mov     [rsp+0A8h+var_48], 0
0x180012b41  lea     rcx, [rsp+0A8h+pvar]; pvar
0x180012b46  call    cs:__imp_PropVariantClear
0x180012b4d  nop     dword ptr [rax+rax+00h]
0x180012b52  mov     rcx, [rsp+0A8h+var_50]
0x180012b57  test    rcx, rcx
0x180012b5a  jz      short loc_180012B6C
0x180012b5c  mov     rax, [rcx]
0x180012b5f  mov     edx, 1
0x180012b64  mov     rax, [rax]
0x180012b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b6c  mov     [rsp+0A8h+var_50], 0
0x180012b75  inc     r14d
0x180012b78  mov     r9, [rsp+0A8h+arg_18]
0x180012b80  jmp     loc_180012983
0x180012b85  mov     edi, [rsp+0A8h+var_58]
0x180012b89  mov     rcx, [rsp+0A8h+var_50]
0x180012b8e  test    rcx, rcx
0x180012b91  jz      short loc_180012BA3
0x180012b93  mov     rax, [rcx]
0x180012b96  mov     edx, 1
0x180012b9b  mov     rax, [rax]
0x180012b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba3  mov     rcx, [rsp+0A8h+var_48]
0x180012ba8  test    rcx, rcx
0x180012bab  jz      short loc_180012BBD
0x180012bad  mov     r8, [rcx]
0x180012bb0  mov     edx, 1
0x180012bb5  mov     rax, [r8]
0x180012bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bbd  mov     eax, edi
0x180012bbf  lea     r11, [rsp+0A8h+var_18]
0x180012bc7  mov     rdi, [r11+20h]
0x180012bcb  mov     r12, [r11+28h]
0x180012bcf  mov     rsp, r11
0x180012bd2  pop     r15
0x180012bd4  pop     r14
0x180012bd6  pop     r13
0x180012bd8  retn
```
