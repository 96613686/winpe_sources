# SetFileToCurrentTime

- ea: `0x14002bf54`
- end: `0x14002c06b`
- name: `SetFileToCurrentTime`
- size: `279`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140028424`
- `0x14002bb00`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14002bf54`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002bfdb`
- `KERNEL32!GetLastError` at `0x14002c018`
- `KERNEL32!GetLastError` at `0x14002bfdb`
- `KERNEL32!GetLastError` at `0x14002c018`
- `KERNEL32!GetSystemTime` at `0x14002bfbf`
- `KERNEL32!GetSystemTime` at `0x14002bfbf`
- `KERNEL32!SystemTimeToFileTime` at `0x14002bfcf`
- `KERNEL32!SystemTimeToFileTime` at `0x14002bfcf`
- `KERNEL32!SetFileTime` at `0x14002c00c`
- `KERNEL32!SetFileTime` at `0x14002c00c`

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
0x14002bf54  mov     [rsp+arg_8], rbx
0x14002bf59  mov     [rsp+arg_10], rbp
0x14002bf5e  push    rdi
0x14002bf5f  sub     rsp, 40h
0x14002bf63  mov     rax, cs:__security_cookie
0x14002bf6a  xor     rax, rsp
0x14002bf6d  mov     [rsp+48h+var_10], rax
0x14002bf72  xorps   xmm0, xmm0
0x14002bf75  mov     qword ptr [rsp+48h+FileTime.dwLowDateTime], 0
0x14002bf7e  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x14002bf83  mov     rdi, rcx
0x14002bf86  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bf8d  lea     rbp, WPP_GLOBAL_Control
0x14002bf94  cmp     rcx, rbp
0x14002bf97  jz      short loc_14002BFBA
0x14002bf99  test    byte ptr [rcx+1Ch], 4
0x14002bf9d  jz      short loc_14002BFBA
0x14002bf9f  cmp     byte ptr [rcx+19h], 5
0x14002bfa3  jb      short loc_14002BFBA
0x14002bfa5  mov     rcx, [rcx+10h]
0x14002bfa9  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002bfb0  mov     edx, 79h ; 'y'
0x14002bfb5  call    WPP_SF_
0x14002bfba  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x14002bfbf  call    cs:__imp_GetSystemTime
0x14002bfc5  lea     rdx, [rsp+48h+FileTime]; lpFileTime
0x14002bfca  lea     rcx, [rsp+48h+SystemTime]; lpSystemTime
0x14002bfcf  call    cs:__imp_SystemTimeToFileTime
0x14002bfd5  mov     ebx, eax
0x14002bfd7  test    eax, eax
0x14002bfd9  jnz     short loc_14002BFFE
0x14002bfdb  call    cs:__imp_GetLastError
0x14002bfe1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bfe8  cmp     rcx, rbp
0x14002bfeb  jz      short loc_14002C04C
0x14002bfed  test    byte ptr [rcx+1Ch], 4
0x14002bff1  jz      short loc_14002C04C
0x14002bff3  cmp     byte ptr [rcx+19h], 2
0x14002bff7  jb      short loc_14002C04C
0x14002bff9  lea     edx, [rbx+7Ah]
0x14002bffc  jmp     short loc_14002C039
0x14002bffe  xor     r9d, r9d; lpLastWriteTime
0x14002c001  lea     rdx, [rsp+48h+FileTime]; lpCreationTime
0x14002c006  xor     r8d, r8d; lpLastAccessTime
0x14002c009  mov     rcx, rdi; hFile
0x14002c00c  call    cs:__imp_SetFileTime
0x14002c012  mov     ebx, eax
0x14002c014  test    eax, eax
0x14002c016  jnz     short loc_14002C04C
0x14002c018  call    cs:__imp_GetLastError
0x14002c01e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c025  cmp     rcx, rbp
0x14002c028  jz      short loc_14002C04C
0x14002c02a  test    byte ptr [rcx+1Ch], 4
0x14002c02e  jz      short loc_14002C04C
0x14002c030  cmp     byte ptr [rcx+19h], 2
0x14002c034  jb      short loc_14002C04C
0x14002c036  lea     edx, [rbx+7Bh]
0x14002c039  mov     rcx, [rcx+10h]
0x14002c03d  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002c044  mov     r9d, eax
0x14002c047  call    WPP_SF_d
0x14002c04c  mov     eax, ebx
0x14002c04e  mov     rcx, [rsp+48h+var_10]
0x14002c053  xor     rcx, rsp; StackCookie
0x14002c056  call    __security_check_cookie
0x14002c05b  mov     rbx, [rsp+48h+arg_8]
0x14002c060  mov     rbp, [rsp+48h+arg_10]
0x14002c065  add     rsp, 40h
0x14002c069  pop     rdi
0x14002c06a  retn
```
