# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140003c44`
- end: `0x140003ed4`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `656`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003c44`
- `0x140003f20`

## callees

- `0x140003c44`
- `0x140007d00`
- `0x140007d40`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140003cc5`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140003cc5`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r12d
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r14
  char v7; // cl
  BOOL v8; // ebp
  bool v9; // cf
  bool v10; // zf
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // eax
  int v18; // ecx
  int v19; // edi
  int v20; // r15d
  unsigned int ***v21; // r14
  BOOL v22; // esi
  unsigned int **v23; // rcx
  char v24; // al
  BOOL v25; // eax
  unsigned int v26; // edi
  signed __int32 v27; // esi
  signed __int32 v28; // eax
  __int64 v31; // [rsp+20h] [rbp-78h]
  __int64 v32; // [rsp+28h] [rbp-70h]
  __int64 v34; // [rsp+38h] [rbp-60h] BYREF
  __int64 v35; // [rsp+40h] [rbp-58h] BYREF
  int v36; // [rsp+48h] [rbp-50h]

  v3 = 0;
  v5 = a2;
  v6 = a1;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges(a1);
  v7 = *(_BYTE *)(a3 + 28);
  v34 = 0;
  v7 -= 2;
  v8 = 1;
  v9 = v7 == 0;
  v10 = v7 == 1;
  v11 = *(unsigned int *)(a3 + 24);
  v35 = 0;
  v36 = 0;
  v12 = RtlQueryFeatureConfiguration(v11, !v9 && !v10, &v34, &v35, a2);
  if ( v12 )
  {
    v13 = 0;
    if ( v12 == 279 )
    {
      v14 = 1;
      v15 = 8 * (BYTE4(v35) & 0x80);
    }
    else
    {
      v14 = 0;
      v15 = 0;
    }
  }
  else
  {
    v13 = (HIDWORD(v35) >> 4) & 3;
    v14 = 1;
    v15 = 8 * (BYTE4(v35) & 0x80);
    if ( (v35 & 0x4000000000LL) != 0 )
    {
      v16 = 2048;
      goto LABEL_10;
    }
  }
  v16 = 0;
LABEL_10:
  v17 = v14 != 0 ? v13 : 0;
  if ( v17 )
  {
    v18 = 64;
    if ( v13 != 2 )
      v18 = 0;
  }
  else
  {
    v18 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v19 = v18 | v16 | v15 | (v17 << 7);
  if ( (v19 & 0xC00) == 0xC00 )
  {
    v20 = 1;
  }
  else
  {
    v20 = 0;
    if ( !(v18 & 0x40 | v16 & 0x40 | v15 & 0x40) )
    {
      v22 = 0;
      goto LABEL_33;
    }
  }
  v21 = *(unsigned int ****)(a3 + 32);
  v22 = 1;
  if ( v21 )
  {
    while ( 1 )
    {
      v23 = *v21;
      if ( !*v21 )
        break;
      if ( *((_BYTE *)v23 + 30) || *((_BYTE *)v23 + 29) )
      {
        if ( !*((_BYTE *)v23 + 31) )
        {
          v22 = 0;
          break;
        }
        v22 = 1;
        ++v21;
      }
      else
      {
        v32 = **v23;
        if ( (v32 & 2) != 0 )
          v24 = **v23;
        else
          v24 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v23, v32, v23);
        v22 = (v24 & 1) != 0;
        ++v21;
        if ( (v24 & 1) == 0 )
          break;
      }
    }
  }
  v6 = a1;
  if ( v20 && !v22 )
    v19 &= ~0x400u;
LABEL_33:
  v25 = (v19 & 0x40) != 0 && v22;
  v26 = v25 | v19 & 0xFFFFFFFE;
  if ( !*(_BYTE *)(a3 + 28) )
    v8 = v3 != 0;
  while ( 1 )
  {
    LODWORD(v31) = v5;
    v27 = v5;
    if ( v8 )
    {
      LODWORD(v31) = v5;
      if ( (v5 & 2) == 0 )
      {
        v27 = v5 ^ (v5 ^ v26) & 0x9C1 | 2;
        LODWORD(v31) = v27;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v27 = v27 ^ ((unsigned __int16)v26 ^ (unsigned __int16)v27) & 0x400 | 4;
      LODWORD(v31) = v27;
    }
    v28 = _InterlockedCompareExchange(v6, v27, v5);
    if ( v5 == v28 )
      break;
    v5 = v28;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(v6, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v31) = v27 ^ (v27 ^ v26) & 0x9C1;
  return v31;
}

```

## disassembly

