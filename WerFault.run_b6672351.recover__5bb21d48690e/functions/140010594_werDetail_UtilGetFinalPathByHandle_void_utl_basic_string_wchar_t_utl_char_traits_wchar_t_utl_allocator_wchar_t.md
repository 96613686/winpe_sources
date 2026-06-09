# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x140010594`
- end: `0x140010963`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `975`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x1400130f8`
- `0x1400151b8`

## callees

- `0x140001150`
- `0x140002490`
- `0x140002748`
- `0x14000cf48`
- `0x14000e9d4`
- `0x140010594`
- `0x14001096c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400106a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001087c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400106a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001087c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14001068f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010849`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14001068f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x140010849`

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
  int v16; // [rsp+20h] [rbp-49h]
  int v17; // [rsp+20h] [rbp-49h]
  int v18; // [rsp+20h] [rbp-49h]
  int v19; // [rsp+20h] [rbp-49h]
  int v20; // [rsp+30h] [rbp-39h] BYREF
  int v21; // [rsp+34h] [rbp-35h] BYREF
  LPWSTR lpszFilePath; // [rsp+38h] [rbp-31h] BYREF
  WCHAR *v23; // [rsp+40h] [rbp-29h]
  _WORD v24[12]; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v25[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v26; // [rsp+80h] [rbp+17h]
  __int64 v27; // [rsp+88h] [rbp+1Fh]
  int *v28; // [rsp+90h] [rbp+27h]
  __int64 v29; // [rsp+98h] [rbp+2Fh]

  lpszFilePath = v24;
  v23 = v24;
  v24[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      v21 = -2147024882;
      v5 = &v21;
      v20 = 261;
      v6 = &v20;
      v7 = &unk_140072B38;
LABEL_6:
      v26 = v6;
      v28 = v5;
      v16 = 4;
      v27 = 4;
      v29 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, v7, 0, 0, v16, v25);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, lpszFilePath, v23 - lpszFilePath, 0);
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
      if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
      {
        v20 = FinalPathOnUnmountedVolume;
        v26 = &v20;
        v27 = 4;
        v17 = 3;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &dword_140072B04, 0, 0, v17, v25);
      }
    }
    goto LABEL_44;
  }
  v11 = v23;
  v12 = lpszFilePath;
  v13 = v23 - lpszFilePath;
  if ( v9 == v13 )
  {
    FinalPathOnUnmountedVolume = -2147418113;
    if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
    {
      v20 = -2147418113;
      v26 = &v20;
      v27 = 4;
      v18 = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &byte_140072AC7, 0, 0, v18, v25);
    }
    goto LABEL_44;
  }
  if ( v9 <= v13 )
    goto LABEL_41;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &lpszFilePath,
                          v9) )
  {
    v14 = GetFinalPathNameByHandleW(hFile, lpszFilePath, v23 - lpszFilePath, 0);
    v9 = v14;
    if ( !v14 )
    {
      FinalPathOnUnmountedVolume = GetLastError();
      if ( FinalPathOnUnmountedVolume <= 0 )
      {
LABEL_35:
        if ( FinalPathOnUnmountedVolume >= 0 )
          FinalPathOnUnmountedVolume = -2147467259;
        if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
        {
          v20 = FinalPathOnUnmountedVolume;
          v26 = &v20;
          v27 = 4;
          v19 = 3;
          tlgWriteTransfer_EventWriteTransfer(&dword_14007E000, &dword_140072A4C, 0, 0, v19, v25);
        }
        goto LABEL_44;
      }
LABEL_34:
      FinalPathOnUnmountedVolume = (unsigned __int16)FinalPathOnUnmountedVolume | 0x80070000;
      goto LABEL_35;
    }
    v11 = v23;
    v12 = lpszFilePath;
    if ( v14 >= (unsigned __int64)(v23 - lpszFilePath) )
    {
      LOWORD(FinalPathOnUnmountedVolume) = 111;
      goto LABEL_34;
    }
LABEL_41:
    if ( (unsigned int)v9 > (unsigned __int64)(v11 - v12) )
      __int2c();
    v23 = &v12[v9];
    *v23 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpszFilePath);
    FinalPathOnUnmountedVolume = 0;
    goto LABEL_44;
  }
  FinalPathOnUnmountedVolume = -2147024882;
  if ( (unsigned int)dword_14007E000 > 2 && (qword_14007E010 & 8) != 0 && (qword_14007E018 & 8) == qword_14007E018 )
  {
    v20 = -2147024882;
    v5 = &v20;
    v21 = v9;
    v6 = &v21;
    v7 = &unk_140072A80;
    goto LABEL_6;
  }
