# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1400061c4`
- end: `0x140006451`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `653`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400061c4`
- `0x14000649c`

## callees

- `0x1400061c4`
- `0x140007750`
- `0x140008010`

## import_xrefs

- `ntdll!RtlQueryFeatureConfiguration` at `0x140006245`
- `ntdll!RtlQueryFeatureConfiguration` at `0x140006245`

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
  int v13; // r8d
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  int v17; // ecx
  int v18; // r9d
  int v19; // eax
  int v20; // esi
  int v21; // ecx
  int v22; // esi
  int v23; // r15d
  unsigned int ***v24; // r14
  BOOL v25; // edi
  unsigned int **v26; // rcx
  char v27; // al
  BOOL v28; // eax
  unsigned int v29; // esi
  signed __int32 v30; // edi
  signed __int32 v31; // eax
  __int64 v34; // [rsp+20h] [rbp-78h]
  __int64 v35; // [rsp+28h] [rbp-70h]
  __int64 v37; // [rsp+38h] [rbp-60h] BYREF
  __int64 v38; // [rsp+40h] [rbp-58h] BYREF
  int v39; // [rsp+48h] [rbp-50h]

  v3 = 0;
  v5 = a2;
  v6 = a1;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges(a1);
  v7 = *(_BYTE *)(a3 + 28);
  v37 = 0;
  v7 -= 2;
  v8 = 1;
  v9 = v7 == 0;
  v10 = v7 == 1;
  v11 = *(unsigned int *)(a3 + 24);
  v38 = 0;
  v39 = 0;
  v12 = RtlQueryFeatureConfiguration(v11, !v9 && !v10, &v37, &v38, a2);
  if ( v12 )
  {
    v16 = 0;
    if ( v12 == 279 )
    {
      v13 = 1;
      v17 = 8 * (BYTE4(v38) & 0x80);
LABEL_7:
      v18 = 0;
      goto LABEL_8;
    }
    v14 = 0;
    v15 = 0;
    v13 = 0;
  }
  else
  {
    v13 = 1;
    v14 = (HIDWORD(v38) >> 7) & 1;
    v15 = (HIDWORD(v38) >> 6) & 1;
    v16 = (HIDWORD(v38) >> 4) & 3;
  }
  v17 = v14 << 10;
  if ( !v15 )
    goto LABEL_7;
  v18 = 2048;
LABEL_8:
  v19 = v13 != 0 ? v16 : 0;
  v20 = v18 | v17 | (v19 << 7);
  if ( v19 )
  {
    v21 = 64;
    if ( v16 != 2 )
      v21 = 0;
  }
  else
  {
    v21 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v22 = v21 | v20;
  if ( (v22 & 0xC00) == 0xC00 )
  {
    v23 = 1;
  }
  else
  {
    v23 = 0;
    if ( (v22 & 0x40) == 0 )
    {
      v25 = 0;
      goto LABEL_34;
    }
  }
  v24 = *(unsigned int ****)(a3 + 32);
  v25 = 1;
  if ( v24 )
  {
    while ( 1 )
    {
      v26 = *v24;
      if ( !*v24 )
        break;
      if ( *((_BYTE *)v26 + 30) || *((_BYTE *)v26 + 29) )
      {
        if ( !*((_BYTE *)v26 + 31) )
        {
          v25 = 0;
          break;
        }
        v25 = 1;
        ++v24;
      }
      else
      {
        v35 = **v26;
        if ( (v35 & 2) != 0 )
          v27 = **v26;
        else
          v27 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v26, v35, v26);
        v25 = (v27 & 1) != 0;
        ++v24;
        if ( (v27 & 1) == 0 )
          break;
      }
    }
  }
  v6 = a1;
  if ( v23 && !v25 )
    v22 &= ~0x400u;
LABEL_34:
  v28 = (v22 & 0x40) != 0 && v25;
  v29 = v28 | v22 & 0xFFFFFFFE;
  if ( !*(_BYTE *)(a3 + 28) )
    v8 = v3 != 0;
  while ( 1 )
  {
    LODWORD(v34) = v5;
    v30 = v5;
    if ( v8 )
    {
      LODWORD(v34) = v5;
      if ( (v5 & 2) == 0 )
      {
        v30 = v5 ^ (v5 ^ v29) & 0x9C1 | 2;
        LODWORD(v34) = v30;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v30 = v30 ^ ((unsigned __int16)v29 ^ (unsigned __int16)v30) & 0x400 | 4;
      LODWORD(v34) = v30;
    }
    v31 = _InterlockedCompareExchange(v6, v30, v5);
    if ( v5 == v31 )
      break;
    v5 = v31;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(v6, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v34) = v30 ^ (v29 ^ v30) & 0x9C1;
  return v34;
}

```

## disassembly

