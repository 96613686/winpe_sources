# IsDayOldFileTime(_FILETIME)

- ea: `0x180052a54`
- end: `0x180052ac0`
- name: `?IsDayOldFileTime@@YA_NU_FILETIME@@@Z`
- size: `108`
- prototype: `bool __fastcall(struct _FILETIME)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800341ec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180052a6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180052a6b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180052aa9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180052aa9`

## pseudocode

```c
bool __fastcall IsDayOldFileTime(FILETIME a1)
{
  unsigned __int64 v1; // rdx
  FILETIME FileTime1; // [rsp+30h] [rbp+8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+10h] BYREF

  FileTime1 = a1;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v1 = FileTime1.dwLowDateTime + ((unsigned __int64)FileTime1.dwHighDateTime << 32) + 864000000000LL;
  FileTime1.dwLowDateTime += 711573504;
  FileTime1.dwHighDateTime = HIDWORD(v1);
  return CompareFileTime(&FileTime1, &SystemTimeAsFileTime) <= 0;
}

```

## disassembly

```asm
0x180052a54  mov     qword ptr [rsp+FileTime1.dwLowDateTime], rcx
0x180052a59  sub     rsp, 28h
0x180052a5d  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180052a62  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180052a6b  call    cs:__imp_GetSystemTimeAsFileTime
0x180052a72  nop     dword ptr [rax+rax+00h]
0x180052a77  mov     ecx, [rsp+28h+FileTime1.dwLowDateTime]
0x180052a7b  mov     rdx, 0C92A69C000h
0x180052a85  mov     eax, [rsp+28h+FileTime1.dwHighDateTime]
0x180052a89  shl     rax, 20h
0x180052a8d  add     rdx, rax
0x180052a90  add     rdx, rcx
0x180052a93  lea     rcx, [rsp+28h+FileTime1]; lpFileTime1
0x180052a98  mov     [rsp+28h+FileTime1.dwLowDateTime], edx
0x180052a9c  shr     rdx, 20h
0x180052aa0  mov     [rsp+28h+FileTime1.dwHighDateTime], edx
0x180052aa4  lea     rdx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime2
0x180052aa9  call    cs:__imp_CompareFileTime
0x180052ab0  nop     dword ptr [rax+rax+00h]
0x180052ab5  test    eax, eax
0x180052ab7  setle   al
0x180052aba  add     rsp, 28h
0x180052abe  retn
```
