# wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000c978`
- end: `0x18000ca3a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000c7b8`

## callees

- `0x18000a534`
- `0x18000b0a4`
- `0x18000c978`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x375DAD7, (unsigned int)a2, a3, a4);
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_UxLabTest>::GetImpl'::`2'::impl);
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
0x18000c978  mov     [rsp+arg_0], rbx
0x18000c97d  mov     [rsp+arg_8], rsi
0x18000c982  push    rdi
0x18000c983  sub     rsp, 20h
0x18000c987  mov     ecx, 375DAD7h; this
0x18000c98c  mov     rbx, rdx
0x18000c98f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000c994  mov     edx, eax
0x18000c996  mov     qword ptr [rbx], 0
0x18000c99d  and     edx, 0FFFFFF3Fh
0x18000c9a3  mov     ecx, eax
0x18000c9a5  and     eax, 80h
0x18000c9aa  mov     r8d, edx
0x18000c9ad  and     r8d, 3
0x18000c9b1  mov     esi, 40h ; '@'
0x18000c9b6  shl     r8d, 2
0x18000c9ba  and     ecx, esi
0x18000c9bc  or      r8d, ecx
0x18000c9bf  shl     r8d, 2
0x18000c9c3  or      r8d, eax
0x18000c9c6  shl     r8d, 3
0x18000c9ca  test    edx, edx
0x18000c9cc  jnz     short loc_18000C9D4
0x18000c9ce  mov     ecx, esi
0x18000c9d0  mov     edx, esi
0x18000c9d2  jmp     short loc_18000C9DE
0x18000c9d4  xor     ecx, ecx
0x18000c9d6  cmp     edx, 2
0x18000c9d9  cmovz   ecx, esi
0x18000c9dc  mov     edx, ecx
0x18000c9de  mov     eax, r8d
0x18000c9e1  mov     edi, 1
0x18000c9e6  or      eax, edx
0x18000c9e8  or      r8d, ecx
0x18000c9eb  mov     [rbx], eax
0x18000c9ed  bt      r8d, 0Ah
0x18000c9f2  jnb     short loc_18000C9FD
0x18000c9f4  cmp     r8d, 800h
0x18000c9fb  jnb     short loc_18000CA04
0x18000c9fd  xor     cl, cl
0x18000c9ff  test    sil, r8b
0x18000ca02  jz      short loc_18000CA13
0x18000ca04  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest> `wil::Feature<__WilFeatureTraits_Feature_UxLabTest>::GetImpl(void)'::`2'::impl
0x18000ca0b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000ca10  mov     cl, dil
0x18000ca13  mov     eax, [rbx]
0x18000ca15  test    sil, al
0x18000ca18  jz      short loc_18000CA1E
0x18000ca1a  test    cl, cl
0x18000ca1c  jnz     short loc_18000CA20
0x18000ca1e  xor     edi, edi
0x18000ca20  mov     rsi, [rsp+28h+arg_8]
0x18000ca25  and     eax, 0FFFFFFFEh
0x18000ca28  or      eax, edi
0x18000ca2a  mov     [rbx], eax
0x18000ca2c  mov     rax, rbx
0x18000ca2f  mov     rbx, [rsp+28h+arg_0]
0x18000ca34  add     rsp, 20h
0x18000ca38  pop     rdi
0x18000ca39  retn
```
