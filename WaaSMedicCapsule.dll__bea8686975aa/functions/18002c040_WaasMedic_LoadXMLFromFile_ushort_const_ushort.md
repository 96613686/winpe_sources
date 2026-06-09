# WaasMedic::LoadXMLFromFile(ushort const *,ushort * *)

- ea: `0x18002c040`
- end: `0x18002c231`
- name: `?LoadXMLFromFile@WaasMedic@@YAJPEBGPEAPEAG@Z`
- size: `497`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800555cc`

## callees

- `0x1800023b0`
- `0x180016c9c`
- `0x180024fc4`
- `0x1800251a8`
- `0x18002543c`
- `0x18002c040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c21e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c21e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c098`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c098`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002c0ca`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002c0ca`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c113`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002c113`

## string_xrefs

- `0x18002c05c`: `Invalid pointer input for LoadXMLFromFile`
- `0x18002c139`: `Error in ReadFile 0x%08X\n`
- `0x18002c0e8`: `Failed to allocate memory in LoadXMLFromFile.`
- `0x18002c15d`: `FileUtil: Error when attempting to load XML from file. File name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::LoadXMLFromFile(const WCHAR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  WaasMedic *v3; // rbp
  __int64 v6; // rbx
  void *v7; // rdx
  unsigned int v8; // edi
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD FileSize; // eax
  unsigned __int64 v12; // rdx
  bool v13; // r8
  DWORD v14; // edi
  WaasMedic *v15; // rax
  signed int v16; // eax
  const struct _tlgProvider_t *v17; // rax
  int v18; // r9d
  __int64 v20[7]; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+10h] BYREF
  const WCHAR *v22; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int16 *v23; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    FileW = CreateFileW(this, 0x80000000, 0, 0, 3u, 0x80u, 0);
    v6 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL || (FileSize = GetFileSize(FileW, 0), v14 = FileSize, FileSize == -1) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v15 = (WaasMedic *)WaasMedic::SafeAlloc((WaasMedic *)(FileSize + 2LL), v12, v13);
      v3 = v15;
      if ( !v15 )
      {
        v8 = -2147024882;
        LogLevelW(2u, L"Failed to allocate memory in LoadXMLFromFile.");
        goto LABEL_14;
      }
      if ( ReadFile((HANDLE)v6, v15, v14, 0, 0) )
      {
        v8 = 0;
        *(_QWORD *)a2 = v3;
        goto LABEL_19;
      }
      v16 = GetLastError();
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      LogLevelW(2u, L"Error in ReadFile 0x%08X\n", v8);
    }
    if ( (v8 & 0x80000000) == 0 )
      goto LABEL_19;
    goto LABEL_14;
  }
  v6 = -1;
  LogLevelW(2u, L"Invalid pointer input for LoadXMLFromFile", a3);
  v8 = -2147467261;
LABEL_14:
  WaasMedic::SafeFree(v3, v7);
  LogLevelW(2u, L"FileUtil: Error when attempting to load XML from file. File name: [%s]. hr=0x%08X", this, v8);
  v17 = WaasMedic::TelemetryProvider::Provider();
  if ( *(_DWORD *)v17 > 5u
    && (*((_QWORD *)v17 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v17 + 3) & 0x400000000000LL) == *((_QWORD *)v17 + 3) )
  {
    v21 = v8;
    v23 = &gc_pszVersionString;
    v22 = this;
    v20[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v17,
      (unsigned int)word_1800894BA,
      0,
      v18,
      (__int64)v20,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v21);
  }
LABEL_19:
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  return v8;
}

```

## disassembly

