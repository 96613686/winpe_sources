# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001b81c`
- end: `0x18001b8db`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ad9c`

## callees

- `0x1800162fc`
- `0x18001b81c`
- `0x18001c8e8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37767A9, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl);
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
0x18001b81c  push    rbx
0x18001b81e  push    rbp
0x18001b81f  push    rsi
0x18001b820  push    rdi
0x18001b821  sub     rsp, 28h
0x18001b825  mov     ecx, 37767A9h; this
0x18001b82a  mov     rbx, rdx
0x18001b82d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001b832  mov     edx, eax
0x18001b834  mov     qword ptr [rbx], 0
0x18001b83b  and     edx, 0FFFFFF3Fh
0x18001b841  mov     ecx, eax
0x18001b843  and     eax, 80h
0x18001b848  mov     r8d, edx
0x18001b84b  and     r8d, 3
0x18001b84f  mov     ebp, 40h ; '@'
0x18001b854  shl     r8d, 2
0x18001b858  and     ecx, ebp
0x18001b85a  or      r8d, ecx
0x18001b85d  shl     r8d, 2
0x18001b861  or      r8d, eax
0x18001b864  shl     r8d, 3
0x18001b868  test    edx, edx
0x18001b86a  jnz     short loc_18001B870
0x18001b86c  mov     eax, ebp
0x18001b86e  jmp     short loc_18001B878
0x18001b870  xor     eax, eax
0x18001b872  cmp     edx, 2
0x18001b875  cmovz   eax, ebp
0x18001b878  or      r8d, eax
0x18001b87b  mov     edi, 1
0x18001b880  mov     [rbx], r8d
0x18001b883  bt      r8d, 0Ah
0x18001b888  jnb     short loc_18001B898
0x18001b88a  cmp     r8d, 800h
0x18001b891  jb      short loc_18001B898
0x18001b893  mov     sil, dil
0x18001b896  jmp     short loc_18001B8A2
0x18001b898  xor     sil, sil
0x18001b89b  xor     al, al
0x18001b89d  test    bpl, r8b
0x18001b8a0  jz      short loc_18001B8BB
0x18001b8a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001b8a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001b8ae  test    sil, sil
0x18001b8b1  jz      short loc_18001B8BB
0x18001b8b3  test    al, al
0x18001b8b5  jnz     short loc_18001B8BB
0x18001b8b7  btr     dword ptr [rbx], 0Ah
0x18001b8bb  mov     ecx, [rbx]
0x18001b8bd  test    bpl, cl
0x18001b8c0  jz      short loc_18001B8C6
0x18001b8c2  test    al, al
0x18001b8c4  jnz     short loc_18001B8C8
0x18001b8c6  xor     edi, edi
0x18001b8c8  and     ecx, 0FFFFFFFEh
0x18001b8cb  mov     rax, rbx
0x18001b8ce  or      ecx, edi
0x18001b8d0  mov     [rbx], ecx
0x18001b8d2  add     rsp, 28h
0x18001b8d6  pop     rdi
0x18001b8d7  pop     rsi
0x18001b8d8  pop     rbp
0x18001b8d9  pop     rbx
0x18001b8da  retn
```
