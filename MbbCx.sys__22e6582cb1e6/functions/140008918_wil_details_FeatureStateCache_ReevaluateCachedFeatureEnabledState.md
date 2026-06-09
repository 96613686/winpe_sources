# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140008918`
- end: `0x140008b6f`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `599`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008918`
- `0x140008bd0`

## callees

- `0x140008918`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000898f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000898f`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r15d
  signed __int32 v5; // ebx
  char v7; // cl
  BOOL v8; // ebp
  bool v9; // cf
  bool v10; // zf
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r9d
  int v16; // r10d
  int v17; // eax
  int v18; // ecx
  unsigned int v19; // r8d
  int v20; // esi
  unsigned int ***v21; // rdi
  unsigned int **v22; // rcx
  unsigned __int8 v23; // al
  BOOL v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // esi
  signed __int32 v27; // edi
  signed __int32 v28; // eax
  __int64 v31; // [rsp+20h] [rbp-68h]
  __int64 v32; // [rsp+28h] [rbp-60h]
  __int64 v33; // [rsp+30h] [rbp-58h] BYREF
  __int64 v34; // [rsp+38h] [rbp-50h] BYREF
  int v35; // [rsp+40h] [rbp-48h]

  v3 = 0;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges(a1);
  v7 = *(_BYTE *)(a3 + 28);
  v33 = 0;
  v7 -= 2;
  v8 = 1;
  v9 = v7 == 0;
  v10 = v7 == 1;
  v11 = *(unsigned int *)(a3 + 24);
  v34 = 0;
  v35 = 0;
  v12 = RtlQueryFeatureConfiguration(v11, !v9 && !v10, &v33, &v34, a2);
  if ( v12 )
  {
    v13 = 0;
    if ( v12 == 279 )
    {
      v14 = 1;
      v15 = 8 * (BYTE4(v34) & 0x80);
    }
    else
    {
      v14 = 0;
      v15 = 0;
    }
  }
  else
  {
    v13 = (HIDWORD(v34) >> 4) & 3;
    v14 = 1;
    v15 = 8 * (BYTE4(v34) & 0x80);
    if ( (v34 & 0x4000000000LL) != 0 )
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
  v20 = v19 | (v19 >> 6) & 1;
  if ( ((v19 >> 6) & 1) != 0 )
  {
    v21 = *(unsigned int ****)(a3 + 32);
    if ( v21 )
    {
      while ( (v20 & 1) != 0 )
      {
        v22 = *v21;
        if ( !*v21 )
          break;
        if ( *((_BYTE *)v22 + 30) || *((_BYTE *)v22 + 29) )
        {
          v25 = (v20 & 1) != 0 && *((_BYTE *)v22 + 31);
          v26 = v20 & 0xFFFFFFFE;
        }
        else
        {
          v32 = **v22;
          if ( (v32 & 2) != 0 )
            v23 = **v22;
          else
            v23 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v22, v32, v22);
          v24 = (v23 & (unsigned __int8)v20 & 1) != 0;
          v25 = v20 & 0xFFFFFFFE;
          v26 = v24;
        }
        v20 = v25 | v26;
        ++v21;
      }
    }
  }
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
        v27 = v5 ^ ((unsigned __int16)v5 ^ (unsigned __int16)v20) & 0x9C1 | 2;
        LODWORD(v31) = v27;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v27 = v27 ^ ((unsigned __int16)v20 ^ (unsigned __int16)v27) & 0x400 | 4;
      LODWORD(v31) = v27;
    }
    v28 = _InterlockedCompareExchange(a1, v27, v5);
    if ( v5 == v28 )
      break;
    v5 = v28;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v31) = v27 ^ ((unsigned __int16)v20 ^ (unsigned __int16)v27) & 0x9C1;
  return v31;
}

