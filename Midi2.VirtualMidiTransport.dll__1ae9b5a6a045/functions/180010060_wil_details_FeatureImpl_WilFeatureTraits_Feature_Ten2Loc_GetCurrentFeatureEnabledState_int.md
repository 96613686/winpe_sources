# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010060`
- end: `0x1800101c9`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000f9a0`

## callees

- `0x18000f544`
- `0x180010060`
- `0x180011204`
- `0x180011c54`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989002, 3);
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18002DD68,
      0x37E287Eu,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180010060  mov     [rsp+arg_10], rbx
0x180010065  mov     [rsp+arg_0], rcx
0x18001006a  push    rbp
0x18001006b  push    rsi
0x18001006c  push    rdi
0x18001006d  sub     rsp, 40h
0x180010071  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180010078  mov     rbx, rdx
0x18001007b  test    rax, rax
0x18001007e  jz      short loc_180010093
0x180010080  mov     edx, 3
0x180010085  mov     ecx, 38419CAh
0x18001008a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001008f  mov     edx, eax
0x180010091  jmp     short loc_1800100A1
0x180010093  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001009a  test    rax, rax
0x18001009d  jnz     short loc_180010080
0x18001009f  xor     edx, edx
0x1800100a1  mov     r8d, edx
0x1800100a4  mov     qword ptr [rbx], 0
0x1800100ab  and     r8d, 0FFFFFF3Fh
0x1800100b2  mov     eax, edx
0x1800100b4  and     edx, 80h
0x1800100ba  mov     ecx, r8d
0x1800100bd  and     ecx, 3
0x1800100c0  mov     ebp, 40h ; '@'
0x1800100c5  shl     ecx, 2
0x1800100c8  and     eax, ebp
0x1800100ca  or      ecx, eax
0x1800100cc  shl     ecx, 2
0x1800100cf  or      ecx, edx
0x1800100d1  shl     ecx, 3
0x1800100d4  test    r8d, r8d
0x1800100d7  jnz     short loc_1800100E0
0x1800100d9  mov     edx, ebp
0x1800100db  mov     r8d, ebp
0x1800100de  jmp     short loc_1800100EC
0x1800100e0  xor     edx, edx
0x1800100e2  cmp     r8d, 2
0x1800100e6  cmovz   edx, ebp
0x1800100e9  mov     r8d, edx
0x1800100ec  mov     eax, ecx
0x1800100ee  mov     edi, 1
0x1800100f3  or      eax, r8d
0x1800100f6  or      ecx, edx
0x1800100f8  mov     [rbx], eax
0x1800100fa  bt      ecx, 0Ah
0x1800100fe  jnb     short loc_18001010D
0x180010100  cmp     ecx, 800h
0x180010106  jb      short loc_18001010D
0x180010108  mov     sil, dil
0x18001010b  jmp     short loc_18001011B
0x18001010d  xor     sil, sil
0x180010110  xor     dl, dl
0x180010112  test    bpl, cl
0x180010115  jz      loc_1800101A5
0x18001011b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180010122  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180010127  test    al, al
0x180010129  jz      short loc_180010196
0x18001012b  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180010132  mov     r8d, [rax]
0x180010135  test    r8b, 4
0x180010139  jnz     short loc_180010150
0x18001013b  lea     rdx, [rsp+58h+arg_8]
0x180010140  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180010145  mov     rcx, [rax]
0x180010148  mov     [rsp+58h+arg_8], rcx
0x18001014d  mov     r8d, ecx
0x180010150  xor     eax, eax
0x180010152  mov     word ptr [rsp+58h+arg_0+4], 3
0x180010159  mov     r9d, r8d
0x18001015c  mov     [rsp+58h+var_28], eax
0x180010160  mov     dword ptr [rsp+58h+arg_0], eax
0x180010164  lea     rcx, qword_18002DD68
0x18001016b  shr     r9d, 0Bh
0x18001016f  lea     rax, [rsp+58h+arg_0]
0x180010174  shr     r8d, 0Ah
0x180010178  and     r9d, edi
0x18001017b  and     r8d, edi
0x18001017e  mov     [rsp+58h+var_30], edi
0x180010182  mov     edx, 37E287Eh
0x180010187  mov     [rsp+58h+var_38], rax
0x18001018c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180010191  mov     dl, dil
0x180010194  jmp     short loc_180010198
0x180010196  xor     dl, dl
0x180010198  test    sil, sil
0x18001019b  jz      short loc_1800101A5
0x18001019d  test    dl, dl
0x18001019f  jnz     short loc_1800101A5
0x1800101a1  btr     dword ptr [rbx], 0Ah
0x1800101a5  mov     eax, [rbx]
0x1800101a7  test    bpl, al
0x1800101aa  jz      short loc_1800101B0
0x1800101ac  test    dl, dl
0x1800101ae  jnz     short loc_1800101B2
0x1800101b0  xor     edi, edi
0x1800101b2  and     eax, 0FFFFFFFEh
0x1800101b5  or      eax, edi
0x1800101b7  mov     [rbx], eax
0x1800101b9  mov     rax, rbx
0x1800101bc  mov     rbx, [rsp+58h+arg_10]
0x1800101c1  add     rsp, 40h
0x1800101c5  pop     rdi
0x1800101c6  pop     rsi
0x1800101c7  pop     rbp
0x1800101c8  retn
```
