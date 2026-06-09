# CTieredVolume::MarkVolumeAsRemounted(void)

- ea: `0x140010b50`
- end: `0x140010d16`
- name: `?MarkVolumeAsRemounted@CTieredVolume@@QEAAHXZ`
- size: `454`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007954`

## callees

- `0x140004a68`
- `0x140010b50`
- `0x140017b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140010c4d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140010c5a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140010c4d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140010c5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010bb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010d04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010bb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010d04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010b64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010bf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010b64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010bf8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140010bef`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140010bef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010c8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010c8c`

## pseudocode

```c
__int64 __fastcall CTieredVolume::MarkVolumeAsRemounted(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rbx
  unsigned int v3; // esi
  struct _TP_TIMER *Ptr; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  v1 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  v3 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 32);
  }
  HIBYTE(this[20].Ptr) = 0;
  while ( BYTE6(this[20].Ptr) )
  {
    ReleaseSRWLockExclusive(v1);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 33);
    }
    Sleep(0x32u);
    AcquireSRWLockExclusive(v1);
  }
  if ( BYTE5(this[20].Ptr) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 34);
    }
    ResetEvent(this[96].Ptr);
    ResetEvent(this[97].Ptr);
    Ptr = (struct _TP_TIMER *)this[114].Ptr;
    BYTE5(this[20].Ptr) = 0;
    pftDueTime.dwLowDateTime = -1640261632;
    pftDueTime.dwHighDateTime = -9;
    SetThreadpoolTimer(Ptr, &pftDueTime, 0, 0x186A0u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        LODWORD(this[16].Ptr));
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 36);
    }
    v3 = 0;
  }
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  return v3;
}

```

## disassembly

```asm
0x140010b50  push    rbx
0x140010b52  push    rsi
0x140010b53  push    rdi
0x140010b54  push    r15
0x140010b56  sub     rsp, 38h
0x140010b5a  lea     rbx, [rcx+18h]
0x140010b5e  mov     rdi, rcx
0x140010b61  mov     rcx, rbx; SRWLock
0x140010b64  call    cs:__imp_AcquireSRWLockExclusive
0x140010b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b71  lea     r15, WPP_GLOBAL_Control
0x140010b78  mov     esi, 1
0x140010b7d  cmp     rcx, r15
0x140010b80  jz      short loc_140010BA6
0x140010b82  test    [rcx+1Ch], sil
0x140010b86  jz      short loc_140010BA6
0x140010b88  cmp     byte ptr [rcx+19h], 4
0x140010b8c  jb      short loc_140010BA6
0x140010b8e  mov     r9d, [rdi+80h]
0x140010b95  lea     edx, [rsi+1Fh]
0x140010b98  mov     rcx, [rcx+10h]
0x140010b9c  mov     [rsp+58h+var_38], rdi
0x140010ba1  call    WPP_SF_Dq
0x140010ba6  mov     byte ptr [rdi+0A7h], 0
0x140010bad  jmp     short loc_140010BFE
0x140010baf  mov     rcx, rbx; SRWLock
0x140010bb2  call    cs:__imp_ReleaseSRWLockExclusive
0x140010bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140010bbf  cmp     rcx, r15
0x140010bc2  jz      short loc_140010BEA
0x140010bc4  test    [rcx+1Ch], sil
0x140010bc8  jz      short loc_140010BEA
0x140010bca  cmp     byte ptr [rcx+19h], 3
0x140010bce  jb      short loc_140010BEA
0x140010bd0  mov     r9d, [rdi+80h]
0x140010bd7  mov     edx, 21h ; '!'
0x140010bdc  mov     rcx, [rcx+10h]
0x140010be0  mov     [rsp+58h+var_38], rdi
0x140010be5  call    WPP_SF_Dq
0x140010bea  mov     ecx, 32h ; '2'; dwMilliseconds
0x140010bef  call    cs:__imp_Sleep
0x140010bf5  mov     rcx, rbx; SRWLock
0x140010bf8  call    cs:__imp_AcquireSRWLockExclusive
0x140010bfe  cmp     byte ptr [rdi+0A6h], 0
0x140010c05  jnz     short loc_140010BAF
0x140010c07  cmp     byte ptr [rdi+0A5h], 0
0x140010c0e  jz      loc_140010CC8
0x140010c14  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c1b  cmp     rcx, r15
0x140010c1e  jz      short loc_140010C46
0x140010c20  test    [rcx+1Ch], sil
0x140010c24  jz      short loc_140010C46
0x140010c26  cmp     byte ptr [rcx+19h], 4
0x140010c2a  jb      short loc_140010C46
0x140010c2c  mov     r9d, [rdi+80h]
0x140010c33  mov     edx, 22h ; '"'
0x140010c38  mov     rcx, [rcx+10h]
0x140010c3c  mov     [rsp+58h+var_38], rdi
0x140010c41  call    WPP_SF_Dq
0x140010c46  mov     rcx, [rdi+300h]; hEvent
0x140010c4d  call    cs:__imp_ResetEvent
0x140010c53  mov     rcx, [rdi+308h]; hEvent
0x140010c5a  call    cs:__imp_ResetEvent
0x140010c60  mov     rcx, [rdi+390h]; pti
0x140010c67  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x140010c6c  mov     r9d, 186A0h; msWindowLength
0x140010c72  mov     byte ptr [rdi+0A5h], 0
0x140010c79  xor     r8d, r8d; msPeriod
0x140010c7c  mov     [rsp+58h+pftDueTime.dwLowDateTime], 9E3B9800h
0x140010c84  mov     [rsp+58h+pftDueTime.dwHighDateTime], 0FFFFFFF7h
0x140010c8c  call    cs:__imp_SetThreadpoolTimer
0x140010c92  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c99  cmp     rcx, r15
0x140010c9c  jz      short loc_140010CFC
0x140010c9e  test    [rcx+1Ch], sil
0x140010ca2  jz      short loc_140010CFC
0x140010ca4  cmp     byte ptr [rcx+19h], 4
0x140010ca8  jb      short loc_140010CFC
0x140010caa  mov     r9d, [rdi+80h]
0x140010cb1  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140010cb8  mov     rcx, [rcx+10h]
0x140010cbc  mov     edx, 23h ; '#'
0x140010cc1  call    WPP_SF_d
0x140010cc6  jmp     short loc_140010CFC
0x140010cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ccf  cmp     rcx, r15
0x140010cd2  jz      short loc_140010CFA
0x140010cd4  test    [rcx+1Ch], sil
0x140010cd8  jz      short loc_140010CFA
0x140010cda  cmp     byte ptr [rcx+19h], 4
0x140010cde  jb      short loc_140010CFA
0x140010ce0  mov     r9d, [rdi+80h]
0x140010ce7  mov     edx, 24h ; '$'
0x140010cec  mov     rcx, [rcx+10h]
0x140010cf0  mov     [rsp+58h+var_38], rdi
0x140010cf5  call    WPP_SF_Dq
0x140010cfa  xor     esi, esi
0x140010cfc  test    rbx, rbx
0x140010cff  jz      short loc_140010D0A
0x140010d01  mov     rcx, rbx; SRWLock
0x140010d04  call    cs:__imp_ReleaseSRWLockExclusive
0x140010d0a  mov     eax, esi
0x140010d0c  add     rsp, 38h
0x140010d10  pop     r15
0x140010d12  pop     rdi
0x140010d13  pop     rsi
0x140010d14  pop     rbx
0x140010d15  retn
```
