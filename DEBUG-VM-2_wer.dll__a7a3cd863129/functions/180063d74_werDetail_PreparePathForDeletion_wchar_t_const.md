# _werDetail::PreparePathForDeletion(wchar_t const *)

- ea: `0x180063d74`
- end: `0x180063e9d`
- name: `?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z`
- size: `297`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001abd8`

## callees

- `0x18000716c`
- `0x180023dc4`
- `0x180023e8c`
- `0x1800303dc`
- `0x180063d74`
- `0x18006493c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e38`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180063e2e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180063e2e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180063ddb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180063ddb`

## pseudocode

```c
__int64 __fastcall _werDetail::PreparePathForDeletion(LPCWSTR lpFileName, const wchar_t *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned __int8 *v12; // rdx
  DWORD v13; // eax
  unsigned int v15; // [rsp+48h] [rbp+10h] BYREF
  const size_t *v16; // [rsp+50h] [rbp+18h] BYREF

  v3 = UtilAddAccessToPath(lpFileName, 0x10140u);
  if ( (v3 & 0x80000000) == 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(LastError);
      if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        return v3;
      v12 = (unsigned __int8 *)&unk_1800C6910;
    }
    else
    {
      if ( (FileAttributesW & 1) == 0 )
        return v3;
      if ( SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
        return v3;
      v13 = GetLastError();
      v3 = ERROR_HR_FROM_WIN32(v13);
      if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
        return v3;
      v12 = (unsigned __int8 *)byte_1800C6953;
    }
    v15 = v3;
    v16 = (const size_t *)lpFileName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v9,
      v12,
      v10,
      v11,
      &v16,
      (__int64)&v15);
    return v3;
  }
  if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    v15 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (unsigned __int8 *)byte_1800C68DB,
      v5,
      v6,
      (__int64)&v15);
  }
  return v3;
}

```

## disassembly

```asm
0x180063d74  mov     [rsp+arg_0], rbx
0x180063d79  push    rdi
0x180063d7a  sub     rsp, 30h
0x180063d7e  mov     edx, 10140h; unsigned int
0x180063d83  mov     rdi, rcx
0x180063d86  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x180063d8b  mov     ebx, eax
0x180063d8d  test    eax, eax
0x180063d8f  jns     short loc_180063DD8
0x180063d91  mov     ecx, cs:dword_1800D8000
0x180063d97  cmp     ecx, 2
0x180063d9a  jbe     loc_180063E90
0x180063da0  mov     edx, 8
0x180063da5  lea     rcx, dword_1800D8000
0x180063dac  call    _tlgKeywordOn
0x180063db1  test    al, al
0x180063db3  jz      loc_180063E90
0x180063db9  lea     rax, [rsp+38h+arg_8]
0x180063dbe  mov     [rsp+38h+arg_8], ebx
0x180063dc2  lea     rdx, byte_1800C68DB
0x180063dc9  mov     [rsp+38h+var_18], rax
0x180063dce  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063dd3  jmp     loc_180063E90
0x180063dd8  mov     rcx, rdi; lpFileName
0x180063ddb  call    cs:__imp_GetFileAttributesW
0x180063de1  cmp     eax, 0FFFFFFFFh
0x180063de4  jnz     short loc_180063E22
0x180063de6  call    cs:__imp_GetLastError
0x180063dec  mov     ecx, eax; unsigned int
0x180063dee  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063df3  mov     ebx, eax
0x180063df5  mov     eax, cs:dword_1800D8000
0x180063dfb  cmp     eax, 2
0x180063dfe  jbe     loc_180063E90
0x180063e04  mov     edx, 8
0x180063e09  lea     rcx, dword_1800D8000
0x180063e10  call    _tlgKeywordOn
0x180063e15  test    al, al
0x180063e17  jz      short loc_180063E90
0x180063e19  lea     rdx, unk_1800C6910
0x180063e20  jmp     short loc_180063E6E
0x180063e22  test    al, 1
0x180063e24  jz      short loc_180063E90
0x180063e26  and     eax, 0FFFFFFFEh
0x180063e29  mov     rcx, rdi; lpFileName
0x180063e2c  mov     edx, eax; dwFileAttributes
0x180063e2e  call    cs:__imp_SetFileAttributesW
0x180063e34  test    eax, eax
0x180063e36  jnz     short loc_180063E90
0x180063e38  call    cs:__imp_GetLastError
0x180063e3e  mov     ecx, eax; unsigned int
0x180063e40  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180063e45  mov     ebx, eax
0x180063e47  mov     eax, cs:dword_1800D8000
0x180063e4d  cmp     eax, 2
0x180063e50  jbe     short loc_180063E90
0x180063e52  mov     edx, 8
0x180063e57  lea     rcx, dword_1800D8000
0x180063e5e  call    _tlgKeywordOn
0x180063e63  test    al, al
0x180063e65  jz      short loc_180063E90
0x180063e67  lea     rdx, byte_1800C6953
0x180063e6e  lea     rax, [rsp+38h+arg_8]
0x180063e73  mov     [rsp+38h+var_10], rax
0x180063e78  lea     rax, [rsp+38h+arg_10]
0x180063e7d  mov     [rsp+38h+var_18], rax
0x180063e82  mov     [rsp+38h+arg_8], ebx
0x180063e86  mov     [rsp+38h+arg_10], rdi
0x180063e8b  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180063e90  mov     eax, ebx
0x180063e92  mov     rbx, [rsp+38h+arg_0]
0x180063e97  add     rsp, 30h
0x180063e9b  pop     rdi
0x180063e9c  retn
```
