# CEventLog::Report(ulong,ushort,ulong,wchar_t const * *,ulong,void *)

- ea: `0x140029520`
- end: `0x1400295f4`
- name: `?Report@CEventLog@@QEAAXKGKPEAPEB_WKPEAX@Z`
- size: `212`
- prototype: `void(CEventLog *__hidden this, unsigned int, unsigned __int16, unsigned int, const wchar_t **, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140029fc8`

## callees

- `0x140005220`
- `0x14001d4e8`
- `0x14001e440`
- `0x140029520`
- `0x1400295fc`
- `0x14002a638`

## import_xrefs

- `ext-ms-win-advapi32-eventlog-l1-1-0!ReportEventW` at `0x1400295b1`
- `ext-ms-win-advapi32-eventlog-l1-1-0!ReportEventW` at `0x1400295b1`

## string_xrefs

- `0x140029551`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\eventlog.cxx"`
- `0x1400295d8`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\eventlog.cxx"`

## pseudocode

```c
void __fastcall CEventLog::Report(CEventLog *this, DWORD a2, __int64 a3, int a4, const wchar_t **lpStrings)
{
  WORD wNumStrings; // di
  CEventThrottleManager *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  BOOL v11; // ebx
  unsigned int Error; // eax

  wNumStrings = a4;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\eventlog.cxx\"",
    (const wchar_t *)0x3E,
    (unsigned int)L"[EventLog] CEventLog::Report() called; Severity 0x%04x, Category %d, Args %d",
    (const wchar_t *)1,
    *((unsigned __int16 *)this + 4),
    a4);
  if ( CEventThrottleManager::ShouldThrottle(v8, a2) || !(unsigned __int8)IsDeregisterEventSourcePresent(v10, v9) )
  {
    Error = -2147482633;
  }
  else
  {
    v11 = ReportEventW(*(HANDLE *)this, 1u, *((_WORD *)this + 4), a2, 0, wNumStrings, 0, lpStrings, 0);
    Error = ResultFromLastError();
    if ( v11 )
      return;
  }
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\eventlog.cxx\"",
    (const wchar_t *)0x62,
    (unsigned int)L"[EventLog] ReportEvent() Failed. 0x%08x",
    (const wchar_t *)Error);
}

```

## disassembly

```asm
0x140029520  mov     [rsp+arg_0], rbx
0x140029525  mov     [rsp+arg_8], rsi
0x14002952a  push    rdi
0x14002952b  sub     rsp, 50h
0x14002952f  movzx   eax, word ptr [rcx+8]
0x140029533  lea     r8, aEventlogCevent; "[EventLog] CEventLog::Report() called; "...
0x14002953a  mov     dword ptr [rsp+58h+wNumStrings], r9d
0x14002953f  mov     edi, r9d
0x140029542  mov     r9d, 1; wchar_t *
0x140029548  mov     dword ptr [rsp+58h+lpUserSid], eax
0x14002954c  mov     esi, edx
0x14002954e  mov     rbx, rcx
0x140029551  lea     rcx, aOnecoreuapBase_13; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140029558  lea     edx, [r9+3Dh]; wchar_t *
0x14002955c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x140029561  mov     edx, esi; unsigned int
0x140029563  call    ?ShouldThrottle@CEventThrottleManager@@QEAA_NK@Z; CEventThrottleManager::ShouldThrottle(ulong)
0x140029568  test    al, al
0x14002956a  jnz     short loc_1400295C4
0x14002956c  call    IsDeregisterEventSourcePresent
0x140029571  test    al, al
0x140029573  jz      short loc_1400295C4
0x140029575  mov     rax, [rsp+58h+arg_20]
0x14002957d  mov     edx, 1; wType
0x140029582  movzx   r8d, word ptr [rbx+8]; wCategory
0x140029587  mov     r9d, esi; dwEventID
0x14002958a  mov     rcx, [rbx]; hEventLog
0x14002958d  mov     [rsp+58h+lpRawData], 0; lpRawData
0x140029596  mov     [rsp+58h+lpStrings], rax; lpStrings
0x14002959b  mov     [rsp+58h+dwDataSize], 0; dwDataSize
0x1400295a3  mov     [rsp+58h+wNumStrings], di; wNumStrings
0x1400295a8  mov     [rsp+58h+lpUserSid], 0; lpUserSid
0x1400295b1  call    cs:__imp_ReportEventW
0x1400295b7  mov     ebx, eax
0x1400295b9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400295be  test    ebx, ebx
0x1400295c0  jnz     short loc_1400295E4
0x1400295c2  jmp     short loc_1400295C9
0x1400295c4  mov     eax, 800003F7h
0x1400295c9  mov     r9d, eax; wchar_t *
0x1400295cc  lea     r8, aEventlogReport; "[EventLog] ReportEvent() Failed. 0x%08x"
0x1400295d3  mov     edx, 62h ; 'b'; wchar_t *
0x1400295d8  lea     rcx, aOnecoreuapBase_13; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1400295df  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1400295e4  mov     rbx, [rsp+58h+arg_0]
0x1400295e9  mov     rsi, [rsp+58h+arg_8]
0x1400295ee  add     rsp, 50h
0x1400295f2  pop     rdi
0x1400295f3  retn
```
