# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180036f30`
- end: `0x18003709d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a28c`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036f30`
- `0x18003b548`
- `0x18003bc40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  unsigned int v5; // edx
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
  enum FEATURE_CHANGE_TIME v17; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v17 = FEATURE_CHANGE_TIME_READ;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x3667CA2,
                            v5,
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
      v13 = v17 == FEATURE_CHANGE_TIME_READ;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
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
      v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v15, v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
        3,
        v4);
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
0x180036f30  mov     [rsp+arg_0], rbx
0x180036f35  mov     [rsp+arg_10], rbp
0x180036f3a  push    rsi
0x180036f3b  push    rdi
0x180036f3c  push    r15
0x180036f3e  sub     rsp, 30h
0x180036f42  mov     rax, cs:__security_cookie
0x180036f49  xor     rax, rsp
0x180036f4c  mov     [rsp+48h+var_20], rax
0x180036f51  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180036f58  mov     rbx, rdx
0x180036f5b  mov     qword ptr [rdx], 0
0x180036f62  mov     eax, [rsi]
0x180036f64  mov     [rdx], eax
0x180036f66  and     eax, 6
0x180036f69  cmp     al, 6
0x180036f6b  jz      loc_18003707A
0x180036f71  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180036f76  lea     r8, [rsp+48h+var_28]; enum FEATURE_CHANGE_TIME
0x180036f7b  mov     [rsp+48h+var_28], 0
0x180036f83  mov     ecx, 3667CA2h; this
0x180036f88  mov     ebp, eax
0x180036f8a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180036f8f  mov     r8d, eax
0x180036f92  mov     edx, eax
0x180036f94  and     r8d, 0FFFFFF3Fh
0x180036f9b  and     edx, 80h
0x180036fa1  mov     ecx, r8d
0x180036fa4  mov     r15d, 40h ; '@'
0x180036faa  and     ecx, 3
0x180036fad  and     eax, r15d
0x180036fb0  shl     ecx, 2
0x180036fb3  or      ecx, eax
0x180036fb5  shl     ecx, 2
0x180036fb8  or      ecx, edx
0x180036fba  lea     edi, ds:0[rcx*8]
0x180036fc1  test    r8d, r8d
0x180036fc4  jnz     short loc_180036FCB
0x180036fc6  mov     eax, r15d
0x180036fc9  jmp     short loc_180036FD5
0x180036fcb  xor     eax, eax
0x180036fcd  cmp     r8d, 2
0x180036fd1  cmovz   eax, r15d
0x180036fd5  or      edi, eax
0x180036fd7  mov     eax, [rbx]
0x180036fd9  cmp     [rsp+48h+var_28], 0
0x180036fde  mov     edx, eax
0x180036fe0  mov     [rbx], eax
0x180036fe2  jz      short loc_180037012
0x180036fe4  test    dl, 2
0x180036fe7  jnz     short loc_180037012
0x180036fe9  mov     eax, edi
0x180036feb  xor     eax, edx
0x180036fed  and     eax, 180h
0x180036ff2  xor     eax, edx
0x180036ff4  mov     ecx, eax
0x180036ff6  xor     ecx, edi
0x180036ff8  and     ecx, r15d
0x180036ffb  xor     ecx, eax
0x180036ffd  or      ecx, 1
0x180037000  mov     eax, ecx
0x180037002  xor     eax, edi
0x180037004  and     eax, 800h
0x180037009  xor     eax, ecx
0x18003700b  or      eax, 2
0x18003700e  mov     [rbx], eax
0x180037010  jmp     short loc_180037014
0x180037012  mov     eax, edx
0x180037014  mov     r8d, edx
0x180037017  and     r8d, 4
0x18003701b  jnz     short loc_180037030
0x18003701d  mov     ecx, edi
0x18003701f  xor     ecx, eax
0x180037021  and     ecx, 400h
0x180037027  xor     ecx, eax
0x180037029  or      ecx, 4
0x18003702c  mov     [rbx], ecx
0x18003702e  jmp     short loc_180037032
0x180037030  mov     ecx, eax
0x180037032  mov     eax, edx
0x180037034  lock cmpxchg [rsi], ecx
0x180037038  jnz     short loc_180036FD9
0x18003703a  test    r8d, r8d
0x18003703d  jnz     short loc_18003704F
0x18003703f  mov     r8d, ebp
0x180037042  mov     edx, 3
0x180037047  mov     rcx, rsi
0x18003704a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18003704f  test    byte ptr [rbx], 2
0x180037052  jnz     short loc_18003707A
0x180037054  mov     ecx, [rbx]
0x180037056  xor     ecx, edi
0x180037058  and     ecx, 180h
0x18003705e  xor     ecx, [rbx]
0x180037060  mov     edx, ecx
0x180037062  xor     edx, edi
0x180037064  and     edx, r15d
0x180037067  xor     edx, ecx
0x180037069  or      edx, 1
0x18003706c  mov     ecx, edx
0x18003706e  xor     ecx, edi
0x180037070  and     ecx, 800h
0x180037076  xor     ecx, edx
0x180037078  mov     [rbx], ecx
0x18003707a  mov     rax, rbx
0x18003707d  mov     rcx, [rsp+48h+var_20]
0x180037082  xor     rcx, rsp; StackCookie
0x180037085  call    __security_check_cookie
0x18003708a  mov     rbx, [rsp+48h+arg_0]
0x18003708f  mov     rbp, [rsp+48h+arg_10]
0x180037094  add     rsp, 30h
0x180037098  pop     r15
0x18003709a  pop     rdi
0x18003709b  pop     rsi
0x18003709c  retn
```
