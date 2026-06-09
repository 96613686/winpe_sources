# BuildCacheDirectoryStructure(ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x180003b58`
- end: `0x180003fb7`
- name: `?BuildCacheDirectoryStructure@@YAKPEAPEAG000@Z`
- size: `1119`
- prototype: `__int64 __fastcall(LPCWSTR *, LPCWSTR *, LPCWSTR *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004320`
- `0x180004b04`

## callees

- `0x1800030c4`
- `0x180003b58`
- `0x180004714`
- `0x1800047c4`
- `0x18000490c`
- `0x180004dec`
- `0x18000ede8`
- `0x1800135cc`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003c0f`
- `KERNEL32!HeapAlloc` at `0x180003d09`
- `KERNEL32!HeapAlloc` at `0x180003df5`
- `KERNEL32!HeapAlloc` at `0x180003c0f`
- `KERNEL32!HeapAlloc` at `0x180003d09`
- `KERNEL32!HeapAlloc` at `0x180003df5`
- `KERNEL32!GetProcessHeap` at `0x180003bfd`
- `KERNEL32!GetProcessHeap` at `0x180003cf7`
- `KERNEL32!GetProcessHeap` at `0x180003de3`
- `KERNEL32!GetProcessHeap` at `0x180003f18`
- `KERNEL32!GetProcessHeap` at `0x180003f3b`
- `KERNEL32!GetProcessHeap` at `0x180003f5e`
- `KERNEL32!GetProcessHeap` at `0x180003f82`
- `KERNEL32!GetProcessHeap` at `0x180003bfd`
- `KERNEL32!GetProcessHeap` at `0x180003cf7`
- `KERNEL32!GetProcessHeap` at `0x180003de3`
- `KERNEL32!GetProcessHeap` at `0x180003f18`
- `KERNEL32!GetProcessHeap` at `0x180003f3b`
- `KERNEL32!GetProcessHeap` at `0x180003f5e`
- `KERNEL32!GetProcessHeap` at `0x180003f82`
- `KERNEL32!HeapFree` at `0x180003f26`
- `KERNEL32!HeapFree` at `0x180003f49`
- `KERNEL32!HeapFree` at `0x180003f6c`
- `KERNEL32!HeapFree` at `0x180003f90`
- `KERNEL32!HeapFree` at `0x180003f26`
- `KERNEL32!HeapFree` at `0x180003f49`
- `KERNEL32!HeapFree` at `0x180003f6c`
- `KERNEL32!HeapFree` at `0x180003f90`
- `KERNEL32!GetLastError` at `0x180003c7f`
- `KERNEL32!GetLastError` at `0x180003d6b`
- `KERNEL32!GetLastError` at `0x180003e52`
- `KERNEL32!GetLastError` at `0x180003ec0`
- `KERNEL32!GetLastError` at `0x180003c7f`
- `KERNEL32!GetLastError` at `0x180003d6b`
- `KERNEL32!GetLastError` at `0x180003e52`
- `KERNEL32!GetLastError` at `0x180003ec0`
- `KERNEL32!SetFileAttributesW` at `0x180003e9d`
- `KERNEL32!SetFileAttributesW` at `0x180003e9d`

## pseudocode

```c
__int64 __fastcall BuildCacheDirectoryStructure(LPCWSTR *a1, LPCWSTR *a2, LPCWSTR *a3, unsigned __int16 **a4)
{
  DWORD MrcDir; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  HANDLE v15; // rax
  unsigned __int16 *v16; // rax
  HANDLE v17; // rax
  unsigned __int16 *v18; // rax
  DWORD LastError; // eax
  unsigned __int16 *v20; // rax
  WCHAR *v21; // rdi
  HANDLE v22; // rax
  WCHAR *v23; // rdi
  HANDLE v24; // rax
  WCHAR *v25; // rdi
  HANDLE v26; // rax
  void *v27; // rdi
  HANDLE v28; // rax
  unsigned __int64 v30; // [rsp+50h] [rbp+30h] BYREF

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a1 = 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v30 = 0;
  MrcDir = GetMrcDir(0, &v30);
  if ( MrcDir != 122 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 22;
LABEL_47:
      WPP_SF_d(v9[2], v10, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, MrcDir);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  ProcessHeap = GetProcessHeap();
  v12 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, (unsigned int)(2 * v30));
  *a1 = v12;
  if ( !v12 )
    goto LABEL_55;
  MrcDir = GetMrcDir(v12, &v30);
  if ( MrcDir )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_56;
    v14 = 23;
    goto LABEL_16;
  }
  if ( !(unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(*a1, 0) )
  {
    MrcDir = GetLastError();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 24;
      goto LABEL_47;
    }
LABEL_48:
    if ( !MrcDir )
      return MrcDir;
    goto LABEL_56;
  }
  v30 = 0;
  MrcDir = GetCacheDir(0);
  if ( MrcDir != 122 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 25;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v15 = GetProcessHeap();
  v16 = (unsigned __int16 *)HeapAlloc(v15, 0, (unsigned int)(2 * v30));
  *a2 = v16;
  if ( !v16 )
    goto LABEL_55;
  MrcDir = GetCacheDir(v16);
  if ( MrcDir )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_56;
    v14 = 26;
    goto LABEL_16;
  }
  if ( !(unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(
                        *a2,
                        L"D:P(A;OICI;FR;;;S-1-15-2-1)(A;OICI;FRFX;;;WD)(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)(A;OICI;FRFX;;;BU)") )
  {
    MrcDir = GetLastError();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 27;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v30 = 0;
  MrcDir = GetNewDataDir(0);
  if ( MrcDir != 122 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 28;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  v17 = GetProcessHeap();
  v18 = (unsigned __int16 *)HeapAlloc(v17, 0, (unsigned int)(2 * v30));
  *a3 = v18;
  if ( !v18 )
    goto LABEL_55;
  MrcDir = GetNewDataDir(v18);
  if ( MrcDir )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_56;
    v14 = 29;
LABEL_16:
    WPP_SF_d(v13[2], v14, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, MrcDir);
LABEL_56:
    v21 = (WCHAR *)*a1;
    if ( *a1 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v21);
      *a1 = 0;
    }
    v23 = (WCHAR *)*a2;
    if ( *a2 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v23);
      *a2 = 0;
    }
    v25 = (WCHAR *)*a3;
    if ( *a3 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v25);
      *a3 = 0;
    }
    v27 = *a4;
    if ( *a4 )
    {
      v28 = GetProcessHeap();
      HeapFree(v28, 0, v27);
      *a4 = 0;
    }
    return MrcDir;
  }
  if ( !(unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(*a3, 0) )
  {
    MrcDir = GetLastError();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 30;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  if ( !SetFileAttributesW(*a3, 2u)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, LastError);
  }
  v20 = MemMallocAndCat(*a1, L"\\", L"dmrc.idx", 0);
  *a4 = v20;
  if ( !v20 )
  {
LABEL_55:
    MrcDir = 8;
    goto LABEL_56;
  }
  return MrcDir;
}

