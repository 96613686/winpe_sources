# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14000cc0c`
- end: `0x14000cfbe`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hFile, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x14000e8c4`

## callees

- `0x14000113c`
- `0x1400023d0`
- `0x1400023f4`
- `0x140008d3c`
- `0x14000cc0c`
- `0x14000cfc4`
- `0x14000e1e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cd17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cede`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000cd07`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000ceb5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000cd07`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000ceb5`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  int FinalPathOnUnmountedVolume; // ebx
  int *v5; // rax
  int *v6; // rcx
  char *v7; // rdx
  DWORD FinalPathNameByHandleW; // eax
  unsigned __int64 v9; // rdi
  signed int LastError; // eax
  WCHAR *v11; // rdx
  LPWSTR v12; // r8
  unsigned __int64 v13; // rax
  DWORD v14; // eax
  int v16; // [rsp+30h] [rbp-39h] BYREF
  int v17; // [rsp+34h] [rbp-35h] BYREF
  LPWSTR lpszFilePath; // [rsp+38h] [rbp-31h] BYREF
  WCHAR *v19; // [rsp+40h] [rbp-29h]
  _WORD v20[12]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]
  int *v24; // [rsp+90h] [rbp+27h]
  __int64 v25; // [rsp+98h] [rbp+2Fh]

  lpszFilePath = v20;
  v19 = v20;
  v20[0] = 0;
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(&lpszFilePath, 0x105u) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
    {
      v17 = -2147024882;
      v5 = &v17;
      v16 = 261;
      v6 = &v16;
      v7 = &byte_140015EB7;
LABEL_6:
      v22 = v6;
      v24 = v5;
      v23 = 4;
      v25 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, v7, 0, 0, 4, v21);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath, v19 - lpszFilePath, 0);
  v9 = FinalPathNameByHandleW;
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
    FinalPathOnUnmountedVolume = LastError;
    if ( LastError == 3 )
    {
      FinalPathOnUnmountedVolume = _werDetail::UtilGetFinalPathOnUnmountedVolume(hFile, a2);
    }
    else
    {
      if ( LastError > 0 )
        FinalPathOnUnmountedVolume = (unsigned __int16)LastError | 0x80070000;
      if ( FinalPathOnUnmountedVolume >= 0 )
        FinalPathOnUnmountedVolume = -2147467259;
      if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
      {
        v16 = FinalPathOnUnmountedVolume;
        v22 = &v16;
        v23 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, byte_140015E83, 0, 0, 3, v21);
      }
    }
    goto LABEL_44;
  }
  v11 = v19;
  v12 = lpszFilePath;
  v13 = v19 - lpszFilePath;
  if ( v9 == v13 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
    {
      v16 = -2147418113;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, &word_140015E46, 0, 0, 3, v21);
    }
    goto LABEL_44;
  }
  if ( v9 <= v13 )
    goto LABEL_41;
  if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(&lpszFilePath, v9) )
  {
    v14 = GetFinalPathNameByHandleW(hFile, lpszFilePath, v19 - lpszFilePath, 0);
    v9 = v14;
    if ( !v14 )
    {
      FinalPathOnUnmountedVolume = GetLastError();
      if ( FinalPathOnUnmountedVolume <= 0 )
      {
LABEL_35:
        if ( FinalPathOnUnmountedVolume >= 0 )
          FinalPathOnUnmountedVolume = -2147467259;
        if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
        {
          v16 = FinalPathOnUnmountedVolume;
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_14001A000, byte_140015DCB, 0, 0, 3, v21);
        }
        goto LABEL_44;
      }
LABEL_34:
      FinalPathOnUnmountedVolume = (unsigned __int16)FinalPathOnUnmountedVolume | 0x80070000;
      goto LABEL_35;
    }
    v11 = v19;
    v12 = lpszFilePath;
    if ( v14 >= (unsigned __int64)(v19 - lpszFilePath) )
    {
      LOWORD(FinalPathOnUnmountedVolume) = 111;
      goto LABEL_34;
    }
LABEL_41:
    if ( (unsigned int)v9 > (unsigned __int64)(v11 - v12) )
      __int2c();
    v19 = &v12[v9];
    *v19 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, (__int64)&lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_44;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_14001A000 > 2 && (qword_14001A010 & 8) != 0 && (qword_14001A018 & 8) == qword_14001A018 )
  {
    v16 = -2147024882;
    v5 = &v16;
    v17 = v9;
    v6 = &v17;
    v7 = &byte_140015DFF;
    goto LABEL_6;
  }