```asm
0x1400061c4  mov     [rsp+arg_18], rbx
0x1400061c9  push    rbp
0x1400061ca  push    rsi
0x1400061cb  push    rdi
0x1400061cc  push    r12
0x1400061ce  push    r13
0x1400061d0  push    r14
0x1400061d2  push    r15
0x1400061d4  sub     rsp, 60h
0x1400061d8  mov     rax, cs:__security_cookie
0x1400061df  xor     rax, rsp
0x1400061e2  mov     [rsp+98h+var_48], rax
0x1400061e7  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1400061ee  xor     r12d, r12d
0x1400061f1  mov     [rsp+98h+var_68], rcx
0x1400061f6  mov     r13, r8
0x1400061f9  mov     [rsp+98h+var_78], rdx
0x1400061fe  mov     rbx, rdx
0x140006201  mov     r14, rcx
0x140006204  test    rax, rax
0x140006207  jz      short loc_140006211
0x140006209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000620e  mov     r12d, eax
0x140006211  mov     cl, [r13+1Ch]
0x140006215  lea     r9, [rsp+98h+var_58]
0x14000621a  xor     edx, edx
0x14000621c  mov     [rsp+98h+var_60], 0
0x140006225  sub     cl, 2
0x140006228  lea     r8, [rsp+98h+var_60]
0x14000622d  lea     ebp, [rdx+1]
0x140006230  cmp     cl, bpl
0x140006233  mov     ecx, [r13+18h]
0x140006237  setnbe  dl
0x14000623a  xor     eax, eax
0x14000623c  mov     [rsp+98h+var_58], rax
0x140006241  mov     [rsp+98h+var_50], eax
0x140006245  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000624b  test    eax, eax
0x14000624d  jnz     short loc_14000626C
0x14000624f  mov     edx, dword ptr [rsp+98h+var_58+4]
0x140006253  mov     r8d, ebp
0x140006256  mov     ecx, edx
0x140006258  mov     eax, edx
0x14000625a  shr     ecx, 7
0x14000625d  shr     eax, 6
0x140006260  and     ecx, ebp
0x140006262  and     eax, ebp
0x140006264  shr     edx, 4
0x140006267  and     edx, 3
0x14000626a  jmp     short loc_1400062B4
0x14000626c  xor     edx, edx
0x14000626e  cmp     eax, 117h
0x140006273  jnz     short loc_1400062AD
0x140006275  mov     eax, dword ptr [rsp+98h+var_58+4]
0x140006279  mov     r8d, ebp
0x14000627c  and     eax, 80h
0x140006281  lea     ecx, ds:0[rax*8]
0x140006288  xor     r9d, r9d
0x14000628b  neg     r8d
0x14000628e  sbb     eax, eax
0x140006290  and     eax, edx
0x140006292  mov     esi, eax
0x140006294  shl     esi, 7
0x140006297  or      esi, ecx
0x140006299  or      esi, r9d
0x14000629c  test    eax, eax
0x14000629e  jnz     short loc_1400062C3
0x1400062a0  mov     al, [r13+1Fh]
0x1400062a4  neg     al
0x1400062a6  sbb     ecx, ecx
0x1400062a8  and     ecx, 40h
0x1400062ab  jmp     short loc_1400062D0
0x1400062ad  xor     ecx, ecx
0x1400062af  xor     eax, eax
0x1400062b1  xor     r8d, r8d
0x1400062b4  shl     ecx, 0Ah
0x1400062b7  test    eax, eax
0x1400062b9  jz      short loc_140006288
0x1400062bb  mov     r9d, 800h
0x1400062c1  jmp     short loc_14000628B
0x1400062c3  xor     eax, eax
0x1400062c5  mov     ecx, 40h ; '@'
0x1400062ca  cmp     edx, 2
0x1400062cd  cmovnz  ecx, eax
0x1400062d0  or      esi, ecx
0x1400062d2  mov     ecx, 0C00h
0x1400062d7  mov     eax, esi
0x1400062d9  and     eax, ecx
0x1400062db  cmp     eax, ecx
0x1400062dd  jnz     short loc_1400062E4
0x1400062df  mov     r15d, ebp
0x1400062e2  jmp     short loc_1400062F1
0x1400062e4  xor     r15d, r15d
0x1400062e7  test    sil, 40h
0x1400062eb  jz      loc_14000637F
0x1400062f1  mov     r14, [r13+20h]
0x1400062f5  mov     edi, ebp
0x1400062f7  test    r14, r14
0x1400062fa  jz      short loc_14000636B
0x1400062fc  mov     rcx, [r14]
0x1400062ff  test    rcx, rcx
0x140006302  jz      short loc_14000636B
0x140006304  cmp     byte ptr [rcx+1Eh], 0
0x140006308  jnz     short loc_140006357
0x14000630a  cmp     byte ptr [rcx+1Dh], 0
0x14000630e  jnz     short loc_140006357
0x140006310  mov     r9, [rcx]
0x140006313  mov     [rsp+98h+var_70], 0
0x14000631c  mov     eax, [r9]
0x14000631f  mov     dword ptr [rsp+98h+var_70], eax
0x140006323  test    al, 2
0x140006325  jz      short loc_14000632E
0x140006327  mov     rax, [rsp+98h+var_70]
0x14000632c  jmp     short loc_14000633E
0x14000632e  mov     rdx, [rsp+98h+var_70]
0x140006333  mov     r8, rcx
0x140006336  mov     rcx, r9
0x140006339  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x14000633e  test    edi, edi
0x140006340  jz      short loc_14000634B
0x140006342  test    bpl, al
0x140006345  jz      short loc_14000634B
0x140006347  mov     edi, ebp
0x140006349  jmp     short loc_14000634D
0x14000634b  xor     edi, edi
0x14000634d  add     r14, 8
0x140006351  test    edi, edi
0x140006353  jnz     short loc_1400062FC
0x140006355  jmp     short loc_14000636B
0x140006357  test    edi, edi
0x140006359  jz      short loc_140006369
0x14000635b  cmp     byte ptr [rcx+1Fh], 0
0x14000635f  jz      short loc_140006369
0x140006361  mov     edi, ebp
0x140006363  add     r14, 8
0x140006367  jmp     short loc_1400062FC
0x140006369  xor     edi, edi
0x14000636b  mov     r14, [rsp+98h+var_68]
0x140006370  test    r15d, r15d
0x140006373  jz      short loc_140006381
0x140006375  test    edi, edi
0x140006377  jnz     short loc_140006381
0x140006379  btr     esi, 0Ah
0x14000637d  jmp     short loc_140006381
0x14000637f  xor     edi, edi
0x140006381  test    sil, 40h
0x140006385  jz      short loc_14000638F
0x140006387  test    edi, edi
0x140006389  jz      short loc_14000638F
0x14000638b  mov     eax, ebp
0x14000638d  jmp     short loc_140006391
0x14000638f  xor     eax, eax
0x140006391  and     esi, 0FFFFFFFEh
0x140006394  or      esi, eax
0x140006396  cmp     byte ptr [r13+1Ch], 0
0x14000639b  jnz     short loc_1400063A6
0x14000639d  mov     eax, r12d
0x1400063a0  neg     eax
0x1400063a2  sbb     ecx, ecx
0x1400063a4  and     ebp, ecx
0x1400063a6  mov     r15d, 9C1h
0x1400063ac  mov     dword ptr [rsp+98h+var_78], ebx
0x1400063b0  mov     edi, ebx
0x1400063b2  test    ebp, ebp
0x1400063b4  jz      short loc_1400063CF
0x1400063b6  mov     dword ptr [rsp+98h+var_78], ebx
0x1400063ba  test    bl, 2
0x1400063bd  jnz     short loc_1400063CF
0x1400063bf  mov     edi, esi
0x1400063c1  xor     edi, ebx
0x1400063c3  and     edi, r15d
0x1400063c6  xor     edi, ebx
0x1400063c8  or      edi, 2
0x1400063cb  mov     dword ptr [rsp+98h+var_78], edi
0x1400063cf  mov     ecx, ebx
0x1400063d1  and     ecx, 4
0x1400063d4  jnz     short loc_1400063E9
0x1400063d6  mov     eax, edi
0x1400063d8  xor     edi, esi
0x1400063da  and     edi, 400h
0x1400063e0  xor     edi, eax
0x1400063e2  or      edi, 4
0x1400063e5  mov     dword ptr [rsp+98h+var_78], edi
0x1400063e9  mov     eax, ebx
0x1400063eb  lock cmpxchg [r14], edi
0x1400063f0  jz      short loc_1400063F6
0x1400063f2  mov     ebx, eax
0x1400063f4  jmp     short loc_1400063AC
0x1400063f6  test    ecx, ecx
0x1400063f8  jnz     short loc_140006416
0x1400063fa  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140006401  test    rax, rax
0x140006404  jz      short loc_140006416
0x140006406  movzx   edx, byte ptr [r13+1Ch]
0x14000640b  mov     r8d, r12d
0x14000640e  mov     rcx, r14
0x140006411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006416  test    ebp, ebp
0x140006418  jnz     short loc_140006427
0x14000641a  mov     eax, edi
0x14000641c  xor     eax, esi
0x14000641e  and     eax, r15d
0x140006421  xor     eax, edi
0x140006423  mov     dword ptr [rsp+98h+var_78], eax
0x140006427  mov     rax, [rsp+98h+var_78]
0x14000642c  mov     rcx, [rsp+98h+var_48]
0x140006431  xor     rcx, rsp; StackCookie
0x140006434  call    __security_check_cookie
0x140006439  mov     rbx, [rsp+98h+arg_18]
0x140006441  add     rsp, 60h
0x140006445  pop     r15
0x140006447  pop     r14
0x140006449  pop     r13
0x14000644b  pop     r12
0x14000644d  pop     rdi
0x14000644e  pop     rsi
0x14000644f  pop     rbp
0x140006450  retn
```
