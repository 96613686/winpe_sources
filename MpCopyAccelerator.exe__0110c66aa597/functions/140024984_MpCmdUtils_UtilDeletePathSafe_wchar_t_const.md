# MpCmdUtils::UtilDeletePathSafe(wchar_t const *)

- ea: `0x140024984`
- end: `0x140024bc5`
- name: `?UtilDeletePathSafe@MpCmdUtils@@YAJPEB_W@Z`
- size: `577`
- prototype: `__int64 __fastcall(void **this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1400242c4`

## callees

- `0x14000436c`
- `0x14000493c`
- `0x140005c20`
- `0x14001da70`
- `0x14001dac4`
- `0x140020220`
- `0x14002476c`
- `0x140024984`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x140024b5f`
- `KERNEL32!SetFileInformationByHandle` at `0x140024b5f`
- `KERNEL32!GetFileInformationByHandle` at `0x140024a4d`
- `KERNEL32!GetFileInformationByHandle` at `0x140024a4d`
- `KERNEL32!CloseHandle` at `0x140024b98`
- `KERNEL32!CloseHandle` at `0x140024b98`

## pseudocode

```c
__int64 __fastcall MpCmdUtils::UtilDeletePathSafe(void **this, const wchar_t *a2)
{
  int File; // eax
  unsigned int v4; // ebx
  unsigned int LastFailure; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  char dwFileAttributes; // al
  HANDLE hFile; // [rsp+48h] [rbp+7h] BYREF
  char v11[8]; // [rsp+50h] [rbp+Fh] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp+17h] BYREF

  File = CommonUtil::UtilCreateFile(
           (CommonUtil *)&hFile,
           this,
           (const wchar_t *)0x10000000,
           0,
           3u,
           0x2200000u,
           0,
           0,
           (void *)0xFFFFFFFFFFFFFFFFLL);
  v4 = File;
  if ( File < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids,
        (unsigned int)File);
    return v4;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation) )
  {
    LastFailure = HrGetLastFailure();
    v4 = LastFailure;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 35;
LABEL_9:
      WPP_SF_d(v6[2], v7, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids, LastFailure);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  dwFileAttributes = FileInformation.dwFileAttributes;
  if ( (FileInformation.dwFileAttributes & 0x400) == 0 )
  {
LABEL_19:
    if ( (dwFileAttributes & 0x10) != 0 )
    {
      v4 = -2147024560;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids,
          (_DWORD)this,
          80);
      goto LABEL_28;
    }
    v11[0] = 1;
    if ( SetFileInformationByHandle(hFile, FileDispositionInfo, v11, 1u) )
    {
      v4 = 0;
    }
    else
    {
      LastFailure = HrGetLastFailure();
      v4 = LastFailure;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 39;
        goto LABEL_9;
      }
    }
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids, this);
  LastFailure = MpCmdUtils::DeleteReparsePoint(hFile);
  v4 = LastFailure;
  if ( !LastFailure )
  {
    dwFileAttributes = FileInformation.dwFileAttributes;
    goto LABEL_19;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 37;
    goto LABEL_9;
  }
LABEL_28:
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  return v4;
}