```asm
0x18002c040  push    rbx
0x18002c042  push    rbp
0x18002c043  push    rsi
0x18002c044  push    rdi
0x18002c045  push    r14
0x18002c047  sub     rsp, 50h
0x18002c04b  xor     ebp, ebp
0x18002c04d  mov     rsi, rdx
0x18002c050  mov     r14, rcx
0x18002c053  test    rdx, rdx
0x18002c056  jnz     short loc_18002C075
0x18002c058  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c05c  lea     rdx, aInvalidPointer_2; "Invalid pointer input for LoadXMLFromFi"...
0x18002c063  lea     ecx, [rsi+2]; unsigned __int8
0x18002c066  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c06b  mov     edi, 80004003h
0x18002c070  jmp     loc_18002C152
0x18002c075  mov     [rdx], rbp
0x18002c078  xor     r9d, r9d; lpSecurityAttributes
0x18002c07b  mov     [rsp+78h+hTemplateFile], rbp; hTemplateFile
0x18002c080  mov     edx, 80000000h; dwDesiredAccess
0x18002c085  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002c08d  xor     r8d, r8d; dwShareMode
0x18002c090  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c098  call    cs:__imp_CreateFileW
0x18002c09e  mov     rbx, rax
0x18002c0a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c0a5  jnz     short loc_18002C0C5
0x18002c0a7  call    cs:__imp_GetLastError
0x18002c0ad  mov     edi, eax
0x18002c0af  test    eax, eax
0x18002c0b1  jle     loc_18002C14A
0x18002c0b7  movzx   edi, ax
0x18002c0ba  or      edi, 80070000h
0x18002c0c0  jmp     loc_18002C14A
0x18002c0c5  xor     edx, edx; lpFileSizeHigh
0x18002c0c7  mov     rcx, rbx; hFile
0x18002c0ca  call    cs:__imp_GetFileSize
0x18002c0d0  mov     edi, eax
0x18002c0d2  cmp     eax, 0FFFFFFFFh
0x18002c0d5  jz      short loc_18002C0A7
0x18002c0d7  lea     rcx, [rdi+2]; this
0x18002c0db  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x18002c0e0  mov     rbp, rax
0x18002c0e3  test    rax, rax
0x18002c0e6  jnz     short loc_18002C0FE
0x18002c0e8  lea     rdx, aFailedToAlloca_3; "Failed to allocate memory in LoadXMLFro"...
0x18002c0ef  mov     edi, 8007000Eh
0x18002c0f4  lea     ecx, [rax+2]; unsigned __int8
0x18002c0f7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c0fc  jmp     short loc_18002C152
0x18002c0fe  xor     r9d, r9d; lpNumberOfBytesRead
0x18002c101  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x18002c10a  mov     r8d, edi; nNumberOfBytesToRead
0x18002c10d  mov     rdx, rbp; lpBuffer
0x18002c110  mov     rcx, rbx; hFile
0x18002c113  call    cs:__imp_ReadFile
0x18002c119  test    eax, eax
0x18002c11b  jnz     loc_18002C20C
0x18002c121  call    cs:__imp_GetLastError
0x18002c127  mov     edi, eax
0x18002c129  test    eax, eax
0x18002c12b  jle     short loc_18002C136
0x18002c12d  movzx   edi, ax
0x18002c130  or      edi, 80070000h
0x18002c136  mov     r8d, edi
0x18002c139  lea     rdx, aErrorInReadfil; "Error in ReadFile 0x%08X\n"
0x18002c140  mov     ecx, 2; unsigned __int8
0x18002c145  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c14a  test    edi, edi
0x18002c14c  jns     loc_18002C211
0x18002c152  mov     rcx, rbp; this
0x18002c155  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18002c15a  mov     r9d, edi
0x18002c15d  lea     rdx, aFileutilErrorW; "FileUtil: Error when attempting to load"...
0x18002c164  mov     r8, r14
0x18002c167  mov     ecx, 2; unsigned __int8
0x18002c16c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c171  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18002c176  mov     ecx, [rax]
0x18002c178  cmp     ecx, 5
0x18002c17b  jbe     loc_18002C211
0x18002c181  mov     rdx, [rax+18h]
0x18002c185  mov     r8, 400000000000h
0x18002c18f  mov     rcx, [rax+10h]
0x18002c193  test    r8, rcx
0x18002c196  jz      short loc_18002C211
0x18002c198  mov     rcx, rdx
0x18002c19b  and     rcx, r8
0x18002c19e  cmp     rcx, rdx
0x18002c1a1  jnz     short loc_18002C211
0x18002c1a3  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18002c1aa  mov     [rsp+78h+arg_8], edi
0x18002c1b1  mov     [rsp+78h+arg_18], rcx
0x18002c1b9  lea     rdx, word_1800894BA
0x18002c1c0  lea     rcx, [rsp+78h+arg_8]
0x18002c1c8  mov     [rsp+78h+arg_10], r14
0x18002c1d0  mov     [rsp+78h+var_40], rcx
0x18002c1d5  lea     rcx, [rsp+78h+arg_10]
0x18002c1dd  mov     [rsp+78h+hTemplateFile], rcx
0x18002c1e2  lea     rcx, [rsp+78h+arg_18]
0x18002c1ea  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rcx
0x18002c1ef  lea     rcx, [rsp+78h+var_38]
0x18002c1f4  mov     qword ptr [rsp+78h+dwCreationDisposition], rcx
0x18002c1f9  mov     rcx, rax
0x18002c1fc  mov     [rsp+78h+var_38], 1000000h
0x18002c205  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002c20a  jmp     short loc_18002C211
0x18002c20c  xor     edi, edi
0x18002c20e  mov     [rsi], rbp
0x18002c211  lea     rcx, [rbx-1]
0x18002c215  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c219  ja      short loc_18002C224
0x18002c21b  mov     rcx, rbx; hObject
0x18002c21e  call    cs:__imp_CloseHandle
0x18002c224  mov     eax, edi
0x18002c226  add     rsp, 50h
0x18002c22a  pop     r14
0x18002c22c  pop     rdi
0x18002c22d  pop     rsi
0x18002c22e  pop     rbp
0x18002c22f  pop     rbx
0x18002c230  retn
```
