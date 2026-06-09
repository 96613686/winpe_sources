# StartMSRAProcess(int,int,int)

- ea: `0x14000eb50`
- end: `0x14000ed4e`
- name: `?StartMSRAProcess@@YAJHHH@Z`
- size: `510`
- prototype: `__int64 __fastcall(int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e7b0`

## callees

- `0x14000aab8`
- `0x14000eb50`
- `0x140015240`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000eb78`
- `KERNEL32!HeapAlloc` at `0x14000ebc5`
- `KERNEL32!HeapAlloc` at `0x14000eb78`
- `KERNEL32!HeapAlloc` at `0x14000ebc5`
- `KERNEL32!GetProcessHeap` at `0x14000eb62`
- `KERNEL32!GetProcessHeap` at `0x14000ebb4`
- `KERNEL32!GetProcessHeap` at `0x14000ed14`
- `KERNEL32!GetProcessHeap` at `0x14000ed2d`
- `KERNEL32!GetProcessHeap` at `0x14000eb62`
- `KERNEL32!GetProcessHeap` at `0x14000ebb4`
- `KERNEL32!GetProcessHeap` at `0x14000ed14`
- `KERNEL32!GetProcessHeap` at `0x14000ed2d`
- `KERNEL32!HeapFree` at `0x14000ed22`
- `KERNEL32!HeapFree` at `0x14000ed3b`
- `KERNEL32!HeapFree` at `0x14000ed22`
- `KERNEL32!HeapFree` at `0x14000ed3b`
- `SHELL32!ShellExecuteW` at `0x14000ecdd`
- `SHELL32!ShellExecuteW` at `0x14000ecdd`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14000ebf8`
- `SHELL32!SHGetSpecialFolderPathW` at `0x14000ebf8`

## string_xrefs

- `0x14000eb9e`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ec06`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ed03`: `base\diagnosis\ra\dcom\src\remoteassistance.cpp`
- `0x14000ec4c`: `-CreateRAConnectionString `

## pseudocode

```c
__int64 __fastcall StartMSRAProcess(int a1, int a2, int a3)
{
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  unsigned __int16 *v9; // rdi
  unsigned int v10; // ebx
  HANDLE v11; // rax
  WCHAR *v12; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  WCHAR *lpDirectory; // rsi
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  CEventLogger *v17; // rcx
  signed int v18; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  signed int v21; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  signed int v24; // eax
  const struct _EVENT_DESCRIPTOR *v25; // rdx
  CEventLogger *v26; // rcx
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  HANDLE v29; // rax
  HANDLE v30; // rax

  ProcessHeap = GetProcessHeap();
  v9 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  if ( !v9 )
  {
    v10 = -2147024882;
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x18u,
      L"StartMSRAProcess",
      0x8007000E);
    return v10;
  }
  v11 = GetProcessHeap();
  v12 = (WCHAR *)HeapAlloc(v11, 8u, 0x208u);
  lpDirectory = v12;
  if ( !v12 )
  {
    v10 = -2147024882;
    CEventLogger::LogError(
      v14,
      v13,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x19u,
      L"StartMSRAProcess",
      0x8007000E);
    goto LABEL_20;
  }
  if ( !SHGetSpecialFolderPathW(0, v12, 37, 1) )
  {
    CEventLogger::LogError(
      v17,
      v16,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x1Eu,
      L"StartMSRAProcess",
      0);
    v10 = -2147467259;
    goto LABEL_20;
  }
  if ( !a2 )
  {
    if ( !a1 )
    {
      v10 = -2147418113;
      CEventLogger::LogError(
        v17,
        v16,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x31u,
        L"StartMSRAProcess",
        0x8000FFFF);
      goto LABEL_20;
    }
    v18 = StringCchCopyW(v9, 0x104u, L"-CreateRAConnectionString ");
    v10 = v18;
    if ( v18 < 0 )
    {
      CEventLogger::LogError(
        v20,
        v19,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x37u,
        L"StartMSRAProcess",
        v18);
      goto LABEL_20;
    }
LABEL_18:
    if ( (__int64)ShellExecuteW(0, 0, L"msra.exe", v9, lpDirectory, 1) <= 32 )
    {
      v10 = -2147467259;
      CEventLogger::LogError(
        v28,
        v27,
        L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
        0x70u,
        L"StartMSRAProcess",
        0x80004005);
    }
    goto LABEL_20;
  }
  v10 = 0;
  if ( a3 )
    goto LABEL_18;
  if ( a1 )
  {
    v21 = StringCchCopyW(v9, 0x104u, L"-OfferIM ");
    v10 = v21;
    if ( v21 >= 0 )
      goto LABEL_18;
    CEventLogger::LogError(
      v23,
      v22,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x50u,
      L"StartMSRAProcess",
      v21);
  }
  else
  {
    v24 = StringCchCopyW(v9, 0x104u, L"-SolicitedIM ");
    v10 = v24;
    if ( v24 >= 0 )
      goto LABEL_18;
    CEventLogger::LogError(
      v26,
      v25,
      L"base\\diagnosis\\ra\\dcom\\src\\remoteassistance.cpp",
      0x57u,
      L"StartMSRAProcess",
      v24);
  }
LABEL_20:
  v29 = GetProcessHeap();
  HeapFree(v29, 0, v9);
  if ( lpDirectory )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, lpDirectory);
  }
  return v10;
}

```

