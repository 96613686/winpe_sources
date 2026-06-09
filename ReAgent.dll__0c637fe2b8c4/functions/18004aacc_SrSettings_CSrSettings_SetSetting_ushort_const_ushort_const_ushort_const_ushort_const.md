# SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18004aacc`
- end: `0x18004ad17`
- name: `?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z`
- size: `587`
- prototype: `int(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180046ed0`
- `0x180049360`
- `0x18004a814`
- `0x18004ad20`
- `0x18004bfa0`

## callees

- `0x18004aacc`
- `0x18004c0e8`
- `0x18004c44c`
- `0x18004c5a0`
- `0x18004c5c8`
- `0x18004c6c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004ab6e`
- `KERNEL32!GetLastError` at `0x18004ab8e`
- `KERNEL32!GetLastError` at `0x18004ac2e`
- `KERNEL32!GetLastError` at `0x18004ac4f`
- `KERNEL32!GetLastError` at `0x18004acd1`
- `KERNEL32!GetLastError` at `0x18004ab6e`
- `KERNEL32!GetLastError` at `0x18004ab8e`
- `KERNEL32!GetLastError` at `0x18004ac2e`
- `KERNEL32!GetLastError` at `0x18004ac4f`
- `KERNEL32!GetLastError` at `0x18004acd1`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004ab60`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004ac24`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004ac81`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004ab60`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004ac24`
- `KERNEL32!WritePrivateProfileStringW` at `0x18004ac81`
- `KERNEL32!CreateFileW` at `0x18004acae`
- `KERNEL32!CreateFileW` at `0x18004acae`
- `KERNEL32!CloseHandle` at `0x18004acc9`
- `KERNEL32!CloseHandle` at `0x18004acc9`
- `KERNEL32!FlushFileBuffers` at `0x18004acc0`
- `KERNEL32!FlushFileBuffers` at `0x18004acc0`

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
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-78h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-78h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-78h]
  LPCWSTR lpString[2]; // [rsp+48h] [rbp-50h] BYREF
  _WORD v18[32]; // [rsp+58h] [rbp-40h] BYREF

  v5 = a4;
  if ( *((_BYTE *)this + 3944) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Cannot set setting in UseInWinRE mode");
    return -2147024891;
  }
  if ( !a2 || !a3 )
    return -2147024809;
  if ( a5 )
  {
    lpString[0] = v18;
    lpString[1] = v18;
    v18[0] = 0;
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            lpString,
                            L"\"",
                            1)
      && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            lpString,
                            a5)
      && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            lpString,
                            L"\"",
                            1) )
    {
      if ( WritePrivateProfileStringW(a3, v5, lpString[0], a2) )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpString);
        goto LABEL_18;
      }
      dwCreationDispositionb = GetLastError();
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to set setting %s. Error: %d", v5, dwCreationDispositionb);
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v11 = -2147024888;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)lpString);
    return v11;
  }
  if ( !a4 )
    a4 = &cchOriginalDestLength;
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
LABEL_18:
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

```

## disassembly

