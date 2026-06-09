# winreCreatePBRMarkerFile(ushort const *)

- ea: `0x18002da38`
- end: `0x18002dd1f`
- name: `?winreCreatePBRMarkerFile@@YAHPEBG@Z`
- size: `743`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x18002fc20`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000ffcc`
- `0x18002da38`
- `0x180031e88`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002dbed`
- `KERNEL32!GetLastError` at `0x18002dc1a`
- `KERNEL32!GetLastError` at `0x18002dc9c`
- `KERNEL32!GetLastError` at `0x18002dbed`
- `KERNEL32!GetLastError` at `0x18002dc1a`
- `KERNEL32!GetLastError` at `0x18002dc9c`
- `KERNEL32!WriteFile` at `0x18002dc92`
- `KERNEL32!WriteFile` at `0x18002dc92`
- `KERNEL32!CreateFileW` at `0x18002dbde`
- `KERNEL32!CreateFileW` at `0x18002dbde`
- `KERNEL32!CloseHandle` at `0x18002dcc8`
- `KERNEL32!CloseHandle` at `0x18002dcc8`
- `ole32!CoTaskMemFree` at `0x18002dcb9`
- `ole32!CoTaskMemFree` at `0x18002dcb9`

## string_xrefs

- `0x18002dadb`: `failed to allocate path`
- `0x18002dbac`: `failed to append path`
- `0x18002dab0`: `Invalid parameter because image path is not specified`
- `0x18002dbfd`: `failed to create file (%s). Error: 0x%08X`
- `0x18002dca2`: `WriteFile failed. Error: 0x%08X`
- `0x18002dce3`: `winreCreatePBRMarkerFile returning %s`
- `0x18002dc33`: `Upgrade will not replace the on-disk recovery image if this file is present. Do not delete or modify this file.`
- `0x18002db52`: `DONOTREPLACE.txt`

## pseudocode

```c
__int64 __fastcall winreCreatePBRMarkerFile(const unsigned __int16 *a1)
{
  unsigned int v2; // r15d
  __int64 v3; // rsi
  int v4; // eax
  BYTE *v5; // r14
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const unsigned __int16 *v9; // r8
  DWORD v10; // eax
  DWORD LastError; // eax
  const wchar_t *v12; // rdx
  int v13; // eax
  __int64 v14; // r8
  const wchar_t *v15; // r8
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[606]; // [rsp+52h] [rbp-AEh] BYREF
  unsigned __int16 Buffer; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v21[606]; // [rsp+2B2h] [rbp+1B2h] BYREF

  FileName = 0;
  v2 = 0;
  memset_0(v19, 0, 0x25Au);
  Buffer = 0;
  memset_0(v21, 0, 0x25Au);
  pv[0] = 0;
  if ( !a1 )
  {
    UnattendLogW(1, L"Invalid parameter because image path is not specified");
    goto LABEL_37;
  }
  v3 = -1;
  v4 = winreAllocPath(pv);
  v5 = (BYTE *)pv[0];
  if ( v4 )
  {
    UnattendLogW(1, L"failed to allocate path");
    goto LABEL_33;
  }
  pv[0] = 0;
  v6 = StringCchLengthW(a1, 0x7FFFFFFFu, (unsigned __int64 *)pv);
  if ( v6 >= 0 )
  {
    if ( !pv[0] || (v9 = L"%s\\%s", a1[(__int64)pv[0] - 1] == 92) )
      v9 = L"%s%s";
    v6 = StringCchPrintfW(&FileName, 0x12Eu, v9, a1, L"DONOTREPLACE.txt");
    if ( v6 >= 0 )
      goto LABEL_20;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 15;
      goto LABEL_17;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 14;
LABEL_17:
      WPP_SF_d(v7[2], v8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v6);
    }
  }
  if ( (_WORD)v6 )
  {
    UnattendLogW(1, L"failed to append path");
    goto LABEL_33;
  }
