# WaasMedic::ResetRepairPlugin::WriteToFile(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004a840`
- end: `0x18004aa44`
- name: `?WriteToFile@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@1@Z`
- size: `516`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800455d4`
- `0x180047ea4`
- `0x18004815c`

## callees

- `0x1800040b8`
- `0x180005e40`
- `0x18002543c`
- `0x18004a840`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a89e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a8e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a9d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aa23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a972`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a972`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004a9cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004a9cc`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004a894`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004a8dc`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004a894`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004a8dc`

## string_xrefs

- `0x18004a9a0`: `Failed to create [%s]. Err=0x%08x`
- `0x18004a90b`: `Failed to get security info from parent folder [%s]. Err=0x%08x`
- `0x18004a9f5`: `Failed to write to [%s]. Err=0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::ResetRepairPlugin::WriteToFile(__int64 a1, _DWORD *a2, __int64 *a3, const WCHAR *a4)
{
  const WCHAR *v4; // rdi
  const WCHAR *v7; // rcx
  void *v8; // r14
  unsigned int v9; // ebx
  const WCHAR *v10; // rcx
  signed int LastError; // eax
  const WCHAR *v12; // rcx
  char *v13; // rax
  char *v14; // r15
  signed int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  DWORD v17; // r8d
  signed int v18; // eax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-20h] BYREF
  DWORD nLengthNeeded; // [rsp+90h] [rbp+30h] BYREF
  int v22; // [rsp+94h] [rbp+34h]

  v22 = HIDWORD(a1);
  nLengthNeeded = 0;
  v4 = a4;
  if ( *((_QWORD *)a4 + 3) <= 7u )
    v7 = a4;
  else
    v7 = *(const WCHAR **)a4;
  if ( GetFileSecurityW(v7, 7u, 0, 0, &nLengthNeeded) || GetLastError() == 122 )
  {
    v9 = 0;
    v8 = operator new[](nLengthNeeded);
    if ( *((_QWORD *)v4 + 3) <= 7u )
      v10 = v4;
    else
      v10 = *(const WCHAR **)v4;
    if ( GetFileSecurityW(v10, 7u, v8, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_17;
  }
  else
  {
    v8 = 0;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( *((_QWORD *)v4 + 3) > 7u )
      v4 = *(const WCHAR **)v4;
    LogLevelW(2u, L"Failed to get security info from parent folder [%s]. Err=0x%08x", v4, v9);
    return v9;
  }
LABEL_17:
  SecurityAttributes.nLength = nLengthNeeded;
  *(&SecurityAttributes.nLength + 1) = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = v8;
  if ( (unsigned __int64)a3[3] <= 7 )
    v12 = (const WCHAR *)a3;
  else
    v12 = (const WCHAR *)*a3;
  v13 = (char *)CreateFileW(v12, 0xC0000000, 3u, &SecurityAttributes, 2u, 0x80u, 0);
  v14 = v13;
  if ( v13 == (char *)-1LL )
  {
    v15 = GetLastError();
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    if ( (unsigned __int64)a3[3] > 7 )
      a3 = (__int64 *)*a3;
    LogLevelW(2u, L"Failed to create [%s]. Err=0x%08x", a3, v9);
  }
  else
  {
    v17 = a2[4];
    if ( *((_QWORD *)a2 + 3) > 0xFu )
      a2 = *(_DWORD **)a2;
    if ( !WriteFile(v13, a2, v17, 0, 0) )
    {
      v18 = GetLastError();
      v9 = v18;
      if ( v18 > 0 )
        v9 = (unsigned __int16)v18 | 0x80070000;
      if ( (unsigned __int64)a3[3] > 7 )
        a3 = (__int64 *)*a3;
      LogLevelW(2u, L"Failed to write to [%s]. Err=0x%08x", a3, v9);
    }
  }
  if ( v8 )
    operator delete(v8, v16);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  return v9;
}

```

## disassembly

