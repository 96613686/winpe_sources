# SrSettings::CSrSettings::SetResourceString(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000ebf8`
- end: `0x18000ef00`
- name: `?SetResourceString@CSrSettings@SrSettings@@AEAAJPEBG000@Z`
- size: `776`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *lpStruct)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180010400`

## callees

- `0x180002178`
- `0x18000ebf8`
- `0x18000ef08`
- `0x1800105f8`
- `0x180010a0c`
- `0x180011b60`
- `0x180011c80`
- `0x1800142d2`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ee08`
- `KERNEL32!GetLastError` at `0x18000ee29`
- `KERNEL32!GetLastError` at `0x18000eebf`
- `KERNEL32!GetLastError` at `0x18000ee08`
- `KERNEL32!GetLastError` at `0x18000ee29`
- `KERNEL32!GetLastError` at `0x18000eebf`
- `KERNEL32!FlushFileBuffers` at `0x18000eeab`
- `KERNEL32!FlushFileBuffers` at `0x18000eeab`
- `KERNEL32!CloseHandle` at `0x18000eeb4`
- `KERNEL32!CloseHandle` at `0x18000eeb4`
- `KERNEL32!WritePrivateProfileStructW` at `0x18000edfe`
- `KERNEL32!WritePrivateProfileStructW` at `0x18000edfe`
- `KERNEL32!CreateFileW` at `0x18000ee99`
- `KERNEL32!CreateFileW` at `0x18000ee99`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000ee68`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000ee68`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SrSettings::CSrSettings::SetResourceString(
        SrSettings::CSrSettings *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *lpStruct)
{
  const WCHAR *v9; // r9
  int v10; // esi
  const wchar_t *v11; // r8
  __int64 v13; // r8
  __int64 v14; // rax
  UINT v15; // r15d
  int v16; // eax
  signed int LastError; // eax
  unsigned int v18; // ebx
  HANDLE FileW; // rax
  void *v20; // rbx
  LPCWSTR szFile; // [rsp+20h] [rbp-81h]
  LPCWSTR szFilea; // [rsp+20h] [rbp-81h]
  LPCWSTR szFileb; // [rsp+20h] [rbp-81h]
  unsigned __int16 *v24[2]; // [rsp+40h] [rbp-61h] BYREF
  _WORD v25[8]; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int16 v26[32]; // [rsp+60h] [rbp-41h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  v24[0] = v25;
  v24[1] = v25;
  v25[0] = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( !lpStruct )
  {
    v9 = a4;
    if ( !a4 )
      v9 = &Default;
    SrSettings::CSrSettings::Trace(this, 0, L"Clear resource string [%s] in [%s]", v9, a3);
    v10 = SrSettings::CSrSettings::SetSetting(this, a2, a3, a4, 0);
    if ( v10 < 0 )
    {
      v11 = L"Failed to clear resource string %s. Error: 0x%08x";
LABEL_8:
      LODWORD(szFile) = v10;
      SrSettings::CSrSettings::Trace(this, 2, v11, a4, szFile);
      goto LABEL_9;
    }
  }
  if ( a4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a4[v13] );
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v24,
                           a4) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to assign setting name %s", a4);
LABEL_19:
    if ( v24[0] != v25 )
      operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942408LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v24,
                           L"_Length") )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to append _Length to setting name %s", a4);
    goto LABEL_19;
  }
  v14 = -1;
  do
    ++v14;
  while ( lpStruct[v14] );
  v15 = 2 * v14 + 2;
  v16 = StringCchPrintfW(v26, 0x20u, L"%u", v15);
  v10 = v16;
  if ( v16 < 0 )
  {
    LODWORD(szFile) = v16;
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to convert DWORD [%u] to string. Error: 0x%08x", v15, szFile);
    goto LABEL_9;
  }
  v10 = SrSettings::CSrSettings::SetSetting(this, a2, a3, v24[0], v26);
  if ( v10 < 0 )
  {
    v11 = L"Failed to set length of setting %s. Error: 0x%08x";
    goto LABEL_8;
  }
  if ( WritePrivateProfileStructW(a3, a4, lpStruct, v15, a2) )
  {
    WritePrivateProfileStringW(0, 0, 0, 0);
    FileW = CreateFileW(a2, 0x40000000u, 1u, 0, 4u, 0x80000000, 0);
    v20 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LODWORD(szFileb) = GetLastError();
      SrSettings::CSrSettings::Trace(this, 1, L"Failed to flush setting file %s. Error: %d", a2, szFileb);
    }
    else
    {
      FlushFileBuffers(FileW);
      CloseHandle(v20);
    }