LABEL_20:
  v3 = (__int64)CreateFileW(&FileName, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  if ( v3 != -1 )
  {
    if ( (unsigned int)winreGetPrereleaseVersion(v5) )
    {
      LastError = GetLastError();
      v12 = L"failed to get prerelease version. Error: 0x%08X";
    }
    else
    {
      v13 = StringCchPrintfW(
              &Buffer,
              0x12Eu,
              L"%s\r\n\r\nBuild ID: %s",
              L"Upgrade will not replace the on-disk recovery image if this file is present. Do not delete or modify this file.",
              v5);
      if ( v13 < 0 )
      {
        UnattendLogW(1, L"StringCchPrintf failed. Error: 0x%08X", (unsigned __int16)v13);
        goto LABEL_33;
      }
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&v21[2 * v14 - 2] );
      if ( WriteFile((HANDLE)v3, &Buffer, 2 * v14, 0, 0) )
      {
        v2 = 1;
        goto LABEL_33;
      }
      LastError = GetLastError();
      v12 = L"WriteFile failed. Error: 0x%08X";
    }
    UnattendLogW(1, v12, LastError);
    goto LABEL_33;
  }
  v10 = GetLastError();
  UnattendLogW(1, L"failed to create file (%s). Error: 0x%08X", &FileName, v10);
LABEL_33:
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
LABEL_37:
  v15 = L"TRUE";
  if ( !v2 )
    v15 = L"FALSE";
  UnattendLogW(0, L"winreCreatePBRMarkerFile returning %s", v15);
  return v2;
}

