# CPMKIDCacheHelpers::SaveNewPMKIDEntriesInPMKIDCache(CPortPropertyCache *,DOT11_PMKID_LIST *)

- ea: `0x1400b19b4`
- end: `0x1400b1cf4`
- name: `?SaveNewPMKIDEntriesInPMKIDCache@CPMKIDCacheHelpers@@SAHPEAVCPortPropertyCache@@PEAUDOT11_PMKID_LIST@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(struct CPortPropertyCache *this, struct DOT11_PMKID_LIST *Src)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002de30`
- `0x14007ea90`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x14001a630`
- `0x14002a9f8`
- `0x14005ab30`
- `0x1400b19b4`
- `0x1400dfd00`
- `0x1400dfe00`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b1ad6`
- `ntoskrnl!RtlCompareMemory` at `0x1400b1ad6`

## pseudocode

```c
__int64 __fastcall CPMKIDCacheHelpers::SaveNewPMKIDEntriesInPMKIDCache(
        struct CPortPropertyCache *this,
        struct DOT11_PMKID_LIST *Src)
{
  CPropertyCache *v3; // r14
  int PropertyBuffer; // eax
  __int64 v5; // rdx
  ULONG v6; // r15d
  struct DOT11_PMKID_LIST *v7; // rbx
  unsigned int v8; // ebx
  ULONG uNumOfEntries; // ebp
  struct DOT11_PMKID_LIST *v10; // rdi
  ULONG v11; // r12d
  ULONG i; // r14d
  __int64 v13; // r8
  unsigned int uTotalNumOfEntries; // ecx
  unsigned int v15; // r11d
  int v16; // r10d
  __int64 v17; // rcx
  struct DOT11_PMKID_LIST *v18; // rax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  unsigned int v23; // [rsp+50h] [rbp-168h] BYREF
  unsigned __int8 *v24; // [rsp+58h] [rbp-160h] BYREF
  struct CPortPropertyCache *v25; // [rsp+60h] [rbp-158h]
  _DWORD v26[64]; // [rsp+70h] [rbp-148h] BYREF

  v25 = this;
  v3 = this;
  v23 = 0;
  v24 = 0;
  memset(v26, 0, sizeof(v26));
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(v3, 0x2Cu, &v23, &v24);
  v6 = v23;
  if ( PropertyBuffer || v23 < 0xC )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        67,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
    }
    v7 = 0;
  }
  else
  {
    v7 = (struct DOT11_PMKID_LIST *)v24;
  }
  if ( v7 && v7->uTotalNumOfEntries >= 0x40 )
  {
    if ( v7->uNumOfEntries > 0x40 )
      return (unsigned int)-1073741811;
    uNumOfEntries = Src->uNumOfEntries;
    v10 = 0;
    v11 = 0;
    if ( uNumOfEntries )
    {
      do
      {
        for ( i = 0; i < v7->uNumOfEntries; ++i )
        {
          if ( RtlCompareMemory(&Src->PMKIDs[v11], &v7->PMKIDs[i], 6u) == 6 )
          {
            v26[i] = 1;
            --uNumOfEntries;
            break;
          }
        }
        ++v11;
      }
      while ( v11 < Src->uNumOfEntries );
      v3 = v25;
    }
    LODWORD(v13) = v7->uNumOfEntries;
    uTotalNumOfEntries = v7->uTotalNumOfEntries;
    if ( (unsigned int)v13 + uNumOfEntries <= uTotalNumOfEntries )
    {
      v15 = v13 + uNumOfEntries - 1;
      v16 = 0;
    }
    else
    {
      v15 = uTotalNumOfEntries - 1;
      v16 = uNumOfEntries + v13 - uTotalNumOfEntries;
      uNumOfEntries = uTotalNumOfEntries - v13;
    }
    while ( (_DWORD)v13 )
    {
      v13 = (unsigned int)(v13 - 1);
      if ( !v26[v13] )
      {
        if ( v16 )
        {
          --v16;
        }
        else
        {
          v5 = 28LL * (unsigned int)v13;
          v17 = v15--;
          *(_OWORD *)v7->PMKIDs[v17].BSSID = *(_OWORD *)&v7->PMKIDs[0].BSSID[v5];
          *(_OWORD *)&v7->PMKIDs[v17].PMKID[6] = *(_OWORD *)&v7->PMKIDs[0].PMKID[v5 + 6];
        }
      }
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v5) = 5;
      WPP_RECORDER_SF_ddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        0,
        69,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        Src->uNumOfEntries,
        v7->uNumOfEntries,
        uNumOfEntries,
        v15,
        v16);
    }
    memmove(v7->PMKIDs, Src->PMKIDs, 28LL * Src->uNumOfEntries);
    v7->uNumOfEntries += uNumOfEntries;
  }
  else
  {
    v6 = 1832;
    v18 = (struct DOT11_PMKID_LIST *)operator new(0x728u);
    v10 = v18;
    if ( v18 )
    {
      memset(v18, 0, 0x728u);
      memmove(v10, Src, 28LL * Src->uNumOfEntries + 12);
      v10->uTotalNumOfEntries = 64;
      v7 = v10;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          68,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids);
      }
      v7 = Src;
      v6 = 28 * Src->uNumOfEntries + 12;
    }
  }
  v20 = CPropertyCache::SetPropertyBuffer(v3, 0x2Cu, v6, &v7->Header.Type);
  v8 = v20;
  if ( v20 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v21) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v21,
      1,
      70,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      v20);
  }
  if ( v10 )
    operator delete(v10);
  return v8;
}

```

