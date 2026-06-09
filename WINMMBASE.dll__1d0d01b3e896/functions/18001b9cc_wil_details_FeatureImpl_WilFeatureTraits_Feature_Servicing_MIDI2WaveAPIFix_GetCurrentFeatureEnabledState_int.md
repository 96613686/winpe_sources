# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001b9cc`
- end: `0x18001ba8b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001af5c`

## callees

- `0x1800162fc`
- `0x18001b9cc`
- `0x18001c834`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38E5A18, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18001b9cc  push    rbx
0x18001b9ce  push    rbp
0x18001b9cf  push    rsi
0x18001b9d0  push    rdi
0x18001b9d1  sub     rsp, 28h
0x18001b9d5  mov     ecx, 38E5A18h; this
0x18001b9da  mov     rbx, rdx
0x18001b9dd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001b9e2  mov     edx, eax
0x18001b9e4  mov     qword ptr [rbx], 0
0x18001b9eb  and     edx, 0FFFFFF3Fh
0x18001b9f1  mov     ecx, eax
0x18001b9f3  and     eax, 80h
0x18001b9f8  mov     r8d, edx
0x18001b9fb  and     r8d, 3
0x18001b9ff  mov     ebp, 40h ; '@'
0x18001ba04  shl     r8d, 2
0x18001ba08  and     ecx, ebp
0x18001ba0a  or      r8d, ecx
0x18001ba0d  shl     r8d, 2
0x18001ba11  or      r8d, eax
0x18001ba14  shl     r8d, 3
0x18001ba18  test    edx, edx
0x18001ba1a  jnz     short loc_18001BA20
0x18001ba1c  mov     eax, ebp
0x18001ba1e  jmp     short loc_18001BA28
0x18001ba20  xor     eax, eax
0x18001ba22  cmp     edx, 2
0x18001ba25  cmovz   eax, ebp
0x18001ba28  or      r8d, eax
0x18001ba2b  mov     edi, 1
0x18001ba30  mov     [rbx], r8d
0x18001ba33  bt      r8d, 0Ah
0x18001ba38  jnb     short loc_18001BA48
0x18001ba3a  cmp     r8d, 800h
0x18001ba41  jb      short loc_18001BA48
0x18001ba43  mov     sil, dil
0x18001ba46  jmp     short loc_18001BA52
0x18001ba48  xor     sil, sil
0x18001ba4b  xor     al, al
0x18001ba4d  test    bpl, r8b
0x18001ba50  jz      short loc_18001BA6B
0x18001ba52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2602@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2602>::GetImpl(void)'::`2'::impl
0x18001ba59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::__private_IsEnabled(wil::ReportingKind)
0x18001ba5e  test    sil, sil
0x18001ba61  jz      short loc_18001BA6B
0x18001ba63  test    al, al
0x18001ba65  jnz     short loc_18001BA6B
0x18001ba67  btr     dword ptr [rbx], 0Ah
0x18001ba6b  mov     ecx, [rbx]
0x18001ba6d  test    bpl, cl
0x18001ba70  jz      short loc_18001BA76
0x18001ba72  test    al, al
0x18001ba74  jnz     short loc_18001BA78
0x18001ba76  xor     edi, edi
0x18001ba78  and     ecx, 0FFFFFFFEh
0x18001ba7b  mov     rax, rbx
0x18001ba7e  or      ecx, edi
0x18001ba80  mov     [rbx], ecx
0x18001ba82  add     rsp, 28h
0x18001ba86  pop     rdi
0x18001ba87  pop     rsi
0x18001ba88  pop     rbp
0x18001ba89  pop     rbx
0x18001ba8a  retn
```
