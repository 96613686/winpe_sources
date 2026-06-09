# BrowserDataLogger::Util::GetCurrentTimeInMs(void)

- ea: `0x180004828`
- end: `0x180004868`
- name: `?GetCurrentTimeInMs@Util@BrowserDataLogger@@CA_KXZ`
- size: `64`
- prototype: `unsigned __int64(void)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000448c`
- `0x1800048e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000483a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000483a`

## pseudocode

```c
unsigned __int64 BrowserDataLogger::Util::GetCurrentTimeInMs(void)
{
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  return (SystemTimeAsFileTime.dwLowDateTime + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)) / 0x2710;
}

```

## disassembly

```asm
0x180004828  sub     rsp, 28h
0x18000482c  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004831  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000483a  call    cs:__imp_GetSystemTimeAsFileTime
0x180004840  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180004844  mov     ecx, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x180004848  shl     rcx, 20h
0x18000484c  add     rcx, rax
0x18000484f  mov     rax, 346DC5D63886594Bh
0x180004859  mul     rcx
0x18000485c  shr     rdx, 0Bh
0x180004860  mov     rax, rdx
0x180004863  add     rsp, 28h
0x180004867  retn
```
