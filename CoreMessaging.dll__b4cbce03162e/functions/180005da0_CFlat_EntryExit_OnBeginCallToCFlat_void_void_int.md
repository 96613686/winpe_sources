# CFlat::EntryExit::OnBeginCallToCFlat(void *,void *,int)

- ea: `0x180005da0`
- end: `0x18000604b`
- name: `?OnBeginCallToCFlat@EntryExit@CFlat@@SAJPEAX0H@Z`
- size: `683`
- prototype: `__int64 __fastcall(void *, void *, int)`
- caller_count: `132`
- callee_count: `7`
- tags: ``

## callers

- `0x180005030`
- `0x180005110`
- `0x180005920`
- `0x180005b40`
- `0x1800196c4`
- `0x18001e760`
- `0x180021920`
- `0x180021c60`
- `0x180032e30`
- `0x180033940`
- `0x180043160`
- `0x180043250`
- `0x180046080`
- `0x180047540`
- `0x180047a70`
- `0x180048ad0`
- `0x180048c10`
- `0x180048fd0`
- `0x180049800`
- `0x1800499f0`
- `0x18004a060`
- `0x18004a540`
- `0x18004c6d0`
- `0x18004cce0`
- `0x18004e860`
- `0x18005bc90`
- `0x18006d3c0`
- `0x18006d580`
- `0x18006d6b0`
- `0x18006da10`
- `0x18006db80`
- `0x18006dc50`
- `0x18006ddd0`
- `0x18006e050`
- `0x18006e440`
- `0x18006e510`
- `0x18006e720`
- `0x18006e890`
- `0x18006e9c0`
- `0x18006eb00`
- `0x18006ec80`
- `0x18006ee20`
- `0x18006efb0`
- `0x18006f0d0`
- `0x18006f1c0`
- `0x18006f360`
- `0x18006f450`
- `0x18006f5f0`
- `0x18006f7b0`
- `0x18006f930`

## callees

