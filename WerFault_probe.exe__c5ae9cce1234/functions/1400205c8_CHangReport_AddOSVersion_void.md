# CHangReport::_AddOSVersion(void)

- ea: `0x1400205c8`
- end: `0x1400207ef`
- name: `?_AddOSVersion@CHangReport@@AEAAJXZ`
- size: `551`
- prototype: `__int64 __fastcall(CHangReport *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x140020fc0`

## callees

- `0x140002470`
- `0x1400135c0`
- `0x140014474`
- `0x140014ddc`
- `0x1400205c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400206cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400206cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400207cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400207cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400206c3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400206c3`
- `wer!WerpAddFile` at `0x140020785`
- `wer!WerpAddFile` at `0x140020785`

## string_xrefs

- `0x140020627`: `.version.xml`
- `0x140020761`: `version.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHangReport::_AddOSVersion(CHangReport *this)
{
  int TempFile; // ebx
  HANDLE v3; // rdi
  CUserModeHangReport *v4; // rcx
  __int64 v5; // rdx
  signed int LastError; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+58h] [rbp-A8h]
  wchar_t v13[264]; // [rsp+60h] [rbp-A0h] BYREF

  hFile = 0;
  v11 = -1;
  v12 = 0;
  v13[0] = 0;
  TempFile = UtilGetTempFile(&hFile, 0, (__int64)L".version.xml", v13, (__int64)lpOverlapped, 0, 1u, 0);
  v3 = hFile;
  if ( TempFile >= 0 )
  {
    if ( hFile == (HANDLE)-1LL )
    {
      TempFile = -2147024809;
    }
    else
    {
      v11 = (__int64)hFile;
      v12 = 0;
      NumberOfBytesWritten = 0;
      if ( WriteFile(hFile, &unk_1400640E0, 0x50u, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == 80 )
        {
          TempFile = UtilWriteOSVersionInfo((struct CXMLWriter *)&v11);
          if ( TempFile >= 0 )
          {
            TempFile = WerpAddFile(*((_QWORD *)this + 3055), v13, 5);
            if ( TempFile >= 0 )
            {
              TempFile = 0;
            }
            else
            {
              v4 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v5 = 93;
                goto LABEL_5;
              }
            }
          }
          else
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v5 = 92;
              goto LABEL_5;
            }
          }
          goto LABEL_28;
        }
        TempFile = -2147024867;
      }
      else
      {
        LastError = GetLastError();
        TempFile = LastError;
        if ( LastError > 0 )
          TempFile = (unsigned __int16)LastError | 0x80070000;
        if ( TempFile >= 0 )
          TempFile = -2147467259;
      }
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 91;
      goto LABEL_5;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 90;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids, (unsigned int)TempFile);
    }
  }
LABEL_28:
  v11 = -1;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x1400205c8  push    rbp
0x1400205ca  push    rbx
0x1400205cb  push    rsi
0x1400205cc  push    rdi
0x1400205cd  lea     rbp, [rsp-188h]
0x1400205d5  sub     rsp, 288h
0x1400205dc  mov     rax, cs:__security_cookie
0x1400205e3  xor     rax, rsp
0x1400205e6  mov     [rbp+1A0h+var_30], rax
0x1400205ed  mov     rsi, rcx
0x1400205f0  mov     [rsp+2A0h+hFile], 0
0x1400205f9  mov     [rsp+2A0h+var_250], 0FFFFFFFFFFFFFFFFh
0x140020602  mov     [rsp+2A0h+var_248], 0
0x14002060a  xor     eax, eax
0x14002060c  mov     [rsp+2A0h+var_240], ax
0x140020611  mov     [rsp+2A0h+var_268], eax
0x140020615  mov     [rsp+2A0h+var_270], 1
0x14002061d  mov     [rsp+2A0h+var_278], rax
0x140020622  lea     r9, [rsp+2A0h+var_240]
0x140020627  lea     r8, aVersionXml_0; ".version.xml"
0x14002062e  xor     edx, edx
0x140020630  lea     rcx, [rsp+2A0h+hFile]
0x140020635  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x14002063a  mov     ebx, eax
0x14002063c  mov     rdi, [rsp+2A0h+hFile]
0x140020641  test    eax, eax
0x140020643  jns     short loc_140020683
0x140020645  lea     rax, WPP_GLOBAL_Control
0x14002064c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020653  cmp     rcx, rax
0x140020656  jz      loc_1400207B6
0x14002065c  test    byte ptr [rcx+1Ch], 1
0x140020660  jz      loc_1400207B6
0x140020666  mov     edx, 5Ah ; 'Z'
0x14002066b  mov     r9d, ebx
0x14002066e  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020675  mov     rcx, [rcx+10h]
0x140020679  call    WPP_SF_d
0x14002067e  jmp     loc_1400207B6
0x140020683  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140020687  jnz     short loc_140020690
0x140020689  mov     ebx, 80070057h
0x14002068e  jmp     short loc_1400206FA
0x140020690  mov     [rsp+2A0h+var_250], rdi
0x140020695  mov     [rsp+2A0h+var_248], 0
0x14002069d  mov     [rsp+2A0h+NumberOfBytesWritten], 0
0x1400206a5  mov     [rsp+2A0h+lpOverlapped], 0; lpOverlapped
0x1400206ae  lea     r9, [rsp+2A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400206b3  mov     r8d, 50h ; 'P'; nNumberOfBytesToWrite
0x1400206b9  lea     rdx, unk_1400640E0; lpBuffer
0x1400206c0  mov     rcx, rdi; hFile
0x1400206c3  call    cs:__imp_WriteFile
0x1400206c9  test    eax, eax
0x1400206cb  jnz     short loc_1400206EE
0x1400206cd  call    cs:__imp_GetLastError
0x1400206d3  mov     ebx, eax
0x1400206d5  test    eax, eax
0x1400206d7  jle     short loc_1400206E2
0x1400206d9  movzx   ebx, ax
0x1400206dc  or      ebx, 80070000h
0x1400206e2  mov     eax, 80004005h
0x1400206e7  test    ebx, ebx
0x1400206e9  cmovns  ebx, eax
0x1400206ec  jmp     short loc_1400206FA
0x1400206ee  cmp     [rsp+2A0h+NumberOfBytesWritten], 50h ; 'P'
0x1400206f3  jz      short loc_140020725
0x1400206f5  mov     ebx, 8007001Dh
0x1400206fa  lea     rax, WPP_GLOBAL_Control
0x140020701  mov     rcx, cs:WPP_GLOBAL_Control
0x140020708  cmp     rcx, rax
0x14002070b  jz      loc_1400207B6
0x140020711  test    byte ptr [rcx+1Ch], 1
0x140020715  jz      loc_1400207B6
0x14002071b  mov     edx, 5Bh ; '['
0x140020720  jmp     loc_14002066B
0x140020725  lea     rcx, [rsp+2A0h+var_250]; struct CXMLWriter *
0x14002072a  call    ?UtilWriteOSVersionInfo@@YAJPEAVCXMLWriter@@@Z; UtilWriteOSVersionInfo(CXMLWriter *)
0x14002072f  mov     ebx, eax
0x140020731  test    eax, eax
0x140020733  jns     short loc_140020758
0x140020735  lea     rax, WPP_GLOBAL_Control
0x14002073c  mov     rcx, cs:WPP_GLOBAL_Control
0x140020743  cmp     rcx, rax
0x140020746  jz      short loc_1400207B6
0x140020748  test    byte ptr [rcx+1Ch], 1
0x14002074c  jz      short loc_1400207B6
0x14002074e  mov     edx, 5Ch ; '\'
0x140020753  jmp     loc_14002066B
0x140020758  mov     [rsp+2A0h+var_278], 0
0x140020761  lea     rax, aVersionXml; "version.xml"
0x140020768  mov     [rsp+2A0h+lpOverlapped], rax
0x14002076d  mov     r9d, 40003h
0x140020773  mov     r8d, 5
0x140020779  lea     rdx, [rsp+2A0h+var_240]
0x14002077e  mov     rcx, [rsi+5F78h]
0x140020785  call    cs:__imp_WerpAddFile
0x14002078b  mov     ebx, eax
0x14002078d  test    eax, eax
0x14002078f  jns     short loc_1400207B4
0x140020791  lea     rax, WPP_GLOBAL_Control
0x140020798  mov     rcx, cs:WPP_GLOBAL_Control
0x14002079f  cmp     rcx, rax
0x1400207a2  jz      short loc_1400207B6
0x1400207a4  test    byte ptr [rcx+1Ch], 1
0x1400207a8  jz      short loc_1400207B6
0x1400207aa  mov     edx, 5Dh ; ']'
0x1400207af  jmp     loc_14002066B
0x1400207b4  xor     ebx, ebx
0x1400207b6  mov     [rsp+2A0h+var_250], 0FFFFFFFFFFFFFFFFh
0x1400207bf  lea     rax, [rdi+1]
0x1400207c3  cmp     rax, 1
0x1400207c7  jbe     short loc_1400207D2
0x1400207c9  mov     rcx, rdi; hObject
0x1400207cc  call    cs:__imp_CloseHandle
0x1400207d2  mov     eax, ebx
0x1400207d4  mov     rcx, [rbp+1A0h+var_30]
0x1400207db  xor     rcx, rsp; StackCookie
0x1400207de  call    __security_check_cookie
0x1400207e3  add     rsp, 288h
0x1400207ea  pop     rdi
0x1400207eb  pop     rsi
0x1400207ec  pop     rbx
0x1400207ed  pop     rbp
0x1400207ee  retn
```
