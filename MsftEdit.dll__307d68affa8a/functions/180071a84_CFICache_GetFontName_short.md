# CFICache::GetFontName(short)

- ea: `0x180071a84`
- end: `0x180071b58`
- name: `?GetFontName@CFICache@@SAPEBGF@Z`
- size: `212`
- prototype: `const unsigned __int16 *__fastcall(__int16)`
- caller_count: `31`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c820`
- `0x180021dc4`
- `0x180022344`
- `0x18002b310`
- `0x18002cb14`
- `0x180037390`
- `0x18004e254`
- `0x180051618`
- `0x180055400`
- `0x18005eb58`
- `0x180060690`
- `0x1800617a4`
- `0x1800645e4`
- `0x1800719a0`
- `0x180074ed4`
- `0x180080968`
- `0x1800b61b0`
- `0x1800dd964`
- `0x18010ae08`
- `0x1801196d8`
- `0x180122b30`
- `0x18012d0d8`
- `0x18012f99c`
- `0x180146e38`
- `0x18014ebbc`
- `0x180155a70`
- `0x180183efc`
- `0x180187de0`
- `0x18019d598`
- `0x18019dc30`
- `0x1802054e0`

## callees

- `0x18002ab44`
- `0x18002af88`
- `0x180071a84`
- `0x1800810b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071b31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180071b31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071b37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180071b37`

## pseudocode

```c
const unsigned __int16 *__fastcall CFICache::GetFontName(__int16 a1)
{
  __int64 v1; // rbx
  int v2; // edi
  _DWORD *LockTelemetry; // rax
  __int64 v4; // rbx
  RTL_SRWLOCK *Lock; // rax
  __int64 v7; // rax
  int v8; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
    return 0;
  if ( a1 < 70 )
    return (&off_18027B0F0)[a1];
  v2 = (int)CLockSharedData::LockOwner;
  v8 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v2 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v7 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v7 + 4);
  }
  if ( (__int16)(v1 - 70) >= CFICache::_cFontInfo )
    v4 = 0;
  else
    v4 = *((_QWORD *)CFICache::_pFontInfo + 7 * v1 - 484);
  CWriteLock::~CWriteLock((CWriteLock *)&v8);
  return (const unsigned __int16 *)v4;
}

```

## disassembly

```asm
0x180071a84  push    rbx
0x180071a86  push    rbp
0x180071a87  push    rsi
0x180071a88  push    rdi
0x180071a89  sub     rsp, 28h
0x180071a8d  movsx   rbx, cx
0x180071a91  xor     esi, esi
0x180071a93  test    bx, bx
0x180071a96  js      loc_180071B54
0x180071a9c  movsx   edx, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180071aa3  lea     ebp, [rsi+46h]
0x180071aa6  add     edx, ebp
0x180071aa8  cmp     ebx, edx
0x180071aaa  jge     loc_180071B54
0x180071ab0  cmp     bx, bp
0x180071ab3  jl      short loc_180071B1A
0x180071ab5  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180071abb  mov     [rsp+48h+arg_0], esi
0x180071abf  test    edi, edi
0x180071ac1  jz      short loc_180071B27
0x180071ac3  call    cs:__imp_GetCurrentThreadId
0x180071ac9  cmp     edi, eax
0x180071acb  jnz     short loc_180071B27
0x180071acd  xor     ecx, ecx
0x180071acf  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180071ad4  inc     dword ptr [rax]
0x180071ad6  mov     edx, cs:?g_cFCLock@@3JA; long g_cFCLock
0x180071adc  movzx   eax, bx
0x180071adf  sub     ax, bp
0x180071ae2  cmp     ax, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x180071ae9  jge     short loc_180071B4F
0x180071aeb  mov     rax, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; FONTINFOEX * CFICache::_pFontInfo
0x180071af2  imul    rcx, rbx, 38h ; '8'
0x180071af6  mov     rbx, [rcx+rax-0F20h]
0x180071afe  lea     rcx, [rsp+48h+arg_0]; this
0x180071b03  mov     cs:?g_cFCLock@@3JA, edx; long g_cFCLock
0x180071b09  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180071b0e  mov     rax, rbx
0x180071b11  add     rsp, 28h
0x180071b15  pop     rdi
0x180071b16  pop     rsi
0x180071b17  pop     rbp
0x180071b18  pop     rbx
0x180071b19  retn
0x180071b1a  lea     rcx, off_18027B0F0; "Arial"
0x180071b21  mov     rax, [rcx+rbx*8]
0x180071b25  jmp     short loc_180071B11
0x180071b27  xor     ecx, ecx
0x180071b29  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180071b2e  mov     rcx, rax; SRWLock
0x180071b31  call    cs:__imp_AcquireSRWLockExclusive
0x180071b37  call    cs:__imp_GetCurrentThreadId
0x180071b3d  xor     ecx, ecx
0x180071b3f  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180071b45  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180071b4a  inc     dword ptr [rax+4]
0x180071b4d  jmp     short loc_180071AD6
0x180071b4f  mov     rbx, rsi
0x180071b52  jmp     short loc_180071AFE
0x180071b54  xor     eax, eax
0x180071b56  jmp     short loc_180071B11
```
