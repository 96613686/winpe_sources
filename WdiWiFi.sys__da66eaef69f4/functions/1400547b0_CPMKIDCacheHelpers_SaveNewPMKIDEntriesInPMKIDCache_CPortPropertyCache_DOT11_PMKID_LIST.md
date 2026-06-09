# CPMKIDCacheHelpers::SaveNewPMKIDEntriesInPMKIDCache(CPortPropertyCache *,DOT11_PMKID_LIST *)

- ea: `0x1400547b0`
- end: `0x140054b3c`
- name: `?SaveNewPMKIDEntriesInPMKIDCache@CPMKIDCacheHelpers@@SAHPEAVCPortPropertyCache@@PEAUDOT11_PMKID_LIST@@@Z`
- size: `908`
- prototype: `__int64 __fastcall(CPropertyCache *this, struct DOT11_PMKID_LIST *Src)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400544f0`
- `0x1400b2040`

## callees

- `0x140010390`
- `0x1400109f8`
- `0x140023ae0`
- `0x140034e04`
- `0x140034ec4`
- `0x14005360c`
- `0x1400547b0`
- `0x1400da4f0`
- `0x1400da740`
- `0x1400dac80`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140054942`
- `ntoskrnl!RtlCompareMemory` at `0x140054942`
- `ntoskrnl!ExAllocatePool2` at `0x140054863`
- `ntoskrnl!ExAllocatePool2` at `0x140054863`

## pseudocode

```c
__int64 __fastcall CPMKIDCacheHelpers::SaveNewPMKIDEntriesInPMKIDCache(
        CPropertyCache *this,
        struct DOT11_PMKID_LIST *Src)
{
  CPropertyCache *v3; // r14
  int PropertyBuffer; // eax
  unsigned int v5; // r12d
  __int64 v6; // rdx
  struct DOT11_PMKID_LIST *v7; // rbx
  struct DOT11_PMKID_LIST *Pool2; // rax
  int v9; // edx
  struct DOT11_PMKID_LIST *v10; // rdi
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // ebx
  unsigned int uNumOfEntries; // ebp
  unsigned int v16; // r15d
  unsigned int i; // r14d
  __int64 v18; // r8
  unsigned int uTotalNumOfEntries; // ecx
  unsigned int v20; // r11d
  int v21; // r10d
  __int64 v22; // rcx
  __int64 v23; // [rsp+28h] [rbp-190h]
  unsigned int v24; // [rsp+50h] [rbp-168h] BYREF
  unsigned __int8 *v25; // [rsp+58h] [rbp-160h] BYREF
  CPropertyCache *v26; // [rsp+60h] [rbp-158h]
  _DWORD v27[64]; // [rsp+70h] [rbp-148h] BYREF

