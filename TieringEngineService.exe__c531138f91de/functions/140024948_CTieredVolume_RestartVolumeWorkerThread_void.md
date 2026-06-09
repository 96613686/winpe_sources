# CTieredVolume::RestartVolumeWorkerThread(void)

- ea: `0x140024948`
- end: `0x140024b59`
- name: `?RestartVolumeWorkerThread@CTieredVolume@@AEAAXXZ`
- size: `529`
- prototype: `void __fastcall(CTieredVolume *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d2d4`
- `0x14000d5f0`
- `0x1400237c8`

## callees

- `0x140017930`
- `0x140017e78`
- `0x140024948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400249a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400249bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400249a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400249bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140024b4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140024b4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024978`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140024978`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140024ac5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140024ac5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14002496b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14002496b`

## pseudocode

```c
void __fastcall CTieredVolume::RestartVolumeWorkerThread(CTieredVolume *this)
{
  int v2; // eax
  int v3; // ecx
  struct _FILETIME v4; // rcx
  __int64 v5; // r9
  _QWORD *v6; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  pftDueTime = 0;
  WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 114), 1);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  if ( !*(_WORD *)((char *)this + 165)
    && WaitForSingleObject(*((HANDLE *)this + 96), 0) == 258
    && WaitForSingleObject(*((HANDLE *)this + 95), 0) == 258 )
  {
    v2 = *((_DWORD *)this + 46);
    v3 = 7;
    if ( v2 != 7 )
    {
      v3 = 3;
      if ( v2 != 3 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
            (char *)this + 672);
        }
        *((_DWORD *)this + 46) = 1;
        v3 = 1;
      }
    }
    if ( *((_BYTE *)this + 728) || ((v3 - 1) & 0xFFFFFFF9) == 0 )
      v4 = 0;
    else
      v4 = (struct _FILETIME)-36000000000LL;
    pftDueTime = v4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v5 = ((unsigned __int128)(*(__int64 *)&v4 * (__int128)0x29406B2A1A85BD43LL) >> 64) - *(_QWORD *)&v4;
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)&WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids,
        ((unsigned __int64)v5 >> 63) + (v5 >> 23),
        (__int64)this + 672);
    }
    SetThreadpoolTimer(*((PTP_TIMER *)this + 114), &pftDueTime, 0, 0x186A0u);
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          252,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (char *)this + 672);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
        WPP_SF_Z(v6[2], 73, &WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids, (char *)this + 672);
    }
    *((_DWORD *)this + 46) = 1;
  }
  if ( this != (CTieredVolume *)-24LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 3);
}

```

## disassembly

