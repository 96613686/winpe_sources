# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014234`
- end: `0x18001433c`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `264`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013bd8`

## callees

- `0x180014234`
- `0x1800176d0`
- `0x180017850`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_NetshInterface>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // edx
  char v12; // si
  bool v13; // cl

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(51777756, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( v5 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_21;
  }
  v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Netsh>::GetImpl'::`2'::impl);
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_21:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180014234  push    rbx
0x180014236  push    rbp
0x180014237  push    rsi
0x180014238  push    rdi
0x180014239  sub     rsp, 28h
0x18001423d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014244  mov     rbx, rdx
0x180014247  mov     edi, 3
0x18001424c  test    rax, rax
0x18001424f  jz      short loc_180014261
0x180014251  mov     edx, edi
0x180014253  mov     ecx, 31610DCh
0x180014258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001425d  mov     edx, eax
0x18001425f  jmp     short loc_18001426F
0x180014261  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014268  test    rax, rax
0x18001426b  jnz     short loc_180014251
0x18001426d  xor     edx, edx
0x18001426f  mov     r8d, edx
0x180014272  mov     qword ptr [rbx], 0
0x180014279  mov     eax, edx
0x18001427b  and     r8d, 0FFFFFF3Fh
0x180014282  and     edx, 80h
0x180014288  mov     ecx, r8d
0x18001428b  and     ecx, edi
0x18001428d  mov     ebp, 40h ; '@'
0x180014292  shl     ecx, 2
0x180014295  and     eax, ebp
0x180014297  or      ecx, eax
0x180014299  shl     ecx, 2
0x18001429c  or      ecx, edx
0x18001429e  lea     edx, ds:0[rcx*8]
0x1800142a5  test    r8d, r8d
0x1800142a8  jnz     short loc_1800142B1
0x1800142aa  mov     ecx, ebp
0x1800142ac  mov     r8d, ebp
0x1800142af  jmp     short loc_1800142BD
0x1800142b1  xor     ecx, ecx
0x1800142b3  cmp     r8d, 2
0x1800142b7  cmovz   ecx, ebp
0x1800142ba  mov     r8d, ecx
0x1800142bd  mov     eax, edx
0x1800142bf  mov     edi, 1
0x1800142c4  or      eax, r8d
0x1800142c7  or      edx, ecx
0x1800142c9  mov     [rbx], eax
0x1800142cb  bt      edx, 0Ah
0x1800142cf  jnb     short loc_1800142DE
0x1800142d1  cmp     edx, 800h
0x1800142d7  jb      short loc_1800142DE
0x1800142d9  mov     sil, dil
0x1800142dc  jmp     short loc_1800142E8
0x1800142de  xor     sil, sil
0x1800142e1  xor     cl, cl
0x1800142e3  test    bpl, dl
0x1800142e6  jz      short loc_18001431C
0x1800142e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::GetImpl(void)'::`2'::impl
0x1800142ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_IpxlatSvcRpc>::__private_IsEnabled(wil::ReportingKind)
0x1800142f4  test    al, al
0x1800142f6  jz      short loc_18001430D
0x1800142f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Netsh@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Netsh@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Netsh>::GetImpl(void)'::`2'::impl
0x1800142ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Netsh@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Netsh>::__private_IsEnabled(wil::ReportingKind)
0x180014304  test    al, al
0x180014306  jz      short loc_18001430D
0x180014308  mov     cl, dil
0x18001430b  jmp     short loc_18001430F
0x18001430d  xor     cl, cl
0x18001430f  test    sil, sil
0x180014312  jz      short loc_18001431C
0x180014314  test    cl, cl
0x180014316  jnz     short loc_18001431C
0x180014318  btr     dword ptr [rbx], 0Ah
0x18001431c  mov     eax, [rbx]
0x18001431e  test    bpl, al
0x180014321  jz      short loc_180014327
0x180014323  test    cl, cl
0x180014325  jnz     short loc_180014329
0x180014327  xor     edi, edi
0x180014329  and     eax, 0FFFFFFFEh
0x18001432c  or      eax, edi
0x18001432e  mov     [rbx], eax
0x180014330  mov     rax, rbx
0x180014333  add     rsp, 28h
0x180014337  pop     rdi
0x180014338  pop     rsi
0x180014339  pop     rbp
0x18001433a  pop     rbx
0x18001433b  retn
```
