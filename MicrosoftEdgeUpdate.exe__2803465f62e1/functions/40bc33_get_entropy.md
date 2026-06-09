# ___get_entropy

- ea: `0x40bc33`
- end: `0x40bc80`
- name: `___get_entropy`
- size: `77`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x40bc80`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x40bc6a`
- `KERNEL32!QueryPerformanceCounter` at `0x40bc6a`
- `KERNEL32!GetCurrentProcessId` at `0x40bc5d`
- `KERNEL32!GetCurrentProcessId` at `0x40bc5d`
- `KERNEL32!GetCurrentThreadId` at `0x40bc54`
- `KERNEL32!GetCurrentThreadId` at `0x40bc54`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40bc45`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x40bc45`

## pseudocode

```c
unsigned int __get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
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
0x40bc33  push    ebp
0x40bc34  mov     ebp, esp
0x40bc36  sub     esp, 14h
0x40bc39  and     [ebp+SystemTimeAsFileTime.dwLowDateTime], 0
0x40bc3d  lea     eax, [ebp+SystemTimeAsFileTime]
0x40bc40  and     [ebp+SystemTimeAsFileTime.dwHighDateTime], 0
0x40bc44  push    eax; lpSystemTimeAsFileTime
0x40bc45  call    ds:GetSystemTimeAsFileTime
0x40bc4b  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x40bc4e  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x40bc51  mov     [ebp+var_4], eax
0x40bc54  call    ds:GetCurrentThreadId
0x40bc5a  xor     [ebp+var_4], eax
0x40bc5d  call    ds:GetCurrentProcessId
0x40bc63  xor     [ebp+var_4], eax
0x40bc66  lea     eax, [ebp+PerformanceCount]
0x40bc69  push    eax; lpPerformanceCount
0x40bc6a  call    ds:QueryPerformanceCounter
0x40bc70  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x40bc73  lea     ecx, [ebp+var_4]
0x40bc76  xor     eax, dword ptr [ebp+PerformanceCount]
0x40bc79  xor     eax, [ebp+var_4]
0x40bc7c  xor     eax, ecx
0x40bc7e  leave
0x40bc7f  retn
```
