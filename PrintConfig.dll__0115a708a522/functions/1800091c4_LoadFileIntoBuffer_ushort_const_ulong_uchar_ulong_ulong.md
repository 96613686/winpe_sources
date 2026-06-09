# LoadFileIntoBuffer(ushort const *,ulong *,uchar *,ulong,ulong *)

- ea: `0x1800091c4`
- end: `0x180009322`
- name: `?LoadFileIntoBuffer@@YAKPEBGPEAKPEAEK1@Z`
- size: `350`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int *, unsigned __int8 *, DWORD, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800081a0`

## callees

- `0x180003400`
- `0x1800091c4`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x180009218`
- `KERNEL32!GetFileAttributesExW` at `0x180009218`
- `KERNEL32!ReadFile` at `0x1800092be`
- `KERNEL32!ReadFile` at `0x1800092be`
- `KERNEL32!CreateFileW` at `0x18000927a`
- `KERNEL32!CreateFileW` at `0x18000927a`
- `KERNEL32!CloseHandle` at `0x1800092f1`
- `KERNEL32!CloseHandle` at `0x1800092f1`
- `KERNEL32!GetLastError` at `0x18000928f`
- `KERNEL32!GetLastError` at `0x1800092ce`
- `KERNEL32!GetLastError` at `0x18000928f`
- `KERNEL32!GetLastError` at `0x1800092ce`

## pseudocode

```c
__int64 __fastcall LoadFileIntoBuffer(
        LPCWSTR lpFileName,
        unsigned int *a2,
        unsigned __int8 *a3,
        DWORD a4,
        unsigned int *a5)
{
  bool v9; // zf
  DWORD v10; // eax
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  void *v13; // rdi
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-68h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-60h] BYREF
  __int128 v17; // [rsp+58h] [rbp-50h]
  unsigned int v18; // [rsp+68h] [rbp-40h]

  v18 = 0;
  FileInformation = 0;
  v17 = 0;
  if ( !lpFileName || !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
    return 2;
  v9 = HIDWORD(v17) == 0;
  v10 = v18;
  *a5 = v18;
  *a2 = 3;
  if ( v9 )
  {
    if ( v10 <= a4 )
    {
      FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
      v13 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        return GetLastError();
      }
      else
      {
        NumberOfBytesRead = 0;
        if ( ReadFile(FileW, a3, a4, &NumberOfBytesRead, 0) )
        {
          LastError = 0;
          if ( *a5 != NumberOfBytesRead )
            LastError = 995;
        }
        else
        {
          LastError = GetLastError();
        }
        CloseHandle(v13);
      }
    }
    else
    {
      return 234;
    }
  }
  else
  {
    return 8;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800091c4  push    rbx
0x1800091c6  push    rbp
0x1800091c7  push    rsi
0x1800091c8  push    rdi
0x1800091c9  push    r14
0x1800091cb  sub     rsp, 80h
0x1800091d2  mov     rax, cs:__security_cookie
0x1800091d9  xor     rax, rsp
0x1800091dc  mov     [rsp+0A8h+var_38], rax
0x1800091e1  mov     rsi, [rsp+0A8h+arg_20]
0x1800091e9  xor     eax, eax
0x1800091eb  mov     [rsp+0A8h+var_40], eax
0x1800091ef  xorps   xmm0, xmm0
0x1800091f2  mov     ebp, r9d
0x1800091f5  mov     r14, r8
0x1800091f8  mov     rdi, rdx
0x1800091fb  mov     rbx, rcx
0x1800091fe  movups  [rsp+0A8h+FileInformation], xmm0
0x180009203  movups  [rsp+0A8h+var_50], xmm0
0x180009208  test    rcx, rcx
0x18000920b  jz      loc_180009301
0x180009211  lea     r8, [rsp+0A8h+FileInformation]; lpFileInformation
0x180009216  xor     edx, edx; fInfoLevelId
0x180009218  call    cs:__imp_GetFileAttributesExW
0x18000921f  nop     dword ptr [rax+rax+00h]
0x180009224  test    eax, eax
0x180009226  jz      loc_180009301
0x18000922c  cmp     dword ptr [rsp+0A8h+var_50+0Ch], 0
0x180009231  mov     ecx, 3
0x180009236  mov     eax, [rsp+0A8h+var_40]
0x18000923a  mov     [rsi], eax
0x18000923c  mov     [rdi], ecx
0x18000923e  jz      short loc_180009248
0x180009240  lea     ebx, [rcx+5]
0x180009243  jmp     loc_1800092FD
0x180009248  cmp     eax, ebp
0x18000924a  jbe     short loc_180009256
0x18000924c  mov     ebx, 0EAh
0x180009251  jmp     loc_1800092FD
0x180009256  xor     r9d, r9d; lpSecurityAttributes
0x180009259  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x180009262  mov     [rsp+0A8h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x18000926a  mov     edx, 80000000h; dwDesiredAccess
0x18000926f  mov     [rsp+0A8h+dwCreationDisposition], ecx; dwCreationDisposition
0x180009273  mov     rcx, rbx; lpFileName
0x180009276  lea     r8d, [r9+1]; dwShareMode
0x18000927a  call    cs:__imp_CreateFileW
0x180009281  nop     dword ptr [rax+rax+00h]
0x180009286  mov     rdi, rax
0x180009289  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000928d  jnz     short loc_18000929F
0x18000928f  call    cs:__imp_GetLastError
0x180009296  nop     dword ptr [rax+rax+00h]
0x18000929b  mov     ebx, eax
0x18000929d  jmp     short loc_1800092FD
0x18000929f  lea     r9, [rsp+0A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800092a4  mov     [rsp+0A8h+NumberOfBytesRead], 0
0x1800092ac  mov     r8d, ebp; nNumberOfBytesToRead
0x1800092af  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0; lpOverlapped
0x1800092b8  mov     rdx, r14; lpBuffer
0x1800092bb  mov     rcx, rdi; hFile
0x1800092be  call    cs:__imp_ReadFile
0x1800092c5  nop     dword ptr [rax+rax+00h]
0x1800092ca  test    eax, eax
0x1800092cc  jnz     short loc_1800092DE
0x1800092ce  call    cs:__imp_GetLastError
0x1800092d5  nop     dword ptr [rax+rax+00h]
0x1800092da  mov     ebx, eax
0x1800092dc  jmp     short loc_1800092EE
0x1800092de  mov     eax, [rsp+0A8h+NumberOfBytesRead]
0x1800092e2  xor     ebx, ebx
0x1800092e4  cmp     [rsi], eax
0x1800092e6  mov     ecx, 3E3h
0x1800092eb  cmovnz  ebx, ecx
0x1800092ee  mov     rcx, rdi; hObject
0x1800092f1  call    cs:__imp_CloseHandle
0x1800092f8  nop     dword ptr [rax+rax+00h]
0x1800092fd  mov     eax, ebx
0x1800092ff  jmp     short loc_180009306
0x180009301  mov     eax, 2
0x180009306  mov     rcx, [rsp+0A8h+var_38]
0x18000930b  xor     rcx, rsp; StackCookie
0x18000930e  call    __security_check_cookie
0x180009313  add     rsp, 80h
0x18000931a  pop     r14
0x18000931c  pop     rdi
0x18000931d  pop     rsi
0x18000931e  pop     rbp
0x18000931f  pop     rbx
0x180009320  retn
```
