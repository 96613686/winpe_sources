# CMsmqVssWriter::CopyFiles(wchar_t const *,wchar_t const *,wchar_t const *,int,void *)

- ea: `0x18008f714`
- end: `0x18008f951`
- name: `?CopyFiles@CMsmqVssWriter@@AEAAJPEB_W00HPEAX@Z`
- size: `573`
- prototype: `__int64 __fastcall(CMsmqVssWriter *this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800921e0`
- `0x180093860`
- `0x180093a9c`

## callees

- `0x18000bb04`
- `0x1800261e0`
- `0x18002c61c`
- `0x18008f714`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18008f8c0`
- `KERNEL32!CopyFileW` at `0x18008f8c0`
- `KERNEL32!GetLastError` at `0x18008f7c3`
- `KERNEL32!GetLastError` at `0x18008f8ca`
- `KERNEL32!GetLastError` at `0x18008f7c3`
- `KERNEL32!GetLastError` at `0x18008f8ca`
- `KERNEL32!FindFirstFileW` at `0x18008f7af`
- `KERNEL32!FindFirstFileW` at `0x18008f7af`
- `KERNEL32!FindNextFileW` at `0x18008f8eb`
- `KERNEL32!FindNextFileW` at `0x18008f8eb`

## string_xrefs

- `0x18008f775`: `writer/mqwriter`
- `0x18008f7ef`: `writer/mqwriter`
- `0x18008f93e`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::CopyFiles(
        CMsmqVssWriter *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  HANDLE FirstFileW; // rbx
  signed int LastError; // eax
  int v10; // edx
  int v11; // edx
  signed int v12; // edi
  signed int v13; // eax
  unsigned __int16 v15; // r8
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF
  WCHAR NewFileName[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v6 = StringCchPrintfW(FileName, 0x105u, L"%s\\%s", a2, a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", 0xEB0u);
    return v7;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v16[0] = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 2 )
    {
LABEL_24:
      v7 = 0;
    }
    else
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
        LogMsgHR(v7, (wchar_t *)L"writer/mqwriter", 0xEC4u);
    }
    goto LABEL_25;
  }
  while ( 1 )
  {
    v10 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
      v10 = FindFileData.cFileName[1];
    if ( !v10 )
      goto LABEL_23;
    v11 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
    {
      v11 = FindFileData.cFileName[1] - 46;
      if ( FindFileData.cFileName[1] == 46 )
        v11 = FindFileData.cFileName[2];
    }
    if ( !v11 )
      goto LABEL_23;
    v12 = StringCchPrintfW(FileName, 0x105u, L"%s\\%s", a2, FindFileData.cFileName);
    if ( v12 < 0 )
      break;
    v12 = StringCchPrintfW(NewFileName, 0x105u, L"%s\\%s", a4, FindFileData.cFileName);
    if ( v12 < 0 )
    {
      v15 = 3820;
      goto LABEL_30;
    }
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 && !CopyFileW(FileName, NewFileName, 0) )
    {
      v13 = GetLastError();
      v12 = v13;
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      if ( v12 < 0 )
      {
        v15 = 3880;
        goto LABEL_30;
      }
    }
LABEL_23:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_24;
  }
  v15 = 3800;
LABEL_30:
  LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", v15);
  v7 = v12;
LABEL_25:
  CAutoCloseFindFile::~CAutoCloseFindFile((CAutoCloseFindFile *)v16);
  return v7;
}

```

## disassembly

