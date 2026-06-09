# CHandlerCache::RefreshHandlerCollections(void)

- ea: `0x180014ad4`
- end: `0x180014ba9`
- name: `?RefreshHandlerCollections@CHandlerCache@@QEAAJXZ`
- size: `213`
- prototype: `__int64 __fastcall(CHandlerCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800201d0`

## callees

- `0x18000a714`
- `0x180012e54`
- `0x180014ad4`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180014b5f`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180014b5f`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180014b1b`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180014b1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014b83`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ae9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ae9`

## pseudocode

```c
__int64 __fastcall CHandlerCache::RefreshHandlerCollections(CHandlerCache *this)
{
  unsigned int v2; // esi
  void *v3; // rcx
  int Error; // ebx
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp+8h] BYREF

  LOBYTE(v2) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v3 = (void *)*((_QWORD *)this + 54);
  DueTime.QuadPart = -5000000;
  if ( SetWaitableTimer(v3, &DueTime, 0, 0, 0, 0) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    if ( *((_QWORD *)this + 53) == -1 )
    {
      _InterlockedExchange((volatile __int32 *)this + 24, 0);
      _InterlockedIncrement((volatile signed __int32 *)this + 99);
      if ( SHCreateThreadWithHandle((WCHAR)CHandlerCache::s_RefreshHandlerCollectionsThreadProc) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      v2 = (unsigned int)Error >> 31;
    }
    else
    {
      Error = 1;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  if ( (_BYTE)v2 == 1 )
    CHandlerCache::Release(this);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180014ad4  mov     [rsp+arg_8], rbx
0x180014ad9  mov     [rsp+arg_10], rsi
0x180014ade  push    rdi
0x180014adf  sub     rsp, 30h
0x180014ae3  mov     rdi, rcx
0x180014ae6  xor     sil, sil
0x180014ae9  call    cs:__imp_EnterCriticalSection
0x180014aef  mov     rcx, [rdi+1B0h]; hTimer
0x180014af6  lea     rdx, [rsp+38h+DueTime]; lpDueTime
0x180014afb  xor     r9d, r9d; pfnCompletionRoutine
0x180014afe  mov     [rsp+38h+fResume], 0; fResume
0x180014b06  xor     r8d, r8d; lPeriod
0x180014b09  mov     qword ptr [rsp+38h+DueTime], 0FFFFFFFFFFB3B4C0h
0x180014b12  mov     [rsp+38h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x180014b1b  call    cs:__imp_SetWaitableTimer
0x180014b21  test    eax, eax
0x180014b23  jnz     short loc_180014B30
0x180014b25  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014b2a  mov     ebx, eax
0x180014b2c  test    eax, eax
0x180014b2e  js      short loc_180014B80
0x180014b30  lea     rcx, [rdi+1A8h]
0x180014b37  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180014b3b  jnz     short loc_180014B7B
0x180014b3d  xor     eax, eax
0x180014b3f  xchg    eax, [rdi+60h]
0x180014b42  lock inc dword ptr [rdi+18Ch]
0x180014b49  xor     r9d, r9d
0x180014b4c  mov     [rsp+38h+lpArgToCompletionRoutine], rcx
0x180014b51  mov     rdx, rdi
0x180014b54  lea     rcx, ?s_RefreshHandlerCollectionsThreadProc@CHandlerCache@@CAKPEAX@Z; ch
0x180014b5b  lea     r8d, [r9+8]
0x180014b5f  call    cs:__imp_SHCreateThreadWithHandle
0x180014b65  test    eax, eax
0x180014b67  jz      short loc_180014B6D
0x180014b69  xor     ebx, ebx
0x180014b6b  jmp     short loc_180014B74
0x180014b6d  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014b72  mov     ebx, eax
0x180014b74  mov     esi, ebx
0x180014b76  shr     esi, 1Fh
0x180014b79  jmp     short loc_180014B80
0x180014b7b  mov     ebx, 1
0x180014b80  mov     rcx, rdi; lpCriticalSection
0x180014b83  call    cs:__imp_LeaveCriticalSection
0x180014b89  cmp     sil, 1
0x180014b8d  jnz     short loc_180014B97
0x180014b8f  mov     rcx, rdi; this
0x180014b92  call    ?Release@CHandlerCache@@QEAAJXZ; CHandlerCache::Release(void)
0x180014b97  mov     rsi, [rsp+38h+arg_10]
0x180014b9c  mov     eax, ebx
0x180014b9e  mov     rbx, [rsp+38h+arg_8]
0x180014ba3  add     rsp, 30h
0x180014ba7  pop     rdi
0x180014ba8  retn
```
