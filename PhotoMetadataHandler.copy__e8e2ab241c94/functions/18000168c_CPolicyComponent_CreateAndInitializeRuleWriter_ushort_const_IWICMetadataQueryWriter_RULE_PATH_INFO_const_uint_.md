# CPolicyComponent::CreateAndInitializeRuleWriter(ushort const *,IWICMetadataQueryWriter *,RULE_PATH_INFO const *,uint,RULE_LIST_INDEX_ENTRY const *,uint,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,CRuleWriter * *)

- ea: `0x18000168c`
- end: `0x1800017e3`
- name: `?CreateAndInitializeRuleWriter@CPolicyComponent@@AEAAJPEBGPEAUIWICMetadataQueryWriter@@PEBURULE_PATH_INFO@@IPEBURULE_LIST_INDEX_ENTRY@@IPEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAVCRuleWriter@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(int, int, int, int, int, struct RULE_LIST_INDEX_ENTRY *, unsigned int, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001570`
- `0x1800120a8`
- `0x1800156d0`

## callees

- `0x18000168c`
- `0x1800018a0`
- `0x180001ac0`
- `0x180028010`

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
0x18000168c  push    rbx
0x18000168e  push    rsi
0x18000168f  push    rdi
0x180001690  push    r12
0x180001692  push    r14
0x180001694  push    r15
0x180001696  sub     rsp, 88h
0x18000169d  mov     r15, r9
0x1800016a0  mov     r12, r8
0x1800016a3  mov     rsi, rcx
0x1800016a6  mov     rdi, [rsp+0B8h+arg_40]
0x1800016ae  mov     qword ptr [rdi], 0
0x1800016b5  mov     [rsp+0B8h+var_68], 0
0x1800016be  lea     r8, [rsp+0B8h+var_68]; struct KEY_LIST_ENTRY **
0x1800016c3  call    ?_SearchForKey@CPolicyComponent@@AEAAJPEBGPEAPEBUKEY_LIST_ENTRY@@@Z; CPolicyComponent::_SearchForKey(ushort const *,KEY_LIST_ENTRY const * *)
0x1800016c8  mov     ebx, eax
0x1800016ca  test    eax, eax
0x1800016cc  jns     short loc_1800016F8
0x1800016ce  test    ebx, ebx
0x1800016d0  jns     short loc_1800016E5
0x1800016d2  mov     rcx, [rdi]
0x1800016d5  test    rcx, rcx
0x1800016d8  jnz     loc_1800017CE
0x1800016de  mov     qword ptr [rdi], 0
0x1800016e5  mov     eax, ebx
0x1800016e7  add     rsp, 88h
0x1800016ee  pop     r15
0x1800016f0  pop     r14
0x1800016f2  pop     r12
0x1800016f4  pop     rdi
0x1800016f5  pop     rsi
0x1800016f6  pop     rbx
0x1800016f7  retn
0x1800016f8  xorps   xmm0, xmm0
0x1800016fb  xor     eax, eax
0x1800016fd  movups  [rsp+0B8h+var_58], xmm0
0x180001702  mov     [rsp+0B8h+var_48], eax
0x180001706  lea     rax, [rsp+0B8h+var_58]
0x18000170b  mov     [rsp+0B8h+var_90], rax; struct RULE_LIST_INDEX_ENTRY *
0x180001710  mov     eax, [rsi+44h]
0x180001713  mov     [rsp+0B8h+var_98], eax; unsigned int
0x180001717  mov     r14, [rsp+0B8h+var_68]
0x18000171c  mov     r9d, [r14+4]; unsigned int
0x180001720  mov     r8d, [rsp+0B8h+arg_30]; unsigned int
0x180001728  mov     rdx, [rsp+0B8h+arg_28]; struct RULE_LIST_INDEX_ENTRY *
0x180001730  call    ?_SearchForIndexEntry@CPolicyComponent@@AEAAJPEBURULE_LIST_INDEX_ENTRY@@IKKPEAU2@@Z; CPolicyComponent::_SearchForIndexEntry(RULE_LIST_INDEX_ENTRY const *,uint,ulong,ulong,RULE_LIST_INDEX_ENTRY *)
0x180001735  mov     ebx, eax
0x180001737  test    eax, eax
0x180001739  js      short loc_1800016CE
0x18000173b  mov     rax, [rsi]
0x18000173e  mov     r8, rdi
0x180001741  mov     edx, [r14]
0x180001744  mov     rcx, rsi
0x180001747  mov     rax, [rax+40h]
0x18000174b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001750  mov     ebx, eax
0x180001752  test    eax, eax
0x180001754  js      loc_1800016CE
0x18000175a  mov     rcx, [rdi]
0x18000175d  mov     r11, [rcx]
0x180001760  mov     ebx, dword ptr [rsp+0B8h+var_58+0Ch]
0x180001764  sub     ebx, dword ptr [rsp+0B8h+var_58+8]
0x180001768  inc     ebx
0x18000176a  mov     r10d, dword ptr [rsp+0B8h+var_58+8]
0x18000176f  shl     r10, 6
0x180001773  add     r10, r15
0x180001776  mov     eax, [rsp+0B8h+var_48]
0x18000177a  lea     r8, [rax+rax*8]
0x18000177e  lea     rax, ?gc_rgCapList@@3QBUCAPABILITIES_LIST_ENTRY@@B; CAPABILITIES_LIST_ENTRY const near * const gc_rgCapList
0x180001785  lea     r8, [rax+r8*8]
0x180001789  mov     r9, [rsp+0B8h+arg_38]
0x180001791  mov     [rsp+0B8h+var_80], r9
0x180001796  mov     [rsp+0B8h+var_88], rsi
0x18000179b  mov     dword ptr [rsp+0B8h+var_90], ebx
0x18000179f  mov     qword ptr [rsp+0B8h+var_98], r10
0x1800017a4  mov     r9, r12
0x1800017a7  mov     rdx, r14
0x1800017aa  mov     rax, [r11+10h]
0x1800017ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017b3  mov     ebx, eax
0x1800017b5  jmp     loc_1800016CE
0x1800017ba  mov     rdi, [rsp+0B8h+arg_40]
0x1800017c2  mov     ebx, [rsp+0B8h+arg_20]
0x1800017c9  jmp     loc_1800016CE
0x1800017ce  mov     rax, [rcx]
0x1800017d1  mov     edx, 1
0x1800017d6  mov     rax, [rax]
0x1800017d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017de  jmp     loc_1800016DE
```
