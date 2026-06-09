# AfdGetTransportInfo

- ea: `0x140037374`
- end: `0x14003761c`
- name: `AfdGetTransportInfo`
- size: `680`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140014ed0`
- `0x140037e80`
- `0x140043aa4`
- `0x140046094`
- `0x140066380`

## callees

- `0x140003670`
- `0x140037374`
- `0x14003f254`
- `0x14004f3e0`
- `0x1400672a4`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400373b9`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400373b9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400373ee`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400373ee`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037456`
- `ntoskrnl!ExReleaseResourceLite` at `0x140037456`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003746b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003746b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400374ce`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400374ce`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140037507`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375a1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375d8`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140037507`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375a1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400375d8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140037529`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140037529`

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
0x140037374  mov     [rsp+arg_10], rbx
0x140037379  mov     [rsp+arg_18], rbp
0x14003737e  push    rsi
0x14003737f  push    rdi
0x140037380  push    r12
0x140037382  sub     rsp, 50h
0x140037386  mov     rax, cs:__security_cookie
0x14003738d  xor     rax, rsp
0x140037390  mov     [rsp+68h+var_20], rax
0x140037395  xorps   xmm0, xmm0
0x140037398  mov     rdi, rcx
0x14003739b  mov     rcx, cs:AfdGlobalData; Resource
0x1400373a2  xor     eax, eax
0x1400373a4  movups  [rsp+68h+VirtualAddress], xmm0
0x1400373a9  mov     [rsp+68h+var_28], rax
0x1400373ae  mov     rsi, rdx
0x1400373b1  movups  [rsp+68h+var_38], xmm0
0x1400373b6  mov     bpl, 1
0x1400373b9  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x1400373c0  nop     dword ptr [rax+rax+00h]
0x1400373c5  mov     rbx, [rsi]
0x1400373c8  test    rbx, rbx
0x1400373cb  jnz     loc_14003758E
0x1400373d1  lea     r12, AfdTransportInfoListHead
0x1400373d8  mov     rbx, cs:AfdTransportInfoListHead
0x1400373df  cmp     rbx, r12
0x1400373e2  jz      short loc_14003743A
0x1400373e4  lea     rcx, [rbx+20h]; String1
0x1400373e8  mov     r8b, 1; CaseInSensitive
0x1400373eb  mov     rdx, rdi; String2
0x1400373ee  call    cs:__imp_RtlCompareUnicodeString
0x1400373f5  nop     dword ptr [rax+rax+00h]
0x1400373fa  test    eax, eax
0x1400373fc  jz      short loc_140037403
0x1400373fe  mov     rbx, [rbx]
0x140037401  jmp     short loc_1400373DF
0x140037403  prefetchw byte ptr [rbx+10h]
0x140037407  mov     rax, [rbx+10h]
0x14003740b  lea     rcx, [rax+1]
0x14003740f  cmp     rcx, 1
0x140037413  jbe     short loc_14003742F
0x140037415  lock cmpxchg [rbx+10h], rcx
0x14003741b  jnz     short loc_14003740B
0x14003741d  cmp     byte ptr [rbx+18h], 0
0x140037421  jz      loc_140037500
0x140037427  mov     [rsi], rbx
0x14003742a  jmp     loc_140037598
0x14003742f  jz      short loc_14003744A
0x140037431  mov     ecx, 0Eh
0x140037436  int     29h; Win8: RtlFailFast(ecx)
0x140037438  jmp     short loc_14003744A
0x14003743a  mov     rcx, rdi
0x14003743d  call    AfdIsValidTdiDeviceName
0x140037442  test    al, al
0x140037444  jz      loc_140037587
0x14003744a  test    bpl, bpl
0x14003744d  jz      short loc_14003747F
0x14003744f  mov     rcx, cs:AfdGlobalData; Resource
0x140037456  call    cs:__imp_ExReleaseResourceLite
0x14003745d  nop     dword ptr [rax+rax+00h]
0x140037462  mov     rcx, cs:AfdGlobalData; Resource
0x140037469  mov     dl, 1; Wait
0x14003746b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140037472  nop     dword ptr [rax+rax+00h]
0x140037477  xor     bpl, bpl
0x14003747a  jmp     loc_1400373D8
0x14003747f  movzx   edx, word ptr [rdi]
0x140037482  mov     ecx, 40h ; '@'
0x140037487  add     rdx, 62h ; 'b'
0x14003748b  mov     r8d, 54646641h
0x140037491  lea     r9d, [rcx-30h]
0x140037495  call    AfdAllocatePoolPriority
0x14003749a  mov     rbx, rax
0x14003749d  test    rax, rax
0x1400374a0  jnz     short loc_1400374AC
0x1400374a2  mov     ebx, 0C000009Ah
0x1400374a7  jmp     loc_14003759A
0x1400374ac  mov     qword ptr [rax+10h], 1
0x1400374b4  lea     rcx, [rbx+20h]; DestinationString
0x1400374b8  movzx   eax, word ptr [rdi]
0x1400374bb  mov     rdx, rdi; SourceString
0x1400374be  add     ax, 2
0x1400374c2  mov     [rbx+22h], ax
0x1400374c6  lea     rax, [rbx+60h]
0x1400374ca  mov     [rbx+28h], rax
0x1400374ce  call    cs:__imp_RtlCopyUnicodeString
0x1400374d5  nop     dword ptr [rax+rax+00h]
0x1400374da  mov     rax, cs:AfdTransportInfoListHead
0x1400374e1  cmp     [rax+8], r12
0x1400374e5  jz      short loc_1400374EE
0x1400374e7  mov     ecx, 3
0x1400374ec  int     29h; Win8: RtlFailFast(ecx)
0x1400374ee  mov     [rbx], rax
0x1400374f1  mov     [rbx+8], r12
0x1400374f5  mov     [rax+8], rbx
0x1400374f9  mov     cs:AfdTransportInfoListHead, rbx
0x140037500  mov     rcx, cs:AfdGlobalData; Resource
0x140037507  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003750e  nop     dword ptr [rax+rax+00h]
0x140037513  mov     rdx, rbx
0x140037516  lea     rcx, [rsp+68h+VirtualAddress]; VirtualAddress
0x14003751b  call    AfdQueryProviderInfo
0x140037520  mov     rcx, cs:AfdGlobalData; Resource
0x140037527  mov     edi, eax
0x140037529  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140037530  nop     dword ptr [rax+rax+00h]
0x140037535  test    edi, edi
0x140037537  js      short loc_1400375B1
0x140037539  cmp     byte ptr [rbx+18h], 0
0x14003753d  jnz     loc_1400375CC
0x140037543  cmp     byte ptr [rbx+19h], 0
0x140037547  movups  xmm0, [rsp+68h+VirtualAddress]
0x14003754c  movups  xmmword ptr [rbx+38h], xmm0
0x140037550  movups  xmm1, [rsp+68h+var_38]
0x140037555  movups  xmmword ptr [rbx+48h], xmm1
0x140037559  movsd   xmm0, [rsp+68h+var_28]
0x14003755f  movsd   qword ptr [rbx+58h], xmm0
0x140037564  jnz     short loc_140037581
0x140037566  mov     eax, 1
0x14003756b  lock xadd [rbx+10h], rax
0x140037571  inc     rax
0x140037574  cmp     rax, 1
0x140037578  jg      short loc_140037581
0x14003757a  mov     ecx, 0Eh
0x14003757f  int     29h; Win8: RtlFailFast(ecx)
0x140037581  mov     byte ptr [rbx+18h], 1
0x140037585  jmp     short loc_1400375CC
0x140037587  mov     ebx, 0C0000010h
0x14003758c  jmp     short loc_14003759A
0x14003758e  cmp     byte ptr [rbx+18h], 0
0x140037592  jz      loc_140037500
0x140037598  xor     ebx, ebx
0x14003759a  mov     rcx, cs:AfdGlobalData; Resource
0x1400375a1  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400375a8  nop     dword ptr [rax+rax+00h]
0x1400375ad  mov     eax, ebx
0x1400375af  jmp     short loc_1400375F9
0x1400375b1  lea     eax, [rdi+3FFFFFF2h]
0x1400375b7  cmp     eax, 2Ch ; ','
0x1400375ba  ja      short loc_1400375D1
0x1400375bc  mov     rcx, 104000000001h
0x1400375c6  bt      rcx, rax
0x1400375ca  jnb     short loc_1400375D1
0x1400375cc  mov     [rsi], rbx
0x1400375cf  xor     ebx, ebx
0x1400375d1  mov     rcx, cs:AfdGlobalData; Resource
0x1400375d8  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400375df  nop     dword ptr [rax+rax+00h]
0x1400375e4  test    rbx, rbx
0x1400375e7  jz      short loc_1400375F7
0x1400375e9  cmp     qword ptr [rsi], 0
0x1400375ed  jnz     short loc_1400375F7
0x1400375ef  mov     rcx, rbx
0x1400375f2  call    AfdDereferenceTransport
0x1400375f7  mov     eax, edi
0x1400375f9  mov     rcx, [rsp+68h+var_20]
0x1400375fe  xor     rcx, rsp; StackCookie
0x140037601  call    __security_check_cookie
0x140037606  lea     r11, [rsp+68h+var_18]
0x14003760b  mov     rbx, [r11+30h]
0x14003760f  mov     rbp, [r11+38h]
0x140037613  mov     rsp, r11
0x140037616  pop     r12
0x140037618  pop     rdi
0x140037619  pop     rsi
0x14003761a  retn
```
