# wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005ed0`
- end: `0x180005f8f`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005304`

## callees

- `0x180005ed0`
- `0x18000a544`
- `0x18000aa24`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_StateRepository_SRCacheContextCacheLeak>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x274777D, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
0x180005ed0  push    rbx
0x180005ed2  push    rbp
0x180005ed3  push    rsi
0x180005ed4  push    rdi
0x180005ed5  sub     rsp, 28h
0x180005ed9  mov     ecx, 274777Dh; this
0x180005ede  mov     rbx, rdx
0x180005ee1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005ee6  mov     edx, eax
0x180005ee8  mov     qword ptr [rbx], 0
0x180005eef  and     edx, 0FFFFFF3Fh
0x180005ef5  mov     ecx, eax
0x180005ef7  and     eax, 80h
0x180005efc  mov     r8d, edx
0x180005eff  and     r8d, 3
0x180005f03  mov     ebp, 40h ; '@'
0x180005f08  shl     r8d, 2
0x180005f0c  and     ecx, ebp
0x180005f0e  or      r8d, ecx
0x180005f11  shl     r8d, 2
0x180005f15  or      r8d, eax
0x180005f18  shl     r8d, 3
0x180005f1c  test    edx, edx
0x180005f1e  jnz     short loc_180005F24
0x180005f20  mov     eax, ebp
0x180005f22  jmp     short loc_180005F2C
0x180005f24  xor     eax, eax
0x180005f26  cmp     edx, 2
0x180005f29  cmovz   eax, ebp
0x180005f2c  or      r8d, eax
0x180005f2f  mov     edi, 1
0x180005f34  mov     [rbx], r8d
0x180005f37  bt      r8d, 0Ah
0x180005f3c  jnb     short loc_180005F4C
0x180005f3e  cmp     r8d, 800h
0x180005f45  jb      short loc_180005F4C
0x180005f47  mov     sil, dil
0x180005f4a  jmp     short loc_180005F56
0x180005f4c  xor     sil, sil
0x180005f4f  xor     al, al
0x180005f51  test    bpl, r8b
0x180005f54  jz      short loc_180005F6F
0x180005f56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x180005f5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180005f62  test    sil, sil
0x180005f65  jz      short loc_180005F6F
0x180005f67  test    al, al
0x180005f69  jnz     short loc_180005F6F
0x180005f6b  btr     dword ptr [rbx], 0Ah
0x180005f6f  mov     ecx, [rbx]
0x180005f71  test    bpl, cl
0x180005f74  jz      short loc_180005F7A
0x180005f76  test    al, al
0x180005f78  jnz     short loc_180005F7C
0x180005f7a  xor     edi, edi
0x180005f7c  and     ecx, 0FFFFFFFEh
0x180005f7f  mov     rax, rbx
0x180005f82  or      ecx, edi
0x180005f84  mov     [rbx], ecx
0x180005f86  add     rsp, 28h
0x180005f8a  pop     rdi
0x180005f8b  pop     rsi
0x180005f8c  pop     rbp
0x180005f8d  pop     rbx
0x180005f8e  retn
```
