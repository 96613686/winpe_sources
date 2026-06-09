# QueryVolumeFreeSpace(wchar_t const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1400472e0`
- end: `0x14004749b`
- name: `?QueryVolumeFreeSpace@@YAJPEB_WPEA_K1@Z`
- size: `443`
- prototype: `__int64 __fastcall(const wchar_t *Src, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140037b60`

## callees

- `0x140002748`
- `0x14000e658`
- `0x140012994`
- `0x1400372dc`
- `0x1400472e0`
- `0x14005f588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047409`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140047409`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400473f9`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400473f9`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1400473a9`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1400473a9`

## string_xrefs

- `0x1400473bb`: `PathCchStripToRoot failed`

## pseudocode

```c
__int64 __fastcall QueryVolumeFreeSpace(const wchar_t *Src, unsigned __int64 *a2, unsigned __int64 *a3)
{
  unsigned int DWORD; // eax
  unsigned int v6; // ebx
  __int64 v7; // rbx
  void **unique_for; // rax
  const struct std::nothrow_t *v9; // rdx
  void *v10; // rsi
  const char *v11; // rax
  __int64 v12; // rdx
  const struct std::nothrow_t *v13; // rdx
  signed int LastError; // eax
  wil::details *v16; // [rsp+20h] [rbp-38h]
  wil::details *v17; // [rsp+20h] [rbp-38h]
  bool v18; // [rsp+28h] [rbp-30h]
  const char *v19; // [rsp+30h] [rbp-28h]
  wil::details::in1diag4 *retaddr; // [rsp+58h] [rbp+0h]
  _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+60h] [rbp+8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+70h] [rbp+18h] BYREF
  void *v23; // [rsp+78h] [rbp+20h] BYREF

  TotalNumberOfFreeBytes.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  if ( !Src || !a2 )
  {
    v6 = -2147024809;
    LODWORD(v16) = -2147024809;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
      "QueryVolumeFreeSpace",
      v16,
      (int)"Invalid params",
      v19);
    return v6;
  }
  *a2 = 0;
  DWORD = UtilRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
            L"FreeVolumeSpaceMB",
            0,
            0,
            v18);
  if ( !DWORD )
  {
    v7 = -1;
    do
      ++v7;
    while ( Src[v7] );
    unique_for = (void **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v23, v7 + 1);
    v10 = *unique_for;
    *unique_for = 0;
    if ( v23 )
      operator delete(v23, v9);
    if ( !v10 )
      return (unsigned int)-2147024882;
    memcpy_0(v10, Src, 2 * v7 + 2);
    v6 = PathCchStripToRoot((PWSTR)v10, v7 + 1);
    if ( v6 )
    {
      v11 = "PathCchStripToRoot failed";
      v12 = 233;
    }
    else
    {
      if ( GetDiskFreeSpaceExW((LPCWSTR)v10, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
      {
        v6 = 0;
        *a2 = TotalNumberOfFreeBytes.QuadPart >> 20;
        goto LABEL_21;
      }
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v12 = 240;
      if ( (v6 & 0x80000000) == 0 )
        v6 = -2147467259;
      v11 = "GetDiskFreeSpaceExW failed";
    }
    LODWORD(v17) = v6;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelhelper.cpp",
      "QueryVolumeFreeSpace",
      v17,
      (int)v11,
      v19);
LABEL_21:
    operator delete(v10, v13);
    return v6;
  }
  v6 = 0;
  *a2 = DWORD;
  return v6;
}

