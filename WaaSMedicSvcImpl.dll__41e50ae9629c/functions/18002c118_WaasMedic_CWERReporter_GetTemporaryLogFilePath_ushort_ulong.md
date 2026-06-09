# WaasMedic::CWERReporter::GetTemporaryLogFilePath(ushort *,ulong)

- ea: `0x18002c118`
- end: `0x18002c2d4`
- name: `?GetTemporaryLogFilePath@CWERReporter@WaasMedic@@AEAAJPEAGK@Z`
- size: `444`
- prototype: `int(WaasMedic::CWERReporter *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002b63c`

## callees

- `0x1800050a0`
- `0x18000c638`
- `0x180028b9c`
- `0x18002c118`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c187`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c187`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c2ac`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c2ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c170`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1c5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c1ed`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c1ed`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002c1a9`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002c1a9`

## string_xrefs

- `0x18002c169`: `kernelbase.dll`
- `0x18002c17d`: `GetTempPath2W`
- `0x18002c1dd`: `Failed to fetch temporary log file path! hr = 0x%08x`
- `0x18002c192`: `Failed to get GetTempPath2W. Falling back to GetTempPath.`
- `0x18002c1f9`: `Failed to create temporary folder GUID path! hr = 0x%08x`
- `0x18002c28f`: `Failed to print format string for temporary log file path! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CWERReporter::GetTemporaryLogFilePath(
        WaasMedic::CWERReporter *this,
        unsigned __int16 *a2)
{
  bool IsTestSigningEnabled; // al
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  signed int LastError; // eax
  unsigned int v8; // edi
  HRESULT v9; // eax
  const unsigned __int16 *v10; // rdx
  DWORD v12; // [rsp+70h] [rbp-19h]
  GUID pguid; // [rsp+80h] [rbp-9h] BYREF

  pguid = GUID_NULL;
  IsTestSigningEnabled = WaasMedic::IsTestSigningEnabled(this);
  Library = LoadLibraryExW(L"kernelbase.dll", 0, (!IsTestSigningEnabled + 16) << 7);
  ProcAddress = GetProcAddress(Library, "GetTempPath2W");
  if ( ProcAddress )
  {
    TempPathW = ((__int64 (__fastcall *)(__int64, unsigned __int16 *))ProcAddress)(260, a2);
  }
  else
  {
    LogLevelW(3u, L"Failed to get GetTempPath2W. Falling back to GetTempPath.");
    TempPathW = GetTempPathW(0x104u, a2);
  }
  v12 = TempPathW;
  if ( TempPathW )
  {
    v9 = CoCreateGuid(&pguid);
    v8 = v9;
    if ( v9 >= 0 )
    {
      v9 = StringCchPrintfW(
             &a2[v12],
             260 - v12,
             L"_%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
             pguid.Data1,
             pguid.Data2,
             pguid.Data3,
             pguid.Data4[0],
             pguid.Data4[1],
             pguid.Data4[2],
             pguid.Data4[3],
             pguid.Data4[4],
             pguid.Data4[5],
             pguid.Data4[6],
             pguid.Data4[7]);
      v8 = v9;
      if ( v9 >= 0 )
        goto LABEL_13;
      v10 = L"Failed to print format string for temporary log file path! hr = 0x%08x";
    }
    else
    {
      v10 = L"Failed to create temporary folder GUID path! hr = 0x%08x";
    }
    LogLevelW(2u, v10, (unsigned int)v9);
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to fetch temporary log file path! hr = 0x%08x", v8);
  }
LABEL_13:
  if ( Library )
    FreeLibrary(Library);
  return v8;
}

```

## disassembly

