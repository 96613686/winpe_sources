# PresentEventConsumer::ComputeStatistics(__int64)

- ea: `0x180015040`
- end: `0x180015279`
- name: `?ComputeStatistics@PresentEventConsumer@@UEAA?AUCombinedStatistics@@_J@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000b930`

## callees

- `0x180003ab0`
- `0x1800047f0`
- `0x18000b550`
- `0x18000b670`
- `0x18000fc54`
- `0x1800146e8`
- `0x180015040`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PresentEventConsumer::ComputeStatistics(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdx
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 **v9; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _OWORD *v12; // rax
  _OWORD *v13; // rcx
  __int64 v14; // rdx
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+48h] [rbp-B8h]
  _QWORD v19[5]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v20[160]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v21; // [rsp+120h] [rbp+20h]
  __int64 v22; // [rsp+128h] [rbp+28h]
  __int64 v23; // [rsp+130h] [rbp+30h]
  __int64 v24; // [rsp+138h] [rbp+38h]
  __int64 v25; // [rsp+140h] [rbp+40h]
  _BYTE v26[160]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v27; // [rsp+1E8h] [rbp+E8h]
  _BYTE v28[912]; // [rsp+1F0h] [rbp+F0h] BYREF

  *(_DWORD *)(a1 + 152) = *(_DWORD *)(a1 + 80);
  v16 = 0;
  v17 = 0;
  memset(v19, 0, sizeof(v19));
  memset_0(v20, 0, sizeof(v20));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v18 = *(_OWORD *)(a1 + 152);
  v7 = **(__int64 ***)(a1 + 136);
  while ( !*((_BYTE *)v7 + 25) )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v7[5] + 32LL))(v7[5], v28);
    std::vector<PresentStatistics>::emplace_back<PresentStatistics>(&v16, v8);
    v9 = (__int64 **)v7[2];
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v7 = i;
      v7 = i;
    }
    else
    {
      v7 = (__int64 *)v7[2];
      for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v7 = j;
    }
  }
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl'::`2'::impl,
    v6,
    0);
  v12 = (_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 184) + 24LL))(
                    *(_QWORD *)(a1 + 184),
                    v28);
  v13 = v19;
  v14 = 3;
  do
  {
    *v13 = *v12;
    v13[1] = v12[1];
    v13[2] = v12[2];
    v13[3] = v12[3];
    v13[4] = v12[4];
    v13[5] = v12[5];
    v13[6] = v12[6];
    v13[7] = v12[7];
    v13 += 8;
    v12 += 8;
    --v14;
  }
  while ( v14 );
  *v13 = *v12;
  *((_QWORD *)v13 + 2) = *((_QWORD *)v12 + 2);
  *(_OWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 128) = a3;
  CombinedStatistics::CombinedStatistics();
  if ( (_QWORD)v16 )
    std::_Deallocate<16>((void *)v16, 16 * ((v17 - (__int64)v16) >> 4));
  return a2;
}

