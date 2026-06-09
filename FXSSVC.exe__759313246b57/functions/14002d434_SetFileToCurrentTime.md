# SetFileToCurrentTime

- ea: `0x14002d434`
- end: `0x14002d56a`
- name: `SetFileToCurrentTime`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400297b0`
- `0x14002cfa4`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14002d434`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002d4c7`
- `KERNEL32!GetLastError` at `0x14002d510`
- `KERNEL32!GetLastError` at `0x14002d4c7`
- `KERNEL32!GetLastError` at `0x14002d510`
- `KERNEL32!GetSystemTime` at `0x14002d49f`
- `KERNEL32!GetSystemTime` at `0x14002d49f`
- `KERNEL32!SystemTimeToFileTime` at `0x14002d4b5`
- `KERNEL32!SystemTimeToFileTime` at `0x14002d4b5`
- `KERNEL32!SetFileTime` at `0x14002d4fe`
- `KERNEL32!SetFileTime` at `0x14002d4fe`

## pseudocode

```c
__int64 __fastcall SetFileToCurrentTime(HANDLE hFile)
{
  unsigned int v2; // ebx
  DWORD LastError; // eax
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  FileTime = 0;
  SystemTime = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  GetSystemTime(&SystemTime);
  v2 = SystemTimeToFileTime(&SystemTime, &FileTime);
  if ( v2 )
  {
    v2 = SetFileTime(hFile, &FileTime, 0, 0);
    if ( !v2 )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 123;
        goto LABEL_15;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 122;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14002d434  mov     [rsp+arg_8], rbx
0x14002d439  mov     [rsp+arg_10], rbp
0x14002d43e  push    rdi
0x14002d43f  sub     rsp, 40h
0x14002d443  mov     rax, cs:__security_cookie
0x14002d44a  xor     rax, rsp
0x14002d44d  mov     [rsp+48h+var_10], rax
0x14002d452  xorps   xmm0, xmm0
0x14002d455  mov     qword ptr [rsp+48h+FileTime.dwLowDateTime], 0
0x14002d45e  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x14002d463  mov     rdi, rcx
0x14002d466  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d46d  lea     rbp, WPP_GLOBAL_Control
0x14002d474  cmp     rcx, rbp
0x14002d477  jz      short loc_14002D49A
0x14002d479  test    byte ptr [rcx+1Ch], 4
0x14002d47d  jz      short loc_14002D49A
0x14002d47f  cmp     byte ptr [rcx+19h], 5
0x14002d483  jb      short loc_14002D49A
0x14002d485  mov     rcx, [rcx+10h]
0x14002d489  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d490  mov     edx, 79h ; 'y'
0x14002d495  call    WPP_SF_
0x14002d49a  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x14002d49f  call    cs:__imp_GetSystemTime
0x14002d4a6  nop     dword ptr [rax+rax+00h]
0x14002d4ab  lea     rdx, [rsp+48h+FileTime]; lpFileTime
0x14002d4b0  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x14002d4b5  call    cs:__imp_SystemTimeToFileTime
0x14002d4bc  nop     dword ptr [rax+rax+00h]
0x14002d4c1  mov     ebx, eax
0x14002d4c3  test    eax, eax
0x14002d4c5  jnz     short loc_14002D4F0
0x14002d4c7  call    cs:__imp_GetLastError
0x14002d4ce  nop     dword ptr [rax+rax+00h]
0x14002d4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d4da  cmp     rcx, rbp
0x14002d4dd  jz      short loc_14002D54A
0x14002d4df  test    byte ptr [rcx+1Ch], 4
0x14002d4e3  jz      short loc_14002D54A
0x14002d4e5  cmp     byte ptr [rcx+19h], 2
0x14002d4e9  jb      short loc_14002D54A
0x14002d4eb  lea     edx, [rbx+7Ah]
0x14002d4ee  jmp     short loc_14002D537
0x14002d4f0  xor     r9d, r9d; lpLastWriteTime
0x14002d4f3  lea     rdx, [rsp+48h+FileTime]; lpCreationTime
0x14002d4f8  xor     r8d, r8d; lpLastAccessTime
0x14002d4fb  mov     rcx, rdi; hFile
0x14002d4fe  call    cs:__imp_SetFileTime
0x14002d505  nop     dword ptr [rax+rax+00h]
0x14002d50a  mov     ebx, eax
0x14002d50c  test    eax, eax
0x14002d50e  jnz     short loc_14002D54A
0x14002d510  call    cs:__imp_GetLastError
0x14002d517  nop     dword ptr [rax+rax+00h]
0x14002d51c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d523  cmp     rcx, rbp
0x14002d526  jz      short loc_14002D54A
0x14002d528  test    byte ptr [rcx+1Ch], 4
0x14002d52c  jz      short loc_14002D54A
0x14002d52e  cmp     byte ptr [rcx+19h], 2
0x14002d532  jb      short loc_14002D54A
0x14002d534  lea     edx, [rbx+7Bh]
0x14002d537  mov     rcx, [rcx+10h]
0x14002d53b  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002d542  mov     r9d, eax
0x14002d545  call    WPP_SF_d
0x14002d54a  mov     eax, ebx
0x14002d54c  mov     rcx, [rsp+48h+var_10]
0x14002d551  xor     rcx, rsp; StackCookie
0x14002d554  call    __security_check_cookie
0x14002d559  mov     rbx, [rsp+48h+arg_8]
0x14002d55e  mov     rbp, [rsp+48h+arg_10]
0x14002d563  add     rsp, 40h
0x14002d567  pop     rdi
0x14002d568  retn
```
