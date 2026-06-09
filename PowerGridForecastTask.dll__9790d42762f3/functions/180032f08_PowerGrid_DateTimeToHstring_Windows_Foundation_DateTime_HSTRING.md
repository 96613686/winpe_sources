# PowerGrid::DateTimeToHstring(Windows::Foundation::DateTime,HSTRING__ * *)

- ea: `0x180032f08`
- end: `0x180032fee`
- name: `?DateTimeToHstring@PowerGrid@@YAJUDateTime@Foundation@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `230`
- prototype: `HRESULT __fastcall(FILETIME, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180031c98`

## callees

- `0x1800268ef`
- `0x1800314d4`
- `0x180032f08`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180032f52`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180032f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180032fc8`

## pseudocode

```c
HRESULT __fastcall PowerGrid::DateTimeToHstring(FILETIME a1, HSTRING *a2)
{
  __int64 v3; // rdx
  FILETIME FileTime; // [rsp+40h] [rbp-C0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR sourceString[264]; // [rsp+60h] [rbp-A0h] BYREF

  FileTime = a1;
  SystemTime = 0;
  FileTimeToSystemTime(&FileTime, &SystemTime);
  memset_0(sourceString, 0, 0x208u);
  swprintf_s<260>(
    sourceString,
    L"%04d-%02d-%02dT%02d:%02d:%02dZ",
    SystemTime.wYear,
    SystemTime.wMonth,
    SystemTime.wDay,
    SystemTime.wHour,
    SystemTime.wMinute,
    SystemTime.wSecond);
  v3 = -1;
  do
    ++v3;
  while ( sourceString[v3] );
  return WindowsCreateString(sourceString, v3, a2);
}

```

## disassembly

```asm
0x180032f08  mov     [rsp-8+arg_10], rbx
0x180032f0d  push    rbp
0x180032f0e  lea     rbp, [rsp-180h]
0x180032f16  sub     rsp, 280h
0x180032f1d  mov     rax, cs:__security_cookie
0x180032f24  xor     rax, rsp
0x180032f27  mov     [rbp+180h+var_10], rax
0x180032f2e  mov     rax, rcx
0x180032f31  mov     [rsp+280h+FileTime.dwLowDateTime], ecx
0x180032f35  shr     rax, 20h
0x180032f39  lea     rcx, [rsp+280h+FileTime]; lpFileTime
0x180032f3e  mov     rbx, rdx
0x180032f41  mov     [rsp+280h+FileTime.dwHighDateTime], eax
0x180032f45  xorps   xmm0, xmm0
0x180032f48  lea     rdx, [rsp+280h+SystemTime]; lpSystemTime
0x180032f4d  movups  xmmword ptr [rsp+280h+SystemTime.wYear], xmm0
0x180032f52  call    cs:__imp_FileTimeToSystemTime
0x180032f58  xor     edx, edx; Val
0x180032f5a  lea     rcx, [rsp+280h+sourceString]; void *
0x180032f5f  mov     r8d, 208h; Size
0x180032f65  call    memset_0
0x180032f6a  movzx   ecx, [rsp+280h+SystemTime.wMinute]
0x180032f6f  movzx   edx, [rsp+280h+SystemTime.wHour]
0x180032f74  movzx   eax, [rsp+280h+SystemTime.wSecond]
0x180032f79  movzx   r10d, [rsp+280h+SystemTime.wDay]
0x180032f7f  movzx   r9d, [rsp+280h+SystemTime.wMonth]
0x180032f85  movzx   r8d, [rsp+280h+SystemTime.wYear]
0x180032f8b  mov     [rsp+280h+var_248], eax
0x180032f8f  mov     [rsp+280h+var_250], ecx
0x180032f93  lea     rcx, [rsp+280h+sourceString]
0x180032f98  mov     [rsp+280h+var_258], edx
0x180032f9c  lea     rdx, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02dZ"
0x180032fa3  mov     [rsp+280h+var_260], r10d
0x180032fa8  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@GPEBGZZ; swprintf_s<260>(ushort (&)[260],ushort const *,...)
0x180032fad  lea     rax, [rsp+280h+sourceString]
0x180032fb2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180032fb6  inc     rdx; length
0x180032fb9  cmp     word ptr [rax+rdx*2], 0
0x180032fbe  jnz     short loc_180032FB6
0x180032fc0  mov     r8, rbx; string
0x180032fc3  lea     rcx, [rsp+280h+sourceString]; sourceString
0x180032fc8  call    cs:__imp_WindowsCreateString
0x180032fce  mov     rcx, [rbp+180h+var_10]
0x180032fd5  xor     rcx, rsp; StackCookie
0x180032fd8  call    __security_check_cookie
0x180032fdd  mov     rbx, [rsp+280h+arg_10]
0x180032fe5  add     rsp, 280h
0x180032fec  pop     rbp
0x180032fed  retn
```
