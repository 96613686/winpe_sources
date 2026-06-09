# _werDetail::PreparePathForDeletion(wchar_t const *)

- ea: `0x140008ce4`
- end: `0x140008ea0`
- name: `?PreparePathForDeletion@_werDetail@@YAJPEB_W@Z`
- size: `444`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000be08`

## callees

- `0x140001270`
- `0x14000162c`
- `0x140003200`
- `0x140008ce4`
- `0x14000a804`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008d9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008e11`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140008e07`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140008e07`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140008d94`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140008d94`

## pseudocode

```c
__int64 __fastcall _werDetail::PreparePathForDeletion(LPCWSTR lpFileName, const wchar_t *a2)
{
  int v3; // ebx
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  __int16 *v9; // rdx
  signed int v10; // eax
  int v12; // [rsp+30h] [rbp-50h] BYREF
  LPCWSTR v13; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-40h] BYREF
  int *v15; // [rsp+60h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-18h]

  v3 = UtilAddAccessToPath(lpFileName, (const struct std::nothrow_t *)0x10140);
  if ( v3 < 0 )
  {
    if ( (unsigned int)dword_14002C000 > 2 && (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
    {
      v12 = v3;
      v15 = &v12;
      v16 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_14002C000, (unsigned __int8 *)&unk_140026278, 0, 0, 3u, &v14);
    }
    return (unsigned int)v3;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    if ( (unsigned int)dword_14002C000 > 2 )
    {
      v8 = qword_14002C018;
      if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        v9 = (__int16 *)byte_140026235;
LABEL_25:
        v12 = v3;
        v13 = lpFileName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
          v8,
          (_DWORD)v9,
          v6,
          v7,
          (__int64)&v13,
          (__int64)&v12);
      }
    }
  }
  else if ( (FileAttributesW & 1) != 0 && !SetFileAttributesW(lpFileName, FileAttributesW & 0xFFFFFFFE) )
  {
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    if ( (unsigned int)dword_14002C000 > 2 )
    {
      v8 = qword_14002C018;
      if ( (qword_14002C010 & 8) != 0 && (qword_14002C018 & 8) == qword_14002C018 )
      {
        v9 = word_1400261F2;
        goto LABEL_25;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140008ce4  mov     [rsp-8+arg_8], rbx
0x140008ce9  mov     [rsp-8+arg_10], rdi
0x140008cee  push    rbp
0x140008cef  mov     rbp, rsp
0x140008cf2  sub     rsp, 80h
0x140008cf9  mov     rax, cs:__security_cookie
0x140008d00  xor     rax, rsp
0x140008d03  mov     [rbp+var_10], rax
0x140008d07  mov     edx, 10140h; unsigned int
0x140008d0c  mov     rdi, rcx
0x140008d0f  call    ?UtilAddAccessToPath@@YAJPEB_WK@Z; UtilAddAccessToPath(wchar_t const *,ulong)
0x140008d14  mov     ebx, eax
0x140008d16  test    eax, eax
0x140008d18  jns     short loc_140008D91
0x140008d1a  mov     ecx, cs:dword_14002C000
0x140008d20  cmp     ecx, 2
0x140008d23  jbe     loc_140008E7D
0x140008d29  mov     rdx, cs:qword_14002C018
0x140008d30  mov     rcx, cs:qword_14002C010
0x140008d37  test    cl, 8
0x140008d3a  jz      loc_140008E7D
0x140008d40  mov     rax, rdx
0x140008d43  and     eax, 8
0x140008d46  cmp     rax, rdx
0x140008d49  jnz     loc_140008E7D
0x140008d4f  lea     rax, [rbp+var_50]
0x140008d53  mov     [rbp+var_50], ebx
0x140008d56  mov     [rbp+var_20], rax
0x140008d5a  lea     rdx, unk_140026278
0x140008d61  lea     rax, [rbp+var_40]
0x140008d65  mov     [rbp+var_18], 4
0x140008d6d  mov     [rsp+80h+var_58], rax
0x140008d72  lea     rcx, dword_14002C000
0x140008d79  xor     r9d, r9d
0x140008d7c  mov     dword ptr [rsp+80h+var_60], 3
0x140008d84  xor     r8d, r8d
0x140008d87  call    _tlgWriteTransfer_EventWriteTransfer
0x140008d8c  jmp     loc_140008E7D
0x140008d91  mov     rcx, rdi; lpFileName
0x140008d94  call    cs:__imp_GetFileAttributesW
0x140008d9a  cmp     eax, 0FFFFFFFFh
0x140008d9d  jnz     short loc_140008DFB
0x140008d9f  call    cs:__imp_GetLastError
0x140008da5  mov     ebx, eax
0x140008da7  test    eax, eax
0x140008da9  jle     short loc_140008DB4
0x140008dab  movzx   ebx, ax
0x140008dae  or      ebx, 80070000h
0x140008db4  test    ebx, ebx
0x140008db6  mov     eax, 80004005h
0x140008dbb  cmovns  ebx, eax
0x140008dbe  mov     eax, cs:dword_14002C000
0x140008dc4  cmp     eax, 2
0x140008dc7  jbe     loc_140008E7D
0x140008dcd  mov     rcx, cs:qword_14002C018
0x140008dd4  mov     rax, cs:qword_14002C010
0x140008ddb  test    al, 8
0x140008ddd  jz      loc_140008E7D
0x140008de3  mov     rax, rcx
0x140008de6  and     eax, 8
0x140008de9  cmp     rax, rcx
0x140008dec  jnz     loc_140008E7D
0x140008df2  lea     rdx, byte_140026235
0x140008df9  jmp     short loc_140008E5F
0x140008dfb  test    al, 1
0x140008dfd  jz      short loc_140008E7D
0x140008dff  and     eax, 0FFFFFFFEh
0x140008e02  mov     rcx, rdi; lpFileName
0x140008e05  mov     edx, eax; dwFileAttributes
0x140008e07  call    cs:__imp_SetFileAttributesW
0x140008e0d  test    eax, eax
0x140008e0f  jnz     short loc_140008E7D
0x140008e11  call    cs:__imp_GetLastError
0x140008e17  mov     ebx, eax
0x140008e19  test    eax, eax
0x140008e1b  jle     short loc_140008E26
0x140008e1d  movzx   ebx, ax
0x140008e20  or      ebx, 80070000h
0x140008e26  test    ebx, ebx
0x140008e28  mov     eax, 80004005h
0x140008e2d  cmovns  ebx, eax
0x140008e30  mov     eax, cs:dword_14002C000
0x140008e36  cmp     eax, 2
0x140008e39  jbe     short loc_140008E7D
0x140008e3b  mov     rcx, cs:qword_14002C018
0x140008e42  mov     rax, cs:qword_14002C010
0x140008e49  test    al, 8
0x140008e4b  jz      short loc_140008E7D
0x140008e4d  mov     rax, rcx
0x140008e50  and     eax, 8
0x140008e53  cmp     rax, rcx
0x140008e56  jnz     short loc_140008E7D
0x140008e58  lea     rdx, word_1400261F2
0x140008e5f  lea     rax, [rbp+var_50]
0x140008e63  mov     [rsp+80h+var_58], rax
0x140008e68  lea     rax, [rbp+var_48]
0x140008e6c  mov     [rsp+80h+var_60], rax
0x140008e71  mov     [rbp+var_50], ebx
0x140008e74  mov     [rbp+var_48], rdi
0x140008e78  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x140008e7d  mov     eax, ebx
0x140008e7f  mov     rcx, [rbp+var_10]
0x140008e83  xor     rcx, rsp; StackCookie
0x140008e86  call    __security_check_cookie
0x140008e8b  lea     r11, [rsp+80h+var_s0]
0x140008e93  mov     rbx, [r11+18h]
0x140008e97  mov     rdi, [r11+20h]
0x140008e9b  mov     rsp, r11
0x140008e9e  pop     rbp
0x140008e9f  retn
```
