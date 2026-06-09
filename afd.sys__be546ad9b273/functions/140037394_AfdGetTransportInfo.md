# AfdGetTransportInfo

- ea: `0x140037394`
- end: `0x14003763c`
- name: `AfdGetTransportInfo`
- size: `680`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, __int64 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140014ed0`
- `0x140037ea0`
- `0x140043ac4`
- `0x140046114`
- `0x140066520`

## callees

- `0x140003670`
- `0x140037394`
- `0x14003f274`
- `0x14004f480`
- `0x140067444`
- `0x140072840`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400373d9`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400373d9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003740e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003740e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037476`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037476`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003748b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003748b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400374ee`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400374ee`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140037527`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375c1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375f8`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140037527`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375c1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375f8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140037549`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140037549`

## pseudocode

```c
__int64 __fastcall AfdGetTransportInfo(PCUNICODE_STRING SourceString, __int64 *a2)
{
  char v4; // bp
  __int64 i; // rbx
  signed __int64 v6; // rax
  signed __int64 v7; // rtt
  __int64 PoolPriority; // rax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // edi
  bool v12; // zf
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  __int128 VirtualAddress; // [rsp+20h] [rbp-48h] BYREF
  __int128 v17; // [rsp+30h] [rbp-38h]
  __int64 v18; // [rsp+40h] [rbp-28h]

  VirtualAddress = 0;
  v18 = 0;
  v17 = 0;
  v4 = 1;
  ExEnterCriticalRegionAndAcquireResourceShared(AfdGlobalData);
  i = *a2;
  if ( !*a2 )
  {
    while ( 2 )
    {
      for ( i = AfdTransportInfoListHead; (__int64 *)i != &AfdTransportInfoListHead; i = *(_QWORD *)i )
      {
        if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(i + 32), SourceString, 1u) )
        {
          _m_prefetchw((const void *)(i + 16));
          v6 = *(_QWORD *)(i + 16);
          do
          {
            if ( (unsigned __int64)(v6 + 1) <= 1 )
            {
              if ( v6 )
                __fastfail(0xEu);
              goto LABEL_14;
            }
            v7 = v6;
            v6 = _InterlockedCompareExchange64((volatile signed __int64 *)(i + 16), v6 + 1, v6);
          }
          while ( v7 != v6 );
          if ( !*(_BYTE *)(i + 24) )
            goto LABEL_21;
          *a2 = i;
          goto LABEL_29;
        }
      }
      if ( !(unsigned __int8)AfdIsValidTdiDeviceName(SourceString) )
      {
        v9 = -1073741808;
        goto LABEL_30;
      }
LABEL_14:
      if ( v4 )
      {
        ExReleaseResourceLite(AfdGlobalData);
        ExAcquireResourceExclusiveLite(AfdGlobalData, 1u);
        v4 = 0;
        continue;
      }
      break;
    }
    PoolPriority = AfdAllocatePoolPriority(64, SourceString->Length + 98LL, 1415865921, 16);
    i = PoolPriority;
    if ( !PoolPriority )
    {
      v9 = -1073741670;
      goto LABEL_30;
    }
    *(_QWORD *)(PoolPriority + 16) = 1;
    *(_WORD *)(PoolPriority + 34) = SourceString->Length + 2;
    *(_QWORD *)(PoolPriority + 40) = PoolPriority + 96;
    RtlCopyUnicodeString((PUNICODE_STRING)(PoolPriority + 32), SourceString);
    v10 = AfdTransportInfoListHead;
    if ( *(__int64 **)(AfdTransportInfoListHead + 8) != &AfdTransportInfoListHead )
      __fastfail(3u);
    *(_QWORD *)i = AfdTransportInfoListHead;
    *(_QWORD *)(i + 8) = &AfdTransportInfoListHead;
    *(_QWORD *)(v10 + 8) = i;
    AfdTransportInfoListHead = i;
LABEL_21:
    ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
    v11 = AfdQueryProviderInfo(&VirtualAddress);
    ExEnterCriticalRegionAndAcquireResourceExclusive(AfdGlobalData);
    if ( v11 < 0 )
    {
      v14 = (unsigned int)(v11 + 1073741810);
      if ( (unsigned int)v14 > 0x2C )
        goto LABEL_34;
      v15 = 0x104000000001LL;
      if ( !_bittest64(&v15, v14) )
        goto LABEL_34;
    }
    else if ( !*(_BYTE *)(i + 24) )
    {
      v12 = *(_BYTE *)(i + 25) == 0;
      *(_OWORD *)(i + 56) = VirtualAddress;
      *(_OWORD *)(i + 72) = v17;
      *(_QWORD *)(i + 88) = v18;
      if ( v12 && _InterlockedIncrement64((volatile signed __int64 *)(i + 16)) <= 1 )
        __fastfail(0xEu);
      *(_BYTE *)(i + 24) = 1;
    }
    *a2 = i;
    i = 0;
