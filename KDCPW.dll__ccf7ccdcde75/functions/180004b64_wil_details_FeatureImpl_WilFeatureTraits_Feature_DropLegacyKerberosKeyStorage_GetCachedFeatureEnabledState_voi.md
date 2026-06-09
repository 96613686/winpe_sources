# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage>::GetCachedFeatureEnabledState(void)

- ea: `0x180004b64`
- end: `0x180004cd3`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007944`

## callees

- `0x180004618`
- `0x180004b64`
- `0x180008250`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DropLegacyKerberosKeyStorage>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, wil::details **); // rax
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
  v3 = *(_DWORD *)Feature_DropLegacyKerberosKeyStorage__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DropLegacyKerberosKeyStorage__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    v6 = 0;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(47350999, 0, &v14);
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
    if ( !v4 )
      LODWORD(v14) = 0;
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
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_DropLegacyKerberosKeyStorage__descriptor,
             v12,
             v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_DropLegacyKerberosKeyStorage__descriptor,
        0,
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
0x180004b64  mov     [rsp+arg_8], rbx
0x180004b69  mov     [rsp+arg_10], rbp
0x180004b6e  mov     [rsp+arg_0], rcx
0x180004b73  push    rsi
0x180004b74  push    rdi
0x180004b75  push    r15
0x180004b77  sub     rsp, 20h
0x180004b7b  mov     rsi, cs:Feature_DropLegacyKerberosKeyStorage__descriptor
0x180004b82  mov     rbx, rdx
0x180004b85  mov     qword ptr [rdx], 0
0x180004b8c  mov     eax, [rsi]
0x180004b8e  mov     [rdx], eax
0x180004b90  and     eax, 6
0x180004b93  cmp     al, 6
0x180004b95  jz      loc_180004CBD
0x180004b9b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004ba0  mov     ebp, eax
0x180004ba2  mov     dword ptr [rsp+38h+arg_0], 0
0x180004baa  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180004bb1  xor     edx, edx
0x180004bb3  test    rax, rax
0x180004bb6  jnz     short loc_180004BC4
0x180004bb8  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180004bbf  test    rax, rax
0x180004bc2  jz      short loc_180004BD5
0x180004bc4  lea     r8, [rsp+38h+arg_0]
0x180004bc9  mov     ecx, 2D284D7h
0x180004bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd3  mov     edx, eax
0x180004bd5  mov     r8d, edx
0x180004bd8  mov     eax, edx
0x180004bda  and     r8d, 0FFFFFF3Fh
0x180004be1  and     edx, 80h
0x180004be7  mov     ecx, r8d
0x180004bea  mov     r15d, 40h ; '@'
0x180004bf0  and     ecx, 3
0x180004bf3  and     eax, r15d
0x180004bf6  shl     ecx, 2
0x180004bf9  or      ecx, eax
0x180004bfb  shl     ecx, 2
0x180004bfe  or      ecx, edx
0x180004c00  lea     edi, ds:0[rcx*8]
0x180004c07  test    r8d, r8d
0x180004c0a  jnz     short loc_180004C11
0x180004c0c  mov     eax, r15d
0x180004c0f  jmp     short loc_180004C1B
0x180004c11  xor     eax, eax
0x180004c13  cmp     r8d, 2
0x180004c17  cmovz   eax, r15d
0x180004c1b  or      edi, eax
0x180004c1d  test    ebp, ebp
0x180004c1f  jnz     short loc_180004C25
0x180004c21  mov     dword ptr [rsp+38h+arg_0], ebp
0x180004c25  mov     eax, [rbx]
0x180004c27  cmp     dword ptr [rsp+38h+arg_0], 0
0x180004c2c  mov     edx, eax
0x180004c2e  mov     [rbx], eax
0x180004c30  jz      short loc_180004C5C
0x180004c32  test    dl, 2
0x180004c35  jnz     short loc_180004C5C
0x180004c37  xor     eax, edi
0x180004c39  and     eax, 180h
0x180004c3e  xor     eax, edx
0x180004c40  mov     ecx, eax
0x180004c42  xor     ecx, edi
0x180004c44  and     ecx, r15d
0x180004c47  xor     ecx, eax
0x180004c49  or      ecx, 1
0x180004c4c  mov     eax, ecx
0x180004c4e  xor     eax, edi
0x180004c50  and     eax, 800h
0x180004c55  xor     eax, ecx
0x180004c57  or      eax, 2
0x180004c5a  mov     [rbx], eax
0x180004c5c  mov     r8d, edx
0x180004c5f  and     r8d, 4
0x180004c63  jnz     short loc_180004C78
0x180004c65  mov     ecx, edi
0x180004c67  xor     ecx, eax
0x180004c69  and     ecx, 400h
0x180004c6f  xor     ecx, eax
0x180004c71  or      ecx, 4
0x180004c74  mov     [rbx], ecx
0x180004c76  jmp     short loc_180004C7A
0x180004c78  mov     ecx, eax
0x180004c7a  mov     eax, edx
0x180004c7c  lock cmpxchg [rsi], ecx
0x180004c80  jnz     short loc_180004C27
0x180004c82  test    r8d, r8d
0x180004c85  jnz     short loc_180004C94
0x180004c87  mov     r8d, ebp
0x180004c8a  xor     edx, edx
0x180004c8c  mov     rcx, rsi
0x180004c8f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180004c94  test    byte ptr [rbx], 2
0x180004c97  jnz     short loc_180004CBD
0x180004c99  mov     eax, [rbx]
0x180004c9b  xor     eax, edi
0x180004c9d  and     eax, 180h
0x180004ca2  xor     eax, [rbx]
0x180004ca4  mov     ecx, eax
0x180004ca6  xor     ecx, edi
0x180004ca8  and     ecx, r15d
0x180004cab  xor     ecx, eax
0x180004cad  or      ecx, 1
0x180004cb0  mov     eax, ecx
0x180004cb2  xor     eax, edi
0x180004cb4  and     eax, 800h
0x180004cb9  xor     eax, ecx
0x180004cbb  mov     [rbx], eax
0x180004cbd  mov     rbp, [rsp+38h+arg_10]
0x180004cc2  mov     rax, rbx
0x180004cc5  mov     rbx, [rsp+38h+arg_8]
0x180004cca  add     rsp, 20h
0x180004cce  pop     r15
0x180004cd0  pop     rdi
0x180004cd1  pop     rsi
0x180004cd2  retn
```
