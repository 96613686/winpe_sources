# Control_ProcessTransferEventWithED0

- ea: `0x14000ba7c`
- end: `0x14000bdf8`
- name: `Control_ProcessTransferEventWithED0`
- size: `892`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400029b0`
- `0x14000af00`

## callees

- `0x14000a7b0`
- `0x14000aa20`
- `0x14000ac60`
- `0x14000ba7c`
- `0x14000be00`
- `0x14000c264`
- `0x14000c7c0`
- `0x14002792c`
- `0x1400283c8`
- `0x14003be88`
- `0x140059a80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bc4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bdd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb2d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bb9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bc4a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bdd3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bae1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bae1`

## string_xrefs

- `0x14000bc73`: `Received duplicate Transfer Event TRB with Halted Completion Code`

## pseudocode

```c
char __fastcall Control_ProcessTransferEventWithED0(__int64 a1, __int64 a2)
{
  unsigned __int8 *v4; // r12
  _QWORD *v5; // rsi
  _QWORD *v6; // r13
  char v7; // bp
  KIRQL v8; // al
  __int64 v9; // rbx
  size_t v11; // r8
  unsigned int v12; // edx
  __int64 v13; // r10
  KIRQL v14; // dl
  const char *v15; // rax
  signed __int32 v16; // eax
  signed __int32 v17; // ett
  int v18; // edx
  __int64 v19; // rax
  char v20; // dl
  KIRQL v21; // dl
  size_t Size; // [rsp+A0h] [rbp+8h] BYREF
  int v23; // [rsp+A8h] [rbp+10h] BYREF

  v23 = 0;
  LODWORD(Size) = 0;
  v4 = (unsigned __int8 *)(a1 + 11);
  v5 = (_QWORD *)(a2 + 56);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_DDqLDDi(*(_QWORD *)(*v5 + 80LL), *(unsigned __int8 *)(a1 + 15), *v4, 18);
  v6 = v5;
  if ( (unsigned __int8)Endpoint_StoppedCompletionCode(*v4) )
  {
    if ( (*(_DWORD *)(*v5 + 32LL) & 0x40) != 0 )
      return 1;
    v6 = (_QWORD *)(a2 + 56);
  }
  v7 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
  v9 = *(_QWORD *)(a2 + 360);
  *(_BYTE *)(a2 + 104) = v8;
  if ( !v9 )
  {
    v14 = v8;
    goto LABEL_15;
  }
  if ( (unsigned __int8)Control_ProcessTransferEventPointer(a2, v9, a1, (unsigned int)&v23, (__int64)&Size) )
  {
    v11 = (unsigned int)Size;
    if ( (unsigned int)Size > *(_DWORD *)(v9 + 104) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v18 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 48) + 143LL);
        LOBYTE(v18) = 3;
        WPP_RECORDER_SF_DDDD(
          *(_QWORD *)(*v6 + 80LL),
          v18,
          14,
          19,
          (__int64)WPP_033405c12d5f32917339b215e0870938_Traceguids,
          *(_BYTE *)(*(_QWORD *)(a2 + 48) + 143LL),
          *(_DWORD *)(*v6 + 152LL),
          Size,
          *(_DWORD *)(v9 + 104));
      }
      v11 = 0;
    }
    if ( (_DWORD)v11 )
    {
      v19 = *(_QWORD *)(v9 + 48);
      *(_DWORD *)(v9 + 108) = v11;
      if ( (*(_DWORD *)(v19 + 32) & 1) != 0 && *(_DWORD *)(v9 + 64) == 2 )
        memmove(*(void **)(v9 + 80), *(const void **)(*(_QWORD *)(v9 + 88) + 16LL), v11);
    }
    if ( (unsigned __int8)Endpoint_HaltedCompletionCode(*v5, *v4) )
    {
      *(_DWORD *)(v9 + 124) = v12;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
      v13 = *v5;
      _m_prefetchw((const void *)(*v5 + 32LL));
      if ( (_InterlockedOr((volatile signed __int32 *)(v13 + 32), 0x20u) & 0x20) == 0 )
      {
        ESM_AddEvent((PVOID)(v13 + 312));
        return 1;
      }
      v15 = "Received duplicate Transfer Event TRB with Halted Completion Code";
LABEL_19:
      Controller_HwVerifierBreakIfEnabled(
        *(_QWORD *)v13,
        *(_QWORD *)(v13 + 8),
        *(_QWORD *)(v13 + 24),
        0x2000000,
        (__int64)v15,
        0,
        0);
      return 1;
    }
    if ( (unsigned __int8)Endpoint_StoppedCompletionCode(v12) )
    {
      if ( *(_DWORD *)(v9 + 108) == *(_DWORD *)(v9 + 104) )
      {
        *(_DWORD *)(v9 + 124) = 1;
      }
      else if ( v20 == 28 )
      {
        *(_DWORD *)(v9 + 124) = 28;
      }
      ++*(_DWORD *)(v9 + 132);
      v21 = *(_BYTE *)(a2 + 104);
      *(_DWORD *)(a2 + 372) = v23 - *(_DWORD *)(v9 + 132) + 1;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), v21);
      v13 = *v5;
      _m_prefetchw((const void *)(*v5 + 32LL));
      v16 = *(_DWORD *)(v13 + 32);
      do
      {
        v17 = v16;
        v16 = _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 32), v16 | 0x10, v16);
      }
      while ( v17 != v16 );
      if ( (v16 & 0x10) == 0 )
      {
        _m_prefetchw((const void *)(v13 + 32));
        if ( (_InterlockedXor((volatile signed __int32 *)(v13 + 32), 8u) & 8) != 0 )
          ESM_AddEsmEvent(v13, 118);
        return 1;
      }
      v15 = "Received duplicate Stopped Transfer Events";
      goto LABEL_19;
    }
    v14 = *(_BYTE *)(a2 + 104);
