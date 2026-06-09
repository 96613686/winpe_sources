# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18004353c`
- end: `0x1800437d0`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `660`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004353c`
- `0x180043830`

## callees

- `0x18004353c`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlQueryFeatureConfiguration` at `0x1800435bd`
- `ntdll!RtlQueryFeatureConfiguration` at `0x1800435bd`

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
0x18004353c  mov     [rsp+arg_18], rbx
0x180043541  push    rbp
0x180043542  push    rsi
0x180043543  push    rdi
0x180043544  push    r12
0x180043546  push    r13
0x180043548  push    r14
0x18004354a  push    r15
0x18004354c  sub     rsp, 60h
0x180043550  mov     rax, cs:__security_cookie
0x180043557  xor     rax, rsp
0x18004355a  mov     [rsp+98h+var_48], rax
0x18004355f  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180043566  xor     r12d, r12d
0x180043569  mov     [rsp+98h+var_68], rcx
0x18004356e  mov     r13, r8
0x180043571  mov     [rsp+98h+var_78], rdx
0x180043576  mov     rbx, rdx
0x180043579  mov     r14, rcx
0x18004357c  test    rax, rax
0x18004357f  jz      short loc_180043589
0x180043581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043586  mov     r12d, eax
0x180043589  mov     cl, [r13+1Ch]
0x18004358d  lea     r9, [rsp+98h+var_58]
0x180043592  xor     edx, edx
0x180043594  mov     [rsp+98h+var_60], 0
0x18004359d  sub     cl, 2
0x1800435a0  lea     r8, [rsp+98h+var_60]
0x1800435a5  lea     ebp, [rdx+1]
0x1800435a8  cmp     cl, bpl
0x1800435ab  mov     ecx, [r13+18h]
0x1800435af  setnbe  dl
0x1800435b2  xor     eax, eax
0x1800435b4  mov     [rsp+98h+var_58], rax
0x1800435b9  mov     [rsp+98h+var_50], eax
0x1800435bd  call    cs:__imp_RtlQueryFeatureConfiguration
0x1800435c4  nop     dword ptr [rax+rax+00h]
0x1800435c9  test    eax, eax
0x1800435cb  jnz     short loc_1800435EA
0x1800435cd  mov     edx, dword ptr [rsp+98h+var_58+4]
0x1800435d1  mov     r8d, ebp
0x1800435d4  mov     ecx, edx
0x1800435d6  mov     eax, edx
0x1800435d8  shr     ecx, 7
0x1800435db  shr     eax, 6
0x1800435de  and     ecx, ebp
0x1800435e0  and     eax, ebp
0x1800435e2  shr     edx, 4
0x1800435e5  and     edx, 3
0x1800435e8  jmp     short loc_180043632
0x1800435ea  xor     edx, edx
0x1800435ec  cmp     eax, 117h
0x1800435f1  jnz     short loc_18004362B
0x1800435f3  mov     eax, dword ptr [rsp+98h+var_58+4]
0x1800435f7  mov     r8d, ebp
0x1800435fa  and     eax, 80h
0x1800435ff  lea     ecx, ds:0[rax*8]
0x180043606  xor     r9d, r9d
0x180043609  neg     r8d
0x18004360c  sbb     eax, eax
0x18004360e  and     eax, edx
0x180043610  mov     esi, eax
0x180043612  shl     esi, 7
0x180043615  or      esi, ecx
0x180043617  or      esi, r9d
0x18004361a  test    eax, eax
0x18004361c  jnz     short loc_180043641
0x18004361e  mov     al, [r13+1Fh]
0x180043622  neg     al
0x180043624  sbb     ecx, ecx
0x180043626  and     ecx, 40h
0x180043629  jmp     short loc_18004364E
0x18004362b  xor     ecx, ecx
0x18004362d  xor     eax, eax
0x18004362f  xor     r8d, r8d
0x180043632  shl     ecx, 0Ah
0x180043635  test    eax, eax
0x180043637  jz      short loc_180043606
0x180043639  mov     r9d, 800h
0x18004363f  jmp     short loc_180043609
0x180043641  xor     eax, eax
0x180043643  mov     ecx, 40h ; '@'
0x180043648  cmp     edx, 2
0x18004364b  cmovnz  ecx, eax
0x18004364e  or      esi, ecx
0x180043650  mov     ecx, 0C00h
0x180043655  mov     eax, esi
0x180043657  and     eax, ecx
0x180043659  cmp     eax, ecx
0x18004365b  jnz     short loc_180043662
0x18004365d  mov     r15d, ebp
0x180043660  jmp     short loc_18004366F
0x180043662  xor     r15d, r15d
0x180043665  test    sil, 40h
0x180043669  jz      loc_1800436FD
0x18004366f  mov     r14, [r13+20h]
0x180043673  mov     edi, ebp
0x180043675  test    r14, r14
0x180043678  jz      short loc_1800436E9
0x18004367a  mov     rcx, [r14]
0x18004367d  test    rcx, rcx
0x180043680  jz      short loc_1800436E9
0x180043682  cmp     byte ptr [rcx+1Eh], 0
0x180043686  jnz     short loc_1800436D5
0x180043688  cmp     byte ptr [rcx+1Dh], 0
0x18004368c  jnz     short loc_1800436D5
0x18004368e  mov     r9, [rcx]
0x180043691  mov     [rsp+98h+var_70], 0
0x18004369a  mov     eax, [r9]
0x18004369d  mov     dword ptr [rsp+98h+var_70], eax
0x1800436a1  test    al, 2
0x1800436a3  jz      short loc_1800436AC
0x1800436a5  mov     rax, [rsp+98h+var_70]
0x1800436aa  jmp     short loc_1800436BC
0x1800436ac  mov     rdx, [rsp+98h+var_70]
0x1800436b1  mov     r8, rcx
0x1800436b4  mov     rcx, r9
0x1800436b7  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x1800436bc  test    edi, edi
0x1800436be  jz      short loc_1800436C9
0x1800436c0  test    bpl, al
0x1800436c3  jz      short loc_1800436C9
0x1800436c5  mov     edi, ebp
0x1800436c7  jmp     short loc_1800436CB
0x1800436c9  xor     edi, edi
0x1800436cb  add     r14, 8
0x1800436cf  test    edi, edi
0x1800436d1  jnz     short loc_18004367A
0x1800436d3  jmp     short loc_1800436E9
0x1800436d5  test    edi, edi
0x1800436d7  jz      short loc_1800436E7
0x1800436d9  cmp     byte ptr [rcx+1Fh], 0
0x1800436dd  jz      short loc_1800436E7
0x1800436df  mov     edi, ebp
0x1800436e1  add     r14, 8
0x1800436e5  jmp     short loc_18004367A
0x1800436e7  xor     edi, edi
0x1800436e9  mov     r14, [rsp+98h+var_68]
0x1800436ee  test    r15d, r15d
0x1800436f1  jz      short loc_1800436FF
0x1800436f3  test    edi, edi
0x1800436f5  jnz     short loc_1800436FF
0x1800436f7  btr     esi, 0Ah
0x1800436fb  jmp     short loc_1800436FF
0x1800436fd  xor     edi, edi
0x1800436ff  test    sil, 40h
0x180043703  jz      short loc_18004370D
0x180043705  test    edi, edi
0x180043707  jz      short loc_18004370D
0x180043709  mov     eax, ebp
0x18004370b  jmp     short loc_18004370F
0x18004370d  xor     eax, eax
0x18004370f  and     esi, 0FFFFFFFEh
0x180043712  or      esi, eax
0x180043714  cmp     byte ptr [r13+1Ch], 0
0x180043719  jnz     short loc_180043724
0x18004371b  mov     eax, r12d
0x18004371e  neg     eax
0x180043720  sbb     ecx, ecx
0x180043722  and     ebp, ecx
0x180043724  mov     r15d, 9C1h
0x18004372a  mov     dword ptr [rsp+98h+var_78], ebx
0x18004372e  mov     edi, ebx
0x180043730  test    ebp, ebp
0x180043732  jz      short loc_18004374D
0x180043734  mov     dword ptr [rsp+98h+var_78], ebx
0x180043738  test    bl, 2
0x18004373b  jnz     short loc_18004374D
0x18004373d  mov     edi, esi
0x18004373f  xor     edi, ebx
0x180043741  and     edi, r15d
0x180043744  xor     edi, ebx
0x180043746  or      edi, 2
0x180043749  mov     dword ptr [rsp+98h+var_78], edi
0x18004374d  mov     ecx, ebx
0x18004374f  and     ecx, 4
0x180043752  jnz     short loc_180043767
0x180043754  mov     eax, edi
0x180043756  xor     edi, esi
0x180043758  and     edi, 400h
0x18004375e  xor     edi, eax
0x180043760  or      edi, 4
0x180043763  mov     dword ptr [rsp+98h+var_78], edi
0x180043767  mov     eax, ebx
0x180043769  lock cmpxchg [r14], edi
0x18004376e  jz      short loc_180043774
0x180043770  mov     ebx, eax
0x180043772  jmp     short loc_18004372A
0x180043774  test    ecx, ecx
0x180043776  jnz     short loc_180043794
0x180043778  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18004377f  test    rax, rax
0x180043782  jz      short loc_180043794
0x180043784  movzx   edx, byte ptr [r13+1Ch]
0x180043789  mov     r8d, r12d
0x18004378c  mov     rcx, r14
0x18004378f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043794  test    ebp, ebp
0x180043796  jnz     short loc_1800437A5
0x180043798  mov     eax, edi
0x18004379a  xor     eax, esi
0x18004379c  and     eax, r15d
0x18004379f  xor     eax, edi
0x1800437a1  mov     dword ptr [rsp+98h+var_78], eax
0x1800437a5  mov     rax, [rsp+98h+var_78]
0x1800437aa  mov     rcx, [rsp+98h+var_48]
0x1800437af  xor     rcx, rsp; StackCookie
0x1800437b2  call    __security_check_cookie
0x1800437b7  mov     rbx, [rsp+98h+arg_18]
0x1800437bf  add     rsp, 60h
0x1800437c3  pop     r15
0x1800437c5  pop     r14
0x1800437c7  pop     r13
0x1800437c9  pop     r12
0x1800437cb  pop     rdi
0x1800437cc  pop     rsi
0x1800437cd  pop     rbp
0x1800437ce  retn
```