## disassembly

```asm
0x14000eb50  push    rbx
0x14000eb52  push    rbp
0x14000eb53  push    rsi
0x14000eb54  push    rdi
0x14000eb55  push    r14
0x14000eb57  sub     rsp, 30h
0x14000eb5b  mov     r14d, r8d
0x14000eb5e  mov     ebx, edx
0x14000eb60  mov     ebp, ecx
0x14000eb62  call    cs:__imp_GetProcessHeap
0x14000eb68  mov     esi, 208h
0x14000eb6d  mov     edx, 8; dwFlags
0x14000eb72  mov     rcx, rax; hHeap
0x14000eb75  mov     r8d, esi; dwBytes
0x14000eb78  call    cs:__imp_HeapAlloc
0x14000eb7e  mov     rdi, rax
0x14000eb81  test    rax, rax
0x14000eb84  jnz     short loc_14000EBB4
0x14000eb86  lea     rax, aStartmsraproce; "StartMSRAProcess"
0x14000eb8d  mov     [rsp+58h+nShowCmd], 8007000Eh; unsigned int
0x14000eb95  lea     r9d, [rdi+18h]; unsigned int
0x14000eb99  mov     [rsp+58h+lpDirectory], rax; unsigned __int16 *
0x14000eb9e  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000eba5  mov     ebx, 8007000Eh
0x14000ebaa  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ebaf  jmp     loc_14000ED41
0x14000ebb4  call    cs:__imp_GetProcessHeap
0x14000ebba  mov     r8, rsi; dwBytes
0x14000ebbd  mov     edx, 8; dwFlags
0x14000ebc2  mov     rcx, rax; hHeap
0x14000ebc5  call    cs:__imp_HeapAlloc
0x14000ebcb  mov     rsi, rax
0x14000ebce  test    rax, rax
0x14000ebd1  jnz     short loc_14000EBE9
0x14000ebd3  mov     ebx, 8007000Eh
0x14000ebd8  mov     [rsp+58h+nShowCmd], 8007000Eh
0x14000ebe0  lea     r9d, [rax+19h]
0x14000ebe4  jmp     loc_14000ECFC
0x14000ebe9  mov     r9d, 1; fCreate
0x14000ebef  mov     rdx, rsi; pszPath
0x14000ebf2  xor     ecx, ecx; hwnd
0x14000ebf4  lea     r8d, [r9+24h]; csidl
0x14000ebf8  call    cs:__imp_SHGetSpecialFolderPathW
0x14000ebfe  test    eax, eax
0x14000ec00  jnz     short loc_14000EC2E
0x14000ec02  mov     [rsp+58h+nShowCmd], eax; unsigned int
0x14000ec06  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ec0d  lea     rax, aStartmsraproce; "StartMSRAProcess"
0x14000ec14  mov     r9d, 1Eh; unsigned int
0x14000ec1a  mov     [rsp+58h+lpDirectory], rax; unsigned __int16 *
0x14000ec1f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ec24  mov     ebx, 80004005h
0x14000ec29  jmp     loc_14000ED14
0x14000ec2e  test    ebx, ebx
0x14000ec30  jnz     short loc_14000EC75
0x14000ec32  test    ebp, ebp
0x14000ec34  jnz     short loc_14000EC4C
0x14000ec36  mov     ebx, 8000FFFFh
0x14000ec3b  mov     [rsp+58h+nShowCmd], 8000FFFFh
0x14000ec43  lea     r9d, [rbp+31h]
0x14000ec47  jmp     loc_14000ECFC
0x14000ec4c  lea     r8, aCreateraconnec; "-CreateRAConnectionString "
0x14000ec53  mov     edx, 104h; unsigned __int64
0x14000ec58  mov     rcx, rdi; unsigned __int16 *
0x14000ec5b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ec60  mov     ebx, eax
0x14000ec62  test    eax, eax
0x14000ec64  jns     short loc_14000ECC2
0x14000ec66  mov     [rsp+58h+nShowCmd], eax
0x14000ec6a  mov     r9d, 37h ; '7'
0x14000ec70  jmp     loc_14000ECFC
0x14000ec75  xor     ebx, ebx
0x14000ec77  test    r14d, r14d
0x14000ec7a  jnz     short loc_14000ECC2
0x14000ec7c  mov     edx, 104h; unsigned __int64
0x14000ec81  mov     rcx, rdi; unsigned __int16 *
0x14000ec84  test    ebp, ebp
0x14000ec86  jz      short loc_14000ECA4
0x14000ec88  lea     r8, aOfferim; "-OfferIM "
0x14000ec8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ec94  mov     ebx, eax
0x14000ec96  test    eax, eax
0x14000ec98  jns     short loc_14000ECC2
0x14000ec9a  mov     [rsp+58h+nShowCmd], eax
0x14000ec9e  lea     r9d, [r14+50h]
0x14000eca2  jmp     short loc_14000ECFC
0x14000eca4  lea     r8, aSolicitedim; "-SolicitedIM "
0x14000ecab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000ecb0  mov     ebx, eax
0x14000ecb2  test    eax, eax
0x14000ecb4  jns     short loc_14000ECC2
0x14000ecb6  mov     [rsp+58h+nShowCmd], eax
0x14000ecba  mov     r9d, 57h ; 'W'
0x14000ecc0  jmp     short loc_14000ECFC
0x14000ecc2  mov     [rsp+58h+nShowCmd], 1; nShowCmd
0x14000ecca  lea     r8, aMsraExe_0; "msra.exe"
0x14000ecd1  mov     r9, rdi; lpParameters
0x14000ecd4  mov     [rsp+58h+lpDirectory], rsi; lpDirectory
0x14000ecd9  xor     edx, edx; lpOperation
0x14000ecdb  xor     ecx, ecx; hwnd
0x14000ecdd  call    cs:__imp_ShellExecuteW
0x14000ece3  cmp     rax, 20h ; ' '
0x14000ece7  jg      short loc_14000ED14
0x14000ece9  mov     ebx, 80004005h
0x14000ecee  mov     [rsp+58h+nShowCmd], 80004005h; unsigned int
0x14000ecf6  mov     r9d, 70h ; 'p'; unsigned int
0x14000ecfc  lea     rax, aStartmsraproce; "StartMSRAProcess"
0x14000ed03  lea     r8, aBaseDiagnosisR_6; "base\\diagnosis\\ra\\dcom\\src\\remotea"...
0x14000ed0a  mov     [rsp+58h+lpDirectory], rax; unsigned __int16 *
0x14000ed0f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000ed14  call    cs:__imp_GetProcessHeap
0x14000ed1a  mov     r8, rdi; lpMem
0x14000ed1d  xor     edx, edx; dwFlags
0x14000ed1f  mov     rcx, rax; hHeap
0x14000ed22  call    cs:__imp_HeapFree
0x14000ed28  test    rsi, rsi
0x14000ed2b  jz      short loc_14000ED41
0x14000ed2d  call    cs:__imp_GetProcessHeap
0x14000ed33  mov     r8, rsi; lpMem
0x14000ed36  xor     edx, edx; dwFlags
0x14000ed38  mov     rcx, rax; hHeap
0x14000ed3b  call    cs:__imp_HeapFree
0x14000ed41  mov     eax, ebx
0x14000ed43  add     rsp, 30h
0x14000ed47  pop     r14
0x14000ed49  pop     rdi
0x14000ed4a  pop     rsi
0x14000ed4b  pop     rbp
0x14000ed4c  pop     rbx
0x14000ed4d  retn
```
