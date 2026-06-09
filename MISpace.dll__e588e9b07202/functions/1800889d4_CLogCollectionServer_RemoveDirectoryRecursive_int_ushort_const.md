# CLogCollectionServer::_RemoveDirectoryRecursive(int,ushort const *)

- ea: `0x1800889d4`
- end: `0x180088cbc`
- name: `?_RemoveDirectoryRecursive@CLogCollectionServer@@AEBA?AV_status_t@@HPEBG@Z`
- size: `744`
- prototype: `struct _status_t __high(int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18008488c`
- `0x1800889d4`

## callees

- `0x1800015b8`
- `0x180006290`
- `0x180006cf4`
- `0x18000ce3c`
- `0x180028f84`
- `0x1800889d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180088acb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180088acb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180088c5b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180088c5b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180088c90`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180088c90`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180088bf7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180088bf7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180088bbe`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180088bbe`

## string_xrefs

- `0x180088a86`: `CLogCollectionServer::_RemoveDirectoryRecursive`
- `0x180088ad4`: `CLogCollectionServer::_RemoveDirectoryRecursive`

## pseudocode

```c
_status_t *__fastcall CLogCollectionServer::_RemoveDirectoryRecursive(_DWORD *a1, _status_t *a2, int a3, __int64 a4)
{
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  char *FirstFileW; // rsi
  int v12; // eax
  bool v13; // zf
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  BOOL v18; // eax
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int *v22; // rdx
  BOOL v23; // eax
  BOOL NextFileW; // eax
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  const char *v28; // [rsp+48h] [rbp-B8h] BYREF
  char v29[16]; // [rsp+50h] [rbp-B0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR PathName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  *(_QWORD *)a2 = 0;
  *((_BYTE *)a2 + 8) = 0;
  if ( a3 > *a1 )
    return a2;
  v8 = StringCchPrintfW(FileName, 0x104u, L"%s*", a4);
  *(_DWORD *)a2 = v8;
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v26 = v8;
      v27 = 2376;
      v28 = "CLogCollectionServer::_RemoveDirectoryRecursive";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)word_18031712A,
        v9,
        v10,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
    return a2;
  }
  FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
  do
  {
    if ( FindFileData.cFileName[0] != 46
      || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
    {
      memset_0(PathName, 0, 0x208u);
      v12 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a4, FindFileData.cFileName);
      v13 = (FindFileData.dwFileAttributes & 0x10) == 0;
      *(_DWORD *)a2 = v12;
      if ( v13 )
      {
        v23 = DeleteFileW(PathName);
        _status_t::SetBoolGle(a2, v23);
        v21 = *(_DWORD *)a2;
        if ( *(int *)a2 < 0 && (unsigned int)dword_180397B68 > 2 )
        {
          v26 = 2412;
          v22 = &dword_1803161AC;
          goto LABEL_20;
        }
      }
      else
      {
        v14 = CLogCollectionServer::_RemoveDirectoryRecursive(a1, v29, (unsigned int)(a3 + 1), PathName);
        *(_QWORD *)a2 = *(_QWORD *)v14;
        *((_DWORD *)a2 + 2) = *(_DWORD *)(v14 + 8);
        v17 = *(_DWORD *)a2;
        if ( *(int *)a2 < 0 && (unsigned int)dword_180397B68 > 2 )
        {
          v27 = *(_DWORD *)a2;
          v26 = 2399;
          v28 = "CLogCollectionServer::_RemoveDirectoryRecursive";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)&unk_180317350,
            v15,
            v16,
            (__int64)&v28,
            (__int64)&v26,
            (__int64)&v27);
        }
        v18 = RemoveDirectoryW(PathName);
        _status_t::SetBoolGle(a2, v18);
        v21 = *(_DWORD *)a2;
        if ( *(int *)a2 < 0 && (unsigned int)dword_180397B68 > 2 )
        {
          v26 = 2405;
          v22 = (int *)byte_1803165B5;
LABEL_20:
          v27 = v21;
          v28 = "CLogCollectionServer::_RemoveDirectoryRecursive";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v21,
            (_DWORD)v22,
            v19,
            v20,
            (__int64)&v28,
            (__int64)&v26,
            (__int64)&v27);
        }
      }
    }
    NextFileW = FindNextFileW(FirstFileW, &FindFileData);
    _status_t::SetBoolGle(a2, NextFileW);
  }
  while ( *(int *)a2 >= 0 );
  if ( *(_DWORD *)a2 == -2147024878 )
  {
    *(_QWORD *)a2 = 0;
    *((_BYTE *)a2 + 8) = 0;
  }
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
  return a2;
}