```asm
0x18008f714  push    rbp
0x18008f716  push    rbx
0x18008f717  push    rsi
0x18008f718  push    rdi
0x18008f719  push    r13
0x18008f71b  push    r14
0x18008f71d  push    r15
0x18008f71f  lea     rbp, [rsp-5C0h]
0x18008f727  sub     rsp, 6C0h
0x18008f72e  mov     rax, cs:__security_cookie
0x18008f735  xor     rax, rsp
0x18008f738  mov     [rbp+5F0h+var_40], rax
0x18008f73f  mov     r14, r9
0x18008f742  mov     rsi, rdx
0x18008f745  mov     [rsp+6F0h+var_6D0], r8
0x18008f74a  mov     r9, rdx
0x18008f74d  lea     r8, aSS_3; "%s\\%s"
0x18008f754  mov     r13d, 105h
0x18008f75a  mov     edx, r13d; unsigned __int64
0x18008f75d  lea     rcx, [rbp+5F0h+FileName]; wchar_t *
0x18008f764  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008f769  mov     ebx, eax
0x18008f76b  test    eax, eax
0x18008f76d  jns     short loc_18008F788
0x18008f76f  mov     r8d, 0EB0h; unsigned __int16
0x18008f775  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f77c  mov     ecx, eax; int
0x18008f77e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f783  jmp     loc_18008F905
0x18008f788  mov     [rsp+6F0h+var_6C0], 0FFFFFFFFFFFFFFFFh
0x18008f791  xor     edx, edx; Val
0x18008f793  mov     r8d, 250h; Size
0x18008f799  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x18008f79e  call    memset_0
0x18008f7a3  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x18008f7a8  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x18008f7af  call    cs:__imp_FindFirstFileW
0x18008f7b5  mov     rbx, rax
0x18008f7b8  mov     [rsp+6F0h+var_6C0], rax
0x18008f7bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008f7c1  jnz     short loc_18008F802
0x18008f7c3  call    cs:__imp_GetLastError
0x18008f7c9  mov     ebx, eax
0x18008f7cb  cmp     eax, 2
0x18008f7ce  jz      loc_18008F8F9
0x18008f7d4  test    eax, eax
0x18008f7d6  jle     short loc_18008F7E1
0x18008f7d8  movzx   ebx, ax
0x18008f7db  or      ebx, 80070000h
0x18008f7e1  test    ebx, ebx
0x18008f7e3  jns     loc_18008F8FB
0x18008f7e9  mov     r8d, 0EC4h; unsigned __int16
0x18008f7ef  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f7f6  mov     ecx, ebx; int
0x18008f7f8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f7fd  jmp     loc_18008F8FB
0x18008f802  mov     r15d, 2Eh ; '.'
0x18008f808  movzx   edx, [rsp+6F0h+FindFileData.cFileName]
0x18008f80d  sub     edx, r15d
0x18008f810  jnz     short loc_18008F81E
0x18008f812  movzx   edx, [rsp+6F0h+FindFileData.cFileName+2]
0x18008f817  xor     eax, eax
0x18008f819  movzx   ecx, ax
0x18008f81c  sub     edx, ecx
0x18008f81e  test    edx, edx
0x18008f820  jz      loc_18008F8E3
0x18008f826  movzx   edx, [rsp+6F0h+FindFileData.cFileName]
0x18008f82b  sub     edx, r15d
0x18008f82e  jnz     short loc_18008F846
0x18008f830  movzx   edx, [rsp+6F0h+FindFileData.cFileName+2]
0x18008f835  sub     edx, r15d
0x18008f838  jnz     short loc_18008F846
0x18008f83a  movzx   edx, [rsp+6F0h+FindFileData.cFileName+4]
0x18008f83f  xor     eax, eax
0x18008f841  movzx   ecx, ax
0x18008f844  sub     edx, ecx
0x18008f846  test    edx, edx
0x18008f848  jz      loc_18008F8E3
0x18008f84e  lea     rax, [rsp+6F0h+FindFileData.cFileName]
0x18008f853  mov     [rsp+6F0h+var_6D0], rax
0x18008f858  mov     r9, rsi
0x18008f85b  lea     r8, aSS_3; "%s\\%s"
0x18008f862  mov     rdx, r13; unsigned __int64
0x18008f865  lea     rcx, [rbp+5F0h+FileName]; wchar_t *
0x18008f86c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008f871  mov     edi, eax
0x18008f873  test    eax, eax
0x18008f875  js      loc_18008F938
0x18008f87b  lea     rax, [rsp+6F0h+FindFileData.cFileName]
0x18008f880  mov     [rsp+6F0h+var_6D0], rax
0x18008f885  mov     r9, r14
0x18008f888  lea     r8, aSS_3; "%s\\%s"
0x18008f88f  mov     rdx, r13; unsigned __int64
0x18008f892  lea     rcx, [rbp+5F0h+NewFileName]; wchar_t *
0x18008f899  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008f89e  mov     edi, eax
0x18008f8a0  test    eax, eax
0x18008f8a2  js      loc_18008F930
0x18008f8a8  test    byte ptr [rsp+6F0h+FindFileData.dwFileAttributes], 10h
0x18008f8ad  jnz     short loc_18008F8E3
0x18008f8af  xor     r8d, r8d; bFailIfExists
0x18008f8b2  lea     rdx, [rbp+5F0h+NewFileName]; lpNewFileName
0x18008f8b9  lea     rcx, [rbp+5F0h+FileName]; lpExistingFileName
0x18008f8c0  call    cs:__imp_CopyFileW
0x18008f8c6  test    eax, eax
0x18008f8c8  jnz     short loc_18008F8E3
0x18008f8ca  call    cs:__imp_GetLastError
0x18008f8d0  mov     edi, eax
0x18008f8d2  test    eax, eax
0x18008f8d4  jle     short loc_18008F8DF
0x18008f8d6  movzx   edi, ax
0x18008f8d9  or      edi, 80070000h
0x18008f8df  test    edi, edi
0x18008f8e1  js      short loc_18008F928
0x18008f8e3  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x18008f8e8  mov     rcx, rbx; hFindFile
0x18008f8eb  call    cs:__imp_FindNextFileW
0x18008f8f1  test    eax, eax
0x18008f8f3  jnz     loc_18008F808
0x18008f8f9  xor     ebx, ebx
0x18008f8fb  lea     rcx, [rsp+6F0h+var_6C0]; this
0x18008f900  call    ??1CAutoCloseFindFile@@QEAA@XZ; CAutoCloseFindFile::~CAutoCloseFindFile(void)
0x18008f905  mov     eax, ebx
0x18008f907  mov     rcx, [rbp+5F0h+var_40]
0x18008f90e  xor     rcx, rsp; StackCookie
0x18008f911  call    __security_check_cookie
0x18008f916  add     rsp, 6C0h
0x18008f91d  pop     r15
0x18008f91f  pop     r14
0x18008f921  pop     r13
0x18008f923  pop     rdi
0x18008f924  pop     rsi
0x18008f925  pop     rbx
0x18008f926  pop     rbp
0x18008f927  retn
0x18008f928  mov     r8d, 0F28h
0x18008f92e  jmp     short loc_18008F93E
0x18008f930  mov     r8d, 0EECh
0x18008f936  jmp     short loc_18008F93E
0x18008f938  mov     r8d, 0ED8h; unsigned __int16
0x18008f93e  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008f945  mov     ecx, edi; int
0x18008f947  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008f94c  mov     ebx, edi
0x18008f94e  jmp     short loc_18008F8FB
```
