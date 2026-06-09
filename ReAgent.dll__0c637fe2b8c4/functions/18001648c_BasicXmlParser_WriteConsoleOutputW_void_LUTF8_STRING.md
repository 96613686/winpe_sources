# BasicXmlParser::WriteConsoleOutputW(void *,_LUTF8_STRING *)

- ea: `0x18001648c`
- end: `0x180016666`
- name: `?WriteConsoleOutputW@BasicXmlParser@@IEAAKPEAXPEAU_LUTF8_STRING@@@Z`
- size: `474`
- prototype: `unsigned int(BasicXmlParser *__hidden this, void *, struct _LUTF8_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x180015800`

## callees

- `0x1800059fc`
- `0x18001648c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016553`
- `KERNEL32!GetLastError` at `0x1800165bb`
- `KERNEL32!GetLastError` at `0x1800165ed`
- `KERNEL32!GetLastError` at `0x180016629`
- `KERNEL32!GetLastError` at `0x180016553`
- `KERNEL32!GetLastError` at `0x1800165bb`
- `KERNEL32!GetLastError` at `0x1800165ed`
- `KERNEL32!GetLastError` at `0x180016629`
- `KERNEL32!WriteConsoleW` at `0x1800165ad`
- `KERNEL32!WriteConsoleW` at `0x1800165ad`
- `KERNEL32!WriteConsoleA` at `0x180016549`
- `KERNEL32!WriteConsoleA` at `0x180016549`
- `KERNEL32!GetConsoleMode` at `0x1800164f6`
- `KERNEL32!GetConsoleMode` at `0x1800164f6`
- `KERNEL32!GetFileType` at `0x1800164df`
- `KERNEL32!GetFileType` at `0x1800164df`
- `KERNEL32!WriteFile` at `0x18001661f`
- `KERNEL32!WriteFile` at `0x18001661f`
- `KERNEL32!SetEndOfFile` at `0x1800165e3`
- `KERNEL32!SetEndOfFile` at `0x1800165e3`

## string_xrefs