```

## disassembly

```asm
0x1800889d4  push    rbp
0x1800889d6  push    rbx
0x1800889d7  push    rsi
0x1800889d8  push    rdi
0x1800889d9  push    r12
0x1800889db  push    r13
0x1800889dd  push    r14
0x1800889df  push    r15
0x1800889e1  lea     rbp, [rsp-5E8h]
0x1800889e9  sub     rsp, 6E8h
0x1800889f0  mov     rax, cs:__security_cookie
0x1800889f7  xor     rax, rsp
0x1800889fa  mov     [rbp+620h+var_50], rax
0x180088a01  mov     r13d, r8d
0x180088a04  mov     rbx, rdx
0x180088a07  mov     r15, rcx
0x180088a0a  xor     edx, edx; Val
0x180088a0c  mov     r8d, 208h; Size
0x180088a12  lea     rcx, [rbp+620h+FileName]; void *
0x180088a19  mov     r14, r9
0x180088a1c  call    memset_0
0x180088a21  xor     edx, edx; Val
0x180088a23  lea     rcx, [rsp+720h+FindFileData]; void *
0x180088a28  mov     r8d, 250h; Size
0x180088a2e  call    memset_0
0x180088a33  xor     r12d, r12d
0x180088a36  mov     [rbx], r12
0x180088a39  mov     [rbx+8], r12b
0x180088a3d  cmp     r13d, [r15]
0x180088a40  jg      loc_180088C96
0x180088a46  mov     r9, r14
0x180088a49  lea     r8, aS_3; "%s*"
0x180088a50  mov     edx, 104h; unsigned __int64
0x180088a55  lea     rcx, [rbp+620h+FileName]; unsigned __int16 *
0x180088a5c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180088a61  mov     [rbx], eax
0x180088a63  mov     ecx, eax
0x180088a65  test    eax, eax
0x180088a67  jns     short loc_180088ABF
0x180088a69  mov     eax, cs:dword_180397B68
0x180088a6f  cmp     eax, 2
0x180088a72  jbe     loc_180088C96
0x180088a78  lea     rax, [rsp+720h+var_6E0]
0x180088a7d  mov     [rsp+720h+var_6E0], ecx
0x180088a81  mov     [rsp+720h+var_6F0], rax
0x180088a86  lea     rdi, aClogcollection_24; "CLogCollectionServer::_RemoveDirectoryR"...
0x180088a8d  lea     rax, [rsp+720h+var_6DC]
0x180088a92  mov     [rsp+720h+var_6DC], 948h
0x180088a9a  mov     [rsp+720h+var_6F8], rax
0x180088a9f  lea     rdx, word_18031712A
0x180088aa6  lea     rax, [rsp+720h+var_6D8]
0x180088aab  mov     [rsp+720h+var_6D8], rdi
0x180088ab0  mov     [rsp+720h+var_700], rax
0x180088ab5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088aba  jmp     loc_180088C96
0x180088abf  lea     rdx, [rsp+720h+FindFileData]; lpFindFileData
0x180088ac4  lea     rcx, [rbp+620h+FileName]; lpFileName
0x180088acb  call    cs:__imp_FindFirstFileW
0x180088ad1  mov     rsi, rax
0x180088ad4  lea     rdi, aClogcollection_24; "CLogCollectionServer::_RemoveDirectoryR"...
0x180088adb  cmp     [rbp+620h+FindFileData.cFileName], 2Eh ; '.'
0x180088ae0  jnz     short loc_180088B00
0x180088ae2  movzx   ecx, [rbp+620h+FindFileData.cFileName+2]
0x180088ae6  test    cx, cx
0x180088ae9  jz      loc_180088C53
0x180088aef  cmp     cx, 2Eh ; '.'
0x180088af3  jnz     short loc_180088B00
0x180088af5  cmp     [rbp+620h+FindFileData.cFileName+4], r12w
0x180088afa  jz      loc_180088C53
0x180088b00  xor     edx, edx; Val
0x180088b02  lea     rcx, [rbp+620h+PathName]; void *
0x180088b09  mov     r8d, 208h; Size
0x180088b0f  call    memset_0
0x180088b14  lea     rax, [rbp+620h+FindFileData.cFileName]
0x180088b18  mov     r9, r14
0x180088b1b  lea     r8, Format; "%s\\%s"
0x180088b22  mov     [rsp+720h+var_700], rax
0x180088b27  mov     edx, 104h; unsigned __int64
0x180088b2c  lea     rcx, [rbp+620h+PathName]; unsigned __int16 *
0x180088b33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180088b38  test    byte ptr [rsp+720h+FindFileData.dwFileAttributes], 10h
0x180088b3d  mov     [rbx], eax
0x180088b3f  jz      loc_180088BF0
0x180088b45  lea     r8d, [r13+1]
0x180088b49  mov     rcx, r15
0x180088b4c  lea     r9, [rbp+620h+PathName]
0x180088b53  lea     rdx, [rsp+720h+var_6D0]
0x180088b58  call    ?_RemoveDirectoryRecursive@CLogCollectionServer@@AEBA?AV_status_t@@HPEBG@Z; CLogCollectionServer::_RemoveDirectoryRecursive(int,ushort const *)
0x180088b5d  movsd   xmm0, qword ptr [rax]
0x180088b61  movsd   qword ptr [rbx], xmm0
0x180088b65  mov     eax, [rax+8]
0x180088b68  mov     [rbx+8], eax
0x180088b6b  mov     ecx, [rbx]
0x180088b6d  test    ecx, ecx
0x180088b6f  jns     short loc_180088BB7
0x180088b71  mov     eax, cs:dword_180397B68
0x180088b77  cmp     eax, 2
0x180088b7a  jbe     short loc_180088BB7
0x180088b7c  lea     rax, [rsp+720h+var_6DC]
0x180088b81  mov     [rsp+720h+var_6DC], ecx
0x180088b85  mov     [rsp+720h+var_6F0], rax
0x180088b8a  lea     rdx, unk_180317350
0x180088b91  lea     rax, [rsp+720h+var_6E0]
0x180088b96  mov     [rsp+720h+var_6E0], 95Fh
0x180088b9e  mov     [rsp+720h+var_6F8], rax
0x180088ba3  lea     rax, [rsp+720h+var_6D8]
0x180088ba8  mov     [rsp+720h+var_700], rax
0x180088bad  mov     [rsp+720h+var_6D8], rdi
0x180088bb2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088bb7  lea     rcx, [rbp+620h+PathName]; lpPathName
0x180088bbe  call    cs:__imp_RemoveDirectoryW
0x180088bc4  mov     edx, eax; int
0x180088bc6  mov     rcx, rbx; this
0x180088bc9  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x180088bce  mov     ecx, [rbx]
0x180088bd0  test    ecx, ecx
0x180088bd2  jns     short loc_180088C53
0x180088bd4  mov     eax, cs:dword_180397B68
0x180088bda  cmp     eax, 2
0x180088bdd  jbe     short loc_180088C53
0x180088bdf  mov     [rsp+720h+var_6E0], 965h
0x180088be7  lea     rdx, byte_1803165B5
0x180088bee  jmp     short loc_180088C27
0x180088bf0  lea     rcx, [rbp+620h+PathName]; lpFileName
0x180088bf7  call    cs:__imp_DeleteFileW
0x180088bfd  mov     edx, eax; int
0x180088bff  mov     rcx, rbx; this
0x180088c02  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x180088c07  mov     ecx, [rbx]
0x180088c09  test    ecx, ecx
0x180088c0b  jns     short loc_180088C53
0x180088c0d  mov     eax, cs:dword_180397B68
0x180088c13  cmp     eax, 2
0x180088c16  jbe     short loc_180088C53
0x180088c18  mov     [rsp+720h+var_6E0], 96Ch
0x180088c20  lea     rdx, dword_1803161AC
0x180088c27  lea     rax, [rsp+720h+var_6DC]
0x180088c2c  mov     [rsp+720h+var_6F0], rax
0x180088c31  lea     rax, [rsp+720h+var_6E0]
0x180088c36  mov     [rsp+720h+var_6F8], rax
0x180088c3b  lea     rax, [rsp+720h+var_6D8]
0x180088c40  mov     [rsp+720h+var_700], rax
0x180088c45  mov     [rsp+720h+var_6DC], ecx
0x180088c49  mov     [rsp+720h+var_6D8], rdi
0x180088c4e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180088c53  lea     rdx, [rsp+720h+FindFileData]; lpFindFileData
0x180088c58  mov     rcx, rsi; hFindFile
0x180088c5b  call    cs:__imp_FindNextFileW
0x180088c61  mov     edx, eax; int
0x180088c63  mov     rcx, rbx; this
0x180088c66  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x180088c6b  cmp     [rbx], r12d
0x180088c6e  jge     loc_180088ADB
0x180088c74  cmp     dword ptr [rbx], 80070012h
0x180088c7a  jnz     short loc_180088C83
0x180088c7c  mov     [rbx], r12
0x180088c7f  mov     [rbx+8], r12b
0x180088c83  lea     rcx, [rsi-1]
0x180088c87  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180088c8b  ja      short loc_180088C96
0x180088c8d  mov     rcx, rsi; hFindFile
0x180088c90  call    cs:__imp_FindClose
0x180088c96  mov     rax, rbx
0x180088c99  mov     rcx, [rbp+620h+var_50]
0x180088ca0  xor     rcx, rsp; StackCookie
0x180088ca3  call    __security_check_cookie
0x180088ca8  add     rsp, 6E8h
0x180088caf  pop     r15
0x180088cb1  pop     r14
0x180088cb3  pop     r13
0x180088cb5  pop     r12
0x180088cb7  pop     rdi
0x180088cb8  pop     rsi
0x180088cb9  pop     rbx
0x180088cba  pop     rbp
0x180088cbb  retn
```
