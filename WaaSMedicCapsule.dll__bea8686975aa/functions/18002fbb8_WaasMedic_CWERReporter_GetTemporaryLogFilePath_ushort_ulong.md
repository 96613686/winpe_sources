# WaasMedic::CWERReporter::GetTemporaryLogFilePath(ushort *,ulong)

- ea: `0x18002fbb8`
- end: `0x18002fd74`
- name: `?GetTemporaryLogFilePath@CWERReporter@WaasMedic@@AEAAJPEAGK@Z`
- size: `444`
- prototype: `int(WaasMedic::CWERReporter *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ed2c`
- `0x18002ede4`

## callees

- `0x180003bb0`
- `0x18000a5d0`
- `0x18002543c`
- `0x18002fbb8`
- `0x180030fbc`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fc27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fc27`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fc10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fc10`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fd4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fd4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc65`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002fc8d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002fc8d`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002fc49`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002fc49`

## string_xrefs

- `0x18002fc09`: `kernelbase.dll`
- `0x18002fc32`: `Failed to get GetTempPath2W. Falling back to GetTempPath.`
- `0x18002fc1d`: `GetTempPath2W`
- `0x18002fc99`: `Failed to create temporary folder GUID path! hr = 0x%08x`
- `0x18002fc7d`: `Failed to fetch temporary log file path! hr = 0x%08x`
- `0x18002fd2f`: `Failed to print format string for temporary log file path! hr = 0x%08x`

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
0x18002fbb8  push    rbp
0x18002fbba  push    rbx
0x18002fbbb  push    rsi
0x18002fbbc  push    rdi
0x18002fbbd  push    r12
0x18002fbbf  push    r13
0x18002fbc1  push    r14
0x18002fbc3  push    r15
0x18002fbc5  lea     rbp, [rsp-1Fh]
0x18002fbca  sub     rsp, 0A8h
0x18002fbd1  mov     rax, cs:__security_cookie
0x18002fbd8  xor     rax, rsp
0x18002fbdb  mov     [rbp+57h+var_50], rax
0x18002fbdf  mov     rdi, rdx
0x18002fbe2  mov     [rbp+57h+var_68], rdx
0x18002fbe6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002fbed  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18002fbf2  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x18002fbf7  movzx   r8d, al
0x18002fbfb  xor     r8d, 1
0x18002fbff  add     r8d, 10h
0x18002fc03  shl     r8d, 7; dwFlags
0x18002fc07  xor     edx, edx; hFile
0x18002fc09  lea     rcx, LibFileName; "kernelbase.dll"
0x18002fc10  call    cs:__imp_LoadLibraryExW
0x18002fc16  mov     rbx, rax
0x18002fc19  mov     [rbp+57h+var_70], rax
0x18002fc1d  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18002fc24  mov     rcx, rax; hModule
0x18002fc27  call    cs:__imp_GetProcAddress
0x18002fc2d  test    rax, rax
0x18002fc30  jnz     short loc_18002FC51
0x18002fc32  lea     rdx, aFailedToGetGet; "Failed to get GetTempPath2W. Falling ba"...
0x18002fc39  lea     ecx, [rax+3]; unsigned __int8
0x18002fc3c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002fc41  mov     rdx, rdi; lpBuffer
0x18002fc44  mov     ecx, 104h; nBufferLength
0x18002fc49  call    cs:__imp_GetTempPathW
0x18002fc4f  jmp     short loc_18002FC5E
0x18002fc51  mov     rdx, rdi
0x18002fc54  mov     ecx, 104h
0x18002fc59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc5e  mov     dword ptr [rbp+57h+var_70], eax
0x18002fc61  test    eax, eax
0x18002fc63  jnz     short loc_18002FC89
0x18002fc65  call    cs:__imp_GetLastError
0x18002fc6b  mov     edi, eax
0x18002fc6d  test    eax, eax
0x18002fc6f  jle     short loc_18002FC7A
0x18002fc71  movzx   edi, ax
0x18002fc74  or      edi, 80070000h
0x18002fc7a  mov     r8d, edi
0x18002fc7d  lea     rdx, aFailedToFetchT; "Failed to fetch temporary log file path"...
0x18002fc84  jmp     loc_18002FD39
0x18002fc89  lea     rcx, [rbp+57h+pguid]; pguid
0x18002fc8d  call    cs:__imp_CoCreateGuid
0x18002fc93  mov     edi, eax
0x18002fc95  test    eax, eax
0x18002fc97  jns     short loc_18002FCA5
0x18002fc99  lea     rdx, aFailedToCreate_15; "Failed to create temporary folder GUID "...
0x18002fca0  jmp     loc_18002FD36
0x18002fca5  movzx   r8d, [rbp+57h+pguid.Data4+7]
0x18002fcaa  movzx   r9d, [rbp+57h+pguid.Data4+6]
0x18002fcaf  movzx   r10d, [rbp+57h+pguid.Data4+5]
0x18002fcb4  movzx   r11d, [rbp+57h+pguid.Data4+4]
0x18002fcb9  movzx   edi, [rbp+57h+pguid.Data4+3]
0x18002fcbd  movzx   esi, [rbp+57h+pguid.Data4+2]
0x18002fcc1  movzx   r14d, [rbp+57h+pguid.Data4+1]
0x18002fcc6  movzx   r15d, [rbp+57h+pguid.Data4]
0x18002fccb  movzx   r12d, [rbp+57h+pguid.Data3]
0x18002fcd0  movzx   r13d, [rbp+57h+pguid.Data2]
0x18002fcd5  mov     edx, 104h
0x18002fcda  mov     ecx, dword ptr [rbp+57h+var_70]
0x18002fcdd  sub     edx, ecx; unsigned __int64
0x18002fcdf  mov     eax, ecx
0x18002fce1  mov     rcx, [rbp+57h+var_68]
0x18002fce5  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18002fce9  mov     [rsp+0E0h+var_78], r8d
0x18002fcee  mov     [rsp+0E0h+var_80], r9d
0x18002fcf3  mov     [rsp+0E0h+var_88], r10d
0x18002fcf8  mov     [rsp+0E0h+var_90], r11d
0x18002fcfd  mov     [rsp+0E0h+var_98], edi
0x18002fd01  mov     [rsp+0E0h+var_A0], esi
0x18002fd05  mov     [rsp+0E0h+var_A8], r14d
0x18002fd0a  mov     [rsp+0E0h+var_B0], r15d
0x18002fd0f  mov     [rsp+0E0h+var_B8], r12d
0x18002fd14  mov     [rsp+0E0h+var_C0], r13d
0x18002fd19  mov     r9d, [rbp+57h+pguid.Data1]
0x18002fd1d  lea     r8, a08x04x04x02x02; "_%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x18002fd24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002fd29  mov     edi, eax
0x18002fd2b  test    eax, eax
0x18002fd2d  jns     short loc_18002FD44
0x18002fd2f  lea     rdx, aFailedToPrintF_0; "Failed to print format string for tempo"...
0x18002fd36  mov     r8d, eax
0x18002fd39  mov     ecx, 2; unsigned __int8
0x18002fd3e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002fd43  nop
0x18002fd44  test    rbx, rbx
0x18002fd47  jz      short loc_18002FD52
0x18002fd49  mov     rcx, rbx; hLibModule
0x18002fd4c  call    cs:__imp_FreeLibrary
0x18002fd52  mov     eax, edi
0x18002fd54  mov     rcx, [rbp+57h+var_50]
0x18002fd58  xor     rcx, rsp; StackCookie
0x18002fd5b  call    __security_check_cookie
0x18002fd60  add     rsp, 0A8h
0x18002fd67  pop     r15
0x18002fd69  pop     r14
0x18002fd6b  pop     r13
0x18002fd6d  pop     r12
0x18002fd6f  pop     rdi
0x18002fd70  pop     rsi
0x18002fd71  pop     rbx
0x18002fd72  pop     rbp
0x18002fd73  retn
```