  v26 = this;
  v3 = this;
  v24 = 0;
  v25 = 0;
  memset(v27, 0, sizeof(v27));
  PropertyBuffer = CPropertyCache::GetPropertyBuffer(v3, 0x2Bu, &v24, &v25);
  v5 = v24;
  v6 = (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids;
  if ( PropertyBuffer || v24 < 0xC )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        1,
        41,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
    }
    v7 = 0;
  }
  else
  {
    v7 = (struct DOT11_PMKID_LIST *)v25;
  }
  if ( v7 && v7->uTotalNumOfEntries >= 0x40 )
  {
    if ( v7->uNumOfEntries > 0x40 )
      return (unsigned int)-1073741811;
    uNumOfEntries = Src->uNumOfEntries;
    v10 = 0;
    v16 = 0;
    if ( uNumOfEntries )
    {
      do
      {
        for ( i = 0; i < v7->uNumOfEntries; ++i )
        {
          if ( RtlCompareMemory(&Src->PMKIDs[v16], &v7->PMKIDs[i], 6u) == 6 )
          {
            v27[i] = 1;
            --uNumOfEntries;
            break;
          }
        }
        ++v16;
      }
      while ( v16 < Src->uNumOfEntries );
      v3 = v26;
    }
    LODWORD(v18) = v7->uNumOfEntries;
    uTotalNumOfEntries = v7->uTotalNumOfEntries;
    if ( (unsigned int)v18 + uNumOfEntries > uTotalNumOfEntries )
    {
      v20 = uTotalNumOfEntries - 1;
      v21 = uNumOfEntries + v18 - uTotalNumOfEntries;
      uNumOfEntries = uTotalNumOfEntries - v18;
    }
    else
    {
      v20 = v18 + uNumOfEntries - 1;
      v21 = 0;
    }
    while ( (_DWORD)v18 )
    {
      v18 = (unsigned int)(v18 - 1);
      if ( !v27[v18] )
      {
        if ( v21 )
        {
          --v21;
        }
        else
        {
          v6 = 28LL * (unsigned int)v18;
          v22 = v20--;
          *(_OWORD *)v7->PMKIDs[v22].BSSID = *(_OWORD *)&v7->PMKIDs[0].BSSID[v6];
          *(_OWORD *)&v7->PMKIDs[v22].PMKID[6] = *(_OWORD *)&v7->PMKIDs[0].PMKID[v6 + 6];
        }
      }
    }
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
      && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v6) = 5;
      WPP_RECORDER_SF_ddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        0,
        43,
        (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
        Src->uNumOfEntries,
        v7->uNumOfEntries,
        uNumOfEntries,
        v20,
        v21);
    }
    memmove(v7->PMKIDs, Src->PMKIDs, 28LL * Src->uNumOfEntries);
    v7->uNumOfEntries += uNumOfEntries;
  }
  else
  {
    v5 = 1832;
    Pool2 = (struct DOT11_PMKID_LIST *)ExAllocatePool2(64, 1832, 1198089303);
    v10 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, 0x728u);
      memmove(v10, Src, 28LL * Src->uNumOfEntries + 12);
      v10->uTotalNumOfEntries = 64;
      v7 = v10;
    }
    else
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          1,
          42,
          (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids);
      }
      v7 = Src;
      v5 = 28 * Src->uNumOfEntries + 12;
    }
  }
  v11 = CPropertyCache::SetPropertyBuffer(v3, 0x2Bu, v5, &v7->Header.Type);
  v13 = v11;
  if ( v11 && *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v23) = v11;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      44,
      (__int64)WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids,
      v23);
  }
  if ( v10 )
    operator delete(v10);
  return v13;
}

