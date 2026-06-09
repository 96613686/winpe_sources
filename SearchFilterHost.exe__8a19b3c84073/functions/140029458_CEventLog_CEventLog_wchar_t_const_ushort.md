# CEventLog::CEventLog(wchar_t const *,ushort)

- ea: `0x140029458`
- end: `0x1400294db`
- name: `??0CEventLog@@QEAA@PEB_WG@Z`
- size: `131`
- prototype: `CEventLog *__fastcall(CEventLog *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002753c`

## callees

- `0x140005220`
- `0x14001e440`
- `0x140024944`
- `0x140029458`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002948e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002948e`
- `ext-ms-win-advapi32-eventlog-l1-1-0!RegisterEventSourceW` at `0x140029480`
- `ext-ms-win-advapi32-eventlog-l1-1-0!RegisterEventSourceW` at `0x140029480`

## string_xrefs

- `0x140029477`: `Windows Search Service`
- `0x1400294af`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\eventlog.cxx"`
- `0x1400294c0`: `onecoreuap\base\appmodel\search\common\pkmutild\eventlog.cxx`

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
0x140029458  push    rbx
0x14002945a  sub     rsp, 20h
0x14002945e  mov     rbx, rcx
0x140029461  mov     qword ptr [rcx], 0
0x140029468  mov     word ptr [rcx+8], 3
0x14002946e  call    IsDeregisterEventSourcePresent
0x140029473  test    al, al
0x140029475  jz      short loc_1400294D2
0x140029477  lea     rdx, SourceName; "Windows Search Service"
0x14002947e  xor     ecx, ecx; lpUNCServerName
0x140029480  call    cs:__imp_RegisterEventSourceW
0x140029486  mov     [rbx], rax
0x140029489  test    rax, rax
0x14002948c  jnz     short loc_1400294D2
0x14002948e  call    cs:__imp_GetLastError
0x140029494  test    eax, eax
0x140029496  jle     short loc_1400294A0
0x140029498  movzx   eax, ax
0x14002949b  or      eax, 80070000h
0x1400294a0  mov     r9d, eax; wchar_t *
0x1400294a3  lea     r8, aEventlogEventl; "[EventLog] EventLog could not be regist"...
0x1400294aa  mov     edx, 24h ; '$'; wchar_t *
0x1400294af  lea     rcx, aOnecoreuapBase_13; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1400294b6  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1400294bb  mov     rcx, [rsp+28h]; this
0x1400294c0  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400294c7  mov     edx, 25h ; '%'; void *
0x1400294cc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400294d2  mov     rax, rbx
0x1400294d5  add     rsp, 20h
0x1400294d9  pop     rbx
0x1400294da  retn
```
