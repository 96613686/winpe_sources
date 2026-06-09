# ScCacheRead

- ea: `0x18002896c`
- end: `0x180028c7f`
- name: `ScCacheRead`
- size: `787`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180021724`
- `0x180022754`
- `0x180022a88`
- `0x180023504`

## callees

- `0x18000a766`
- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x1800281b8`
- `0x180028244`
- `0x18002896c`
- `0x1800292d0`
- `0x1800296c0`
- `0x18002e010`

## import_xrefs

- `msvcrt!time` at `0x180028b51`
- `msvcrt!time` at `0x180028b51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028b17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c1a`

## string_xrefs

- `0x180028ad0`: `ScCacheRead`

## pseudocode

```c
__int64 __fastcall ScCacheRead(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        _QWORD *a7,
        _DWORD *a8)
{
  __int64 v9; // rbx
  int v10; // esi
  PVOID v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // r8
  unsigned int Item; // eax
  __int64 v17; // rdi
  __int64 v18; // rdx
  LPCRITICAL_SECTION v19; // rcx
  void *v20; // rax
  __int64 v21; // rcx
  __int128 v23; // [rsp+A8h] [rbp-29h] BYREF
  int v24; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-11h]
  int v26; // [rsp+C8h] [rbp-9h]
  __int64 v27; // [rsp+D0h] [rbp-1h]
  time_t Time; // [rsp+118h] [rbp+47h] BYREF
  int v29; // [rsp+128h] [rbp+57h]
  __int64 v30; // [rsp+130h] [rbp+5Fh]

  v30 = a4;
  v29 = a3;
  Time = 0;
  v9 = a4;
  v10 = a3;
  WppTraceIndent((__int64)lpCriticalSection, 0);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v23 = 0;
  if ( v9 )
  {
    if ( !a2 )
    {
      v13 = -2146434960;
      goto LABEL_31;
    }
    WppTraceIndent((__int64)v12, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_ssDDDDDDDDDDDSDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        *(unsigned __int8 *)(a2 + 14),
        *(unsigned __int8 *)(a2 + 13),
        (__int64)"ScCacheRead",
        *(_DWORD *)a2,
        *(_WORD *)(a2 + 4),
        *(_WORD *)(a2 + 6),
        *(_BYTE *)(a2 + 8),
        *(_BYTE *)(a2 + 9),
        *(_BYTE *)(a2 + 10),
        *(_BYTE *)(a2 + 11),
        *(_BYTE *)(a2 + 12),
        *(_BYTE *)(a2 + 13),
        *(_BYTE *)(a2 + 14),
        *(_BYTE *)(a2 + 15),
        v30,
        v29);
      v9 = v30;
      v10 = v29;
    }
    v24 = 16;
    v14 = -1;
    v25 = a2;
    do
      ++v14;
    while ( *(_WORD *)(v9 + 2 * v14) );
    v27 = v9;
    v26 = 2 * v14;
    EnterCriticalSection(lpCriticalSection);
    Item = CacheGetItem(lpCriticalSection[1].DebugInfo, &v24, v15, &v23);
    v13 = Item;
    if ( Item )
    {
      if ( Item == 1168 )
        v13 = -2146434960;
    }
    else
    {
      v17 = *((_QWORD *)&v23 + 1);
      time(&Time);
      if ( Time - *(_QWORD *)(v17 + 16) < 0
        || *(__int64 *)(v17 + 16) < 0
        || Time - *(_QWORD *)(v17 + 16) > (unsigned int)(86400 * LODWORD(lpCriticalSection[2].OwningThread)) )
      {
        v18 = v17;
        v19 = lpCriticalSection;
      }
      else
      {
        v18 = v17;
        v19 = lpCriticalSection;
        if ( v10 == *(_DWORD *)(v17 + 12) )
        {
          I_ServerCacheSetMRU(lpCriticalSection, v17);
          v20 = (void *)(*(__int64 (__fastcall **)(_QWORD))&lpCriticalSection[1].LockCount)(*(unsigned int *)(v17 + 8));
          v21 = (__int64)a7;
          *a7 = v20;
          if ( v20 )
          {
            memcpy_0(v20, *(const void **)v17, *(unsigned int *)(v17 + 8));
            *a8 = *(_DWORD *)(v17 + 8);
          }
          else
          {
            WppTraceIndent(v21, 2u);
            v13 = 8;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_s(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
                WPP_pszIndent);
            }
          }
          goto LABEL_30;
        }
      }
      I_ServerCacheRemoveItem(v19, v18, &v24);
      v13 = -2146434959;
    }
LABEL_30:
    LeaveCriticalSection(lpCriticalSection);
    goto LABEL_31;
  }
  v13 = -2146435068;
LABEL_31:
  WppTraceIndent((__int64)v12, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x18002896c  mov     rax, rsp
0x18002896f  mov     [rax+10h], rbx
0x180028973  mov     [rax+20h], r9
0x180028977  mov     [rax+18h], r8d
0x18002897b  push    rbp
0x18002897c  push    rsi
0x18002897d  push    rdi
0x18002897e  push    r12
0x180028980  push    r13
0x180028982  push    r14
0x180028984  push    r15
0x180028986  lea     rbp, [rax-3Fh]
0x18002898a  sub     rsp, 0D0h
0x180028991  mov     r12, rdx
0x180028994  xor     r14d, r14d
0x180028997  xor     edx, edx
0x180028999  mov     [rbp+37h+Time], r14
0x18002899d  mov     rbx, r9
0x1800289a0  mov     esi, r8d
0x1800289a3  mov     r13, rcx
0x1800289a6  call    WppTraceIndent
0x1800289ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289b2  lea     r15, WPP_GLOBAL_Control
0x1800289b9  cmp     rcx, r15
0x1800289bc  jz      short loc_1800289E5
0x1800289be  test    byte ptr [rcx+1Ch], 2
0x1800289c2  jz      short loc_1800289E5
0x1800289c4  cmp     byte ptr [rcx+19h], 5
0x1800289c8  jb      short loc_1800289E5
0x1800289ca  mov     r9, cs:WPP_pszIndent
0x1800289d1  lea     edx, [r14+17h]
0x1800289d5  mov     rcx, [rcx+10h]
0x1800289d9  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800289e0  call    WPP_SF_s
0x1800289e5  xorps   xmm0, xmm0
0x1800289e8  movups  [rbp+37h+var_60], xmm0
0x1800289ec  test    rbx, rbx
0x1800289ef  jnz     short loc_1800289FB
0x1800289f1  mov     ebx, 80100004h
0x1800289f6  jmp     loc_180028C20
0x1800289fb  test    r12, r12
0x1800289fe  jnz     short loc_180028A0A
0x180028a00  mov     ebx, 80100070h
0x180028a05  jmp     loc_180028C20
0x180028a0a  mov     edx, 2
0x180028a0f  call    WppTraceIndent
0x180028a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a1b  cmp     rcx, r15
0x180028a1e  jz      loc_180028AF2
0x180028a24  test    byte ptr [rcx+1Ch], 4
0x180028a28  jz      loc_180028AF2
0x180028a2e  cmp     byte ptr [rcx+19h], 4
0x180028a32  jb      loc_180028AF2
0x180028a38  movzx   eax, byte ptr [r12+0Fh]
0x180028a3e  mov     edx, 18h
0x180028a43  mov     ecx, [rbp+37h+arg_10]
0x180028a46  movzx   r8d, byte ptr [r12+0Eh]
0x180028a4c  movzx   r9d, byte ptr [r12+0Dh]
0x180028a52  movzx   r10d, byte ptr [r12+0Ch]
0x180028a58  movzx   r11d, byte ptr [r12+0Bh]
0x180028a5e  movzx   ebx, byte ptr [r12+0Ah]
0x180028a64  movzx   edi, byte ptr [r12+9]
0x180028a6a  movzx   esi, byte ptr [r12+8]
0x180028a70  movzx   r14d, word ptr [r12+6]
0x180028a76  movzx   r15d, word ptr [r12+4]
0x180028a7c  mov     [rsp+88h], ecx
0x180028a83  mov     rcx, [rbp+37h+arg_18]
0x180028a87  mov     qword ptr [rsp+100h+var_80], rcx
0x180028a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a96  mov     dword ptr [rsp+100h+var_88], eax
0x180028a9a  mov     eax, [r12]
0x180028a9e  mov     [rsp+100h+var_90], r8d
0x180028aa3  mov     rcx, [rcx+10h]
0x180028aa7  mov     [rsp+100h+var_98], r9d
0x180028aac  mov     [rsp+100h+var_A0], r10d
0x180028ab1  mov     [rsp+100h+var_A8], r11d
0x180028ab6  mov     [rsp+100h+var_B0], ebx
0x180028aba  mov     [rsp+100h+var_B8], edi
0x180028abe  mov     [rsp+100h+var_C0], esi
0x180028ac2  mov     [rsp+100h+var_C8], r14d
0x180028ac7  mov     [rsp+100h+var_D0], r15d
0x180028acc  mov     [rsp+100h+var_D8], eax
0x180028ad0  lea     rax, aSccacheread; "ScCacheRead"
0x180028ad7  mov     qword ptr [rsp+100h+var_E0], rax
0x180028adc  call    WPP_SF_ssDDDDDDDDDDDSDS
0x180028ae1  mov     rbx, [rbp+37h+arg_18]
0x180028ae5  lea     r15, WPP_GLOBAL_Control
0x180028aec  mov     esi, [rbp+37h+arg_10]
0x180028aef  xor     r14d, r14d
0x180028af2  mov     [rbp+37h+var_50], 10h
0x180028af9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028afd  mov     [rbp+37h+var_48], r12
0x180028b01  inc     rax
0x180028b04  cmp     [rbx+rax*2], r14w
0x180028b09  jnz     short loc_180028B01
0x180028b0b  add     eax, eax
0x180028b0d  mov     [rbp+37h+var_38], rbx
0x180028b11  mov     rcx, r13; lpCriticalSection
0x180028b14  mov     [rbp+37h+var_40], eax
0x180028b17  call    cs:__imp_EnterCriticalSection
0x180028b1d  mov     rcx, [r13+28h]
0x180028b21  lea     r9, [rbp+37h+var_60]
0x180028b25  lea     rdx, [rbp+37h+var_50]
0x180028b29  call    CacheGetItem
0x180028b2e  mov     ebx, eax
0x180028b30  test    eax, eax
0x180028b32  jz      short loc_180028B49
0x180028b34  cmp     eax, 490h
0x180028b39  jnz     loc_180028C17
0x180028b3f  mov     ebx, 80100070h
0x180028b44  jmp     loc_180028C17
0x180028b49  mov     rdi, qword ptr [rbp+37h+var_60+8]
0x180028b4d  lea     rcx, [rbp+37h+Time]; Time
0x180028b51  call    cs:__imp_time
0x180028b57  mov     rdx, [rbp+37h+Time]
0x180028b5b  sub     rdx, [rdi+10h]
0x180028b5f  js      loc_180028C03
0x180028b65  cmp     [rdi+10h], r14
0x180028b69  jl      loc_180028C03
0x180028b6f  imul    ecx, [r13+60h], 15180h
0x180028b77  cmp     rdx, rcx
0x180028b7a  jg      loc_180028C03
0x180028b80  mov     rdx, rdi
0x180028b83  mov     rcx, r13
0x180028b86  cmp     esi, [rdi+0Ch]
0x180028b89  jnz     short loc_180028C09
0x180028b8b  call    I_ServerCacheSetMRU
0x180028b90  mov     rax, [r13+30h]
0x180028b94  mov     ecx, [rdi+8]
0x180028b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b9c  mov     rcx, [rbp+37h+arg_30]
0x180028ba0  mov     [rcx], rax
0x180028ba3  test    rax, rax
0x180028ba6  jnz     short loc_180028BE9
0x180028ba8  lea     edx, [rax+2]
0x180028bab  call    WppTraceIndent
0x180028bb0  mov     ebx, 8
0x180028bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bbc  cmp     rcx, r15
0x180028bbf  jz      short loc_180028C17
0x180028bc1  test    byte ptr [rcx+1Ch], 1
0x180028bc5  jz      short loc_180028C17
0x180028bc7  cmp     byte ptr [rcx+19h], 2
0x180028bcb  jb      short loc_180028C17
0x180028bcd  mov     r9, cs:WPP_pszIndent
0x180028bd4  lea     edx, [rbx+11h]
0x180028bd7  mov     rcx, [rcx+10h]
0x180028bdb  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028be2  call    WPP_SF_s
0x180028be7  jmp     short loc_180028C17
0x180028be9  mov     r8d, [rdi+8]; Size
0x180028bed  mov     rcx, rax; void *
0x180028bf0  mov     rdx, [rdi]; Src
0x180028bf3  call    memcpy_0
0x180028bf8  mov     rax, [rbp+37h+arg_38]
0x180028bfc  mov     ecx, [rdi+8]
0x180028bff  mov     [rax], ecx
0x180028c01  jmp     short loc_180028C17
0x180028c03  mov     rdx, rdi
0x180028c06  mov     rcx, r13
0x180028c09  lea     r8, [rbp+37h+var_50]
0x180028c0d  call    I_ServerCacheRemoveItem
0x180028c12  mov     ebx, 80100071h
0x180028c17  mov     rcx, r13; lpCriticalSection
0x180028c1a  call    cs:__imp_LeaveCriticalSection
0x180028c20  mov     edx, 1
0x180028c25  call    WppTraceIndent
0x180028c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c31  cmp     rcx, r15
0x180028c34  jz      short loc_180028C62
0x180028c36  test    byte ptr [rcx+1Ch], 2
0x180028c3a  jz      short loc_180028C62
0x180028c3c  cmp     byte ptr [rcx+19h], 5
0x180028c40  jb      short loc_180028C62
0x180028c42  mov     r9, cs:WPP_pszIndent
0x180028c49  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028c50  mov     rcx, [rcx+10h]
0x180028c54  mov     edx, 1Ah
0x180028c59  mov     [rsp+100h+var_E0], ebx
0x180028c5d  call    WPP_SF_sD
0x180028c62  mov     eax, ebx
0x180028c64  mov     rbx, [rsp+100h+arg_8]
0x180028c6c  add     rsp, 0D0h
0x180028c73  pop     r15
0x180028c75  pop     r14
0x180028c77  pop     r13
0x180028c79  pop     r12
0x180028c7b  pop     rdi
0x180028c7c  pop     rsi
0x180028c7d  pop     rbp
0x180028c7e  retn
```