```asm
0x140003c44  mov     [rsp+arg_18], rbx
0x140003c49  push    rbp
0x140003c4a  push    rsi
0x140003c4b  push    rdi
0x140003c4c  push    r12
0x140003c4e  push    r13
0x140003c50  push    r14
0x140003c52  push    r15
0x140003c54  sub     rsp, 60h
0x140003c58  mov     rax, cs:__security_cookie
0x140003c5f  xor     rax, rsp
0x140003c62  mov     [rsp+98h+var_48], rax
0x140003c67  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140003c6e  xor     r12d, r12d
0x140003c71  mov     [rsp+98h+var_68], rcx
0x140003c76  mov     r13, r8
0x140003c79  mov     [rsp+98h+var_78], rdx
0x140003c7e  mov     rbx, rdx
0x140003c81  mov     r14, rcx
0x140003c84  test    rax, rax
0x140003c87  jz      short loc_140003C91
0x140003c89  call    _guard_dispatch_icall
0x140003c8e  mov     r12d, eax
0x140003c91  mov     cl, [r13+1Ch]
0x140003c95  lea     r9, [rsp+98h+var_58]
0x140003c9a  xor     edx, edx
0x140003c9c  mov     [rsp+98h+var_60], 0
0x140003ca5  sub     cl, 2
0x140003ca8  lea     r8, [rsp+98h+var_60]
0x140003cad  lea     ebp, [rdx+1]
0x140003cb0  cmp     cl, bpl
0x140003cb3  mov     ecx, [r13+18h]
0x140003cb7  setnbe  dl
0x140003cba  xor     eax, eax
0x140003cbc  mov     [rsp+98h+var_58], rax
0x140003cc1  mov     [rsp+98h+var_50], eax
0x140003cc5  call    cs:__imp_RtlQueryFeatureConfiguration
0x140003ccc  nop     dword ptr [rax+rax+00h]
0x140003cd1  test    eax, eax
0x140003cd3  jnz     short loc_140003CFF
0x140003cd5  mov     ecx, dword ptr [rsp+98h+var_58+4]
0x140003cd9  mov     edx, ecx
0x140003cdb  mov     eax, ecx
0x140003cdd  shr     edx, 4
0x140003ce0  and     eax, 80h
0x140003ce5  and     edx, 3
0x140003ce8  test    cl, 40h
0x140003ceb  mov     ecx, ebp
0x140003ced  lea     r8d, ds:0[rax*8]
0x140003cf5  jz      short loc_140003D22
0x140003cf7  mov     r9d, 800h
0x140003cfd  jmp     short loc_140003D25
0x140003cff  xor     edx, edx
0x140003d01  cmp     eax, 117h
0x140003d06  jnz     short loc_140003D1D
0x140003d08  mov     eax, dword ptr [rsp+98h+var_58+4]
0x140003d0c  mov     ecx, ebp
0x140003d0e  and     eax, 80h
0x140003d13  lea     r8d, ds:0[rax*8]
0x140003d1b  jmp     short loc_140003D22
0x140003d1d  xor     ecx, ecx
0x140003d1f  xor     r8d, r8d
0x140003d22  xor     r9d, r9d
0x140003d25  neg     ecx
0x140003d27  sbb     eax, eax
0x140003d29  and     eax, edx
0x140003d2b  mov     edi, eax
0x140003d2d  shl     edi, 7
0x140003d30  or      edi, r8d
0x140003d33  or      edi, r9d
0x140003d36  test    eax, eax
0x140003d38  jnz     short loc_140003D47
0x140003d3a  mov     al, [r13+1Fh]
0x140003d3e  neg     al
0x140003d40  sbb     ecx, ecx
0x140003d42  and     ecx, 40h
0x140003d45  jmp     short loc_140003D54
0x140003d47  xor     eax, eax
0x140003d49  mov     ecx, 40h ; '@'
0x140003d4e  cmp     edx, 2
0x140003d51  cmovnz  ecx, eax
0x140003d54  or      edi, ecx
0x140003d56  mov     ecx, 0C00h
0x140003d5b  mov     eax, edi
0x140003d5d  and     eax, ecx
0x140003d5f  cmp     eax, ecx
0x140003d61  jnz     short loc_140003D68
0x140003d63  mov     r15d, ebp
0x140003d66  jmp     short loc_140003D75
0x140003d68  xor     r15d, r15d
0x140003d6b  test    dil, 40h
0x140003d6f  jz      loc_140003E03
0x140003d75  mov     r14, [r13+20h]
0x140003d79  mov     esi, ebp
0x140003d7b  test    r14, r14
0x140003d7e  jz      short loc_140003DEF
0x140003d80  mov     rcx, [r14]
0x140003d83  test    rcx, rcx
0x140003d86  jz      short loc_140003DEF
0x140003d88  cmp     byte ptr [rcx+1Eh], 0
0x140003d8c  jnz     short loc_140003DDB
0x140003d8e  cmp     byte ptr [rcx+1Dh], 0
0x140003d92  jnz     short loc_140003DDB
0x140003d94  mov     r9, [rcx]
0x140003d97  mov     [rsp+98h+var_70], 0
0x140003da0  mov     eax, [r9]
0x140003da3  mov     dword ptr [rsp+98h+var_70], eax
0x140003da7  test    al, 2
0x140003da9  jz      short loc_140003DB2
0x140003dab  mov     rax, [rsp+98h+var_70]
0x140003db0  jmp     short loc_140003DC2
0x140003db2  mov     rdx, [rsp+98h+var_70]
0x140003db7  mov     r8, rcx
0x140003dba  mov     rcx, r9
0x140003dbd  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140003dc2  test    esi, esi
0x140003dc4  jz      short loc_140003DCF
0x140003dc6  test    bpl, al
0x140003dc9  jz      short loc_140003DCF
0x140003dcb  mov     esi, ebp
0x140003dcd  jmp     short loc_140003DD1
0x140003dcf  xor     esi, esi
0x140003dd1  add     r14, 8
0x140003dd5  test    esi, esi
0x140003dd7  jnz     short loc_140003D80
0x140003dd9  jmp     short loc_140003DEF
0x140003ddb  test    esi, esi
0x140003ddd  jz      short loc_140003DED
0x140003ddf  cmp     byte ptr [rcx+1Fh], 0
0x140003de3  jz      short loc_140003DED
0x140003de5  mov     esi, ebp
0x140003de7  add     r14, 8
0x140003deb  jmp     short loc_140003D80
0x140003ded  xor     esi, esi
0x140003def  mov     r14, [rsp+98h+var_68]
0x140003df4  test    r15d, r15d
0x140003df7  jz      short loc_140003E05
0x140003df9  test    esi, esi
0x140003dfb  jnz     short loc_140003E05
0x140003dfd  btr     edi, 0Ah
0x140003e01  jmp     short loc_140003E05
0x140003e03  xor     esi, esi
0x140003e05  test    dil, 40h
0x140003e09  jz      short loc_140003E13
0x140003e0b  test    esi, esi
0x140003e0d  jz      short loc_140003E13
0x140003e0f  mov     eax, ebp
0x140003e11  jmp     short loc_140003E15
0x140003e13  xor     eax, eax
0x140003e15  and     edi, 0FFFFFFFEh
0x140003e18  or      edi, eax
0x140003e1a  cmp     byte ptr [r13+1Ch], 0
0x140003e1f  jnz     short loc_140003E2A
0x140003e21  mov     eax, r12d
0x140003e24  neg     eax
0x140003e26  sbb     ecx, ecx
0x140003e28  and     ebp, ecx
0x140003e2a  mov     r15d, 9C1h
0x140003e30  mov     dword ptr [rsp+98h+var_78], ebx
0x140003e34  mov     esi, ebx
0x140003e36  test    ebp, ebp
0x140003e38  jz      short loc_140003E53
0x140003e3a  mov     dword ptr [rsp+98h+var_78], ebx
0x140003e3e  test    bl, 2
0x140003e41  jnz     short loc_140003E53
0x140003e43  mov     esi, edi
0x140003e45  xor     esi, ebx
0x140003e47  and     esi, r15d
0x140003e4a  xor     esi, ebx
0x140003e4c  or      esi, 2
0x140003e4f  mov     dword ptr [rsp+98h+var_78], esi
0x140003e53  mov     ecx, ebx
0x140003e55  and     ecx, 4
0x140003e58  jnz     short loc_140003E6D
0x140003e5a  mov     eax, esi
0x140003e5c  xor     esi, edi
0x140003e5e  and     esi, 400h
0x140003e64  xor     esi, eax
0x140003e66  or      esi, 4
0x140003e69  mov     dword ptr [rsp+98h+var_78], esi
0x140003e6d  mov     eax, ebx
0x140003e6f  lock cmpxchg [r14], esi
0x140003e74  jz      short loc_140003E7A
0x140003e76  mov     ebx, eax
0x140003e78  jmp     short loc_140003E30
0x140003e7a  test    ecx, ecx
0x140003e7c  jnz     short loc_140003E9A
0x140003e7e  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140003e85  test    rax, rax
0x140003e88  jz      short loc_140003E9A
0x140003e8a  movzx   edx, byte ptr [r13+1Ch]
0x140003e8f  mov     r8d, r12d
0x140003e92  mov     rcx, r14
0x140003e95  call    _guard_dispatch_icall
0x140003e9a  test    ebp, ebp
0x140003e9c  jnz     short loc_140003EA9
0x140003e9e  xor     edi, esi
0x140003ea0  and     edi, r15d
0x140003ea3  xor     edi, esi
0x140003ea5  mov     dword ptr [rsp+98h+var_78], edi
0x140003ea9  mov     rax, [rsp+98h+var_78]
0x140003eae  mov     rcx, [rsp+98h+var_48]
0x140003eb3  xor     rcx, rsp; StackCookie
0x140003eb6  call    __security_check_cookie
0x140003ebb  mov     rbx, [rsp+98h+arg_18]
0x140003ec3  add     rsp, 60h
0x140003ec7  pop     r15
0x140003ec9  pop     r14
0x140003ecb  pop     r13
0x140003ecd  pop     r12
0x140003ecf  pop     rdi
0x140003ed0  pop     rsi
0x140003ed1  pop     rbp
0x140003ed2  retn
```
