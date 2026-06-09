# CPolicyComponent::CreateAndInitializeRuleWriter(ushort const *,IWICMetadataQueryWriter *,RULE_PATH_INFO const *,uint,RULE_LIST_INDEX_ENTRY const *,uint,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,CRuleWriter * *)

- ea: `0x18000170c`
- end: `0x180001864`
- name: `?CreateAndInitializeRuleWriter@CPolicyComponent@@AEAAJPEBGPEAUIWICMetadataQueryWriter@@PEBURULE_PATH_INFO@@IPEBURULE_LIST_INDEX_ENTRY@@IPEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAVCRuleWriter@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(int, int, int, int, int, struct RULE_LIST_INDEX_ENTRY *, unsigned int, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800015f0`
- `0x180012950`
- `0x1800160e0`

## callees

- `0x18000170c`
- `0x180001920`
- `0x180001b50`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall CPolicyComponent::CreateAndInitializeRuleWriter(
        unsigned int *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        struct RULE_LIST_INDEX_ENTRY *a6,
        unsigned int a7,
        __int64 a8,
        _QWORD *a9)
{
  _QWORD *v12; // rdi
  CPolicyComponent *v13; // rcx
  int v14; // ebx
  struct KEY_LIST_ENTRY *v16; // r14
  struct KEY_LIST_ENTRY *v17; // [rsp+50h] [rbp-68h] BYREF
  const ATL::CAtlException *v18; // [rsp+58h] [rbp-60h] BYREF
  __int128 v19; // [rsp+60h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+70h] [rbp-48h]

  v12 = a9;
  *a9 = 0;
  v17 = 0;
  v14 = CPolicyComponent::_SearchForKey((CPolicyComponent *)a1, a2, &v17);
  if ( v14 >= 0 )
  {
    v19 = 0;
    v20 = 0;
    v16 = v17;
    v14 = CPolicyComponent::_SearchForIndexEntry(
            v13,
            a6,
            a7,
            *((_DWORD *)v17 + 1),
            a1[17],
            (struct RULE_LIST_INDEX_ENTRY *)&v19);
    if ( v14 >= 0 )
    {
      try
      {
        v14 = (*(__int64 (**)(void))(*(_QWORD *)a1 + 64LL))();
        if ( v14 >= 0 )
          v14 = (*(__int64 (__fastcall **)(_QWORD, struct KEY_LIST_ENTRY *, const struct CAPABILITIES_LIST_ENTRY near *const *, __int64, unsigned __int64, int, unsigned int *, __int64))(*(_QWORD *)*a9 + 16LL))(
                  *a9,
                  v16,
                  &gc_rgCapList + 9 * v20,
                  a3,
                  a4 + ((unsigned __int64)DWORD2(v19) << 6),
                  HIDWORD(v19) - DWORD2(v19) + 1,
                  a1,
                  a8);
      }
      catch ( const ATL::CAtlException *v18 )
      {
        v12 = a9;
        v14 = *(_DWORD *)v18;
      }
    }
  }
  if ( v14 < 0 )
  {
    if ( *v12 )
      (**(void (__fastcall ***)(_QWORD, __int64))*v12)(*v12, 1);
    *v12 = 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000170c  push    rbx
0x18000170e  push    rsi
0x18000170f  push    rdi
0x180001710  push    r12
0x180001712  push    r14
0x180001714  push    r15
0x180001716  sub     rsp, 88h
0x18000171d  mov     r15, r9
0x180001720  mov     r12, r8
0x180001723  mov     rsi, rcx
0x180001726  mov     rdi, [rsp+0B8h+arg_40]
0x18000172e  mov     qword ptr [rdi], 0
0x180001735  mov     [rsp+0B8h+var_68], 0
0x18000173e  lea     r8, [rsp+0B8h+var_68]; struct KEY_LIST_ENTRY **
0x180001743  call    ?_SearchForKey@CPolicyComponent@@AEAAJPEBGPEAPEBUKEY_LIST_ENTRY@@@Z; CPolicyComponent::_SearchForKey(ushort const *,KEY_LIST_ENTRY const * *)
0x180001748  mov     ebx, eax
0x18000174a  test    eax, eax
0x18000174c  jns     short loc_180001779
0x18000174e  test    ebx, ebx
0x180001750  jns     short loc_180001765
0x180001752  mov     rcx, [rdi]
0x180001755  test    rcx, rcx
0x180001758  jnz     loc_18000184F
0x18000175e  mov     qword ptr [rdi], 0
0x180001765  mov     eax, ebx
0x180001767  add     rsp, 88h
0x18000176e  pop     r15
0x180001770  pop     r14
0x180001772  pop     r12
0x180001774  pop     rdi
0x180001775  pop     rsi
0x180001776  pop     rbx
0x180001777  retn
0x180001779  xorps   xmm0, xmm0
0x18000177c  xor     eax, eax
0x18000177e  movups  [rsp+0B8h+var_58], xmm0
0x180001783  mov     [rsp+0B8h+var_48], eax
0x180001787  lea     rax, [rsp+0B8h+var_58]
0x18000178c  mov     [rsp+0B8h+var_90], rax; struct RULE_LIST_INDEX_ENTRY *
0x180001791  mov     eax, [rsi+44h]
0x180001794  mov     [rsp+0B8h+var_98], eax; unsigned int
0x180001798  mov     r14, [rsp+0B8h+var_68]
0x18000179d  mov     r9d, [r14+4]; unsigned int
0x1800017a1  mov     r8d, [rsp+0B8h+arg_30]; unsigned int
0x1800017a9  mov     rdx, [rsp+0B8h+arg_28]; struct RULE_LIST_INDEX_ENTRY *
0x1800017b1  call    ?_SearchForIndexEntry@CPolicyComponent@@AEAAJPEBURULE_LIST_INDEX_ENTRY@@IKKPEAU2@@Z; CPolicyComponent::_SearchForIndexEntry(RULE_LIST_INDEX_ENTRY const *,uint,ulong,ulong,RULE_LIST_INDEX_ENTRY *)
0x1800017b6  mov     ebx, eax
0x1800017b8  test    eax, eax
0x1800017ba  js      short loc_18000174E
0x1800017bc  mov     rax, [rsi]
0x1800017bf  mov     r8, rdi
0x1800017c2  mov     edx, [r14]
0x1800017c5  mov     rcx, rsi
0x1800017c8  mov     rax, [rax+40h]
0x1800017cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017d1  mov     ebx, eax
0x1800017d3  test    eax, eax
0x1800017d5  js      loc_18000174E
0x1800017db  mov     rcx, [rdi]
0x1800017de  mov     r11, [rcx]
0x1800017e1  mov     ebx, dword ptr [rsp+0B8h+var_58+0Ch]
0x1800017e5  sub     ebx, dword ptr [rsp+0B8h+var_58+8]
0x1800017e9  inc     ebx
0x1800017eb  mov     r10d, dword ptr [rsp+0B8h+var_58+8]
0x1800017f0  shl     r10, 6
0x1800017f4  add     r10, r15
0x1800017f7  mov     eax, [rsp+0B8h+var_48]
0x1800017fb  lea     r8, [rax+rax*8]
0x1800017ff  lea     rax, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x180001806  lea     r8, [rax+r8*8]
0x18000180a  mov     r9, [rsp+0B8h+arg_38]
0x180001812  mov     [rsp+0B8h+var_80], r9
0x180001817  mov     [rsp+0B8h+var_88], rsi
0x18000181c  mov     dword ptr [rsp+0B8h+var_90], ebx
0x180001820  mov     qword ptr [rsp+0B8h+var_98], r10
0x180001825  mov     r9, r12
0x180001828  mov     rdx, r14
0x18000182b  mov     rax, [r11+10h]
0x18000182f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001834  mov     ebx, eax
0x180001836  jmp     loc_18000174E
0x18000183b  mov     rdi, [rsp+0B8h+arg_40]
0x180001843  mov     ebx, [rsp+0B8h+arg_20]
0x18000184a  jmp     loc_18000174E
0x18000184f  mov     rax, [rcx]
0x180001852  mov     edx, 1
0x180001857  mov     rax, [rax]
0x18000185a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000185f  jmp     loc_18000175E
```
