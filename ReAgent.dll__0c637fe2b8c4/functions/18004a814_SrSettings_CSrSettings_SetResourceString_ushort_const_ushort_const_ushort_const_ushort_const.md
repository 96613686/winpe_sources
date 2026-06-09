# SrSettings::CSrSettings::SetResourceString(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18004a814`
- end: `0x18004aac5`
- name: `?SetResourceString@CSrSettings@SrSettings@@AEAAJPEBG000@Z`
- size: `689`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *lpStruct)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18004bfa0`

## callees

- `0x18000c6f0`
- `0x18004a814`
- `0x18004aacc`
- `0x18004c0e8`
- `0x18004c44c`
- `0x18004c5c8`
- `0x18004c6a0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004a9e4`
- `KERNEL32!GetLastError` at `0x18004aa05`
- `KERNEL32!GetLastError` at `0x18004aa84`
- `KERNEL32!GetLastError` at `0x18004a9e4`
- `KERNEL32!GetLastError` at `0x18004aa05`
- `KERNEL32!GetLastError` at `0x18004aa84`
- `KERNEL32!WritePrivateProfileStructW` at `0x18004a9da`
- `KERNEL32!WritePrivateProfileStructW` at `0x18004a9da`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004aa30`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004aa30`
- `KERNEL32!CreateFileW` at `0x18004aa61`
- `KERNEL32!CreateFileW` at `0x18004aa61`
- `KERNEL32!CloseHandle` at `0x18004aa7c`
- `KERNEL32!CloseHandle` at `0x18004aa7c`
- `KERNEL32!FlushFileBuffers` at `0x18004aa73`
- `KERNEL32!FlushFileBuffers` at `0x18004aa73`

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
  int v10; // eax
  unsigned int v11; // ebx
  const wchar_t *v12; // r8
  __int64 v13; // rax
  UINT v14; // r12d
  int v15; // eax
  int v16; // eax
  signed int LastError; // eax
  HANDLE FileW; // rax
  void *v20; // rsi
  LPCWSTR szFile; // [rsp+20h] [rbp-91h]
  LPCWSTR szFilea; // [rsp+20h] [rbp-91h]
  LPCWSTR szFileb; // [rsp+20h] [rbp-91h]
  unsigned __int16 *v24[2]; // [rsp+40h] [rbp-71h] BYREF
  _WORD v25[8]; // [rsp+50h] [rbp-61h] BYREF
  __int64 v26; // [rsp+60h] [rbp-51h]
  unsigned __int16 v27[32]; // [rsp+70h] [rbp-41h] BYREF

  v26 = -2;
  if ( a2 && a3 )
  {
    v24[0] = v25;
    v24[1] = v25;
    v25[0] = 0;
    memset_0(v27, 0, sizeof(v27));
    if ( !lpStruct )
    {
      v9 = a4;
      if ( !a4 )
        v9 = &cchOriginalDestLength;
      SrSettings::CSrSettings::Trace(this, 0, L"Clear resource string [%s] in [%s]", v9, a3);
      v10 = SrSettings::CSrSettings::SetSetting(this, a2, a3, a4, 0);
      v11 = v10;
      if ( v10 < 0 )
      {
        LODWORD(szFile) = v10;
        v12 = L"Failed to clear resource string %s. Error: 0x%08x";
LABEL_19:
        SrSettings::CSrSettings::Trace(this, 2, v12, a4, szFile);
        goto LABEL_25;
      }
    }
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            v24,
                            a4) )
    {
      if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              v24,
                              L"_Length",
                              7) )
      {
        v13 = -1;
        do
          ++v13;
        while ( lpStruct[v13] );
        v14 = 2 * v13 + 2;
        v15 = StringCchPrintfW(v27, 0x20u, L"%u", v14);
        v11 = v15;
        if ( v15 >= 0 )
        {
          v16 = SrSettings::CSrSettings::SetSetting(this, a2, a3, v24[0], v27);
          v11 = v16;
          if ( v16 >= 0 )
          {
            if ( WritePrivateProfileStructW(a3, a4, lpStruct, v14, a2) )
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
            }
            else
            {
              LODWORD(szFilea) = GetLastError();
              SrSettings::CSrSettings::Trace(this, 2, L"Failed to set setting %s. Error: %d", a4, szFilea);
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              v11 = LastError;
            }
            goto LABEL_25;
          }
          LODWORD(szFile) = v16;
          v12 = L"Failed to set length of setting %s. Error: 0x%08x";
          goto LABEL_19;
        }
        LODWORD(szFile) = v15;
        SrSettings::CSrSettings::Trace(this, 2, L"Failed to convert DWORD [%u] to string. Error: 0x%08x", v14, szFile);
LABEL_25:
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)v24);
        return v11;
      }
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to append _Length to setting name %s", a4);
    }
    else
    {
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to assign setting name %s", a4);
    }
    v11 = -2147024888;
    goto LABEL_25;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18004a814  push    rbp
0x18004a816  push    rbx
0x18004a817  push    rsi
0x18004a818  push    rdi
0x18004a819  push    r12
0x18004a81b  push    r13
0x18004a81d  push    r14
0x18004a81f  push    r15
0x18004a821  lea     rbp, [rsp-17h]
0x18004a826  sub     rsp, 0C8h
0x18004a82d  mov     [rbp+4Fh+var_A0], 0FFFFFFFFFFFFFFFEh
0x18004a835  mov     rax, cs:__security_cookie
0x18004a83c  xor     rax, rsp
0x18004a83f  mov     [rbp+4Fh+var_50], rax
0x18004a843  mov     rsi, r9
0x18004a846  mov     r15, r8
0x18004a849  mov     r14, rdx
0x18004a84c  mov     rdi, rcx
0x18004a84f  mov     r13, [rbp+4Fh+lpStruct]
0x18004a853  xor     r12d, r12d
0x18004a856  test    rdx, rdx
0x18004a859  jz      loc_18004AAA0
0x18004a85f  test    r8, r8
0x18004a862  jz      loc_18004AAA0
0x18004a868  lea     rax, [rbp+4Fh+var_B0]
0x18004a86c  mov     [rbp+4Fh+var_C0], rax
0x18004a870  lea     rax, [rbp+4Fh+var_B0]
0x18004a874  mov     [rbp+4Fh+var_B8], rax
0x18004a878  mov     [rbp+4Fh+var_B0], r12w
0x18004a87d  xor     edx, edx; Val
0x18004a87f  lea     r8d, [r12+40h]; Size
0x18004a884  lea     rcx, [rbp+4Fh+var_90]; void *
0x18004a888  call    memset_0
0x18004a88d  test    r13, r13
0x18004a890  jnz     short loc_18004A8E5
0x18004a892  lea     rax, cchOriginalDestLength
0x18004a899  mov     r9, rsi
0x18004a89c  test    rsi, rsi
0x18004a89f  cmovz   r9, rax
0x18004a8a3  mov     [rsp+100h+szFile], r15
0x18004a8a8  lea     r8, aClearResourceS; "Clear resource string [%s] in [%s]"
0x18004a8af  xor     edx, edx
0x18004a8b1  mov     rcx, rdi
0x18004a8b4  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a8b9  mov     [rsp+100h+szFile], r12; unsigned __int16 *
0x18004a8be  mov     r9, rsi; unsigned __int16 *
0x18004a8c1  mov     r8, r15; unsigned __int16 *
0x18004a8c4  mov     rdx, r14; unsigned __int16 *
0x18004a8c7  mov     rcx, rdi; this
0x18004a8ca  call    ?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)
0x18004a8cf  mov     ebx, eax
0x18004a8d1  test    eax, eax
0x18004a8d3  jns     short loc_18004A8E5
0x18004a8d5  mov     dword ptr [rsp+100h+szFile], eax
0x18004a8d9  lea     r8, aFailedToClearR_0; "Failed to clear resource string %s. Err"...
0x18004a8e0  jmp     loc_18004A9B7
0x18004a8e5  mov     rdx, rsi
0x18004a8e8  lea     rcx, [rbp+4Fh+var_C0]
0x18004a8ec  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18004a8f1  test    al, al
0x18004a8f3  jnz     short loc_18004A916
0x18004a8f5  lea     r8, aFailedToAssign_3; "Failed to assign setting name %s"
0x18004a8fc  mov     r9, rsi
0x18004a8ff  mov     edx, 2
0x18004a904  mov     rcx, rdi
0x18004a907  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a90c  mov     ebx, 80070008h
0x18004a911  jmp     loc_18004AA19
0x18004a916  mov     r8d, 7
0x18004a91c  lea     rdx, aLength; "_Length"
0x18004a923  lea     rcx, [rbp+4Fh+var_C0]
0x18004a927  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18004a92c  test    al, al
0x18004a92e  jnz     short loc_18004A939
0x18004a930  lea     r8, aFailedToAppend_13; "Failed to append _Length to setting nam"...
0x18004a937  jmp     short loc_18004A8FC
0x18004a939  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004a93d  inc     rax
0x18004a940  cmp     [r13+rax*2+0], r12w
0x18004a946  jnz     short loc_18004A93D
0x18004a948  lea     r12d, ds:2[rax*2]
0x18004a950  mov     r9d, r12d
0x18004a953  lea     r8, aU; "%u"
0x18004a95a  mov     edx, 20h ; ' '; unsigned __int64
0x18004a95f  lea     rcx, [rbp+4Fh+var_90]; unsigned __int16 *
0x18004a963  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a968  mov     ebx, eax
0x18004a96a  mov     rcx, rdi; this
0x18004a96d  test    eax, eax
0x18004a96f  jns     short loc_18004A98E
0x18004a971  mov     dword ptr [rsp+100h+szFile], eax
0x18004a975  mov     r9d, r12d
0x18004a978  lea     r8, aFailedToConver_3; "Failed to convert DWORD [%u] to string."...
0x18004a97f  mov     edx, 2
0x18004a984  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a989  jmp     loc_18004AA19
0x18004a98e  lea     rax, [rbp+4Fh+var_90]
0x18004a992  mov     [rsp+100h+szFile], rax; unsigned __int16 *
0x18004a997  mov     r9, [rbp+4Fh+var_C0]; unsigned __int16 *
0x18004a99b  mov     r8, r15; unsigned __int16 *
0x18004a99e  mov     rdx, r14; unsigned __int16 *
0x18004a9a1  call    ?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)
0x18004a9a6  mov     ebx, eax
0x18004a9a8  test    eax, eax
0x18004a9aa  jns     short loc_18004A9C9
0x18004a9ac  mov     dword ptr [rsp+100h+szFile], eax
0x18004a9b0  lea     r8, aFailedToSetLen; "Failed to set length of setting %s. Err"...
0x18004a9b7  mov     r9, rsi
0x18004a9ba  mov     edx, 2
0x18004a9bf  mov     rcx, rdi
0x18004a9c2  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a9c7  jmp     short loc_18004AA19
0x18004a9c9  mov     [rsp+100h+szFile], r14; szFile
0x18004a9ce  mov     r9d, r12d; uSizeStruct
0x18004a9d1  mov     r8, r13; lpStruct
0x18004a9d4  mov     rdx, rsi; lpszKey
0x18004a9d7  mov     rcx, r15; lpszSection
0x18004a9da  call    cs:__imp_WritePrivateProfileStructW
0x18004a9e0  test    eax, eax
0x18004a9e2  jnz     short loc_18004AA26
0x18004a9e4  call    cs:__imp_GetLastError
0x18004a9ea  mov     dword ptr [rsp+100h+szFile], eax
0x18004a9ee  mov     r9, rsi
0x18004a9f1  lea     r8, aFailedToSetSet; "Failed to set setting %s. Error: %d"
0x18004a9f8  mov     edx, 2
0x18004a9fd  mov     rcx, rdi
0x18004aa00  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004aa05  call    cs:__imp_GetLastError
0x18004aa0b  test    eax, eax
0x18004aa0d  jle     short loc_18004AA17
0x18004aa0f  movzx   eax, ax
0x18004aa12  or      eax, 80070000h
0x18004aa17  mov     ebx, eax
0x18004aa19  lea     rcx, [rbp+4Fh+var_C0]
0x18004aa1d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004aa22  mov     eax, ebx
0x18004aa24  jmp     short loc_18004AAA5
0x18004aa26  xor     r9d, r9d; lpFileName
0x18004aa29  xor     r8d, r8d; lpString
0x18004aa2c  xor     edx, edx; lpKeyName
0x18004aa2e  xor     ecx, ecx; lpAppName
0x18004aa30  call    cs:__imp_WritePrivateProfileStringW
0x18004aa36  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x18004aa3f  mov     [rsp+100h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18004aa47  mov     dword ptr [rsp+100h+szFile], 4; dwCreationDisposition
0x18004aa4f  xor     r9d, r9d; lpSecurityAttributes
0x18004aa52  lea     r15d, [r9+1]
0x18004aa56  mov     r8d, r15d; dwShareMode
0x18004aa59  mov     edx, 40000000h; dwDesiredAccess
0x18004aa5e  mov     rcx, r14; lpFileName
0x18004aa61  call    cs:__imp_CreateFileW
0x18004aa67  mov     rsi, rax
0x18004aa6a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004aa6e  jz      short loc_18004AA84
0x18004aa70  mov     rcx, rax; hFile
0x18004aa73  call    cs:__imp_FlushFileBuffers
0x18004aa79  mov     rcx, rsi; hObject
0x18004aa7c  call    cs:__imp_CloseHandle
0x18004aa82  jmp     short loc_18004AA19
0x18004aa84  call    cs:__imp_GetLastError
0x18004aa8a  mov     dword ptr [rsp+100h+szFile], eax
0x18004aa8e  mov     r9, r14
0x18004aa91  lea     r8, aFailedToFlushS; "Failed to flush setting file %s. Error:"...
0x18004aa98  mov     edx, r15d
0x18004aa9b  jmp     loc_18004A9BF
0x18004aaa0  mov     eax, 80070057h
0x18004aaa5  mov     rcx, [rbp+4Fh+var_50]
0x18004aaa9  xor     rcx, rsp; StackCookie
0x18004aaac  call    __security_check_cookie
0x18004aab1  add     rsp, 0C8h
0x18004aab8  pop     r15
0x18004aaba  pop     r14
0x18004aabc  pop     r13
0x18004aabe  pop     r12
0x18004aac0  pop     rdi
0x18004aac1  pop     rsi
0x18004aac2  pop     rbx
0x18004aac3  pop     rbp
0x18004aac4  retn
```
