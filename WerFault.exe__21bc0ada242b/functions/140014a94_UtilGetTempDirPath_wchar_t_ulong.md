# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x140014a94`
- end: `0x140014dd4`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `832`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x140014ddc`
- `0x140041be8`

## callees

- `0x14000113c`
- `0x14000134c`
- `0x140002470`
- `0x140002728`
- `0x1400146f0`
- `0x140014a94`
- `0x14005b7e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014c8f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140014b02`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140014b02`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140014aea`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140014aea`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140014acf`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x140014acf`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(WCHAR *lpFileName)
{
  DWORD FileAttributesW; // eax
  signed int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  signed int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  signed int LastError; // eax
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-39h] BYREF
  WCHAR *v13; // [rsp+38h] [rbp-31h] BYREF
  void *Src; // [rsp+40h] [rbp-29h]
  char *v15; // [rsp+48h] [rbp-21h]
  _WORD v16[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-9h] BYREF
  int *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  if ( lpFileName )
  {
    *lpFileName = 0;
    if ( !(unsigned int)GetTempPath2W(260, lpFileName) || !*lpFileName )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
      {
        v12 = v6;
        v18 = &v12;
        v19 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &dword_14006EF54, 0, 0, 3, v17);
      }
      goto LABEL_36;
    }
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( (FileAttributesW == -1 || (FileAttributesW & 0x10) == 0) && !CreateDirectoryW(lpFileName, 0) )
    {
      v3 = GetLastError();
      v6 = v3;
      if ( v3 > 0 )
        v6 = (unsigned __int16)v3 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
      {
        v12 = v6;
        v13 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          qword_14007A018,
          (__int64)&unk_14006EF10,
          v4,
          v5,
          (const WCHAR **)&v13,
          (__int64)&v12);
      }
      *lpFileName = 0;
LABEL_36:
      if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 )
      {
        v10 = qword_14007A018 & 8;
        if ( v10 == qword_14007A018 )
        {
          v12 = v6;
          v13 = lpFileName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
            v10,
            (__int64)byte_14006EEA3,
            v4,
            v5,
            (const WCHAR **)&v13,
            (__int64)&v12);
        }
      }
      return (unsigned int)v6;
    }
    v16[0] = 0;
    Src = v16;
    v15 = (char *)v16;
    if ( (unsigned int)UtilGetFinalPath(lpFileName) )
    {
      v7 = (v15 - (_BYTE *)Src) >> 1;
      if ( v7 >= 0x104 )
      {
        *lpFileName = 0;
        v6 = -2147024809;
        if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
        {
          v12 = -2147024809;
          v18 = &v12;
          v19 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, &dword_14006EEDC, 0, 0, 3, v17);
        }
        if ( Src != v16 )
          operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_36;
      }
      v8 = v7;
      memcpy_0(lpFileName, Src, v8 * 2);
      lpFileName[v8] = 0;
    }
    if ( Src != v16 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v6 = 0;
    goto LABEL_36;
  }
  if ( (unsigned int)dword_14007A000 > 2 && (qword_14007A010 & 8) != 0 && (qword_14007A018 & 8) == qword_14007A018 )
    tlgWriteTransfer_EventWriteTransfer(&dword_14007A000, qword_14006EF88, 0, 0, 2, v17);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140014a94  push    rbp