```

## disassembly

```asm
0x140008918  push    rbx
0x14000891a  push    rbp
0x14000891b  push    rsi
0x14000891c  push    rdi
0x14000891d  push    r12
0x14000891f  push    r14
0x140008921  push    r15
0x140008923  sub     rsp, 50h
0x140008927  mov     rax, cs:__security_cookie
0x14000892e  xor     rax, rsp
0x140008931  mov     [rsp+88h+var_40], rax
0x140008936  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14000893d  xor     r15d, r15d
0x140008940  mov     [rsp+88h+var_68], rdx
0x140008945  mov     r14, r8
0x140008948  mov     rbx, rdx
0x14000894b  mov     r12, rcx
0x14000894e  test    rax, rax
0x140008951  jz      short loc_14000895B
0x140008953  call    _guard_dispatch_icall
0x140008958  mov     r15d, eax
0x14000895b  mov     cl, [r14+1Ch]
0x14000895f  lea     r9, [rsp+88h+var_50]
0x140008964  xor     edx, edx
0x140008966  mov     [rsp+88h+var_58], 0
0x14000896f  sub     cl, 2
0x140008972  lea     r8, [rsp+88h+var_58]
0x140008977  lea     ebp, [rdx+1]
0x14000897a  cmp     cl, bpl
0x14000897d  mov     ecx, [r14+18h]
0x140008981  setnbe  dl
0x140008984  xor     eax, eax
0x140008986  mov     [rsp+88h+var_50], rax
0x14000898b  mov     [rsp+88h+var_48], eax
0x14000898f  call    cs:__imp_RtlQueryFeatureConfiguration
0x140008996  nop     dword ptr [rax+rax+00h]
0x14000899b  test    eax, eax
0x14000899d  jnz     short loc_1400089C9
0x14000899f  mov     ecx, dword ptr [rsp+88h+var_50+4]
0x1400089a3  mov     edx, ecx
0x1400089a5  mov     eax, ecx
0x1400089a7  shr     edx, 4
0x1400089aa  and     eax, 80h
0x1400089af  and     edx, 3
0x1400089b2  test    cl, 40h
0x1400089b5  mov     ecx, ebp
0x1400089b7  lea     r9d, ds:0[rax*8]
0x1400089bf  jz      short loc_1400089EC
0x1400089c1  mov     r10d, 800h
0x1400089c7  jmp     short loc_1400089EF
0x1400089c9  xor     edx, edx
0x1400089cb  cmp     eax, 117h
0x1400089d0  jnz     short loc_1400089E7
0x1400089d2  mov     eax, dword ptr [rsp+88h+var_50+4]
0x1400089d6  mov     ecx, ebp
0x1400089d8  and     eax, 80h
0x1400089dd  lea     r9d, ds:0[rax*8]
0x1400089e5  jmp     short loc_1400089EC
0x1400089e7  xor     ecx, ecx
0x1400089e9  xor     r9d, r9d
0x1400089ec  xor     r10d, r10d
0x1400089ef  neg     ecx
0x1400089f1  sbb     eax, eax
0x1400089f3  and     eax, edx
0x1400089f5  mov     r8d, eax
0x1400089f8  shl     r8d, 7
0x1400089fc  or      r8d, r9d
0x1400089ff  or      r8d, r10d
0x140008a02  test    eax, eax
0x140008a04  jnz     short loc_140008A13
0x140008a06  mov     al, [r14+1Fh]
0x140008a0a  neg     al
0x140008a0c  sbb     ecx, ecx
0x140008a0e  and     ecx, 40h
0x140008a11  jmp     short loc_140008A20
0x140008a13  xor     eax, eax
0x140008a15  mov     ecx, 40h ; '@'
0x140008a1a  cmp     edx, 2
0x140008a1d  cmovnz  ecx, eax
0x140008a20  or      r8d, ecx
0x140008a23  mov     eax, r8d
0x140008a26  shr     eax, 6
0x140008a29  and     eax, ebp
0x140008a2b  mov     esi, eax
0x140008a2d  or      esi, r8d
0x140008a30  test    eax, eax
0x140008a32  jz      loc_140008ABC
0x140008a38  mov     rdi, [r14+20h]
0x140008a3c  test    rdi, rdi
0x140008a3f  jz      short loc_140008ABC
0x140008a41  jmp     short loc_140008AB7
0x140008a43  mov     rcx, [rdi]
0x140008a46  test    rcx, rcx
0x140008a49  jz      short loc_140008ABC
0x140008a4b  cmp     byte ptr [rcx+1Eh], 0
0x140008a4f  jnz     short loc_140008A9D
0x140008a51  cmp     byte ptr [rcx+1Dh], 0
0x140008a55  jnz     short loc_140008A9D
0x140008a57  mov     r9, [rcx]
0x140008a5a  mov     [rsp+88h+var_60], 0
0x140008a63  mov     eax, [r9]
0x140008a66  mov     dword ptr [rsp+88h+var_60], eax
0x140008a6a  test    al, 2
0x140008a6c  jz      short loc_140008A75
0x140008a6e  mov     rax, [rsp+88h+var_60]
0x140008a73  jmp     short loc_140008A85
0x140008a75  mov     rdx, [rsp+88h+var_60]
0x140008a7a  mov     r8, rcx
0x140008a7d  mov     rcx, r9
0x140008a80  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x140008a85  mov     ecx, esi
0x140008a87  and     ecx, eax
0x140008a89  mov     eax, esi
0x140008a8b  test    bpl, cl
0x140008a8e  mov     ecx, 0
0x140008a93  setnz   cl
0x140008a96  and     eax, 0FFFFFFFEh
0x140008a99  mov     esi, ecx
0x140008a9b  jmp     short loc_140008AB1
0x140008a9d  test    bpl, sil
0x140008aa0  jz      short loc_140008AAC
0x140008aa2  cmp     byte ptr [rcx+1Fh], 0
0x140008aa6  jz      short loc_140008AAC
0x140008aa8  mov     eax, ebp
0x140008aaa  jmp     short loc_140008AAE
0x140008aac  xor     eax, eax
0x140008aae  and     esi, 0FFFFFFFEh
0x140008ab1  or      esi, eax
0x140008ab3  add     rdi, 8
0x140008ab7  test    bpl, sil
0x140008aba  jnz     short loc_140008A43
0x140008abc  cmp     byte ptr [r14+1Ch], 0
0x140008ac1  jnz     short loc_140008ACC
0x140008ac3  mov     eax, r15d
0x140008ac6  neg     eax
0x140008ac8  sbb     ecx, ecx
0x140008aca  and     ebp, ecx
0x140008acc  mov     dword ptr [rsp+88h+var_68], ebx
0x140008ad0  mov     edi, ebx
0x140008ad2  test    ebp, ebp
0x140008ad4  jz      short loc_140008AF2
0x140008ad6  mov     dword ptr [rsp+88h+var_68], ebx
0x140008ada  test    bl, 2
0x140008add  jnz     short loc_140008AF2
0x140008adf  mov     edi, esi
0x140008ae1  xor     edi, ebx
0x140008ae3  and     edi, 9C1h
0x140008ae9  xor     edi, ebx
0x140008aeb  or      edi, 2
0x140008aee  mov     dword ptr [rsp+88h+var_68], edi
0x140008af2  mov     ecx, ebx
0x140008af4  and     ecx, 4
0x140008af7  jnz     short loc_140008B0C
0x140008af9  mov     eax, edi
0x140008afb  xor     edi, esi
0x140008afd  and     edi, 400h
0x140008b03  xor     edi, eax
0x140008b05  or      edi, 4
0x140008b08  mov     dword ptr [rsp+88h+var_68], edi
0x140008b0c  mov     eax, ebx
0x140008b0e  lock cmpxchg [r12], edi
0x140008b14  jz      short loc_140008B1A
0x140008b16  mov     ebx, eax
0x140008b18  jmp     short loc_140008ACC
0x140008b1a  test    ecx, ecx
0x140008b1c  jnz     short loc_140008B3A
0x140008b1e  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140008b25  test    rax, rax
0x140008b28  jz      short loc_140008B3A
0x140008b2a  movzx   edx, byte ptr [r14+1Ch]
0x140008b2f  mov     r8d, r15d
0x140008b32  mov     rcx, r12
0x140008b35  call    _guard_dispatch_icall
0x140008b3a  test    ebp, ebp
0x140008b3c  jnz     short loc_140008B4D
0x140008b3e  mov     eax, edi
0x140008b40  xor     eax, esi
0x140008b42  and     eax, 9C1h
0x140008b47  xor     eax, edi
0x140008b49  mov     dword ptr [rsp+88h+var_68], eax
0x140008b4d  mov     rax, [rsp+88h+var_68]
0x140008b52  mov     rcx, [rsp+88h+var_40]
0x140008b57  xor     rcx, rsp; StackCookie
0x140008b5a  call    __security_check_cookie
0x140008b5f  add     rsp, 50h
0x140008b63  pop     r15
0x140008b65  pop     r14
0x140008b67  pop     r12
0x140008b69  pop     rdi
0x140008b6a  pop     rsi
0x140008b6b  pop     rbp
0x140008b6c  pop     rbx
0x140008b6d  retn
```