LABEL_15:
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), v14);
    return v7;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *(_BYTE *)(a2 + 104));
  Control_ValidateED0TrbPointerOnMismatch(a2, a1);
  return v7;
}

```

## disassembly

```asm
0x14000ba7c  mov     rax, rsp
0x14000ba7f  mov     [rax+18h], rbx
0x14000ba83  push    rbp
0x14000ba84  push    rsi
0x14000ba85  push    rdi
0x14000ba86  push    r12
0x14000ba88  push    r13
0x14000ba8a  push    r14
0x14000ba8c  push    r15
0x14000ba8e  sub     rsp, 60h
0x14000ba92  mov     rdi, rdx
0x14000ba95  mov     dword ptr [rax+10h], 0
0x14000ba9c  mov     r15, rcx
0x14000ba9f  mov     dword ptr [rax+8], 0
0x14000baa6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000baad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000bab4  lea     r12, [rcx+0Bh]
0x14000bab8  lea     rsi, [rdx+38h]
0x14000babc  jnz     loc_14000BBE2
0x14000bac2  movzx   ecx, byte ptr [r12]
0x14000bac7  mov     r13, rsi
0x14000baca  call    Endpoint_StoppedCompletionCode
0x14000bacf  test    al, al
0x14000bad1  jnz     loc_14000BC5B
0x14000bad7  lea     r14, [rdi+60h]
0x14000badb  xor     bpl, bpl
0x14000bade  mov     rcx, r14; SpinLock
0x14000bae1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bae8  nop     dword ptr [rax+rax+00h]
0x14000baed  mov     rbx, [rdi+168h]
0x14000baf4  mov     [rdi+68h], al
0x14000baf7  test    rbx, rbx
0x14000bafa  jz      loc_14000BC45
0x14000bb00  lea     rax, [rsp+98h+Size]
0x14000bb08  mov     r8, r15
0x14000bb0b  lea     r9, [rsp+98h+arg_8]
0x14000bb13  mov     [rsp+98h+var_78], rax
0x14000bb18  mov     rdx, rbx
0x14000bb1b  mov     rcx, rdi
0x14000bb1e  call    Control_ProcessTransferEventPointer
0x14000bb23  test    al, al
0x14000bb25  jnz     short loc_14000BB60
0x14000bb27  mov     dl, [rdi+68h]; NewIrql
0x14000bb2a  mov     rcx, r14; SpinLock
0x14000bb2d  call    cs:__imp_KeReleaseSpinLock
0x14000bb34  nop     dword ptr [rax+rax+00h]
0x14000bb39  mov     rdx, r15
0x14000bb3c  mov     rcx, rdi
0x14000bb3f  call    Control_ValidateED0TrbPointerOnMismatch
0x14000bb44  mov     rbx, [rsp+98h+arg_10]
0x14000bb4c  mov     al, bpl
0x14000bb4f  add     rsp, 60h
0x14000bb53  pop     r15
0x14000bb55  pop     r14
0x14000bb57  pop     r13
0x14000bb59  pop     r12
0x14000bb5b  pop     rdi
0x14000bb5c  pop     rsi
0x14000bb5d  pop     rbp
0x14000bb5e  retn
0x14000bb60  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x14000bb68  mov     r10d, [rbx+68h]
0x14000bb6c  cmp     r8d, r10d
0x14000bb6f  ja      loc_14000BCF6
0x14000bb75  test    r8d, r8d
0x14000bb78  jnz     loc_14000BD56
0x14000bb7e  movzx   edx, byte ptr [r12]
0x14000bb83  mov     rcx, [rsi]
0x14000bb86  call    Endpoint_HaltedCompletionCode
0x14000bb8b  test    al, al
0x14000bb8d  jz      loc_14000BD8A
0x14000bb93  mov     [rbx+7Ch], edx
0x14000bb96  mov     rcx, r14; SpinLock
0x14000bb99  mov     dl, [rdi+68h]; NewIrql
0x14000bb9c  call    cs:__imp_KeReleaseSpinLock
0x14000bba3  nop     dword ptr [rax+rax+00h]
0x14000bba8  mov     r10, [rsi]
0x14000bbab  prefetchw byte ptr [r10+20h]
0x14000bbb0  mov     eax, [r10+20h]
0x14000bbb4  mov     ecx, eax
0x14000bbb6  or      ecx, 20h
0x14000bbb9  lock cmpxchg [r10+20h], ecx
0x14000bbbf  jnz     short loc_14000BBB4
0x14000bbc1  test    al, 20h
0x14000bbc3  jnz     loc_14000BC73
0x14000bbc9  lea     rcx, [r10+138h]; Context
0x14000bbd0  mov     edx, 9Ah
0x14000bbd5  call    ESM_AddEvent
0x14000bbda  mov     bpl, 1
0x14000bbdd  jmp     loc_14000BB44
0x14000bbe2  mov     ebx, [rcx+0Ch]
0x14000bbe5  mov     r9d, 12h
0x14000bbeb  mov     r10d, [rcx+8]
0x14000bbef  mov     r11d, ebx
0x14000bbf2  movzx   edx, byte ptr [rcx+0Fh]
0x14000bbf6  and     r10d, 0FFFFFFh
0x14000bbfd  mov     rax, [r15]
0x14000bc00  mov     rcx, [rsi]
0x14000bc03  movzx   r8d, byte ptr [r12]
0x14000bc08  mov     [rsp+98h+var_40], rax
0x14000bc0d  shr     r11d, 2
0x14000bc11  mov     rcx, [rcx+50h]
0x14000bc15  and     r11d, 1
0x14000bc19  mov     [rsp+98h+var_48], r11d
0x14000bc1e  mov     [rsp+98h+var_50], r10d
0x14000bc23  mov     [rsp+98h+var_58], r8d
0x14000bc28  shr     ebx, 10h
0x14000bc2b  and     ebx, 1Fh
0x14000bc2e  mov     [rsp+98h+var_60], r15
0x14000bc33  mov     dword ptr [rsp+98h+var_68], ebx
0x14000bc37  mov     dword ptr [rsp+98h+var_70], edx
0x14000bc3b  call    WPP_RECORDER_SF_DDqLDDi
0x14000bc40  jmp     loc_14000BAC2
0x14000bc45  mov     dl, al; NewIrql
0x14000bc47  mov     rcx, r14; SpinLock
0x14000bc4a  call    cs:__imp_KeReleaseSpinLock
0x14000bc51  nop     dword ptr [rax+rax+00h]
0x14000bc56  jmp     loc_14000BB44
0x14000bc5b  mov     rax, [rsi]
0x14000bc5e  mov     ecx, [rax+20h]
0x14000bc61  test    cl, 40h
0x14000bc64  jnz     loc_14000BBDA
0x14000bc6a  lea     r13, [rdi+38h]
0x14000bc6e  jmp     loc_14000BAD7
0x14000bc73  lea     rax, aReceivedDuplic; "Received duplicate Transfer Event TRB w"...
0x14000bc7a  mov     r8, [r10+18h]
0x14000bc7e  mov     r9d, 2000000h
0x14000bc84  mov     rdx, [r10+8]
0x14000bc88  mov     rcx, [r10]
0x14000bc8b  mov     [rsp+98h+var_68], 0
0x14000bc94  mov     [rsp+98h+var_70], 0
0x14000bc9d  mov     [rsp+98h+var_78], rax
0x14000bca2  call    Controller_HwVerifierBreakIfEnabled
0x14000bca7  jmp     loc_14000BBDA
0x14000bcac  mov     ecx, eax
0x14000bcae  or      ecx, 10h
0x14000bcb1  lock cmpxchg [r10+20h], ecx
0x14000bcb7  jnz     short loc_14000BCAC
0x14000bcb9  test    al, 10h
0x14000bcbb  jnz     short loc_14000BCED
0x14000bcbd  prefetchw byte ptr [r10+20h]
0x14000bcc2  mov     eax, [r10+20h]
0x14000bcc6  mov     ecx, eax
0x14000bcc8  xor     ecx, 8
0x14000bccb  lock cmpxchg [r10+20h], ecx
0x14000bcd1  jnz     short loc_14000BCC6
0x14000bcd3  test    al, 8
0x14000bcd5  jz      loc_14000BBDA
0x14000bcdb  mov     edx, 76h ; 'v'
0x14000bce0  mov     rcx, r10
0x14000bce3  call    ESM_AddEsmEvent
0x14000bce8  jmp     loc_14000BBDA
0x14000bced  lea     rax, aReceivedDuplic_0; "Received duplicate Stopped Transfer Eve"...
0x14000bcf4  jmp     short loc_14000BC7A
0x14000bcf6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000bcfd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000bd04  jz      short loc_14000BD4E
0x14000bd06  mov     rax, [rdi+30h]
0x14000bd0a  mov     r9d, 13h
0x14000bd10  mov     rcx, [r13+0]
0x14000bd14  mov     [rsp+98h+var_58], r10d
0x14000bd19  mov     dword ptr [rsp+98h+var_60], r8d
0x14000bd1e  movzx   edx, byte ptr [rax+8Fh]
0x14000bd25  lea     r8d, [r9-5]
0x14000bd29  mov     eax, [rcx+98h]
0x14000bd2f  mov     rcx, [rcx+50h]
0x14000bd33  mov     dword ptr [rsp+98h+var_68], eax
0x14000bd37  lea     rax, WPP_033405c12d5f32917339b215e0870938_Traceguids
0x14000bd3e  mov     dword ptr [rsp+98h+var_70], edx
0x14000bd42  mov     dl, 3
0x14000bd44  mov     [rsp+98h+var_78], rax
0x14000bd49  call    WPP_RECORDER_SF_DDDD
0x14000bd4e  xor     r8d, r8d
0x14000bd51  jmp     loc_14000BB75
0x14000bd56  mov     rax, [rbx+30h]
0x14000bd5a  mov     [rbx+6Ch], r8d
0x14000bd5e  mov     ecx, [rax+20h]
0x14000bd61  test    cl, 1
0x14000bd64  jz      loc_14000BB7E
0x14000bd6a  cmp     dword ptr [rbx+40h], 2
0x14000bd6e  jnz     loc_14000BB7E
0x14000bd74  mov     rdx, [rbx+58h]
0x14000bd78  mov     rcx, [rbx+50h]; void *
0x14000bd7c  mov     rdx, [rdx+10h]; Src
0x14000bd80  call    memmove
0x14000bd85  jmp     loc_14000BB7E
0x14000bd8a  mov     ecx, edx
0x14000bd8c  call    Endpoint_StoppedCompletionCode
0x14000bd91  test    al, al
0x14000bd93  jz      short loc_14000BDF0
0x14000bd95  mov     eax, [rbx+68h]
0x14000bd98  cmp     [rbx+6Ch], eax
0x14000bd9b  jnz     short loc_14000BDA6
0x14000bd9d  mov     dword ptr [rbx+7Ch], 1
0x14000bda4  jmp     short loc_14000BDB2
0x14000bda6  cmp     dl, 1Ch
0x14000bda9  jnz     short loc_14000BDB2
0x14000bdab  mov     dword ptr [rbx+7Ch], 1Ch
0x14000bdb2  inc     dword ptr [rbx+84h]
0x14000bdb8  mov     ecx, [rsp+98h+arg_8]
0x14000bdbf  sub     ecx, [rbx+84h]
0x14000bdc5  mov     dl, [rdi+68h]; NewIrql
0x14000bdc8  inc     ecx
0x14000bdca  mov     [rdi+174h], ecx
0x14000bdd0  mov     rcx, r14; SpinLock
0x14000bdd3  call    cs:__imp_KeReleaseSpinLock
0x14000bdda  nop     dword ptr [rax+rax+00h]
0x14000bddf  mov     r10, [rsi]
0x14000bde2  prefetchw byte ptr [r10+20h]
0x14000bde7  mov     eax, [r10+20h]
0x14000bdeb  jmp     loc_14000BCAC
0x14000bdf0  mov     dl, [rdi+68h]
0x14000bdf3  jmp     loc_14000BC47
```
