# CFICache::GetFontMetrics(short,CFontOptions const &,short,long,long &,long &,long &,FONTINFO_FLAGS &)

- ea: `0x18002e508`
- end: `0x18002e6dc`
- name: `?GetFontMetrics@CFICache@@SAHFAEBVCFontOptions@@FJAEAJ11AEATFONTINFO_FLAGS@@@Z`
- size: `468`
- prototype: `static int(__int16, const struct CFontOptions *, __int16, int, int *, int *, int *, union FONTINFO_FLAGS *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180126158`
- `0x18018b968`

## callees

- `0x180029548`
- `0x18002ab44`
- `0x18002af88`
- `0x18002cb14`
- `0x18002e508`
- `0x18006e770`
- `0x1800810b8`
- `0x18017b70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e624`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e624`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e5c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e62a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e5c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e62a`

## pseudocode

```c
__int64 __fastcall CFICache::GetFontMetrics(
        __int16 a1,
        const struct CFontOptions *a2,
        __int16 a3,
        int a4,
        int *a5,
        int *a6,
        int *a7,
        union FONTINFO_FLAGS *a8)
{
  int v8; // ebx
  int v9; // r12d
  unsigned __int16 v12; // ax
  int v14; // edi
  _DWORD *LockTelemetry; // rax
  RTL_SRWLOCK *Lock; // rax
  __int64 v17; // rax
  unsigned __int16 FontEMSquare; // ax
  int v19; // ebx
  int v20; // edi
  int v21; // r11d
  int v22; // r11d
  int v23; // r11d
  unsigned __int16 v24[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 v25[2]; // [rsp+34h] [rbp-24h] BYREF
  _QWORD v26[4]; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 v27; // [rsp+A0h] [rbp+48h] BYREF

  v8 = a1;
  v9 = a3;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
    return 0;
  v26[0] = 0;
  v26[1] = 0;
  v27 = 0;
  if ( a1 >= 70 )
  {
    v14 = (int)CLockSharedData::LockOwner;
    *(_DWORD *)v25 = 0;
    if ( (_DWORD)CLockSharedData::LockOwner && v14 == GetCurrentThreadId() )
    {
      LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
      ++*LockTelemetry;
    }
    else
    {
      Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
      AcquireSRWLockExclusive(Lock);
      LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
      v17 = CLock::GetLockTelemetry(0);
      ++*(_DWORD *)(v17 + 4);
    }
    ++g_cFCLock;
    CFICache::GetFontInfoFromFaceNameHelper(
      (struct FONTINFO *)CFICache::_pFontInfo + 2 * v8 - 140,
      v8,
      a2,
      (union FONTINFO_FLAGS *)&v27,
      (struct CCharFlags *)v26);
    --g_cFCLock;
    CWriteLock::~CWriteLock((CWriteLock *)v25);
  }
  else
  {
    CFICache::GetFontInfoFromFaceNameHelper(
      (FONTINFO *)((char *)&CFICache::_PredefFontInfo + 48 * a1),
      a1,
      a2,
      (union FONTINFO_FLAGS *)&v27,
      (struct CCharFlags *)v26);
  }
  v12 = v27;
  *(_WORD *)a8 = v27;
  if ( (v12 & 0x100) == 0 && (v12 & 0x2000) == 0 )
    return 0;
  v25[0] = 0;
  v24[0] = 0;
  v27 = 0;
  CFICache::GetFontInfoMetrics(v8, v25, v24, &v27);
  FontEMSquare = CFICache::GetFontEMSquare(v8);
  v19 = v27;
  v20 = v24[0];
  v21 = FontEMSquare;
  if ( a4 == 914400 )
    a4 = 635;
  else
    v21 = 1440 * FontEMSquare;
  *a5 = CW32System::MulDivFunc(v25[0], a4 * v9, v21);
  *a6 = CW32System::MulDivFunc(v20, a4 * v9, v22);
  *a7 = CW32System::MulDivFunc(v19, a4 * v9, v23);
  return 1;
}

```

## disassembly

