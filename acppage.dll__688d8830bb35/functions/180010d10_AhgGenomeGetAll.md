# AhgGenomeGetAll

- ea: `0x180010d10`
- end: `0x180011014`
- name: `AhgGenomeGetAll`
- size: `772`
- prototype: `__int64 __fastcall(const WCHAR *, void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180011640`

## callees

- `0x180010d10`
- `0x18001101c`
- `0x18001123c`
- `0x180011924`
- `0x180011c84`
- `0x180011d60`
- `0x180015220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010d83`
- `KERNEL32!GetLastError` at `0x180010d83`
- `KERNEL32!CloseHandle` at `0x180010ecd`
- `KERNEL32!CloseHandle` at `0x180010ecd`
- `KERNEL32!CreateFileW` at `0x180010d74`
- `KERNEL32!CreateFileW` at `0x180010d74`

## string_xrefs

- `0x180010d89`: `Failed to open file [%d]`
- `0x180010fe3`: `Cannot get manifest data [%d]`

## pseudocode

```c
__int64 __fastcall AhgGenomeGetAll(const WCHAR *a1, void *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // edi
  HANDLE FileW; // rsi
  DWORD LastError; // ebx
  int v9; // r14d
  const char *v10; // r9
  __int64 v11; // r8
  DWORD FileExeType; // eax
  const char *v13; // r9
  __int64 v14; // r8
  int PE; // eax
  unsigned int Manifest; // eax
  BOOL v18; // [rsp+80h] [rbp+8h] BYREF
  __int64 v19; // [rsp+88h] [rbp+10h] BYREF
  int v20; // [rsp+98h] [rbp+20h] BYREF
  int v21; // [rsp+9Ch] [rbp+24h]

  v21 = HIDWORD(a4);
  v19 = 0;
  v4 = 87;
  v18 = 0;
  v20 = 0;
  FileW = a2;
  if ( a2 == (void *)-1LL )
  {
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "AhgGenomeGetFileAttributes", 278, "Failed to open file [%d]");
      goto LABEL_21;
    }
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  LastError = AhgGetFileCreationTime(&v19, FileW);
  if ( LastError )
  {
    v10 = "Failed to get the creation time [%d]";
    v11 = 291;
LABEL_8:
    AslLogCallPrintf(1, "AhgGenomeGetFileAttributes", v11, v10);
    goto LABEL_19;
  }
  if ( !(unsigned int)AhgpSetAttribute(a1 + 316, 7, &v19) )
  {
    LastError = 87;
    v10 = "Failed to set data for attribute AHG_TAG_FILE_CREATION_TIME [%d]";
    v11 = 301;
    goto LABEL_8;
  }
  FileExeType = AhgGetFileExeType(&v20, &v18, FileW);
  LastError = FileExeType;
  if ( FileExeType )
  {
    if ( FileExeType != 193 )
    {
      v10 = "Failed to get the exe type [%d]";
      v11 = 312;
      goto LABEL_8;
    }
  }
  else
  {
    if ( !(unsigned int)AhgpSetAttribute(a1 + 324, 8, &v20) )
    {
      LastError = 87;
      v10 = "Failed to set data for attribute AHG_TAG_FILE_EXE_TYPE [%d]";
      v11 = 323;
      goto LABEL_8;
    }
    if ( !(unsigned int)AhgpSetAttribute(a1 + 332, 9, &v18) )
    {
      LastError = 87;
      v10 = "Failed to set data for attribute AHG_TAG_FILE_EXE_ILONLY [%d]";
      v11 = 333;
      goto LABEL_8;
    }
    LastError = 0;
  }
LABEL_19:
  if ( v9 )
    CloseHandle(FileW);
LABEL_21:
  if ( LastError == 30 )
  {
    v4 = 30;
    v13 = "Bad image file [%d]";
    v14 = 745;
LABEL_23:
    AslLogCallPrintf(1, "AhgGenomeGetAll", v14, v13);
    return v4;
  }
  if ( LastError )
    AslLogCallPrintf(3, "AhgGenomeGetAll", 750, "Cannot get file attribute [%d]");
  PE = AhgGenomeGetPE(a1, a3);
  if ( PE == 30 )
  {
    v20 = 1;
    if ( !(unsigned int)AhgpSetAttribute(a1 + 380, 15, &v20) )
    {
      AslLogCallPrintf(1, "AhgGenomeRecordBadImageOr16BitApp", 590, "Failed to set data for attribute AHG_TAG_NOT_PE");
      v13 = "Failed to set bad image or 16 bit app into genome [%d]";
      v14 = 762;
      goto LABEL_23;
    }
  }
  else if ( PE )
  {
    AslLogCallPrintf(3, "AhgGenomeGetAll", 768, "Cannot get PE data [%d]");
  }
  Manifest = AhgGenomeGetManifest(a1);
  v4 = Manifest;
  if ( Manifest == 30 )
  {
    v13 = "Bad image file [%d]";
    v14 = 778;
    goto LABEL_23;
  }
  if ( Manifest )
    AslLogCallPrintf(3, "AhgGenomeGetAll", 783, "Cannot get manifest data [%d]");
  return 0;
}

```

