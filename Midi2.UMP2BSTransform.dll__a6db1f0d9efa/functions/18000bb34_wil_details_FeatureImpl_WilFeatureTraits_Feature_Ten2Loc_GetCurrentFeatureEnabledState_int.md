# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000bb34`
- end: `0x18000bc9d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b554`

## callees

- `0x18000b26c`
- `0x18000bb34`
- `0x18000c804`
- `0x18000df50`
- `0x18000f010`

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
      (__int64)&qword_180015818,
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
0x18000bb34  mov     [rsp+arg_10], rbx
0x18000bb39  mov     [rsp+arg_0], rcx
0x18000bb3e  push    rbp
0x18000bb3f  push    rsi
0x18000bb40  push    rdi
0x18000bb41  sub     rsp, 40h
0x18000bb45  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000bb4c  mov     rbx, rdx
0x18000bb4f  test    rax, rax
0x18000bb52  jz      short loc_18000BB67
0x18000bb54  mov     edx, 3
0x18000bb59  mov     ecx, 38419CAh
0x18000bb5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb63  mov     edx, eax
0x18000bb65  jmp     short loc_18000BB75
0x18000bb67  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000bb6e  test    rax, rax
0x18000bb71  jnz     short loc_18000BB54
0x18000bb73  xor     edx, edx
0x18000bb75  mov     r8d, edx
0x18000bb78  mov     qword ptr [rbx], 0
0x18000bb7f  and     r8d, 0FFFFFF3Fh
0x18000bb86  mov     eax, edx
0x18000bb88  and     edx, 80h
0x18000bb8e  mov     ecx, r8d
0x18000bb91  and     ecx, 3
0x18000bb94  mov     ebp, 40h ; '@'
0x18000bb99  shl     ecx, 2
0x18000bb9c  and     eax, ebp
0x18000bb9e  or      ecx, eax
0x18000bba0  shl     ecx, 2
0x18000bba3  or      ecx, edx
0x18000bba5  shl     ecx, 3
0x18000bba8  test    r8d, r8d
0x18000bbab  jnz     short loc_18000BBB4
0x18000bbad  mov     edx, ebp
0x18000bbaf  mov     r8d, ebp
0x18000bbb2  jmp     short loc_18000BBC0
0x18000bbb4  xor     edx, edx
0x18000bbb6  cmp     r8d, 2
0x18000bbba  cmovz   edx, ebp
0x18000bbbd  mov     r8d, edx
0x18000bbc0  mov     eax, ecx
0x18000bbc2  mov     edi, 1
0x18000bbc7  or      eax, r8d
0x18000bbca  or      ecx, edx
0x18000bbcc  mov     [rbx], eax
0x18000bbce  bt      ecx, 0Ah
0x18000bbd2  jnb     short loc_18000BBE1
0x18000bbd4  cmp     ecx, 800h
0x18000bbda  jb      short loc_18000BBE1
0x18000bbdc  mov     sil, dil
0x18000bbdf  jmp     short loc_18000BBEF
0x18000bbe1  xor     sil, sil
0x18000bbe4  xor     dl, dl
0x18000bbe6  test    bpl, cl
0x18000bbe9  jz      loc_18000BC79
0x18000bbef  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18000bbf6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18000bbfb  test    al, al
0x18000bbfd  jz      short loc_18000BC6A
0x18000bbff  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000bc06  mov     r8d, [rax]
0x18000bc09  test    r8b, 4
0x18000bc0d  jnz     short loc_18000BC24
0x18000bc0f  lea     rdx, [rsp+58h+arg_8]
0x18000bc14  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18000bc19  mov     rcx, [rax]
0x18000bc1c  mov     [rsp+58h+arg_8], rcx
0x18000bc21  mov     r8d, ecx
0x18000bc24  xor     eax, eax
0x18000bc26  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000bc2d  mov     r9d, r8d
0x18000bc30  mov     [rsp+58h+var_28], eax
0x18000bc34  mov     dword ptr [rsp+58h+arg_0], eax
0x18000bc38  lea     rcx, qword_180015818
0x18000bc3f  shr     r9d, 0Bh
0x18000bc43  lea     rax, [rsp+58h+arg_0]
0x18000bc48  shr     r8d, 0Ah
0x18000bc4c  and     r9d, edi
0x18000bc4f  and     r8d, edi
0x18000bc52  mov     [rsp+58h+var_30], edi
0x18000bc56  mov     edx, 37E287Eh
0x18000bc5b  mov     [rsp+58h+var_38], rax
0x18000bc60  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000bc65  mov     dl, dil
0x18000bc68  jmp     short loc_18000BC6C
0x18000bc6a  xor     dl, dl
0x18000bc6c  test    sil, sil
0x18000bc6f  jz      short loc_18000BC79
0x18000bc71  test    dl, dl
0x18000bc73  jnz     short loc_18000BC79
0x18000bc75  btr     dword ptr [rbx], 0Ah
0x18000bc79  mov     eax, [rbx]
0x18000bc7b  test    bpl, al
0x18000bc7e  jz      short loc_18000BC84
0x18000bc80  test    dl, dl
0x18000bc82  jnz     short loc_18000BC86
0x18000bc84  xor     edi, edi
0x18000bc86  and     eax, 0FFFFFFFEh
0x18000bc89  or      eax, edi
0x18000bc8b  mov     [rbx], eax
0x18000bc8d  mov     rax, rbx
0x18000bc90  mov     rbx, [rsp+58h+arg_10]
0x18000bc95  add     rsp, 40h
0x18000bc99  pop     rdi
0x18000bc9a  pop     rsi
0x18000bc9b  pop     rbp
0x18000bc9c  retn
```
