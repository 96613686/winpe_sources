# SxRotateLogs(ushort const *,ulong)

- ea: `0x14000f7a0`
- end: `0x14000fa16`
- name: `?SxRotateLogs@@YAJPEBGK@Z`
- size: `630`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400039e4`

## callees

- `0x140002e1c`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ef3c`
- `0x14000f510`
- `0x14000f7a0`
- `0x14000fe8c`
- `0x140010168`
- `0x140010744`

## import_xrefs

- `KERNEL32!MoveFileExW` at `0x14000f943`
- `KERNEL32!MoveFileExW` at `0x14000f943`
- `KERNEL32!DeleteFileW` at `0x14000f8ef`
- `KERNEL32!DeleteFileW` at `0x14000f8ef`
- `KERNEL32!GetFileAttributesW` at `0x14000f881`
- `KERNEL32!GetFileAttributesW` at `0x14000f881`
- `KERNEL32!GetLastError` at `0x14000f88c`
- `KERNEL32!GetLastError` at `0x14000f94d`
- `KERNEL32!GetLastError` at `0x14000f88c`
- `KERNEL32!GetLastError` at `0x14000f94d`

## pseudocode

```c
__int64 __fastcall SxRotateLogs(const unsigned __int16 *a1)
{
  unsigned int v2; // edx
  signed int v3; // ebx
  __int16 v4; // ax
  int v5; // r14d
  const WCHAR *v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx
  LPCWSTR lpFileName; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h]
  LPCWSTR lpExistingFileName[2]; // [rsp+40h] [rbp-29h] BYREF
  int v13; // [rsp+50h] [rbp-19h] BYREF
  __int16 v14; // [rsp+54h] [rbp-15h]
  __int16 v15; // [rsp+56h] [rbp-13h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SxRotateLogs", 0x1BAu, 1u);
  lpExistingFileName[1] = 0;
  lpExistingFileName[0] = (LPCWSTR)qword_140013960;
  lpFileName = (LPCWSTR)qword_140013960;
  v11 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 450;
LABEL_26:
    v13 = v3;
    goto LABEL_27;
  }
  v13 = 0;
  v14 = 451;
  SxMergeExtraLogs(a1, v2);
  v3 = CBsString::Format((CBsString *)&lpFileName, L"%s.%d.%s", a1, 0, L"etl");
  v13 = v3;
  v4 = 458;
  if ( v3 < 0 )
  {
LABEL_27:
    v15 = v4;
    goto LABEL_28;
  }
  v14 = 458;
  if ( GetFileAttributesW(lpFileName) != -1 || GetLastError() - 2 > 1 )
  {
    v5 = 2;
    v3 = CBsString::Format((CBsString *)&lpFileName, L"%s.%d.%s", a1, 2, L"etl");
    v13 = v3;
    v4 = 471;
    if ( v3 >= 0 )
    {
      v6 = lpFileName;
      v14 = 471;
      DeleteFileW(lpFileName);
      while ( 1 )
      {
        v3 = CBsString::Format((CBsString *)lpExistingFileName, L"%s.%d.%s", a1, (unsigned int)--v5, L"etl");
        v13 = v3;
        v4 = 478;
        if ( v3 < 0 )
          break;
        v14 = 478;
        if ( !MoveFileExW(lpExistingFileName[0], v6, 1u) )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0x20 || (v8 = 0x100000024LL, !_bittest64(&v8, LastError)) )
          {
            if ( (int)LastError > 0 )
              v3 = (unsigned __int16)LastError | 0x80070000;
            v4 = 491;
            goto LABEL_26;
          }
          v13 = 0;
          v14 = 491;
        }
        SxCompressLogFile(v6);
        if ( (_DWORD)v11 )
        {
          LODWORD(v11) = 0;
          *v6 = 0;
        }
        v13 = CBsString::Append((CBsString *)&lpFileName, lpExistingFileName[0]);
        v3 = v13;
        if ( v13 < 0 )
        {
          v15 = 498;
          goto LABEL_28;
        }
        v14 = 498;
        if ( !v5 )
          goto LABEL_28;
        v6 = lpFileName;
      }
    }
    goto LABEL_27;
  }
  v13 = 0;
  v14 = 466;
  v3 = 0;
LABEL_28:
  CBsString::_Release((CBsString *)&lpFileName);
  CBsString::_Release((CBsString *)lpExistingFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000f7a0  push    rbp
0x14000f7a2  push    rbx
0x14000f7a3  push    rsi
0x14000f7a4  push    rdi
0x14000f7a5  push    r13
0x14000f7a7  push    r14
0x14000f7a9  lea     rbp, [rsp-2Fh]
0x14000f7ae  sub     rsp, 98h
0x14000f7b5  mov     rsi, rcx
0x14000f7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7bf  lea     rax, WPP_GLOBAL_Control
0x14000f7c6  cmp     rcx, rax
0x14000f7c9  jz      short loc_14000F7E9
0x14000f7cb  test    dword ptr [rcx+1Ch], 20000000h
0x14000f7d2  jz      short loc_14000F7E9
0x14000f7d4  mov     rcx, [rcx+10h]
0x14000f7d8  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000f7df  mov     edx, 14h
0x14000f7e4  call    WPP_SF_
0x14000f7e9  mov     r9d, 1; unsigned __int16
0x14000f7ef  lea     rdx, aSxrotatelogs; "SxRotateLogs"
0x14000f7f6  mov     r8d, 1BAh; unsigned __int16
0x14000f7fc  lea     rcx, [rbp+57h+var_70]; this
0x14000f800  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000f805  mov     [rbp+57h+var_78], 0
0x14000f80d  lea     rax, qword_140013960
0x14000f814  mov     [rbp+57h+lpExistingFileName], rax
0x14000f818  mov     [rbp+57h+lpFileName], rax
0x14000f81c  mov     [rbp+57h+var_88], 0
0x14000f824  test    rsi, rsi
0x14000f827  jz      loc_14000F9D8
0x14000f82d  mov     eax, 1C3h
0x14000f832  mov     [rbp+57h+var_70], 0
0x14000f839  mov     rcx, rsi; unsigned __int16 *
0x14000f83c  mov     [rbp+57h+var_6C], ax
0x14000f840  call    ?SxMergeExtraLogs@@YAJPEBGK@Z; SxMergeExtraLogs(ushort const *,ulong)
0x14000f845  lea     rdi, aEtl; "etl"
0x14000f84c  xor     r9d, r9d
0x14000f84f  mov     r8, rsi
0x14000f852  mov     [rsp+0C0h+var_A0], rdi
0x14000f857  lea     rdx, aSDS; "%s.%d.%s"
0x14000f85e  lea     rcx, [rbp+57h+lpFileName]; this
0x14000f862  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000f867  mov     ebx, eax
0x14000f869  mov     [rbp+57h+var_70], eax
0x14000f86c  test    eax, eax
0x14000f86e  mov     eax, 1CAh
0x14000f873  js      loc_14000F9E5
0x14000f879  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14000f87d  mov     [rbp+57h+var_6C], ax
0x14000f881  call    cs:__imp_GetFileAttributesW
0x14000f887  cmp     eax, 0FFFFFFFFh
0x14000f88a  jnz     short loc_14000F8B1
0x14000f88c  call    cs:__imp_GetLastError
0x14000f892  add     eax, 0FFFFFFFEh
0x14000f895  cmp     eax, 1
0x14000f898  ja      short loc_14000F8B1
0x14000f89a  mov     eax, 1D2h
0x14000f89f  mov     [rbp+57h+var_70], 0
0x14000f8a6  mov     [rbp+57h+var_6C], ax
0x14000f8aa  xor     ebx, ebx
0x14000f8ac  jmp     loc_14000F9E9
0x14000f8b1  mov     r14d, 2
0x14000f8b7  mov     [rsp+0C0h+var_A0], rdi
0x14000f8bc  mov     r9d, r14d
0x14000f8bf  lea     rdx, aSDS; "%s.%d.%s"
0x14000f8c6  mov     r8, rsi
0x14000f8c9  lea     rcx, [rbp+57h+lpFileName]; this
0x14000f8cd  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000f8d2  mov     ebx, eax
0x14000f8d4  mov     [rbp+57h+var_70], eax
0x14000f8d7  test    eax, eax
0x14000f8d9  mov     eax, 1D7h
0x14000f8de  js      loc_14000F9E5
0x14000f8e4  mov     rdi, [rbp+57h+lpFileName]
0x14000f8e8  mov     rcx, rdi; lpFileName
0x14000f8eb  mov     [rbp+57h+var_6C], ax
0x14000f8ef  call    cs:__imp_DeleteFileW
0x14000f8f5  mov     r13d, 1F2h
0x14000f8fb  lea     rax, aEtl; "etl"
0x14000f902  dec     r14d
0x14000f905  mov     r9d, r14d
0x14000f908  mov     [rsp+0C0h+var_A0], rax
0x14000f90d  mov     r8, rsi
0x14000f910  lea     rdx, aSDS; "%s.%d.%s"
0x14000f917  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x14000f91b  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x14000f920  mov     ebx, eax
0x14000f922  mov     [rbp+57h+var_70], eax
0x14000f925  test    eax, eax
0x14000f927  mov     eax, 1DEh
0x14000f92c  js      loc_14000F9E5
0x14000f932  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x14000f936  mov     r8d, 1; dwFlags
0x14000f93c  mov     rdx, rdi; lpNewFileName
0x14000f93f  mov     [rbp+57h+var_6C], ax
0x14000f943  call    cs:__imp_MoveFileExW
0x14000f949  test    eax, eax
0x14000f94b  jnz     short loc_14000F97A
0x14000f94d  call    cs:__imp_GetLastError
0x14000f953  mov     ebx, eax
0x14000f955  cmp     eax, 20h ; ' '
0x14000f958  ja      short loc_14000F9BD
0x14000f95a  mov     rcx, 100000024h
0x14000f964  bt      rcx, rbx
0x14000f968  jnb     short loc_14000F9BD
0x14000f96a  mov     eax, 1EBh
0x14000f96f  mov     [rbp+57h+var_70], 0
0x14000f976  mov     [rbp+57h+var_6C], ax
0x14000f97a  mov     rcx, rdi; lpFileName
0x14000f97d  call    ?SxCompressLogFile@@YAJPEBG@Z; SxCompressLogFile(ushort const *)
0x14000f982  cmp     dword ptr [rbp+57h+var_88], 0
0x14000f986  jz      short loc_14000F994
0x14000f988  xor     eax, eax
0x14000f98a  mov     dword ptr [rbp+57h+var_88], 0
0x14000f991  mov     [rdi], ax
0x14000f994  mov     rdx, [rbp+57h+lpExistingFileName]; unsigned __int16 *
0x14000f998  lea     rcx, [rbp+57h+lpFileName]; this
0x14000f99c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x14000f9a1  mov     [rbp+57h+var_70], eax
0x14000f9a4  mov     ebx, eax
0x14000f9a6  test    eax, eax
0x14000f9a8  js      short loc_14000F9D1
0x14000f9aa  mov     [rbp+57h+var_6C], r13w
0x14000f9af  test    r14d, r14d
0x14000f9b2  jz      short loc_14000F9E9
0x14000f9b4  mov     rdi, [rbp+57h+lpFileName]
0x14000f9b8  jmp     loc_14000F8FB
0x14000f9bd  test    ebx, ebx
0x14000f9bf  jle     short loc_14000F9CA
0x14000f9c1  movzx   ebx, bx
0x14000f9c4  or      ebx, 80070000h
0x14000f9ca  mov     eax, 1EBh
0x14000f9cf  jmp     short loc_14000F9E2
0x14000f9d1  mov     [rbp+57h+var_6A], r13w
0x14000f9d6  jmp     short loc_14000F9E9
0x14000f9d8  mov     ebx, 80070057h
0x14000f9dd  mov     eax, 1C2h
0x14000f9e2  mov     [rbp+57h+var_70], ebx
0x14000f9e5  mov     [rbp+57h+var_6A], ax
0x14000f9e9  lea     rcx, [rbp+57h+lpFileName]; this
0x14000f9ed  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000f9f2  lea     rcx, [rbp+57h+lpExistingFileName]; this
0x14000f9f6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x14000f9fb  lea     rcx, [rbp+57h+var_70]; this
0x14000f9ff  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000fa04  mov     eax, ebx
0x14000fa06  add     rsp, 98h
0x14000fa0d  pop     r14
0x14000fa0f  pop     r13
0x14000fa11  pop     rdi
0x14000fa12  pop     rsi
0x14000fa13  pop     rbx
0x14000fa14  pop     rbp
0x14000fa15  retn
```
