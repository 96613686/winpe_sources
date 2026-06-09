# CFICache::GetFontInfoFromFaceName(short,CFontOptions const &,CCharFlags *,FONTINFO_FLAGS *)

- ea: `0x18002c970`
- end: `0x18002cb0e`
- name: `?GetFontInfoFromFaceName@CFICache@@SAJFAEBVCFontOptions@@PEAVCCharFlags@@PEATFONTINFO_FLAGS@@@Z`
- size: `414`
- prototype: `static int(__int16, const struct CFontOptions *, struct CCharFlags *, union FONTINFO_FLAGS *)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180022aa8`
- `0x180038ad4`
- `0x18004ebe0`
- `0x1800500f8`
- `0x180055400`
- `0x180060690`
- `0x180063590`
- `0x180074ed4`
- `0x1800b4610`
- `0x1800b61b0`
- `0x1800c1154`
- `0x1800c2640`
- `0x1800c33f8`
- `0x1800f6470`
- `0x180102a84`
- `0x180139328`
- `0x18017b7b8`
- `0x18017bca8`
- `0x1801ddc3c`

## callees

- `0x18002af88`
- `0x18002c970`
- `0x18002cb14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cac3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002cac3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002caae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002caae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ca4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cac9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ca4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cac9`

## pseudocode

```c
__int64 __fastcall CFICache::GetFontInfoFromFaceName(
        __int16 a1,
        const struct CFontOptions *a2,
        struct CCharFlags *a3,
        union FONTINFO_FLAGS *a4)
{
  __int64 v4; // rbp
  unsigned int v8; // edi
  char v9; // al
  int v11; // r14d
  RTL_SRWLOCK *v12; // rax
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  _OWORD v15[5]; // [rsp+30h] [rbp-58h] BYREF
  __int16 v16; // [rsp+90h] [rbp+8h] BYREF

  v4 = a1;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
  {
    if ( a3 )
    {
      *(_QWORD *)a3 = 0;
      *((_QWORD *)a3 + 1) = 0;
    }
    if ( a4 )
      *(_WORD *)a4 = 0;
    return 2147942487LL;
  }
  else
  {
    v15[0] = 0u;
    v8 = 1;
    v16 = 0;
    if ( a1 >= 70 )
    {
      v11 = (int)CLockSharedData::LockOwner;
      if ( (_DWORD)CLockSharedData::LockOwner && v11 == GetCurrentThreadId() )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry + 1;
      }
      else
      {
        Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
        AcquireSRWLockExclusive(Lock);
        CurrentThreadId = GetCurrentThreadId();
        ++dword_1802DF74C[0];
        LODWORD(CLockSharedData::LockOwner) = CurrentThreadId;
      }
      ++g_cFCLock;
      CFICache::GetFontInfoFromFaceNameHelper(
        (struct FONTINFO *)CFICache::_pFontInfo + 2 * v4 - 140,
        v4,
        a2,
        (union FONTINFO_FLAGS *)&v16,
        (struct CCharFlags *)v15);
      --g_cFCLock;
      if ( (int)CLockSharedData::LockTelemetry > 0 )
      {
        LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
      }
      else
      {
        LODWORD(CLockSharedData::LockOwner) = 0;
        v12 = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
        ReleaseSRWLockExclusive(v12);
      }
    }
    else
    {
      CFICache::GetFontInfoFromFaceNameHelper(
        (FONTINFO *)((char *)&CFICache::_PredefFontInfo + 48 * a1),
        a1,
        a2,
        (union FONTINFO_FLAGS *)&v16,
        (struct CCharFlags *)v15);
    }
    if ( a3 )
      *(_OWORD *)a3 = v15[0];
    v9 = v16;
    if ( a4 )
      *(_WORD *)a4 = v16;
    if ( v15[0] != 0 && (v9 & 2) == 0 )
      return 0;
    return v8;
  }
}

```

## disassembly

