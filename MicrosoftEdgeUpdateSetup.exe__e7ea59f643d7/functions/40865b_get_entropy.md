# ___get_entropy

- ea: `0x40865b`
- end: `0x4086a8`
- name: `___get_entropy`
- size: `77`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x4086a8`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x408692`
- `KERNEL32!QueryPerformanceCounter` at `0x408692`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40866d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40866d`
- `KERNEL32!GetCurrentThreadId` at `0x40867c`
- `KERNEL32!GetCurrentThreadId` at `0x40867c`
- `KERNEL32!GetCurrentProcessId` at `0x408685`
- `KERNEL32!GetCurrentProcessId` at `0x408685`

## pseudocode

```c
unsigned int __get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  DWORD v3; // [esp+10h] [ebp-4h] BYREF

  SystemTimeAsFileTime.dwLowDateTime = 0;
  SystemTimeAsFileTime.dwHighDateTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
  v3 ^= GetCurrentThreadId();
  v3 ^= GetCurrentProcessId();
  QueryPerformanceCounter(&PerformanceCount);
  return (unsigned int)&v3 ^ v3 ^ PerformanceCount.LowPart ^ PerformanceCount.HighPart;
}

```

## disassembly

```asm
0x40865b  push    ebp
0x40865c  mov     ebp, esp
0x40865e  sub     esp, 14h
0x408661  and     [ebp+SystemTimeAsFileTime.dwLowDateTime], 0
0x408665  lea     eax, [ebp+SystemTimeAsFileTime]
0x408668  and     [ebp+SystemTimeAsFileTime.dwHighDateTime], 0
0x40866c  push    eax; lpSystemTimeAsFileTime
0x40866d  call    ds:GetSystemTimeAsFileTime
0x408673  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x408676  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x408679  mov     [ebp+var_4], eax
0x40867c  call    ds:GetCurrentThreadId
0x408682  xor     [ebp+var_4], eax
0x408685  call    ds:GetCurrentProcessId
0x40868b  xor     [ebp+var_4], eax
0x40868e  lea     eax, [ebp+PerformanceCount]
0x408691  push    eax; lpPerformanceCount
0x408692  call    ds:QueryPerformanceCounter
0x408698  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x40869b  lea     ecx, [ebp+var_4]
0x40869e  xor     eax, dword ptr [ebp+PerformanceCount]
0x4086a1  xor     eax, [ebp+var_4]
0x4086a4  xor     eax, ecx
0x4086a6  leave
0x4086a7  retn
```