- `0x180005da0`
- `0x1800089c0`
- `0x180020df8`
- `0x180024980`
- `0x18003950c`
- `0x18008ae1c`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005dfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005dfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005f00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000600e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000600e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005ffd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ff3`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005e76`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005e76`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e13`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e62`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005eb1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005ee3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005f19`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e13`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005e62`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005eb1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005ee3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005f19`

## pseudocode

```c
__int64 __fastcall CFlat::EntryExit::OnBeginCallToCFlat(const char16_t *a1, void *a2, int a3)
{
  struct Cn::Context *Value; // rdi
  char v6; // r14
  __int64 v7; // rsi
  int v8; // ecx
  int v9; // eax
  const char16_t *v10; // rcx
  const char16_t *v11; // rcx
  __int64 result; // rax
  Cn::Engine::Lock *v13; // rbx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  __int64 v17; // rax
  int v18; // ebx
  HANDLE CurrentThread; // rax
  int v20; // [rsp+60h] [rbp+18h] BYREF

  v20 = a3;
  if ( !Cn::Context::s_fTypeIsInitialized )
    CFlat::Abandonment::Fail(a1, a2);
  if ( a1 && *((_BYTE *)a1 + 79) && TlsGetValue(Cn::Context::s_tlsStorage) == a1 )
    return 0;
  Value = (struct Cn::Context *)a1;
  v6 = 0;
LABEL_4:
  if ( !Value )
    goto LABEL_24;
  while ( 1 )
  {
    v7 = *((_QWORD *)Value + 11);
    if ( v7 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      v8 = *(_DWORD *)(v7 + 60);
      *(_DWORD *)(v7 + 60) = v8 + 1;
      if ( !v8 )
      {
        *(_QWORD *)(v7 + 64) = TlsGetValue(Cn::Context::s_tlsStorage);
        *(_DWORD *)(v7 + 72) = GetCurrentThreadId();
      }
      v6 = 1;
    }
    v9 = *((_DWORD *)Value + 18);
    if ( !v9 )
    {
      if ( a1 && Value != (struct Cn::Context *)a1 )
        CFlat::Abandonment::FailWithHR(-2018443006, a2, -2018443006);
      if ( v7 )
      {
        if ( TlsGetValue(Cn::Context::s_tlsStorage) )
          CFlat::Abandonment::Fail(v10);
        if ( TlsGetValue(Cn::Context::s_tlsStorage) != Value && !TlsSetValue(Cn::Context::s_tlsStorage, Value) )
          CFlat::Abandonment::Fail(v11);
        _InterlockedIncrement((volatile signed __int32 *)Value + 2);
      }
      return 0;
    }
    if ( v9 == 2 )
      break;
    if ( v6 )
    {
      Cn::Engine::Lock::Leave((Cn::Engine::Lock *)v7);
      v6 = 0;
    }
LABEL_24:
    if ( a1 )
      goto LABEL_4;
    Value = (struct Cn::Context *)TlsGetValue(Cn::Context::s_tlsStorage);
    if ( Value )
      goto LABEL_4;
    v13 = Cn::Context::s_lockType;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)Cn::Context::s_lockType + 16));
    v14 = *((_DWORD *)v13 + 15);
    *((_DWORD *)v13 + 15) = v14 + 1;
    if ( !v14 )
    {
      *((_QWORD *)v13 + 8) = TlsGetValue(Cn::Context::s_tlsStorage);
      *((_DWORD *)v13 + 18) = GetCurrentThreadId();
    }
    CurrentThreadId = GetCurrentThreadId();
    for ( Value = Cn::Context::s_pctxHead; Value; Value = (struct Cn::Context *)*((_QWORD *)Value + 13) )
    {
      if ( *((_DWORD *)Value + 10) == CurrentThreadId )
        break;
    }
    if ( (*((_DWORD *)v13 + 15))-- == 1 )
    {
      *((_QWORD *)v13 + 8) = 0;
      *((_DWORD *)v13 + 18) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v13 + 16));
    if ( !Value )
    {
      result = 2276524289LL;
      v20 = -2018443007;
      if ( !Cn::Process::Host )
        return result;
      (*(void (__fastcall **)(struct Cn::ICnHost *, int *, void *))(*(_QWORD *)Cn::Process::Host + 48LL))(
        Cn::Process::Host,
        &v20,
        a2);
      result = (unsigned int)v20;
      if ( v20 < 0 )
        return result;
      goto LABEL_4;
    }
  }
  v17 = *((_QWORD *)Value + 12);
  if ( v17 )
    v18 = *(_DWORD *)(v17 + 152);
  else
    v18 = 0;
  if ( v18 != GetCurrentThreadId() )
  {
    CurrentThread = GetCurrentThread();
    WaitForSingleObjectEx(CurrentThread, 0x7530u, 0);
  }
  if ( Cn::Process::Host )
    (*(void (__fastcall **)(struct Cn::ICnHost *, void *))(*(_QWORD *)Cn::Process::Host + 56LL))(Cn::Process::Host, a2);
  CFlat::EntryExit::OnEndCallToCFlat(Value);
  return 2276524291LL;
}

