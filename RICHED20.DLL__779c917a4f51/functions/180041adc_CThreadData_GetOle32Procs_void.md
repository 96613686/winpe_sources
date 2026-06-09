# CThreadData::GetOle32Procs(void)

- ea: `0x180041adc`
- end: `0x180041b14`
- name: `?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ`
- size: `56`
- prototype: `struct COLE32_PROC *(void)`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x18004a23c`
- `0x18004b168`
- `0x1800532ec`
- `0x18005361c`
- `0x180053d4c`
- `0x180055f28`
- `0x18005afc8`
- `0x18005c250`
- `0x18006f94c`
- `0x180074458`
- `0x18007c360`
- `0x18007cb94`
- `0x18007d7bc`
- `0x18007da2c`
- `0x18008c2dc`
- `0x18008d5ac`
- `0x18008d624`
- `0x18008fbd0`
- `0x18008fc64`
- `0x18008fcfc`
- `0x18008fd94`
- `0x18008fdf0`
- `0x18008fe40`
- `0x18008fe9c`
- `0x18008fef8`
- `0x18008ff64`
- `0x18008ffc8`
- `0x18009049c`
- `0x180090508`
- `0x180090564`
- `0x180090f20`
- `0x180090f8c`

## callees

- `0x180041adc`
- `0x180090068`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180041ae7`
- `KERNEL32!EnterCriticalSection` at `0x180041ae7`
- `KERNEL32!LeaveCriticalSection` at `0x180041b02`
- `KERNEL32!LeaveCriticalSection` at `0x180041b02`

## pseudocode

```c
struct COLE32_PROC *CThreadData::GetOle32Procs(void)
{
  EnterCriticalSection(&g_CriticalSection);
  if ( !CW32System::_fOleinitCheckDisabled )
    CThreadData::OnOleCall();
  LeaveCriticalSection(&g_CriticalSection);
  return (struct COLE32_PROC *)qword_1800A3FA0;
}

```

## disassembly

```asm
0x180041adc  sub     rsp, 28h
0x180041ae0  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180041ae7  call    cs:__imp_EnterCriticalSection
0x180041aed  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x180041af4  jnz     short loc_180041AFB
0x180041af6  call    ?OnOleCall@CThreadData@@SAXXZ; CThreadData::OnOleCall(void)
0x180041afb  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180041b02  call    cs:__imp_LeaveCriticalSection
0x180041b08  lea     rax, qword_1800A3FA0
0x180041b0f  add     rsp, 28h
0x180041b13  retn
```