```asm
0x18004a840  mov     [rsp-28h+arg_8], rbx
0x18004a845  mov     [rsp-28h+arg_10], rsi
0x18004a84a  mov     qword ptr [rsp-28h+nLengthNeeded], rcx
0x18004a84f  push    rbp
0x18004a850  push    rdi
0x18004a851  push    r12
0x18004a853  push    r14
0x18004a855  push    r15
0x18004a857  mov     rbp, rsp
0x18004a85a  sub     rsp, 60h
0x18004a85e  mov     r15d, 7
0x18004a864  mov     [rbp+nLengthNeeded], 0
0x18004a86b  mov     rdi, r9
0x18004a86e  mov     rsi, r8
0x18004a871  mov     r12, rdx
0x18004a874  cmp     [r9+18h], r15
0x18004a878  jbe     short loc_18004A87F
0x18004a87a  mov     rcx, [r9]
0x18004a87d  jmp     short loc_18004A882
0x18004a87f  mov     rcx, rdi; lpFileName
0x18004a882  lea     rax, [rbp+nLengthNeeded]
0x18004a886  xor     r9d, r9d; nLength
0x18004a889  xor     r8d, r8d; pSecurityDescriptor
0x18004a88c  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18004a891  mov     edx, r15d; RequestedInformation
0x18004a894  call    cs:__imp_GetFileSecurityW
0x18004a89a  test    eax, eax
0x18004a89c  jnz     short loc_18004A8AE
0x18004a89e  call    cs:__imp_GetLastError
0x18004a8a4  cmp     eax, 7Ah ; 'z'
0x18004a8a7  jz      short loc_18004A8AE
0x18004a8a9  xor     r14d, r14d
0x18004a8ac  jmp     short loc_18004A8E6
0x18004a8ae  mov     ecx, [rbp+nLengthNeeded]; unsigned __int64
0x18004a8b1  xor     ebx, ebx
0x18004a8b3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004a8b8  mov     r14, rax
0x18004a8bb  cmp     [rdi+18h], r15
0x18004a8bf  jbe     short loc_18004A8C6
0x18004a8c1  mov     rcx, [rdi]
0x18004a8c4  jmp     short loc_18004A8C9
0x18004a8c6  mov     rcx, rdi; lpFileName
0x18004a8c9  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18004a8cd  lea     rax, [rbp+nLengthNeeded]
0x18004a8d1  mov     r8, r14; pSecurityDescriptor
0x18004a8d4  mov     [rsp+60h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18004a8d9  mov     edx, r15d; RequestedInformation
0x18004a8dc  call    cs:__imp_GetFileSecurityW
0x18004a8e2  test    eax, eax
0x18004a8e4  jnz     short loc_18004A924
0x18004a8e6  call    cs:__imp_GetLastError
0x18004a8ec  mov     ebx, eax
0x18004a8ee  test    eax, eax
0x18004a8f0  jle     short loc_18004A8FB
0x18004a8f2  movzx   ebx, ax
0x18004a8f5  or      ebx, 80070000h
0x18004a8fb  test    ebx, ebx
0x18004a8fd  jns     short loc_18004A924
0x18004a8ff  cmp     [rdi+18h], r15
0x18004a903  jbe     short loc_18004A908
0x18004a905  mov     rdi, [rdi]
0x18004a908  mov     r9d, ebx
0x18004a90b  lea     rdx, aFailedToGetSec_0; "Failed to get security info from parent"...
0x18004a912  mov     r8, rdi
0x18004a915  mov     ecx, 2; unsigned __int8
0x18004a91a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004a91f  jmp     loc_18004AA29
0x18004a924  mov     eax, [rbp+nLengthNeeded]
0x18004a927  mov     [rbp+SecurityAttributes.nLength], eax
0x18004a92a  mov     dword ptr [rbp+SecurityAttributes+4], 0
0x18004a931  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x18004a939  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], r14
0x18004a93d  cmp     [rsi+18h], r15
0x18004a941  jbe     short loc_18004A948
0x18004a943  mov     rcx, [rsi]
0x18004a946  jmp     short loc_18004A94B
0x18004a948  mov     rcx, rsi; lpFileName
0x18004a94b  mov     edi, 2
0x18004a950  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18004a959  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004a961  lea     r9, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18004a965  mov     edx, 0C0000000h; dwDesiredAccess
0x18004a96a  mov     dword ptr [rsp+60h+lpnLengthNeeded], edi; dwCreationDisposition
0x18004a96e  lea     r8d, [rdi+1]; dwShareMode
0x18004a972  call    cs:__imp_CreateFileW
0x18004a978  mov     r15, rax
0x18004a97b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a97f  jnz     short loc_18004A9A9
0x18004a981  call    cs:__imp_GetLastError
0x18004a987  mov     ebx, eax
0x18004a989  test    eax, eax
0x18004a98b  jle     short loc_18004A996
0x18004a98d  movzx   ebx, ax
0x18004a990  or      ebx, 80070000h
0x18004a996  cmp     qword ptr [rsi+18h], 7
0x18004a99b  jbe     short loc_18004A9A0
0x18004a99d  mov     rsi, [rsi]
0x18004a9a0  lea     rdx, aFailedToCreate; "Failed to create [%s]. Err=0x%08x"
0x18004a9a7  jmp     short loc_18004A9FC
0x18004a9a9  cmp     qword ptr [r12+18h], 0Fh
0x18004a9af  mov     r8d, [r12+10h]; nNumberOfBytesToWrite
0x18004a9b4  jbe     short loc_18004A9BA
0x18004a9b6  mov     r12, [r12]
0x18004a9ba  xor     r9d, r9d; lpNumberOfBytesWritten
0x18004a9bd  mov     [rsp+60h+lpnLengthNeeded], 0; lpOverlapped
0x18004a9c6  mov     rdx, r12; lpBuffer
0x18004a9c9  mov     rcx, r15; hFile
0x18004a9cc  call    cs:__imp_WriteFile
0x18004a9d2  test    eax, eax
0x18004a9d4  jnz     short loc_18004AA09
0x18004a9d6  call    cs:__imp_GetLastError
0x18004a9dc  mov     ebx, eax
0x18004a9de  test    eax, eax
0x18004a9e0  jle     short loc_18004A9EB
0x18004a9e2  movzx   ebx, ax
0x18004a9e5  or      ebx, 80070000h
0x18004a9eb  cmp     qword ptr [rsi+18h], 7
0x18004a9f0  jbe     short loc_18004A9F5
0x18004a9f2  mov     rsi, [rsi]
0x18004a9f5  lea     rdx, aFailedToWriteT; "Failed to write to [%s]. Err=0x%08x"
0x18004a9fc  mov     r9d, ebx
0x18004a9ff  mov     r8, rsi
0x18004aa02  mov     ecx, edi; unsigned __int8
0x18004aa04  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004aa09  test    r14, r14
0x18004aa0c  jz      short loc_18004AA16
0x18004aa0e  mov     rcx, r14; void *
0x18004aa11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004aa16  lea     rax, [r15-1]
0x18004aa1a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004aa1e  ja      short loc_18004AA29
0x18004aa20  mov     rcx, r15; hObject
0x18004aa23  call    cs:__imp_CloseHandle
0x18004aa29  lea     r11, [rsp+60h+var_s0]
0x18004aa2e  mov     eax, ebx
0x18004aa30  mov     rbx, [r11+38h]
0x18004aa34  mov     rsi, [r11+40h]
0x18004aa38  mov     rsp, r11
0x18004aa3b  pop     r15
0x18004aa3d  pop     r14
0x18004aa3f  pop     r12
0x18004aa41  pop     rdi
0x18004aa42  pop     rbp
0x18004aa43  retn
```
