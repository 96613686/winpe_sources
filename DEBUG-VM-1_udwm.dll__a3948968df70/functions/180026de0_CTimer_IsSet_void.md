# CTimer::IsSet(void)

- ea: `0x180026de0`
- end: `0x180026e35`
- name: `?IsSet@CTimer@@QEAA_NXZ`
- size: `85`
- prototype: `bool __fastcall(CTimer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180026d1c`
- `0x18008b644`

## callees

- `0x180026de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026df4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026df4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e1e`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180026e07`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180026e07`

## pseudocode

```c
char __fastcall CTimer::IsSet(CTimer *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  BOOL v3; // eax
  char v4; // bl

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_QWORD *)this + 7) || (v3 = IsThreadpoolTimerSet(*((PTP_TIMER *)this + 7)), v4 = 1, !v3) )
    v4 = 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  return v4;
}

```

## disassembly

```asm
0x180026de0  mov     [rsp+arg_0], rbx
0x180026de5  push    rdi
0x180026de6  sub     rsp, 20h
0x180026dea  lea     rdi, [rcx+10h]
0x180026dee  mov     rbx, rcx
0x180026df1  mov     rcx, rdi; lpCriticalSection
0x180026df4  call    cs:__imp_EnterCriticalSection
0x180026dfa  mov     rax, [rbx+38h]
0x180026dfe  test    rax, rax
0x180026e01  jz      short loc_180026E31
0x180026e03  mov     rcx, [rbx+38h]; pti
0x180026e07  call    cs:__imp_IsThreadpoolTimerSet
0x180026e0d  mov     ebx, 1
0x180026e12  cmp     eax, ebx
0x180026e14  jnz     short loc_180026E31
0x180026e16  test    rdi, rdi
0x180026e19  jz      short loc_180026E24
0x180026e1b  mov     rcx, rdi; lpCriticalSection
0x180026e1e  call    cs:__imp_LeaveCriticalSection
0x180026e24  mov     al, bl
0x180026e26  mov     rbx, [rsp+28h+arg_0]
0x180026e2b  add     rsp, 20h
0x180026e2f  pop     rdi
0x180026e30  retn
0x180026e31  xor     bl, bl
0x180026e33  jmp     short loc_180026E16
```
