# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18000886c`
- end: `0x1800089e3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `375`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b40`
- `0x180008f18`
- `0x1800091a8`
- `0x1800092f0`

## callees

- `0x18000787c`
- `0x18000886c`
- `0x180010684`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000886c  mov     [rsp+arg_8], rbx
0x180008871  mov     [rsp+arg_10], rbp
0x180008876  mov     [rsp+arg_0], rcx
0x18000887b  push    rsi
0x18000887c  push    rdi
0x18000887d  push    r15
0x18000887f  sub     rsp, 20h
0x180008883  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18000888a  mov     rbx, rdx
0x18000888d  mov     qword ptr [rdx], 0
0x180008894  mov     eax, [rsi]
0x180008896  mov     [rdx], eax
0x180008898  and     eax, 6
0x18000889b  cmp     al, 6
0x18000889d  jz      loc_1800089CD
0x1800088a3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800088a8  mov     ebp, eax
0x1800088aa  mov     dword ptr [rsp+38h+arg_0], 0
0x1800088b2  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800088b9  test    rax, rax
0x1800088bc  jz      short loc_1800088D6
0x1800088be  lea     r8, [rsp+38h+arg_0]
0x1800088c3  mov     edx, 3
0x1800088c8  mov     ecx, 2F29A04h
0x1800088cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088d2  mov     edx, eax
0x1800088d4  jmp     short loc_1800088E4
0x1800088d6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800088dd  test    rax, rax
0x1800088e0  jnz     short loc_1800088BE
0x1800088e2  xor     edx, edx
0x1800088e4  mov     r8d, edx
0x1800088e7  mov     eax, edx
0x1800088e9  and     r8d, 0FFFFFF3Fh
0x1800088f0  and     edx, 80h
0x1800088f6  mov     ecx, r8d
0x1800088f9  mov     r15d, 40h ; '@'
0x1800088ff  and     ecx, 3
0x180008902  and     eax, r15d
0x180008905  shl     ecx, 2
0x180008908  or      ecx, eax
0x18000890a  shl     ecx, 2
0x18000890d  or      ecx, edx
0x18000890f  lea     edi, ds:0[rcx*8]
0x180008916  test    r8d, r8d
0x180008919  jnz     short loc_180008920
0x18000891b  mov     eax, r15d
0x18000891e  jmp     short loc_18000892A
0x180008920  xor     eax, eax
0x180008922  cmp     r8d, 2
0x180008926  cmovz   eax, r15d
0x18000892a  or      edi, eax
0x18000892c  mov     eax, [rbx]
0x18000892e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180008933  mov     edx, eax
0x180008935  mov     [rbx], eax
0x180008937  jz      short loc_180008967
0x180008939  test    dl, 2
0x18000893c  jnz     short loc_180008967
0x18000893e  mov     eax, edi
0x180008940  xor     eax, edx
0x180008942  and     eax, 180h
0x180008947  xor     eax, edx
0x180008949  mov     ecx, eax
0x18000894b  xor     ecx, edi
0x18000894d  and     ecx, r15d
0x180008950  xor     ecx, eax
0x180008952  or      ecx, 1
0x180008955  mov     eax, ecx
0x180008957  xor     eax, edi
0x180008959  and     eax, 800h
0x18000895e  xor     eax, ecx
0x180008960  or      eax, 2
0x180008963  mov     [rbx], eax
0x180008965  jmp     short loc_180008969
0x180008967  mov     eax, edx
0x180008969  mov     r8d, edx
0x18000896c  and     r8d, 4
0x180008970  jnz     short loc_180008985
0x180008972  mov     ecx, edi
0x180008974  xor     ecx, eax
0x180008976  and     ecx, 400h
0x18000897c  xor     ecx, eax
0x18000897e  or      ecx, 4
0x180008981  mov     [rbx], ecx
0x180008983  jmp     short loc_180008987
0x180008985  mov     ecx, eax
0x180008987  mov     eax, edx
0x180008989  lock cmpxchg [rsi], ecx
0x18000898d  jnz     short loc_18000892E
0x18000898f  test    r8d, r8d
0x180008992  jnz     short loc_1800089A4
0x180008994  mov     r8d, ebp
0x180008997  mov     edx, 3
0x18000899c  mov     rcx, rsi
0x18000899f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800089a4  test    byte ptr [rbx], 2
0x1800089a7  jnz     short loc_1800089CD
0x1800089a9  mov     eax, [rbx]
0x1800089ab  xor     eax, edi
0x1800089ad  and     eax, 180h
0x1800089b2  xor     eax, [rbx]
0x1800089b4  mov     ecx, eax
0x1800089b6  xor     ecx, edi
0x1800089b8  and     ecx, r15d
0x1800089bb  xor     ecx, eax
0x1800089bd  or      ecx, 1
0x1800089c0  mov     eax, ecx
0x1800089c2  xor     eax, edi
0x1800089c4  and     eax, 800h
0x1800089c9  xor     eax, ecx
0x1800089cb  mov     [rbx], eax
0x1800089cd  mov     rbp, [rsp+38h+arg_10]
0x1800089d2  mov     rax, rbx
0x1800089d5  mov     rbx, [rsp+38h+arg_8]
0x1800089da  add     rsp, 20h
0x1800089de  pop     r15
0x1800089e0  pop     rdi
0x1800089e1  pop     rsi
0x1800089e2  retn
```
