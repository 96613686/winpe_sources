# CMeasurerLS::GetPols(void)

- ea: `0x18002dd3c`
- end: `0x18002deda`
- name: `?GetPols@CMeasurerLS@@QEAAPEAUols@Ptls6@@XZ`
- size: `414`
- prototype: `struct Ptls6::ols *__fastcall(CMeasurerLS *__hidden this)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180018af0`
- `0x180059fac`
- `0x180080d3c`
- `0x1800810d8`
- `0x18008a9dc`
- `0x18018ee74`

## callees

- `0x18002af88`
- `0x18002d374`
- `0x18002dd3c`
- `0x18002dee0`
- `0x1800f4940`
- `0x180100cd4`
- `0x18013beb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002de4d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002de4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002de2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002de2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dd9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002de53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dd9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002de53`

## pseudocode

```c
struct Ptls6::ols *__fastcall CMeasurerLS::GetPols(CMeasurerLS *this)
{
  __int64 v2; // rdi
  __int64 v3; // rdi
  int v4; // ebx
  Ptls6::ols **v5; // rbx
  Ptls6::ols *v6; // rax
  unsigned int v7; // edx
  CMeasurerNoFC *v8; // rcx
  Ptls6::ols *v9; // rbx
  RTL_SRWLOCK *Lock; // rax
  DWORD CurrentThreadId; // eax
  Ptls6::ols *v13; // rax

  if ( !*(_QWORD *)this )
    return 0;
  v2 = *(_QWORD *)(*(_QWORD *)this + 16LL);
  if ( !v2 )
    return 0;
  v3 = *(_QWORD *)(v2 + 40);
  if ( !v3 || CLSLock::_fNoLS || (*(_BYTE *)(v3 + 358) & 1) == 0 )
    return 0;
  v4 = (int)CLockSharedData::LockOwner;
  if ( (_DWORD)CLockSharedData::LockOwner && v4 == GetCurrentThreadId() )
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
  v5 = (Ptls6::ols **)(v3 + 616);
  if ( (*(_DWORD *)(v3 + 184) & 0x40000000) == 0 )
    v5 = &CLSLock::_pols;
  v6 = *v5;
  if ( *v5 )
    goto LABEL_12;
  if ( (*(_DWORD *)(v3 + 184) & 0x40000000) != 0 )
  {
    *v5 = 0;
  }
  else
  {
    v13 = (Ptls6::ols *)operator new(0x420u);
    v6 = (Ptls6::ols *)Ptls6::ols::ols(v13);
    *v5 = v6;
    if ( v6 )
    {
LABEL_12:
      *((_OWORD *)this + 3) = *(_OWORD *)((char *)v6 + 56);
      *((_QWORD *)this + 8) = *((_QWORD *)v6 + 9);
      if ( (unsigned int)Ptls6::ols::Init(*v5, this) )
      {
        if ( (*(_DWORD *)(v3 + 184) & 0x40000000) == 0 && *v5 )
          Ptls6::ols::`scalar deleting destructor'(*v5, v7);
        *v5 = 0;
      }
      v8 = *(CMeasurerNoFC **)this;
      *((_QWORD *)this + 5) = *v5;
      CMeasurerNoFC::UpdatePF(v8);
    }
  }
  v9 = *v5;
  if ( (int)CLockSharedData::LockTelemetry > 0 )
  {
    LODWORD(CLockSharedData::LockTelemetry) = (_DWORD)CLockSharedData::LockTelemetry - 1;
  }
  else
  {
    LODWORD(CLockSharedData::LockOwner) = 0;
    ReleaseSRWLockExclusive(&SRW_RELock);
  }
  return v9;
}

