# MUIOffline_EnumUILanguages

- ea: `0x18005db94`
- end: `0x18005dd9b`
- name: `MUIOffline_EnumUILanguages`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003c534`

## callees

- `0x180005de8`
- `0x18005db94`
- `0x18005dda4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dc37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005dc37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005dc24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005dd26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005dc24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005dd26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005dd34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005dd34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dd56`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dd7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dd7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dc88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dd0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dc88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005dd0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dd1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dd6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dd1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005dd6e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005dcb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005dcb8`

## pseudocode

```c
__int64 __fastcall MUIOffline_EnumUILanguages(_WORD *a1, __int64 a2, DWORD a3, __int64 a4)
{
  HKEY v5; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rcx
  _WORD *v9; // rax
  LSTATUS v10; // ebx
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  __int64 v13; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v15; // r8
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  WCHAR *v19; // rdi
  HANDLE v20; // rax
  DWORD LastError; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-30h]
  DWORD cbData; // [rsp+30h] [rbp-20h] BYREF
  HKEY v25; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  __int64 Data; // [rsp+98h] [rbp+48h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+50h] BYREF

  Type = a3;
  Data = a2;
  v5 = 0;
  v25 = 0;
  v7 = 0;
  if ( !a1 )
  {
    v10 = 87;
    goto LABEL_23;
  }
  hKey = 0;
  v8 = 0x7FFFFFFF;
  Type = 0;
  LODWORD(Data) = 0;
  v9 = a1;
  cbData = 4;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  if ( !v8 )
  {
    v10 = 50;
LABEL_20:
    v5 = 0;
    v25 = 0;
    goto LABEL_23;
  }
  v11 = ((0x7FFFFFFF - (_DWORD)v8) & (unsigned int)-(v8 != 0)) + 16;
  v12 = (unsigned int)v11;
  v13 = 2 * v11;
  ProcessHeap = GetProcessHeap();
  v15 = v13;
  v10 = 8;
  v16 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v15);
  v19 = v16;
  if ( v16 )
  {
    if ( (int)StringCchPrintfW(v16, (unsigned int)v12, L"%s\\Select", a1) < 0 )
      goto LABEL_9;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &hKey);
    if ( v10 )
      goto LABEL_15;
    v10 = RegQueryValueExW(hKey, L"Default", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v10 )
      goto LABEL_15;
    if ( Type == 4
      && (LODWORD(phkResult) = Data, (int)StringCchPrintfW(v19, v12, L"%s\\ControlSet%03u", a1, phkResult) >= 0) )
    {
      v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &v25);
    }
    else
    {
LABEL_9:
      v10 = 50;
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v19 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
  }
  if ( v10 )
    goto LABEL_20;
  v7 = MUIOffline_EnumUILanguagesFromKey(v25, v17, v18, a4);
  LastError = GetLastError();
  v5 = v25;
  v10 = LastError;
LABEL_23:
  if ( v5 )
    RegCloseKey(v5);
  if ( v10 )
    SetLastError(v10);
  return v7;
}

```

## disassembly

