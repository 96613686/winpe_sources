# WriteSIDKeyInCache(_SID_KEY_HEADER *,ulong,uchar *,ulong,ushort const *,ushort const *)

- ea: `0x18000ce40`
- end: `0x18000d23f`
- name: `?WriteSIDKeyInCache@@YAJPEAU_SID_KEY_HEADER@@KPEAEKPEBG2@Z`
- size: `1023`
- prototype: `__int64 __usercall@<rax>(struct _SID_KEY_HEADER *Src@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800196cc`
- `0x180019bec`

## callees

- `0x18000a878`
- `0x18000bb30`
- `0x18000ce40`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d202`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ceea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d00d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d086`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d1f3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000d15c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000d15c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18000cffa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18000d077`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18000cffa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileTransactedW` at `0x18000d077`
- `ntdll!NtRollbackTransaction` at `0x18000d1ab`
- `ntdll!NtRollbackTransaction` at `0x18000d1ab`
- `ntdll!NtCommitTransaction` at `0x18000d1b9`
- `ntdll!NtCommitTransaction` at `0x18000d1b9`
- `ntdll!NtCreateTransaction` at `0x18000cf88`
- `ntdll!NtCreateTransaction` at `0x18000cf88`
- `CRYPT32!CryptProtectData` at `0x18000cee0`
- `CRYPT32!CryptProtectData` at `0x18000cee0`

## string_xrefs