```asm
0x18002e508  push    rbp
0x18002e50a  push    rbx
0x18002e50b  push    rsi
0x18002e50c  push    rdi
0x18002e50d  push    r12
0x18002e50f  push    r13
0x18002e511  push    r14
0x18002e513  push    r15
0x18002e515  mov     rbp, rsp
0x18002e518  sub     rsp, 58h
0x18002e51c  movsx   rbx, cx
0x18002e520  xor     r13d, r13d
0x18002e523  movsx   r12d, r8w
0x18002e527  mov     r14d, r9d
0x18002e52a  mov     r15, rdx
0x18002e52d  test    bx, bx
0x18002e530  js      short loc_18002E5A3
0x18002e532  movsx   eax, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x18002e539  lea     ecx, [r13+46h]
0x18002e53d  add     eax, ecx
0x18002e53f  cmp     ebx, eax
0x18002e541  jge     short loc_18002E5A3
0x18002e543  mov     [rbp+var_20], r13
0x18002e547  mov     [rbp+var_18], r13
0x18002e54b  mov     [rbp+arg_0], r13w
0x18002e550  cmp     bx, cx
0x18002e553  jge     short loc_18002E5B6
0x18002e555  lea     rax, ?_PredefFontInfo@CFICache@@0PAUFONTINFO@@A; FONTINFO near * CFICache::_PredefFontInfo
0x18002e55c  mov     r8, rdx; struct CFontOptions *
0x18002e55f  lea     rcx, [rbx+rbx*2]
0x18002e563  movzx   edx, bx; __int16
0x18002e566  shl     rcx, 4
0x18002e56a  lea     r9, [rbp+arg_0]; union FONTINFO_FLAGS *
0x18002e56e  add     rcx, rax; struct FONTINFO *
0x18002e571  lea     rax, [rbp+var_20]
0x18002e575  mov     [rsp+58h+var_38], rax; struct CCharFlags *
0x18002e57a  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x18002e57f  movzx   eax, [rbp+arg_0]
0x18002e583  bt      ax, 8
0x18002e588  mov     rcx, [rbp+arg_38]
0x18002e58f  mov     [rcx], ax
0x18002e592  jb      loc_18002E642
0x18002e598  bt      ax, 0Dh
0x18002e59d  jb      loc_18002E642
0x18002e5a3  xor     eax, eax
0x18002e5a5  add     rsp, 58h
0x18002e5a9  pop     r15
0x18002e5ab  pop     r14
0x18002e5ad  pop     r13
0x18002e5af  pop     r12
0x18002e5b1  pop     rdi
0x18002e5b2  pop     rsi
0x18002e5b3  pop     rbx
0x18002e5b4  pop     rbp
0x18002e5b5  retn
0x18002e5b6  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002e5bc  mov     dword ptr [rbp+var_24], r13d
0x18002e5c0  test    edi, edi
0x18002e5c2  jz      short loc_18002E61A
0x18002e5c4  call    cs:__imp_GetCurrentThreadId
0x18002e5ca  cmp     edi, eax
0x18002e5cc  jnz     short loc_18002E61A
0x18002e5ce  xor     ecx, ecx
0x18002e5d0  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18002e5d5  inc     dword ptr [rax]
0x18002e5d7  inc     cs:?g_cFCLock@@3JA; long g_cFCLock
0x18002e5dd  lea     eax, [rbx-46h]
0x18002e5e0  movsxd  rcx, eax
0x18002e5e3  lea     r9, [rbp+arg_0]; union FONTINFO_FLAGS *
0x18002e5e7  imul    rcx, 38h ; '8'
0x18002e5eb  lea     rax, [rbp+var_20]
0x18002e5ef  mov     r8, r15; struct CFontOptions *
0x18002e5f2  add     rcx, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; struct FONTINFO *
0x18002e5f9  movzx   edx, bx; __int16
0x18002e5fc  mov     [rsp+58h+var_38], rax; struct CCharFlags *
0x18002e601  call    ?GetFontInfoFromFaceNameHelper@CFICache@@CAXAEAUFONTINFO@@FAEBVCFontOptions@@AEATFONTINFO_FLAGS@@AEAVCCharFlags@@@Z; CFICache::GetFontInfoFromFaceNameHelper(FONTINFO &,short,CFontOptions const &,FONTINFO_FLAGS &,CCharFlags &)
0x18002e606  dec     cs:?g_cFCLock@@3JA; long g_cFCLock
0x18002e60c  lea     rcx, [rbp+var_24]; this
0x18002e610  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18002e615  jmp     loc_18002E57F
0x18002e61a  xor     ecx, ecx
0x18002e61c  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002e621  mov     rcx, rax; SRWLock
0x18002e624  call    cs:__imp_AcquireSRWLockExclusive
0x18002e62a  call    cs:__imp_GetCurrentThreadId
0x18002e630  xor     ecx, ecx
0x18002e632  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18002e638  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18002e63d  inc     dword ptr [rax+4]
0x18002e640  jmp     short loc_18002E5D7
0x18002e642  lea     r9, [rbp+arg_0]; unsigned __int16 *
0x18002e646  mov     [rbp+var_24], r13w
0x18002e64b  lea     r8, [rbp+var_28]; unsigned __int16 *
0x18002e64f  mov     [rbp+var_28], r13w
0x18002e654  lea     rdx, [rbp+var_24]; unsigned __int16 *
0x18002e658  mov     [rbp+arg_0], r13w
0x18002e65d  movzx   ecx, bx; __int16
0x18002e660  call    ?GetFontInfoMetrics@CFICache@@SAXFAEAG00@Z; CFICache::GetFontInfoMetrics(short,ushort &,ushort &,ushort &)
0x18002e665  movzx   ecx, bx; __int16
0x18002e668  mov     esi, r12d
0x18002e66b  call    ?GetFontEMSquare@CFICache@@SAGF@Z; CFICache::GetFontEMSquare(short)
0x18002e670  movzx   ebx, [rbp+arg_0]
0x18002e674  movzx   edi, [rbp+var_28]
0x18002e678  movzx   ecx, [rbp+var_24]; int
0x18002e67c  movzx   r11d, ax
0x18002e680  cmp     r14d, 0DF3E0h
0x18002e687  jnz     short loc_18002E691
0x18002e689  mov     r14d, 27Bh
0x18002e68f  jmp     short loc_18002E698
0x18002e691  imul    r11d, 5A0h
0x18002e698  imul    esi, r14d
0x18002e69c  mov     r8d, r11d; int
0x18002e69f  mov     edx, esi; int
0x18002e6a1  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18002e6a6  mov     r9, [rbp+arg_20]
0x18002e6aa  mov     r8d, r11d; int
0x18002e6ad  mov     edx, esi; int
0x18002e6af  mov     ecx, edi; int
0x18002e6b1  mov     [r9], eax
0x18002e6b4  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18002e6b9  mov     r9, [rbp+arg_28]
0x18002e6bd  mov     r8d, r11d; int
0x18002e6c0  mov     edx, esi; int
0x18002e6c2  mov     ecx, ebx; int
0x18002e6c4  mov     [r9], eax
0x18002e6c7  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18002e6cc  mov     rcx, [rbp+arg_30]
0x18002e6d0  mov     [rcx], eax
0x18002e6d2  mov     eax, 1
0x18002e6d7  jmp     loc_18002E5A5
```
