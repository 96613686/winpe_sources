# CHandlerCache::s_GetInstance(CHandlerCache * *,bool)

- ea: `0x180004c70`
- end: `0x180004dd7`
- name: `?s_GetInstance@CHandlerCache@@SAJPEAPEAV1@_N@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct CHandlerCache **, bool)`
- caller_count: `23`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800047d0`
- `0x1800113c8`
- `0x180011570`
- `0x180012050`
- `0x1800123d0`
- `0x180015e00`
- `0x180015e60`
- `0x18001f700`
- `0x1800204a4`
- `0x180020664`
- `0x1800207a4`
- `0x18002095c`
- `0x180020a48`
- `0x180020bbc`
- `0x180021550`
- `0x180021650`
- `0x1800216c0`
- `0x180021700`
- `0x180021770`
- `0x1800217b0`
- `0x180021890`
- `0x180021a78`
- `0x180023314`

## callees

- `0x180004c70`
- `0x180009940`
- `0x18000a5e4`
- `0x180012e54`
- `0x18001343c`
- `0x18001358c`
- `0x1800155a0`
- `0x180015af8`
- `0x180015f6c`
- `0x180052950`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180004d77`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180004d77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ce0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004ce0`

## pseudocode

```c
__int64 __fastcall CHandlerCache::s_GetInstance(struct CHandlerCache **a1, char a2, int a3)
{
  int Error; // edi
  CHandlerCache *v6; // rbx
  char v7; // bp
  struct _RTL_CRITICAL_SECTION *v8; // rax
  CHandlerCache *v9; // rax
  _BYTE v11[16]; // [rsp+30h] [rbp-48h] BYREF

  Error = 0;
  if ( (Microsoft_Windows_mobsyncEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)a1,
      (unsigned int)SyncMgrTraceId_HandlerCacheCreate_Start,
      a3,
      1,
      (__int64)v11);
  v6 = (CHandlerCache *)_InterlockedExchange64(
                          (volatile __int64 *)&CHandlerCache::s_pSelf,
                          (__int64)CHandlerCache::s_pSelf);
  if ( !v6 )
  {
    if ( a2 != 1 )
    {
      Error = -2147467259;
      goto LABEL_16;
    }
    v7 = 0;
    EnterCriticalSection(&g_DllCriticalSection);
    v6 = (CHandlerCache *)_InterlockedExchange64(
                            (volatile __int64 *)&CHandlerCache::s_pSelf,
                            (__int64)CHandlerCache::s_pSelf);
    if ( v6 )
      goto LABEL_12;
    Error = -2147024882;
    v8 = (struct _RTL_CRITICAL_SECTION *)operator new(0x1C0u);
    if ( v8 )
    {
      v9 = CHandlerCache::CHandlerCache(v8);
      v6 = v9;
      if ( !v9 )
      {
LABEL_12:
        LeaveCriticalSection(&g_DllCriticalSection);
        if ( v7 == 1 && !SHCreateThreadWithHandle((WCHAR)CHandlerCache::s_StaticWorkerThreadProc) )
        {
          Error = ResultFromKnownLastError();
          CHandlerCache::_Shutdown(v6);
        }
        goto LABEL_16;
      }
      Error = CHandlerCache::_Init(v9);
      if ( Error >= 0 )
      {
        _InterlockedExchange64((volatile __int64 *)&CHandlerCache::s_pSelf, (__int64)v6);
        v7 = 1;
        goto LABEL_12;
      }
      CHandlerCache::~CHandlerCache(v6);
      CZeroInitNew::operator delete(v6);
    }
    v6 = 0;
    goto LABEL_12;
  }
LABEL_16:
  *a1 = v6;
  if ( (Microsoft_Windows_mobsyncEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)a1,
      (unsigned int)SyncMgrTraceId_HandlerCacheCreate_Stop,
      a3,
      1,
      (__int64)v11);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180004c70  push    rbx
0x180004c72  push    rbp
0x180004c73  push    rsi
0x180004c74  push    rdi
0x180004c75  sub     rsp, 58h
0x180004c79  mov     rax, cs:__security_cookie
0x180004c80  xor     rax, rsp
0x180004c83  mov     [rsp+78h+var_38], rax
0x180004c88  xor     edi, edi
0x180004c8a  movzx   ebp, dl
0x180004c8d  test    cs:Microsoft_Windows_mobsyncEnableBits, 1
0x180004c94  mov     rsi, rcx
0x180004c97  jz      short loc_180004CB5
0x180004c99  lea     rax, [rsp+78h+var_48]
0x180004c9e  mov     r9d, 1
0x180004ca4  lea     rdx, SyncMgrTraceId_HandlerCacheCreate_Start
0x180004cab  mov     [rsp+78h+var_58], rax
0x180004cb0  call    McGenEventWrite_EtwEventWriteTransfer
0x180004cb5  mov     rbx, cs:?s_pSelf@CHandlerCache@@0PEAV1@EA; CHandlerCache * CHandlerCache::s_pSelf
0x180004cbc  xchg    rbx, cs:?s_pSelf@CHandlerCache@@0PEAV1@EA; CHandlerCache * CHandlerCache::s_pSelf
0x180004cc3  test    rbx, rbx
0x180004cc6  jnz     loc_180004D97
0x180004ccc  cmp     bpl, 1
0x180004cd0  jnz     loc_180004D92
0x180004cd6  lea     rcx, ?g_DllCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004cdd  xor     bpl, bpl
0x180004ce0  call    cs:__imp_EnterCriticalSection
0x180004ce6  mov     rbx, cs:?s_pSelf@CHandlerCache@@0PEAV1@EA; CHandlerCache * CHandlerCache::s_pSelf
0x180004ced  xchg    rbx, cs:?s_pSelf@CHandlerCache@@0PEAV1@EA; CHandlerCache * CHandlerCache::s_pSelf
0x180004cf4  test    rbx, rbx
0x180004cf7  jnz     short loc_180004D49
0x180004cf9  mov     ecx, 1C0h; unsigned __int64
0x180004cfe  mov     edi, 8007000Eh
0x180004d03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d08  test    rax, rax
0x180004d0b  jz      short loc_180004D47
0x180004d0d  mov     rcx, rax; lpCriticalSection
0x180004d10  call    ??0CHandlerCache@@AEAA@XZ; CHandlerCache::CHandlerCache(void)
0x180004d15  mov     rbx, rax
0x180004d18  test    rax, rax
0x180004d1b  jz      short loc_180004D49
0x180004d1d  mov     rcx, rax; this
0x180004d20  call    ?_Init@CHandlerCache@@AEAAJXZ; CHandlerCache::_Init(void)
0x180004d25  mov     edi, eax
0x180004d27  mov     rcx, rbx; lpCriticalSection
0x180004d2a  test    eax, eax
0x180004d2c  js      short loc_180004D3A
0x180004d2e  xchg    rcx, cs:?s_pSelf@CHandlerCache@@0PEAV1@EA; CHandlerCache * CHandlerCache::s_pSelf
0x180004d35  mov     bpl, 1
0x180004d38  jmp     short loc_180004D49
0x180004d3a  call    ??1CHandlerCache@@AEAA@XZ; CHandlerCache::~CHandlerCache(void)
0x180004d3f  mov     rcx, rbx; lpMem
0x180004d42  call    ??3CZeroInitNew@@SAXPEAX@Z; CZeroInitNew::operator delete(void *)
0x180004d47  xor     ebx, ebx
0x180004d49  lea     rcx, ?g_DllCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004d50  call    cs:__imp_LeaveCriticalSection
0x180004d56  cmp     bpl, 1
0x180004d5a  jnz     short loc_180004D97
0x180004d5c  lea     rax, [rbx+68h]
0x180004d60  xor     r9d, r9d
0x180004d63  xor     edx, edx
0x180004d65  mov     [rsp+78h+var_58], rax
0x180004d6a  mov     r8d, 8
0x180004d70  lea     rcx, ?s_StaticWorkerThreadProc@CHandlerCache@@CAKPEAX@Z; ch
0x180004d77  call    cs:__imp_SHCreateThreadWithHandle
0x180004d7d  test    eax, eax
0x180004d7f  jnz     short loc_180004D97
0x180004d81  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004d86  mov     rcx, rbx; this
0x180004d89  mov     edi, eax
0x180004d8b  call    ?_Shutdown@CHandlerCache@@AEAAXXZ; CHandlerCache::_Shutdown(void)
0x180004d90  jmp     short loc_180004D97
0x180004d92  mov     edi, 80004005h
0x180004d97  mov     [rsi], rbx
0x180004d9a  test    cs:Microsoft_Windows_mobsyncEnableBits, 1
0x180004da1  jz      short loc_180004DBF
0x180004da3  lea     rax, [rsp+78h+var_48]
0x180004da8  mov     r9d, 1
0x180004dae  lea     rdx, SyncMgrTraceId_HandlerCacheCreate_Stop
0x180004db5  mov     [rsp+78h+var_58], rax
0x180004dba  call    McGenEventWrite_EtwEventWriteTransfer
0x180004dbf  mov     eax, edi
0x180004dc1  mov     rcx, [rsp+78h+var_38]
0x180004dc6  xor     rcx, rsp; StackCookie
0x180004dc9  call    __security_check_cookie
0x180004dce  add     rsp, 58h
0x180004dd2  pop     rdi
0x180004dd3  pop     rsi
0x180004dd4  pop     rbp
0x180004dd5  pop     rbx
0x180004dd6  retn
```
