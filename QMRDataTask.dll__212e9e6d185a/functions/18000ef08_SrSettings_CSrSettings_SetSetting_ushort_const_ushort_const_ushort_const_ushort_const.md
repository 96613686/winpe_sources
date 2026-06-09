# SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000ef08`
- end: `0x18000f162`
- name: `?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z`
- size: `602`
- prototype: `int(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180006e00`
- `0x180006eb0`
- `0x180006f40`
- `0x180006fe0`
- `0x18000b290`
- `0x18000ebf8`
- `0x18000f170`
- `0x18000f1f0`
- `0x180010400`

## callees

- `0x180002178`
- `0x18000ef08`
- `0x180010a0c`
- `0x180011b60`
- `0x180011c80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ef9a`
- `KERNEL32!GetLastError` at `0x18000efbb`
- `KERNEL32!GetLastError` at `0x18000f063`
- `KERNEL32!GetLastError` at `0x18000f084`
- `KERNEL32!GetLastError` at `0x18000f12d`
- `KERNEL32!GetLastError` at `0x18000ef9a`
- `KERNEL32!GetLastError` at `0x18000efbb`
- `KERNEL32!GetLastError` at `0x18000f063`
- `KERNEL32!GetLastError` at `0x18000f084`
- `KERNEL32!GetLastError` at `0x18000f12d`
- `KERNEL32!FlushFileBuffers` at `0x18000f11c`
- `KERNEL32!FlushFileBuffers` at `0x18000f11c`
- `KERNEL32!CloseHandle` at `0x18000f125`
- `KERNEL32!CloseHandle` at `0x18000f125`
- `KERNEL32!CreateFileW` at `0x18000f10a`
- `KERNEL32!CreateFileW` at `0x18000f10a`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000ef8c`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000f059`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000f0dc`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000ef8c`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000f059`
- `KERNEL32!WritePrivateProfileStringW` at `0x18000f0dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SrSettings::CSrSettings::SetSetting(
        SrSettings::CSrSettings *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const WCHAR *v5; // rsi
  int result; // eax
  signed int LastError; // eax
  unsigned int v11; // ebx
  HANDLE FileW; // rax
  void *v13; // rsi
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-40h]
  LPCWSTR lpString[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v18[8]; // [rsp+50h] [rbp-10h] BYREF

  v5 = a4;
  if ( *((_BYTE *)this + 3944) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Cannot set setting in UseInWinRE mode");
    return -2147024891;
  }
  if ( !a2 || !a3 )
    return -2147024809;
  if ( !a5 )
  {
    if ( !a4 )
      a4 = &Default;
    SrSettings::CSrSettings::Trace(this, 0, L"Clear setting [%s] in [%s]", a4, a3);
    if ( !WritePrivateProfileStringW(a3, v5, 0, a2) )
    {
      dwCreationDisposition[0] = GetLastError();
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to set setting %s. Error: %d",
        v5,
        *(_QWORD *)dwCreationDisposition);
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    goto LABEL_25;
  }
  lpString[0] = v18;
  lpString[1] = v18;
  v18[0] = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpString,
                          L"\"")
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          lpString,
                          a5)
    && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          lpString,
                          L"\"") )
  {
    if ( WritePrivateProfileStringW(a3, v5, lpString[0], a2) )
    {
      if ( lpString[0] != v18 )
        operator delete((void *)lpString[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_25:
      WritePrivateProfileStringW(0, 0, 0, 0);
      FileW = CreateFileW(a2, 0x40000000u, 1u, 0, 4u, 0x80000000, 0);
      v13 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        dwCreationDispositiona[0] = GetLastError();
        SrSettings::CSrSettings::Trace(
          this,
          1,
          L"Failed to flush setting file %s. Error: %d",
          a2,
          *(_QWORD *)dwCreationDispositiona);
      }
      else
      {
        FlushFileBuffers(FileW);
        CloseHandle(v13);
      }
      return 0;
    }
    dwCreationDispositionb = GetLastError();
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to set setting %s. Error: %d", v5, dwCreationDispositionb);
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( lpString[0] != v18 )
      operator delete((void *)lpString[0], (const struct std::nothrow_t *)&std::nothrow);
    return v11;
  }
  else
  {
    if ( lpString[0] != v18 )
      operator delete((void *)lpString[0], (const struct std::nothrow_t *)&std::nothrow);
    return -2147024888;
  }
}

