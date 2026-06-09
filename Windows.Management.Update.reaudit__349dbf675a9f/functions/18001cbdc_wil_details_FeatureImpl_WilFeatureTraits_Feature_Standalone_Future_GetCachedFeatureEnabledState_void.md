# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001cbdc`
- end: `0x18001cd74`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dac0`

## callees

- `0x18000b284`
- `0x18000f6bc`
- `0x18001cbdc`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 (__fastcall *v6)(__int64, __int64, int *); // rax
  int v7; // edx
  int v8; // ebx
  int v9; // eax
  char v10; // cl
  int v11; // eax
  signed __int32 v12; // edx
  int v13; // ebx
  bool v14; // zf
  signed __int32 v15; // ecx
  signed __int32 v16; // eax
  int v17; // eax
  int v19; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v19 = 0;
  v5 = v4;
  v6 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(49453572, 3, &v19);
  }
  else
  {
    v7 = 0;
  }
  v8 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
  if ( (v7 & 0xFFFFFF3F) != 0 )
  {
    v9 = 0;
    if ( (v7 & 0xFFFFFF3F) == 2 )
      v9 = 64;
    v8 |= v9;
  }
  v10 = 0;
  if ( (v8 & 0xC00) == 0xC00 )
  {
    v10 = 1;
  }
  else if ( (v8 & 0x40) != 0 )
  {
    goto LABEL_16;
  }
  if ( (v8 & 0x40) == 0 || !v10 )
  {
    v11 = 0;
    goto LABEL_17;
  }
LABEL_16:
  v11 = 1;
LABEL_17:
  v12 = *(_DWORD *)a2;
  v13 = v11 | v8;
  while ( 1 )
  {
    v14 = v19 == 0;
    v15 = v12;
    *(_DWORD *)a2 = v12;
    if ( !v14 && (v12 & 2) == 0 )
    {
      v15 = v12
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v13)
          & 0x180
          ^ (v13
           ^ v12
           ^ ((unsigned __int16)v12
            ^ (unsigned __int16)v13)
           & 0x180)
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
          & 1
          ^ ((unsigned __int16)v13
           ^ (unsigned __int16)(v12
                              ^ (v12
                               ^ v13)
                              & 0x180
                              ^ (v13
                               ^ v12
                               ^ (v12
                                ^ v13)
                               & 0x180)
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v12 ^ (v12 ^ v13) & 0x80 ^ (v13 ^ v12 ^ (v12 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    if ( (v12 & 4) == 0 )
    {
      v15 = ((unsigned __int16)v15 ^ (unsigned __int16)v13) & 0x400 ^ v15 | 4;
      *(_DWORD *)a2 = v15;
    }
    v16 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v15, v12);
    if ( v12 == v16 )
      break;
    v12 = v16;
  }
  if ( (v12 & 4) == 0 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v5);
  if ( (*(_BYTE *)a2 & 2) == 0 )
  {
    v17 = *(_DWORD *)a2 ^ (*(_DWORD *)a2 ^ v13) & 0x180;
    *(_DWORD *)a2 = v17
                  ^ (v17
                   ^ v13)
                  & 0x40
                  ^ ((unsigned __int8)v13
                   ^ (unsigned __int8)(v17 ^ (v17 ^ v13) & 0x40))
                  & 1
                  ^ ((unsigned __int16)v13
                   ^ (unsigned __int16)(v17
                                      ^ (v17
                                       ^ v13)
                                      & 0x40
                                      ^ ((unsigned __int8)v13
                                       ^ (unsigned __int8)(v17 ^ (v17 ^ v13) & 0x40))
                                      & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18001cbdc  mov     [rsp+arg_0], rbx
0x18001cbe1  mov     [rsp+arg_10], rbp
0x18001cbe6  push    rsi
0x18001cbe7  push    rdi
0x18001cbe8  push    r15
0x18001cbea  sub     rsp, 20h
0x18001cbee  and     qword ptr [rdx], 0
0x18001cbf2  mov     rdi, rdx
0x18001cbf5  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001cbfc  mov     eax, [rsi]
0x18001cbfe  mov     [rdx], eax
0x18001cc00  and     eax, 6
0x18001cc03  cmp     al, 6
0x18001cc05  jz      loc_18001CD5D
0x18001cc0b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001cc10  and     [rsp+38h+arg_8], 0
0x18001cc15  mov     ebp, eax
0x18001cc17  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001cc1e  test    rax, rax
0x18001cc21  jz      short loc_18001CC3B
0x18001cc23  lea     r8, [rsp+38h+arg_8]
0x18001cc28  mov     edx, 3
0x18001cc2d  mov     ecx, 2F29A04h
0x18001cc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc37  mov     edx, eax
0x18001cc39  jmp     short loc_18001CC49
0x18001cc3b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001cc42  test    rax, rax
0x18001cc45  jnz     short loc_18001CC23
0x18001cc47  xor     edx, edx
0x18001cc49  mov     r8d, edx
0x18001cc4c  mov     eax, edx
0x18001cc4e  and     r8d, 0FFFFFF3Fh
0x18001cc55  and     edx, 80h
0x18001cc5b  mov     ecx, r8d
0x18001cc5e  mov     r15d, 40h ; '@'
0x18001cc64  and     ecx, 3
0x18001cc67  and     eax, r15d
0x18001cc6a  shl     ecx, 2
0x18001cc6d  or      ecx, eax
0x18001cc6f  shl     ecx, 2
0x18001cc72  or      ecx, edx
0x18001cc74  lea     ebx, ds:0[rcx*8]
0x18001cc7b  test    r8d, r8d
0x18001cc7e  jz      short loc_18001CC8C
0x18001cc80  xor     eax, eax
0x18001cc82  cmp     r8d, 2
0x18001cc86  cmovz   eax, r15d
0x18001cc8a  or      ebx, eax
0x18001cc8c  mov     edx, 0C00h
0x18001cc91  mov     eax, ebx
0x18001cc93  and     eax, edx
0x18001cc95  xor     cl, cl
0x18001cc97  cmp     eax, edx
0x18001cc99  jnz     short loc_18001CC9F
0x18001cc9b  mov     cl, 1
0x18001cc9d  jmp     short loc_18001CCA4
0x18001cc9f  test    r15b, bl
0x18001cca2  jnz     short loc_18001CCB1
0x18001cca4  test    r15b, bl
0x18001cca7  jz      short loc_18001CCAD
0x18001cca9  test    cl, cl
0x18001ccab  jnz     short loc_18001CCB1
0x18001ccad  xor     eax, eax
0x18001ccaf  jmp     short loc_18001CCB6
0x18001ccb1  mov     eax, 1
0x18001ccb6  mov     edx, [rdi]
0x18001ccb8  or      ebx, eax
0x18001ccba  cmp     [rsp+38h+arg_8], 0
0x18001ccbf  mov     ecx, edx
0x18001ccc1  mov     [rdi], edx
0x18001ccc3  jz      short loc_18001CCF8
0x18001ccc5  test    dl, 2
0x18001ccc8  jnz     short loc_18001CCF8
0x18001ccca  mov     eax, ebx
0x18001cccc  xor     eax, edx
0x18001ccce  and     eax, 180h
0x18001ccd3  xor     eax, edx
0x18001ccd5  mov     ecx, eax
0x18001ccd7  xor     ecx, ebx
0x18001ccd9  and     ecx, r15d
0x18001ccdc  xor     ecx, eax
0x18001ccde  mov     eax, ecx
0x18001cce0  xor     eax, ebx
0x18001cce2  and     eax, 1
0x18001cce5  xor     eax, ecx
0x18001cce7  mov     ecx, eax
0x18001cce9  xor     ecx, ebx
0x18001cceb  and     ecx, 800h
0x18001ccf1  xor     ecx, eax
0x18001ccf3  or      ecx, 2
0x18001ccf6  mov     [rdi], ecx
0x18001ccf8  test    dl, 4
0x18001ccfb  jnz     short loc_18001CD0D
0x18001ccfd  mov     eax, ebx
0x18001ccff  xor     eax, ecx
0x18001cd01  and     eax, 400h
0x18001cd06  xor     ecx, eax
0x18001cd08  or      ecx, 4
0x18001cd0b  mov     [rdi], ecx
0x18001cd0d  mov     eax, edx
0x18001cd0f  lock cmpxchg [rsi], ecx
0x18001cd13  jz      short loc_18001CD19
0x18001cd15  mov     edx, eax
0x18001cd17  jmp     short loc_18001CCBA
0x18001cd19  test    dl, 4
0x18001cd1c  jnz     short loc_18001CD2E
0x18001cd1e  mov     r8d, ebp
0x18001cd21  mov     edx, 3
0x18001cd26  mov     rcx, rsi
0x18001cd29  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001cd2e  test    byte ptr [rdi], 2
0x18001cd31  jnz     short loc_18001CD5D
0x18001cd33  mov     eax, ebx
0x18001cd35  mov     ecx, ebx
0x18001cd37  xor     eax, [rdi]
0x18001cd39  and     eax, 180h
0x18001cd3e  xor     eax, [rdi]
0x18001cd40  xor     ecx, eax
0x18001cd42  and     ecx, r15d
0x18001cd45  xor     ecx, eax
0x18001cd47  mov     edx, ecx
0x18001cd49  xor     edx, ebx
0x18001cd4b  and     edx, 1
0x18001cd4e  xor     edx, ecx
0x18001cd50  mov     eax, edx
0x18001cd52  xor     eax, ebx
0x18001cd54  and     eax, 800h
0x18001cd59  xor     eax, edx
0x18001cd5b  mov     [rdi], eax
0x18001cd5d  mov     rbx, [rsp+38h+arg_0]
0x18001cd62  mov     rax, rdi
0x18001cd65  mov     rbp, [rsp+38h+arg_10]
0x18001cd6a  add     rsp, 20h
0x18001cd6e  pop     r15
0x18001cd70  pop     rdi
0x18001cd71  pop     rsi
0x18001cd72  retn
```
