# Cn::Context::CreateStage1(bool)

- ea: `0x18004ac98`
- end: `0x18004ad2e`
- name: `?CreateStage1@Context@Cn@@AEAAX_N@Z`
- size: `150`
- prototype: `void __fastcall(Cn::Context *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180049d98`

## callees

- `0x1800067f0`
- `0x180024980`
- `0x18004ac98`
- `0x18004baf0`
- `0x18004c11c`
- `0x18008ae1c`
- `0x18008f584`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ace5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ace5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004acc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004acc8`

## pseudocode

```c
void __fastcall Cn::Context::CreateStage1(Cn::Context *this, char a2)
{
  Cn::Engine::Lock *v2; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  DWORD CurrentThreadId; // eax
  const char16_t *v8; // rcx
  HANDLE ProcessHeap; // rax

  v2 = Cn::Context::s_lockType;
  Cn::Engine::Lock::Enter(Cn::Context::s_lockType);
  _InterlockedIncrement(&Cn::Context::s_cContexts);
  if ( a2 )
    CurrentThreadId = GetCurrentThreadId();
  else
    CurrentThreadId = 0;
  *((_DWORD *)this + 10) = CurrentThreadId;
  LOBYTE(v5) = 1;
  LOBYTE(v6) = 113;
  Cn::Engine::Lock::Create(v6, v5, (char *)this + 88);
  if ( *((_QWORD *)this + 7) )
    CFlat::Abandonment::Fail(v8);
  ProcessHeap = GetProcessHeap();
  *((_QWORD *)this + 7) = ProcessHeap;
  if ( !ProcessHeap )
    Cn::FailFast::ForWin32();
  if ( a2 )
    Cn::Context::AddContextNL(this);
  if ( v2 )
    Cn::Engine::Lock::Leave(v2);
}

```

## disassembly

```asm
0x18004ac98  mov     [rsp+arg_0], rbx
0x18004ac9d  mov     [rsp+arg_8], rsi
0x18004aca2  push    rdi
0x18004aca3  sub     rsp, 20h
0x18004aca7  mov     rbx, cs:?s_lockType@Context@Cn@@0V?$SmartPtr@VLock@Engine@Cn@@@CFlat@@A; CFlat::SmartPtr<Cn::Engine::Lock> Cn::Context::s_lockType
0x18004acae  mov     rdi, rcx
0x18004acb1  mov     rcx, rbx; this
0x18004acb4  mov     sil, dl
0x18004acb7  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x18004acbc  lock inc cs:?s_cContexts@Context@Cn@@0HA; int Cn::Context::s_cContexts
0x18004acc3  test    sil, sil
0x18004acc6  jz      short loc_18004AD24
0x18004acc8  call    cs:__imp_GetCurrentThreadId
0x18004acce  lea     r8, [rdi+58h]
0x18004acd2  mov     [rdi+28h], eax
0x18004acd5  mov     dl, 1
0x18004acd7  mov     cl, 71h ; 'q'
0x18004acd9  call    ?Create@Lock@Engine@Cn@@CAXULockPriority@23@_NPEAPEAV123@@Z; Cn::Engine::Lock::Create(Cn::Engine::LockPriority,bool,Cn::Engine::Lock * *)
0x18004acde  cmp     qword ptr [rdi+38h], 0
0x18004ace3  jnz     short loc_18004AD1E
0x18004ace5  call    cs:__imp_GetProcessHeap
0x18004aceb  mov     [rdi+38h], rax
0x18004acef  test    rax, rax
0x18004acf2  jz      short loc_18004AD28
0x18004acf4  test    sil, sil
0x18004acf7  jz      short loc_18004AD01
0x18004acf9  mov     rcx, rdi; struct Cn::Context *
0x18004acfc  call    ?AddContextNL@Context@Cn@@CAXPEAV12@@Z; Cn::Context::AddContextNL(Cn::Context *)
0x18004ad01  test    rbx, rbx
0x18004ad04  jz      short loc_18004AD0E
0x18004ad06  mov     rcx, rbx; this
0x18004ad09  call    ?Leave@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Leave(void)
0x18004ad0e  mov     rbx, [rsp+28h+arg_0]
0x18004ad13  mov     rsi, [rsp+28h+arg_8]
0x18004ad18  add     rsp, 20h
0x18004ad1c  pop     rdi
0x18004ad1d  retn
0x18004ad1e  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x18004ad24  xor     eax, eax
0x18004ad26  jmp     short loc_18004ACCE
0x18004ad28  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
```
