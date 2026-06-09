# LQSDeleteInternal(wchar_t const *)

- ea: `0x180027c5c`
- end: `0x180027d8b`
- name: `?LQSDeleteInternal@@YAJPEB_W@Z`
- size: `303`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180027a18`
- `0x180027b88`

## callees

- `0x18000bab8`
- `0x18000cb80`
- `0x18000e558`
- `0x1800261e0`
- `0x180027c5c`
- `0x1800280a8`
- `0x18002c61c`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180027d16`
- `KERNEL32!GetLastError` at `0x180027d16`
- `KERNEL32!FindFirstFileW` at `0x180027c98`
- `KERNEL32!FindFirstFileW` at `0x180027c98`
- `KERNEL32!DeleteFileW` at `0x180027d0c`
- `KERNEL32!DeleteFileW` at `0x180027d0c`

## pseudocode

```c
__int64 __fastcall LQSDeleteInternal(LPCWSTR lpFileName)
{
  unsigned __int16 v2; // r8
  unsigned int v3; // ebx
  int v4; // ecx
  unsigned int v5; // ebx
  wchar_t *v6; // rax
  int v7; // eax
  char LastError; // al
  HANDLE v10[2]; // [rsp+30h] [rbp-4E8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-4D8h] BYREF
  WCHAR FileName[312]; // [rsp+290h] [rbp-288h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v10[0] = FindFirstFileW(lpFileName, &FindFileData);
  if ( v10[0] == (HANDLE)-1LL )
  {
    v2 = 230;
  }
  else
  {
    v5 = 306 - mqwcslen(FileName);
    v6 = (wchar_t *)LQSGetDirectory(FileName);
    v7 = StringCchCopyW(v6, v5, FindFileData.cFileName);
    v3 = v7;
    if ( v7 < 0 )
    {
      v2 = 5970;
      v4 = v7;
      goto LABEL_6;
    }
    if ( DeleteFileW(FileName) )
    {
      v3 = 0;
      goto LABEL_13;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    v2 = 1194;
  }
  v3 = -1072824317;
  v4 = -1072824317;
LABEL_6:
  LogMsgHR(v4, (wchar_t *)L"lqs", v2);
LABEL_13:
  CAutoCloseFindFile::~CAutoCloseFindFile((CAutoCloseFindFile *)v10);
  return v3;
}

```

## disassembly

```asm
0x180027c5c  mov     [rsp+arg_8], rbx
0x180027c61  push    rdi
0x180027c62  sub     rsp, 510h
0x180027c69  mov     rax, cs:__security_cookie
0x180027c70  xor     rax, rsp
0x180027c73  mov     [rsp+518h+var_18], rax
0x180027c7b  mov     rdi, rcx
0x180027c7e  xor     edx, edx; Val
0x180027c80  mov     r8d, 250h; Size
0x180027c86  lea     rcx, [rsp+518h+FindFileData]; void *
0x180027c8b  call    memset_0
0x180027c90  lea     rdx, [rsp+518h+FindFileData]; lpFindFileData
0x180027c95  mov     rcx, rdi; lpFileName
0x180027c98  call    cs:__imp_FindFirstFileW
0x180027c9e  mov     [rsp+518h+var_4E8], rax
0x180027ca3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027ca7  jnz     short loc_180027CB8
0x180027ca9  mov     r8d, 0E6h
0x180027caf  mov     ebx, 0C00E0003h
0x180027cb4  mov     ecx, ebx
0x180027cb6  jmp     short loc_180027CF6
0x180027cb8  lea     rcx, [rsp+518h+FileName]; wchar_t *
0x180027cc0  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027cc5  mov     ebx, 132h
0x180027cca  sub     ebx, eax
0x180027ccc  lea     rcx, [rsp+518h+FileName]; wchar_t *
0x180027cd4  call    LQSGetDirectory
0x180027cd9  lea     r8, [rsp+518h+FindFileData.cFileName]; wchar_t *
0x180027cde  mov     edx, ebx; unsigned __int64
0x180027ce0  mov     rcx, rax; wchar_t *
0x180027ce3  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180027ce8  mov     ebx, eax
0x180027cea  test    eax, eax
0x180027cec  jns     short loc_180027D04
0x180027cee  mov     r8d, 1752h; unsigned __int16
0x180027cf4  mov     ecx, eax; int
0x180027cf6  lea     rdx, aLqs_0; "lqs"
0x180027cfd  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180027d02  jmp     short loc_180027D5E
0x180027d04  lea     rcx, [rsp+518h+FileName]; lpFileName
0x180027d0c  call    cs:__imp_DeleteFileW
0x180027d12  test    eax, eax
0x180027d14  jnz     short loc_180027D5C
0x180027d16  call    cs:__imp_GetLastError
0x180027d1c  lea     rdx, WPP_GLOBAL_Control
0x180027d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d2a  cmp     rcx, rdx
0x180027d2d  jz      short loc_180027D51
0x180027d2f  test    byte ptr [rcx+1Ch], 1
0x180027d33  jz      short loc_180027D51
0x180027d35  mov     edx, 24h ; '$'
0x180027d3a  mov     dword ptr [rsp+518h+var_4F8], eax; char
0x180027d3e  mov     r9, rdi
0x180027d41  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x180027d48  mov     rcx, [rcx+10h]; LoggerHandle
0x180027d4c  call    WPP_SF_Sd
0x180027d51  mov     r8d, 4AAh
0x180027d57  jmp     loc_180027CAF
0x180027d5c  xor     ebx, ebx
0x180027d5e  lea     rcx, [rsp+518h+var_4E8]; this
0x180027d63  call    ??1CAutoCloseFindFile@@QEAA@XZ; CAutoCloseFindFile::~CAutoCloseFindFile(void)
0x180027d68  mov     eax, ebx
0x180027d6a  mov     rcx, [rsp+518h+var_18]
0x180027d72  xor     rcx, rsp; StackCookie
0x180027d75  call    __security_check_cookie
0x180027d7a  mov     rbx, [rsp+518h+arg_8]
0x180027d82  add     rsp, 510h
0x180027d89  pop     rdi
0x180027d8a  retn
```