## disassembly

```asm
0x1400b19b4  mov     [rsp+arg_10], rbx
0x1400b19b9  push    rbp
0x1400b19ba  push    rsi
0x1400b19bb  push    rdi
0x1400b19bc  push    r12
0x1400b19be  push    r13
0x1400b19c0  push    r14
0x1400b19c2  push    r15
0x1400b19c4  sub     rsp, 180h
0x1400b19cb  mov     rax, cs:__security_cookie
0x1400b19d2  xor     rax, rsp
0x1400b19d5  mov     [rsp+1B8h+var_48], rax
0x1400b19dd  mov     rsi, rdx
0x1400b19e0  mov     [rsp+1B8h+var_158], rcx
0x1400b19e5  mov     r14, rcx
0x1400b19e8  xor     r13d, r13d
0x1400b19eb  xor     edx, edx; Val
0x1400b19ed  mov     [rsp+1B8h+var_168], r13d
0x1400b19f2  lea     rcx, [rsp+1B8h+var_148]; void *
0x1400b19f7  mov     [rsp+1B8h+var_160], r13
0x1400b19fc  mov     r8d, 100h; Size
0x1400b1a02  call    memset
0x1400b1a07  lea     r9, [rsp+1B8h+var_160]; unsigned __int8 **
0x1400b1a0c  mov     rcx, r14; this
0x1400b1a0f  lea     r8, [rsp+1B8h+var_168]; unsigned int *
0x1400b1a14  lea     edx, [r13+2Ch]; unsigned int
0x1400b1a18  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x1400b1a1d  mov     r15d, [rsp+1B8h+var_168]
0x1400b1a22  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400b1a29  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b1a30  test    eax, eax
0x1400b1a32  jnz     short loc_1400B1A41
0x1400b1a34  cmp     r15d, 0Ch
0x1400b1a38  jb      short loc_1400B1A41
0x1400b1a3a  mov     rbx, [rsp+1B8h+var_160]
0x1400b1a3f  jmp     short loc_1400B1A7B
0x1400b1a41  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400b1a48  jz      short loc_1400B1A78
0x1400b1a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1a51  cmp     byte ptr [rcx+29h], 5
0x1400b1a55  jnb     short loc_1400B1A5E
0x1400b1a57  cmp     [rcx+48h], r13w
0x1400b1a5c  jz      short loc_1400B1A78
0x1400b1a5e  mov     rcx, [rcx+40h]
0x1400b1a62  mov     r9d, 43h ; 'C'
0x1400b1a68  mov     dl, 5
0x1400b1a6a  mov     [rsp+1B8h+var_198], r12
0x1400b1a6f  lea     r8d, [r9-42h]
0x1400b1a73  call    WPP_RECORDER_SF_
0x1400b1a78  mov     rbx, r13
0x1400b1a7b  test    rbx, rbx
0x1400b1a7e  jz      loc_1400B1BF7
0x1400b1a84  cmp     dword ptr [rbx+8], 40h ; '@'
0x1400b1a88  jb      loc_1400B1BF7
0x1400b1a8e  cmp     dword ptr [rbx+4], 40h ; '@'
0x1400b1a92  jbe     short loc_1400B1A9E
0x1400b1a94  mov     ebx, 0C000000Dh
0x1400b1a99  jmp     loc_1400B1CC6
0x1400b1a9e  mov     ebp, [rsi+4]
0x1400b1aa1  mov     rdi, r13
0x1400b1aa4  mov     r12d, r13d
0x1400b1aa7  test    ebp, ebp
0x1400b1aa9  jz      short loc_1400B1B09
0x1400b1aab  mov     r14d, r13d
0x1400b1aae  cmp     r14d, [rbx+4]
0x1400b1ab2  jnb     short loc_1400B1AF8
0x1400b1ab4  mov     eax, r12d
0x1400b1ab7  mov     r8d, 6; Length
0x1400b1abd  imul    rcx, rax, 1Ch
0x1400b1ac1  mov     r13d, r14d
0x1400b1ac4  add     rcx, 0Ch
0x1400b1ac8  imul    rdx, r13, 1Ch
0x1400b1acc  add     rcx, rsi; Source1
0x1400b1acf  add     rdx, 0Ch
0x1400b1ad3  add     rdx, rbx; Source2
0x1400b1ad6  call    cs:__imp_RtlCompareMemory
0x1400b1add  nop     dword ptr [rax+rax+00h]
0x1400b1ae2  cmp     rax, 6
0x1400b1ae6  jz      short loc_1400B1AED
0x1400b1ae8  inc     r14d
0x1400b1aeb  jmp     short loc_1400B1AAE
0x1400b1aed  mov     [rsp+r13*4+1B8h+var_148], 1
0x1400b1af6  dec     ebp
0x1400b1af8  inc     r12d
0x1400b1afb  mov     r13, rdi
0x1400b1afe  cmp     r12d, [rsi+4]
0x1400b1b02  jb      short loc_1400B1AAB
0x1400b1b04  mov     r14, [rsp+1B8h+var_158]
0x1400b1b09  mov     r8d, [rbx+4]
0x1400b1b0d  mov     ecx, [rbx+8]
0x1400b1b10  lea     eax, [r8+rbp]
0x1400b1b14  cmp     eax, ecx
0x1400b1b16  jbe     short loc_1400B1B2A
0x1400b1b18  mov     r10d, r8d
0x1400b1b1b  lea     r11d, [rcx-1]
0x1400b1b1f  sub     r10d, ecx
0x1400b1b22  add     r10d, ebp
0x1400b1b25  sub     ebp, r10d
0x1400b1b28  jmp     short loc_1400B1B6C
0x1400b1b2a  lea     r11d, [rax-1]
0x1400b1b2e  mov     r10d, r13d
0x1400b1b31  jmp     short loc_1400B1B6C
0x1400b1b33  dec     r8d
0x1400b1b36  mov     eax, r8d
0x1400b1b39  cmp     [rsp+r8*4+1B8h+var_148], r13d
0x1400b1b3e  jnz     short loc_1400B1B6C
0x1400b1b40  test    r10d, r10d
0x1400b1b43  jz      short loc_1400B1B4A
0x1400b1b45  dec     r10d
0x1400b1b48  jmp     short loc_1400B1B6C
0x1400b1b4a  imul    rdx, rax, 1Ch
0x1400b1b4e  mov     eax, r11d
0x1400b1b51  imul    rcx, rax, 1Ch
0x1400b1b55  movups  xmm0, xmmword ptr [rdx+rbx+0Ch]
0x1400b1b5a  dec     r11d
0x1400b1b5d  movups  xmmword ptr [rcx+rbx+0Ch], xmm0
0x1400b1b62  movups  xmm1, xmmword ptr [rdx+rbx+18h]
0x1400b1b67  movups  xmmword ptr [rcx+rbx+18h], xmm1
0x1400b1b6c  test    r8d, r8d
0x1400b1b6f  jnz     short loc_1400B1B33
0x1400b1b71  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b1b78  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b1b7f  jz      short loc_1400B1BD0
0x1400b1b81  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1b88  cmp     byte ptr [rcx+29h], 5
0x1400b1b8c  jnb     short loc_1400B1B95
0x1400b1b8e  cmp     [rcx+48h], r13w
0x1400b1b93  jz      short loc_1400B1BD0
0x1400b1b95  mov     eax, [rbx+4]
0x1400b1b98  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b1b9f  mov     rcx, [rcx+40h]
0x1400b1ba3  mov     r9d, 45h ; 'E'
0x1400b1ba9  mov     [rsp+1B8h+var_170], r10d
0x1400b1bae  mov     dl, 5
0x1400b1bb0  mov     [rsp+1B8h+var_178], r11d
0x1400b1bb5  mov     [rsp+1B8h+var_180], ebp
0x1400b1bb9  mov     [rsp+1B8h+var_188], eax
0x1400b1bbd  mov     eax, [rsi+4]
0x1400b1bc0  mov     [rsp+1B8h+var_190], eax
0x1400b1bc4  mov     [rsp+1B8h+var_198], r12
0x1400b1bc9  call    WPP_RECORDER_SF_ddddd
0x1400b1bce  jmp     short loc_1400B1BD7
0x1400b1bd0  lea     r12, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b1bd7  mov     eax, [rsi+4]
0x1400b1bda  lea     rdx, [rsi+0Ch]; Src
0x1400b1bde  imul    r8, rax, 1Ch; Size
0x1400b1be2  lea     rcx, [rbx+0Ch]; void *
0x1400b1be6  call    memmove
0x1400b1beb  add     [rbx+4], ebp
0x1400b1bee  lea     rbp, WPP_RECORDER_INITIALIZED
0x1400b1bf5  jmp     short loc_1400B1C72
0x1400b1bf7  mov     r15d, 728h
0x1400b1bfd  mov     ecx, r15d; unsigned __int64
0x1400b1c00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b1c05  mov     rdi, rax
0x1400b1c08  test    rax, rax
0x1400b1c0b  jz      short loc_1400B1C3C
0x1400b1c0d  mov     r8d, r15d; Size
0x1400b1c10  xor     edx, edx; Val
0x1400b1c12  mov     rcx, rax; void *
0x1400b1c15  call    memset
0x1400b1c1a  mov     ecx, [rsi+4]
0x1400b1c1d  mov     rdx, rsi; Src
0x1400b1c20  imul    r8, rcx, 1Ch
0x1400b1c24  mov     rcx, rdi; void *
0x1400b1c27  add     r8, 0Ch; Size
0x1400b1c2b  call    memmove
0x1400b1c30  mov     dword ptr [rdi+8], 40h ; '@'
0x1400b1c37  mov     rbx, rdi
0x1400b1c3a  jmp     short loc_1400B1C72
0x1400b1c3c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400b1c43  jz      short loc_1400B1C66
0x1400b1c45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1c4c  mov     r9d, 44h ; 'D'
0x1400b1c52  mov     dl, 2
0x1400b1c54  mov     [rsp+1B8h+var_198], r12
0x1400b1c59  mov     rcx, [rcx+40h]
0x1400b1c5d  lea     r8d, [r9-43h]
0x1400b1c61  call    WPP_RECORDER_SF_
0x1400b1c66  imul    r15d, [rsi+4], 1Ch
0x1400b1c6b  mov     rbx, rsi
0x1400b1c6e  add     r15d, 0Ch
0x1400b1c72  mov     r9, rbx; unsigned __int8 *
0x1400b1c75  mov     r8d, r15d; unsigned int
0x1400b1c78  mov     edx, 2Ch ; ','; unsigned int
0x1400b1c7d  mov     rcx, r14; this
0x1400b1c80  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)
0x1400b1c85  mov     ebx, eax
0x1400b1c87  test    eax, eax
0x1400b1c89  jz      short loc_1400B1CB9
0x1400b1c8b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400b1c92  jz      short loc_1400B1CB9
0x1400b1c94  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1c9b  mov     r9d, 46h ; 'F'
0x1400b1ca1  mov     [rsp+1B8h+var_190], eax
0x1400b1ca5  mov     dl, 2
0x1400b1ca7  mov     [rsp+1B8h+var_198], r12
0x1400b1cac  mov     rcx, [rcx+40h]
0x1400b1cb0  lea     r8d, [r9-45h]
0x1400b1cb4  call    WPP_RECORDER_SF_d
0x1400b1cb9  test    rdi, rdi
0x1400b1cbc  jz      short loc_1400B1CC6
0x1400b1cbe  mov     rcx, rdi; void *
0x1400b1cc1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b1cc6  mov     eax, ebx
0x1400b1cc8  mov     rcx, [rsp+1B8h+var_48]
0x1400b1cd0  xor     rcx, rsp; StackCookie
0x1400b1cd3  call    __security_check_cookie
0x1400b1cd8  mov     rbx, [rsp+1B8h+arg_10]
0x1400b1ce0  add     rsp, 180h
0x1400b1ce7  pop     r15
0x1400b1ce9  pop     r14
0x1400b1ceb  pop     r13
0x1400b1ced  pop     r12
0x1400b1cef  pop     rdi
0x1400b1cf0  pop     rsi
0x1400b1cf1  pop     rbp
0x1400b1cf2  retn
```