0x140014a96  push    rbx
0x140014a97  push    rdi
0x140014a98  push    r14
0x140014a9a  lea     rbp, [rsp-3Fh]
0x140014a9f  sub     rsp, 0A8h
0x140014aa6  mov     rax, cs:__security_cookie
0x140014aad  xor     rax, rsp
0x140014ab0  mov     [rbp+57h+var_30], rax
0x140014ab4  xor     r14d, r14d
0x140014ab7  mov     rdi, rcx
0x140014aba  test    rcx, rcx
0x140014abd  jz      loc_140014D64
0x140014ac3  mov     [rcx], r14w
0x140014ac7  mov     rdx, rcx
0x140014aca  mov     ecx, 104h
0x140014acf  call    cs:__imp_GetTempPath2W
0x140014ad5  test    eax, eax
0x140014ad7  jz      loc_140014C8F
0x140014add  cmp     [rdi], r14w
0x140014ae1  jz      loc_140014C8F
0x140014ae7  mov     rcx, rdi; lpFileName
0x140014aea  call    cs:__imp_GetFileAttributesW
0x140014af0  cmp     eax, 0FFFFFFFFh
0x140014af3  jz      short loc_140014AFD
0x140014af5  test    al, 10h
0x140014af7  jnz     loc_140014B81
0x140014afd  xor     edx, edx; lpSecurityAttributes
0x140014aff  mov     rcx, rdi; lpPathName
0x140014b02  call    cs:__imp_CreateDirectoryW
0x140014b08  test    eax, eax
0x140014b0a  jnz     short loc_140014B81
0x140014b0c  call    cs:__imp_GetLastError
0x140014b12  mov     ebx, eax
0x140014b14  test    eax, eax
0x140014b16  jle     short loc_140014B21
0x140014b18  movzx   ebx, ax
0x140014b1b  or      ebx, 80070000h
0x140014b21  test    ebx, ebx
0x140014b23  mov     eax, 80004005h
0x140014b28  cmovns  ebx, eax
0x140014b2b  mov     eax, cs:dword_14007A000
0x140014b31  cmp     eax, 2
0x140014b34  jbe     short loc_140014B78
0x140014b36  mov     rcx, cs:qword_14007A018
0x140014b3d  mov     rax, cs:qword_14007A010
0x140014b44  test    al, 8
0x140014b46  jz      short loc_140014B78
0x140014b48  mov     rax, rcx
0x140014b4b  and     eax, 8
0x140014b4e  cmp     rax, rcx
0x140014b51  jnz     short loc_140014B78
0x140014b53  lea     rax, [rbp+57h+var_90]
0x140014b57  mov     [rbp+57h+var_90], ebx
0x140014b5a  mov     [rsp+0C0h+var_98], rax
0x140014b5f  lea     rdx, unk_14006EF10
0x140014b66  lea     rax, [rbp+57h+var_88]
0x140014b6a  mov     [rbp+57h+var_88], rdi
0x140014b6e  mov     [rsp+0C0h+var_A0], rax
0x140014b73  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140014b78  mov     [rdi], r14w
0x140014b7c  jmp     loc_140014D13
0x140014b81  lea     rax, [rbp+57h+var_70]
0x140014b85  mov     [rbp+57h+var_70], r14w
0x140014b8a  mov     [rbp+57h+Src], rax
0x140014b8e  lea     rdx, [rbp+57h+Src]
0x140014b92  lea     rax, [rbp+57h+var_70]
0x140014b96  mov     rcx, rdi; lpFileName
0x140014b99  mov     [rbp+57h+var_78], rax
0x140014b9d  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140014ba2  test    eax, eax
0x140014ba4  jz      loc_140014C6D
0x140014baa  mov     rbx, [rbp+57h+var_78]
0x140014bae  sub     rbx, [rbp+57h+Src]
0x140014bb2  sar     rbx, 1
0x140014bb5  cmp     rbx, 104h
0x140014bbc  jb      loc_140014C56
0x140014bc2  mov     [rdi], r14w
0x140014bc6  mov     ebx, 80070057h
0x140014bcb  mov     eax, cs:dword_14007A000
0x140014bd1  cmp     eax, 2
0x140014bd4  jbe     short loc_140014C34
0x140014bd6  mov     rcx, cs:qword_14007A018
0x140014bdd  mov     rax, cs:qword_14007A010
0x140014be4  test    al, 8
0x140014be6  jz      short loc_140014C34
0x140014be8  mov     rax, rcx
0x140014beb  and     eax, 8
0x140014bee  cmp     rax, rcx
0x140014bf1  jnz     short loc_140014C34
0x140014bf3  lea     rax, [rbp+57h+var_90]
0x140014bf7  mov     [rbp+57h+var_90], 80070057h
0x140014bfe  mov     [rbp+57h+var_40], rax
0x140014c02  lea     rdx, dword_14006EEDC
0x140014c09  lea     rax, [rbp+57h+var_60]
0x140014c0d  mov     [rbp+57h+var_38], 4
0x140014c15  mov     [rsp+0C0h+var_98], rax
0x140014c1a  lea     rcx, dword_14007A000
0x140014c21  xor     r9d, r9d
0x140014c24  mov     dword ptr [rsp+0C0h+var_A0], 3
0x140014c2c  xor     r8d, r8d
0x140014c2f  call    _tlgWriteTransfer_EventWriteTransfer
0x140014c34  mov     rcx, [rbp+57h+Src]; void *
0x140014c38  lea     rax, [rbp+57h+var_70]
0x140014c3c  cmp     rcx, rax
0x140014c3f  jz      loc_140014D13
0x140014c45  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140014c4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014c51  jmp     loc_140014D13
0x140014c56  mov     rdx, [rbp+57h+Src]; Src
0x140014c5a  add     rbx, rbx
0x140014c5d  mov     r8, rbx; Size
0x140014c60  mov     rcx, rdi; void *
0x140014c63  call    memcpy_0
0x140014c68  mov     [rbx+rdi], r14w
0x140014c6d  lea     rax, [rbp+57h+var_70]
0x140014c71  cmp     [rbp+57h+Src], rax
0x140014c75  jz      short loc_140014C87
0x140014c77  mov     rcx, [rbp+57h+Src]; void *
0x140014c7b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140014c82  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014c87  mov     ebx, r14d
0x140014c8a  jmp     loc_140014D13
0x140014c8f  call    cs:__imp_GetLastError
0x140014c95  mov     ebx, eax
0x140014c97  test    eax, eax
0x140014c99  jle     short loc_140014CA4
0x140014c9b  movzx   ebx, ax
0x140014c9e  or      ebx, 80070000h
0x140014ca4  test    ebx, ebx
0x140014ca6  mov     eax, 80004005h
0x140014cab  cmovns  ebx, eax
0x140014cae  mov     eax, cs:dword_14007A000
0x140014cb4  cmp     eax, 2
0x140014cb7  jbe     short loc_140014D13
0x140014cb9  mov     rcx, cs:qword_14007A018
0x140014cc0  mov     rax, cs:qword_14007A010
0x140014cc7  test    al, 8
0x140014cc9  jz      short loc_140014D13
0x140014ccb  mov     rax, rcx
0x140014cce  and     eax, 8
0x140014cd1  cmp     rax, rcx
0x140014cd4  jnz     short loc_140014D13
0x140014cd6  lea     rax, [rbp+57h+var_90]
0x140014cda  mov     [rbp+57h+var_90], ebx
0x140014cdd  mov     [rbp+57h+var_40], rax
0x140014ce1  lea     rdx, dword_14006EF54
0x140014ce8  lea     rax, [rbp+57h+var_60]
0x140014cec  mov     [rbp+57h+var_38], 4
0x140014cf4  mov     [rsp+0C0h+var_98], rax
0x140014cf9  lea     rcx, dword_14007A000
0x140014d00  xor     r9d, r9d
0x140014d03  mov     dword ptr [rsp+0C0h+var_A0], 3
0x140014d0b  xor     r8d, r8d
0x140014d0e  call    _tlgWriteTransfer_EventWriteTransfer
0x140014d13  mov     eax, cs:dword_14007A000
0x140014d19  cmp     eax, 2
0x140014d1c  jbe     short loc_140014D60
0x140014d1e  mov     rdx, cs:qword_14007A018
0x140014d25  mov     rax, cs:qword_14007A010
0x140014d2c  test    al, 8
0x140014d2e  jz      short loc_140014D60
0x140014d30  mov     rcx, rdx
0x140014d33  and     ecx, 8
0x140014d36  cmp     rcx, rdx
0x140014d39  jnz     short loc_140014D60
0x140014d3b  lea     rax, [rbp+57h+var_90]
0x140014d3f  mov     [rbp+57h+var_90], ebx
0x140014d42  mov     [rsp+0C0h+var_98], rax
0x140014d47  lea     rdx, byte_14006EEA3
0x140014d4e  lea     rax, [rbp+57h+var_88]
0x140014d52  mov     [rbp+57h+var_88], rdi
0x140014d56  mov     [rsp+0C0h+var_A0], rax
0x140014d5b  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140014d60  mov     eax, ebx
0x140014d62  jmp     short loc_140014DBB
0x140014d64  mov     eax, cs:dword_14007A000
0x140014d6a  cmp     eax, 2
0x140014d6d  jbe     short loc_140014DB6
0x140014d6f  mov     rcx, cs:qword_14007A018
0x140014d76  mov     rax, cs:qword_14007A010
0x140014d7d  test    al, 8
0x140014d7f  jz      short loc_140014DB6
0x140014d81  mov     rax, rcx
0x140014d84  and     eax, 8
0x140014d87  cmp     rax, rcx
0x140014d8a  jnz     short loc_140014DB6
0x140014d8c  lea     rax, [rbp+57h+var_60]
0x140014d90  xor     r9d, r9d
0x140014d93  mov     [rsp+0C0h+var_98], rax
0x140014d98  lea     rdx, qword_14006EF88
0x140014d9f  xor     r8d, r8d
0x140014da2  mov     dword ptr [rsp+0C0h+var_A0], 2
0x140014daa  lea     rcx, dword_14007A000
0x140014db1  call    _tlgWriteTransfer_EventWriteTransfer
0x140014db6  mov     eax, 80070057h
0x140014dbb  mov     rcx, [rbp+57h+var_30]
0x140014dbf  xor     rcx, rsp; StackCookie
0x140014dc2  call    __security_check_cookie
0x140014dc7  add     rsp, 0A8h
0x140014dce  pop     r14
0x140014dd0  pop     rdi
0x140014dd1  pop     rbx
0x140014dd2  pop     rbp
0x140014dd3  retn
```