```

## disassembly

```asm
0x1400472e0  mov     rax, rsp
0x1400472e3  mov     [rax+10h], rbx
0x1400472e7  mov     [rax+18h], r8
0x1400472eb  push    rbp
0x1400472ec  push    rsi
0x1400472ed  push    rdi
0x1400472ee  push    r14
0x1400472f0  push    r15; char *
0x1400472f2  sub     rsp, 30h
0x1400472f6  xor     r15d, r15d
0x1400472f9  mov     rdi, rdx
0x1400472fc  mov     [rax+18h], r15
0x140047300  mov     rbp, rcx
0x140047303  mov     [rax+8], r15
0x140047307  test    rcx, rcx
0x14004730a  jz      loc_140047455
0x140047310  test    rdx, rdx
0x140047313  jz      loc_140047455
0x140047319  mov     [rdx], r15
0x14004731c  lea     r8, aFreevolumespac; "FreeVolumeSpaceMB"
0x140047323  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x14004732a  mov     [rax-38h], r15
0x14004732e  xor     r9d, r9d; unsigned int
0x140047331  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140047338  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x14004733d  test    eax, eax
0x14004733f  jz      short loc_14004734E
0x140047341  mov     eax, eax
0x140047343  mov     ebx, r15d
0x140047346  mov     [rdi], rax
0x140047349  jmp     loc_140047487
0x14004734e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140047352  inc     rbx
0x140047355  cmp     [rbp+rbx*2+0], r15w
0x14004735b  jnz     short loc_140047352
0x14004735d  lea     rdx, [rbx+1]
0x140047361  lea     rcx, [rsp+58h+arg_18]
0x140047366  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14004736b  mov     rsi, [rax]
0x14004736e  mov     [rax], r15
0x140047371  mov     rcx, [rsp+58h+arg_18]; void *
0x140047376  test    rcx, rcx
0x140047379  jz      short loc_140047380
0x14004737b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140047380  test    rsi, rsi
0x140047383  jnz     short loc_14004738F
0x140047385  mov     ebx, 8007000Eh
0x14004738a  jmp     loc_140047487
0x14004738f  lea     r8, ds:2[rbx*2]; Size
0x140047397  mov     rdx, rbp; Src
0x14004739a  mov     rcx, rsi; void *
0x14004739d  call    memcpy_0
0x1400473a2  lea     rdx, [rbx+1]; cchPath
0x1400473a6  mov     rcx, rsi; pszPath
0x1400473a9  call    cs:__imp_PathCchStripToRoot
0x1400473b0  nop     dword ptr [rax+rax+00h]
0x1400473b5  mov     ebx, eax
0x1400473b7  test    eax, eax
0x1400473b9  jz      short loc_1400473EA
0x1400473bb  lea     rax, aPathcchstripto; "PathCchStripToRoot failed"
0x1400473c2  mov     edx, 0E9h; void *
0x1400473c7  mov     rcx, [rsp+58h]; this
0x1400473cc  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x1400473d3  mov     qword ptr [rsp+58h+var_30], rax; int
0x1400473d8  lea     r9, aQueryvolumefre; "QueryVolumeFreeSpace"
0x1400473df  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x1400473e3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400473e8  jmp     short loc_14004744B
0x1400473ea  lea     r9, [rsp+58h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1400473ef  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1400473f1  lea     r8, [rsp+58h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1400473f6  mov     rcx, rsi; lpDirectoryName
0x1400473f9  call    cs:__imp_GetDiskFreeSpaceExW
0x140047400  nop     dword ptr [rax+rax+00h]
0x140047405  test    eax, eax
0x140047407  jnz     short loc_14004743C
0x140047409  call    cs:__imp_GetLastError
0x140047410  nop     dword ptr [rax+rax+00h]
0x140047415  mov     ebx, eax
0x140047417  test    eax, eax
0x140047419  jle     short loc_140047424
0x14004741b  movzx   ebx, ax
0x14004741e  or      ebx, 80070000h
0x140047424  mov     eax, 80004005h
0x140047429  test    ebx, ebx
0x14004742b  mov     edx, 0F0h
0x140047430  cmovns  ebx, eax
0x140047433  lea     rax, aGetdiskfreespa; "GetDiskFreeSpaceExW failed"
0x14004743a  jmp     short loc_1400473C7
0x14004743c  mov     rax, qword ptr [rsp+58h+TotalNumberOfFreeBytes]
0x140047441  mov     ebx, r15d
0x140047444  shr     rax, 14h
0x140047448  mov     [rdi], rax
0x14004744b  mov     rcx, rsi; void *
0x14004744e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140047453  jmp     short loc_140047487
0x140047455  mov     rcx, [rsp+58h]; this
0x14004745a  lea     rax, aInvalidParams; "Invalid params"
0x140047461  mov     qword ptr [rsp+58h+var_30], rax; int
0x140047466  lea     r9, aQueryvolumefre; "QueryVolumeFreeSpace"
0x14004746d  mov     ebx, 80070057h
0x140047472  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x140047479  mov     edx, 0BFh; void *
0x14004747e  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x140047482  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140047487  mov     eax, ebx
0x140047489  mov     rbx, [rsp+58h+arg_8]
0x14004748e  add     rsp, 30h
0x140047492  pop     r15
0x140047494  pop     r14
0x140047496  pop     rdi
0x140047497  pop     rsi
0x140047498  pop     rbp
0x140047499  retn
```
