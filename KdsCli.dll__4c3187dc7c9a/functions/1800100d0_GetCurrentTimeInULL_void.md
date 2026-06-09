# GetCurrentTimeInULL(void)

- ea: `0x1800100d0`
- end: `0x180010126`
- name: `?GetCurrentTimeInULL@@YA_KXZ`
- size: `86`
- prototype: `unsigned __int64(void)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f9c`
- `0x180007d28`
- `0x180008cf0`
- `0x18000b310`
- `0x18000eab8`
- `0x18000edb8`
- `0x18000ef64`
- `0x180010010`
- `0x180010080`

## callees

- `0x180001630`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800100f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800100f9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180010109`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180010109`

## pseudocode

```c
struct _FILETIME GetCurrentTimeInULL(void)
{
  struct _FILETIME FileTime; // [rsp+20h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  FileTime = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  return FileTime;
}

```

## disassembly

```asm
0x1800100d0  sub     rsp, 48h
0x1800100d4  mov     rax, cs:__security_cookie
0x1800100db  xor     rax, rsp
0x1800100de  mov     [rsp+48h+var_10], rax
0x1800100e3  xorps   xmm0, xmm0
0x1800100e6  mov     qword ptr [rsp+48h+FileTime.dwLowDateTime], 0
0x1800100ef  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x1800100f4  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x1800100f9  call    cs:__imp_GetSystemTime
0x1800100ff  lea     rdx, [rsp+48h+FileTime]; lpFileTime
0x180010104  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x180010109  call    cs:__imp_SystemTimeToFileTime
0x18001010f  mov     rax, qword ptr [rsp+48h+FileTime.dwLowDateTime]
0x180010114  mov     rcx, [rsp+48h+var_10]
0x180010119  xor     rcx, rsp; StackCookie
0x18001011c  call    __security_check_cookie
0x180010121  add     rsp, 48h
0x180010125  retn
```
