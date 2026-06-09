# ___get_entropy

- ea: `0x40dcba`
- end: `0x40dd07`
- name: `___get_entropy`
- size: `77`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x40dd07`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x40dcf1`
- `KERNEL32!QueryPerformanceCounter` at `0x40dcf1`
- `KERNEL32!GetCurrentProcessId` at `0x40dce4`
- `KERNEL32!GetCurrentProcessId` at `0x40dce4`
- `KERNEL32!GetCurrentThreadId` at `0x40dcdb`
- `KERNEL32!GetCurrentThreadId` at `0x40dcdb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40dccc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40dccc`

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
0x40dcba  push    ebp
0x40dcbb  mov     ebp, esp
0x40dcbd  sub     esp, 14h
0x40dcc0  and     [ebp+SystemTimeAsFileTime.dwLowDateTime], 0
0x40dcc4  lea     eax, [ebp+SystemTimeAsFileTime]
0x40dcc7  and     [ebp+SystemTimeAsFileTime.dwHighDateTime], 0
0x40dccb  push    eax; lpSystemTimeAsFileTime
0x40dccc  call    ds:GetSystemTimeAsFileTime
0x40dcd2  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x40dcd5  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x40dcd8  mov     [ebp+var_4], eax
0x40dcdb  call    ds:GetCurrentThreadId
0x40dce1  xor     [ebp+var_4], eax
0x40dce4  call    ds:GetCurrentProcessId
0x40dcea  xor     [ebp+var_4], eax
0x40dced  lea     eax, [ebp+PerformanceCount]
0x40dcf0  push    eax; lpPerformanceCount
0x40dcf1  call    ds:QueryPerformanceCounter
0x40dcf7  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x40dcfa  lea     ecx, [ebp+var_4]
0x40dcfd  xor     eax, dword ptr [ebp+PerformanceCount]
0x40dd00  xor     eax, [ebp+var_4]
0x40dd03  xor     eax, ecx
0x40dd05  leave
0x40dd06  retn
```
