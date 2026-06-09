# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Mercury_App_Backup_Shared>::GetCachedFeatureEnabledState(void)

- ea: `0x180007e74`
- end: `0x180007fe1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Mercury_App_Backup_Shared@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800083d0`

## callees

- `0x180007854`
- `0x180007e74`
- `0x18000d31c`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Mercury_App_Backup_Shared>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Mercury_App_Backup_Shared__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Mercury_App_Backup_Shared__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(42529603, 3, &v14);
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
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Mercury_App_Backup_Shared__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Mercury_App_Backup_Shared__descriptor,
        3,
        v4);
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
0x180007e74  mov     [rsp+arg_8], rbx
0x180007e79  mov     [rsp+arg_10], rbp
0x180007e7e  mov     [rsp+arg_0], rcx
0x180007e83  push    rsi
0x180007e84  push    rdi
0x180007e85  push    r15
0x180007e87  sub     rsp, 20h
0x180007e8b  mov     rsi, cs:Feature_Mercury_App_Backup_Shared__descriptor
0x180007e92  mov     rbx, rdx
0x180007e95  mov     qword ptr [rdx], 0
0x180007e9c  mov     eax, [rsi]
0x180007e9e  mov     [rdx], eax
0x180007ea0  and     eax, 6
0x180007ea3  cmp     al, 6
0x180007ea5  jz      loc_180007FCB
0x180007eab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180007eb0  mov     ebp, eax
0x180007eb2  mov     dword ptr [rsp+38h+arg_0], 0
0x180007eba  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180007ec1  test    rax, rax
0x180007ec4  jz      short loc_180007EDE
0x180007ec6  lea     r8, [rsp+38h+arg_0]
0x180007ecb  mov     edx, 3
0x180007ed0  mov     ecx, 288F343h
0x180007ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eda  mov     edx, eax
0x180007edc  jmp     short loc_180007EEC
0x180007ede  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180007ee5  test    rax, rax
0x180007ee8  jnz     short loc_180007EC6
0x180007eea  xor     edx, edx
0x180007eec  mov     r8d, edx
0x180007eef  mov     eax, edx
0x180007ef1  and     r8d, 0FFFFFF3Fh
0x180007ef8  and     edx, 80h
0x180007efe  mov     ecx, r8d
0x180007f01  mov     r15d, 40h ; '@'
0x180007f07  and     ecx, 3
0x180007f0a  and     eax, r15d
0x180007f0d  shl     ecx, 2
0x180007f10  or      ecx, eax
0x180007f12  shl     ecx, 2
0x180007f15  or      ecx, edx
0x180007f17  lea     edi, ds:0[rcx*8]
0x180007f1e  test    r8d, r8d
0x180007f21  jnz     short loc_180007F28
0x180007f23  mov     eax, r15d
0x180007f26  jmp     short loc_180007F32
0x180007f28  xor     eax, eax
0x180007f2a  cmp     r8d, 2
0x180007f2e  cmovz   eax, r15d
0x180007f32  or      edi, eax
0x180007f34  mov     eax, [rbx]
0x180007f36  cmp     dword ptr [rsp+38h+arg_0], 0
0x180007f3b  mov     edx, eax
0x180007f3d  mov     [rbx], eax
0x180007f3f  jz      short loc_180007F6B
0x180007f41  test    dl, 2
0x180007f44  jnz     short loc_180007F6B
0x180007f46  xor     eax, edi
0x180007f48  and     eax, 180h
0x180007f4d  xor     eax, edx
0x180007f4f  mov     ecx, eax
0x180007f51  xor     ecx, edi
0x180007f53  and     ecx, r15d
0x180007f56  xor     ecx, eax
0x180007f58  or      ecx, 1
0x180007f5b  mov     eax, ecx
0x180007f5d  xor     eax, edi
0x180007f5f  and     eax, 800h
0x180007f64  xor     eax, ecx
0x180007f66  or      eax, 2
0x180007f69  mov     [rbx], eax
0x180007f6b  mov     r8d, edx
0x180007f6e  mov     ecx, eax
0x180007f70  and     r8d, 4
0x180007f74  jnz     short loc_180007F85
0x180007f76  xor     ecx, edi
0x180007f78  and     ecx, 400h
0x180007f7e  xor     ecx, eax
0x180007f80  or      ecx, 4
0x180007f83  mov     [rbx], ecx
0x180007f85  mov     eax, edx
0x180007f87  lock cmpxchg [rsi], ecx
0x180007f8b  jnz     short loc_180007F36
0x180007f8d  test    r8d, r8d
0x180007f90  jnz     short loc_180007FA2
0x180007f92  mov     r8d, ebp
0x180007f95  mov     edx, 3
0x180007f9a  mov     rcx, rsi
0x180007f9d  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180007fa2  test    byte ptr [rbx], 2
0x180007fa5  jnz     short loc_180007FCB
0x180007fa7  mov     eax, [rbx]
0x180007fa9  xor     eax, edi
0x180007fab  and     eax, 180h
0x180007fb0  xor     eax, [rbx]
0x180007fb2  mov     ecx, eax
0x180007fb4  xor     ecx, edi
0x180007fb6  and     ecx, r15d
0x180007fb9  xor     ecx, eax
0x180007fbb  or      ecx, 1
0x180007fbe  mov     eax, ecx
0x180007fc0  xor     eax, edi
0x180007fc2  and     eax, 800h
0x180007fc7  xor     eax, ecx
0x180007fc9  mov     [rbx], eax
0x180007fcb  mov     rbp, [rsp+38h+arg_10]
0x180007fd0  mov     rax, rbx
0x180007fd3  mov     rbx, [rsp+38h+arg_8]
0x180007fd8  add     rsp, 20h
0x180007fdc  pop     r15
0x180007fde  pop     rdi
0x180007fdf  pop     rsi
0x180007fe0  retn
```