- `0x18001656a`: `base\diagnosis\srt\reagent2\reinfo\parser_2.0.cpp`
- `0x180016637`: `failed to write file`
- `0x180016561`: `failed to write console`
- `0x180016579`: `BasicXmlParser::WriteConsoleOutputW %s (0x%x) in file %S line %d`
- `0x1800165c9`: `failed to write new line to console`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BasicXmlParser::WriteConsoleOutputW(BasicXmlParser *this, char *a2, LPCVOID *a3)
{
  _BYTE *v5; // rdx
  DWORD v6; // r8d
  DWORD LastError; // eax
  const wchar_t *v8; // r8
  DWORD v9; // ebx
  int v11; // [rsp+28h] [rbp-30h]
  __int64 NumberOfCharsWritten; // [rsp+40h] [rbp-18h] BYREF

  NumberOfCharsWritten = 0;
  if ( (unsigned __int64)(a2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 50;
  if ( GetFileType(a2) != 2 || !GetConsoleMode(a2, (LPDWORD)&NumberOfCharsWritten + 1) )
  {
    UnattendLogW(0, L"Writing to file");
    if ( !SetEndOfFile(a2) )
    {
      LastError = GetLastError();
      v11 = 2634;
      v8 = L"failed to set end of file";
      goto LABEL_11;
    }
    if ( !WriteFile(a2, a3[2], *(_DWORD *)a3, (LPDWORD)&NumberOfCharsWritten, 0) )
    {
      LastError = GetLastError();
      v11 = 2638;
      v8 = L"failed to write file";
      goto LABEL_11;
    }
    return 0;
  }
  UnattendLogW(0, L"Writing to console");
  v5 = a3[2];
  v6 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 >= 3u && *v5 == 0xEF && v5[1] == 0xBB && v5[2] == 0xBF )
  {
    v5 += 3;
    v6 -= 3;
  }
  if ( WriteConsoleA(a2, v5, v6, (LPDWORD)&NumberOfCharsWritten, 0) )
  {
    if ( !WriteConsoleW(a2, L"\r\n\r\n", 4u, (LPDWORD)&NumberOfCharsWritten, 0) )
    {
      LastError = GetLastError();
      v11 = 2629;
      v8 = L"failed to write new line to console";
      goto LABEL_11;
    }
    return 0;
  }
  LastError = GetLastError();
  v11 = 2625;
  v8 = L"failed to write console";
LABEL_11:
  v9 = LastError;
  UnattendLogW(
    2,
    L"BasicXmlParser::WriteConsoleOutputW %s (0x%x) in file %S line %d",
    v8,
    LastError,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\parser_2.0.cpp",
    v11,
    -2,
    0,
    NumberOfCharsWritten);
  return v9;
}

```

## disassembly

```asm
0x18001648c  push    rdi
0x18001648e  sub     rsp, 50h
0x180016492  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001649b  mov     [rsp+58h+arg_0], rbx
0x1800164a0  mov     rax, cs:__security_cookie
0x1800164a7  xor     rax, rsp
0x1800164aa  mov     [rsp+58h+var_10], rax
0x1800164af  mov     rdi, r8
0x1800164b2  mov     rbx, rdx
0x1800164b5  mov     [rsp+58h+var_20], 0
0x1800164be  mov     [rsp+58h+NumberOfCharsWritten], 0
0x1800164c6  mov     [rsp+58h+Mode], 0
0x1800164ce  lea     rax, [rdx-1]
0x1800164d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800164d6  ja      loc_180016647
0x1800164dc  mov     rcx, rdx; hFile
0x1800164df  call    cs:__imp_GetFileType
0x1800164e5  cmp     eax, 2
0x1800164e8  jnz     loc_1800165D2
0x1800164ee  lea     rdx, [rsp+58h+Mode]; lpMode
0x1800164f3  mov     rcx, rbx; hConsoleHandle
0x1800164f6  call    cs:__imp_GetConsoleMode
0x1800164fc  test    eax, eax
0x1800164fe  jz      loc_1800165D2
0x180016504  lea     rdx, aWritingToConso; "Writing to console"
0x18001650b  xor     ecx, ecx
0x18001650d  call    UnattendLogW
0x180016512  mov     rdx, [rdi+10h]
0x180016516  mov     r8d, [rdi]
0x180016519  cmp     r8d, 3
0x18001651d  jb      short loc_180016538
0x18001651f  cmp     byte ptr [rdx], 0EFh
0x180016522  jnz     short loc_180016538
0x180016524  cmp     byte ptr [rdx+1], 0BBh
0x180016528  jnz     short loc_180016538
0x18001652a  cmp     byte ptr [rdx+2], 0BFh
0x18001652e  jnz     short loc_180016538
0x180016530  add     rdx, 3; lpBuffer
0x180016534  add     r8d, 0FFFFFFFDh; nNumberOfCharsToWrite
0x180016538  mov     [rsp+58h+lpReserved], 0; lpReserved
0x180016541  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x180016546  mov     rcx, rbx; hConsoleOutput
0x180016549  call    cs:__imp_WriteConsoleA
0x18001654f  test    eax, eax
0x180016551  jnz     short loc_18001658F
0x180016553  call    cs:__imp_GetLastError
0x180016559  mov     [rsp+58h+var_30], 0A41h
0x180016561  lea     r8, aFailedToWriteC_2; "failed to write console"
0x180016568  mov     ebx, eax
0x18001656a  lea     rax, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180016571  mov     r9d, ebx
0x180016574  mov     [rsp+58h+lpReserved], rax
0x180016579  lea     rdx, aBasicxmlparser_7; "BasicXmlParser::WriteConsoleOutputW %s "...
0x180016580  mov     ecx, 2
0x180016585  call    UnattendLogW
0x18001658a  jmp     loc_18001664C
0x18001658f  mov     [rsp+58h+lpReserved], 0; lpReserved
0x180016598  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x18001659d  mov     r8d, 4; nNumberOfCharsToWrite
0x1800165a3  lea     rdx, asc_18006A4A8; "\r\n\r\n"
0x1800165aa  mov     rcx, rbx; hConsoleOutput
0x1800165ad  call    cs:__imp_WriteConsoleW
0x1800165b3  test    eax, eax
0x1800165b5  jnz     loc_180016643
0x1800165bb  call    cs:__imp_GetLastError
0x1800165c1  mov     [rsp+58h+var_30], 0A45h
0x1800165c9  lea     r8, aFailedToWriteN; "failed to write new line to console"
0x1800165d0  jmp     short loc_180016568
0x1800165d2  lea     rdx, aWritingToFile; "Writing to file"
0x1800165d9  xor     ecx, ecx
0x1800165db  call    UnattendLogW
0x1800165e0  mov     rcx, rbx; hFile
0x1800165e3  call    cs:__imp_SetEndOfFile
0x1800165e9  test    eax, eax
0x1800165eb  jnz     short loc_180016607
0x1800165ed  call    cs:__imp_GetLastError
0x1800165f3  mov     [rsp+58h+var_30], 0A4Ah
0x1800165fb  lea     r8, aFailedToSetEnd; "failed to set end of file"
0x180016602  jmp     loc_180016568
0x180016607  mov     [rsp+58h+lpReserved], 0; lpOverlapped
0x180016610  lea     r9, [rsp+58h+NumberOfCharsWritten]; lpNumberOfBytesWritten
0x180016615  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x180016618  mov     rdx, [rdi+10h]; lpBuffer
0x18001661c  mov     rcx, rbx; hFile
0x18001661f  call    cs:__imp_WriteFile
0x180016625  test    eax, eax
0x180016627  jnz     short loc_180016643
0x180016629  call    cs:__imp_GetLastError
0x18001662f  mov     [rsp+58h+var_30], 0A4Eh
0x180016637  lea     r8, aFailedToWriteF; "failed to write file"
0x18001663e  jmp     loc_180016568
0x180016643  xor     ebx, ebx
0x180016645  jmp     short loc_18001664C
0x180016647  mov     ebx, 32h ; '2'
0x18001664c  mov     eax, ebx
0x18001664e  mov     rcx, [rsp+58h+var_10]
0x180016653  xor     rcx, rsp; StackCookie
0x180016656  call    __security_check_cookie
0x18001665b  mov     rbx, [rsp+58h+arg_0]
0x180016660  add     rsp, 50h
0x180016664  pop     rdi
0x180016665  retn
```