```asm
0x18002c118  push    rbp
0x18002c11a  push    rbx
0x18002c11b  push    rsi
0x18002c11c  push    rdi
0x18002c11d  push    r12
0x18002c11f  push    r13
0x18002c121  push    r14
0x18002c123  push    r15
0x18002c125  lea     rbp, [rsp-1Fh]
0x18002c12a  sub     rsp, 0A8h
0x18002c131  mov     rax, cs:__security_cookie
0x18002c138  xor     rax, rsp
0x18002c13b  mov     [rbp+57h+var_50], rax
0x18002c13f  mov     rdi, rdx
0x18002c142  mov     [rbp+57h+var_68], rdx
0x18002c146  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002c14d  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18002c152  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x18002c157  movzx   r8d, al
0x18002c15b  xor     r8d, 1
0x18002c15f  add     r8d, 10h
0x18002c163  shl     r8d, 7; dwFlags
0x18002c167  xor     edx, edx; hFile
0x18002c169  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002c170  call    cs:__imp_LoadLibraryExW
0x18002c176  mov     rbx, rax
0x18002c179  mov     [rbp+57h+var_70], rax
0x18002c17d  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18002c184  mov     rcx, rax; hModule
0x18002c187  call    cs:__imp_GetProcAddress
0x18002c18d  test    rax, rax
0x18002c190  jnz     short loc_18002C1B1
0x18002c192  lea     rdx, aFailedToGetGet; "Failed to get GetTempPath2W. Falling ba"...
0x18002c199  lea     ecx, [rax+3]; unsigned __int8
0x18002c19c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c1a1  mov     rdx, rdi; lpBuffer
0x18002c1a4  mov     ecx, 104h; nBufferLength
0x18002c1a9  call    cs:__imp_GetTempPathW
0x18002c1af  jmp     short loc_18002C1BE
0x18002c1b1  mov     rdx, rdi
0x18002c1b4  mov     ecx, 104h
0x18002c1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1be  mov     dword ptr [rbp+57h+var_70], eax
0x18002c1c1  test    eax, eax
0x18002c1c3  jnz     short loc_18002C1E9
0x18002c1c5  call    cs:__imp_GetLastError
0x18002c1cb  mov     edi, eax
0x18002c1cd  test    eax, eax
0x18002c1cf  jle     short loc_18002C1DA
0x18002c1d1  movzx   edi, ax
0x18002c1d4  or      edi, 80070000h
0x18002c1da  mov     r8d, edi
0x18002c1dd  lea     rdx, aFailedToFetchT; "Failed to fetch temporary log file path"...
0x18002c1e4  jmp     loc_18002C299
0x18002c1e9  lea     rcx, [rbp+57h+pguid]; pguid
0x18002c1ed  call    cs:__imp_CoCreateGuid
0x18002c1f3  mov     edi, eax
0x18002c1f5  test    eax, eax
0x18002c1f7  jns     short loc_18002C205
0x18002c1f9  lea     rdx, aFailedToCreate_12; "Failed to create temporary folder GUID "...
0x18002c200  jmp     loc_18002C296
0x18002c205  movzx   r8d, [rbp+57h+pguid.Data4+7]
0x18002c20a  movzx   r9d, [rbp+57h+pguid.Data4+6]
0x18002c20f  movzx   r10d, [rbp+57h+pguid.Data4+5]
0x18002c214  movzx   r11d, [rbp+57h+pguid.Data4+4]
0x18002c219  movzx   edi, [rbp+57h+pguid.Data4+3]
0x18002c21d  movzx   esi, [rbp+57h+pguid.Data4+2]
0x18002c221  movzx   r14d, [rbp+57h+pguid.Data4+1]
0x18002c226  movzx   r15d, [rbp+57h+pguid.Data4]
0x18002c22b  movzx   r12d, [rbp+57h+pguid.Data3]
0x18002c230  movzx   r13d, [rbp+57h+pguid.Data2]
0x18002c235  mov     edx, 104h
0x18002c23a  mov     ecx, dword ptr [rbp+57h+var_70]
0x18002c23d  sub     edx, ecx; unsigned __int64
0x18002c23f  mov     eax, ecx
0x18002c241  mov     rcx, [rbp+57h+var_68]
0x18002c245  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18002c249  mov     [rsp+0E0h+var_78], r8d
0x18002c24e  mov     [rsp+0E0h+var_80], r9d
0x18002c253  mov     [rsp+0E0h+var_88], r10d
0x18002c258  mov     [rsp+0E0h+var_90], r11d
0x18002c25d  mov     [rsp+0E0h+var_98], edi
0x18002c261  mov     [rsp+0E0h+var_A0], esi
0x18002c265  mov     [rsp+0E0h+var_A8], r14d
0x18002c26a  mov     [rsp+0E0h+var_B0], r15d
0x18002c26f  mov     [rsp+0E0h+var_B8], r12d
0x18002c274  mov     [rsp+0E0h+var_C0], r13d
0x18002c279  mov     r9d, [rbp+57h+pguid.Data1]
0x18002c27d  lea     r8, a08x04x04x02x02; "_%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x18002c284  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c289  mov     edi, eax
0x18002c28b  test    eax, eax
0x18002c28d  jns     short loc_18002C2A4
0x18002c28f  lea     rdx, aFailedToPrintF_0; "Failed to print format string for tempo"...
0x18002c296  mov     r8d, eax
0x18002c299  mov     ecx, 2; unsigned __int8
0x18002c29e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002c2a3  nop
0x18002c2a4  test    rbx, rbx
0x18002c2a7  jz      short loc_18002C2B2
0x18002c2a9  mov     rcx, rbx; hLibModule
0x18002c2ac  call    cs:__imp_FreeLibrary
0x18002c2b2  mov     eax, edi
0x18002c2b4  mov     rcx, [rbp+57h+var_50]
0x18002c2b8  xor     rcx, rsp; StackCookie
0x18002c2bb  call    __security_check_cookie
0x18002c2c0  add     rsp, 0A8h
0x18002c2c7  pop     r15
0x18002c2c9  pop     r14
0x18002c2cb  pop     r13
0x18002c2cd  pop     r12
0x18002c2cf  pop     rdi
0x18002c2d0  pop     rsi
0x18002c2d1  pop     rbx
0x18002c2d2  pop     rbp
0x18002c2d3  retn
```
