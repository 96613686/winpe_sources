# ___get_entropy

- ea: `0x10010c2e`
- end: `0x10010c7b`
- name: `___get_entropy`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10010c7b`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x10010c58`
- `KERNEL32!GetCurrentProcessId` at `0x10010c58`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10010c40`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10010c40`
- `KERNEL32!GetCurrentThreadId` at `0x10010c4f`
- `KERNEL32!GetCurrentThreadId` at `0x10010c4f`
- `KERNEL32!QueryPerformanceCounter` at `0x10010c65`
- `KERNEL32!QueryPerformanceCounter` at `0x10010c65`

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
0x10010c2e  push    ebp
0x10010c2f  mov     ebp, esp
0x10010c31  sub     esp, 14h
0x10010c34  and     [ebp+SystemTimeAsFileTime.dwLowDateTime], 0
0x10010c38  lea     eax, [ebp+SystemTimeAsFileTime]
0x10010c3b  and     [ebp+SystemTimeAsFileTime.dwHighDateTime], 0
0x10010c3f  push    eax; lpSystemTimeAsFileTime
0x10010c40  call    ds:GetSystemTimeAsFileTime
0x10010c46  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10010c49  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x10010c4c  mov     [ebp+var_4], eax
0x10010c4f  call    ds:GetCurrentThreadId
0x10010c55  xor     [ebp+var_4], eax
0x10010c58  call    ds:GetCurrentProcessId
0x10010c5e  xor     [ebp+var_4], eax
0x10010c61  lea     eax, [ebp+PerformanceCount]
0x10010c64  push    eax; lpPerformanceCount
0x10010c65  call    ds:QueryPerformanceCounter
0x10010c6b  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x10010c6e  lea     ecx, [ebp+var_4]
0x10010c71  xor     eax, dword ptr [ebp+PerformanceCount]
0x10010c74  xor     eax, [ebp+var_4]
0x10010c77  xor     eax, ecx
0x10010c79  leave
0x10010c7a  retn
```