LABEL_9:
    if ( v24[0] != v25 )
      operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v10;
  }
  LODWORD(szFilea) = GetLastError();
  SrSettings::CSrSettings::Trace(this, 2, L"Failed to set setting %s. Error: %d", a4, szFilea);
  LastError = GetLastError();
  v18 = LastError;
  if ( LastError > 0 )
    v18 = (unsigned __int16)LastError | 0x80070000;
  if ( v24[0] != v25 )
    operator delete(v24[0], (const struct std::nothrow_t *)&std::nothrow);
  return v18;
}

```

## disassembly

```asm
0x18000ebf8  push    rbp
0x18000ebfa  push    rbx
0x18000ebfb  push    rsi
0x18000ebfc  push    rdi
0x18000ebfd  push    r12
0x18000ebff  push    r13
0x18000ec01  push    r14
0x18000ec03  push    r15
0x18000ec05  lea     rbp, [rsp-17h]
0x18000ec0a  sub     rsp, 0B8h
0x18000ec11  mov     rax, cs:__security_cookie
0x18000ec18  xor     rax, rsp
0x18000ec1b  mov     [rbp+4Fh+var_50], rax
0x18000ec1f  mov     rbx, r9
0x18000ec22  mov     r12, r8
0x18000ec25  mov     r14, rdx
0x18000ec28  mov     rdi, rcx
0x18000ec2b  mov     r13, [rbp+4Fh+lpStruct]
0x18000ec2f  xor     r15d, r15d
0x18000ec32  test    rdx, rdx
0x18000ec35  jz      loc_18000EEDB
0x18000ec3b  test    r8, r8
0x18000ec3e  jz      loc_18000EEDB
0x18000ec44  lea     rax, [rbp+4Fh+var_A0]
0x18000ec48  mov     [rbp+4Fh+var_B0], rax
0x18000ec4c  lea     rax, [rbp+4Fh+var_A0]
0x18000ec50  mov     [rbp+4Fh+var_A8], rax
0x18000ec54  mov     [rbp+4Fh+var_A0], r15w
0x18000ec59  xor     edx, edx; Val
0x18000ec5b  lea     r8d, [r15+40h]; Size
0x18000ec5f  lea     rcx, [rbp+4Fh+var_90]; void *
0x18000ec63  call    memset_0
0x18000ec68  test    r13, r13
0x18000ec6b  jnz     short loc_18000ECEC
0x18000ec6d  lea     rax, Default
0x18000ec74  mov     r9, rbx
0x18000ec77  test    rbx, rbx
0x18000ec7a  cmovz   r9, rax
0x18000ec7e  mov     [rsp+0F0h+szFile], r12
0x18000ec83  lea     r8, aClearResourceS; "Clear resource string [%s] in [%s]"
0x18000ec8a  xor     edx, edx
0x18000ec8c  mov     rcx, rdi
0x18000ec8f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ec94  mov     [rsp+0F0h+szFile], r15; unsigned __int16 *
0x18000ec99  mov     r9, rbx; unsigned __int16 *
0x18000ec9c  mov     r8, r12; unsigned __int16 *
0x18000ec9f  mov     rdx, r14; unsigned __int16 *
0x18000eca2  mov     rcx, rdi; this
0x18000eca5  call    ?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)
0x18000ecaa  mov     esi, eax
0x18000ecac  test    eax, eax
0x18000ecae  jns     short loc_18000ECEC
0x18000ecb0  lea     r8, aFailedToClearR; "Failed to clear resource string %s. Err"...
0x18000ecb7  mov     r9, rbx
0x18000ecba  mov     dword ptr [rsp+0F0h+szFile], esi
0x18000ecbe  mov     edx, 2
0x18000ecc3  mov     rcx, rdi
0x18000ecc6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000eccb  nop
0x18000eccc  lea     rax, [rbp+4Fh+var_A0]
0x18000ecd0  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18000ecd4  cmp     rcx, rax
0x18000ecd7  jz      short loc_18000ECE5
0x18000ecd9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ece0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ece5  mov     eax, esi
0x18000ece7  jmp     loc_18000EEE0
0x18000ecec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ecf0  test    rbx, rbx
0x18000ecf3  jz      short loc_18000ED04
0x18000ecf5  mov     r8, rsi
0x18000ecf8  inc     r8
0x18000ecfb  cmp     [rbx+r8*2], r15w
0x18000ed00  jnz     short loc_18000ECF8
0x18000ed02  jmp     short loc_18000ED07
0x18000ed04  mov     r8, r15
0x18000ed07  mov     rdx, rbx
0x18000ed0a  lea     rcx, [rbp+4Fh+var_B0]
0x18000ed0e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000ed13  test    al, al
0x18000ed15  jnz     short loc_18000ED20
0x18000ed17  lea     r8, aFailedToAssign_3; "Failed to assign setting name %s"
0x18000ed1e  jmp     short loc_18000ED3B
0x18000ed20  lea     rdx, aLength; "_Length"
0x18000ed27  lea     rcx, [rbp+4Fh+var_B0]
0x18000ed2b  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000ed30  test    al, al
0x18000ed32  jnz     short loc_18000ED6F
0x18000ed34  lea     r8, aFailedToAppend_7; "Failed to append _Length to setting nam"...
0x18000ed3b  mov     r9, rbx
0x18000ed3e  mov     edx, 2
0x18000ed43  mov     rcx, rdi
0x18000ed46  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ed4b  nop
0x18000ed4c  lea     rax, [rbp+4Fh+var_A0]
0x18000ed50  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18000ed54  cmp     rcx, rax
0x18000ed57  jz      short loc_18000ED65
0x18000ed59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ed60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ed65  mov     eax, 80070008h
0x18000ed6a  jmp     loc_18000EEE0
0x18000ed6f  mov     rax, rsi
0x18000ed72  inc     rax
0x18000ed75  cmp     [r13+rax*2+0], r15w
0x18000ed7b  jnz     short loc_18000ED72
0x18000ed7d  lea     r15d, ds:2[rax*2]
0x18000ed85  mov     r9d, r15d
0x18000ed88  lea     r8, aU_0; "%u"
0x18000ed8f  mov     edx, 20h ; ' '; unsigned __int64
0x18000ed94  lea     rcx, [rbp+4Fh+var_90]; unsigned __int16 *
0x18000ed98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ed9d  mov     esi, eax
0x18000ed9f  mov     rcx, rdi; this
0x18000eda2  test    eax, eax
0x18000eda4  jns     short loc_18000EDC3
0x18000eda6  mov     dword ptr [rsp+0F0h+szFile], eax
0x18000edaa  mov     r9d, r15d
0x18000edad  lea     r8, aFailedToConver; "Failed to convert DWORD [%u] to string."...
0x18000edb4  mov     edx, 2
0x18000edb9  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000edbe  jmp     loc_18000ECCC
0x18000edc3  lea     rax, [rbp+4Fh+var_90]
0x18000edc7  mov     [rsp+0F0h+szFile], rax; unsigned __int16 *
0x18000edcc  mov     r9, [rbp+4Fh+var_B0]; unsigned __int16 *
0x18000edd0  mov     r8, r12; unsigned __int16 *
0x18000edd3  mov     rdx, r14; unsigned __int16 *
0x18000edd6  call    ?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)
0x18000eddb  mov     esi, eax
0x18000eddd  test    eax, eax
0x18000eddf  jns     short loc_18000EDED
0x18000ede1  lea     r8, aFailedToSetLen; "Failed to set length of setting %s. Err"...
0x18000ede8  jmp     loc_18000ECB7
0x18000eded  mov     [rsp+0F0h+szFile], r14; szFile
0x18000edf2  mov     r9d, r15d; uSizeStruct
0x18000edf5  mov     r8, r13; lpStruct
0x18000edf8  mov     rdx, rbx; lpszKey
0x18000edfb  mov     rcx, r12; lpszSection
0x18000edfe  call    cs:__imp_WritePrivateProfileStructW
0x18000ee04  test    eax, eax
0x18000ee06  jnz     short loc_18000EE5E
0x18000ee08  call    cs:__imp_GetLastError
0x18000ee0e  mov     dword ptr [rsp+0F0h+szFile], eax
0x18000ee12  mov     r9, rbx
0x18000ee15  lea     r8, aFailedToSetSet; "Failed to set setting %s. Error: %d"
0x18000ee1c  mov     edx, 2
0x18000ee21  mov     rcx, rdi
0x18000ee24  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ee29  call    cs:__imp_GetLastError
0x18000ee2f  mov     ebx, eax
0x18000ee31  test    eax, eax
0x18000ee33  jle     short loc_18000EE3E
0x18000ee35  movzx   ebx, ax
0x18000ee38  or      ebx, 80070000h
0x18000ee3e  lea     rax, [rbp+4Fh+var_A0]
0x18000ee42  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18000ee46  cmp     rcx, rax
0x18000ee49  jz      short loc_18000EE57
0x18000ee4b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ee52  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ee57  mov     eax, ebx
0x18000ee59  jmp     loc_18000EEE0
0x18000ee5e  xor     r9d, r9d; lpFileName
0x18000ee61  xor     r8d, r8d; lpString
0x18000ee64  xor     edx, edx; lpKeyName
0x18000ee66  xor     ecx, ecx; lpAppName
0x18000ee68  call    cs:__imp_WritePrivateProfileStringW
0x18000ee6e  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18000ee77  mov     [rsp+0F0h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18000ee7f  mov     dword ptr [rsp+0F0h+szFile], 4; dwCreationDisposition
0x18000ee87  xor     r9d, r9d; lpSecurityAttributes
0x18000ee8a  lea     r15d, [r9+1]
0x18000ee8e  mov     r8d, r15d; dwShareMode
0x18000ee91  mov     edx, 40000000h; dwDesiredAccess
0x18000ee96  mov     rcx, r14; lpFileName
0x18000ee99  call    cs:__imp_CreateFileW
0x18000ee9f  mov     rbx, rax
0x18000eea2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000eea6  jz      short loc_18000EEBF
0x18000eea8  mov     rcx, rax; hFile
0x18000eeab  call    cs:__imp_FlushFileBuffers
0x18000eeb1  mov     rcx, rbx; hObject
0x18000eeb4  call    cs:__imp_CloseHandle
0x18000eeba  jmp     loc_18000ECCC
0x18000eebf  call    cs:__imp_GetLastError
0x18000eec5  mov     dword ptr [rsp+0F0h+szFile], eax
0x18000eec9  mov     r9, r14
0x18000eecc  lea     r8, aFailedToFlushS; "Failed to flush setting file %s. Error:"...
0x18000eed3  mov     edx, r15d
0x18000eed6  jmp     loc_18000ECC3
0x18000eedb  mov     eax, 80070057h
0x18000eee0  mov     rcx, [rbp+4Fh+var_50]
0x18000eee4  xor     rcx, rsp; StackCookie
0x18000eee7  call    __security_check_cookie
0x18000eeec  add     rsp, 0B8h
0x18000eef3  pop     r15
0x18000eef5  pop     r14
0x18000eef7  pop     r13
0x18000eef9  pop     r12
0x18000eefb  pop     rdi
0x18000eefc  pop     rsi
0x18000eefd  pop     rbx
0x18000eefe  pop     rbp
0x18000eeff  retn
```