```

## disassembly

```asm
0x180005da0  mov     [rsp+arg_8], rbx
0x180005da5  mov     [rsp+arg_18], rbp
0x180005daa  mov     [rsp+arg_10], r8d
0x180005daf  push    rsi
0x180005db0  push    rdi
0x180005db1  push    r12
0x180005db3  push    r14
0x180005db5  push    r15
0x180005db7  sub     rsp, 20h
0x180005dbb  mov     r15, rdx
0x180005dbe  mov     rbp, rcx
0x180005dc1  cmp     cs:?s_fTypeIsInitialized@Context@Cn@@0_NA, 0; bool Cn::Context::s_fTypeIsInitialized
0x180005dc8  jz      loc_180005FB4
0x180005dce  test    rcx, rcx
0x180005dd1  jnz     loc_180005EA1
0x180005dd7  mov     rdi, rbp
0x180005dda  xor     esi, esi
0x180005ddc  xor     r14b, r14b
0x180005ddf  test    rdi, rdi
0x180005de2  jz      loc_180005ED4
0x180005de8  test    r14b, r14b
0x180005deb  jnz     short loc_180005E29
0x180005ded  mov     rsi, [rdi+58h]
0x180005df1  test    rsi, rsi
0x180005df4  jz      short loc_180005E29
0x180005df6  lea     rcx, [rsi+10h]; lpCriticalSection
0x180005dfa  call    cs:__imp_EnterCriticalSection
0x180005e00  mov     ecx, [rsi+3Ch]
0x180005e03  lea     eax, [rcx+1]
0x180005e06  mov     [rsi+3Ch], eax
0x180005e09  test    ecx, ecx
0x180005e0b  jnz     short loc_180005E26
0x180005e0d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005e13  call    cs:__imp_TlsGetValue
0x180005e19  mov     [rsi+40h], rax
0x180005e1d  call    cs:__imp_GetCurrentThreadId
0x180005e23  mov     [rsi+48h], eax
0x180005e26  mov     r14b, 1
0x180005e29  mov     eax, [rdi+48h]
0x180005e2c  test    eax, eax
0x180005e2e  jnz     loc_180005FD2
0x180005e34  test    rbp, rbp
0x180005e37  jz      short loc_180005E42
0x180005e39  cmp     rdi, rbp
0x180005e3c  jnz     loc_180005FBA
0x180005e42  test    rsi, rsi
0x180005e45  jz      short loc_180005E88
0x180005e47  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005e4d  call    cs:__imp_TlsGetValue
0x180005e53  test    rax, rax
0x180005e56  jnz     loc_180005FCC
0x180005e5c  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005e62  call    cs:__imp_TlsGetValue
0x180005e68  cmp     rax, rdi
0x180005e6b  jz      short loc_180005E84
0x180005e6d  mov     rdx, rdi; lpTlsValue
0x180005e70  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005e76  call    cs:__imp_TlsSetValue
0x180005e7c  test    eax, eax
0x180005e7e  jz      loc_180006045
0x180005e84  lock inc dword ptr [rdi+8]
0x180005e88  xor     eax, eax
0x180005e8a  mov     rbx, [rsp+48h+arg_8]
0x180005e8f  mov     rbp, [rsp+48h+arg_18]
0x180005e94  add     rsp, 20h
0x180005e98  pop     r15
0x180005e9a  pop     r14
0x180005e9c  pop     r12
0x180005e9e  pop     rdi
0x180005e9f  pop     rsi
0x180005ea0  retn
0x180005ea1  cmp     byte ptr [rcx+4Fh], 0
0x180005ea5  jz      loc_180005DD7
0x180005eab  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005eb1  call    cs:__imp_TlsGetValue
0x180005eb7  cmp     rax, rbp
0x180005eba  jnz     loc_180005DD7
0x180005ec0  jmp     short loc_180005E88
0x180005ec2  test    r14b, r14b
0x180005ec5  jz      short loc_180005ED4
0x180005ec7  mov     rcx, rsi; this
0x180005eca  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x180005ecf  xor     esi, esi
0x180005ed1  xor     r14b, r14b
0x180005ed4  test    rbp, rbp
0x180005ed7  jnz     loc_180005DDF
0x180005edd  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005ee3  call    cs:__imp_TlsGetValue
0x180005ee9  mov     rdi, rax
0x180005eec  test    rax, rax
0x180005eef  jnz     loc_180005DDF
0x180005ef5  mov     rbx, cs:?s_lockType@Context@Cn@@0V?$SmartPtr@VLock@Engine@Cn@@@CFlat@@A; CFlat::SmartPtr<Cn::Engine::Lock> Cn::Context::s_lockType
0x180005efc  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005f00  call    cs:__imp_EnterCriticalSection
0x180005f06  mov     ecx, [rbx+3Ch]
0x180005f09  lea     eax, [rcx+1]
0x180005f0c  mov     [rbx+3Ch], eax
0x180005f0f  test    ecx, ecx
0x180005f11  jnz     short loc_180005F2C
0x180005f13  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x180005f19  call    cs:__imp_TlsGetValue
0x180005f1f  mov     [rbx+40h], rax
0x180005f23  call    cs:__imp_GetCurrentThreadId
0x180005f29  mov     [rbx+48h], eax
0x180005f2c  call    cs:__imp_GetCurrentThreadId
0x180005f32  mov     rdi, cs:?s_pctxHead@Context@Cn@@0PEAV12@EA; Cn::Context * Cn::Context::s_pctxHead
0x180005f39  test    rdi, rdi
0x180005f3c  jz      short loc_180005F4E
0x180005f3e  xchg    ax, ax
0x180005f40  cmp     [rdi+28h], eax
0x180005f43  jz      short loc_180005F4E
0x180005f45  mov     rdi, [rdi+68h]
0x180005f49  test    rdi, rdi
0x180005f4c  jnz     short loc_180005F40
0x180005f4e  add     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x180005f52  jnz     short loc_180005F63
0x180005f54  mov     qword ptr [rbx+40h], 0
0x180005f5c  mov     dword ptr [rbx+48h], 0
0x180005f63  lea     rcx, [rbx+10h]; lpCriticalSection
0x180005f67  call    cs:__imp_LeaveCriticalSection
0x180005f6d  test    rdi, rdi
0x180005f70  jnz     loc_180005DE8
0x180005f76  mov     eax, 87B10101h
0x180005f7b  mov     [rsp+48h+arg_10], eax
0x180005f7f  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x180005f86  test    rcx, rcx
0x180005f89  jz      loc_180005E8A
0x180005f8f  mov     rax, [rcx]
0x180005f92  mov     r8, r15
0x180005f95  lea     rdx, [rsp+48h+arg_10]
0x180005f9a  mov     rax, [rax+30h]
0x180005f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa3  mov     eax, [rsp+48h+arg_10]
0x180005fa7  test    eax, eax
0x180005fa9  js      loc_180005E8A
0x180005faf  jmp     loc_180005DDF
0x180005fb4  call    ?Fail@Abandonment@CFlat@@SAXPEB_SPEAX@Z; CFlat::Abandonment::Fail(char16_t const *,void *)
0x180005fba  mov     r8d, 87B10102h; int
0x180005fc0  mov     rdx, r15; void *
0x180005fc3  mov     ecx, r8d; int
0x180005fc6  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180005fcc  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180005fd2  sub     eax, 1
0x180005fd5  jz      loc_180005EC2
0x180005fdb  cmp     eax, 1
0x180005fde  jnz     loc_180005EC2
0x180005fe4  mov     rax, [rdi+60h]
0x180005fe8  test    rax, rax
0x180005feb  jz      short loc_180006041
0x180005fed  mov     ebx, [rax+98h]
0x180005ff3  call    cs:__imp_GetCurrentThreadId
0x180005ff9  cmp     ebx, eax
0x180005ffb  jz      short loc_180006014
0x180005ffd  call    cs:__imp_GetCurrentThread
0x180006003  mov     rcx, rax; hHandle
0x180006006  xor     r8d, r8d; bAlertable
0x180006009  mov     edx, 7530h; dwMilliseconds
0x18000600e  call    cs:__imp_WaitForSingleObjectEx
0x180006014  mov     rcx, cs:?Host@Process@Cn@@2PEAUICnHost@2@EA; Cn::ICnHost * Cn::Process::Host
0x18000601b  test    rcx, rcx
0x18000601e  jz      short loc_18000602F
0x180006020  mov     rax, [rcx]
0x180006023  mov     rdx, r15
0x180006026  mov     rax, [rax+38h]
0x18000602a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602f  mov     rcx, rdi; void *
0x180006032  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x180006037  mov     eax, 87B10103h
0x18000603c  jmp     loc_180005E8A
0x180006041  xor     ebx, ebx
0x180006043  jmp     short loc_180005FF3
0x180006045  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
```
