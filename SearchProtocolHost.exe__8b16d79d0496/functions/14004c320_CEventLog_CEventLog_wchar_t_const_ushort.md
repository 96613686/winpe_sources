# CEventLog::CEventLog(wchar_t const *,ushort)

- ea: `0x14004c320`
- end: `0x14004c3a3`
- name: `??0CEventLog@@QEAA@PEB_WG@Z`
- size: `131`
- prototype: `CEventLog *__fastcall(CEventLog *__hidden this, const wchar_t *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400446b0`

## callees

- `0x140006bbc`
- `0x140015958`
- `0x14003178c`
- `0x14004c320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c356`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c356`
- `ext-ms-win-advapi32-eventlog-l1-1-0!RegisterEventSourceW` at `0x14004c348`
- `ext-ms-win-advapi32-eventlog-l1-1-0!RegisterEventSourceW` at `0x14004c348`

## string_xrefs

- `0x14004c33f`: `Windows Search Service`
- `0x14004c377`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\eventlog.cxx"`
- `0x14004c388`: `onecoreuap\base\appmodel\search\common\pkmutild\eventlog.cxx`

## pseudocode

```c
CEventLog *__fastcall CEventLog::CEventLog(CEventLog *this, const wchar_t *a2)
{
  HANDLE v3; // rax
  signed int LastError; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_WORD *)this + 4) = 3;
  if ( (unsigned __int8)IsDeregisterEventSourcePresent(this, a2) )
  {
    v3 = RegisterEventSourceW(0, L"Windows Search Service");
    *(_QWORD *)this = v3;
    if ( !v3 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmutild\\\\eventlog.cxx\"",
        (const wchar_t *)0x24,
        (unsigned int)L"[EventLog] EventLog could not be registered! Error 0x%08x",
        (const wchar_t *)(unsigned int)LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\eventlog.cxx",
        v5);
    }
  }
  return this;
}

```

## disassembly

```asm
0x14004c320  push    rbx
0x14004c322  sub     rsp, 20h
0x14004c326  mov     rbx, rcx
0x14004c329  mov     qword ptr [rcx], 0
0x14004c330  mov     word ptr [rcx+8], 3
0x14004c336  call    IsDeregisterEventSourcePresent
0x14004c33b  test    al, al
0x14004c33d  jz      short loc_14004C39A
0x14004c33f  lea     rdx, SourceName; "Windows Search Service"
0x14004c346  xor     ecx, ecx; lpUNCServerName
0x14004c348  call    cs:__imp_RegisterEventSourceW
0x14004c34e  mov     [rbx], rax
0x14004c351  test    rax, rax
0x14004c354  jnz     short loc_14004C39A
0x14004c356  call    cs:__imp_GetLastError
0x14004c35c  test    eax, eax
0x14004c35e  jle     short loc_14004C368
0x14004c360  movzx   eax, ax
0x14004c363  or      eax, 80070000h
0x14004c368  mov     r9d, eax; wchar_t *
0x14004c36b  lea     r8, aEventlogEventl; "[EventLog] EventLog could not be regist"...
0x14004c372  mov     edx, 24h ; '$'; wchar_t *
0x14004c377  lea     rcx, aOnecoreuapBase_16; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14004c37e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14004c383  mov     rcx, [rsp+28h]; this
0x14004c388  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004c38f  mov     edx, 25h ; '%'; void *
0x14004c394  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14004c39a  mov     rax, rbx
0x14004c39d  add     rsp, 20h
0x14004c3a1  pop     rbx
0x14004c3a2  retn
```
