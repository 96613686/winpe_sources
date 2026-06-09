# CUpgradeDiagnostics::ResetTimer(void)

- ea: `0x180025e48`
- end: `0x180025eb1`
- name: `?ResetTimer@CUpgradeDiagnostics@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CUpgradeDiagnostics *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800299a0`
- `0x180029a3c`
- `0x180029ad4`
- `0x180043290`
- `0x1800473f4`

## callees

- `0x180012e80`
- `0x180025e48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e72`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025e9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025e9d`

## pseudocode

```c
void __fastcall CUpgradeDiagnostics::ResetTimer(struct _TP_TIMER **this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(this + 2);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 2));
  v3 = *this;
  if ( *this && !*((_BYTE *)this + 8) )
  {
    pftDueTime = (struct _FILETIME)-300000000LL;
    SetThreadpoolTimer(v3, &pftDueTime, 0, 0);
    AudMigLibSetupLog(L"Migration diagnostics reset due to activity\r\n");
  }
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180025e48  mov     [rsp+arg_8], rbx
0x180025e4d  push    rdi
0x180025e4e  sub     rsp, 20h
0x180025e52  lea     rbx, [rcx+10h]
0x180025e56  mov     rdi, rcx
0x180025e59  mov     rcx, rbx; lpCriticalSection
0x180025e5c  call    cs:__imp_EnterCriticalSection
0x180025e62  mov     rcx, [rdi]; pti
0x180025e65  test    rcx, rcx
0x180025e68  jnz     short loc_180025E83
0x180025e6a  test    rbx, rbx
0x180025e6d  jz      short loc_180025E78
0x180025e6f  mov     rcx, rbx; lpCriticalSection
0x180025e72  call    cs:__imp_LeaveCriticalSection
0x180025e78  mov     rbx, [rsp+28h+arg_8]
0x180025e7d  add     rsp, 20h
0x180025e81  pop     rdi
0x180025e82  retn
0x180025e83  cmp     byte ptr [rdi+8], 0
0x180025e87  jnz     short loc_180025E6A
0x180025e89  xor     r9d, r9d; msWindowLength
0x180025e8c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x180025e95  xor     r8d, r8d; msPeriod
0x180025e98  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180025e9d  call    cs:__imp_SetThreadpoolTimer
0x180025ea3  lea     rcx, aMigrationDiagn_0; "Migration diagnostics reset due to acti"...
0x180025eaa  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x180025eaf  jmp     short loc_180025E6A
```