LABEL_34:
    ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
    if ( i )
    {
      if ( !*a2 )
        AfdDereferenceTransport(i);
    }
    return (unsigned int)v11;
  }
  if ( !*(_BYTE *)(i + 24) )
    goto LABEL_21;
LABEL_29:
  v9 = 0;
LABEL_30:
  ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
  return v9;
}

```

## disassembly

```asm
0x140037394  mov     [rsp+arg_10], rbx
0x140037399  mov     [rsp+arg_18], rbp
0x14003739e  push    rsi
0x14003739f  push    rdi
0x1400373a0  push    r12
0x1400373a2  sub     rsp, 50h
0x1400373a6  mov     rax, cs:__security_cookie
0x1400373ad  xor     rax, rsp
0x1400373b0  mov     [rsp+68h+var_20], rax
0x1400373b5  xorps   xmm0, xmm0
0x1400373b8  mov     rdi, rcx
0x1400373bb  mov     rcx, cs:AfdGlobalData; Resource
0x1400373c2  xor     eax, eax
0x1400373c4  movups  [rsp+68h+VirtualAddress], xmm0
0x1400373c9  mov     [rsp+68h+var_28], rax
0x1400373ce  mov     rsi, rdx
0x1400373d1  movups  [rsp+68h+var_38], xmm0
0x1400373d6  mov     bpl, 1
0x1400373d9  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x1400373e0  nop     dword ptr [rax+rax+00h]
0x1400373e5  mov     rbx, [rsi]
0x1400373e8  test    rbx, rbx
0x1400373eb  jnz     loc_1400375AE
0x1400373f1  lea     r12, AfdTransportInfoListHead
0x1400373f8  mov     rbx, cs:AfdTransportInfoListHead
0x1400373ff  cmp     rbx, r12
0x140037402  jz      short loc_14003745A
0x140037404  lea     rcx, [rbx+20h]; String1
0x140037408  mov     r8b, 1; CaseInSensitive
0x14003740b  mov     rdx, rdi; String2
0x14003740e  call    cs:__imp_RtlCompareUnicodeString
0x140037415  nop     dword ptr [rax+rax+00h]
0x14003741a  test    eax, eax
0x14003741c  jz      short loc_140037423
0x14003741e  mov     rbx, [rbx]
0x140037421  jmp     short loc_1400373FF
0x140037423  prefetchw byte ptr [rbx+10h]
0x140037427  mov     rax, [rbx+10h]
0x14003742b  lea     rcx, [rax+1]
0x14003742f  cmp     rcx, 1
0x140037433  jbe     short loc_14003744F
0x140037435  lock cmpxchg [rbx+10h], rcx
0x14003743b  jnz     short loc_14003742B
0x14003743d  cmp     byte ptr [rbx+18h], 0
0x140037441  jz      loc_140037520
0x140037447  mov     [rsi], rbx
0x14003744a  jmp     loc_1400375B8
0x14003744f  jz      short loc_14003746A
0x140037451  mov     ecx, 0Eh
0x140037456  int     29h; Win8: RtlFailFast(ecx)
0x140037458  jmp     short loc_14003746A
0x14003745a  mov     rcx, rdi
0x14003745d  call    AfdIsValidTdiDeviceName
0x140037462  test    al, al
0x140037464  jz      loc_1400375A7
0x14003746a  test    bpl, bpl
0x14003746d  jz      short loc_14003749F
0x14003746f  mov     rcx, cs:AfdGlobalData; Resource
0x140037476  call    cs:__imp_ExReleaseResourceLite
0x14003747d  nop     dword ptr [rax+rax+00h]
0x140037482  mov     rcx, cs:AfdGlobalData; Resource
0x140037489  mov     dl, 1; Wait
0x14003748b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140037492  nop     dword ptr [rax+rax+00h]
0x140037497  xor     bpl, bpl
0x14003749a  jmp     loc_1400373F8
0x14003749f  movzx   edx, word ptr [rdi]
0x1400374a2  mov     ecx, 40h ; '@'
0x1400374a7  add     rdx, 62h ; 'b'
0x1400374ab  mov     r8d, 54646641h
0x1400374b1  lea     r9d, [rcx-30h]
0x1400374b5  call    AfdAllocatePoolPriority
0x1400374ba  mov     rbx, rax
0x1400374bd  test    rax, rax
0x1400374c0  jnz     short loc_1400374CC
0x1400374c2  mov     ebx, 0C000009Ah
0x1400374c7  jmp     loc_1400375BA
0x1400374cc  mov     qword ptr [rax+10h], 1
0x1400374d4  lea     rcx, [rbx+20h]; DestinationString
0x1400374d8  movzx   eax, word ptr [rdi]
0x1400374db  mov     rdx, rdi; SourceString
0x1400374de  add     ax, 2
0x1400374e2  mov     [rbx+22h], ax
0x1400374e6  lea     rax, [rbx+60h]
0x1400374ea  mov     [rbx+28h], rax
0x1400374ee  call    cs:__imp_RtlCopyUnicodeString
0x1400374f5  nop     dword ptr [rax+rax+00h]
0x1400374fa  mov     rax, cs:AfdTransportInfoListHead
0x140037501  cmp     [rax+8], r12
0x140037505  jz      short loc_14003750E
0x140037507  mov     ecx, 3
0x14003750c  int     29h; Win8: RtlFailFast(ecx)
0x14003750e  mov     [rbx], rax
0x140037511  mov     [rbx+8], r12
0x140037515  mov     [rax+8], rbx
0x140037519  mov     cs:AfdTransportInfoListHead, rbx
0x140037520  mov     rcx, cs:AfdGlobalData; Resource
0x140037527  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003752e  nop     dword ptr [rax+rax+00h]
0x140037533  mov     rdx, rbx
0x140037536  lea     rcx, [rsp+68h+VirtualAddress]; VirtualAddress
0x14003753b  call    AfdQueryProviderInfo
0x140037540  mov     rcx, cs:AfdGlobalData; Resource
0x140037547  mov     edi, eax
0x140037549  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140037550  nop     dword ptr [rax+rax+00h]
0x140037555  test    edi, edi
0x140037557  js      short loc_1400375D1
0x140037559  cmp     byte ptr [rbx+18h], 0
0x14003755d  jnz     loc_1400375EC
0x140037563  cmp     byte ptr [rbx+19h], 0
0x140037567  movups  xmm0, [rsp+68h+VirtualAddress]
0x14003756c  movups  xmmword ptr [rbx+38h], xmm0
0x140037570  movups  xmm1, [rsp+68h+var_38]
0x140037575  movups  xmmword ptr [rbx+48h], xmm1
0x140037579  movsd   xmm0, [rsp+68h+var_28]
0x14003757f  movsd   qword ptr [rbx+58h], xmm0
0x140037584  jnz     short loc_1400375A1
0x140037586  mov     eax, 1
0x14003758b  lock xadd [rbx+10h], rax
0x140037591  inc     rax
0x140037594  cmp     rax, 1
0x140037598  jg      short loc_1400375A1
0x14003759a  mov     ecx, 0Eh
0x14003759f  int     29h; Win8: RtlFailFast(ecx)
0x1400375a1  mov     byte ptr [rbx+18h], 1
0x1400375a5  jmp     short loc_1400375EC
0x1400375a7  mov     ebx, 0C0000010h
0x1400375ac  jmp     short loc_1400375BA
0x1400375ae  cmp     byte ptr [rbx+18h], 0
0x1400375b2  jz      loc_140037520
0x1400375b8  xor     ebx, ebx
0x1400375ba  mov     rcx, cs:AfdGlobalData; Resource
0x1400375c1  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400375c8  nop     dword ptr [rax+rax+00h]
0x1400375cd  mov     eax, ebx
0x1400375cf  jmp     short loc_140037619
0x1400375d1  lea     eax, [rdi+3FFFFFF2h]
0x1400375d7  cmp     eax, 2Ch ; ','
0x1400375da  ja      short loc_1400375F1
0x1400375dc  mov     rcx, 104000000001h
0x1400375e6  bt      rcx, rax
0x1400375ea  jnb     short loc_1400375F1
0x1400375ec  mov     [rsi], rbx
0x1400375ef  xor     ebx, ebx
0x1400375f1  mov     rcx, cs:AfdGlobalData; Resource
0x1400375f8  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400375ff  nop     dword ptr [rax+rax+00h]
0x140037604  test    rbx, rbx
0x140037607  jz      short loc_140037617
0x140037609  cmp     qword ptr [rsi], 0
0x14003760d  jnz     short loc_140037617
0x14003760f  mov     rcx, rbx
0x140037612  call    AfdDereferenceTransport
0x140037617  mov     eax, edi
0x140037619  mov     rcx, [rsp+68h+var_20]
0x14003761e  xor     rcx, rsp; StackCookie
0x140037621  call    __security_check_cookie
0x140037626  lea     r11, [rsp+68h+var_18]
0x14003762b  mov     rbx, [r11+30h]
0x14003762f  mov     rbp, [r11+38h]
0x140037633  mov     rsp, r11
0x140037636  pop     r12
0x140037638  pop     rdi
0x140037639  pop     rsi
0x14003763a  retn
```