## disassembly

```asm
0x180010d10  mov     rax, rsp
0x180010d13  mov     [rax+20h], r9
0x180010d17  push    rbx
0x180010d18  push    rbp
0x180010d19  push    rsi
0x180010d1a  push    rdi
0x180010d1b  push    r13
0x180010d1d  push    r14
0x180010d1f  push    r15
0x180010d21  sub     rsp, 40h
0x180010d25  mov     qword ptr [rax+10h], 0
0x180010d2d  mov     edi, 57h ; 'W'
0x180010d32  mov     dword ptr [rax+8], 0
0x180010d39  mov     r15, r8
0x180010d3c  mov     dword ptr [rax+20h], 0
0x180010d43  mov     rsi, rdx
0x180010d46  mov     rbp, rcx
0x180010d49  lea     r13d, [rdi-56h]
0x180010d4d  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180010d51  jnz     short loc_180010DB5
0x180010d53  mov     qword ptr [rax-48h], 0
0x180010d5b  xor     r9d, r9d; lpSecurityAttributes
0x180010d5e  mov     dword ptr [rax-50h], 80h
0x180010d65  mov     r8d, r13d; dwShareMode
0x180010d68  mov     edx, 80000000h; dwDesiredAccess
0x180010d6d  mov     dword ptr [rax-58h], 3
0x180010d74  call    cs:__imp_CreateFileW
0x180010d7a  mov     rsi, rax
0x180010d7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010d81  jnz     short loc_180010DB0
0x180010d83  call    cs:__imp_GetLastError
0x180010d89  lea     r9, aFailedToOpenFi; "Failed to open file [%d]"
0x180010d90  mov     r8d, 116h
0x180010d96  lea     rdx, aAhggenomegetfi; "AhgGenomeGetFileAttributes"
0x180010d9d  mov     [rsp+78h+var_58], eax
0x180010da1  mov     ecx, r13d
0x180010da4  mov     ebx, eax
0x180010da6  call    AslLogCallPrintf
0x180010dab  jmp     loc_180010ED3
0x180010db0  mov     r14d, r13d
0x180010db3  jmp     short loc_180010DB8
0x180010db5  xor     r14d, r14d
0x180010db8  mov     rdx, rsi
0x180010dbb  lea     rcx, [rsp+78h+arg_8]
0x180010dc3  call    AhgGetFileCreationTime
0x180010dc8  mov     ebx, eax
0x180010dca  test    eax, eax
0x180010dcc  jz      short loc_180010DF3
0x180010dce  lea     r9, aFailedToGetThe_0; "Failed to get the creation time [%d]"
0x180010dd5  mov     r8d, 123h
0x180010ddb  mov     [rsp+78h+var_58], eax
0x180010ddf  lea     rdx, aAhggenomegetfi; "AhgGenomeGetFileAttributes"
0x180010de6  mov     ecx, r13d
0x180010de9  call    AslLogCallPrintf
0x180010dee  jmp     loc_180010EC5
0x180010df3  mov     edx, 7
0x180010df8  lea     rcx, [rbp+278h]
0x180010dff  lea     r8, [rsp+78h+arg_8]
0x180010e07  call    AhgpSetAttribute
0x180010e0c  test    eax, eax
0x180010e0e  jnz     short loc_180010E25
0x180010e10  mov     ebx, edi
0x180010e12  mov     [rsp+78h+var_58], edi
0x180010e16  lea     r9, aFailedToSetDat_7; "Failed to set data for attribute AHG_TA"...
0x180010e1d  mov     r8d, 12Dh
0x180010e23  jmp     short loc_180010DDF
0x180010e25  mov     r8, rsi
0x180010e28  lea     rdx, [rsp+78h+arg_0]
0x180010e30  lea     rcx, [rsp+78h+arg_18]
0x180010e38  call    AhgGetFileExeType
0x180010e3d  mov     ebx, eax
0x180010e3f  test    eax, eax
0x180010e41  jz      short loc_180010E59
0x180010e43  cmp     eax, 0C1h
0x180010e48  jz      short loc_180010EC5
0x180010e4a  lea     r9, aFailedToGetThe; "Failed to get the exe type [%d]"
0x180010e51  mov     r8d, 138h
0x180010e57  jmp     short loc_180010DDB
0x180010e59  mov     edx, 8
0x180010e5e  lea     rcx, [rbp+288h]
0x180010e65  lea     r8, [rsp+78h+arg_18]
0x180010e6d  call    AhgpSetAttribute
0x180010e72  test    eax, eax
0x180010e74  jnz     short loc_180010E8E
0x180010e76  mov     ebx, edi
0x180010e78  mov     [rsp+78h+var_58], edi
0x180010e7c  lea     r9, aFailedToSetDat_8; "Failed to set data for attribute AHG_TA"...
0x180010e83  mov     r8d, 143h
0x180010e89  jmp     loc_180010DDF
0x180010e8e  mov     edx, 9
0x180010e93  lea     rcx, [rbp+298h]
0x180010e9a  lea     r8, [rsp+78h+arg_0]
0x180010ea2  call    AhgpSetAttribute
0x180010ea7  test    eax, eax
0x180010ea9  jnz     short loc_180010EC3
0x180010eab  mov     ebx, edi
0x180010ead  mov     [rsp+78h+var_58], edi
0x180010eb1  lea     r9, aFailedToSetDat_4; "Failed to set data for attribute AHG_TA"...
0x180010eb8  mov     r8d, 14Dh
0x180010ebe  jmp     loc_180010DDF
0x180010ec3  xor     ebx, ebx
0x180010ec5  test    r14d, r14d
0x180010ec8  jz      short loc_180010ED3
0x180010eca  mov     rcx, rsi; hObject
0x180010ecd  call    cs:__imp_CloseHandle
0x180010ed3  mov     r14d, 1Eh
0x180010ed9  cmp     ebx, r14d
0x180010edc  jnz     short loc_180010F07
0x180010ede  mov     edi, r14d
0x180010ee1  mov     [rsp+78h+var_58], r14d
0x180010ee6  lea     r9, aBadImageFileD; "Bad image file [%d]"
0x180010eed  mov     r8d, 2E9h
0x180010ef3  lea     rdx, aAhggenomegetal; "AhgGenomeGetAll"
0x180010efa  mov     ecx, r13d
0x180010efd  call    AslLogCallPrintf
0x180010f02  jmp     loc_180011003
0x180010f07  lea     rsi, aAhggenomegetal; "AhgGenomeGetAll"
0x180010f0e  test    ebx, ebx
0x180010f10  jz      short loc_180010F30
0x180010f12  lea     r9, aCannotGetFileA; "Cannot get file attribute [%d]"
0x180010f19  mov     [rsp+78h+var_58], ebx
0x180010f1d  mov     r8d, 2EEh
0x180010f23  mov     rdx, rsi
0x180010f26  mov     ecx, 3
0x180010f2b  call    AslLogCallPrintf
0x180010f30  mov     rdx, r15
0x180010f33  mov     rcx, rbp
0x180010f36  call    AhgGenomeGetPE
0x180010f3b  cmp     eax, r14d
0x180010f3e  jnz     short loc_180010F9A
0x180010f40  mov     edx, 0Fh
0x180010f45  mov     [rsp+78h+arg_18], r13d
0x180010f4d  lea     rcx, [rbp+2F8h]
0x180010f54  lea     r8, [rsp+78h+arg_18]
0x180010f5c  call    AhgpSetAttribute
0x180010f61  test    eax, eax
0x180010f63  jnz     short loc_180010FBC
0x180010f65  lea     r9, aFailedToSetDat_5; "Failed to set data for attribute AHG_TA"...
0x180010f6c  mov     r8d, 24Eh
0x180010f72  lea     rdx, aAhggenomerecor; "AhgGenomeRecordBadImageOr16BitApp"
0x180010f79  mov     ecx, r13d
0x180010f7c  call    AslLogCallPrintf
0x180010f81  lea     r9, aFailedToSetBad; "Failed to set bad image or 16 bit app i"...
0x180010f88  mov     [rsp+78h+var_58], edi
0x180010f8c  mov     r8d, 2FAh
0x180010f92  mov     rdx, rsi
0x180010f95  jmp     loc_180010EFA
0x180010f9a  test    eax, eax
0x180010f9c  jz      short loc_180010FBC
0x180010f9e  lea     r9, aCannotGetPeDat; "Cannot get PE data [%d]"
0x180010fa5  mov     [rsp+78h+var_58], eax
0x180010fa9  mov     r8d, 300h
0x180010faf  mov     rdx, rsi
0x180010fb2  mov     ecx, 3
0x180010fb7  call    AslLogCallPrintf
0x180010fbc  mov     rcx, rbp
0x180010fbf  call    AhgGenomeGetManifest
0x180010fc4  mov     edi, eax
0x180010fc6  cmp     eax, r14d
0x180010fc9  jnz     short loc_180010FDF
0x180010fcb  mov     [rsp+78h+var_58], r14d
0x180010fd0  lea     r9, aBadImageFileD; "Bad image file [%d]"
0x180010fd7  mov     r8d, 30Ah
0x180010fdd  jmp     short loc_180010F92
0x180010fdf  test    eax, eax
0x180010fe1  jz      short loc_180011001
0x180010fe3  lea     r9, aCannotGetManif; "Cannot get manifest data [%d]"
0x180010fea  mov     [rsp+78h+var_58], eax
0x180010fee  mov     r8d, 30Fh
0x180010ff4  mov     rdx, rsi
0x180010ff7  mov     ecx, 3
0x180010ffc  call    AslLogCallPrintf
0x180011001  xor     edi, edi
0x180011003  mov     eax, edi
0x180011005  add     rsp, 40h
0x180011009  pop     r15
0x18001100b  pop     r14
0x18001100d  pop     r13
0x18001100f  pop     rdi
0x180011010  pop     rsi
0x180011011  pop     rbp
0x180011012  pop     rbx
0x180011013  retn
```
