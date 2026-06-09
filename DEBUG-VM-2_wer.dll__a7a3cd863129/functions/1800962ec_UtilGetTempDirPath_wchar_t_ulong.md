# UtilGetTempDirPath(wchar_t *,ulong)

- ea: `0x1800962ec`
- end: `0x18009652e`
- name: `?UtilGetTempDirPath@@YAJPEA_WK@Z`
- size: `578`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18001bbc4`

## callees

- `0x180002acc`
- `0x18000716c`
- `0x18000dad0`
- `0x180023dc4`
- `0x180023e8c`
- `0x1800303dc`
- `0x180030408`
- `0x18005b8d1`
- `0x18006549c`
- `0x1800962ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009645c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009645c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009634d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009634d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180096320`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180096320`

## pseudocode

```c
__int64 __fastcall UtilGetTempDirPath(WCHAR *lpFileName, int a2)
{
  DWORD v3; // eax
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned __int64 v8; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  unsigned __int64 v12; // rbx
  DWORD LastError; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 v21; // rcx
  void *Src; // [rsp+30h] [rbp-20h] BYREF
  char *v23; // [rsp+38h] [rbp-18h]
  _WORD v24[8]; // [rsp+40h] [rbp-10h] BYREF
  WCHAR *v25; // [rsp+70h] [rbp+20h] BYREF
  int v26; // [rsp+78h] [rbp+28h] BYREF

  v26 = a2;
  if ( lpFileName )
  {
    *lpFileName = 0;
    if ( !(unsigned int)GetTempPath2W(260, lpFileName) || !*lpFileName )
    {
      LastError = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(LastError);
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v26 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)byte_1800C87BD,
          v15,
          v16,
          (__int64)&v26);
      }
      goto LABEL_21;
    }
    if ( UtilPathIsDirectory(lpFileName) || CreateDirectoryW(lpFileName, 0) )
    {
      v24[0] = 0;
      Src = v24;
      v23 = (char *)v24;
      if ( (unsigned int)UtilGetFinalPath(lpFileName) )
      {
        v8 = (v23 - (_BYTE *)Src) >> 1;
        if ( v8 >= 0x104 )
        {
          *lpFileName = 0;
          v4 = -2147024809;
          if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
          {
            v26 = -2147024809;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              v9,
              (unsigned int)byte_1800C8745,
              v10,
              v11,
              (__int64)&v26);
          }
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Src);
          goto LABEL_21;
        }
        v12 = v8;
        memcpy_0(lpFileName, Src, v12 * 2);
        lpFileName[v12] = 0;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&Src);
      v4 = 0;
    }
    else
    {
      v3 = GetLastError();
      v4 = ERROR_HR_FROM_WIN32(v3);
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v26 = v4;
        v25 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v5,
          (unsigned int)byte_1800C8779,
          v6,
          v7,
          (__int64)&v25,
          (__int64)&v26);
      }
      *lpFileName = 0;
    }
LABEL_21:
    if ( (unsigned int)dword_1800D8000 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v26 = v4;
        v25 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&dword_1800C870C,
          v18,
          v19,
          (__int64)&v25,
          (__int64)&v26);
      }
    }
    return v4;
  }
  if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v21,
      byte_1800C87F1);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800962ec  mov     [rsp-18h+arg_10], rbx
0x1800962f1  mov     [rsp-18h+arg_18], rsi
0x1800962f6  mov     [rsp-18h+arg_8], edx
0x1800962fa  push    rbp
0x1800962fb  push    rdi
0x1800962fc  push    r15
0x1800962fe  mov     rbp, rsp
0x180096301  sub     rsp, 50h
0x180096305  xor     r15d, r15d
0x180096308  mov     rdi, rcx
0x18009630b  test    rcx, rcx
0x18009630e  jz      loc_1800964E8
0x180096314  mov     [rcx], r15w
0x180096318  mov     rdx, rcx
0x18009631b  mov     ecx, 104h
0x180096320  call    cs:__imp_GetTempPath2W
0x180096326  lea     esi, [r15+8]
0x18009632a  test    eax, eax
0x18009632c  jz      loc_18009645C
0x180096332  cmp     [rdi], r15w
0x180096336  jz      loc_18009645C
0x18009633c  mov     rcx, rdi; wchar_t *
0x18009633f  call    ?UtilPathIsDirectory@@YA_NPEB_W@Z; UtilPathIsDirectory(wchar_t const *)
0x180096344  test    al, al
0x180096346  jnz     short loc_1800963B1
0x180096348  xor     edx, edx; lpSecurityAttributes
0x18009634a  mov     rcx, rdi; lpPathName
0x18009634d  call    cs:__imp_CreateDirectoryW
0x180096353  test    eax, eax
0x180096355  jnz     short loc_1800963B1
0x180096357  call    cs:__imp_GetLastError
0x18009635d  mov     ecx, eax; unsigned int
0x18009635f  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180096364  mov     ebx, eax
0x180096366  mov     eax, cs:dword_1800D8000
0x18009636c  cmp     eax, 2
0x18009636f  jbe     short loc_1800963A8
0x180096371  mov     edx, esi
0x180096373  lea     rcx, dword_1800D8000
0x18009637a  call    _tlgKeywordOn
0x18009637f  test    al, al
0x180096381  jz      short loc_1800963A8
0x180096383  lea     rax, [rbp+arg_8]
0x180096387  mov     [rbp+arg_8], ebx
0x18009638a  mov     [rsp+50h+var_28], rax
0x18009638f  lea     rdx, byte_1800C8779
0x180096396  lea     rax, [rbp+arg_0]
0x18009639a  mov     [rbp+arg_0], rdi
0x18009639e  mov     [rsp+50h+var_30], rax
0x1800963a3  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800963a8  mov     [rdi], r15w
0x1800963ac  jmp     loc_1800964A1
0x1800963b1  lea     rax, [rbp+var_10]
0x1800963b5  mov     [rbp+var_10], r15w
0x1800963ba  mov     [rbp+Src], rax
0x1800963be  lea     rdx, [rbp+Src]
0x1800963c2  lea     rax, [rbp+var_10]
0x1800963c6  mov     rcx, rdi; lpFileName
0x1800963c9  mov     [rbp+var_18], rax
0x1800963cd  call    ?UtilGetFinalPath@@YAHPEB_WAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetFinalPath(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800963d2  test    eax, eax
0x1800963d4  jz      short loc_18009644E
0x1800963d6  mov     rbx, [rbp+var_18]
0x1800963da  mov     rdx, [rbp+Src]; Src
0x1800963de  sub     rbx, rdx
0x1800963e1  sar     rbx, 1
0x1800963e4  cmp     rbx, 104h
0x1800963eb  jb      short loc_18009643B
0x1800963ed  mov     [rdi], r15w
0x1800963f1  mov     ebx, 80070057h
0x1800963f6  mov     eax, cs:dword_1800D8000
0x1800963fc  cmp     eax, 2
0x1800963ff  jbe     short loc_180096430
0x180096401  mov     rdx, rsi
0x180096404  lea     rcx, dword_1800D8000
0x18009640b  call    _tlgKeywordOn
0x180096410  test    al, al
0x180096412  jz      short loc_180096430
0x180096414  lea     rax, [rbp+arg_8]
0x180096418  mov     [rbp+arg_8], 80070057h
0x18009641f  lea     rdx, byte_1800C8745
0x180096426  mov     [rsp+50h+var_30], rax
0x18009642b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180096430  lea     rcx, [rbp+Src]; void *
0x180096434  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180096439  jmp     short loc_1800964A1
0x18009643b  add     rbx, rbx
0x18009643e  mov     rcx, rdi; void *
0x180096441  mov     r8, rbx; Size
0x180096444  call    memcpy_0
0x180096449  mov     [rbx+rdi], r15w
0x18009644e  lea     rcx, [rbp+Src]; void *
0x180096452  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180096457  mov     ebx, r15d
0x18009645a  jmp     short loc_1800964A1
0x18009645c  call    cs:__imp_GetLastError
0x180096462  mov     ecx, eax; unsigned int
0x180096464  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180096469  mov     ebx, eax
0x18009646b  mov     eax, cs:dword_1800D8000
0x180096471  cmp     eax, 2
0x180096474  jbe     short loc_1800964A1
0x180096476  mov     rdx, rsi
0x180096479  lea     rcx, dword_1800D8000
0x180096480  call    _tlgKeywordOn
0x180096485  test    al, al
0x180096487  jz      short loc_1800964A1
0x180096489  lea     rax, [rbp+arg_8]
0x18009648d  mov     [rbp+arg_8], ebx
0x180096490  lea     rdx, byte_1800C87BD
0x180096497  mov     [rsp+50h+var_30], rax
0x18009649c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800964a1  mov     eax, cs:dword_1800D8000
0x1800964a7  cmp     eax, 2
0x1800964aa  jbe     short loc_1800964E4
0x1800964ac  mov     rdx, rsi
0x1800964af  lea     rcx, dword_1800D8000
0x1800964b6  call    _tlgKeywordOn
0x1800964bb  test    al, al
0x1800964bd  jz      short loc_1800964E4
0x1800964bf  lea     rax, [rbp+arg_8]
0x1800964c3  mov     [rbp+arg_8], ebx
0x1800964c6  mov     [rsp+50h+var_28], rax
0x1800964cb  lea     rdx, dword_1800C870C
0x1800964d2  lea     rax, [rbp+arg_0]
0x1800964d6  mov     [rbp+arg_0], rdi
0x1800964da  mov     [rsp+50h+var_30], rax
0x1800964df  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1800964e4  mov     eax, ebx
0x1800964e6  jmp     short loc_180096519
0x1800964e8  mov     eax, cs:dword_1800D8000
0x1800964ee  cmp     eax, 2
0x1800964f1  jbe     short loc_180096514
0x1800964f3  mov     edx, 8
0x1800964f8  lea     rcx, dword_1800D8000
0x1800964ff  call    _tlgKeywordOn
0x180096504  test    al, al
0x180096506  jz      short loc_180096514
0x180096508  lea     rdx, byte_1800C87F1
0x18009650f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180096514  mov     eax, 80070057h
0x180096519  lea     r11, [rsp+50h+var_s0]
0x18009651e  mov     rbx, [r11+30h]
0x180096522  mov     rsi, [r11+38h]
0x180096526  mov     rsp, r11
0x180096529  pop     r15
0x18009652b  pop     rdi
0x18009652c  pop     rbp
0x18009652d  retn
```
