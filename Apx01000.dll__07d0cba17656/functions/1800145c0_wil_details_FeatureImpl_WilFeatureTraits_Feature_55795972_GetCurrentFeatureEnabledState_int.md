# wil::details::FeatureImpl<__WilFeatureTraits_Feature_55795972>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800145c0`
- end: `0x180014723`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_55795972@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `355`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012f60`

## callees

- `0x18000ab68`
- `0x180014098`
- `0x1800145c0`
- `0x1800152c0`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_55795972>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // si
  bool v13; // dl
  unsigned int v14; // r8d
  char IsEnabled; // al
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(55795972, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( ((unsigned __int8)v11 & 0x40) == 0 )
      goto LABEL_19;
  }
  v14 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (*(_DWORD *)Feature_UxLabTest__descriptor & 4) == 0 )
  {
    v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(v11, &v18);
    v14 = v18;
  }
  WORD2(v17) = 3;
  LODWORD(v17) = 0;
  wil::details::ReportUsageToService(&qword_1800337F8, 57048218, (v14 >> 10) & 1, (v14 >> 11) & 1, &v17, 1, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53100197>::GetImpl'::`2'::impl);
  v13 = IsEnabled != 0;
  if ( v12 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_19:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800145c0  mov     [rsp+arg_10], rbx
0x1800145c5  mov     [rsp+arg_0], rcx
0x1800145ca  push    rbp
0x1800145cb  push    rsi
0x1800145cc  push    rdi
0x1800145cd  sub     rsp, 40h
0x1800145d1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800145d8  mov     rbx, rdx
0x1800145db  test    rax, rax
0x1800145de  jz      short loc_1800145F3
0x1800145e0  mov     edx, 3
0x1800145e5  mov     ecx, 3536104h
0x1800145ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145ef  mov     edx, eax
0x1800145f1  jmp     short loc_180014601
0x1800145f3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800145fa  test    rax, rax
0x1800145fd  jnz     short loc_1800145E0
0x1800145ff  xor     edx, edx
0x180014601  mov     r8d, edx
0x180014604  mov     qword ptr [rbx], 0
0x18001460b  and     r8d, 0FFFFFF3Fh
0x180014612  mov     eax, edx
0x180014614  and     edx, 80h
0x18001461a  mov     ecx, r8d
0x18001461d  and     ecx, 3
0x180014620  mov     ebp, 40h ; '@'
0x180014625  shl     ecx, 2
0x180014628  and     eax, ebp
0x18001462a  or      ecx, eax
0x18001462c  shl     ecx, 2
0x18001462f  or      ecx, edx
0x180014631  shl     ecx, 3
0x180014634  test    r8d, r8d
0x180014637  jnz     short loc_180014640
0x180014639  mov     edx, ebp
0x18001463b  mov     r8d, ebp
0x18001463e  jmp     short loc_18001464C
0x180014640  xor     edx, edx
0x180014642  cmp     r8d, 2
0x180014646  cmovz   edx, ebp
0x180014649  mov     r8d, edx
0x18001464c  mov     eax, ecx
0x18001464e  mov     edi, 1
0x180014653  or      eax, r8d
0x180014656  or      ecx, edx
0x180014658  mov     [rbx], eax
0x18001465a  bt      ecx, 0Ah
0x18001465e  jnb     short loc_18001466D
0x180014660  cmp     ecx, 800h
0x180014666  jb      short loc_18001466D
0x180014668  mov     sil, dil
0x18001466b  jmp     short loc_18001467B
0x18001466d  xor     sil, sil
0x180014670  xor     dl, dl
0x180014672  test    bpl, cl
0x180014675  jz      loc_1800146FF
0x18001467b  mov     rax, cs:Feature_UxLabTest__descriptor
0x180014682  mov     r8d, [rax]
0x180014685  test    r8b, 4
0x180014689  jnz     short loc_1800146A0
0x18001468b  lea     rdx, [rsp+58h+arg_8]
0x180014690  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)
0x180014695  mov     rcx, [rax]
0x180014698  mov     [rsp+58h+arg_8], rcx
0x18001469d  mov     r8d, ecx
0x1800146a0  xor     eax, eax
0x1800146a2  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800146a9  mov     r9d, r8d
0x1800146ac  mov     [rsp+58h+var_28], eax
0x1800146b0  mov     dword ptr [rsp+58h+arg_0], eax
0x1800146b4  lea     rcx, qword_1800337F8
0x1800146bb  shr     r9d, 0Bh
0x1800146bf  lea     rax, [rsp+58h+arg_0]
0x1800146c4  shr     r8d, 0Ah
0x1800146c8  and     r9d, edi
0x1800146cb  and     r8d, edi
0x1800146ce  mov     [rsp+58h+var_30], edi
0x1800146d2  mov     edx, 3667C9Ah
0x1800146d7  mov     [rsp+58h+var_38], rax
0x1800146dc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800146e1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53100197@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53100197@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197> `wil::Feature<__WilFeatureTraits_Feature_53100197>::GetImpl(void)'::`2'::impl
0x1800146e8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53100197@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::__private_IsEnabled(wil::ReportingKind)
0x1800146ed  test    al, al
0x1800146ef  setnz   dl
0x1800146f2  test    sil, sil
0x1800146f5  jz      short loc_1800146FF
0x1800146f7  test    dl, dl
0x1800146f9  jnz     short loc_1800146FF
0x1800146fb  btr     dword ptr [rbx], 0Ah
0x1800146ff  mov     eax, [rbx]
0x180014701  test    bpl, al
0x180014704  jz      short loc_18001470A
0x180014706  test    dl, dl
0x180014708  jnz     short loc_18001470C
0x18001470a  xor     edi, edi
0x18001470c  and     eax, 0FFFFFFFEh
0x18001470f  or      eax, edi
0x180014711  mov     [rbx], eax
0x180014713  mov     rax, rbx
0x180014716  mov     rbx, [rsp+58h+arg_10]
0x18001471b  add     rsp, 40h
0x18001471f  pop     rdi
0x180014720  pop     rsi
0x180014721  pop     rbp
0x180014722  retn
```
