# QueryVolumeFreeSpace(wchar_t const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1400442d4`
- end: `0x14004447c`
- name: `?QueryVolumeFreeSpace@@YAJPEB_WPEA_K1@Z`
- size: `424`
- prototype: `__int64 __fastcall(const wchar_t *Src, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140035654`

## callees

- `0x140002728`
- `0x14000e3c4`
- `0x14001211c`
- `0x140034d9c`
- `0x1400442d4`
- `0x14005b7e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443f1`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400443e7`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400443e7`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x14004439d`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x14004439d`

## string_xrefs

- `0x1400443a9`: `PathCchStripToRoot failed`

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
0x1400442d4  mov     rax, rsp
0x1400442d7  mov     [rax+10h], rbx
0x1400442db  mov     [rax+18h], r8
0x1400442df  push    rbp
0x1400442e0  push    rsi
0x1400442e1  push    rdi
0x1400442e2  push    r14
0x1400442e4  push    r15; char *
0x1400442e6  sub     rsp, 30h
0x1400442ea  xor     r15d, r15d
0x1400442ed  mov     rdi, rdx
0x1400442f0  mov     [rax+18h], r15
0x1400442f4  mov     rbp, rcx
0x1400442f7  mov     [rax+8], r15
0x1400442fb  test    rcx, rcx
0x1400442fe  jz      loc_140044437
0x140044304  test    rdx, rdx
0x140044307  jz      loc_140044437
0x14004430d  mov     [rdx], r15
0x140044310  lea     r8, aFreevolumespac; "FreeVolumeSpaceMB"
0x140044317  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x14004431e  mov     [rax-38h], r15
0x140044322  xor     r9d, r9d; unsigned int
0x140044325  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004432c  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140044331  test    eax, eax
0x140044333  jz      short loc_140044342
0x140044335  mov     eax, eax
0x140044337  mov     ebx, r15d
0x14004433a  mov     [rdi], rax
0x14004433d  jmp     loc_140044469
0x140044342  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140044346  inc     rbx
0x140044349  cmp     [rbp+rbx*2+0], r15w
0x14004434f  jnz     short loc_140044346
0x140044351  lea     rdx, [rbx+1]
0x140044355  lea     rcx, [rsp+58h+arg_18]
0x14004435a  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14004435f  mov     rsi, [rax]
0x140044362  mov     [rax], r15
0x140044365  mov     rcx, [rsp+58h+arg_18]; void *
0x14004436a  test    rcx, rcx
0x14004436d  jz      short loc_140044374
0x14004436f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140044374  test    rsi, rsi
0x140044377  jnz     short loc_140044383
0x140044379  mov     ebx, 8007000Eh
0x14004437e  jmp     loc_140044469
0x140044383  lea     r8, ds:2[rbx*2]; Size
0x14004438b  mov     rdx, rbp; Src
0x14004438e  mov     rcx, rsi; void *
0x140044391  call    memcpy_0
0x140044396  lea     rdx, [rbx+1]; cchPath
0x14004439a  mov     rcx, rsi; pszPath
0x14004439d  call    cs:__imp_PathCchStripToRoot
0x1400443a3  mov     ebx, eax
0x1400443a5  test    eax, eax
0x1400443a7  jz      short loc_1400443D8
0x1400443a9  lea     rax, aPathcchstripto; "PathCchStripToRoot failed"
0x1400443b0  mov     edx, 0E9h; void *
0x1400443b5  mov     rcx, [rsp+58h]; this
0x1400443ba  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x1400443c1  mov     qword ptr [rsp+58h+var_30], rax; int
0x1400443c6  lea     r9, aQueryvolumefre; "QueryVolumeFreeSpace"
0x1400443cd  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x1400443d1  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400443d6  jmp     short loc_14004442D
0x1400443d8  lea     r9, [rsp+58h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1400443dd  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1400443df  lea     r8, [rsp+58h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1400443e4  mov     rcx, rsi; lpDirectoryName
0x1400443e7  call    cs:__imp_GetDiskFreeSpaceExW
0x1400443ed  test    eax, eax
0x1400443ef  jnz     short loc_14004441E
0x1400443f1  call    cs:__imp_GetLastError
0x1400443f7  mov     ebx, eax
0x1400443f9  test    eax, eax
0x1400443fb  jle     short loc_140044406
0x1400443fd  movzx   ebx, ax
0x140044400  or      ebx, 80070000h
0x140044406  mov     eax, 80004005h
0x14004440b  test    ebx, ebx
0x14004440d  mov     edx, 0F0h
0x140044412  cmovns  ebx, eax
0x140044415  lea     rax, aGetdiskfreespa; "GetDiskFreeSpaceExW failed"
0x14004441c  jmp     short loc_1400443B5
0x14004441e  mov     rax, qword ptr [rsp+58h+TotalNumberOfFreeBytes]
0x140044423  mov     ebx, r15d
0x140044426  shr     rax, 14h
0x14004442a  mov     [rdi], rax
0x14004442d  mov     rcx, rsi; void *
0x140044430  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140044435  jmp     short loc_140044469
0x140044437  mov     rcx, [rsp+58h]; this
0x14004443c  lea     rax, aInvalidParams; "Invalid params"
0x140044443  mov     qword ptr [rsp+58h+var_30], rax; int
0x140044448  lea     r9, aQueryvolumefre; "QueryVolumeFreeSpace"
0x14004444f  mov     ebx, 80070057h
0x140044454  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\werfa"...
0x14004445b  mov     edx, 0BFh; void *
0x140044460  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x140044464  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044469  mov     eax, ebx
0x14004446b  mov     rbx, [rsp+58h+arg_8]
0x140044470  add     rsp, 30h
0x140044474  pop     r15
0x140044476  pop     r14
0x140044478  pop     rdi
0x140044479  pop     rsi
0x14004447a  pop     rbp
0x14004447b  retn
```
