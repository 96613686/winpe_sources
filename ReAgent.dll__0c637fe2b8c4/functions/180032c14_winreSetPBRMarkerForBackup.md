# winreSetPBRMarkerForBackup

- ea: `0x180032c14`
- end: `0x180032dc2`
- name: `winreSetPBRMarkerForBackup`
- size: `430`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18002dd30`

## callees

- `0x1800059fc`
- `0x1800103f4`
- `0x18001c354`
- `0x18001c448`
- `0x18001ee18`
- `0x18001f0c0`
- `0x18001f218`
- `0x18001f47c`
- `0x180032c14`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180032d74`
- `KERNEL32!GetLastError` at `0x180032d74`
- `KERNEL32!CreateFileW` at `0x180032d3c`
- `KERNEL32!CreateFileW` at `0x180032d3c`
- `KERNEL32!CloseHandle` at `0x180032d69`
- `KERNEL32!CloseHandle` at `0x180032d69`
- `KERNEL32!GetFileAttributesW` at `0x180032c5a`
- `KERNEL32!GetFileAttributesW` at `0x180032c5a`

## string_xrefs

- `0x180032d58`: `Marker file %s created`
- `0x180032d8a`: `Unable to create the marker file %s. Error: 0X%X`
- `0x180032c41`: `BackupDirectory is NULL`
- `0x180032c65`: `BackupDirectory does not exist`

## pseudocode

```c
__int64 __fastcall winreSetPBRMarkerForBackup(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  _QWORD *v5; // rax
  const WCHAR *v6; // r9
  unsigned __int64 v7; // rax
  __int64 v8; // r9
  unsigned __int64 v9; // rax
  const WCHAR *v10; // rax
  HANDLE FileW; // rdi
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD v15[4]; // [rsp+40h] [rbp-38h] BYREF

  std::wstring::wstring(v15, a2);
  v3 = 0;
  if ( !a1 )
  {
    UnattendLogW(2, L"BackupDirectory is NULL");
    goto LABEL_14;
  }
  if ( GetFileAttributesW(a1) == -1 )
  {
    UnattendLogW(2, L"BackupDirectory does not exist");
  }
  else
  {
    if ( (unsigned int)winreDoesFileExist(a1, L"$PBR_IN_PROGRESS_BACKUP.MARKER") )
    {
      UnattendLogW(0, L"[%s] contains a [%s] marker. Use existing one.", a1, L"$PBR_IN_PROGRESS_BACKUP.MARKER");
    }
    else
    {
      std::wstring::assign(v15, a1);
      v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      v6 = &cchOriginalDestLength;
      if ( *((_WORD *)v5 + v15[2] - 1) != 92 )
        v6 = L"\\";
      v7 = std::char_traits<unsigned short>::length(v6);
      std::wstring::append(v15, v8, v7);
      v9 = std::char_traits<unsigned short>::length(L"$PBR_IN_PROGRESS_BACKUP.MARKER");
      std::wstring::append(v15, (__int64)L"$PBR_IN_PROGRESS_BACKUP.MARKER", v9);
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      FileW = CreateFileW(v10, 0x40000000u, 0, 0, 2u, 2u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        GetLastError();
        v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
        UnattendLogW(2, L"Unable to create the marker file %s. Error: 0X%X", v13);
        goto LABEL_14;
      }
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
      UnattendLogW(0, L"Marker file %s created", v12);
      CloseHandle(FileW);
    }
    v3 = 1;
  }
LABEL_14:
  std::wstring::~wstring((__int64)v15, v4);
  return v3;
}

```

## disassembly