- `0x18000cf01`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000cfa2`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000d0d7`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000d172`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall WriteSIDKeyInCache(
        struct _SID_KEY_HEADER *Src,
        unsigned int a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  __int64 v7; // r13
  char *FileTransactedW; // rdi
  unsigned __int64 v9; // rdx
  int v10; // r12d
  unsigned __int64 v11; // rdx
  WCHAR *v12; // r15
  __int64 v13; // rax
  char *v14; // rcx
  char *v15; // r14
  DWORD LastError; // eax
  unsigned int v17; // r9d
  signed int v18; // ebx
  unsigned int v19; // ecx
  __int64 v20; // rdx
  bool v21; // sf
  unsigned int v22; // edx
  int v23; // r8d
  signed int SIDKeyFileName; // eax
  unsigned int v25; // r9d
  int SIDKeyCacheFolder; // eax
  unsigned int v27; // r9d
  unsigned int v28; // ecx
  DWORD v29; // r12d
  char *v30; // rax
  __int64 v31; // rdx
  HANDLE hObject; // [rsp+58h] [rbp-29h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-21h] BYREF
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-19h] BYREF
  DATA_BLOB pDataIn; // [rsp+78h] [rbp-9h] BYREF
  struct _GUID v37; // [rsp+88h] [rbp+7h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+D8h] [rbp+57h] BYREF
  void *Srca; // [rsp+E8h] [rbp+67h]
  size_t Size; // [rsp+F0h] [rbp+6Fh]

  LODWORD(Size) = a4;
  Srca = a3;
  pDataIn.cbData = *((_DWORD *)Src + 17) + *((_DWORD *)Src + 16);
  v7 = a2;
  FileTransactedW = 0;
  v9 = *((unsigned int *)Src + 18) + (unsigned __int64)*((unsigned int *)Src + 19);
  hObject = 0;
  v10 = 0;
  v11 = *((unsigned int *)Src + 13) + v9;
  *(&pDataIn.cbData + 1) = 0;
  v12 = 0;
  v13 = *((unsigned int *)Src + 10);
  v14 = (char *)Src + *((unsigned int *)Src + 11) + *((unsigned int *)Src + 12) + v11;
  NumberOfBytesWritten = 0;
  lpFileName = 0;
  pDataIn.pbData = (BYTE *)&v14[v13 + 80];
  v15 = 0;
  pDataOut = 0;
  if ( !CryptProtectData(&pDataIn, 0, 0, 0, 0, 0, &pDataOut) )
  {
    LastError = GetLastError();
    v17 = 712;
LABEL_3:
    v18 = LastError;
    v19 = LastError;
    goto LABEL_4;
  }
  v22 = *((_DWORD *)Src + 3);
  v23 = *((_DWORD *)Src + 2) & 1;
  v37 = *(struct _GUID *)((char *)Src + 24);
  SIDKeyFileName = GetSIDKeyFileName(&v37, v22, v23, a5, (unsigned __int16 **)&lpFileName);
  v18 = SIDKeyFileName;
  if ( SIDKeyFileName < 0 )
  {
    v25 = 726;
LABEL_10:
    SidKeyDebugTraceError(
      SIDKeyFileName,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      v25);
    v12 = (WCHAR *)lpFileName;
    goto LABEL_33;
  }
  SIDKeyFileName = NtCreateTransaction(&hObject, 2031679, 0, 0, 0, 0, 0, 0, 0, 0);
  v18 = SIDKeyFileName;
  if ( SIDKeyFileName < 0 )
  {
    hObject = (HANDLE)-1LL;
    v25 = 747;
    goto LABEL_10;
  }
  v12 = (WCHAR *)lpFileName;
  FileTransactedW = (char *)CreateFileTransactedW(lpFileName, 0x40000000u, 0, 0, 4u, 0x8000002u, 0, hObject, 0, 0);
  if ( FileTransactedW != (char *)-1LL )
    goto LABEL_19;
  v18 = GetLastError();
  if ( v18 == 3 )
  {
    SIDKeyCacheFolder = CreateSIDKeyCacheFolder(a6, a5, *((_DWORD *)Src + 2) & 1);
    v18 = SIDKeyCacheFolder;
    if ( SIDKeyCacheFolder < 0 )
    {
      v27 = 775;
      goto LABEL_15;
    }
    FileTransactedW = (char *)CreateFileTransactedW(v12, 0x40000000u, 2u, 0, 4u, 0, 0, hObject, 0, 0);
    if ( FileTransactedW == (char *)-1LL )
    {
      LastError = GetLastError();
      v17 = 793;
      goto LABEL_3;
    }
LABEL_19:
    v29 = Size + v7 + pDataOut.cbData - *((_DWORD *)Src + 16) - *((_DWORD *)Src + 17);
    v30 = (char *)SIDKeyProvAlloc(v29);
    v15 = v30;
    if ( !v30 )
    {
      v18 = -2147024882;
      v27 = 816;
      v28 = -2147024882;
      goto LABEL_21;
    }
    memcpy_0(v30, Src, (unsigned int)(v7 - *((_DWORD *)Src + 16) - *((_DWORD *)Src + 17)));
    memcpy_0(&v15[v7 - *((unsigned int *)Src + 16) - *((unsigned int *)Src + 17)], pDataOut.pbData, pDataOut.cbData);
    memcpy_0(
      &v15[v7 + pDataOut.cbData - (unsigned __int64)*((unsigned int *)Src + 16) - *((unsigned int *)Src + 17)],
      Srca,
      (unsigned int)Size);
    if ( !WriteFile(FileTransactedW, v15, v29, &NumberOfBytesWritten, 0) )
    {
      v18 = GetLastError();
      SidKeyDebugTraceError(
        v18,
        "dwReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        0x348u);
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v10 = 1;
      goto LABEL_26;
    }
    LOBYTE(v31) = 1;
    SIDKeyCacheFolder = NtCommitTransaction(hObject, v31);
    v18 = SIDKeyCacheFolder;
    if ( SIDKeyCacheFolder >= 0 )
    {
      v18 = 0;
      goto LABEL_33;
    }
    v27 = 853;
LABEL_15:
    v28 = SIDKeyCacheFolder;
LABEL_21:
    SidKeyDebugTraceError(v28, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v27);
    goto LABEL_33;
  }
  v17 = 800;
  v19 = v18;
LABEL_4:
  SidKeyDebugTraceError(v19, "dwReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v17);
  v21 = v18 < 0;
  if ( v18 > 0 )
  {
    v18 = (unsigned __int16)v18 | 0x80070000;
LABEL_26:
    v21 = v18 < 0;
  }
  if ( v21 && v10 )
  {
    LOBYTE(v20) = 1;
    NtRollbackTransaction(hObject, v20);
  }
LABEL_33:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (unsigned __int64)(FileTransactedW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileTransactedW);
  if ( pDataOut.pbData )
    LocalFree(pDataOut.pbData);
  if ( v12 )
    SIDKeyProvFree(v12);
  if ( v15 )
    SIDKeyProvFree(v15);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000ce40  mov     rax, rsp
0x18000ce43  mov     [rax+10h], rbx
0x18000ce47  mov     [rax+20h], r9d
0x18000ce4b  mov     [rax+18h], r8
0x18000ce4f  push    rbp
0x18000ce50  push    rsi
0x18000ce51  push    rdi
0x18000ce52  push    r12
0x18000ce54  push    r13
0x18000ce56  push    r14
0x18000ce58  push    r15
0x18000ce5a  lea     rbp, [rax-4Fh]
0x18000ce5e  sub     rsp, 90h
0x18000ce65  mov     eax, [rcx+40h]
0x18000ce68  xor     ebx, ebx
0x18000ce6a  add     eax, [rcx+44h]
0x18000ce6d  mov     rsi, rcx
0x18000ce70  mov     [rbp+47h+pDataIn.cbData], eax
0x18000ce73  xorps   xmm0, xmm0
0x18000ce76  mov     eax, [rcx+48h]
0x18000ce79  xor     r9d, r9d; pvReserved
0x18000ce7c  mov     r13d, edx
0x18000ce7f  xor     r8d, r8d; pOptionalEntropy
0x18000ce82  mov     edx, [rcx+4Ch]
0x18000ce85  mov     edi, ebx
0x18000ce87  add     rdx, rax
0x18000ce8a  mov     [rbp+47h+hObject], rbx
0x18000ce8e  mov     eax, [rcx+34h]
0x18000ce91  mov     r12d, ebx
0x18000ce94  add     rdx, rax
0x18000ce97  mov     dword ptr [rbp+47h+pDataIn+4], ebx
0x18000ce9a  mov     eax, [rcx+30h]
0x18000ce9d  mov     r15d, ebx
0x18000cea0  mov     ecx, [rcx+2Ch]
0x18000cea3  add     rdx, rax
0x18000cea6  mov     eax, [rsi+28h]
0x18000cea9  add     rcx, rsi
0x18000ceac  add     rcx, rdx
0x18000ceaf  mov     [rbp+47h+NumberOfBytesWritten], ebx
0x18000ceb2  add     rax, 50h ; 'P'
0x18000ceb6  mov     [rbp+47h+lpFileName], rbx
0x18000ceba  add     rax, rcx
0x18000cebd  xor     edx, edx; szDataDescr
0x18000cebf  mov     [rbp+47h+pDataIn.pbData], rax
0x18000cec3  lea     rcx, [rbp+47h+pDataIn]; pDataIn
0x18000cec7  lea     rax, [rbp+47h+var_60]
0x18000cecb  mov     r14d, ebx
0x18000cece  mov     [rsp+0C0h+pDataOut], rax; pDataOut
0x18000ced3  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x18000ced7  mov     [rsp+0C0h+pPromptStruct], rbx; pPromptStruct
0x18000cedc  movups  xmmword ptr [rbp+47h+var_60.cbData], xmm0
0x18000cee0  call    cs:__imp_CryptProtectData
0x18000cee6  test    eax, eax
0x18000cee8  jnz     short loc_18000CF23
0x18000ceea  call    cs:__imp_GetLastError
0x18000cef0  mov     r9d, 2C8h; unsigned int
0x18000cef6  mov     ebx, eax
0x18000cef8  mov     ecx, eax; unsigned int
0x18000cefa  lea     rdx, aDwreturn; "dwReturn"
0x18000cf01  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000cf08  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000cf0d  test    ebx, ebx
0x18000cf0f  jle     loc_18000D19E
0x18000cf15  movzx   ebx, bx
0x18000cf18  or      ebx, 80070000h
0x18000cf1e  jmp     loc_18000D19C
0x18000cf23  movups  xmm0, xmmword ptr [rsi+18h]
0x18000cf27  mov     r8d, [rsi+8]
0x18000cf2b  lea     rax, [rbp+47h+lpFileName]
0x18000cf2f  mov     r9, [rbp+47h+arg_20]; unsigned __int16 *
0x18000cf33  lea     rcx, [rbp+47h+var_40]; struct _GUID
0x18000cf37  mov     edx, [rsi+0Ch]; unsigned int
0x18000cf3a  and     r8d, 1; int
0x18000cf3e  movdqu  xmmword ptr [rbp+47h+var_40.Data1], xmm0
0x18000cf43  mov     [rsp+0C0h+pPromptStruct], rax; unsigned __int16 **
0x18000cf48  call    ?GetSIDKeyFileName@@YAJU_GUID@@KHPEBGPEAPEAG@Z; GetSIDKeyFileName(_GUID,ulong,int,ushort const *,ushort * *)
0x18000cf4d  mov     ebx, eax
0x18000cf4f  test    eax, eax
0x18000cf51  jns     short loc_18000CF5B
0x18000cf53  mov     r9d, 2D6h
0x18000cf59  jmp     short loc_18000CFA2
0x18000cf5b  mov     [rsp+48h], r15
0x18000cf60  lea     rcx, [rbp+47h+hObject]
0x18000cf64  mov     [rsp+0C0h+pusMiniVersion], r15
0x18000cf69  xor     r9d, r9d
0x18000cf6c  mov     dword ptr [rsp+0C0h+hTransaction], r15d
0x18000cf71  xor     r8d, r8d
0x18000cf74  mov     dword ptr [rsp+0C0h+pDataOut], r15d
0x18000cf79  mov     edx, 1F003Fh
0x18000cf7e  mov     [rsp+0C0h+dwFlags], r15d
0x18000cf83  mov     [rsp+0C0h+pPromptStruct], r15
0x18000cf88  call    cs:__imp_NtCreateTransaction
0x18000cf8e  mov     ebx, eax
0x18000cf90  test    eax, eax
0x18000cf92  jns     short loc_18000CFC0
0x18000cf94  mov     [rbp+47h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000cf9c  mov     r9d, 2EBh; unsigned int
0x18000cfa2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000cfa9  mov     ecx, eax; unsigned int
0x18000cfab  lea     rdx, aHr; "hr"
0x18000cfb2  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000cfb7  mov     r15, [rbp+47h+lpFileName]
0x18000cfbb  jmp     loc_18000D1D2
0x18000cfc0  mov     rax, [rbp+47h+hObject]
0x18000cfc4  xor     r9d, r9d; lpSecurityAttributes
0x18000cfc7  mov     [rsp+48h], r15; lpExtendedParameter
0x18000cfcc  xor     r8d, r8d; dwShareMode
0x18000cfcf  mov     [rsp+0C0h+pusMiniVersion], r15; pusMiniVersion
0x18000cfd4  mov     edx, 40000000h; dwDesiredAccess
0x18000cfd9  mov     [rsp+0C0h+hTransaction], rax; hTransaction
0x18000cfde  mov     [rsp+0C0h+pDataOut], r15; hTemplateFile
0x18000cfe3  mov     r15, [rbp+47h+lpFileName]
0x18000cfe7  mov     rcx, r15; lpFileName
0x18000cfea  mov     [rsp+0C0h+dwFlags], 8000002h; dwFlagsAndAttributes
0x18000cff2  mov     dword ptr [rsp+0C0h+pPromptStruct], 4; dwCreationDisposition
0x18000cffa  call    cs:__imp_CreateFileTransactedW
0x18000d000  mov     rdi, rax
0x18000d003  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d007  jnz     loc_18000D0A4
0x18000d00d  call    cs:__imp_GetLastError
0x18000d013  mov     ebx, eax
0x18000d015  cmp     eax, 3
0x18000d018  jnz     short loc_18000D097
0x18000d01a  mov     r8d, [rsi+8]
0x18000d01e  mov     rdx, [rbp+47h+arg_20]
0x18000d022  and     r8d, 1
0x18000d026  mov     rcx, [rbp+47h+arg_28]
0x18000d02a  call    CreateSIDKeyCacheFolder
0x18000d02f  xor     ecx, ecx
0x18000d031  mov     ebx, eax
0x18000d033  test    eax, eax
0x18000d035  jns     short loc_18000D044
0x18000d037  mov     r9d, 307h
0x18000d03d  mov     ecx, eax
0x18000d03f  jmp     loc_18000D0D7
0x18000d044  mov     rax, [rbp+47h+hObject]
0x18000d048  xor     r9d, r9d; lpSecurityAttributes
0x18000d04b  mov     [rsp+48h], rcx; lpExtendedParameter
0x18000d050  mov     edx, 40000000h; dwDesiredAccess
0x18000d055  mov     [rsp+0C0h+pusMiniVersion], rcx; pusMiniVersion
0x18000d05a  mov     [rsp+0C0h+hTransaction], rax; hTransaction
0x18000d05f  mov     [rsp+0C0h+pDataOut], rcx; hTemplateFile
0x18000d064  lea     r8d, [r9+2]; dwShareMode
0x18000d068  mov     [rsp+0C0h+dwFlags], ecx; dwFlagsAndAttributes
0x18000d06c  mov     rcx, r15; lpFileName
0x18000d06f  mov     dword ptr [rsp+0C0h+pPromptStruct], 4; dwCreationDisposition
0x18000d077  call    cs:__imp_CreateFileTransactedW
0x18000d07d  mov     rdi, rax
0x18000d080  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d084  jnz     short loc_18000D0A4
0x18000d086  call    cs:__imp_GetLastError
0x18000d08c  mov     r9d, 319h
0x18000d092  jmp     loc_18000CEF6
0x18000d097  mov     r9d, 320h
0x18000d09d  mov     ecx, ebx
0x18000d09f  jmp     loc_18000CEFA
0x18000d0a4  mov     r12d, [rbp+47h+var_60.cbData]
0x18000d0a8  sub     r12d, [rsi+40h]
0x18000d0ac  sub     r12d, [rsi+44h]
0x18000d0b0  add     r12d, r13d
0x18000d0b3  add     r12d, dword ptr [rbp+47h+Size]
0x18000d0b7  mov     ecx, r12d; unsigned __int64
0x18000d0ba  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000d0bf  mov     r14, rax
0x18000d0c2  test    rax, rax
0x18000d0c5  jnz     short loc_18000D0EF
0x18000d0c7  mov     ebx, 8007000Eh
0x18000d0cc  mov     r9d, 330h; unsigned int
0x18000d0d2  mov     ecx, 8007000Eh; unsigned int
0x18000d0d7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000d0de  lea     rdx, aHr; "hr"
0x18000d0e5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000d0ea  jmp     loc_18000D1D2
0x18000d0ef  mov     r8d, r13d
0x18000d0f2  mov     rdx, rsi; Src
0x18000d0f5  sub     r8d, [rsi+40h]
0x18000d0f9  mov     rcx, r14; void *
0x18000d0fc  sub     r8d, [rsi+44h]; Size
0x18000d100  call    memcpy_0
0x18000d105  mov     eax, [rsi+40h]
0x18000d108  mov     rcx, r13
0x18000d10b  mov     r8d, [rbp+47h+var_60.cbData]; Size
0x18000d10f  sub     rcx, rax
0x18000d112  mov     eax, [rsi+44h]
0x18000d115  mov     rdx, [rbp+47h+var_60.pbData]; Src
0x18000d119  sub     rcx, rax
0x18000d11c  add     rcx, r14; void *
0x18000d11f  call    memcpy_0
0x18000d124  mov     eax, [rsi+40h]
0x18000d127  mov     ecx, [rbp+47h+var_60.cbData]
0x18000d12a  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x18000d12e  sub     rcx, rax
0x18000d131  mov     eax, [rsi+44h]
0x18000d134  mov     rdx, [rbp+47h+Src]; Src
0x18000d138  sub     rcx, rax
0x18000d13b  add     rcx, r13
0x18000d13e  add     rcx, r14; void *
0x18000d141  call    memcpy_0
0x18000d146  lea     r9, [rbp+47h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000d14a  mov     [rsp+0C0h+pPromptStruct], 0; lpOverlapped
0x18000d153  mov     r8d, r12d; nNumberOfBytesToWrite
0x18000d156  mov     rdx, r14; lpBuffer
0x18000d159  mov     rcx, rdi; hFile
0x18000d15c  call    cs:__imp_WriteFile
0x18000d162  test    eax, eax
0x18000d164  jnz     short loc_18000D1B3
0x18000d166  call    cs:__imp_GetLastError
0x18000d16c  mov     r9d, 348h; unsigned int
0x18000d172  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000d179  mov     ecx, eax; unsigned int
0x18000d17b  lea     rdx, aDwreturn; "dwReturn"
0x18000d182  mov     ebx, eax
0x18000d184  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000d189  test    ebx, ebx
0x18000d18b  jle     short loc_18000D196
0x18000d18d  movzx   ebx, bx
0x18000d190  or      ebx, 80070000h
0x18000d196  mov     r12d, 1
0x18000d19c  test    ebx, ebx
0x18000d19e  jns     short loc_18000D1D2
0x18000d1a0  test    r12d, r12d
0x18000d1a3  jz      short loc_18000D1D2
0x18000d1a5  mov     rcx, [rbp+47h+hObject]
0x18000d1a9  mov     dl, 1
0x18000d1ab  call    cs:__imp_NtRollbackTransaction
0x18000d1b1  jmp     short loc_18000D1D2
0x18000d1b3  mov     rcx, [rbp+47h+hObject]
0x18000d1b7  mov     dl, 1
0x18000d1b9  call    cs:__imp_NtCommitTransaction
0x18000d1bf  mov     ebx, eax
0x18000d1c1  test    eax, eax
0x18000d1c3  jns     short loc_18000D1D0
0x18000d1c5  mov     r9d, 355h
0x18000d1cb  jmp     loc_18000D03D
0x18000d1d0  xor     ebx, ebx
0x18000d1d2  mov     rcx, [rbp+47h+hObject]; hObject
0x18000d1d6  lea     rax, [rcx-1]
0x18000d1da  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d1de  ja      short loc_18000D1E6
0x18000d1e0  call    cs:__imp_CloseHandle
0x18000d1e6  lea     rax, [rdi-1]
0x18000d1ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d1ee  ja      short loc_18000D1F9
0x18000d1f0  mov     rcx, rdi; hObject
0x18000d1f3  call    cs:__imp_CloseHandle
0x18000d1f9  mov     rcx, [rbp+47h+var_60.pbData]; hMem
0x18000d1fd  test    rcx, rcx
0x18000d200  jz      short loc_18000D208
0x18000d202  call    cs:__imp_LocalFree
0x18000d208  test    r15, r15
0x18000d20b  jz      short loc_18000D215
0x18000d20d  mov     rcx, r15; lpMem
0x18000d210  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000d215  test    r14, r14
0x18000d218  jz      short loc_18000D222
0x18000d21a  mov     rcx, r14; lpMem
0x18000d21d  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000d222  mov     eax, ebx
0x18000d224  mov     rbx, [rsp+0C0h+arg_8]
0x18000d22c  add     rsp, 90h
0x18000d233  pop     r15
0x18000d235  pop     r14
0x18000d237  pop     r13
0x18000d239  pop     r12
0x18000d23b  pop     rdi
0x18000d23c  pop     rsi
0x18000d23d  pop     rbp
0x18000d23e  retn
```