```

## disassembly

```asm
0x1400547b0  mov     [rsp+arg_10], rbx
0x1400547b5  push    rbp
0x1400547b6  push    rsi
0x1400547b7  push    rdi
0x1400547b8  push    r12
0x1400547ba  push    r13
0x1400547bc  push    r14
0x1400547be  push    r15
0x1400547c0  sub     rsp, 180h
0x1400547c7  mov     rax, cs:__security_cookie
0x1400547ce  xor     rax, rsp
0x1400547d1  mov     [rsp+1B8h+var_48], rax
0x1400547d9  mov     rsi, rdx
0x1400547dc  mov     [rsp+1B8h+var_158], rcx
0x1400547e1  mov     r14, rcx
0x1400547e4  xor     r13d, r13d
0x1400547e7  xor     edx, edx; Val
0x1400547e9  mov     [rsp+1B8h+var_168], r13d
0x1400547ee  lea     rcx, [rsp+1B8h+var_148]; void *
0x1400547f3  mov     [rsp+1B8h+var_160], r13
0x1400547f8  mov     r8d, 100h; Size
0x1400547fe  call    memset
0x140054803  lea     r9, [rsp+1B8h+var_160]; unsigned __int8 **
0x140054808  mov     rcx, r14; this
0x14005480b  lea     r8, [rsp+1B8h+var_168]; unsigned int *
0x140054810  lea     edx, [r13+2Bh]; unsigned int
0x140054814  call    ?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z; CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)
0x140054819  mov     r12d, [rsp+1B8h+var_168]
0x14005481e  lea     r15, WPP_RECORDER_INITIALIZED
0x140054825  lea     rdx, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x14005482c  test    eax, eax
0x14005482e  jnz     loc_140054A5E
0x140054834  cmp     r12d, 0Ch
0x140054838  jb      loc_140054A5E
0x14005483e  mov     rbx, [rsp+1B8h+var_160]
0x140054843  mov     ebp, 40h ; '@'
0x140054848  test    rbx, rbx
0x14005484b  jnz     loc_1400548F8
0x140054851  mov     r12d, 728h
0x140054857  mov     r8d, 47696457h
0x14005485d  mov     edx, r12d
0x140054860  mov     rcx, rbp
0x140054863  call    cs:__imp_ExAllocatePool2
0x14005486a  nop     dword ptr [rax+rax+00h]
0x14005486f  mov     rdi, rax
0x140054872  test    rax, rax
0x140054875  jz      loc_140054AAF
0x14005487b  mov     r8d, r12d; Size
0x14005487e  xor     edx, edx; Val
0x140054880  mov     rcx, rax; void *
0x140054883  call    memset
0x140054888  mov     ecx, [rsi+4]
0x14005488b  mov     rdx, rsi; Src
0x14005488e  imul    r8, rcx, 1Ch
0x140054892  mov     rcx, rdi; void *
0x140054895  add     r8, 0Ch; Size
0x140054899  call    memmove
0x14005489e  mov     [rdi+8], ebp
0x1400548a1  mov     rbx, rdi
0x1400548a4  mov     r9, rbx; unsigned __int8 *
0x1400548a7  mov     r8d, r12d; unsigned int
0x1400548aa  mov     edx, 2Bh ; '+'; unsigned int
0x1400548af  mov     rcx, r14; this
0x1400548b2  call    ?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEAE@Z; CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar *)
0x1400548b7  mov     ebx, eax
0x1400548b9  test    eax, eax
0x1400548bb  jnz     loc_140054AF1
0x1400548c1  test    rdi, rdi
0x1400548c4  jnz     loc_140054B2F
0x1400548ca  mov     eax, ebx
0x1400548cc  mov     rcx, [rsp+1B8h+var_48]
0x1400548d4  xor     rcx, rsp; StackCookie
0x1400548d7  call    __security_check_cookie
0x1400548dc  mov     rbx, [rsp+1B8h+arg_10]
0x1400548e4  add     rsp, 180h
0x1400548eb  pop     r15
0x1400548ed  pop     r14
0x1400548ef  pop     r13
0x1400548f1  pop     r12
0x1400548f3  pop     rdi
0x1400548f4  pop     rsi
0x1400548f5  pop     rbp
0x1400548f6  retn
0x1400548f8  cmp     [rbx+8], ebp
0x1400548fb  jb      loc_140054851
0x140054901  cmp     [rbx+4], ebp
0x140054904  ja      loc_140054A9D
0x14005490a  mov     ebp, [rsi+4]
0x14005490d  mov     rdi, r13
0x140054910  mov     r15d, r13d
0x140054913  test    ebp, ebp
0x140054915  jz      short loc_140054975
0x140054917  mov     r14d, r13d
0x14005491a  cmp     r14d, [rbx+4]
0x14005491e  jnb     short loc_140054964
0x140054920  mov     eax, r15d
0x140054923  mov     r8d, 6; Length
0x140054929  imul    rcx, rax, 1Ch
0x14005492d  mov     r13d, r14d
0x140054930  add     rcx, 0Ch
0x140054934  imul    rdx, r13, 1Ch
0x140054938  add     rcx, rsi; Source1
0x14005493b  add     rdx, 0Ch
0x14005493f  add     rdx, rbx; Source2
0x140054942  call    cs:__imp_RtlCompareMemory
0x140054949  nop     dword ptr [rax+rax+00h]
0x14005494e  cmp     rax, 6
0x140054952  jz      short loc_140054959
0x140054954  inc     r14d
0x140054957  jmp     short loc_14005491A
0x140054959  mov     [rsp+r13*4+1B8h+var_148], 1
0x140054962  dec     ebp
0x140054964  inc     r15d
0x140054967  mov     r13, rdi
0x14005496a  cmp     r15d, [rsi+4]
0x14005496e  jb      short loc_140054917
0x140054970  mov     r14, [rsp+1B8h+var_158]
0x140054975  mov     r8d, [rbx+4]
0x140054979  mov     ecx, [rbx+8]
0x14005497c  lea     eax, [r8+rbp]
0x140054980  cmp     eax, ecx
0x140054982  ja      loc_140054A0E
0x140054988  lea     r11d, [rax-1]
0x14005498c  mov     r10d, r13d
0x14005498f  test    r8d, r8d
0x140054992  jz      short loc_1400549CE
0x140054994  dec     r8d
0x140054997  mov     eax, r8d
0x14005499a  cmp     [rsp+r8*4+1B8h+var_148], r13d
0x14005499f  jnz     short loc_14005498F
0x1400549a1  test    r10d, r10d
0x1400549a4  jnz     loc_140054AA7
0x1400549aa  imul    rdx, rax, 1Ch
0x1400549ae  mov     eax, r11d
0x1400549b1  imul    rcx, rax, 1Ch
0x1400549b5  movups  xmm0, xmmword ptr [rdx+rbx+0Ch]
0x1400549ba  dec     r11d
0x1400549bd  movups  xmmword ptr [rcx+rbx+0Ch], xmm0
0x1400549c2  movups  xmm1, xmmword ptr [rdx+rbx+18h]
0x1400549c7  movups  xmmword ptr [rcx+rbx+18h], xmm1
0x1400549cc  jmp     short loc_14005498F
0x1400549ce  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400549d5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400549dc  jz      short loc_1400549F2
0x1400549de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400549e5  cmp     byte ptr [rcx+29h], 5
0x1400549e9  jnb     short loc_140054A23
0x1400549eb  cmp     [rcx+48h], r13w
0x1400549f0  jnz     short loc_140054A23
0x1400549f2  mov     eax, [rsi+4]
0x1400549f5  lea     rdx, [rsi+0Ch]; Src
0x1400549f9  imul    r8, rax, 1Ch; Size
0x1400549fd  lea     rcx, [rbx+0Ch]; void *
0x140054a01  call    memmove
0x140054a06  add     [rbx+4], ebp
0x140054a09  jmp     loc_1400548A4
0x140054a0e  mov     r10d, r8d
0x140054a11  lea     r11d, [rcx-1]
0x140054a15  sub     r10d, ecx
0x140054a18  add     r10d, ebp
0x140054a1b  sub     ebp, r10d
0x140054a1e  jmp     loc_14005498F
0x140054a23  mov     eax, [rbx+4]
0x140054a26  mov     r9d, 2Bh ; '+'
0x140054a2c  mov     rcx, [rcx+40h]
0x140054a30  mov     dl, 5
0x140054a32  mov     [rsp+1B8h+var_170], r10d
0x140054a37  mov     [rsp+1B8h+var_178], r11d
0x140054a3c  mov     [rsp+1B8h+var_180], ebp
0x140054a40  mov     [rsp+1B8h+var_188], eax
0x140054a44  mov     eax, [rsi+4]
0x140054a47  mov     dword ptr [rsp+1B8h+var_190], eax
0x140054a4b  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140054a52  mov     [rsp+1B8h+var_198], rax
0x140054a57  call    WPP_RECORDER_SF_ddddd
0x140054a5c  jmp     short loc_1400549F2
0x140054a5e  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140054a65  jz      short loc_140054A95
0x140054a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140054a6e  cmp     byte ptr [rcx+29h], 5
0x140054a72  jnb     short loc_140054A7B
0x140054a74  cmp     [rcx+48h], r13w
0x140054a79  jz      short loc_140054A95
0x140054a7b  mov     rcx, [rcx+40h]
0x140054a7f  mov     r9d, 29h ; ')'
0x140054a85  mov     [rsp+1B8h+var_198], rdx
0x140054a8a  mov     dl, 5
0x140054a8c  lea     r8d, [r9-28h]
0x140054a90  call    WPP_RECORDER_SF_
0x140054a95  mov     rbx, r13
0x140054a98  jmp     loc_140054843
0x140054a9d  mov     ebx, 0C000000Dh
0x140054aa2  jmp     loc_1400548CA
0x140054aa7  dec     r10d
0x140054aaa  jmp     loc_14005498F
0x140054aaf  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140054ab6  jz      short loc_140054AE0
0x140054ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x140054abf  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140054ac6  mov     r9d, 2Ah ; '*'
0x140054acc  mov     [rsp+1B8h+var_198], rax
0x140054ad1  mov     dl, 2
0x140054ad3  mov     rcx, [rcx+40h]
0x140054ad7  lea     r8d, [r9-29h]
0x140054adb  call    WPP_RECORDER_SF_
0x140054ae0  imul    r12d, [rsi+4], 1Ch
0x140054ae5  mov     rbx, rsi
0x140054ae8  add     r12d, 0Ch
0x140054aec  jmp     loc_1400548A4
0x140054af1  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140054af8  jz      loc_1400548C1
0x140054afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140054b05  mov     r9d, 2Ch ; ','
0x140054b0b  mov     dword ptr [rsp+1B8h+var_190], eax
0x140054b0f  mov     dl, 2
0x140054b11  lea     rax, WPP_4ce070d3319431f0750a2f0fcbe8aee5_Traceguids
0x140054b18  mov     [rsp+1B8h+var_198], rax
0x140054b1d  mov     rcx, [rcx+40h]
0x140054b21  lea     r8d, [r9-2Bh]
0x140054b25  call    WPP_RECORDER_SF_D
0x140054b2a  jmp     loc_1400548C1
0x140054b2f  mov     rcx, rdi; void *
0x140054b32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140054b37  jmp     loc_1400548CA
```