```

## disassembly

```asm
0x140024984  mov     r11, rsp
0x140024987  mov     [r11+10h], rbx
0x14002498b  mov     [r11+18h], rsi
0x14002498f  mov     [r11+20h], rdi
0x140024993  push    rbp
0x140024994  lea     rbp, [r11-5Fh]
0x140024998  sub     rsp, 90h
0x14002499f  mov     rax, cs:__security_cookie
0x1400249a6  xor     rax, rsp
0x1400249a9  mov     [rbp+57h+var_8], rax
0x1400249ad  mov     qword ptr [r11-60h], 0
0x1400249b5  mov     rsi, rcx
0x1400249b8  mov     qword ptr [r11-68h], 0
0x1400249c0  mov     rdx, rcx; void **
0x1400249c3  mov     [rsp+90h+var_68], 2200000h; unsigned int
0x1400249cb  lea     rcx, [rbp+57h+hFile]; this
0x1400249cf  xor     r9d, r9d; unsigned int
0x1400249d2  mov     [rsp+90h+var_70], 3; unsigned int
0x1400249da  mov     r8d, 10000000h; wchar_t *
0x1400249e0  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1400249e8  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x1400249ed  mov     ebx, eax
0x1400249ef  test    eax, eax
0x1400249f1  jns     short loc_140024A31
0x1400249f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249fa  lea     rdi, WPP_GLOBAL_Control
0x140024a01  cmp     rcx, rdi
0x140024a04  jz      loc_140024B9E
0x140024a0a  test    byte ptr [rcx+1Ch], 1
0x140024a0e  jz      loc_140024B9E
0x140024a14  mov     rcx, [rcx+10h]
0x140024a18  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024a1f  mov     edx, 22h ; '"'
0x140024a24  mov     r9d, eax
0x140024a27  call    WPP_SF_d
0x140024a2c  jmp     loc_140024B9E
0x140024a31  mov     rcx, [rbp+57h+hFile]; hFile
0x140024a35  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x140024a39  xorps   xmm0, xmm0
0x140024a3c  xor     eax, eax
0x140024a3e  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x140024a42  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x140024a45  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140024a49  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x140024a4d  call    cs:__imp_GetFileInformationByHandle
0x140024a53  test    eax, eax
0x140024a55  jnz     short loc_140024A9C
0x140024a57  call    HrGetLastFailure
0x140024a5c  mov     ebx, eax
0x140024a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a65  lea     rdi, WPP_GLOBAL_Control
0x140024a6c  cmp     rcx, rdi
0x140024a6f  jz      loc_140024B8E
0x140024a75  test    byte ptr [rcx+1Ch], 1
0x140024a79  jz      loc_140024B8E
0x140024a7f  mov     edx, 23h ; '#'
0x140024a84  mov     rcx, [rcx+10h]
0x140024a88  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024a8f  mov     r9d, eax
0x140024a92  call    WPP_SF_d
0x140024a97  jmp     loc_140024B8E
0x140024a9c  mov     eax, [rbp+57h+FileInformation.dwFileAttributes]
0x140024a9f  lea     rdi, WPP_GLOBAL_Control
0x140024aa6  bt      eax, 0Ah
0x140024aaa  jnb     short loc_140024B0C
0x140024aac  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ab3  cmp     rcx, rdi
0x140024ab6  jz      short loc_140024AD6
0x140024ab8  test    byte ptr [rcx+1Ch], 4
0x140024abc  jz      short loc_140024AD6
0x140024abe  mov     rcx, [rcx+10h]
0x140024ac2  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024ac9  mov     edx, 24h ; '$'
0x140024ace  mov     r9, rsi
0x140024ad1  call    WPP_SF_S
0x140024ad6  mov     rcx, [rbp+57h+hFile]; hDevice
0x140024ada  call    MpCmdUtils__DeleteReparsePoint
0x140024adf  mov     ebx, eax
0x140024ae1  test    eax, eax
0x140024ae3  jz      short loc_140024B09
0x140024ae5  mov     rcx, cs:WPP_GLOBAL_Control
0x140024aec  cmp     rcx, rdi
0x140024aef  jz      loc_140024B8E
0x140024af5  test    byte ptr [rcx+1Ch], 1
0x140024af9  jz      loc_140024B8E
0x140024aff  mov     edx, 25h ; '%'
0x140024b04  jmp     loc_140024A84
0x140024b09  mov     eax, [rbp+57h+FileInformation.dwFileAttributes]
0x140024b0c  test    al, 10h
0x140024b0e  jz      short loc_140024B49
0x140024b10  mov     ebx, 80070150h
0x140024b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b1c  cmp     rcx, rdi
0x140024b1f  jz      short loc_140024B8E
0x140024b21  test    byte ptr [rcx+1Ch], 1
0x140024b25  jz      short loc_140024B8E
0x140024b27  mov     rcx, [rcx+10h]
0x140024b2b  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024b32  mov     edx, 26h ; '&'
0x140024b37  mov     [rsp+90h+var_70], 80070150h
0x140024b3f  mov     r9, rsi
0x140024b42  call    WPP_SF_Sd
0x140024b47  jmp     short loc_140024B8E
0x140024b49  mov     rcx, [rbp+57h+hFile]; hFile
0x140024b4d  lea     r8, [rbp+57h+var_48]; lpFileInformation
0x140024b51  mov     r9d, 1; dwBufferSize
0x140024b57  mov     [rbp+57h+var_48], 1
0x140024b5b  lea     edx, [r9+3]; FileInformationClass
0x140024b5f  call    cs:__imp_SetFileInformationByHandle
0x140024b65  test    eax, eax
0x140024b67  jnz     short loc_140024B8C
0x140024b69  call    HrGetLastFailure
0x140024b6e  mov     ebx, eax
0x140024b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b77  cmp     rcx, rdi
0x140024b7a  jz      short loc_140024B8E
0x140024b7c  test    byte ptr [rcx+1Ch], 1
0x140024b80  jz      short loc_140024B8E
0x140024b82  mov     edx, 27h ; '''
0x140024b87  jmp     loc_140024A84
0x140024b8c  xor     ebx, ebx
0x140024b8e  mov     rcx, [rbp+57h+hFile]; hObject
0x140024b92  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140024b96  jz      short loc_140024B9E
0x140024b98  call    cs:__imp_CloseHandle
0x140024b9e  mov     eax, ebx
0x140024ba0  mov     rcx, [rbp+57h+var_8]
0x140024ba4  xor     rcx, rsp; StackCookie
0x140024ba7  call    __security_check_cookie
0x140024bac  lea     r11, [rsp+90h+var_s0]
0x140024bb4  mov     rbx, [r11+18h]
0x140024bb8  mov     rsi, [r11+20h]
0x140024bbc  mov     rdi, [r11+28h]
0x140024bc0  mov     rsp, r11
0x140024bc3  pop     rbp
0x140024bc4  retn
```