```asm
0x18005db94  mov     [rsp-38h+arg_0], rbx
0x18005db99  mov     [rsp-38h+Type], r8d
0x18005db9e  mov     [rsp-38h+Data], rdx
0x18005dba3  push    rbp
0x18005dba4  push    rsi
0x18005dba5  push    rdi
0x18005dba6  push    r12
0x18005dba8  push    r13
0x18005dbaa  push    r14
0x18005dbac  push    r15
0x18005dbae  mov     rbp, rsp
0x18005dbb1  sub     rsp, 50h
0x18005dbb5  xor     r13d, r13d
0x18005dbb8  mov     rsi, rcx
0x18005dbbb  mov     ecx, r13d; hKey
0x18005dbbe  mov     r12, r9
0x18005dbc1  mov     [rbp+var_18], rcx
0x18005dbc5  mov     r15d, r13d
0x18005dbc8  test    rsi, rsi
0x18005dbcb  jz      loc_18005DD64
0x18005dbd1  mov     edx, 7FFFFFFFh
0x18005dbd6  mov     [rbp+hKey], r13
0x18005dbda  mov     ecx, edx
0x18005dbdc  mov     [rbp+Type], r13d
0x18005dbe0  mov     dword ptr [rbp+Data], r13d
0x18005dbe4  mov     rax, rsi
0x18005dbe7  mov     [rbp+cbData], 4
0x18005dbee  cmp     [rax], r13w
0x18005dbf2  jz      short loc_18005DBFE
0x18005dbf4  add     rax, 2
0x18005dbf8  sub     rcx, 1
0x18005dbfc  jnz     short loc_18005DBEE
0x18005dbfe  sub     rdx, rcx
0x18005dc01  mov     rax, rcx
0x18005dc04  neg     rax
0x18005dc07  sbb     rax, rax
0x18005dc0a  and     rax, rdx
0x18005dc0d  test    rcx, rcx
0x18005dc10  jnz     short loc_18005DC1A
0x18005dc12  lea     ebx, [rcx+32h]
0x18005dc15  jmp     loc_18005DD3E
0x18005dc1a  add     eax, 10h
0x18005dc1d  mov     r14d, eax
0x18005dc20  lea     rbx, [rax+rax]
0x18005dc24  call    cs:__imp_GetProcessHeap
0x18005dc2a  mov     r8, rbx; dwBytes
0x18005dc2d  mov     ebx, 8
0x18005dc32  mov     edx, ebx; dwFlags
0x18005dc34  mov     rcx, rax; hHeap
0x18005dc37  call    cs:__imp_HeapAlloc
0x18005dc3d  mov     rdi, rax
0x18005dc40  test    rax, rax
0x18005dc43  jz      loc_18005DD12
0x18005dc49  mov     r9, rsi
0x18005dc4c  lea     r8, aSSelect; "%s\\Select"
0x18005dc53  mov     edx, r14d; unsigned __int64
0x18005dc56  mov     rcx, rax; unsigned __int16 *
0x18005dc59  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005dc5e  test    eax, eax
0x18005dc60  jns     short loc_18005DC6C
0x18005dc62  mov     ebx, 32h ; '2'
0x18005dc67  jmp     loc_18005DD12
0x18005dc6c  lea     rax, [rbp+hKey]
0x18005dc70  mov     r9d, 20019h; samDesired
0x18005dc76  xor     r8d, r8d; ulOptions
0x18005dc79  mov     [rsp+50h+phkResult], rax; phkResult
0x18005dc7e  mov     rdx, rdi; lpSubKey
0x18005dc81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005dc88  call    cs:__imp_RegOpenKeyExW
0x18005dc8e  mov     ebx, eax
0x18005dc90  test    eax, eax
0x18005dc92  jnz     short loc_18005DD12
0x18005dc94  mov     rcx, [rbp+hKey]; hKey
0x18005dc98  lea     rax, [rbp+cbData]
0x18005dc9c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18005dca1  lea     r9, [rbp+Type]; lpType
0x18005dca5  lea     rax, [rbp+Data]
0x18005dca9  xor     r8d, r8d; lpReserved
0x18005dcac  lea     rdx, aDefault; "Default"
0x18005dcb3  mov     [rsp+50h+phkResult], rax; lpData
0x18005dcb8  call    cs:__imp_RegQueryValueExW
0x18005dcbe  mov     ebx, eax
0x18005dcc0  test    eax, eax
0x18005dcc2  jnz     short loc_18005DD12
0x18005dcc4  cmp     [rbp+Type], 4
0x18005dcc8  jnz     short loc_18005DC62
0x18005dcca  mov     eax, dword ptr [rbp+Data]
0x18005dccd  lea     r8, aSControlset03u; "%s\\ControlSet%03u"
0x18005dcd4  mov     r9, rsi
0x18005dcd7  mov     dword ptr [rsp+50h+phkResult], eax
0x18005dcdb  mov     rdx, r14; unsigned __int64
0x18005dcde  mov     rcx, rdi; unsigned __int16 *
0x18005dce1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005dce6  test    eax, eax
0x18005dce8  js      loc_18005DC62
0x18005dcee  lea     rax, [rbp+var_18]
0x18005dcf2  mov     r9d, 20019h; samDesired
0x18005dcf8  xor     r8d, r8d; ulOptions
0x18005dcfb  mov     [rsp+50h+phkResult], rax; phkResult
0x18005dd00  mov     rdx, rdi; lpSubKey
0x18005dd03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005dd0a  call    cs:__imp_RegOpenKeyExW
0x18005dd10  mov     ebx, eax
0x18005dd12  mov     rcx, [rbp+hKey]; hKey
0x18005dd16  test    rcx, rcx
0x18005dd19  jz      short loc_18005DD21
0x18005dd1b  call    cs:__imp_RegCloseKey
0x18005dd21  test    rdi, rdi
0x18005dd24  jz      short loc_18005DD3A
0x18005dd26  call    cs:__imp_GetProcessHeap
0x18005dd2c  mov     r8, rdi; lpMem
0x18005dd2f  xor     edx, edx; dwFlags
0x18005dd31  mov     rcx, rax; hHeap
0x18005dd34  call    cs:__imp_HeapFree
0x18005dd3a  test    ebx, ebx
0x18005dd3c  jz      short loc_18005DD47
0x18005dd3e  mov     rcx, r13
0x18005dd41  mov     [rbp+var_18], rcx
0x18005dd45  jmp     short loc_18005DD69
0x18005dd47  mov     rcx, [rbp+var_18]
0x18005dd4b  mov     r9, r12
0x18005dd4e  call    MUIOffline_EnumUILanguagesFromKey
0x18005dd53  mov     r15d, eax
0x18005dd56  call    cs:__imp_GetLastError
0x18005dd5c  mov     rcx, [rbp+var_18]
0x18005dd60  mov     ebx, eax
0x18005dd62  jmp     short loc_18005DD69
0x18005dd64  mov     ebx, 57h ; 'W'
0x18005dd69  test    rcx, rcx
0x18005dd6c  jz      short loc_18005DD74
0x18005dd6e  call    cs:__imp_RegCloseKey
0x18005dd74  test    ebx, ebx
0x18005dd76  jz      short loc_18005DD80
0x18005dd78  mov     ecx, ebx; dwErrCode
0x18005dd7a  call    cs:__imp_SetLastError
0x18005dd80  mov     rbx, [rsp+50h+arg_0]
0x18005dd88  mov     eax, r15d
0x18005dd8b  add     rsp, 50h
0x18005dd8f  pop     r15
0x18005dd91  pop     r14
0x18005dd93  pop     r13
0x18005dd95  pop     r12
0x18005dd97  pop     rdi
0x18005dd98  pop     rsi
0x18005dd99  pop     rbp
0x18005dd9a  retn
```