```

## disassembly

```asm
0x18002dd3c  mov     [rsp+arg_0], rbx
0x18002dd41  mov     [rsp+arg_8], rsi
0x18002dd46  push    rdi
0x18002dd47  sub     rsp, 20h
0x18002dd4b  mov     rax, [rcx]
0x18002dd4e  mov     rsi, rcx
0x18002dd51  test    rax, rax
0x18002dd54  jz      loc_18002DE74
0x18002dd5a  mov     rdi, [rax+10h]
0x18002dd5e  test    rdi, rdi
0x18002dd61  jz      loc_18002DE74
0x18002dd67  mov     rdi, [rdi+28h]
0x18002dd6b  test    rdi, rdi
0x18002dd6e  jz      loc_18002DE74
0x18002dd74  cmp     cs:?_fNoLS@CLSLock@@1_NA, 0; bool CLSLock::_fNoLS
0x18002dd7b  jnz     loc_18002DE74
0x18002dd81  test    byte ptr [rdi+166h], 1
0x18002dd88  jz      loc_18002DE74
0x18002dd8e  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x18002dd94  test    ebx, ebx
0x18002dd96  jz      loc_18002DE43
0x18002dd9c  call    cs:__imp_GetCurrentThreadId
0x18002dda2  cmp     ebx, eax
0x18002dda4  jnz     loc_18002DE43
0x18002ddaa  inc     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002ddb0  mov     ecx, [rdi+0B8h]
0x18002ddb6  lea     rbx, [rdi+268h]
0x18002ddbd  shr     ecx, 1Eh
0x18002ddc0  and     cl, 1
0x18002ddc3  jnz     short loc_18002DDCC
0x18002ddc5  lea     rbx, ?_pols@CLSLock@@1PEAUols@Ptls6@@EA; Ptls6::ols * CLSLock::_pols
0x18002ddcc  mov     rax, [rbx]
0x18002ddcf  test    rax, rax
0x18002ddd2  jz      loc_18002DE78
0x18002ddd8  movups  xmm0, xmmword ptr [rax+38h]
0x18002dddc  mov     rdx, rsi; struct CMeasurerLS *
0x18002dddf  movups  xmmword ptr [rsi+30h], xmm0
0x18002dde3  movsd   xmm1, qword ptr [rax+48h]
0x18002dde8  movsd   qword ptr [rsi+40h], xmm1
0x18002dded  mov     rcx, [rbx]; this
0x18002ddf0  call    ?Init@ols@Ptls6@@QEAAJAEBVCMeasurerLS@@@Z; Ptls6::ols::Init(CMeasurerLS const &)
0x18002ddf5  test    eax, eax
0x18002ddf7  jnz     loc_18002DEB4
0x18002ddfd  mov     rax, [rbx]
0x18002de00  mov     rcx, [rsi]; this
0x18002de03  mov     [rsi+28h], rax
0x18002de07  call    ?UpdatePF@CMeasurerNoFC@@QEAAXXZ; CMeasurerNoFC::UpdatePF(void)
0x18002de0c  mov     eax, cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002de12  mov     rbx, [rbx]
0x18002de15  test    eax, eax
0x18002de17  jg      short loc_18002DE6A
0x18002de19  lea     rcx, ?SRW_RELock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18002de20  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, 0; uint near * CLockSharedData::LockOwner
0x18002de2a  call    cs:__imp_ReleaseSRWLockExclusive
0x18002de30  mov     rax, rbx
0x18002de33  mov     rbx, [rsp+28h+arg_0]
0x18002de38  mov     rsi, [rsp+28h+arg_8]
0x18002de3d  add     rsp, 20h
0x18002de41  pop     rdi
0x18002de42  retn
0x18002de43  xor     ecx, ecx
0x18002de45  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18002de4a  mov     rcx, rax; SRWLock
0x18002de4d  call    cs:__imp_AcquireSRWLockExclusive
0x18002de53  call    cs:__imp_GetCurrentThreadId
0x18002de59  inc     cs:dword_1802DF74C
0x18002de5f  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18002de65  jmp     loc_18002DDB0
0x18002de6a  dec     eax
0x18002de6c  mov     cs:?LockTelemetry@CLockSharedData@@2PAULOCK_TELEMETRY@@A, eax; LOCK_TELEMETRY near * CLockSharedData::LockTelemetry
0x18002de72  jmp     short loc_18002DE30
0x18002de74  xor     eax, eax
0x18002de76  jmp     short loc_18002DE33
0x18002de78  test    cl, cl
0x18002de7a  jnz     short loc_18002DEA8
0x18002de7c  test    rax, rax
0x18002de7f  jnz     loc_18002DDD8
0x18002de85  mov     ecx, 420h; Size
0x18002de8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002de8f  mov     rcx, rax; this
0x18002de92  call    ??0ols@Ptls6@@QEAA@XZ; Ptls6::ols::ols(void)
0x18002de97  mov     [rbx], rax
0x18002de9a  test    rax, rax
0x18002de9d  jz      loc_18002DE0C
0x18002dea3  jmp     loc_18002DDD8
0x18002dea8  mov     qword ptr [rbx], 0
0x18002deaf  jmp     loc_18002DE0C
0x18002deb4  mov     eax, [rdi+0B8h]
0x18002deba  shr     eax, 1Eh
0x18002debd  test    al, 1
0x18002debf  jnz     short loc_18002DECE
0x18002dec1  mov     rcx, [rbx]; this
0x18002dec4  test    rcx, rcx
0x18002dec7  jz      short loc_18002DECE
0x18002dec9  call    ??_Gols@Ptls6@@QEAAPEAXI@Z; Ptls6::ols::`scalar deleting destructor'(uint)
0x18002dece  mov     qword ptr [rbx], 0
0x18002ded5  jmp     loc_18002DDFD
```
