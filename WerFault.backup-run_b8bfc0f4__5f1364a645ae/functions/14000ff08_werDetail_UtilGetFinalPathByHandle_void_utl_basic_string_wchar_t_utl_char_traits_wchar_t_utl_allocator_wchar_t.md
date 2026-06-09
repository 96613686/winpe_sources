# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14000ff08`
- end: `0x1400102ba`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x14001280c`
- `0x1400146f0`

## callees

- `0x14000113c`
- `0x140002470`
- `0x140002728`
- `0x14000cc58`
- `0x14000e6dc`
- `0x14000ff08`
- `0x1400102c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400101da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400101da`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010003`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1400101b1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010003`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1400101b1`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathByHandle(HANDLE hFile, __int64 a2)
{
  int FinalPathOnUnmountedVolume; // ebx
  int *v5; // rax
  int *v6; // rcx
  void *v7; // rdx
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
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      v17 = -2147024882;
      v5 = &v17;
      v16 = 261;
      v6 = &v16;
      v7 = &unk_14006EBA0;
LABEL_6:
      v22 = v6;
      v24 = v5;
      v23 = 4;
      v25 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, v7, 0, 0, 4, v21);
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
      if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
      {
        v16 = FinalPathOnUnmountedVolume;
        v22 = &v16;
        v23 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &dword_14006EB6C, 0, 0, 3, v21);
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
    if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    {
      v16 = -2147418113;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &byte_14006EB2F, 0, 0, 3, v21);
    }
    goto LABEL_44;
  }
  if ( v9 <= v13 )
    goto LABEL_41;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &lpszFilePath,
                          v9) )
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
        if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
        {
          v16 = FinalPathOnUnmountedVolume;
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &dword_14006EAB4, 0, 0, 3, v21);
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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_44;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
  {
    v16 = -2147024882;
    v5 = &v16;
    v17 = v9;
    v6 = &v17;
    v7 = &unk_14006EAE8;
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
0x14000ff08  mov     [rsp-8+arg_10], rbx
0x14000ff0d  mov     [rsp-8+arg_18], rsi
0x14000ff12  push    rbp
0x14000ff13  push    rdi
0x14000ff14  push    r14
0x14000ff16  lea     rbp, [rsp-47h]
0x14000ff1b  sub     rsp, 0B0h
0x14000ff22  mov     rax, cs:__security_cookie
0x14000ff29  xor     rax, rsp
0x14000ff2c  mov     [rbp+57h+var_20], rax
0x14000ff30  lea     rax, [rbp+57h+var_78]
0x14000ff34  mov     r14, rdx
0x14000ff37  mov     [rbp+57h+lpszFilePath], rax
0x14000ff3b  mov     rsi, rcx
0x14000ff3e  lea     rax, [rbp+57h+var_78]
0x14000ff42  mov     edi, 105h
0x14000ff47  mov     [rbp+57h+var_80], rax
0x14000ff4b  lea     rcx, [rbp+57h+lpszFilePath]
0x14000ff4f  xor     eax, eax
0x14000ff51  mov     edx, edi
0x14000ff53  mov     [rbp+57h+var_78], ax
0x14000ff57  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000ff5c  test    al, al
0x14000ff5e  jnz     loc_14000FFEF
0x14000ff64  mov     eax, cs:dword_14007A000
0x14000ff6a  mov     ebx, 8007000Eh
0x14000ff6f  cmp     eax, 2
0x14000ff72  jbe     loc_14001027B
0x14000ff78  mov     rcx, cs:qword_14007A018
0x14000ff7f  mov     rax, cs:qword_14007A010
0x14000ff86  test    al, 8
0x14000ff88  jz      loc_14001027B
0x14000ff8e  mov     rax, rcx
0x14000ff91  and     eax, 8
0x14000ff94  cmp     rax, rcx
0x14000ff97  jnz     loc_14001027B
0x14000ff9d  mov     [rbp+57h+var_8C], 8007000Eh
0x14000ffa4  lea     rax, [rbp+57h+var_8C]
0x14000ffa8  mov     [rbp+57h+var_90], edi
0x14000ffab  lea     rcx, [rbp+57h+var_90]
0x14000ffaf  lea     rdx, unk_14006EBA0
0x14000ffb6  mov     [rbp+57h+var_40], rcx
0x14000ffba  lea     rcx, [rbp+57h+var_60]
0x14000ffbe  mov     [rbp+57h+var_30], rax
0x14000ffc2  mov     eax, 4
0x14000ffc7  mov     [rsp+0C0h+var_98], rcx
0x14000ffcc  mov     [rsp+0C0h+var_A0], eax
0x14000ffd0  mov     [rbp+57h+var_38], rax
0x14000ffd4  mov     [rbp+57h+var_28], rax
0x14000ffd8  xor     r9d, r9d
0x14000ffdb  lea     rcx, dword_14007A000
0x14000ffe2  xor     r8d, r8d
0x14000ffe5  call    _tlgWriteTransfer_EventWriteTransfer
0x14000ffea  jmp     loc_14001027B
0x14000ffef  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x14000fff3  xor     r9d, r9d; dwFlags
0x14000fff6  mov     r8, [rbp+57h+var_80]
0x14000fffa  mov     rcx, rsi; hFile
0x14000fffd  sub     r8, rdx
0x140010000  sar     r8, 1; cchFilePath
0x140010003  call    cs:__imp_GetFinalPathNameByHandleW
0x140010009  mov     edi, eax
0x14001000b  test    eax, eax
0x14001000d  jnz     loc_1400100AD
0x140010013  call    cs:__imp_GetLastError
0x140010019  mov     ebx, eax
0x14001001b  cmp     eax, 3
0x14001001e  jnz     short loc_140010032
0x140010020  mov     rdx, r14
0x140010023  mov     rcx, rsi
0x140010026  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14001002b  mov     ebx, eax
0x14001002d  jmp     loc_14001027B
0x140010032  test    eax, eax
0x140010034  jle     short loc_14001003F
0x140010036  movzx   ebx, ax
0x140010039  or      ebx, 80070000h
0x14001003f  test    ebx, ebx
0x140010041  mov     eax, 80004005h
0x140010046  cmovns  ebx, eax
0x140010049  mov     eax, cs:dword_14007A000
0x14001004f  cmp     eax, 2
0x140010052  jbe     loc_14001027B
0x140010058  mov     rcx, cs:qword_14007A018
0x14001005f  mov     rax, cs:qword_14007A010
0x140010066  test    al, 8
0x140010068  jz      loc_14001027B
0x14001006e  mov     rax, rcx
0x140010071  and     eax, 8
0x140010074  cmp     rax, rcx
0x140010077  jnz     loc_14001027B
0x14001007d  lea     rax, [rbp+57h+var_90]
0x140010081  mov     [rbp+57h+var_90], ebx
0x140010084  mov     [rbp+57h+var_40], rax
0x140010088  lea     rdx, dword_14006EB6C
0x14001008f  lea     rax, [rbp+57h+var_60]
0x140010093  mov     [rbp+57h+var_38], 4
0x14001009b  mov     [rsp+0C0h+var_98], rax
0x1400100a0  mov     [rsp+0C0h+var_A0], 3
0x1400100a8  jmp     loc_14000FFD8
0x1400100ad  mov     rdx, [rbp+57h+var_80]
0x1400100b1  mov     r8, [rbp+57h+lpszFilePath]
0x1400100b5  mov     rax, rdx
0x1400100b8  sub     rax, r8
0x1400100bb  sar     rax, 1
0x1400100be  cmp     rdi, rax
0x1400100c1  jnz     short loc_140010130
0x1400100c3  mov     eax, cs:dword_14007A000
0x1400100c9  mov     ebx, 8000FFFFh
0x1400100ce  cmp     eax, 2
0x1400100d1  jbe     loc_14001027B
0x1400100d7  mov     rcx, cs:qword_14007A018
0x1400100de  mov     rax, cs:qword_14007A010
0x1400100e5  test    al, 8
0x1400100e7  jz      loc_14001027B
0x1400100ed  mov     rax, rcx
0x1400100f0  and     eax, 8
0x1400100f3  cmp     rax, rcx
0x1400100f6  jnz     loc_14001027B
0x1400100fc  lea     rax, [rbp+57h+var_90]
0x140010100  mov     [rbp+57h+var_90], 8000FFFFh
0x140010107  mov     [rbp+57h+var_40], rax
0x14001010b  lea     rdx, byte_14006EB2F
0x140010112  lea     rax, [rbp+57h+var_60]
0x140010116  mov     [rbp+57h+var_38], 4
0x14001011e  mov     [rsp+0C0h+var_98], rax
0x140010123  mov     [rsp+0C0h+var_A0], 3
0x14001012b  jmp     loc_14000FFD8
0x140010130  jbe     loc_140010251
0x140010136  mov     rdx, rdi
0x140010139  lea     rcx, [rbp+57h+lpszFilePath]
0x14001013d  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x140010142  test    al, al
0x140010144  jnz     short loc_14001019D
0x140010146  mov     eax, cs:dword_14007A000
0x14001014c  mov     ebx, 8007000Eh
0x140010151  cmp     eax, 2
0x140010154  jbe     loc_14001027B
0x14001015a  mov     rcx, cs:qword_14007A018
0x140010161  mov     rax, cs:qword_14007A010
0x140010168  test    al, 8
0x14001016a  jz      loc_14001027B
0x140010170  mov     rax, rcx
0x140010173  and     eax, 8
0x140010176  cmp     rax, rcx
0x140010179  jnz     loc_14001027B
0x14001017f  mov     [rbp+57h+var_90], 8007000Eh
0x140010186  lea     rax, [rbp+57h+var_90]
0x14001018a  mov     [rbp+57h+var_8C], edi
0x14001018d  lea     rcx, [rbp+57h+var_8C]
0x140010191  lea     rdx, unk_14006EAE8
0x140010198  jmp     loc_14000FFB6
0x14001019d  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x1400101a1  xor     r9d, r9d; dwFlags
0x1400101a4  mov     r8, [rbp+57h+var_80]
0x1400101a8  mov     rcx, rsi; hFile
0x1400101ab  sub     r8, rdx
0x1400101ae  sar     r8, 1; cchFilePath
0x1400101b1  call    cs:__imp_GetFinalPathNameByHandleW
0x1400101b7  mov     edi, eax
0x1400101b9  test    eax, eax
0x1400101bb  jz      short loc_1400101DA
0x1400101bd  mov     rdx, [rbp+57h+var_80]
0x1400101c1  mov     r8, [rbp+57h+lpszFilePath]
0x1400101c5  mov     rcx, rdx
0x1400101c8  sub     rcx, r8
0x1400101cb  sar     rcx, 1
0x1400101ce  cmp     rdi, rcx
0x1400101d1  jb      short loc_140010251
0x1400101d3  mov     ebx, 6Fh ; 'o'
0x1400101d8  jmp     short loc_1400101E6
0x1400101da  call    cs:__imp_GetLastError
0x1400101e0  mov     ebx, eax
0x1400101e2  test    eax, eax
0x1400101e4  jle     short loc_1400101EF
0x1400101e6  movzx   ebx, bx
0x1400101e9  or      ebx, 80070000h
0x1400101ef  test    ebx, ebx
0x1400101f1  mov     eax, 80004005h
0x1400101f6  cmovns  ebx, eax
0x1400101f9  mov     eax, cs:dword_14007A000
0x1400101ff  cmp     eax, 2
0x140010202  jbe     short loc_14001027B
0x140010204  mov     rcx, cs:qword_14007A018
0x14001020b  mov     rax, cs:qword_14007A010
0x140010212  test    al, 8
0x140010214  jz      short loc_14001027B
0x140010216  mov     rax, rcx
0x140010219  and     eax, 8
0x14001021c  cmp     rax, rcx
0x14001021f  jnz     short loc_14001027B
0x140010221  lea     rax, [rbp+57h+var_90]
0x140010225  mov     [rbp+57h+var_90], ebx
0x140010228  mov     [rbp+57h+var_40], rax
0x14001022c  lea     rdx, dword_14006EAB4
0x140010233  lea     rax, [rbp+57h+var_60]
0x140010237  mov     [rbp+57h+var_38], 4
0x14001023f  mov     [rsp+0C0h+var_98], rax
0x140010244  mov     [rsp+0C0h+var_A0], 3
0x14001024c  jmp     loc_14000FFD8
0x140010251  sub     rdx, r8
0x140010254  mov     eax, edi
0x140010256  sar     rdx, 1
0x140010259  cmp     rax, rdx
0x14001025c  jbe     short loc_140010260
0x14001025e  int     2Ch; Windows NT - assertion failure
0x140010260  lea     rcx, [r8+rdi*2]
0x140010264  xor     eax, eax
0x140010266  mov     [rbp+57h+var_80], rcx
0x14001026a  lea     rdx, [rbp+57h+lpszFilePath]
0x14001026e  mov     [rcx], ax
0x140010271  mov     rcx, r14
0x140010274  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x140010279  xor     ebx, ebx
0x14001027b  mov     rcx, [rbp+57h+lpszFilePath]; void *
0x14001027f  lea     rax, [rbp+57h+var_78]
0x140010283  cmp     rcx, rax
0x140010286  jz      short loc_140010294
0x140010288  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001028f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010294  mov     eax, ebx
0x140010296  mov     rcx, [rbp+57h+var_20]
0x14001029a  xor     rcx, rsp; StackCookie
0x14001029d  call    __security_check_cookie
0x1400102a2  lea     r11, [rsp+0C0h+var_10]
0x1400102aa  mov     rbx, [r11+30h]
0x1400102ae  mov     rsi, [r11+38h]
0x1400102b2  mov     rsp, r11
0x1400102b5  pop     r14
0x1400102b7  pop     rdi
0x1400102b8  pop     rbp
0x1400102b9  retn
```