LABEL_44:
  if ( lpszFilePath != v20 )
    operator delete(lpszFilePath, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x14000cc0c  mov     [rsp-8+arg_10], rbx
0x14000cc11  mov     [rsp-8+arg_18], rsi
0x14000cc16  push    rbp
0x14000cc17  push    rdi
0x14000cc18  push    r14
0x14000cc1a  lea     rbp, [rsp-47h]
0x14000cc1f  sub     rsp, 0B0h
0x14000cc26  mov     rax, cs:__security_cookie
0x14000cc2d  xor     rax, rsp
0x14000cc30  mov     [rbp+57h+var_20], rax
0x14000cc34  lea     rax, [rbp+57h+var_78]
0x14000cc38  mov     r14, rdx
0x14000cc3b  mov     [rbp+57h+lpszFilePath], rax
0x14000cc3f  mov     rsi, rcx
0x14000cc42  lea     rax, [rbp+57h+var_78]
0x14000cc46  mov     edi, 105h
0x14000cc4b  mov     [rbp+57h+var_80], rax
0x14000cc4f  lea     rcx, [rbp+57h+lpszFilePath]
0x14000cc53  xor     eax, eax
0x14000cc55  mov     edx, edi
0x14000cc57  mov     [rbp+57h+var_78], ax
0x14000cc5b  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000cc60  test    al, al
0x14000cc62  jnz     loc_14000CCF3
0x14000cc68  mov     eax, cs:dword_14001A000
0x14000cc6e  mov     ebx, 8007000Eh
0x14000cc73  cmp     eax, 2
0x14000cc76  jbe     loc_14000CF7F
0x14000cc7c  mov     rcx, cs:qword_14001A018
0x14000cc83  mov     rax, cs:qword_14001A010
0x14000cc8a  test    al, 8
0x14000cc8c  jz      loc_14000CF7F
0x14000cc92  mov     rax, rcx
0x14000cc95  and     eax, 8
0x14000cc98  cmp     rax, rcx
0x14000cc9b  jnz     loc_14000CF7F
0x14000cca1  mov     [rbp+57h+var_8C], 8007000Eh
0x14000cca8  lea     rax, [rbp+57h+var_8C]
0x14000ccac  mov     [rbp+57h+var_90], edi
0x14000ccaf  lea     rcx, [rbp+57h+var_90]
0x14000ccb3  lea     rdx, byte_140015EB7
0x14000ccba  mov     [rbp+57h+var_40], rcx
0x14000ccbe  lea     rcx, [rbp+57h+var_60]
0x14000ccc2  mov     [rbp+57h+var_30], rax
0x14000ccc6  mov     eax, 4
0x14000cccb  mov     [rsp+0C0h+var_98], rcx
0x14000ccd0  mov     [rsp+0C0h+var_A0], eax
0x14000ccd4  mov     [rbp+57h+var_38], rax
0x14000ccd8  mov     [rbp+57h+var_28], rax
0x14000ccdc  xor     r9d, r9d
0x14000ccdf  lea     rcx, dword_14001A000
0x14000cce6  xor     r8d, r8d
0x14000cce9  call    _tlgWriteTransfer_EventWriteTransfer
0x14000ccee  jmp     loc_14000CF7F
0x14000ccf3  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x14000ccf7  xor     r9d, r9d; dwFlags
0x14000ccfa  mov     r8, [rbp+57h+var_80]
0x14000ccfe  mov     rcx, rsi; hFile
0x14000cd01  sub     r8, rdx
0x14000cd04  sar     r8, 1; cchFilePath
0x14000cd07  call    cs:__imp_GetFinalPathNameByHandleW
0x14000cd0d  mov     edi, eax
0x14000cd0f  test    eax, eax
0x14000cd11  jnz     loc_14000CDB1
0x14000cd17  call    cs:__imp_GetLastError
0x14000cd1d  mov     ebx, eax
0x14000cd1f  cmp     eax, 3
0x14000cd22  jnz     short loc_14000CD36
0x14000cd24  mov     rdx, r14
0x14000cd27  mov     rcx, rsi
0x14000cd2a  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14000cd2f  mov     ebx, eax
0x14000cd31  jmp     loc_14000CF7F
0x14000cd36  test    eax, eax
0x14000cd38  jle     short loc_14000CD43
0x14000cd3a  movzx   ebx, ax
0x14000cd3d  or      ebx, 80070000h
0x14000cd43  test    ebx, ebx
0x14000cd45  mov     eax, 80004005h
0x14000cd4a  cmovns  ebx, eax
0x14000cd4d  mov     eax, cs:dword_14001A000
0x14000cd53  cmp     eax, 2
0x14000cd56  jbe     loc_14000CF7F
0x14000cd5c  mov     rcx, cs:qword_14001A018
0x14000cd63  mov     rax, cs:qword_14001A010
0x14000cd6a  test    al, 8
0x14000cd6c  jz      loc_14000CF7F
0x14000cd72  mov     rax, rcx
0x14000cd75  and     eax, 8
0x14000cd78  cmp     rax, rcx
0x14000cd7b  jnz     loc_14000CF7F
0x14000cd81  lea     rax, [rbp+57h+var_90]
0x14000cd85  mov     [rbp+57h+var_90], ebx
0x14000cd88  mov     [rbp+57h+var_40], rax
0x14000cd8c  lea     rdx, byte_140015E83
0x14000cd93  lea     rax, [rbp+57h+var_60]
0x14000cd97  mov     [rbp+57h+var_38], 4
0x14000cd9f  mov     [rsp+0C0h+var_98], rax
0x14000cda4  mov     [rsp+0C0h+var_A0], 3
0x14000cdac  jmp     loc_14000CCDC
0x14000cdb1  mov     rdx, [rbp+57h+var_80]
0x14000cdb5  mov     r8, [rbp+57h+lpszFilePath]
0x14000cdb9  mov     rax, rdx
0x14000cdbc  sub     rax, r8
0x14000cdbf  sar     rax, 1
0x14000cdc2  cmp     rdi, rax
0x14000cdc5  jnz     short loc_14000CE34
0x14000cdc7  mov     eax, cs:dword_14001A000
0x14000cdcd  mov     ebx, 8000FFFFh
0x14000cdd2  cmp     eax, 2
0x14000cdd5  jbe     loc_14000CF7F
0x14000cddb  mov     rcx, cs:qword_14001A018
0x14000cde2  mov     rax, cs:qword_14001A010
0x14000cde9  test    al, 8
0x14000cdeb  jz      loc_14000CF7F
0x14000cdf1  mov     rax, rcx
0x14000cdf4  and     eax, 8
0x14000cdf7  cmp     rax, rcx
0x14000cdfa  jnz     loc_14000CF7F
0x14000ce00  lea     rax, [rbp+57h+var_90]
0x14000ce04  mov     [rbp+57h+var_90], 8000FFFFh
0x14000ce0b  mov     [rbp+57h+var_40], rax
0x14000ce0f  lea     rdx, word_140015E46
0x14000ce16  lea     rax, [rbp+57h+var_60]
0x14000ce1a  mov     [rbp+57h+var_38], 4
0x14000ce22  mov     [rsp+0C0h+var_98], rax
0x14000ce27  mov     [rsp+0C0h+var_A0], 3
0x14000ce2f  jmp     loc_14000CCDC
0x14000ce34  jbe     loc_14000CF55
0x14000ce3a  mov     rdx, rdi
0x14000ce3d  lea     rcx, [rbp+57h+lpszFilePath]
0x14000ce41  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000ce46  test    al, al
0x14000ce48  jnz     short loc_14000CEA1
0x14000ce4a  mov     eax, cs:dword_14001A000
0x14000ce50  mov     ebx, 8007000Eh
0x14000ce55  cmp     eax, 2
0x14000ce58  jbe     loc_14000CF7F
0x14000ce5e  mov     rcx, cs:qword_14001A018
0x14000ce65  mov     rax, cs:qword_14001A010
0x14000ce6c  test    al, 8
0x14000ce6e  jz      loc_14000CF7F
0x14000ce74  mov     rax, rcx
0x14000ce77  and     eax, 8
0x14000ce7a  cmp     rax, rcx
0x14000ce7d  jnz     loc_14000CF7F
0x14000ce83  mov     [rbp+57h+var_90], 8007000Eh
0x14000ce8a  lea     rax, [rbp+57h+var_90]
0x14000ce8e  mov     [rbp+57h+var_8C], edi
0x14000ce91  lea     rcx, [rbp+57h+var_8C]
0x14000ce95  lea     rdx, byte_140015DFF
0x14000ce9c  jmp     loc_14000CCBA
0x14000cea1  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x14000cea5  xor     r9d, r9d; dwFlags
0x14000cea8  mov     r8, [rbp+57h+var_80]
0x14000ceac  mov     rcx, rsi; hFile
0x14000ceaf  sub     r8, rdx
0x14000ceb2  sar     r8, 1; cchFilePath
0x14000ceb5  call    cs:__imp_GetFinalPathNameByHandleW
0x14000cebb  mov     edi, eax
0x14000cebd  test    eax, eax
0x14000cebf  jz      short loc_14000CEDE
0x14000cec1  mov     rdx, [rbp+57h+var_80]
0x14000cec5  mov     r8, [rbp+57h+lpszFilePath]
0x14000cec9  mov     rcx, rdx
0x14000cecc  sub     rcx, r8
0x14000cecf  sar     rcx, 1
0x14000ced2  cmp     rdi, rcx
0x14000ced5  jb      short loc_14000CF55
0x14000ced7  mov     ebx, 6Fh ; 'o'
0x14000cedc  jmp     short loc_14000CEEA
0x14000cede  call    cs:__imp_GetLastError
0x14000cee4  mov     ebx, eax
0x14000cee6  test    eax, eax
0x14000cee8  jle     short loc_14000CEF3
0x14000ceea  movzx   ebx, bx
0x14000ceed  or      ebx, 80070000h
0x14000cef3  test    ebx, ebx
0x14000cef5  mov     eax, 80004005h
0x14000cefa  cmovns  ebx, eax
0x14000cefd  mov     eax, cs:dword_14001A000
0x14000cf03  cmp     eax, 2
0x14000cf06  jbe     short loc_14000CF7F
0x14000cf08  mov     rcx, cs:qword_14001A018
0x14000cf0f  mov     rax, cs:qword_14001A010
0x14000cf16  test    al, 8
0x14000cf18  jz      short loc_14000CF7F
0x14000cf1a  mov     rax, rcx
0x14000cf1d  and     eax, 8
0x14000cf20  cmp     rax, rcx
0x14000cf23  jnz     short loc_14000CF7F
0x14000cf25  lea     rax, [rbp+57h+var_90]
0x14000cf29  mov     [rbp+57h+var_90], ebx
0x14000cf2c  mov     [rbp+57h+var_40], rax
0x14000cf30  lea     rdx, byte_140015DCB
0x14000cf37  lea     rax, [rbp+57h+var_60]
0x14000cf3b  mov     [rbp+57h+var_38], 4
0x14000cf43  mov     [rsp+0C0h+var_98], rax
0x14000cf48  mov     [rsp+0C0h+var_A0], 3
0x14000cf50  jmp     loc_14000CCDC
0x14000cf55  sub     rdx, r8
0x14000cf58  mov     eax, edi
0x14000cf5a  sar     rdx, 1
0x14000cf5d  cmp     rax, rdx
0x14000cf60  jbe     short loc_14000CF64
0x14000cf62  int     2Ch; Windows NT - assertion failure
0x14000cf64  lea     rcx, [r8+rdi*2]
0x14000cf68  xor     eax, eax
0x14000cf6a  mov     [rbp+57h+var_80], rcx
0x14000cf6e  lea     rdx, [rbp+57h+lpszFilePath]
0x14000cf72  mov     [rcx], ax
0x14000cf75  mov     rcx, r14
0x14000cf78  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14000cf7d  xor     ebx, ebx
0x14000cf7f  mov     rcx, [rbp+57h+lpszFilePath]; void *
0x14000cf83  lea     rax, [rbp+57h+var_78]
0x14000cf87  cmp     rcx, rax
0x14000cf8a  jz      short loc_14000CF98
0x14000cf8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000cf93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000cf98  mov     eax, ebx
0x14000cf9a  mov     rcx, [rbp+57h+var_20]
0x14000cf9e  xor     rcx, rsp; StackCookie
0x14000cfa1  call    __security_check_cookie
0x14000cfa6  lea     r11, [rsp+0C0h+var_10]
0x14000cfae  mov     rbx, [r11+30h]
0x14000cfb2  mov     rsi, [r11+38h]
0x14000cfb6  mov     rsp, r11
0x14000cfb9  pop     r14
0x14000cfbb  pop     rdi
0x14000cfbc  pop     rbp
0x14000cfbd  retn
```
