# CApplication::ProcessPendingSoundLevelNotification(void)

- ea: `0x180018660`
- end: `0x18001871e`
- name: `?ProcessPendingSoundLevelNotification@CApplication@@IEAAXXZ`
- size: `190`
- prototype: `void __fastcall(CApplication *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018d00`

## callees

- `0x180018204`
- `0x180018660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001867c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001867c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800186b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018709`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800186b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018709`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800186df`

## pseudocode

```c
void __fastcall CApplication::ProcessPendingSoundLevelNotification(CApplication *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  DWORD CurrentThreadId; // eax
  unsigned int v4; // esi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 280);
  while ( 1 )
  {
    EnterCriticalSection(v2);
    if ( *((_DWORD *)this + 80) )
    {
      if ( *((_DWORD *)this + 80) != GetCurrentThreadId() )
        break;
    }
    if ( *((_DWORD *)this + 81) == *((_DWORD *)this + 82) && !*((_DWORD *)this + 171) )
    {
      *((_DWORD *)this + 80) = 0;
      if ( !v2 )
        return;
      goto LABEL_6;
    }
    CurrentThreadId = GetCurrentThreadId();
    v4 = *((_DWORD *)this + 81);
    *((_DWORD *)this + 80) = CurrentThreadId;
    *((_DWORD *)this + 82) = v4;
    *((_DWORD *)this + 171) = 0;
    if ( v2 )
      LeaveCriticalSection(v2);
    CApplication::SendSoundLevelNotification(this, v4);
  }
  if ( v2 )
LABEL_6:
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180018660  mov     [rsp+arg_8], rbx
0x180018665  push    rdi
0x180018666  sub     rsp, 20h
0x18001866a  mov     rbx, rcx
0x18001866d  mov     [rsp+28h+arg_0], rsi
0x180018672  lea     rdi, [rcx+118h]
0x180018679  mov     rcx, rdi; lpCriticalSection
0x18001867c  call    cs:__imp_EnterCriticalSection
0x180018682  cmp     dword ptr [rbx+140h], 0
0x180018689  jnz     short loc_1800186CA
0x18001868b  mov     eax, [rbx+148h]
0x180018691  cmp     [rbx+144h], eax
0x180018697  jnz     short loc_1800186DF
0x180018699  cmp     dword ptr [rbx+2ACh], 0
0x1800186a0  jnz     short loc_1800186DF
0x1800186a2  mov     dword ptr [rbx+140h], 0
0x1800186ac  test    rdi, rdi
0x1800186af  jz      short loc_1800186BA
0x1800186b1  mov     rcx, rdi; lpCriticalSection
0x1800186b4  call    cs:__imp_LeaveCriticalSection
0x1800186ba  mov     rsi, [rsp+28h+arg_0]
0x1800186bf  mov     rbx, [rsp+28h+arg_8]
0x1800186c4  add     rsp, 20h
0x1800186c8  pop     rdi
0x1800186c9  retn
0x1800186ca  call    cs:__imp_GetCurrentThreadId
0x1800186d0  cmp     [rbx+140h], eax
0x1800186d6  jz      short loc_18001868B
0x1800186d8  test    rdi, rdi
0x1800186db  jz      short loc_1800186BA
0x1800186dd  jmp     short loc_1800186B1
0x1800186df  call    cs:__imp_GetCurrentThreadId
0x1800186e5  mov     esi, [rbx+144h]
0x1800186eb  mov     [rbx+140h], eax
0x1800186f1  mov     [rbx+148h], esi
0x1800186f7  mov     dword ptr [rbx+2ACh], 0
0x180018701  test    rdi, rdi
0x180018704  jz      short loc_18001870F
0x180018706  mov     rcx, rdi; lpCriticalSection
0x180018709  call    cs:__imp_LeaveCriticalSection
0x18001870f  mov     edx, esi
0x180018711  mov     rcx, rbx
0x180018714  call    ?SendSoundLevelNotification@CApplication@@IEAAXW4__MIDL___MIDL_itf_audiosrv_0000_0000_0004@@@Z; CApplication::SendSoundLevelNotification(__MIDL___MIDL_itf_audiosrv_0000_0000_0004)
0x180018719  jmp     loc_180018679
```