```asm
0x18002c970  mov     r11, rsp
0x18002c973  push    rbx
0x18002c974  push    rbp
0x18002c975  push    rsi
0x18002c976  push    rdi
0x18002c977  push    r12
0x18002c979  push    r13
0x18002c97b  push    r14
0x18002c97d  push    r15
0x18002c97f  sub     rsp, 48h
0x18002c983  movsx   rbp, cx
0x18002c987  xor     r13d, r13d
0x18002c98a  mov     rsi, r9
0x18002c98d  mov     rbx, r8
0x18002c990  mov     r12, rdx
0x18002c993  test    bp, bp
0x18002c996  js      loc_18002CAED
0x18002c99c  movsx   eax, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x18002c9a3  lea     ecx, [r13+46h]
0x18002c9a7  add     eax, ecx
0x18002c9a9  cmp     ebp, eax
0x18002c9ab  jge     loc_18002CAED
0x18002c9b1  mov     [r11-58h], r13
0x18002c9b5  lea     edi, [rcx-45h]
0x18002c9b8  mov     [r11-50h], r13
0x18002c9bc  mov     [r11+8], r13w
0x18002c9c1  cmp     bp, cx
0x18002c9c4  jge     short loc_18002CA3E
0x18002c9c6  lea     rax, ?_PredefFontInfo@CFICache@@0PAUFONTINFO@@A; FONTINFO near * CFICache::_PredefFontInfo
0x18002c9cd  mov     r8, rdx; struct CFontOptions *
0x18002c9d0  lea     rcx, ds:0[rbp*2]
0x18002c9d8  movzx   edx, bp; __int16
0x18002c9db  add     rcx, rbp
0x18002c9de  lea     r9, [r11+8]; union FONTINFO_FLAGS *
0x18002c9e2  shl     rcx, 4
0x18002c9e6  add     rcx, rax; struct FONTINFO *
0x18002c9e9  lea     rax, [r11-58h]
0x18002c9ed  mov     [r11-68h], rax
0x18002c9f1  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x18002c9f6  test    rbx, rbx
0x18002c9f9  jz      short loc_18002CA04
0x18002c9fb  movups  xmm0, [rsp+88h+var_58]
0x18002ca00  movdqu  xmmword ptr [rbx], xmm0
0x18002ca04  movzx   eax, [rsp+88h+arg_0]
0x18002ca0c  test    rsi, rsi
0x18002ca0f  jz      short loc_18002CA14
0x18002ca11  mov     [rsi], ax
0x18002ca14  cmp     qword ptr [rsp+88h+var_58], r13
0x18002ca19  jz      short loc_18002CA24
0x18002ca1b  test    al, 2
0x18002ca1d  jnz     short loc_18002CA2B
0x18002ca1f  mov     edi, r13d
0x18002ca22  jmp     short loc_18002CA2B
0x18002ca24  cmp     qword ptr [rsp+88h+var_58+8], r13
0x18002ca29  jnz     short loc_18002CA1B
0x18002ca2b  mov     eax, edi
0x18002ca2d  add     rsp, 48h
0x18002ca31  pop     r15
0x18002ca33  pop     r14
0x18002ca35  pop     r13
0x18002ca37  pop     r12
0x18002ca39  pop     rdi
0x18002ca3a  pop     rsi
0x18002ca3b  pop     rbp
0x18002ca3c  pop     rbx
0x18002ca3d  retn
0x18002ca3e  mov     r14d, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002ca45  test    r14d, r14d
0x18002ca48  jz      short loc_18002CAB9
0x18002ca4a  call    cs:__imp_GetCurrentThreadId
0x18002ca50  cmp     r14d, eax
0x18002ca53  jnz     short loc_18002CAB9
0x18002ca55  add     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, edi; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002ca5b  add     cs:?g_cFCLock@@3JA, edi; long g_cFCLock
0x18002ca61  lea     rax, [rbp-46h]
0x18002ca65  imul    rcx, rax, 38h ; '8'
0x18002ca69  lea     rax, [rsp+88h+var_58]
0x18002ca6e  mov     r8, r12; struct CFontOptions *
0x18002ca71  add     rcx, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; struct FONTINFO *
0x18002ca78  lea     r9, [rsp+88h+arg_0]; union FONTINFO_FLAGS *
0x18002ca80  movzx   edx, bp; __int16
0x18002ca83  mov     [rsp+88h+var_68], rax; struct CCharFlags *
0x18002ca88  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x18002ca8d  sub     cs:?g_cFCLock@@3JA, edi; long g_cFCLock
0x18002ca93  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002ca99  test    eax, eax
0x18002ca9b  jg      short loc_18002CAE0
0x18002ca9d  xor     ecx, ecx
0x18002ca9f  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, r13d; uint near * CLockSharedData::LockOwner
0x18002caa6  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002caab  mov     rcx, rax; SRWLock
0x18002caae  call    cs:__imp_ReleaseSRWLockExclusive
0x18002cab4  jmp     loc_18002C9F6
0x18002cab9  xor     ecx, ecx
0x18002cabb  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002cac0  mov     rcx, rax; SRWLock
0x18002cac3  call    cs:__imp_AcquireSRWLockExclusive
0x18002cac9  call    cs:__imp_GetCurrentThreadId
0x18002cacf  add     cs:dword_1802DF74C, edi
0x18002cad5  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18002cadb  jmp     loc_18002CA5B
0x18002cae0  dec     eax
0x18002cae2  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002cae8  jmp     loc_18002C9F6
0x18002caed  test    rbx, rbx
0x18002caf0  jz      short loc_18002CAF9
0x18002caf2  mov     [r8], r13
0x18002caf5  mov     [r8+8], r13
0x18002caf9  test    rsi, rsi
0x18002cafc  jnz     short loc_18002CB08
0x18002cafe  mov     eax, 80070057h
0x18002cb03  jmp     loc_18002CA2D
0x18002cb08  mov     [r9], r13w
0x18002cb0c  jmp     short loc_18002CAFE
```
