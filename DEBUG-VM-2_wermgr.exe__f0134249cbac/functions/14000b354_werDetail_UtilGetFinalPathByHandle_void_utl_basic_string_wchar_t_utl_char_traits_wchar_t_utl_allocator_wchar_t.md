# _werDetail::UtilGetFinalPathByHandle(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x14000b354`
- end: `0x14000b706`
- name: `?UtilGetFinalPathByHandle@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x14000c798`

## callees

- `0x14000162c`
- `0x140003200`
- `0x140003224`
- `0x140004d70`
- `0x14000b354`
- `0x14000b70c`
- `0x14000e258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b45f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b45f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b626`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b44f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b5fd`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b44f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000b5fd`

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
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                           &lpszFilePath,
                           261) )
  {
    FinalPathOnUnmountedVolume = -2147024882;
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v17 = -2147024882;
      v5 = &v17;
      v16 = 261;
      v6 = &v16;
      v7 = byte_1400269D9;
LABEL_6:
      v22 = v6;
      v24 = v5;
      v23 = 4;
      v25 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, v7, 0, 0, 4, v21);
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
      if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        v16 = FinalPathOnUnmountedVolume;
        v22 = &v16;
        v23 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, byte_1400269A5, 0, 0, 3, v21);
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
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v16 = -2147418113;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, &unk_140026968, 0, 0, 3, v21);
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
        if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
        {
          v16 = FinalPathOnUnmountedVolume;
          v22 = &v16;
          v23 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, byte_1400268ED, 0, 0, 3, v21);
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
  if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
  {
    v16 = -2147024882;
    v5 = &v16;
    v17 = v9;
    v6 = &v17;
    v7 = byte_140026921;
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
0x14000b354  mov     [rsp-8+arg_10], rbx
0x14000b359  mov     [rsp-8+arg_18], rsi
0x14000b35e  push    rbp
0x14000b35f  push    rdi
0x14000b360  push    r14
0x14000b362  lea     rbp, [rsp-47h]
0x14000b367  sub     rsp, 0B0h
0x14000b36e  mov     rax, cs:__security_cookie
0x14000b375  xor     rax, rsp
0x14000b378  mov     [rbp+57h+var_20], rax
0x14000b37c  lea     rax, [rbp+57h+var_78]
0x14000b380  mov     r14, rdx
0x14000b383  mov     [rbp+57h+lpszFilePath], rax
0x14000b387  mov     rsi, rcx
0x14000b38a  lea     rax, [rbp+57h+var_78]
0x14000b38e  mov     edi, 105h
0x14000b393  mov     [rbp+57h+var_80], rax
0x14000b397  lea     rcx, [rbp+57h+lpszFilePath]
0x14000b39b  xor     eax, eax
0x14000b39d  mov     edx, edi
0x14000b39f  mov     [rbp+57h+var_78], ax
0x14000b3a3  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000b3a8  test    al, al
0x14000b3aa  jnz     loc_14000B43B
0x14000b3b0  mov     eax, cs:dword_14002C000
0x14000b3b6  mov     ebx, 8007000Eh
0x14000b3bb  cmp     eax, 2
0x14000b3be  jbe     loc_14000B6C7
0x14000b3c4  mov     rcx, cs:qword_14002C018
0x14000b3cb  mov     rax, cs:qword_14002C010
0x14000b3d2  test    al, 8
0x14000b3d4  jz      loc_14000B6C7
0x14000b3da  mov     rax, rcx
0x14000b3dd  and     eax, 8
0x14000b3e0  cmp     rax, rcx
0x14000b3e3  jnz     loc_14000B6C7
0x14000b3e9  mov     [rbp+57h+var_8C], 8007000Eh
0x14000b3f0  lea     rax, [rbp+57h+var_8C]
0x14000b3f4  mov     [rbp+57h+var_90], edi
0x14000b3f7  lea     rcx, [rbp+57h+var_90]
0x14000b3fb  lea     rdx, byte_1400269D9
0x14000b402  mov     [rbp+57h+var_40], rcx
0x14000b406  lea     rcx, [rbp+57h+var_60]
0x14000b40a  mov     [rbp+57h+var_30], rax
0x14000b40e  mov     eax, 4
0x14000b413  mov     [rsp+0C0h+var_98], rcx
0x14000b418  mov     [rsp+0C0h+var_A0], eax
0x14000b41c  mov     [rbp+57h+var_38], rax
0x14000b420  mov     [rbp+57h+var_28], rax
0x14000b424  xor     r9d, r9d
0x14000b427  lea     rcx, dword_14002C000
0x14000b42e  xor     r8d, r8d
0x14000b431  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b436  jmp     loc_14000B6C7
0x14000b43b  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x14000b43f  xor     r9d, r9d; dwFlags
0x14000b442  mov     r8, [rbp+57h+var_80]
0x14000b446  mov     rcx, rsi; hFile
0x14000b449  sub     r8, rdx
0x14000b44c  sar     r8, 1; cchFilePath
0x14000b44f  call    cs:__imp_GetFinalPathNameByHandleW
0x14000b455  mov     edi, eax
0x14000b457  test    eax, eax
0x14000b459  jnz     loc_14000B4F9
0x14000b45f  call    cs:__imp_GetLastError
0x14000b465  mov     ebx, eax
0x14000b467  cmp     eax, 3
0x14000b46a  jnz     short loc_14000B47E
0x14000b46c  mov     rdx, r14
0x14000b46f  mov     rcx, rsi
0x14000b472  call    ?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14000b477  mov     ebx, eax
0x14000b479  jmp     loc_14000B6C7
0x14000b47e  test    eax, eax
0x14000b480  jle     short loc_14000B48B
0x14000b482  movzx   ebx, ax
0x14000b485  or      ebx, 80070000h
0x14000b48b  test    ebx, ebx
0x14000b48d  mov     eax, 80004005h
0x14000b492  cmovns  ebx, eax
0x14000b495  mov     eax, cs:dword_14002C000
0x14000b49b  cmp     eax, 2
0x14000b49e  jbe     loc_14000B6C7
0x14000b4a4  mov     rcx, cs:qword_14002C018
0x14000b4ab  mov     rax, cs:qword_14002C010
0x14000b4b2  test    al, 8
0x14000b4b4  jz      loc_14000B6C7
0x14000b4ba  mov     rax, rcx
0x14000b4bd  and     eax, 8
0x14000b4c0  cmp     rax, rcx
0x14000b4c3  jnz     loc_14000B6C7
0x14000b4c9  lea     rax, [rbp+57h+var_90]
0x14000b4cd  mov     [rbp+57h+var_90], ebx
0x14000b4d0  mov     [rbp+57h+var_40], rax
0x14000b4d4  lea     rdx, byte_1400269A5
0x14000b4db  lea     rax, [rbp+57h+var_60]
0x14000b4df  mov     [rbp+57h+var_38], 4
0x14000b4e7  mov     [rsp+0C0h+var_98], rax
0x14000b4ec  mov     [rsp+0C0h+var_A0], 3
0x14000b4f4  jmp     loc_14000B424
0x14000b4f9  mov     rdx, [rbp+57h+var_80]
0x14000b4fd  mov     r8, [rbp+57h+lpszFilePath]
0x14000b501  mov     rax, rdx
0x14000b504  sub     rax, r8
0x14000b507  sar     rax, 1
0x14000b50a  cmp     rdi, rax
0x14000b50d  jnz     short loc_14000B57C
0x14000b50f  mov     eax, cs:dword_14002C000
0x14000b515  mov     ebx, 8000FFFFh
0x14000b51a  cmp     eax, 2
0x14000b51d  jbe     loc_14000B6C7
0x14000b523  mov     rcx, cs:qword_14002C018
0x14000b52a  mov     rax, cs:qword_14002C010
0x14000b531  test    al, 8
0x14000b533  jz      loc_14000B6C7
0x14000b539  mov     rax, rcx
0x14000b53c  and     eax, 8
0x14000b53f  cmp     rax, rcx
0x14000b542  jnz     loc_14000B6C7
0x14000b548  lea     rax, [rbp+57h+var_90]
0x14000b54c  mov     [rbp+57h+var_90], 8000FFFFh
0x14000b553  mov     [rbp+57h+var_40], rax
0x14000b557  lea     rdx, unk_140026968
0x14000b55e  lea     rax, [rbp+57h+var_60]
0x14000b562  mov     [rbp+57h+var_38], 4
0x14000b56a  mov     [rsp+0C0h+var_98], rax
0x14000b56f  mov     [rsp+0C0h+var_A0], 3
0x14000b577  jmp     loc_14000B424
0x14000b57c  jbe     loc_14000B69D
0x14000b582  mov     rdx, rdi
0x14000b585  lea     rcx, [rbp+57h+lpszFilePath]
0x14000b589  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000b58e  test    al, al
0x14000b590  jnz     short loc_14000B5E9
0x14000b592  mov     eax, cs:dword_14002C000
0x14000b598  mov     ebx, 8007000Eh
0x14000b59d  cmp     eax, 2
0x14000b5a0  jbe     loc_14000B6C7
0x14000b5a6  mov     rcx, cs:qword_14002C018
0x14000b5ad  mov     rax, cs:qword_14002C010
0x14000b5b4  test    al, 8
0x14000b5b6  jz      loc_14000B6C7
0x14000b5bc  mov     rax, rcx
0x14000b5bf  and     eax, 8
0x14000b5c2  cmp     rax, rcx
0x14000b5c5  jnz     loc_14000B6C7
0x14000b5cb  mov     [rbp+57h+var_90], 8007000Eh
0x14000b5d2  lea     rax, [rbp+57h+var_90]
0x14000b5d6  mov     [rbp+57h+var_8C], edi
0x14000b5d9  lea     rcx, [rbp+57h+var_8C]
0x14000b5dd  lea     rdx, byte_140026921
0x14000b5e4  jmp     loc_14000B402
0x14000b5e9  mov     rdx, [rbp+57h+lpszFilePath]; lpszFilePath
0x14000b5ed  xor     r9d, r9d; dwFlags
0x14000b5f0  mov     r8, [rbp+57h+var_80]
0x14000b5f4  mov     rcx, rsi; hFile
0x14000b5f7  sub     r8, rdx
0x14000b5fa  sar     r8, 1; cchFilePath
0x14000b5fd  call    cs:__imp_GetFinalPathNameByHandleW
0x14000b603  mov     edi, eax
0x14000b605  test    eax, eax
0x14000b607  jz      short loc_14000B626
0x14000b609  mov     rdx, [rbp+57h+var_80]
0x14000b60d  mov     r8, [rbp+57h+lpszFilePath]
0x14000b611  mov     rcx, rdx
0x14000b614  sub     rcx, r8
0x14000b617  sar     rcx, 1
0x14000b61a  cmp     rdi, rcx
0x14000b61d  jb      short loc_14000B69D
0x14000b61f  mov     ebx, 6Fh ; 'o'
0x14000b624  jmp     short loc_14000B632
0x14000b626  call    cs:__imp_GetLastError
0x14000b62c  mov     ebx, eax
0x14000b62e  test    eax, eax
0x14000b630  jle     short loc_14000B63B
0x14000b632  movzx   ebx, bx
0x14000b635  or      ebx, 80070000h
0x14000b63b  test    ebx, ebx
0x14000b63d  mov     eax, 80004005h
0x14000b642  cmovns  ebx, eax
0x14000b645  mov     eax, cs:dword_14002C000
0x14000b64b  cmp     eax, 2
0x14000b64e  jbe     short loc_14000B6C7
0x14000b650  mov     rcx, cs:qword_14002C018
0x14000b657  mov     rax, cs:qword_14002C010
0x14000b65e  test    al, 8
0x14000b660  jz      short loc_14000B6C7
0x14000b662  mov     rax, rcx
0x14000b665  and     eax, 8
0x14000b668  cmp     rax, rcx
0x14000b66b  jnz     short loc_14000B6C7
0x14000b66d  lea     rax, [rbp+57h+var_90]
0x14000b671  mov     [rbp+57h+var_90], ebx
0x14000b674  mov     [rbp+57h+var_40], rax
0x14000b678  lea     rdx, byte_1400268ED
0x14000b67f  lea     rax, [rbp+57h+var_60]
0x14000b683  mov     [rbp+57h+var_38], 4
0x14000b68b  mov     [rsp+0C0h+var_98], rax
0x14000b690  mov     [rsp+0C0h+var_A0], 3
0x14000b698  jmp     loc_14000B424
0x14000b69d  sub     rdx, r8
0x14000b6a0  mov     eax, edi
0x14000b6a2  sar     rdx, 1
0x14000b6a5  cmp     rax, rdx
0x14000b6a8  jbe     short loc_14000B6AC
0x14000b6aa  int     2Ch; Windows NT - assertion failure
0x14000b6ac  lea     rcx, [r8+rdi*2]
0x14000b6b0  xor     eax, eax
0x14000b6b2  mov     [rbp+57h+var_80], rcx
0x14000b6b6  lea     rdx, [rbp+57h+lpszFilePath]
0x14000b6ba  mov     [rcx], ax
0x14000b6bd  mov     rcx, r14
0x14000b6c0  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14000b6c5  xor     ebx, ebx
0x14000b6c7  mov     rcx, [rbp+57h+lpszFilePath]; void *
0x14000b6cb  lea     rax, [rbp+57h+var_78]
0x14000b6cf  cmp     rcx, rax
0x14000b6d2  jz      short loc_14000B6E0
0x14000b6d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000b6db  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000b6e0  mov     eax, ebx
0x14000b6e2  mov     rcx, [rbp+57h+var_20]
0x14000b6e6  xor     rcx, rsp; StackCookie
0x14000b6e9  call    __security_check_cookie
0x14000b6ee  lea     r11, [rsp+0C0h+var_10]
0x14000b6f6  mov     rbx, [r11+30h]
0x14000b6fa  mov     rsi, [r11+38h]
0x14000b6fe  mov     rsp, r11
0x14000b701  pop     r14
0x14000b703  pop     rdi
0x14000b704  pop     rbp
0x14000b705  retn
```