```asm
0x18004aacc  push    rbx
0x18004aace  push    rbp
0x18004aacf  push    rsi
0x18004aad0  push    rdi
0x18004aad1  push    r15
0x18004aad3  sub     rsp, 70h
0x18004aad7  mov     [rsp+98h+var_58], 0FFFFFFFFFFFFFFFEh
0x18004aae0  mov     rsi, r9
0x18004aae3  mov     rbp, r8
0x18004aae6  mov     rdi, rdx
0x18004aae9  mov     rbx, rcx
0x18004aaec  cmp     byte ptr [rcx+0F68h], 0
0x18004aaf3  jz      short loc_18004AB10
0x18004aaf5  lea     r8, aCannotSetSetti; "Cannot set setting in UseInWinRE mode"
0x18004aafc  mov     edx, 2
0x18004ab01  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004ab06  mov     eax, 80070005h
0x18004ab0b  jmp     loc_18004AD0C
0x18004ab10  test    rdi, rdi
0x18004ab13  jz      loc_18004AD07
0x18004ab19  test    rbp, rbp
0x18004ab1c  jz      loc_18004AD07
0x18004ab22  mov     r15d, 1
0x18004ab28  cmp     [rsp+98h+arg_20], 0
0x18004ab31  jnz     short loc_18004ABA9
0x18004ab33  lea     rax, cchOriginalDestLength
0x18004ab3a  test    rsi, rsi
0x18004ab3d  cmovz   r9, rax
0x18004ab41  mov     qword ptr [rsp+98h+dwCreationDisposition], rbp
0x18004ab46  lea     r8, aClearSettingSI; "Clear setting [%s] in [%s]"
0x18004ab4d  xor     edx, edx
0x18004ab4f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004ab54  mov     r9, rdi; lpFileName
0x18004ab57  xor     r8d, r8d; lpString
0x18004ab5a  mov     rdx, rsi; lpKeyName
0x18004ab5d  mov     rcx, rbp; lpAppName
0x18004ab60  call    cs:__imp_WritePrivateProfileStringW
0x18004ab66  test    eax, eax
0x18004ab68  jnz     loc_18004AC77
0x18004ab6e  call    cs:__imp_GetLastError
0x18004ab74  mov     [rsp+98h+dwCreationDisposition], eax
0x18004ab78  mov     r9, rsi
0x18004ab7b  lea     r8, aFailedToSetSet; "Failed to set setting %s. Error: %d"
0x18004ab82  lea     edx, [r15+1]
0x18004ab86  mov     rcx, rbx
0x18004ab89  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004ab8e  call    cs:__imp_GetLastError
0x18004ab94  test    eax, eax
0x18004ab96  jle     loc_18004AD0C
0x18004ab9c  movzx   eax, ax
0x18004ab9f  or      eax, 80070000h
0x18004aba4  jmp     loc_18004AD0C
0x18004aba9  lea     rax, [rsp+98h+var_40]
0x18004abae  mov     [rsp+98h+lpString], rax
0x18004abb3  lea     rax, [rsp+98h+var_40]
0x18004abb8  mov     [rsp+98h+var_48], rax
0x18004abbd  xor     eax, eax
0x18004abbf  mov     [rsp+98h+var_40], ax
0x18004abc4  mov     r8, r15
0x18004abc7  lea     rdx, asc_18009A8E8; "\""
0x18004abce  lea     rcx, [rsp+98h+lpString]
0x18004abd3  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004abd8  test    al, al
0x18004abda  jz      loc_18004ACF4
0x18004abe0  mov     rdx, [rsp+98h+arg_20]
0x18004abe8  lea     rcx, [rsp+98h+lpString]
0x18004abed  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18004abf2  test    al, al
0x18004abf4  jz      loc_18004ACF4
0x18004abfa  mov     r8, r15
0x18004abfd  lea     rdx, asc_18009A8E8; "\""
0x18004ac04  lea     rcx, [rsp+98h+lpString]
0x18004ac09  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18004ac0e  test    al, al
0x18004ac10  jz      loc_18004ACF4
0x18004ac16  mov     r9, rdi; lpFileName
0x18004ac19  mov     r8, [rsp+98h+lpString]; lpString
0x18004ac1e  mov     rdx, rsi; lpKeyName
0x18004ac21  mov     rcx, rbp; lpAppName
0x18004ac24  call    cs:__imp_WritePrivateProfileStringW
0x18004ac2a  test    eax, eax
0x18004ac2c  jnz     short loc_18004AC6D
0x18004ac2e  call    cs:__imp_GetLastError
0x18004ac34  mov     [rsp+98h+dwCreationDisposition], eax
0x18004ac38  mov     r9, rsi
0x18004ac3b  lea     r8, aFailedToSetSet; "Failed to set setting %s. Error: %d"
0x18004ac42  mov     edx, 2
0x18004ac47  mov     rcx, rbx
0x18004ac4a  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004ac4f  call    cs:__imp_GetLastError
0x18004ac55  mov     ebx, eax
0x18004ac57  test    eax, eax
0x18004ac59  jle     loc_18004ACF9
0x18004ac5f  movzx   ebx, ax
0x18004ac62  or      ebx, 80070000h
0x18004ac68  jmp     loc_18004ACF9
0x18004ac6d  lea     rcx, [rsp+98h+lpString]
0x18004ac72  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004ac77  xor     r9d, r9d; lpFileName
0x18004ac7a  xor     r8d, r8d; lpString
0x18004ac7d  xor     edx, edx; lpKeyName
0x18004ac7f  xor     ecx, ecx; lpAppName
0x18004ac81  call    cs:__imp_WritePrivateProfileStringW
0x18004ac87  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x18004ac90  mov     [rsp+98h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x18004ac98  mov     [rsp+98h+dwCreationDisposition], 4; dwCreationDisposition
0x18004aca0  xor     r9d, r9d; lpSecurityAttributes
0x18004aca3  mov     r8d, r15d; dwShareMode
0x18004aca6  mov     edx, 40000000h; dwDesiredAccess
0x18004acab  mov     rcx, rdi; lpFileName
0x18004acae  call    cs:__imp_CreateFileW
0x18004acb4  mov     rsi, rax
0x18004acb7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004acbb  jz      short loc_18004ACD1
0x18004acbd  mov     rcx, rax; hFile
0x18004acc0  call    cs:__imp_FlushFileBuffers
0x18004acc6  mov     rcx, rsi; hObject
0x18004acc9  call    cs:__imp_CloseHandle
0x18004accf  jmp     short loc_18004ACF0
0x18004acd1  call    cs:__imp_GetLastError
0x18004acd7  mov     [rsp+98h+dwCreationDisposition], eax
0x18004acdb  mov     r9, rdi
0x18004acde  lea     r8, aFailedToFlushS; "Failed to flush setting file %s. Error:"...
0x18004ace5  mov     edx, r15d
0x18004ace8  mov     rcx, rbx
0x18004aceb  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004acf0  xor     eax, eax
0x18004acf2  jmp     short loc_18004AD0C
0x18004acf4  mov     ebx, 80070008h
0x18004acf9  lea     rcx, [rsp+98h+lpString]
0x18004acfe  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18004ad03  mov     eax, ebx
0x18004ad05  jmp     short loc_18004AD0C
0x18004ad07  mov     eax, 80070057h
0x18004ad0c  add     rsp, 70h
0x18004ad10  pop     r15
0x18004ad12  pop     rdi
0x18004ad13  pop     rsi
0x18004ad14  pop     rbp
0x18004ad15  pop     rbx
0x18004ad16  retn
```
