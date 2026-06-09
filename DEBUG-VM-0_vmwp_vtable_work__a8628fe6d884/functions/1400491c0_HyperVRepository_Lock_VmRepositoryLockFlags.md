# HyperVRepository::Lock(VmRepositoryLockFlags)

- ea: `0x1400491c0`
- end: `0x140049407`
- name: `?Lock@HyperVRepository@@UEAAJW4VmRepositoryLockFlags@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400b499c`

## callees

- `0x14002dd68`
- `0x1400491c0`
- `0x14004965c`
- `0x140052030`
- `0x14006af38`
- `0x14008c964`
- `0x14009d7ac`
- `0x1400b42b0`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004929a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400493b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004929a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400493b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004938c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004938c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400491f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400491f4`

## string_xrefs

- `0x14004927e`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140049315`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140049331`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x140049361`: `onecore\vm\common\repository\core\hypervrepository.cpp`
- `0x1400493d6`: `onecore\vm\common\repository\core\hypervrepository.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HyperVRepository::Lock(__int64 a1, char a2)
{
  char v4; // al
  unsigned int TimeRemaining; // eax
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+28h] [rbp-50h]
  char v14; // [rsp+30h] [rbp-48h]
  int v15; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  try
  {
    if ( *(_QWORD *)(a1 + 104) )
    {
      v12[0] = *(_DWORD *)(a1 + 148);
      v12[1] = GetTickCount();
      Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(a1 + 112));
      v13 = a1 + 112;
      v4 = 1;
      v14 = 1;
      while ( v4 )
      {
        while ( *(_DWORD *)(a1 + 140)
             && !HyperVRepository::ThreadHoldsExclusiveLock((HyperVRepository *)a1)
             && ((a2 & 1) != 0 || *(_DWORD *)(a1 + 140) != 1) )
        {
          TimeRemaining = Vml::VmTimeoutTimer::GetTimeRemaining((Vml::VmTimeoutTimer *)v12);
          if ( !Vml::VmConditionVariable::Sleep(
                  (Vml::VmConditionVariable *)(a1 + 128),
                  (struct Vml::VmSlimReaderWriterLock *)(a1 + 112),
                  1,
                  TimeRemaining) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E1,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)0x800705B4LL,
              v12[0]);
            *(_DWORD *)(a1 + 120) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 112));
            return 2147943860LL;
          }
        }
        if ( !*(_DWORD *)(a1 + 136) )
        {
          v15 = 0;
          if ( (*(int (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 104) + 264LL))(*(_QWORD *)(a1 + 104), &v15) >= 0 )
          {
            v9 = v15;
          }
          else
          {
            v9 = 0;
            v15 = 0;
          }
          if ( !v9 )
          {
            if ( !*(_DWORD *)(a1 + 152) )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x1FA,
                (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                (const char *)0x37,
                v12[0]);
            v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 336LL))(*(_QWORD *)(a1 + 104));
            if ( v10 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1F6,
                (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                (const char *)(unsigned int)v10,
                v12[0]);
          }
          LOBYTE(v8) = a2 & 1;
          v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 32LL))(*(_QWORD *)(a1 + 104), v8);
          if ( v11 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1FE,
              (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
              (const char *)(unsigned int)v11,
              v12[0]);
          if ( (a2 & 1) != 0 )
          {
            *(_DWORD *)(a1 + 140) = -1;
            *(_DWORD *)(a1 + 144) = GetCurrentThreadId();
          }
          else
          {
            *(_DWORD *)(a1 + 140) = 1;
          }
        }
        ++*(_DWORD *)(a1 + 136);
        v4 = 0;
        v14 = 0;
      }
      *(_DWORD *)(a1 + 120) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 112));
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
        (const char *)0x8000FFFFLL,
        v12[0]);
      result = 2147549183LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x213,
                           (unsigned int)"onecore\\vm\\common\\repository\\core\\hypervrepository.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1400491c0  push    rbx
0x1400491c2  push    rsi
0x1400491c3  push    rdi
0x1400491c4  push    r14
0x1400491c6  sub     rsp, 58h
0x1400491ca  mov     rax, cs:__security_cookie
0x1400491d1  xor     rax, rsp
0x1400491d4  mov     [rsp+78h+var_38], rax
0x1400491d9  mov     r14d, edx
0x1400491dc  mov     rbx, rcx
0x1400491df  cmp     qword ptr [rcx+68h], 0
0x1400491e4  jz      loc_1400493C9
0x1400491ea  mov     eax, [rcx+94h]
0x1400491f0  mov     [rsp+78h+var_58], eax; int
0x1400491f4  call    cs:__imp_GetTickCount
0x1400491fb  nop     dword ptr [rax+rax+00h]
0x140049200  mov     [rsp+78h+var_54], eax
0x140049204  lea     rdi, [rbx+70h]
0x140049208  mov     rcx, rdi; this
0x14004920b  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140049210  mov     [rsp+78h+var_50], rdi
0x140049215  mov     al, 1
0x140049217  mov     [rsp+78h+var_48], al
0x14004921b  test    al, al
0x14004921d  jz      loc_1400493AF
0x140049223  mov     esi, r14d
0x140049226  and     esi, 1
0x140049229  cmp     dword ptr [rbx+8Ch], 0
0x140049230  jz      short loc_1400492AD
0x140049232  mov     rcx, rbx; this
0x140049235  call    ?ThreadHoldsExclusiveLock@HyperVRepository@@UEBA_NXZ; HyperVRepository::ThreadHoldsExclusiveLock(void)
0x14004923a  test    al, al
0x14004923c  jnz     short loc_1400492AD
0x14004923e  test    esi, esi
0x140049240  jnz     short loc_14004924B
0x140049242  cmp     dword ptr [rbx+8Ch], 1
0x140049249  jz      short loc_1400492AD
0x14004924b  lea     rcx, [rsp+78h+var_58]; this
0x140049250  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x140049255  mov     r9d, eax; unsigned int
0x140049258  lea     rcx, [rbx+80h]; this
0x14004925f  mov     r8d, 1; int
0x140049265  mov     rdx, rdi; struct Vml::VmSlimReaderWriterLock *
0x140049268  call    ?Sleep@VmConditionVariable@Vml@@QEBAHAEAVVmSlimReaderWriterLock@2@HK@Z; Vml::VmConditionVariable::Sleep(Vml::VmSlimReaderWriterLock &,int,ulong)
0x14004926d  test    eax, eax
0x14004926f  jnz     short loc_140049229
0x140049271  mov     rcx, [rsp+78h]; this
0x140049276  mov     ebx, 800705B4h
0x14004927b  mov     r9d, ebx; char *
0x14004927e  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x140049285  mov     edx, 1E1h; void *
0x14004928a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004928f  nop
0x140049290  mov     dword ptr [rdi+8], 0
0x140049297  mov     rcx, rdi; SRWLock
0x14004929a  call    cs:__imp_ReleaseSRWLockExclusive
0x1400492a1  nop     dword ptr [rax+rax+00h]
0x1400492a6  mov     eax, ebx
0x1400492a8  jmp     loc_1400493EF
0x1400492ad  cmp     dword ptr [rbx+88h], 0
0x1400492b4  jnz     loc_14004939E
0x1400492ba  mov     [rsp+78h+var_40], 0
0x1400492c2  mov     rcx, [rbx+68h]
0x1400492c6  mov     rax, [rcx]
0x1400492c9  lea     rdx, [rsp+78h+var_40]
0x1400492ce  mov     rax, [rax+108h]
0x1400492d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400492da  test    eax, eax
0x1400492dc  jns     short loc_1400492E6
0x1400492de  xor     eax, eax
0x1400492e0  mov     [rsp+78h+var_40], eax
0x1400492e4  jmp     short loc_1400492EA
0x1400492e6  mov     eax, [rsp+78h+var_40]
0x1400492ea  test    eax, eax
0x1400492ec  jnz     short loc_140049342
0x1400492ee  cmp     [rbx+98h], eax
0x1400492f4  jz      short loc_140049326
0x1400492f6  mov     rcx, [rbx+68h]
0x1400492fa  mov     rax, [rcx]
0x1400492fd  mov     rax, [rax+150h]
0x140049304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049309  mov     rcx, [rsp+78h]; this
0x14004930e  test    eax, eax
0x140049310  jns     short loc_140049342
0x140049312  mov     r9d, eax; char *
0x140049315  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x14004931c  mov     edx, 1F6h; void *
0x140049321  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140049326  mov     rcx, [rsp+78h]; this
0x14004932b  mov     r9d, 37h ; '7'; char *
0x140049331  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x140049338  mov     edx, 1FAh; void *
0x14004933d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140049342  mov     rcx, [rbx+68h]
0x140049346  mov     rax, [rcx]
0x140049349  mov     dl, sil
0x14004934c  mov     rax, [rax+20h]
0x140049350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049355  mov     rcx, [rsp+78h]; this
0x14004935a  test    eax, eax
0x14004935c  jns     short loc_140049372
0x14004935e  mov     r9d, eax; char *
0x140049361  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x140049368  mov     edx, 1FEh; void *
0x14004936d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140049372  test    esi, esi
0x140049374  jnz     short loc_140049382
0x140049376  mov     dword ptr [rbx+8Ch], 1
0x140049380  jmp     short loc_14004939E
0x140049382  mov     dword ptr [rbx+8Ch], 0FFFFFFFFh
0x14004938c  call    cs:__imp_GetCurrentThreadId
0x140049393  nop     dword ptr [rax+rax+00h]
0x140049398  mov     [rbx+90h], eax
0x14004939e  inc     dword ptr [rbx+88h]
0x1400493a4  xor     al, al
0x1400493a6  mov     [rsp+78h+var_48], al
0x1400493aa  jmp     loc_14004921B
0x1400493af  mov     dword ptr [rdi+8], 0
0x1400493b6  mov     rcx, rdi; SRWLock
0x1400493b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400493c0  nop     dword ptr [rax+rax+00h]
0x1400493c5  xor     eax, eax
0x1400493c7  jmp     short loc_1400493EF
0x1400493c9  mov     rcx, [rsp+78h]; this
0x1400493ce  mov     ebx, 8000FFFFh
0x1400493d3  mov     r9d, ebx; char *
0x1400493d6  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\repository\\core\\"...
0x1400493dd  mov     edx, 1C4h; void *
0x1400493e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400493e7  mov     eax, ebx
0x1400493e9  jmp     short loc_1400493EF
0x1400493eb  mov     eax, [rsp+78h+var_40]
0x1400493ef  mov     rcx, [rsp+78h+var_38]
0x1400493f4  xor     rcx, rsp; StackCookie
0x1400493f7  call    __security_check_cookie
0x1400493fc  add     rsp, 58h
0x140049400  pop     r14
0x140049402  pop     rdi
0x140049403  pop     rsi
0x140049404  pop     rbx
0x140049405  retn
```
