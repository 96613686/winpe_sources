# CDbOperationManager::InitializeGlobalContextState(void)

- ea: `0x1800ea120`
- end: `0x1800ea28f`
- name: `?InitializeGlobalContextState@CDbOperationManager@@CAJXZ`
- size: `367`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800e93ec`

## callees

- `0x180003eec`
- `0x1800d6e58`
- `0x1800d6eb4`
- `0x1800d82ec`
- `0x1800e85c8`
- `0x1800ea120`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ea207`
- `KERNEL32!GetLastError` at `0x1800ea207`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800ea1b6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800ea1b6`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800ea1db`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800ea1f8`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800ea1db`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800ea1f8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ea16d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ea16d`

## pseudocode

```c
__int64 CDbOperationManager::InitializeGlobalContextState(void)
{
  signed int v0; // ebx
  struct _RTL_CRITICAL_SECTION *v1; // rax
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  struct _RTL_CRITICAL_SECTION_DEBUG *SemaphoreW; // rax
  HANDLE v4; // rax
  signed int LastError; // eax
  unsigned int v6; // edx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      "CDbOperationManager::InitializeGlobalContextState");
  v0 = 0;
  while ( _InterlockedCompareExchange(&dword_1801AFEF4, 1, 0) )
    Sleep(0);
  if ( ++dword_1801AFEF0 == 1 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)operator new(0x118u, (const struct std::nothrow_t *)&byte_180166367);
    v2 = v1;
    if ( v1 )
    {
      InitializeCriticalSectionEx(v1, 0, 0);
      v2[1].DebugInfo = 0;
      *(_QWORD *)&v2[1].LockCount = 0;
      CDbTransactionContext::CDbTransactionContext((CDbTransactionContext *)&v2[1].OwningThread);
      SemaphoreW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateSemaphoreW(0, lInitialCount, lInitialCount, 0);
      v2[1].DebugInfo = SemaphoreW;
      if ( SemaphoreW )
      {
        v4 = CreateSemaphoreW(0, lMaximumCount, lMaximumCount, 0);
        *(_QWORD *)&v2[1].LockCount = v4;
        if ( v4 )
          goto LABEL_17;
      }
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
      if ( v0 >= 0 )
        goto LABEL_17;
      GLOBAL_CONTEXT_STATE::`scalar deleting destructor'((GLOBAL_CONTEXT_STATE *)v2, v6);
    }
    else
    {
      v0 = -2147024882;
    }
    v2 = 0;
LABEL_17:
    lpCriticalSection = v2;
    CDbTransactionContext::s_pNullTransactionContext = (struct CDbTransactionContext *)&v2[1].OwningThread;
  }
  _InterlockedExchange(&dword_1801AFEF4, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      (unsigned int)"CDbOperationManager::InitializeGlobalContextState",
      v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800ea120  mov     [rsp+arg_8], rbx
0x1800ea125  mov     [rsp+arg_10], rsi
0x1800ea12a  push    rdi
0x1800ea12b  sub     rsp, 30h
0x1800ea12f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea136  lea     rsi, WPP_GLOBAL_Control
0x1800ea13d  cmp     rcx, rsi
0x1800ea140  jz      short loc_1800EA164
0x1800ea142  test    byte ptr [rcx+1Ch], 4
0x1800ea146  jz      short loc_1800EA164
0x1800ea148  mov     rcx, [rcx+10h]
0x1800ea14c  lea     r9, aCdboperationma_3; "CDbOperationManager::InitializeGlobalCo"...
0x1800ea153  mov     edx, 0Ah
0x1800ea158  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800ea15f  call    WPP_SF_s
0x1800ea164  xor     ebx, ebx
0x1800ea166  lea     edi, [rbx+1]
0x1800ea169  jmp     short loc_1800EA173
0x1800ea16b  xor     ecx, ecx; dwMilliseconds
0x1800ea16d  call    cs:__imp_Sleep
0x1800ea173  xor     eax, eax
0x1800ea175  lock cmpxchg cs:dword_1801AFEF4, edi
0x1800ea17d  jnz     short loc_1800EA16B
0x1800ea17f  mov     eax, cs:dword_1801AFEF0
0x1800ea185  add     eax, edi
0x1800ea187  mov     cs:dword_1801AFEF0, eax
0x1800ea18d  cmp     eax, edi
0x1800ea18f  jnz     loc_1800EA243
0x1800ea195  lea     rdx, byte_180166367; struct std::nothrow_t *
0x1800ea19c  mov     ecx, 118h; unsigned __int64
0x1800ea1a1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800ea1a6  mov     rdi, rax
0x1800ea1a9  test    rax, rax
0x1800ea1ac  jz      short loc_1800EA22A
0x1800ea1ae  xor     r8d, r8d; Flags
0x1800ea1b1  xor     edx, edx; dwSpinCount
0x1800ea1b3  mov     rcx, rax; lpCriticalSection
0x1800ea1b6  call    cs:__imp_InitializeCriticalSectionEx
0x1800ea1bc  lea     rcx, [rdi+38h]; this
0x1800ea1c0  mov     [rdi+28h], rbx
0x1800ea1c4  mov     [rdi+30h], rbx
0x1800ea1c8  call    ??0CDbTransactionContext@@QEAA@XZ; CDbTransactionContext::CDbTransactionContext(void)
0x1800ea1cd  mov     edx, cs:lInitialCount; lInitialCount
0x1800ea1d3  xor     r9d, r9d; lpName
0x1800ea1d6  mov     r8d, edx; lMaximumCount
0x1800ea1d9  xor     ecx, ecx; lpSemaphoreAttributes
0x1800ea1db  call    cs:__imp_CreateSemaphoreW
0x1800ea1e1  mov     [rdi+28h], rax
0x1800ea1e5  test    rax, rax
0x1800ea1e8  jz      short loc_1800EA207
0x1800ea1ea  mov     edx, cs:lMaximumCount; lInitialCount
0x1800ea1f0  xor     r9d, r9d; lpName
0x1800ea1f3  mov     r8d, edx; lMaximumCount
0x1800ea1f6  xor     ecx, ecx; lpSemaphoreAttributes
0x1800ea1f8  call    cs:__imp_CreateSemaphoreW
0x1800ea1fe  mov     [rdi+30h], rax
0x1800ea202  test    rax, rax
0x1800ea205  jnz     short loc_1800EA231
0x1800ea207  call    cs:__imp_GetLastError
0x1800ea20d  mov     ebx, eax
0x1800ea20f  test    eax, eax
0x1800ea211  jle     short loc_1800EA21C
0x1800ea213  movzx   ebx, ax
0x1800ea216  or      ebx, 80070000h
0x1800ea21c  test    ebx, ebx
0x1800ea21e  jns     short loc_1800EA231
0x1800ea220  mov     rcx, rdi; this
0x1800ea223  call    ??_GGLOBAL_CONTEXT_STATE@@QEAAPEAXI@Z; GLOBAL_CONTEXT_STATE::`scalar deleting destructor'(uint)
0x1800ea228  jmp     short loc_1800EA22F
0x1800ea22a  mov     ebx, 8007000Eh
0x1800ea22f  xor     edi, edi
0x1800ea231  lea     rax, [rdi+38h]
0x1800ea235  mov     cs:lpCriticalSection, rdi
0x1800ea23c  mov     cs:?s_pNullTransactionContext@CDbTransactionContext@@0PEAV1@EA, rax; CDbTransactionContext * CDbTransactionContext::s_pNullTransactionContext
0x1800ea243  xor     eax, eax
0x1800ea245  xchg    eax, cs:dword_1801AFEF4
0x1800ea24b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ea252  cmp     rcx, rsi
0x1800ea255  jz      short loc_1800EA27D
0x1800ea257  test    byte ptr [rcx+1Ch], 4
0x1800ea25b  jz      short loc_1800EA27D
0x1800ea25d  mov     rcx, [rcx+10h]
0x1800ea261  lea     r9, aCdboperationma_3; "CDbOperationManager::InitializeGlobalCo"...
0x1800ea268  mov     edx, 0Bh
0x1800ea26d  mov     [rsp+38h+var_18], ebx
0x1800ea271  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800ea278  call    WPP_SF_sD
0x1800ea27d  mov     rsi, [rsp+38h+arg_10]
0x1800ea282  mov     eax, ebx
0x1800ea284  mov     rbx, [rsp+38h+arg_8]
0x1800ea289  add     rsp, 30h
0x1800ea28d  pop     rdi
0x1800ea28e  retn
```
