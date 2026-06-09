# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ca40`
- end: `0x18000cb02`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000c898`

## callees

- `0x18000a640`
- `0x18000b0a4`
- `0x18000ca40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreUpdateTelemetryEvent>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3772E01, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl'::`2'::impl);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000ca40  mov     [rsp+arg_0], rbx
0x18000ca45  mov     [rsp+arg_8], rsi
0x18000ca4a  push    rdi
0x18000ca4b  sub     rsp, 20h
0x18000ca4f  mov     ecx, 3772E01h; this
0x18000ca54  mov     rbx, rdx
0x18000ca57  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000ca5c  mov     edx, eax
0x18000ca5e  mov     qword ptr [rbx], 0
0x18000ca65  and     edx, 0FFFFFF3Fh
0x18000ca6b  mov     ecx, eax
0x18000ca6d  and     eax, 80h
0x18000ca72  mov     r8d, edx
0x18000ca75  and     r8d, 3
0x18000ca79  mov     esi, 40h ; '@'
0x18000ca7e  shl     r8d, 2
0x18000ca82  and     ecx, esi
0x18000ca84  or      r8d, ecx
0x18000ca87  shl     r8d, 2
0x18000ca8b  or      r8d, eax
0x18000ca8e  shl     r8d, 3
0x18000ca92  test    edx, edx
0x18000ca94  jnz     short loc_18000CA9C
0x18000ca96  mov     ecx, esi
0x18000ca98  mov     edx, esi
0x18000ca9a  jmp     short loc_18000CAA6
0x18000ca9c  xor     ecx, ecx
0x18000ca9e  cmp     edx, 2
0x18000caa1  cmovz   ecx, esi
0x18000caa4  mov     edx, ecx
0x18000caa6  mov     eax, r8d
0x18000caa9  mov     edi, 1
0x18000caae  or      eax, edx
0x18000cab0  or      r8d, ecx
0x18000cab3  mov     [rbx], eax
0x18000cab5  bt      r8d, 0Ah
0x18000caba  jnb     short loc_18000CAC5
0x18000cabc  cmp     r8d, 800h
0x18000cac3  jnb     short loc_18000CACC
0x18000cac5  xor     cl, cl
0x18000cac7  test    sil, r8b
0x18000caca  jz      short loc_18000CADB
0x18000cacc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x18000cad3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000cad8  mov     cl, dil
0x18000cadb  mov     eax, [rbx]
0x18000cadd  test    sil, al
0x18000cae0  jz      short loc_18000CAE6
0x18000cae2  test    cl, cl
0x18000cae4  jnz     short loc_18000CAE8
0x18000cae6  xor     edi, edi
0x18000cae8  mov     rsi, [rsp+28h+arg_8]
0x18000caed  and     eax, 0FFFFFFFEh
0x18000caf0  or      eax, edi
0x18000caf2  mov     [rbx], eax
0x18000caf4  mov     rax, rbx
0x18000caf7  mov     rbx, [rsp+28h+arg_0]
0x18000cafc  add     rsp, 20h
0x18000cb00  pop     rdi
0x18000cb01  retn
```