```asm
0x180032c14  mov     [rsp+arg_8], rbx
0x180032c19  push    rdi
0x180032c1a  sub     rsp, 70h
0x180032c1e  mov     rax, cs:__security_cookie
0x180032c25  xor     rax, rsp
0x180032c28  mov     [rsp+78h+var_18], rax
0x180032c2d  mov     rdi, rcx
0x180032c30  lea     rcx, [rsp+78h+var_38]
0x180032c35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180032c3a  xor     ebx, ebx
0x180032c3c  test    rdi, rdi
0x180032c3f  jnz     short loc_180032C57
0x180032c41  lea     rdx, aBackupdirector_0; "BackupDirectory is NULL"
0x180032c48  mov     ecx, 2
0x180032c4d  call    UnattendLogW
0x180032c52  jmp     loc_180032D9B
0x180032c57  mov     rcx, rdi; lpFileName
0x180032c5a  call    cs:__imp_GetFileAttributesW
0x180032c60  cmp     eax, 0FFFFFFFFh
0x180032c63  jnz     short loc_180032C6E
0x180032c65  lea     rdx, aBackupdirector_1; "BackupDirectory does not exist"
0x180032c6c  jmp     short loc_180032C48
0x180032c6e  lea     rdx, aPbrInProgressB; "$PBR_IN_PROGRESS_BACKUP.MARKER"
0x180032c75  mov     rcx, rdi; unsigned __int16 *
0x180032c78  call    winreDoesFileExist
0x180032c7d  test    eax, eax
0x180032c7f  jz      short loc_180032CA3
0x180032c81  lea     r9, aPbrInProgressB; "$PBR_IN_PROGRESS_BACKUP.MARKER"
0x180032c88  mov     r8, rdi
0x180032c8b  lea     rdx, aSContainsASMar; "[%s] contains a [%s] marker. Use existi"...
0x180032c92  xor     ecx, ecx
0x180032c94  call    UnattendLogW
0x180032c99  mov     ebx, 1
0x180032c9e  jmp     loc_180032D9B
0x180032ca3  mov     rdx, rdi
0x180032ca6  lea     rcx, [rsp+78h+var_38]
0x180032cab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180032cb0  lea     rcx, [rsp+78h+var_38]
0x180032cb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032cba  mov     rcx, [rsp+78h+var_28]
0x180032cbf  lea     rdx, pszSrc; "\\"
0x180032cc6  lea     r9, cchOriginalDestLength
0x180032ccd  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180032cd3  cmovnz  r9, rdx
0x180032cd7  mov     rcx, r9
0x180032cda  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180032cdf  mov     r8, rax
0x180032ce2  lea     rcx, [rsp+78h+var_38]
0x180032ce7  mov     rdx, r9
0x180032cea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180032cef  lea     rcx, aPbrInProgressB; "$PBR_IN_PROGRESS_BACKUP.MARKER"
0x180032cf6  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180032cfb  mov     r8, rax
0x180032cfe  lea     rdx, aPbrInProgressB; "$PBR_IN_PROGRESS_BACKUP.MARKER"
0x180032d05  lea     rcx, [rsp+78h+var_38]
0x180032d0a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180032d0f  lea     rcx, [rsp+78h+var_38]
0x180032d14  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032d19  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x180032d1e  mov     rcx, rax; lpFileName
0x180032d21  mov     [rsp+78h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x180032d29  xor     r9d, r9d; lpSecurityAttributes
0x180032d2c  xor     r8d, r8d; dwShareMode
0x180032d2f  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x180032d37  mov     edx, 40000000h; dwDesiredAccess
0x180032d3c  call    cs:__imp_CreateFileW
0x180032d42  mov     rdi, rax
0x180032d45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032d49  jz      short loc_180032D74
0x180032d4b  lea     rcx, [rsp+78h+var_38]
0x180032d50  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032d55  mov     r8, rax
0x180032d58  lea     rdx, aMarkerFileSCre; "Marker file %s created"
0x180032d5f  xor     ecx, ecx
0x180032d61  call    UnattendLogW
0x180032d66  mov     rcx, rdi; hObject
0x180032d69  call    cs:__imp_CloseHandle
0x180032d6f  jmp     loc_180032C99
0x180032d74  call    cs:__imp_GetLastError
0x180032d7a  lea     rcx, [rsp+78h+var_38]
0x180032d7f  mov     r9d, eax
0x180032d82  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032d87  mov     r8, rax
0x180032d8a  lea     rdx, aUnableToCreate; "Unable to create the marker file %s. Er"...
0x180032d91  mov     ecx, 2
0x180032d96  call    UnattendLogW
0x180032d9b  lea     rcx, [rsp+78h+var_38]
0x180032da0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180032da5  mov     eax, ebx
0x180032da7  mov     rcx, [rsp+78h+var_18]
0x180032dac  xor     rcx, rsp; StackCookie
0x180032daf  call    __security_check_cookie
0x180032db4  mov     rbx, [rsp+78h+arg_8]
0x180032dbc  add     rsp, 70h
0x180032dc0  pop     rdi
0x180032dc1  retn
```