```

## disassembly

```asm
0x180003b58  mov     [rsp-28h+arg_8], rbx
0x180003b5d  mov     [rsp-28h+arg_10], rsi
0x180003b62  push    rbp
0x180003b63  push    rdi
0x180003b64  push    r12
0x180003b66  push    r14
0x180003b68  push    r15
0x180003b6a  mov     rbp, rsp
0x180003b6d  sub     rsp, 20h
0x180003b71  mov     r12, r9
0x180003b74  mov     rsi, r8
0x180003b77  mov     r15, rdx
0x180003b7a  mov     r14, rcx
0x180003b7d  test    rcx, rcx
0x180003b80  jnz     short loc_180003B87
0x180003b82  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003b87  test    r15, r15
0x180003b8a  jnz     short loc_180003B91
0x180003b8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003b91  test    rsi, rsi
0x180003b94  jnz     short loc_180003B9B
0x180003b96  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180003b9b  mov     qword ptr [r14], 0
0x180003ba2  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x180003ba6  mov     qword ptr [r15], 0
0x180003bad  xor     ecx, ecx; unsigned __int16 *
0x180003baf  mov     qword ptr [rsi], 0
0x180003bb6  mov     qword ptr [r12], 0
0x180003bbe  mov     [rbp+arg_0], 0
0x180003bc6  call    ?GetMrcDir@@YAKPEAGPEA_K@Z; GetMrcDir(ushort *,unsigned __int64 *)
0x180003bcb  mov     ebx, eax
0x180003bcd  cmp     eax, 7Ah ; 'z'
0x180003bd0  jz      short loc_180003BFD
0x180003bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bd9  lea     rax, WPP_GLOBAL_Control
0x180003be0  cmp     rcx, rax
0x180003be3  jz      loc_180003E8B
0x180003be9  test    byte ptr [rcx+1Ch], 1
0x180003bed  jz      loc_180003E8B
0x180003bf3  mov     edx, 16h
0x180003bf8  jmp     loc_180003E78
0x180003bfd  call    cs:__imp_GetProcessHeap
0x180003c03  mov     ecx, dword ptr [rbp+arg_0]
0x180003c06  xor     edx, edx; dwFlags
0x180003c08  lea     r8d, [rcx+rcx]; dwBytes
0x180003c0c  mov     rcx, rax; hHeap
0x180003c0f  call    cs:__imp_HeapAlloc
0x180003c15  mov     [r14], rax
0x180003c18  test    rax, rax
0x180003c1b  jz      loc_180003F0B
0x180003c21  lea     rdx, [rbp+arg_0]; unsigned __int64 *
0x180003c25  mov     rcx, rax; unsigned __int16 *
0x180003c28  call    ?GetMrcDir@@YAKPEAGPEA_K@Z; GetMrcDir(ushort *,unsigned __int64 *)
0x180003c2d  mov     ebx, eax
0x180003c2f  test    eax, eax
0x180003c31  jz      short loc_180003C71
0x180003c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c3a  lea     rax, WPP_GLOBAL_Control
0x180003c41  cmp     rcx, rax
0x180003c44  jz      loc_180003F10
0x180003c4a  test    byte ptr [rcx+1Ch], 1
0x180003c4e  jz      loc_180003F10
0x180003c54  mov     edx, 17h
0x180003c59  mov     rcx, [rcx+10h]
0x180003c5d  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x180003c64  mov     r9d, ebx
0x180003c67  call    WPP_SF_d
0x180003c6c  jmp     loc_180003F10
0x180003c71  mov     rcx, [r14]; lpFileName
0x180003c74  xor     edx, edx; StringSecurityDescriptor
0x180003c76  call    FSMakeDirPathExist_StringSecurityDescriptor
0x180003c7b  test    eax, eax
0x180003c7d  jnz     short loc_180003CB2
0x180003c7f  call    cs:__imp_GetLastError
0x180003c85  mov     ebx, eax
0x180003c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c8e  lea     rax, WPP_GLOBAL_Control
0x180003c95  cmp     rcx, rax
0x180003c98  jz      loc_180003E8B
0x180003c9e  test    byte ptr [rcx+1Ch], 1
0x180003ca2  jz      loc_180003E8B
0x180003ca8  mov     edx, 18h
0x180003cad  jmp     loc_180003E78
0x180003cb2  lea     rdx, [rbp+arg_0]
0x180003cb6  mov     [rbp+arg_0], 0
0x180003cbe  xor     ecx, ecx; unsigned __int16 *
0x180003cc0  call    GetCacheDir
0x180003cc5  mov     ebx, eax
0x180003cc7  cmp     eax, 7Ah ; 'z'
0x180003cca  jz      short loc_180003CF7
0x180003ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cd3  lea     rax, WPP_GLOBAL_Control
0x180003cda  cmp     rcx, rax
0x180003cdd  jz      loc_180003E8B
0x180003ce3  test    byte ptr [rcx+1Ch], 1
0x180003ce7  jz      loc_180003E8B
0x180003ced  mov     edx, 19h
0x180003cf2  jmp     loc_180003E78
0x180003cf7  call    cs:__imp_GetProcessHeap
0x180003cfd  mov     ecx, dword ptr [rbp+arg_0]
0x180003d00  xor     edx, edx; dwFlags
0x180003d02  lea     r8d, [rcx+rcx]; dwBytes
0x180003d06  mov     rcx, rax; hHeap
0x180003d09  call    cs:__imp_HeapAlloc
0x180003d0f  mov     [r15], rax
0x180003d12  test    rax, rax
0x180003d15  jz      loc_180003F0B
0x180003d1b  lea     rdx, [rbp+arg_0]
0x180003d1f  mov     rcx, rax; unsigned __int16 *
0x180003d22  call    GetCacheDir
0x180003d27  mov     ebx, eax
0x180003d29  test    eax, eax
0x180003d2b  jz      short loc_180003D58
0x180003d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d34  lea     rax, WPP_GLOBAL_Control
0x180003d3b  cmp     rcx, rax
0x180003d3e  jz      loc_180003F10
0x180003d44  test    byte ptr [rcx+1Ch], 1
0x180003d48  jz      loc_180003F10
0x180003d4e  mov     edx, 1Ah
0x180003d53  jmp     loc_180003C59
0x180003d58  mov     rcx, [r15]; lpFileName
0x180003d5b  lea     rdx, StringSecurityDescriptor; "D:P(A;OICI;FR;;;S-1-15-2-1)(A;OICI;FRFX"...
0x180003d62  call    FSMakeDirPathExist_StringSecurityDescriptor
0x180003d67  test    eax, eax
0x180003d69  jnz     short loc_180003D9E
0x180003d6b  call    cs:__imp_GetLastError
0x180003d71  mov     ebx, eax
0x180003d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d7a  lea     rax, WPP_GLOBAL_Control
0x180003d81  cmp     rcx, rax
0x180003d84  jz      loc_180003E8B
0x180003d8a  test    byte ptr [rcx+1Ch], 1
0x180003d8e  jz      loc_180003E8B
0x180003d94  mov     edx, 1Bh
0x180003d99  jmp     loc_180003E78
0x180003d9e  lea     rdx, [rbp+arg_0]
0x180003da2  mov     [rbp+arg_0], 0
0x180003daa  xor     ecx, ecx; unsigned __int16 *
0x180003dac  call    GetNewDataDir
0x180003db1  mov     ebx, eax
0x180003db3  cmp     eax, 7Ah ; 'z'
0x180003db6  jz      short loc_180003DE3
0x180003db8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dbf  lea     rax, WPP_GLOBAL_Control
0x180003dc6  cmp     rcx, rax
0x180003dc9  jz      loc_180003E8B
0x180003dcf  test    byte ptr [rcx+1Ch], 1
0x180003dd3  jz      loc_180003E8B
0x180003dd9  mov     edx, 1Ch
0x180003dde  jmp     loc_180003E78
0x180003de3  call    cs:__imp_GetProcessHeap
0x180003de9  mov     ecx, dword ptr [rbp+arg_0]
0x180003dec  xor     edx, edx; dwFlags
0x180003dee  lea     r8d, [rcx+rcx]; dwBytes
0x180003df2  mov     rcx, rax; hHeap
0x180003df5  call    cs:__imp_HeapAlloc
0x180003dfb  mov     [rsi], rax
0x180003dfe  test    rax, rax
0x180003e01  jz      loc_180003F0B
0x180003e07  lea     rdx, [rbp+arg_0]
0x180003e0b  mov     rcx, rax; unsigned __int16 *
0x180003e0e  call    GetNewDataDir
0x180003e13  mov     ebx, eax
0x180003e15  test    eax, eax
0x180003e17  jz      short loc_180003E44
0x180003e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e20  lea     rax, WPP_GLOBAL_Control
0x180003e27  cmp     rcx, rax
0x180003e2a  jz      loc_180003F10
0x180003e30  test    byte ptr [rcx+1Ch], 1
0x180003e34  jz      loc_180003F10
0x180003e3a  mov     edx, 1Dh
0x180003e3f  jmp     loc_180003C59
0x180003e44  mov     rcx, [rsi]; lpFileName
0x180003e47  xor     edx, edx; StringSecurityDescriptor
0x180003e49  call    FSMakeDirPathExist_StringSecurityDescriptor
0x180003e4e  test    eax, eax
0x180003e50  jnz     short loc_180003E95
0x180003e52  call    cs:__imp_GetLastError
0x180003e58  mov     ebx, eax
0x180003e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e61  lea     rax, WPP_GLOBAL_Control
0x180003e68  cmp     rcx, rax
0x180003e6b  jz      short loc_180003E8B
0x180003e6d  test    byte ptr [rcx+1Ch], 1
0x180003e71  jz      short loc_180003E8B
0x180003e73  mov     edx, 1Eh
0x180003e78  mov     rcx, [rcx+10h]
0x180003e7c  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x180003e83  mov     r9d, ebx
0x180003e86  call    WPP_SF_d
0x180003e8b  test    ebx, ebx
0x180003e8d  jz      loc_180003F9E
0x180003e93  jmp     short loc_180003F10
0x180003e95  mov     rcx, [rsi]; lpFileName
0x180003e98  mov     edx, 2; dwFileAttributes
0x180003e9d  call    cs:__imp_SetFileAttributesW
0x180003ea3  test    eax, eax
0x180003ea5  jnz     short loc_180003EE5
0x180003ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eae  lea     rax, WPP_GLOBAL_Control
0x180003eb5  cmp     rcx, rax
0x180003eb8  jz      short loc_180003EE5
0x180003eba  test    byte ptr [rcx+1Ch], 2
0x180003ebe  jz      short loc_180003EE5
0x180003ec0  call    cs:__imp_GetLastError
0x180003ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ecd  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x180003ed4  mov     edx, 1Fh
0x180003ed9  mov     r9d, eax
0x180003edc  mov     rcx, [rcx+10h]
0x180003ee0  call    WPP_SF_d
0x180003ee5  mov     rcx, [r14]; unsigned __int16 *
0x180003ee8  lea     r8, aDmrcIdx; "dmrc.idx"
0x180003eef  xor     r9d, r9d
0x180003ef2  lea     rdx, asc_180016E08; "\\"
0x180003ef9  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x180003efe  mov     [r12], rax
0x180003f02  test    rax, rax
0x180003f05  jnz     loc_180003F9E
0x180003f0b  mov     ebx, 8
0x180003f10  mov     rdi, [r14]
0x180003f13  test    rdi, rdi
0x180003f16  jz      short loc_180003F33
0x180003f18  call    cs:__imp_GetProcessHeap
0x180003f1e  mov     r8, rdi; lpMem
0x180003f21  xor     edx, edx; dwFlags
0x180003f23  mov     rcx, rax; hHeap
0x180003f26  call    cs:__imp_HeapFree
0x180003f2c  mov     qword ptr [r14], 0
0x180003f33  mov     rdi, [r15]
0x180003f36  test    rdi, rdi
0x180003f39  jz      short loc_180003F56
0x180003f3b  call    cs:__imp_GetProcessHeap
0x180003f41  mov     r8, rdi; lpMem
0x180003f44  xor     edx, edx; dwFlags
0x180003f46  mov     rcx, rax; hHeap
0x180003f49  call    cs:__imp_HeapFree
0x180003f4f  mov     qword ptr [r15], 0
0x180003f56  mov     rdi, [rsi]
0x180003f59  test    rdi, rdi
0x180003f5c  jz      short loc_180003F79
0x180003f5e  call    cs:__imp_GetProcessHeap
0x180003f64  mov     r8, rdi; lpMem
0x180003f67  xor     edx, edx; dwFlags
0x180003f69  mov     rcx, rax; hHeap
0x180003f6c  call    cs:__imp_HeapFree
0x180003f72  mov     qword ptr [rsi], 0
0x180003f79  mov     rdi, [r12]
0x180003f7d  test    rdi, rdi
0x180003f80  jz      short loc_180003F9E
0x180003f82  call    cs:__imp_GetProcessHeap
0x180003f88  mov     r8, rdi; lpMem
0x180003f8b  xor     edx, edx; dwFlags
0x180003f8d  mov     rcx, rax; hHeap
0x180003f90  call    cs:__imp_HeapFree
0x180003f96  mov     qword ptr [r12], 0
0x180003f9e  mov     rsi, [rsp+20h+arg_10]
0x180003fa3  mov     eax, ebx
0x180003fa5  mov     rbx, [rsp+20h+arg_8]
0x180003faa  add     rsp, 20h
0x180003fae  pop     r15
0x180003fb0  pop     r14
0x180003fb2  pop     r12
0x180003fb4  pop     rdi
0x180003fb5  pop     rbp
0x180003fb6  retn
```