```

## disassembly

```asm
0x18002da38  mov     [rsp-8+arg_8], rbx
0x18002da3d  mov     [rsp-8+arg_10], rsi
0x18002da42  push    rbp
0x18002da43  push    rdi
0x18002da44  push    r12
0x18002da46  push    r14
0x18002da48  push    r15
0x18002da4a  lea     rbp, [rsp-420h]
0x18002da52  sub     rsp, 520h
0x18002da59  mov     rax, cs:__security_cookie
0x18002da60  xor     rax, rsp
0x18002da63  mov     [rbp+440h+var_30], rax
0x18002da6a  mov     rdi, rcx
0x18002da6d  xor     r12d, r12d
0x18002da70  mov     ebx, 25Ah
0x18002da75  mov     [rsp+540h+FileName], r12w
0x18002da7b  mov     r8d, ebx; Size
0x18002da7e  lea     rcx, [rsp+540h+var_4EE]; void *
0x18002da83  xor     edx, edx; Val
0x18002da85  mov     r15d, r12d
0x18002da88  call    memset_0
0x18002da8d  mov     r8d, ebx; Size
0x18002da90  mov     [rbp+440h+Buffer], r12w
0x18002da98  xor     edx, edx; Val
0x18002da9a  lea     rcx, [rbp+440h+var_28E]; void *
0x18002daa1  call    memset_0
0x18002daa6  mov     [rsp+540h+pv], r12
0x18002daab  test    rdi, rdi
0x18002daae  jnz     short loc_18002DAC4
0x18002dab0  lea     rdx, aInvalidParamet_0; "Invalid parameter because image path is"...
0x18002dab7  lea     ecx, [rdi+1]
0x18002daba  call    UnattendLogW
0x18002dabf  jmp     loc_18002DCCE
0x18002dac4  lea     rcx, [rsp+540h+pv]
0x18002dac9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002dacd  call    winreAllocPath
0x18002dad2  mov     r14, [rsp+540h+pv]
0x18002dad7  test    eax, eax
0x18002dad9  jz      short loc_18002DAF1
0x18002dadb  lea     rdx, aFailedToAlloca_4; "failed to allocate path"
0x18002dae2  mov     ecx, 1
0x18002dae7  call    UnattendLogW
0x18002daec  jmp     loc_18002DCB1
0x18002daf1  lea     r8, [rsp+540h+pv]; unsigned __int64 *
0x18002daf6  mov     [rsp+540h+pv], r12
0x18002dafb  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002db00  mov     rcx, rdi; unsigned __int16 *
0x18002db03  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002db08  mov     ebx, eax
0x18002db0a  test    eax, eax
0x18002db0c  jns     short loc_18002DB32
0x18002db0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db15  lea     rax, WPP_GLOBAL_Control
0x18002db1c  cmp     rcx, rax
0x18002db1f  jz      loc_18002DBA7
0x18002db25  test    byte ptr [rcx+1Ch], 2
0x18002db29  jz      short loc_18002DBA7
0x18002db2b  mov     edx, 0Eh
0x18002db30  jmp     short loc_18002DB94
0x18002db32  mov     rax, [rsp+540h+pv]
0x18002db37  test    rax, rax
0x18002db3a  jz      short loc_18002DB4B
0x18002db3c  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x18002db42  lea     r8, aSS_1; "%s\\%s"
0x18002db49  jnz     short loc_18002DB52
0x18002db4b  lea     r8, aSS_2; "%s%s"
0x18002db52  lea     rax, aDonotreplaceTx; "DONOTREPLACE.txt"
0x18002db59  mov     r9, rdi
0x18002db5c  mov     edx, 12Eh; unsigned __int64
0x18002db61  mov     qword ptr [rsp+540h+dwCreationDisposition], rax
0x18002db66  lea     rcx, [rsp+540h+FileName]; unsigned __int16 *
0x18002db6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002db70  mov     ebx, eax
0x18002db72  test    eax, eax
0x18002db74  jns     short loc_18002DBB8
0x18002db76  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db7d  lea     rax, WPP_GLOBAL_Control
0x18002db84  cmp     rcx, rax
0x18002db87  jz      short loc_18002DBA7
0x18002db89  test    byte ptr [rcx+1Ch], 2
0x18002db8d  jz      short loc_18002DBA7
0x18002db8f  mov     edx, 0Fh
0x18002db94  mov     rcx, [rcx+10h]
0x18002db98  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18002db9f  mov     r9d, ebx
0x18002dba2  call    WPP_SF_d
0x18002dba7  test    bx, bx
0x18002dbaa  jz      short loc_18002DBB8
0x18002dbac  lea     rdx, aFailedToAppend_7; "failed to append path"
0x18002dbb3  jmp     loc_18002DAE2
0x18002dbb8  mov     [rsp+540h+hTemplateFile], r12; hTemplateFile
0x18002dbbd  lea     rcx, [rsp+540h+FileName]; lpFileName
0x18002dbc2  mov     ebx, 1
0x18002dbc7  mov     [rsp+540h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002dbcf  xor     r9d, r9d; lpSecurityAttributes
0x18002dbd2  mov     [rsp+540h+dwCreationDisposition], ebx; dwCreationDisposition
0x18002dbd6  xor     r8d, r8d; dwShareMode
0x18002dbd9  mov     edx, 40000000h; dwDesiredAccess
0x18002dbde  call    cs:__imp_CreateFileW
0x18002dbe4  mov     rsi, rax
0x18002dbe7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002dbeb  jnz     short loc_18002DC0E
0x18002dbed  call    cs:__imp_GetLastError
0x18002dbf3  lea     r8, [rsp+540h+FileName]
0x18002dbf8  mov     ecx, ebx
0x18002dbfa  mov     r9d, eax
0x18002dbfd  lea     rdx, aFailedToCreate_14; "failed to create file (%s). Error: 0x%0"...
0x18002dc04  call    UnattendLogW
0x18002dc09  jmp     loc_18002DCB1
0x18002dc0e  mov     rcx, r14; lpData
0x18002dc11  call    winreGetPrereleaseVersion
0x18002dc16  test    eax, eax
0x18002dc18  jz      short loc_18002DC33
0x18002dc1a  call    cs:__imp_GetLastError
0x18002dc20  lea     rdx, aFailedToGetPre; "failed to get prerelease version. Error"...
0x18002dc27  mov     r8d, eax
0x18002dc2a  mov     ecx, ebx
0x18002dc2c  call    UnattendLogW
0x18002dc31  jmp     short loc_18002DCB1
0x18002dc33  lea     r9, aUpgradeWillNot; "Upgrade will not replace the on-disk re"...
0x18002dc3a  mov     qword ptr [rsp+540h+dwCreationDisposition], r14
0x18002dc3f  lea     r8, aSBuildIdS; "%s\r\n\r\nBuild ID: %s"
0x18002dc46  mov     edx, 12Eh; unsigned __int64
0x18002dc4b  lea     rcx, [rbp+440h+Buffer]; unsigned __int16 *
0x18002dc52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dc57  test    eax, eax
0x18002dc59  jns     short loc_18002DC68
0x18002dc5b  movzx   r8d, ax
0x18002dc5f  lea     rdx, aStringcchprint; "StringCchPrintf failed. Error: 0x%08X"
0x18002dc66  jmp     short loc_18002DC2A
0x18002dc68  lea     rax, [rbp+440h+Buffer]
0x18002dc6f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002dc73  inc     r8
0x18002dc76  cmp     [rax+r8*2], r12w
0x18002dc7b  jnz     short loc_18002DC73
0x18002dc7d  add     r8d, r8d; nNumberOfBytesToWrite
0x18002dc80  mov     qword ptr [rsp+540h+dwCreationDisposition], r12; lpOverlapped
0x18002dc85  xor     r9d, r9d; lpNumberOfBytesWritten
0x18002dc88  lea     rdx, [rbp+440h+Buffer]; lpBuffer
0x18002dc8f  mov     rcx, rsi; hFile
0x18002dc92  call    cs:__imp_WriteFile
0x18002dc98  test    eax, eax
0x18002dc9a  jnz     short loc_18002DCAE
0x18002dc9c  call    cs:__imp_GetLastError
0x18002dca2  lea     rdx, aWritefileFaile; "WriteFile failed. Error: 0x%08X"
0x18002dca9  jmp     loc_18002DC27
0x18002dcae  mov     r15d, ebx
0x18002dcb1  test    r14, r14
0x18002dcb4  jz      short loc_18002DCBF
0x18002dcb6  mov     rcx, r14; pv
0x18002dcb9  call    cs:__imp_CoTaskMemFree
0x18002dcbf  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002dcc3  jz      short loc_18002DCCE
0x18002dcc5  mov     rcx, rsi; hObject
0x18002dcc8  call    cs:__imp_CloseHandle
0x18002dcce  test    r15d, r15d
0x18002dcd1  lea     rax, aFalse_0; "FALSE"
0x18002dcd8  lea     r8, aTrue_0; "TRUE"
0x18002dcdf  cmovz   r8, rax
0x18002dce3  lea     rdx, aWinrecreatepbr; "winreCreatePBRMarkerFile returning %s"
0x18002dcea  xor     ecx, ecx
0x18002dcec  call    UnattendLogW
0x18002dcf1  mov     eax, r15d
0x18002dcf4  mov     rcx, [rbp+440h+var_30]
0x18002dcfb  xor     rcx, rsp; StackCookie
0x18002dcfe  call    __security_check_cookie
0x18002dd03  lea     r11, [rsp+540h+var_20]
0x18002dd0b  mov     rbx, [r11+38h]
0x18002dd0f  mov     rsi, [r11+40h]
0x18002dd13  mov     rsp, r11
0x18002dd16  pop     r15
0x18002dd18  pop     r14
0x18002dd1a  pop     r12
0x18002dd1c  pop     rdi
0x18002dd1d  pop     rbp
0x18002dd1e  retn
```