LABEL_44:
  if ( lpszFilePath != v24 )
    operator delete(lpszFilePath, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)FinalPathOnUnmountedVolume;
}

```

## disassembly

```asm
0x140010594  mov     [rsp-8+arg_10], rbx
0x140010599  mov     [rsp-8+arg_18], rsi
0x14001059e  push    rbp
0x14001059f  push    rdi
0x1400105a0  push    r14
0x1400105a2  lea     rbp, [rsp-47h]
0x1400105a7  sub     rsp, 0B0h
0x1400105ae  mov     rax, cs:__security_cookie
0x1400105b5  xor     rax, rsp
0x1400105b8  mov     [rbp+57h+var_20], rax
0x1400105bc  lea     rax, [rbp+57h+var_78]
0x1400105c0  mov     r14, rdx
0x1400105c3  mov     [rbp+57h+lpszFilePath], rax
0x1400105c7  mov     rsi, rcx
0x1400105ca  lea     rax, [rbp+57h+var_78]
0x1400105ce  mov     edi, 105h
0x1400105d3  mov     [rbp+57h+var_80], rax
0x1400105d7  lea     rcx, [rbp+57h+lpszFilePath]
0x1400105db  xor     eax, eax
0x1400105dd  mov     edx, edi
0x1400105df  mov     [rbp+57h+var_78], ax
0x1400105e3  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1400105e8  test    al, al
0x1400105ea  jnz     loc_14001067B
0x1400105f0  mov     eax, cs:dword_14007E000
0x1400105f6  mov     ebx, 8007000Eh
0x1400105fb  cmp     eax, 2
0x1400105fe  jbe     loc_140010923
0x140010604  mov     rcx, cs:qword_14007E018
0x14001060b  mov     rax, cs:qword_14007E010
0x140010612  test    al, 8
0x140010614  jz      loc_140010923
0x14001061a  mov     rax, rcx
0x14001061d  and     eax, 8
0x140010620  cmp     rax, rcx
0x140010623  jnz     loc_140010923
0x140010629  mov     [rbp+57h+var_8C], 8007000Eh
0x140010630  lea     rax, [rbp+57h+var_8C]
0x140010634  mov     [rbp+57h+var_90], edi
0x140010637  lea     rcx, [rbp+57h+var_90]
0x14001063b  lea     rdx, unk_140072B38
0x140010642  mov     [rbp+57h+var_40], rcx
0x140010646  lea     rcx, [rbp+57h+var_60]
0x14001064a  mov     [rbp+57h+var_30], rax
0x14001064e  mov     eax, 4
0x140010653  mov     [rsp+0C0h+var_98], rcx
0x140010658  mov     [rsp+0C0h+var_A0], eax
0x14001065c  mov     [rbp+57h+var_38], rax
0x140010660  mov     [rbp+57h+var_28], rax
0x140010664  xor     r9d, r9d
0x140010667  lea     rcx, dword_14007E000
0x14001066e  xor     r8d, r8d
0x140010671  call    _tlgWriteTransfer_EventWriteTransfer
0x140010676  jmp     loc_140010923
0x14001067b  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x14001067f  xor     r9d, r9d; dwFlags
0x140010682  mov     r8, [rbp+57h+var_80]
0x140010686  mov     rcx, rsi; hFile
0x140010689  sub     r8, rdx
0x14001068c  sar     r8, 1; cchFilePath
0x14001068f  call    cs:__imp_GetFinalPathNameByHandleW
0x140010696  nop     dword ptr [rax+rax+00h]
0x14001069b  mov     edi, eax
0x14001069d  test    eax, eax
0x14001069f  jnz     loc_140010745
0x1400106a5  call    cs:__imp_GetLastError
0x1400106ac  nop     dword ptr [rax+rax+00h]
0x1400106b1  mov     ebx, eax
0x1400106b3  cmp     eax, 3
0x1400106b6  jnz     short loc_1400106CA
0x1400106b8  mov     rdx, r14
0x1400106bb  mov     rcx, rsi
0x1400106be  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1400106c3  mov     ebx, eax
0x1400106c5  jmp     loc_140010923
0x1400106ca  test    eax, eax
0x1400106cc  jle     short loc_1400106D7
0x1400106ce  movzx   ebx, ax
0x1400106d1  or      ebx, 80070000h
0x1400106d7  test    ebx, ebx
0x1400106d9  mov     eax, 80004005h
0x1400106de  cmovns  ebx, eax
0x1400106e1  mov     eax, cs:dword_14007E000
0x1400106e7  cmp     eax, 2
0x1400106ea  jbe     loc_140010923
0x1400106f0  mov     rcx, cs:qword_14007E018
0x1400106f7  mov     rax, cs:qword_14007E010
0x1400106fe  test    al, 8
0x140010700  jz      loc_140010923
0x140010706  mov     rax, rcx
0x140010709  and     eax, 8
0x14001070c  cmp     rax, rcx
0x14001070f  jnz     loc_140010923
0x140010715  lea     rax, [rbp+57h+var_90]
0x140010719  mov     [rbp+57h+var_90], ebx
0x14001071c  mov     [rbp+57h+var_40], rax
0x140010720  lea     rdx, dword_140072B04
0x140010727  lea     rax, [rbp+57h+var_60]
0x14001072b  mov     [rbp+57h+var_38], 4
0x140010733  mov     [rsp+0C0h+var_98], rax
0x140010738  mov     [rsp+0C0h+var_A0], 3
0x140010740  jmp     loc_140010664
0x140010745  mov     rdx, [rbp+57h+var_80]
0x140010749  mov     r8, [rbp+57h+lpszFilePath]
0x14001074d  mov     rax, rdx
0x140010750  sub     rax, r8
0x140010753  sar     rax, 1
0x140010756  cmp     rdi, rax
0x140010759  jnz     short loc_1400107C8
0x14001075b  mov     eax, cs:dword_14007E000
0x140010761  mov     ebx, 8000FFFFh
0x140010766  cmp     eax, 2
0x140010769  jbe     loc_140010923
0x14001076f  mov     rcx, cs:qword_14007E018
0x140010776  mov     rax, cs:qword_14007E010
0x14001077d  test    al, 8
0x14001077f  jz      loc_140010923
0x140010785  mov     rax, rcx
0x140010788  and     eax, 8
0x14001078b  cmp     rax, rcx
0x14001078e  jnz     loc_140010923
0x140010794  lea     rax, [rbp+57h+var_90]
0x140010798  mov     [rbp+57h+var_90], 8000FFFFh
0x14001079f  mov     [rbp+57h+var_40], rax
0x1400107a3  lea     rdx, byte_140072AC7
0x1400107aa  lea     rax, [rbp+57h+var_60]
0x1400107ae  mov     [rbp+57h+var_38], 4
0x1400107b6  mov     [rsp+0C0h+var_98], rax
0x1400107bb  mov     [rsp+0C0h+var_A0], 3
0x1400107c3  jmp     loc_140010664
0x1400107c8  jbe     loc_1400108F9
0x1400107ce  mov     rdx, rdi
0x1400107d1  lea     rcx, [rbp+57h+lpszFilePath]
0x1400107d5  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1400107da  test    al, al
0x1400107dc  jnz     short loc_140010835
0x1400107de  mov     eax, cs:dword_14007E000
0x1400107e4  mov     ebx, 8007000Eh
0x1400107e9  cmp     eax, 2
0x1400107ec  jbe     loc_140010923
0x1400107f2  mov     rcx, cs:qword_14007E018
0x1400107f9  mov     rax, cs:qword_14007E010
0x140010800  test    al, 8
0x140010802  jz      loc_140010923
0x140010808  mov     rax, rcx
0x14001080b  and     eax, 8
0x14001080e  cmp     rax, rcx
0x140010811  jnz     loc_140010923
0x140010817  mov     [rbp+57h+var_90], 8007000Eh
0x14001081e  lea     rax, [rbp+57h+var_90]
0x140010822  mov     [rbp+57h+var_8C], edi
0x140010825  lea     rcx, [rbp+57h+var_8C]
0x140010829  lea     rdx, unk_140072A80
0x140010830  jmp     loc_140010642
0x140010835  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x140010839  xor     r9d, r9d; dwFlags
0x14001083c  mov     r8, [rbp+57h+var_80]
0x140010840  mov     rcx, rsi; hFile
0x140010843  sub     r8, rdx
0x140010846  sar     r8, 1; cchFilePath
0x140010849  call    cs:__imp_GetFinalPathNameByHandleW
0x140010850  nop     dword ptr [rax+rax+00h]
0x140010855  mov     edi, eax
0x140010857  test    eax, eax
0x140010859  jz      short loc_14001087C
0x14001085b  mov     rdx, [rbp+57h+var_80]
0x14001085f  mov     r8, [rbp+57h+lpszFilePath]
0x140010863  mov     rcx, rdx
0x140010866  sub     rcx, r8
0x140010869  sar     rcx, 1
0x14001086c  cmp     rdi, rcx
0x14001086f  jb      loc_1400108F9
0x140010875  mov     ebx, 6Fh ; 'o'
0x14001087a  jmp     short loc_14001088E
0x14001087c  call    cs:__imp_GetLastError
0x140010883  nop     dword ptr [rax+rax+00h]
0x140010888  mov     ebx, eax
0x14001088a  test    eax, eax
0x14001088c  jle     short loc_140010897
0x14001088e  movzx   ebx, bx
0x140010891  or      ebx, 80070000h
0x140010897  test    ebx, ebx
0x140010899  mov     eax, 80004005h
0x14001089e  cmovns  ebx, eax
0x1400108a1  mov     eax, cs:dword_14007E000
0x1400108a7  cmp     eax, 2
0x1400108aa  jbe     short loc_140010923
0x1400108ac  mov     rcx, cs:qword_14007E018
0x1400108b3  mov     rax, cs:qword_14007E010
0x1400108ba  test    al, 8
0x1400108bc  jz      short loc_140010923
0x1400108be  mov     rax, rcx
0x1400108c1  and     eax, 8
0x1400108c4  cmp     rax, rcx
0x1400108c7  jnz     short loc_140010923
0x1400108c9  lea     rax, [rbp+57h+var_90]
0x1400108cd  mov     [rbp+57h+var_90], ebx
0x1400108d0  mov     [rbp+57h+var_40], rax
0x1400108d4  lea     rdx, dword_140072A4C
0x1400108db  lea     rax, [rbp+57h+var_60]
0x1400108df  mov     [rbp+57h+var_38], 4
0x1400108e7  mov     [rsp+0C0h+var_98], rax
0x1400108ec  mov     [rsp+0C0h+var_A0], 3
0x1400108f4  jmp     loc_140010664
0x1400108f9  sub     rdx, r8
0x1400108fc  mov     eax, edi
0x1400108fe  sar     rdx, 1
0x140010901  cmp     rax, rdx
0x140010904  jbe     short loc_140010908
0x140010906  int     2Ch; Windows NT - assertion failure
0x140010908  lea     rcx, [r8+rdi*2]
0x14001090c  xor     eax, eax
0x14001090e  mov     [rbp+57h+var_80], rcx
0x140010912  lea     rdx, [rbp+57h+lpszFilePath]
0x140010916  mov     [rcx], ax
0x140010919  mov     rcx, r14
0x14001091c  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x140010921  xor     ebx, ebx
0x140010923  mov     rcx, [rbp+57h+lpszFilePath]; void *
0x140010927  lea     rax, [rbp+57h+var_78]
0x14001092b  cmp     rcx, rax
0x14001092e  jz      short loc_14001093C
0x140010930  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010937  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001093c  mov     eax, ebx
0x14001093e  mov     rcx, [rbp+57h+var_20]
0x140010942  xor     rcx, rsp; StackCookie
0x140010945  call    __security_check_cookie
0x14001094a  lea     r11, [rsp+0C0h+var_10]
0x140010952  mov     rbx, [r11+30h]
0x140010956  mov     rsi, [r11+38h]
0x14001095a  mov     rsp, r11
0x14001095d  pop     r14
0x14001095f  pop     rdi
0x140010960  pop     rbp
0x140010961  retn
```