```

## disassembly

```asm
0x180015040  mov     [rsp-8+arg_10], rbx
0x180015045  push    rbp
0x180015046  push    rsi
0x180015047  push    rdi
0x180015048  push    r14
0x18001504a  push    r15
0x18001504c  lea     rbp, [rsp-490h]
0x180015054  sub     rsp, 590h
0x18001505b  mov     rax, cs:__security_cookie
0x180015062  xor     rax, rsp
0x180015065  mov     [rbp+4B0h+var_30], rax
0x18001506c  mov     r14, r8
0x18001506f  mov     rsi, rdx
0x180015072  mov     rdi, rcx
0x180015075  mov     [rsp+5B0h+var_588], rdx
0x18001507a  xor     r15d, r15d
0x18001507d  mov     eax, [rcx+50h]
0x180015080  mov     [rcx+98h], eax
0x180015086  xorps   xmm0, xmm0
0x180015089  movdqa  [rsp+5B0h+var_580], xmm0
0x18001508f  mov     [rsp+5B0h+var_570], r15
0x180015094  mov     [rsp+5B0h+var_558], r15
0x180015099  mov     [rsp+5B0h+var_550], r15
0x18001509e  mov     [rsp+5B0h+var_548], r15
0x1800150a3  mov     [rsp+5B0h+var_540], r15
0x1800150a8  mov     [rsp+5B0h+var_538], r15
0x1800150ad  mov     ebx, 0A0h
0x1800150b2  mov     r8d, ebx; Size
0x1800150b5  xor     edx, edx; Val
0x1800150b7  lea     rcx, [rbp+4B0h+var_530]; void *
0x1800150bb  call    memset_0
0x1800150c0  mov     [rbp+4B0h+var_490], r15
0x1800150c4  mov     [rbp+4B0h+var_488], r15
0x1800150c8  mov     [rbp+4B0h+var_480], r15
0x1800150cc  mov     [rbp+4B0h+var_478], r15
0x1800150d0  mov     [rbp+4B0h+var_470], r15
0x1800150d4  mov     r8d, ebx; Size
0x1800150d7  xor     edx, edx; Val
0x1800150d9  lea     rcx, [rbp+4B0h+var_468]; void *
0x1800150dd  call    memset_0
0x1800150e2  mov     [rbp+4B0h+var_3C8], r15
0x1800150e9  movups  xmm0, xmmword ptr [rdi+98h]
0x1800150f0  movdqu  [rsp+5B0h+var_568], xmm0
0x1800150f6  mov     rbx, [rdi+88h]
0x1800150fd  mov     rbx, [rbx]
0x180015100  cmp     [rbx+19h], r15b
0x180015104  jnz     short loc_18001516F
0x180015106  mov     rcx, [rbx+28h]
0x18001510a  mov     rax, [rcx]
0x18001510d  lea     rdx, [rbp+4B0h+var_3C0]
0x180015114  mov     rax, [rax+20h]
0x180015118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001511d  mov     rdx, rax
0x180015120  lea     rcx, [rsp+5B0h+var_580]
0x180015125  call    ??$emplace_back@UPresentStatistics@@@?$vector@UPresentStatistics@@V?$allocator@UPresentStatistics@@@std@@@std@@QEAAAEAUPresentStatistics@@$$QEAU2@@Z; std::vector<PresentStatistics>::emplace_back<PresentStatistics>(PresentStatistics &&)
0x18001512a  mov     rcx, [rbx+10h]
0x18001512e  cmp     [rcx+19h], r15b
0x180015132  jz      short loc_180015152
0x180015134  mov     rax, [rbx+8]
0x180015138  jmp     short loc_180015147
0x18001513a  cmp     rbx, [rax+10h]
0x18001513e  jnz     short loc_18001514D
0x180015140  mov     rbx, rax
0x180015143  mov     rax, [rax+8]
0x180015147  cmp     [rax+19h], r15b
0x18001514b  jz      short loc_18001513A
0x18001514d  mov     rbx, rax
0x180015150  jmp     short loc_180015100
0x180015152  mov     rbx, rcx
0x180015155  mov     rcx, [rcx]
0x180015158  cmp     [rcx+19h], r15b
0x18001515c  jnz     short loc_180015100
0x18001515e  mov     rbx, rcx
0x180015161  mov     rax, [rcx]
0x180015164  mov     rcx, rax
0x180015167  cmp     [rax+19h], r15b
0x18001516b  jz      short loc_18001515E
0x18001516d  jmp     short loc_180015100
0x18001516f  xor     r8d, r8d
0x180015172  mov     dl, 1
0x180015174  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl(void)'::`2'::impl
0x18001517b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180015180  mov     rcx, [rdi+0B8h]
0x180015187  mov     rax, [rcx]
0x18001518a  lea     rdx, [rbp+4B0h+var_3C0]
0x180015191  mov     rax, [rax+18h]
0x180015195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001519a  lea     rcx, [rsp+5B0h+var_558]
0x18001519f  mov     edx, 3
0x1800151a4  lea     r8d, [rdx+7Dh]
0x1800151a8  movups  xmm0, xmmword ptr [rax]
0x1800151ab  movups  xmmword ptr [rcx], xmm0
0x1800151ae  movups  xmm1, xmmword ptr [rax+10h]
0x1800151b2  movups  xmmword ptr [rcx+10h], xmm1
0x1800151b6  movups  xmm0, xmmword ptr [rax+20h]
0x1800151ba  movups  xmmword ptr [rcx+20h], xmm0
0x1800151be  movups  xmm1, xmmword ptr [rax+30h]
0x1800151c2  movups  xmmword ptr [rcx+30h], xmm1
0x1800151c6  movups  xmm0, xmmword ptr [rax+40h]
0x1800151ca  movups  xmmword ptr [rcx+40h], xmm0
0x1800151ce  movups  xmm1, xmmword ptr [rax+50h]
0x1800151d2  movups  xmmword ptr [rcx+50h], xmm1
0x1800151d6  movups  xmm0, xmmword ptr [rax+60h]
0x1800151da  movups  xmmword ptr [rcx+60h], xmm0
0x1800151de  movups  xmm1, xmmword ptr [rax+70h]
0x1800151e2  movups  xmmword ptr [rcx+70h], xmm1
0x1800151e6  add     rcx, r8
0x1800151e9  add     rax, r8
0x1800151ec  sub     rdx, 1
0x1800151f0  jnz     short loc_1800151A8
0x1800151f2  movups  xmm0, xmmword ptr [rax]
0x1800151f5  movups  xmmword ptr [rcx], xmm0
0x1800151f8  mov     rax, [rax+10h]
0x1800151fc  mov     [rcx+10h], rax
0x180015200  xorps   xmm0, xmm0
0x180015203  movdqu  xmmword ptr [rdi+98h], xmm0
0x18001520b  mov     [rdi+80h], r14
0x180015212  lea     rdx, [rsp+5B0h+var_580]
0x180015217  mov     rcx, rsi
0x18001521a  call    ??0CombinedStatistics@@QEAA@$$QEAU0@@Z; CombinedStatistics::CombinedStatistics(CombinedStatistics &&)
0x18001521f  nop
0x180015220  mov     rcx, qword ptr [rsp+5B0h+var_580]
0x180015225  test    rcx, rcx
0x180015228  jz      short loc_180015250
0x18001522a  mov     rdx, [rsp+5B0h+var_570]
0x18001522f  sub     rdx, rcx
0x180015232  sar     rdx, 4
0x180015236  mov     rax, 823EE08FB823EE09h
0x180015240  imul    rdx, rax
0x180015244  imul    rdx, 390h
0x18001524b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015250  mov     rax, rsi
0x180015253  mov     rcx, [rbp+4B0h+var_30]
0x18001525a  xor     rcx, rsp; StackCookie
0x18001525d  call    __security_check_cookie
0x180015262  mov     rbx, [rsp+5B0h+arg_10]
0x18001526a  add     rsp, 590h
0x180015271  pop     r15
0x180015273  pop     r14
0x180015275  pop     rdi
0x180015276  pop     rsi
0x180015277  pop     rbp
0x180015278  retn
```
