# CLogger::Open(void)

- ea: `0x18003886c`
- end: `0x1800389cb`
- name: `?Open@CLogger@@QEAAHXZ`
- size: `351`
- prototype: `_BOOL8 __fastcall(LPCWSTR *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180038518`
- `0x180038c10`

## callees

- `0x18000e658`
- `0x18000ee70`
- `0x18000f1c4`
- `0x180011884`
- `0x1800122d8`
- `0x180038018`
- `0x180038164`
- `0x18003886c`
- `0x1800389d4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038990`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038990`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800389a5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800389a5`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800388ed`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x1800388ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CLogger::Open(LPCWSTR *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rax
  int LogLevel; // ebx
  LPCWSTR *v6; // r14
  LPCWSTR v7; // rdx
  int *v8; // rdi
  __int64 v9; // rbx
  WCHAR *FileW; // rax
  int v11; // [rsp+70h] [rbp+8h] BYREF
  char v12; // [rsp+78h] [rbp+10h] BYREF
  char v13; // [rsp+80h] [rbp+18h] BYREF
  _QWORD *v14; // [rsp+88h] [rbp+20h]

  v2 = (_QWORD *)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
                   &v12,
                   this + 1);
  v14 = v2;
  v11 = 0;
  v3 = ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
         &v13,
         v2);
  LogLevel = CLogger::GetLogLevel(v3, &v11);
  ATL::CStringData::Release((ATL::CStringData *)(*v2 - 24LL));
  if ( LogLevel )
  {
    CLogger::m_fLoggingEnabled = 0;
    return 0;
  }
  else
  {
    CLogger::PurgeOld((CLogger *)this);
    SHCreateDirectoryExW(0, this[3], 0);
    v6 = this + 4;
    v7 = this[3];
    v8 = (int *)(this[4] - 12);
    if ( v7 - 12 != (LPCWSTR)v8 )
    {
      if ( v8[4] >= 0 && *((_QWORD *)v7 - 3) == *(_QWORD *)v8 )
      {
        v9 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v8);
        *v6 = (LPCWSTR)(v9 + 24);
      }
      else
      {
        ATL::CSimpleStringT<wchar_t,0>::SetString(this + 4, v7, *((unsigned int *)v7 - 4));
      }
    }
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(this + 4, "\\");
    ATL::CSimpleStringT<wchar_t,0>::Append(this + 4, this[1], *((unsigned int *)this[1] - 4));
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(this + 4, ".txt");
    FileW = (WCHAR *)CreateFileW(*v6, 4u, 3u, 0, 4u, 0x80u, 0);
    this[6] = FileW;
    if ( FileW != (WCHAR *)-1LL )
    {
      *((_DWORD *)this + 15) = GetFileSize(FileW, 0);
      *((_DWORD *)this + 16) = 0;
    }
    return (LPCWSTR)((char *)this[6] + 1) != 0;
  }
}

```

## disassembly

```asm
0x18003886c  push    rbx
0x18003886e  push    rsi
0x18003886f  push    rdi
0x180038870  push    r14
0x180038872  push    r15
0x180038874  sub     rsp, 40h
0x180038878  mov     rsi, rcx
0x18003887b  lea     rdx, [rcx+8]
0x18003887f  lea     rcx, [rsp+68h+arg_8]
0x180038884  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x180038889  mov     rdi, rax
0x18003888c  mov     [rsp+68h+arg_18], rax
0x180038894  mov     [rsp+68h+arg_0], 0
0x18003889c  mov     rdx, rax
0x18003889f  lea     rcx, [rsp+68h+arg_10]
0x1800388a7  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800388ac  lea     rdx, [rsp+68h+arg_0]
0x1800388b1  mov     rcx, rax
0x1800388b4  call    ?GetLogLevel@CLogger@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@PEAW4LogLevel@@@Z; CLogger::GetLogLevel(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,LogLevel *)
0x1800388b9  mov     ebx, eax
0x1800388bb  mov     rcx, [rdi]
0x1800388be  sub     rcx, 18h; this
0x1800388c2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800388c7  test    ebx, ebx
0x1800388c9  jz      short loc_1800388DC
0x1800388cb  mov     cs:?m_fLoggingEnabled@CLogger@@0HA, 0; int CLogger::m_fLoggingEnabled
0x1800388d5  xor     eax, eax
0x1800388d7  jmp     loc_1800389BF
0x1800388dc  mov     rcx, rsi; this
0x1800388df  call    ?PurgeOld@CLogger@@QEAAXXZ; CLogger::PurgeOld(void)
0x1800388e4  xor     r8d, r8d; psa
0x1800388e7  mov     rdx, [rsi+18h]; pszPath
0x1800388eb  xor     ecx, ecx; hwnd
0x1800388ed  call    cs:__imp_SHCreateDirectoryExW
0x1800388f3  lea     r14, [rsi+20h]
0x1800388f7  mov     rdx, [rsi+18h]
0x1800388fb  lea     rcx, [rdx-18h]
0x1800388ff  mov     rdi, [r14]
0x180038902  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180038906  cmp     rcx, rdi
0x180038909  jz      short loc_18003893E
0x18003890b  cmp     dword ptr [rdi+10h], 0
0x18003890f  jl      short loc_180038932
0x180038911  mov     rax, [rdi]
0x180038914  cmp     [rcx], rax
0x180038917  jnz     short loc_180038932
0x180038919  call    ?CloneData@?$CSimpleStringT@_W$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<wchar_t,0>::CloneData(ATL::CStringData *)
0x18003891e  mov     rbx, rax
0x180038921  mov     rcx, rdi; this
0x180038924  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180038929  lea     rax, [rbx+18h]
0x18003892d  mov     [r14], rax
0x180038930  jmp     short loc_18003893E
0x180038932  mov     r8d, [rdx-10h]
0x180038936  mov     rcx, r14
0x180038939  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18003893e  lea     rdx, asc_18004C1CC; "\\"
0x180038945  mov     rcx, r14
0x180038948  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x18003894d  mov     rdx, [rsi+8]
0x180038951  mov     r8d, [rdx-10h]
0x180038955  mov     rcx, r14
0x180038958  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x18003895d  lea     rdx, aTxt_1; ".txt"
0x180038964  mov     rcx, r14
0x180038967  call    ??Y?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::operator+=(char const *)
0x18003896c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180038975  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003897d  mov     edx, 4; dwDesiredAccess
0x180038982  mov     [rsp+68h+dwCreationDisposition], edx; dwCreationDisposition
0x180038986  xor     r9d, r9d; lpSecurityAttributes
0x180038989  lea     r8d, [rdx-1]; dwShareMode
0x18003898d  mov     rcx, [r14]; lpFileName
0x180038990  call    cs:__imp_CreateFileW
0x180038996  mov     [rsi+30h], rax
0x18003899a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003899e  jz      short loc_1800389B5
0x1800389a0  xor     edx, edx; lpFileSizeHigh
0x1800389a2  mov     rcx, rax; hFile
0x1800389a5  call    cs:__imp_GetFileSize
0x1800389ab  mov     [rsi+3Ch], eax
0x1800389ae  mov     dword ptr [rsi+40h], 0
0x1800389b5  xor     eax, eax
0x1800389b7  cmp     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x1800389bc  setnz   al
0x1800389bf  add     rsp, 40h
0x1800389c3  pop     r15
0x1800389c5  pop     r14
0x1800389c7  pop     rdi
0x1800389c8  pop     rsi
0x1800389c9  pop     rbx
0x1800389ca  retn
```
