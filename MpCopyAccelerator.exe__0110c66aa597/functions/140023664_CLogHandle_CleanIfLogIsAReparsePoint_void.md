# CLogHandle::CleanIfLogIsAReparsePoint(void)

- ea: `0x140023664`
- end: `0x140023809`
- name: `?CleanIfLogIsAReparsePoint@CLogHandle@@AEAAJXZ`
- size: `421`
- prototype: `__int64 __fastcall(CLogHandle *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14002380c`

## callees

- `0x14000436c`
- `0x14000493c`
- `0x140005c20`
- `0x14001da70`
- `0x14001dac4`
- `0x140023664`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x14002378b`
- `KERNEL32!SetFileInformationByHandle` at `0x14002378b`
- `KERNEL32!GetFileInformationByHandle` at `0x1400236f7`
- `KERNEL32!GetFileInformationByHandle` at `0x1400236f7`
- `KERNEL32!CloseHandle` at `0x1400237dc`
- `KERNEL32!CloseHandle` at `0x1400237dc`

## pseudocode

```c
__int64 __fastcall CLogHandle::CleanIfLogIsAReparsePoint(CLogHandle *this)
{
  void **v1; // rdx
  int File; // edi
  unsigned int v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int LastFailure; // eax
  void *v10; // [rsp+48h] [rbp+7h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp+Fh] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp+17h] BYREF

  v1 = (void **)*((_QWORD *)this + 7);
  hFile = (HANDLE)-1LL;
  File = CommonUtil::UtilCreateFile((CommonUtil *)&hFile, v1, (const wchar_t *)0x10080, 7u, 4u, 0x200000u, 0, 0, v10);
  if ( File >= 0 )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(hFile, &FileInformation) )
    {
      if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids,
            *((_QWORD *)this + 7));
        LOBYTE(v10) = 1;
        if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, &v10, 1u) )
        {
          File = HrGetLastFailure();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            LastFailure = HrGetLastFailure();
            v5 = WPP_GLOBAL_Control;
            v6 = 21;
            v7 = LastFailure;
            goto LABEL_14;
          }
        }
      }
    }
    else
    {
      v4 = HrGetLastFailure();
      File = v4;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 19;
        v7 = v4;
LABEL_14:
        WPP_SF_d(v5[2], v6, &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids, v7);
      }
    }
  }
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  return (unsigned int)File;
}

```

## disassembly

```asm
0x140023664  mov     r11, rsp
0x140023667  mov     [r11+10h], rbx
0x14002366b  mov     [r11+18h], rsi
0x14002366f  mov     [r11+20h], rdi
0x140023673  push    rbp
0x140023674  lea     rbp, [r11-5Fh]
0x140023678  sub     rsp, 90h
0x14002367f  mov     rax, cs:__security_cookie
0x140023686  xor     rax, rsp
0x140023689  mov     [rbp+57h+var_8], rax
0x14002368d  mov     rdx, [rcx+38h]; void **
0x140023691  mov     rsi, rcx
0x140023694  mov     qword ptr [r11-60h], 0
0x14002369c  lea     rcx, [rbp+57h+hFile]; this
0x1400236a0  mov     qword ptr [r11-68h], 0
0x1400236a8  mov     r9d, 7; unsigned int
0x1400236ae  mov     [rsp+90h+var_68], 200000h; unsigned int
0x1400236b6  mov     r8d, 10080h; wchar_t *
0x1400236bc  mov     [rsp+90h+var_70], 4; unsigned int
0x1400236c4  mov     [rbp+57h+hFile], 0FFFFFFFFFFFFFFFFh
0x1400236cc  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x1400236d1  mov     edi, eax
0x1400236d3  test    eax, eax
0x1400236d5  js      loc_1400237D2
0x1400236db  mov     rcx, [rbp+57h+hFile]; hFile
0x1400236df  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1400236e3  xorps   xmm0, xmm0
0x1400236e6  xor     eax, eax
0x1400236e8  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1400236ec  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1400236ef  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1400236f3  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1400236f7  call    cs:__imp_GetFileInformationByHandle
0x1400236fd  test    eax, eax
0x1400236ff  jnz     short loc_140023736
0x140023701  call    HrGetLastFailure
0x140023706  mov     edi, eax
0x140023708  mov     rcx, cs:WPP_GLOBAL_Control
0x14002370f  lea     rbx, WPP_GLOBAL_Control
0x140023716  cmp     rcx, rbx
0x140023719  jz      loc_1400237D2
0x14002371f  test    byte ptr [rcx+1Ch], 1
0x140023723  jz      loc_1400237D2
0x140023729  mov     edx, 13h
0x14002372e  mov     r9d, eax
0x140023731  jmp     loc_1400237C2
0x140023736  test    [rbp+57h+FileInformation.dwFileAttributes], 400h
0x14002373d  jz      loc_1400237D2
0x140023743  mov     rcx, cs:WPP_GLOBAL_Control
0x14002374a  lea     rbx, WPP_GLOBAL_Control
0x140023751  cmp     rcx, rbx
0x140023754  jz      short loc_140023775
0x140023756  test    byte ptr [rcx+1Ch], 4
0x14002375a  jz      short loc_140023775
0x14002375c  mov     r9, [rsi+38h]
0x140023760  lea     r8, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x140023767  mov     rcx, [rcx+10h]
0x14002376b  mov     edx, 14h
0x140023770  call    WPP_SF_S
0x140023775  mov     rcx, [rbp+57h+hFile]; hFile
0x140023779  lea     r8, [rbp+57h+var_50]; lpFileInformation
0x14002377d  mov     r9d, 1; dwBufferSize
0x140023783  mov     byte ptr [rbp+57h+var_50], 1
0x140023787  lea     edx, [r9+3]; FileInformationClass
0x14002378b  call    cs:__imp_SetFileInformationByHandle
0x140023791  test    eax, eax
0x140023793  jnz     short loc_1400237D2
0x140023795  call    HrGetLastFailure
0x14002379a  mov     edi, eax
0x14002379c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237a3  cmp     rcx, rbx
0x1400237a6  jz      short loc_1400237D2
0x1400237a8  test    byte ptr [rcx+1Ch], 1
0x1400237ac  jz      short loc_1400237D2
0x1400237ae  call    HrGetLastFailure
0x1400237b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237ba  mov     edx, 15h
0x1400237bf  mov     r9d, eax
0x1400237c2  mov     rcx, [rcx+10h]
0x1400237c6  lea     r8, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x1400237cd  call    WPP_SF_d
0x1400237d2  mov     rcx, [rbp+57h+hFile]; hObject
0x1400237d6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400237da  jz      short loc_1400237E2
0x1400237dc  call    cs:__imp_CloseHandle
0x1400237e2  mov     eax, edi
0x1400237e4  mov     rcx, [rbp+57h+var_8]
0x1400237e8  xor     rcx, rsp; StackCookie
0x1400237eb  call    __security_check_cookie
0x1400237f0  lea     r11, [rsp+90h+var_s0]
0x1400237f8  mov     rbx, [r11+18h]
0x1400237fc  mov     rsi, [r11+20h]
0x140023800  mov     rdi, [r11+28h]
0x140023804  mov     rsp, r11
0x140023807  pop     rbp
0x140023808  retn
```