```

## disassembly

```asm
0x18000ef08  push    rbp
0x18000ef0a  push    rbx
0x18000ef0b  push    rsi
0x18000ef0c  push    rdi
0x18000ef0d  push    r14
0x18000ef0f  mov     rbp, rsp
0x18000ef12  sub     rsp, 60h
0x18000ef16  mov     rsi, r9
0x18000ef19  mov     r14, r8
0x18000ef1c  mov     rdi, rdx
0x18000ef1f  mov     rbx, rcx
0x18000ef22  cmp     byte ptr [rcx+0F68h], 0
0x18000ef29  jz      short loc_18000EF46
0x18000ef2b  lea     r8, aCannotSetSetti; "Cannot set setting in UseInWinRE mode"
0x18000ef32  mov     edx, 2
0x18000ef37  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ef3c  mov     eax, 80070005h
0x18000ef41  jmp     loc_18000F157
0x18000ef46  test    rdi, rdi
0x18000ef49  jz      loc_18000F152
0x18000ef4f  test    r14, r14
0x18000ef52  jz      loc_18000F152
0x18000ef58  cmp     [rbp+arg_20], 0
0x18000ef5d  jnz     short loc_18000EFD6
0x18000ef5f  lea     rax, Default
0x18000ef66  test    rsi, rsi
0x18000ef69  cmovz   r9, rax
0x18000ef6d  mov     qword ptr [rsp+60h+dwCreationDisposition], r14
0x18000ef72  lea     r8, aClearSettingSI; "Clear setting [%s] in [%s]"
0x18000ef79  xor     edx, edx
0x18000ef7b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000ef80  mov     r9, rdi; lpFileName
0x18000ef83  xor     r8d, r8d; lpString
0x18000ef86  mov     rdx, rsi; lpKeyName
0x18000ef89  mov     rcx, r14; lpAppName
0x18000ef8c  call    cs:__imp_WritePrivateProfileStringW
0x18000ef92  test    eax, eax
0x18000ef94  jnz     loc_18000F0D2
0x18000ef9a  call    cs:__imp_GetLastError
0x18000efa0  mov     [rsp+60h+dwCreationDisposition], eax
0x18000efa4  mov     r9, rsi
0x18000efa7  lea     r8, aFailedToSetSet; "Failed to set setting %s. Error: %d"
0x18000efae  mov     edx, 2
0x18000efb3  mov     rcx, rbx
0x18000efb6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000efbb  call    cs:__imp_GetLastError
0x18000efc1  test    eax, eax
0x18000efc3  jle     loc_18000F157
0x18000efc9  movzx   eax, ax
0x18000efcc  or      eax, 80070000h
0x18000efd1  jmp     loc_18000F157
0x18000efd6  lea     rax, [rbp+var_10]
0x18000efda  mov     [rbp+lpString], rax
0x18000efde  lea     rax, [rbp+var_10]
0x18000efe2  mov     [rbp+var_18], rax
0x18000efe6  xor     eax, eax
0x18000efe8  mov     [rbp+var_10], ax
0x18000efec  lea     r8d, [rax+1]
0x18000eff0  lea     rdx, asc_18001D4F8; "\""
0x18000eff7  lea     rcx, [rbp+lpString]
0x18000effb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000f000  test    al, al
0x18000f002  jz      short loc_18000F029
0x18000f004  mov     rdx, [rbp+arg_20]
0x18000f008  lea     rcx, [rbp+lpString]
0x18000f00c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000f011  test    al, al
0x18000f013  jz      short loc_18000F029
0x18000f015  lea     rdx, asc_18001D4F8; "\""
0x18000f01c  lea     rcx, [rbp+lpString]
0x18000f020  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000f025  test    al, al
0x18000f027  jnz     short loc_18000F04C
0x18000f029  lea     rax, [rbp+var_10]
0x18000f02d  mov     rcx, [rbp+lpString]; void *
0x18000f031  cmp     rcx, rax
0x18000f034  jz      short loc_18000F042
0x18000f036  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f03d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f042  mov     eax, 80070008h
0x18000f047  jmp     loc_18000F157
0x18000f04c  mov     r9, rdi; lpFileName
0x18000f04f  mov     r8, [rbp+lpString]; lpString
0x18000f053  mov     rdx, rsi; lpKeyName
0x18000f056  mov     rcx, r14; lpAppName
0x18000f059  call    cs:__imp_WritePrivateProfileStringW
0x18000f05f  test    eax, eax
0x18000f061  jnz     short loc_18000F0B9
0x18000f063  call    cs:__imp_GetLastError
0x18000f069  mov     [rsp+60h+dwCreationDisposition], eax
0x18000f06d  mov     r9, rsi
0x18000f070  lea     r8, aFailedToSetSet; "Failed to set setting %s. Error: %d"
0x18000f077  mov     edx, 2
0x18000f07c  mov     rcx, rbx
0x18000f07f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f084  call    cs:__imp_GetLastError
0x18000f08a  mov     ebx, eax
0x18000f08c  test    eax, eax
0x18000f08e  jle     short loc_18000F099
0x18000f090  movzx   ebx, ax
0x18000f093  or      ebx, 80070000h
0x18000f099  lea     rax, [rbp+var_10]
0x18000f09d  mov     rcx, [rbp+lpString]; void *
0x18000f0a1  cmp     rcx, rax
0x18000f0a4  jz      short loc_18000F0B2
0x18000f0a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f0ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f0b2  mov     eax, ebx
0x18000f0b4  jmp     loc_18000F157
0x18000f0b9  lea     rax, [rbp+var_10]
0x18000f0bd  mov     rcx, [rbp+lpString]; void *
0x18000f0c1  cmp     rcx, rax
0x18000f0c4  jz      short loc_18000F0D2
0x18000f0c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f0cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f0d2  xor     r9d, r9d; lpFileName
0x18000f0d5  xor     r8d, r8d; lpString
0x18000f0d8  xor     edx, edx; lpKeyName
0x18000f0da  xor     ecx, ecx; lpAppName
0x18000f0dc  call    cs:__imp_WritePrivateProfileStringW
0x18000f0e2  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18000f0eb  mov     [rsp+60h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18000f0f3  mov     [rsp+60h+dwCreationDisposition], 4; dwCreationDisposition
0x18000f0fb  xor     r9d, r9d; lpSecurityAttributes
0x18000f0fe  mov     edx, 40000000h; dwDesiredAccess
0x18000f103  lea     r8d, [r9+1]; dwShareMode
0x18000f107  mov     rcx, rdi; lpFileName
0x18000f10a  call    cs:__imp_CreateFileW
0x18000f110  mov     rsi, rax
0x18000f113  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f117  jz      short loc_18000F12D
0x18000f119  mov     rcx, rax; hFile
0x18000f11c  call    cs:__imp_FlushFileBuffers
0x18000f122  mov     rcx, rsi; hObject
0x18000f125  call    cs:__imp_CloseHandle
0x18000f12b  jmp     short loc_18000F14E
0x18000f12d  call    cs:__imp_GetLastError
0x18000f133  mov     [rsp+60h+dwCreationDisposition], eax
0x18000f137  mov     r9, rdi
0x18000f13a  lea     r8, aFailedToFlushS; "Failed to flush setting file %s. Error:"...
0x18000f141  mov     edx, 1
0x18000f146  mov     rcx, rbx
0x18000f149  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f14e  xor     eax, eax
0x18000f150  jmp     short loc_18000F157
0x18000f152  mov     eax, 80070057h
0x18000f157  add     rsp, 60h
0x18000f15b  pop     r14
0x18000f15d  pop     rdi
0x18000f15e  pop     rsi
0x18000f15f  pop     rbx
0x18000f160  pop     rbp
0x18000f161  retn
```
