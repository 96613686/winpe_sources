# CFICache::GetFontEMSquare(short)

- ea: `0x180029548`
- end: `0x180029628`
- name: `?GetFontEMSquare@CFICache@@SAGF@Z`
- size: `224`
- prototype: `unsigned __int16 __fastcall(__int16)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180022aa8`
- `0x180028d1c`
- `0x18002b310`
- `0x18002e508`
- `0x1800b2a5c`

## callees

- `0x180029548`
- `0x18002ab44`
- `0x18002af88`
- `0x1800810b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800295ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800295ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002958d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029605`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002958d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029605`

## pseudocode

```c
__int16 __fastcall CFICache::GetFontEMSquare(__int16 a1)
{
  __int64 v1; // rbx
  int v2; // edi
  _DWORD *LockTelemetry; // rax
  __int16 v4; // bx
  __int16 result; // ax
  RTL_SRWLOCK *Lock; // rax
  __int64 v7; // rax
  int v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1;
  if ( a1 < 0 || a1 >= CFICache::_cFontInfo + 70 )
    return 0;
  if ( a1 < 70 )
  {
    result = qword_1802DD9F8[6 * a1];
    if ( !result )
      return 2048;
  }
  else
  {
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
    v4 = *((_WORD *)CFICache::_pFontInfo + 28 * v1 - 1940);
    CWriteLock::~CWriteLock((CWriteLock *)&v8);
    if ( v4 )
      return v4;
    else
      return 2048;
  }
  return result;
}

```

## disassembly

```asm
0x180029548  mov     [rsp+arg_8], rbx
0x18002954d  mov     [rsp+arg_10], rsi
0x180029552  push    rdi
0x180029553  sub     rsp, 20h
0x180029557  movsx   rbx, cx
0x18002955b  xor     esi, esi
0x18002955d  test    bx, bx
0x180029560  js      loc_180029624
0x180029566  movsx   edx, cs:?_cFontInfo@CFICache@@0FA; short CFICache::_cFontInfo
0x18002956d  lea     ecx, [rsi+46h]
0x180029570  add     edx, ecx
0x180029572  cmp     ebx, edx
0x180029574  jge     loc_180029624
0x18002957a  cmp     bx, cx
0x18002957d  jl      short loc_1800295D5
0x18002957f  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180029585  mov     [rsp+28h+arg_0], esi
0x180029589  test    edi, edi
0x18002958b  jz      short loc_1800295F5
0x18002958d  call    cs:__imp_GetCurrentThreadId
0x180029593  cmp     edi, eax
0x180029595  jnz     short loc_1800295F5
0x180029597  xor     ecx, ecx
0x180029599  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18002959e  inc     dword ptr [rax]
0x1800295a0  mov     rax, cs:?_pFontInfo@CFICache@@0PEAUFONTINFOEX@@EA; FONTINFOEX * CFICache::_pFontInfo
0x1800295a7  imul    rcx, rbx, 38h ; '8'
0x1800295ab  movzx   ebx, word ptr [rcx+rax-0F28h]
0x1800295b3  lea     rcx, [rsp+28h+arg_0]; this
0x1800295b8  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800295bd  test    bx, bx
0x1800295c0  jz      short loc_18002961D
0x1800295c2  movzx   eax, bx
0x1800295c5  mov     rbx, [rsp+28h+arg_8]
0x1800295ca  mov     rsi, [rsp+28h+arg_10]
0x1800295cf  add     rsp, 20h
0x1800295d3  pop     rdi
0x1800295d4  retn
0x1800295d5  lea     rcx, [rbx+rbx*2]
0x1800295d9  add     rcx, rcx
0x1800295dc  lea     rax, qword_1802DD9F8
0x1800295e3  movzx   eax, word ptr [rax+rcx*8]
0x1800295e7  mov     ecx, 800h
0x1800295ec  test    ax, ax
0x1800295ef  cmovz   ax, cx
0x1800295f3  jmp     short loc_1800295C5
0x1800295f5  xor     ecx, ecx
0x1800295f7  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x1800295fc  mov     rcx, rax; SRWLock
0x1800295ff  call    cs:__imp_AcquireSRWLockExclusive
0x180029605  call    cs:__imp_GetCurrentThreadId
0x18002960b  xor     ecx, ecx
0x18002960d  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x180029613  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180029618  inc     dword ptr [rax+4]
0x18002961b  jmp     short loc_1800295A0
0x18002961d  mov     eax, 800h
0x180029622  jmp     short loc_1800295C5
0x180029624  mov     eax, esi
0x180029626  jmp     short loc_1800295C5
```
