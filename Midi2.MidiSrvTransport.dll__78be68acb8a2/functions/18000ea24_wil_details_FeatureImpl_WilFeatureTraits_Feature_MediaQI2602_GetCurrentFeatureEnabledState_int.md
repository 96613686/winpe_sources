# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ea24`
- end: `0x18000eb2c`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000dca0`

## callees

- `0x18000ea24`
- `0x1800111e4`
- `0x1800113bc`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(
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
    v4 = v2(59423145, 3);
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
  v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2511>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
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
0x18000ea24  push    rbx
0x18000ea26  push    rbp
0x18000ea27  push    rsi
0x18000ea28  push    rdi
0x18000ea29  sub     rsp, 28h
0x18000ea2d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000ea34  mov     rbx, rdx
0x18000ea37  mov     edi, 3
0x18000ea3c  test    rax, rax
0x18000ea3f  jz      short loc_18000EA51
0x18000ea41  mov     edx, edi
0x18000ea43  mov     ecx, 38AB9A9h
0x18000ea48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea4d  mov     edx, eax
0x18000ea4f  jmp     short loc_18000EA5F
0x18000ea51  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000ea58  test    rax, rax
0x18000ea5b  jnz     short loc_18000EA41
0x18000ea5d  xor     edx, edx
0x18000ea5f  mov     r8d, edx
0x18000ea62  mov     qword ptr [rbx], 0
0x18000ea69  mov     eax, edx
0x18000ea6b  and     r8d, 0FFFFFF3Fh
0x18000ea72  and     edx, 80h
0x18000ea78  mov     ecx, r8d
0x18000ea7b  and     ecx, edi
0x18000ea7d  mov     ebp, 40h ; '@'
0x18000ea82  shl     ecx, 2
0x18000ea85  and     eax, ebp
0x18000ea87  or      ecx, eax
0x18000ea89  shl     ecx, 2
0x18000ea8c  or      ecx, edx
0x18000ea8e  lea     edx, ds:0[rcx*8]
0x18000ea95  test    r8d, r8d
0x18000ea98  jnz     short loc_18000EAA1
0x18000ea9a  mov     ecx, ebp
0x18000ea9c  mov     r8d, ebp
0x18000ea9f  jmp     short loc_18000EAAD
0x18000eaa1  xor     ecx, ecx
0x18000eaa3  cmp     r8d, 2
0x18000eaa7  cmovz   ecx, ebp
0x18000eaaa  mov     r8d, ecx
0x18000eaad  mov     eax, edx
0x18000eaaf  mov     edi, 1
0x18000eab4  or      eax, r8d
0x18000eab7  or      edx, ecx
0x18000eab9  mov     [rbx], eax
0x18000eabb  bt      edx, 0Ah
0x18000eabf  jnb     short loc_18000EACE
0x18000eac1  cmp     edx, 800h
0x18000eac7  jb      short loc_18000EACE
0x18000eac9  mov     sil, dil
0x18000eacc  jmp     short loc_18000EAD8
0x18000eace  xor     sil, sil
0x18000ead1  xor     cl, cl
0x18000ead3  test    bpl, dl
0x18000ead6  jz      short loc_18000EB0C
0x18000ead8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2511>::GetImpl(void)'::`2'::impl
0x18000eadf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::__private_IsEnabled(wil::ReportingKind)
0x18000eae4  test    al, al
0x18000eae6  jz      short loc_18000EAFD
0x18000eae8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18000eaef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18000eaf4  test    al, al
0x18000eaf6  jz      short loc_18000EAFD
0x18000eaf8  mov     cl, dil
0x18000eafb  jmp     short loc_18000EAFF
0x18000eafd  xor     cl, cl
0x18000eaff  test    sil, sil
0x18000eb02  jz      short loc_18000EB0C
0x18000eb04  test    cl, cl
0x18000eb06  jnz     short loc_18000EB0C
0x18000eb08  btr     dword ptr [rbx], 0Ah
0x18000eb0c  mov     eax, [rbx]
0x18000eb0e  test    bpl, al
0x18000eb11  jz      short loc_18000EB17
0x18000eb13  test    cl, cl
0x18000eb15  jnz     short loc_18000EB19
0x18000eb17  xor     edi, edi
0x18000eb19  and     eax, 0FFFFFFFEh
0x18000eb1c  or      eax, edi
0x18000eb1e  mov     [rbx], eax
0x18000eb20  mov     rax, rbx
0x18000eb23  add     rsp, 28h
0x18000eb27  pop     rdi
0x18000eb28  pop     rsi
0x18000eb29  pop     rbp
0x18000eb2a  pop     rbx
0x18000eb2b  retn
```
