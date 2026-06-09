# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f524`
- end: `0x18001f676`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f824`

## callees

- `0x18000d7e0`
- `0x1800170d0`
- `0x180017994`
- `0x18001f524`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2F29A04,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v11
              ^ (unsigned __int16)v12)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v11
               ^ (unsigned __int16)v12)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v11 ^ v12) & 0x180 ^ (v11 ^ v12 ^ (v11 ^ v12) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_Future__descriptor,
        3,
        v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x18001f524  mov     [rsp+arg_8], rbx
0x18001f529  mov     [rsp+arg_10], rbp
0x18001f52e  mov     [rsp+arg_0], rcx
0x18001f533  push    rsi
0x18001f534  push    rdi
0x18001f535  push    r15
0x18001f537  sub     rsp, 20h
0x18001f53b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x18001f542  mov     rbx, rdx
0x18001f545  mov     qword ptr [rdx], 0
0x18001f54c  mov     eax, [rsi]
0x18001f54e  mov     [rdx], eax
0x18001f550  and     eax, 6
0x18001f553  cmp     al, 6
0x18001f555  jz      loc_18001F660
0x18001f55b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f560  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x18001f565  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f56d  mov     edx, 3; unsigned int
0x18001f572  mov     ecx, 2F29A04h; this
0x18001f577  mov     ebp, eax
0x18001f579  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001f57e  mov     r8d, eax
0x18001f581  mov     ecx, eax
0x18001f583  and     r8d, 0FFFFFF3Fh
0x18001f58a  and     eax, 80h
0x18001f58f  mov     edx, r8d
0x18001f592  mov     r15d, 40h ; '@'
0x18001f598  and     edx, 3
0x18001f59b  and     ecx, r15d
0x18001f59e  shl     edx, 2
0x18001f5a1  or      edx, ecx
0x18001f5a3  shl     edx, 2
0x18001f5a6  or      edx, eax
0x18001f5a8  lea     edi, ds:0[rdx*8]
0x18001f5af  test    r8d, r8d
0x18001f5b2  jnz     short loc_18001F5B9
0x18001f5b4  mov     eax, r15d
0x18001f5b7  jmp     short loc_18001F5C3
0x18001f5b9  xor     eax, eax
0x18001f5bb  cmp     r8d, 2
0x18001f5bf  cmovz   eax, r15d
0x18001f5c3  or      edi, eax
0x18001f5c5  mov     eax, [rbx]
0x18001f5c7  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f5cc  mov     edx, eax
0x18001f5ce  mov     [rbx], eax
0x18001f5d0  jz      short loc_18001F5FC
0x18001f5d2  test    dl, 2
0x18001f5d5  jnz     short loc_18001F5FC
0x18001f5d7  xor     eax, edi
0x18001f5d9  and     eax, 180h
0x18001f5de  xor     eax, edx
0x18001f5e0  mov     ecx, eax
0x18001f5e2  xor     ecx, edi
0x18001f5e4  and     ecx, r15d
0x18001f5e7  xor     ecx, eax
0x18001f5e9  or      ecx, 1
0x18001f5ec  mov     eax, ecx
0x18001f5ee  xor     eax, edi
0x18001f5f0  and     eax, 800h
0x18001f5f5  xor     eax, ecx
0x18001f5f7  or      eax, 2
0x18001f5fa  mov     [rbx], eax
0x18001f5fc  mov     r8d, edx
0x18001f5ff  and     r8d, 4
0x18001f603  jnz     short loc_18001F618
0x18001f605  mov     ecx, edi
0x18001f607  xor     ecx, eax
0x18001f609  and     ecx, 400h
0x18001f60f  xor     ecx, eax
0x18001f611  or      ecx, 4
0x18001f614  mov     [rbx], ecx
0x18001f616  jmp     short loc_18001F61A
0x18001f618  mov     ecx, eax
0x18001f61a  mov     eax, edx
0x18001f61c  lock cmpxchg [rsi], ecx
0x18001f620  jnz     short loc_18001F5C7
0x18001f622  test    r8d, r8d
0x18001f625  jnz     short loc_18001F637
0x18001f627  mov     r8d, ebp
0x18001f62a  mov     edx, 3
0x18001f62f  mov     rcx, rsi
0x18001f632  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f637  test    byte ptr [rbx], 2
0x18001f63a  jnz     short loc_18001F660
0x18001f63c  mov     eax, [rbx]
0x18001f63e  xor     eax, edi
0x18001f640  and     eax, 180h
0x18001f645  xor     eax, [rbx]
0x18001f647  mov     ecx, eax
0x18001f649  xor     ecx, edi
0x18001f64b  and     ecx, r15d
0x18001f64e  xor     ecx, eax
0x18001f650  or      ecx, 1
0x18001f653  mov     eax, ecx
0x18001f655  xor     eax, edi
0x18001f657  and     eax, 800h
0x18001f65c  xor     eax, ecx
0x18001f65e  mov     [rbx], eax
0x18001f660  mov     rbp, [rsp+38h+arg_10]
0x18001f665  mov     rax, rbx
0x18001f668  mov     rbx, [rsp+38h+arg_8]
0x18001f66d  add     rsp, 20h
0x18001f671  pop     r15
0x18001f673  pop     rdi
0x18001f674  pop     rsi
0x18001f675  retn
```
