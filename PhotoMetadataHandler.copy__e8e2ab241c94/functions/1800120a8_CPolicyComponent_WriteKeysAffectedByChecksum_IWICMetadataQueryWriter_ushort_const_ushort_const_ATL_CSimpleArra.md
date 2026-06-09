# CPolicyComponent::WriteKeysAffectedByChecksum(IWICMetadataQueryWriter *,ushort const *,ushort const *,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)

- ea: `0x1800120a8`
- end: `0x18001231f`
- name: `?WriteKeysAffectedByChecksum@CPolicyComponent@@AEAAJPEAUIWICMetadataQueryWriter@@PEBG1PEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `631`
- prototype: `__int64 __usercall@<rax>(CPolicyComponent *this@<rcx>, struct IWICMetadataQueryReader *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011838`

## callees

- `0x18000168c`
- `0x180001990`
- `0x1800120a8`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001222e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012292`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001222e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012292`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800120fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800120fe`

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
0x1800120a8  mov     rax, rsp
0x1800120ab  mov     [rax+8], rdi
0x1800120af  mov     [rax+10h], r12
0x1800120b3  mov     [rax+20h], r9
0x1800120b7  mov     [rax+18h], r8
0x1800120bb  push    r13
0x1800120bd  push    r14
0x1800120bf  push    r15
0x1800120c1  sub     rsp, 90h
0x1800120c8  mov     r12, rdx
0x1800120cb  mov     r13, rcx
0x1800120ce  xor     edi, edi
0x1800120d0  mov     [rax-50h], rdi
0x1800120d4  mov     [rax-48h], rdi
0x1800120d8  xor     r14d, r14d
0x1800120db  cmp     r14d, 9Eh
0x1800120e2  jnb     loc_180012235
0x1800120e8  lea     rcx, [r14+r14*2]
0x1800120ec  lea     rax, ?gc_rgKeyList@@3QBUKEY_LIST_ENTRY@@B; KEY_LIST_ENTRY const near * const gc_rgKeyList
0x1800120f3  lea     r15, [rax+rcx*8]
0x1800120f7  mov     rdx, [r15+8]; lpString2
0x1800120fb  mov     rcx, r9; lpString1
0x1800120fe  call    cs:__imp_lstrcmpW
0x180012104  test    eax, eax
0x180012106  jz      loc_1800122BB
0x18001210c  lea     r9, [rsp+0A8h+var_50]; struct CRuleReader **
0x180012111  mov     r8, r12; struct IWICMetadataQueryReader *
0x180012114  mov     rdx, r15; struct KEY_LIST_ENTRY *
0x180012117  mov     rcx, r13; this
0x18001211a  call    ?CreateAndInitializeRuleReader@CPolicyComponent@@AEAAJPEBUKEY_LIST_ENTRY@@PEAUIWICMetadataQueryReader@@PEAPEAVCRuleReader@@@Z; CPolicyComponent::CreateAndInitializeRuleReader(KEY_LIST_ENTRY const *,IWICMetadataQueryReader *,CRuleReader * *)
0x18001211f  mov     edi, eax
0x180012121  test    eax, eax
0x180012123  jns     short loc_18001213D
0x180012125  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001212c  jz      short loc_180012135
0x18001212e  mov     ecx, eax; int
0x180012130  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012135  test    edi, edi
0x180012137  js      loc_180012235
0x18001213d  mov     [rsp+0A8h+var_58], 0
0x180012145  mov     rcx, [rsp+0A8h+var_50]
0x18001214a  mov     rax, [rcx]
0x18001214d  lea     r8, [rsp+0A8h+var_58]
0x180012152  mov     rdx, [rsp+0A8h+arg_10]
0x18001215a  mov     rax, [rax+20h]
0x18001215e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012163  mov     edi, eax
0x180012165  test    eax, eax
0x180012167  jns     short loc_180012181
0x180012169  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012170  jz      short loc_180012179
0x180012172  mov     ecx, eax; int
0x180012174  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012179  test    edi, edi
0x18001217b  js      loc_180012235
0x180012181  cmp     [rsp+0A8h+var_58], 0
0x180012186  jz      loc_180012298
0x18001218c  lea     rax, [rsp+0A8h+var_48]
0x180012191  mov     [rsp+0A8h+var_68], rax; __int64
0x180012196  mov     rax, [rsp+0A8h+arg_20]
0x18001219e  mov     [rsp+0A8h+var_70], rax; __int64
0x1800121a3  mov     [rsp+0A8h+var_78], 2DBh; unsigned int
0x1800121ab  lea     rax, ?gc_rgWritePathIndex@@3QBURULE_LIST_INDEX_ENTRY@@B; RULE_LIST_INDEX_ENTRY const near * const gc_rgWritePathIndex
0x1800121b2  mov     [rsp+0A8h+var_80], rax; struct RULE_LIST_INDEX_ENTRY *
0x1800121b7  lea     r9, ?gc_rgWritePathList@@3QBURULE_PATH_INFO@@B; int
0x1800121be  mov     r8, r12; int
0x1800121c1  mov     rdx, [r15+8]; int
0x1800121c5  mov     rcx, r13; int
0x1800121c8  call    ?CreateAndInitializeRuleWriter@CPolicyComponent@@AEAAJPEBGPEAUIWICMetadataQueryWriter@@PEBURULE_PATH_INFO@@IPEBURULE_LIST_INDEX_ENTRY@@IPEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAVCRuleWriter@@@Z; CPolicyComponent::CreateAndInitializeRuleWriter(ushort const *,IWICMetadataQueryWriter *,RULE_PATH_INFO const *,uint,RULE_LIST_INDEX_ENTRY const *,uint,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,CRuleWriter * *)
0x1800121cd  mov     edi, eax
0x1800121cf  test    eax, eax
0x1800121d1  jns     short loc_1800121E7
0x1800121d3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800121da  jz      short loc_1800121E3
0x1800121dc  mov     ecx, eax; int
0x1800121de  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800121e3  test    edi, edi
0x1800121e5  js      short loc_180012235
0x1800121e7  xorps   xmm0, xmm0
0x1800121ea  xor     eax, eax
0x1800121ec  movups  xmmword ptr [rsp+0A8h+pvar], xmm0
0x1800121f1  mov     qword ptr [rsp+0A8h+pvar+10h], rax
0x1800121f9  mov     rcx, [rsp+0A8h+var_50]
0x1800121fe  mov     rax, [rcx]
0x180012201  lea     rdx, [rsp+0A8h+pvar]
0x180012206  mov     rax, [rax+18h]
0x18001220a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001220f  mov     edi, eax
0x180012211  test    eax, eax
0x180012213  jns     short loc_18001223A
0x180012215  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001221c  jz      short loc_180012225
0x18001221e  mov     ecx, eax; int
0x180012220  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012225  test    edi, edi
0x180012227  jns     short loc_18001223A
0x180012229  lea     rcx, [rsp+0A8h+pvar]; pvar
0x18001222e  call    cs:__imp_PropVariantClear
0x180012234  nop
0x180012235  jmp     loc_1800122CF
0x18001223a  mov     rcx, [rsp+0A8h+var_48]
0x18001223f  mov     rax, [rcx]
0x180012242  lea     rdx, [rsp+0A8h+pvar]
0x180012247  mov     rax, [rax+18h]
0x18001224b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012250  mov     edi, eax
0x180012252  test    eax, eax
0x180012254  jns     short loc_18001226A
0x180012256  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001225d  jz      short loc_180012266
0x18001225f  mov     ecx, eax; int
0x180012261  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012266  test    edi, edi
0x180012268  js      short loc_180012229
0x18001226a  mov     rcx, [rsp+0A8h+var_48]
0x18001226f  test    rcx, rcx
0x180012272  jz      short loc_180012284
0x180012274  mov     rax, [rcx]
0x180012277  mov     edx, 1
0x18001227c  mov     rax, [rax]
0x18001227f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012284  mov     [rsp+0A8h+var_48], 0
0x18001228d  lea     rcx, [rsp+0A8h+pvar]; pvar
0x180012292  call    cs:__imp_PropVariantClear
0x180012298  mov     rcx, [rsp+0A8h+var_50]
0x18001229d  test    rcx, rcx
0x1800122a0  jz      short loc_1800122B2
0x1800122a2  mov     rax, [rcx]
0x1800122a5  mov     edx, 1
0x1800122aa  mov     rax, [rax]
0x1800122ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b2  mov     [rsp+0A8h+var_50], 0
0x1800122bb  inc     r14d
0x1800122be  mov     r9, [rsp+0A8h+arg_18]
0x1800122c6  jmp     loc_1800120DB
0x1800122cb  mov     edi, [rsp+0A8h+var_58]
0x1800122cf  mov     rcx, [rsp+0A8h+var_50]
0x1800122d4  test    rcx, rcx
0x1800122d7  jz      short loc_1800122E9
0x1800122d9  mov     rax, [rcx]
0x1800122dc  mov     edx, 1
0x1800122e1  mov     rax, [rax]
0x1800122e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122e9  mov     rcx, [rsp+0A8h+var_48]
0x1800122ee  test    rcx, rcx
0x1800122f1  jz      short loc_180012303
0x1800122f3  mov     r8, [rcx]
0x1800122f6  mov     edx, 1
0x1800122fb  mov     rax, [r8]
0x1800122fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012303  mov     eax, edi
0x180012305  lea     r11, [rsp+0A8h+var_18]
0x18001230d  mov     rdi, [r11+20h]
0x180012311  mov     r12, [r11+28h]
0x180012315  mov     rsp, r11
0x180012318  pop     r15
0x18001231a  pop     r14
0x18001231c  pop     r13
0x18001231e  retn
```