```asm
0x140024948  push    rbx
0x14002494a  push    rbp
0x14002494b  push    rsi
0x14002494c  push    rdi
0x14002494d  sub     rsp, 38h
0x140024951  mov     rbx, rcx
0x140024954  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0
0x14002495d  mov     rcx, [rcx+390h]; pti
0x140024964  mov     ebp, 1
0x140024969  mov     edx, ebp; fCancelPendingCallbacks
0x14002496b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140024971  lea     rsi, [rbx+18h]
0x140024975  mov     rcx, rsi; SRWLock
0x140024978  call    cs:__imp_AcquireSRWLockExclusive
0x14002497e  cmp     byte ptr [rbx+0A5h], 0
0x140024985  jnz     loc_140024ACD
0x14002498b  cmp     byte ptr [rbx+0A6h], 0
0x140024992  jnz     loc_140024ACD
0x140024998  mov     rcx, [rbx+300h]; hHandle
0x14002499f  xor     edx, edx; dwMilliseconds
0x1400249a1  call    cs:__imp_WaitForSingleObject
0x1400249a7  mov     edi, 102h
0x1400249ac  cmp     eax, edi
0x1400249ae  jnz     loc_140024ACD
0x1400249b4  mov     rcx, [rbx+2F8h]; hHandle
0x1400249bb  xor     edx, edx; dwMilliseconds
0x1400249bd  call    cs:__imp_WaitForSingleObject
0x1400249c3  cmp     eax, edi
0x1400249c5  jnz     loc_140024ACD
0x1400249cb  mov     eax, [rbx+0B8h]
0x1400249d1  lea     ecx, [rbp+6]
0x1400249d4  lea     rdi, WPP_GLOBAL_Control
0x1400249db  cmp     eax, ecx
0x1400249dd  jz      short loc_140024A20
0x1400249df  lea     ecx, [rbp+2]
0x1400249e2  cmp     eax, ecx
0x1400249e4  jz      short loc_140024A20
0x1400249e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249ed  cmp     rcx, rdi
0x1400249f0  jz      short loc_140024A18
0x1400249f2  test    [rcx+1Ch], bpl
0x1400249f6  jz      short loc_140024A18
0x1400249f8  cmp     byte ptr [rcx+19h], 4
0x1400249fc  jb      short loc_140024A18
0x1400249fe  mov     rcx, [rcx+10h]
0x140024a02  lea     r9, [rbx+2A0h]
0x140024a09  lea     edx, [rbp+46h]
0x140024a0c  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024a13  call    WPP_SF_Z
0x140024a18  mov     [rbx+0B8h], ebp
0x140024a1e  mov     ecx, ebp
0x140024a20  cmp     byte ptr [rbx+2D8h], 0
0x140024a27  jnz     short loc_140024A44
0x140024a29  lea     eax, [rcx-1]
0x140024a2c  test    eax, 0FFFFFFF9h
0x140024a31  jnz     short loc_140024A38
0x140024a33  cmp     ecx, 5
0x140024a36  jnz     short loc_140024A44
0x140024a38  mov     rcx, 0FFFFFFF79E3B9800h
0x140024a42  jmp     short loc_140024A46
0x140024a44  xor     ecx, ecx
0x140024a46  mov     rax, rcx
0x140024a49  mov     [rsp+58h+pftDueTime.dwLowDateTime], ecx
0x140024a4d  shr     rax, 20h
0x140024a51  mov     [rsp+58h+pftDueTime.dwHighDateTime], eax
0x140024a55  mov     r11, cs:WPP_GLOBAL_Control
0x140024a5c  cmp     r11, rdi
0x140024a5f  jz      short loc_140024AB0
0x140024a61  test    [r11+1Ch], bpl
0x140024a65  jz      short loc_140024AB0
0x140024a67  cmp     byte ptr [r11+19h], 4
0x140024a6c  jb      short loc_140024AB0
0x140024a6e  lea     r10, [rbx+2A0h]
0x140024a75  mov     rax, 29406B2A1A85BD43h
0x140024a7f  imul    rcx
0x140024a82  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024a89  mov     [rsp+58h+var_38], r10
0x140024a8e  mov     r9, rdx
0x140024a91  mov     edx, 48h ; 'H'
0x140024a96  sub     r9, rcx
0x140024a99  mov     rcx, [r11+10h]
0x140024a9d  sar     r9, 17h
0x140024aa1  mov     rax, r9
0x140024aa4  shr     rax, 3Fh
0x140024aa8  add     r9, rax
0x140024aab  call    WPP_SF_dZ
0x140024ab0  mov     rcx, [rbx+390h]; pti
0x140024ab7  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x140024abc  mov     r9d, 186A0h; msWindowLength
0x140024ac2  xor     r8d, r8d; msPeriod
0x140024ac5  call    cs:__imp_SetThreadpoolTimer
0x140024acb  jmp     short loc_140024B42
0x140024acd  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ad4  lea     rdi, WPP_GLOBAL_Control
0x140024adb  cmp     rcx, rdi
0x140024ade  jz      short loc_140024B3C
0x140024ae0  test    [rcx+1Ch], bpl
0x140024ae4  jz      short loc_140024B0F
0x140024ae6  cmp     byte ptr [rcx+19h], 5
0x140024aea  jb      short loc_140024B0F
0x140024aec  mov     rcx, [rcx+10h]
0x140024af0  lea     r9, [rbx+2A0h]
0x140024af7  mov     edx, 0FCh
0x140024afc  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140024b03  call    WPP_SF_Z
0x140024b08  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b0f  cmp     rcx, rdi
0x140024b12  jz      short loc_140024B3C
0x140024b14  test    [rcx+1Ch], bpl
0x140024b18  jz      short loc_140024B3C
0x140024b1a  cmp     byte ptr [rcx+19h], 4
0x140024b1e  jb      short loc_140024B3C
0x140024b20  mov     rcx, [rcx+10h]
0x140024b24  lea     r9, [rbx+2A0h]
0x140024b2b  mov     edx, 49h ; 'I'
0x140024b30  lea     r8, WPP_0ed2022e4a7938e5631e35e1dba0c2c3_Traceguids
0x140024b37  call    WPP_SF_Z
0x140024b3c  mov     [rbx+0B8h], ebp
0x140024b42  test    rsi, rsi
0x140024b45  jz      short loc_140024B50
0x140024b47  mov     rcx, rsi; SRWLock
0x140024b4a  call    cs:__imp_ReleaseSRWLockExclusive
0x140024b50  add     rsp, 38h
0x140024b54  pop     rdi
0x140024b55  pop     rsi
0x140024b56  pop     rbp
0x140024b57  pop     rbx
0x140024b58  retn
```
