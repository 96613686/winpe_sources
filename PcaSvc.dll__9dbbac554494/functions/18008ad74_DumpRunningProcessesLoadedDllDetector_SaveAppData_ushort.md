# DumpRunningProcessesLoadedDllDetector_SaveAppData(ushort *)

- ea: `0x18008ad74`
- end: `0x18008b009`
- name: `?DumpRunningProcessesLoadedDllDetector_SaveAppData@@YAXPEAG@Z`
- size: `661`
- prototype: `void __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18008a878`
- `0x18008b4f0`

## callees

- `0x180012920`
- `0x18007a9cf`
- `0x18008ad74`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18008afb7`
- `ntdll!RtlFreeHeap` at `0x18008afb7`
- `ntdll!RtlAllocateHeap` at `0x18008aecf`
- `ntdll!RtlAllocateHeap` at `0x18008aecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008adfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ae60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008af4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008adfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ae60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008af4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008af9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008af9a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008ae98`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008af10`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008ae98`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18008af10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008ae52`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008ae52`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008af45`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008af45`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008adf2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008adf2`

## string_xrefs

- `0x18008ae14`: `DumpRunningProcessesLoadedDllDetector_SaveAppData`
- `0x18008af62`: `DumpRunningProcessesLoadedDllDetector_SaveAppData`
- `0x18008af89`: `DumpRunningProcessesLoadedDllDetector_SaveAppData`
- `0x18008afcc`: `DumpRunningProcessesLoadedDllDetector_SaveAppData`
- `0x18008afbf`: `No process DLL data to save.`
- `0x18008ae66`: `Failed to create ProcessLoadedDllListFinal.txt [%d]`
- `0x18008adeb`: `%windir%\appcompat\pca\ProcessLoadedDllListFinal.txt`
- `0x18008af55`: `Failed to write to ProcessLoadedDllListFinal.txt [%d]`
- `0x18008af7c`: `BytesToWrite does not match BytesWritten when writing to ProcessLoadedDllListFinal.txt`

## pseudocode

```c
void __fastcall DumpRunningProcessesLoadedDllDetector_SaveAppData(LPCWCH lpWideCharStr)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  DWORD LastError; // eax
  const char *v5; // r9
  int v6; // r8d
  HANDLE FileW; // r15
  int v8; // eax
  int v9; // r14d
  CHAR *v10; // rsi
  CHAR *Heap; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-278h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-278h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Dst[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(Dst, 0, 0x20Au);
  NumberOfBytesWritten = 0;
  if ( !lpWideCharStr )
    goto LABEL_23;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( lpWideCharStr[v3] );
  if ( v3 )
  {
    if ( !ExpandEnvironmentStringsW(L"%windir%\\appcompat\\pca\\ProcessLoadedDllListFinal.txt", Dst, 0x104u) )
    {
      LastError = GetLastError();
      v5 = "ExpandEnvironmentStringsW failed [%d]";
      v6 = 2051;
LABEL_7:
      dwCreationDisposition[0] = LastError;
      AslLogCallPrintf(
        1,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
        v6,
        (_DWORD)v5,
        *(_QWORD *)dwCreationDisposition);
      return;
    }
    FileW = CreateFileW(Dst, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v5 = "Failed to create ProcessLoadedDllListFinal.txt [%d]";
      v6 = 2064;
      goto LABEL_7;
    }
    v8 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    v9 = v8;
    if ( v8 )
    {
      Heap = (CHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v8);
      v10 = Heap;
      if ( Heap )
      {
        if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, -1, Heap, v9, 0, 0) )
        {
          do
            ++v2;
          while ( v10[v2] );
          if ( WriteFile(FileW, v10, v2, &NumberOfBytesWritten, 0) )
          {
            if ( (_DWORD)v2 != NumberOfBytesWritten )
              AslLogCallPrintf(
                1,
                (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
                2096,
                (unsigned int)"BytesToWrite does not match BytesWritten when writing to ProcessLoadedDllListFinal.txt");
          }
          else
          {
            dwCreationDispositiona[0] = GetLastError();
            AslLogCallPrintf(
              1,
              (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
              2092,
              (unsigned int)"Failed to write to ProcessLoadedDllListFinal.txt [%d]",
              *(_QWORD *)dwCreationDispositiona);
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
            2085,
            (unsigned int)"Failed to convert to UTF-8 for final file");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
          2079,
          (unsigned int)"Failed to allocate memory for UTF-8 content");
      }
    }
    else
    {
      v10 = 0;
      AslLogCallPrintf(
        1,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
        2072,
        (unsigned int)"Failed to get UTF-8 size for final file");
    }
    CloseHandle(FileW);
    if ( v10 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  }
  else
  {
LABEL_23:
    AslLogCallPrintf(
      3,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_SaveAppData",
      2045,
      (unsigned int)"No process DLL data to save.");
  }
}

```

## disassembly

```asm
0x18008ad74  mov     [rsp+arg_8], rbx
0x18008ad79  mov     [rsp+arg_10], rbp
0x18008ad7e  push    rsi
0x18008ad7f  push    rdi
0x18008ad80  push    r12
0x18008ad82  push    r14
0x18008ad84  push    r15
0x18008ad86  sub     rsp, 270h
0x18008ad8d  mov     rax, cs:__security_cookie
0x18008ad94  xor     rax, rsp
0x18008ad97  mov     [rsp+298h+var_38], rax
0x18008ad9f  mov     rbp, rcx
0x18008ada2  xor     edx, edx; Val
0x18008ada4  lea     rcx, [rsp+298h+Dst]; void *
0x18008ada9  mov     r8d, 20Ah; Size
0x18008adaf  call    memset_0
0x18008adb4  xor     r12d, r12d
0x18008adb7  mov     [rsp+298h+NumberOfBytesWritten], r12d
0x18008adbc  test    rbp, rbp
0x18008adbf  jz      loc_18008AFBF
0x18008adc5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008adc9  mov     rax, rbx
0x18008adcc  inc     rax
0x18008adcf  cmp     [rbp+rax*2+0], r12w
0x18008add5  jnz     short loc_18008ADCC
0x18008add7  test    rax, rax
0x18008adda  jz      loc_18008AFBF
0x18008ade0  mov     r8d, 104h; nSize
0x18008ade6  lea     rdx, [rsp+298h+Dst]; lpDst
0x18008adeb  lea     rcx, aWindirAppcompa_0; "%windir%\\appcompat\\pca\\ProcessLoaded"...
0x18008adf2  call    cs:__imp_ExpandEnvironmentStringsW
0x18008adf8  test    eax, eax
0x18008adfa  jnz     short loc_18008AE29
0x18008adfc  call    cs:__imp_GetLastError
0x18008ae02  lea     r9, aExpandenvironm_0; "ExpandEnvironmentStringsW failed [%d]"
0x18008ae09  mov     r8d, 803h
0x18008ae0f  mov     ecx, 1
0x18008ae14  lea     rdx, aDumprunningpro_12; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008ae1b  mov     [rsp+298h+dwCreationDisposition], eax
0x18008ae1f  call    AslLogCallPrintf
0x18008ae24  jmp     loc_18008AFDD
0x18008ae29  xor     r9d, r9d; lpSecurityAttributes
0x18008ae2c  mov     [rsp+298h+hTemplateFile], r12; hTemplateFile
0x18008ae31  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008ae39  lea     rcx, [rsp+298h+Dst]; lpFileName
0x18008ae3e  mov     edx, 40000000h; dwDesiredAccess
0x18008ae43  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x18008ae4b  lea     edi, [r9+1]
0x18008ae4f  mov     r8d, edi; dwShareMode
0x18008ae52  call    cs:__imp_CreateFileW
0x18008ae58  mov     r15, rax
0x18008ae5b  cmp     rax, rbx
0x18008ae5e  jnz     short loc_18008AE77
0x18008ae60  call    cs:__imp_GetLastError
0x18008ae66  lea     r9, aFailedToCreate_63; "Failed to create ProcessLoadedDllListFi"...
0x18008ae6d  mov     r8d, 810h
0x18008ae73  mov     ecx, edi
0x18008ae75  jmp     short loc_18008AE14
0x18008ae77  mov     [rsp+298h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18008ae7c  mov     r9d, ebx; cchWideChar
0x18008ae7f  mov     [rsp+298h+hTemplateFile], r12; lpDefaultChar
0x18008ae84  mov     r8, rbp; lpWideCharStr
0x18008ae87  mov     [rsp+298h+dwFlagsAndAttributes], r12d; cbMultiByte
0x18008ae8c  xor     edx, edx; dwFlags
0x18008ae8e  mov     ecx, 0FDE9h; CodePage
0x18008ae93  mov     qword ptr [rsp+298h+dwCreationDisposition], r12; lpMultiByteStr
0x18008ae98  call    cs:__imp_WideCharToMultiByte
0x18008ae9e  movsxd  r14, eax
0x18008aea1  test    eax, eax
0x18008aea3  jnz     short loc_18008AEBA
0x18008aea5  mov     rsi, r12
0x18008aea8  lea     r9, aFailedToGetUtf_0; "Failed to get UTF-8 size for final file"
0x18008aeaf  mov     r8d, 818h
0x18008aeb5  jmp     loc_18008AF89
0x18008aeba  mov     rcx, gs:60h
0x18008aec3  mov     r8, r14; Size
0x18008aec6  mov     edx, 8; Flags
0x18008aecb  mov     rcx, [rcx+30h]; HeapHandle
0x18008aecf  call    cs:__imp_RtlAllocateHeap
0x18008aed5  mov     rsi, rax
0x18008aed8  test    rax, rax
0x18008aedb  jnz     short loc_18008AEEF
0x18008aedd  lea     r9, aFailedToAlloca_26; "Failed to allocate memory for UTF-8 con"...
0x18008aee4  mov     r8d, 81Fh
0x18008aeea  jmp     loc_18008AF89
0x18008aeef  mov     [rsp+298h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18008aef4  mov     r9d, ebx; cchWideChar
0x18008aef7  mov     [rsp+298h+hTemplateFile], r12; lpDefaultChar
0x18008aefc  mov     r8, rbp; lpWideCharStr
0x18008aeff  mov     [rsp+298h+dwFlagsAndAttributes], r14d; cbMultiByte
0x18008af04  xor     edx, edx; dwFlags
0x18008af06  mov     ecx, 0FDE9h; CodePage
0x18008af0b  mov     qword ptr [rsp+298h+dwCreationDisposition], rsi; lpMultiByteStr
0x18008af10  call    cs:__imp_WideCharToMultiByte
0x18008af16  test    eax, eax
0x18008af18  jnz     short loc_18008AF29
0x18008af1a  lea     r9, aFailedToConver_18; "Failed to convert to UTF-8 for final fi"...
0x18008af21  mov     r8d, 825h
0x18008af27  jmp     short loc_18008AF89
0x18008af29  inc     rbx
0x18008af2c  cmp     [rsi+rbx], r12b
0x18008af30  jnz     short loc_18008AF29
0x18008af32  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008af37  mov     qword ptr [rsp+298h+dwCreationDisposition], r12; lpOverlapped
0x18008af3c  mov     r8d, ebx; nNumberOfBytesToWrite
0x18008af3f  mov     rdx, rsi; lpBuffer
0x18008af42  mov     rcx, r15; hFile
0x18008af45  call    cs:__imp_WriteFile
0x18008af4b  test    eax, eax
0x18008af4d  jnz     short loc_18008AF76
0x18008af4f  call    cs:__imp_GetLastError
0x18008af55  lea     r9, aFailedToWriteT_1; "Failed to write to ProcessLoadedDllList"...
0x18008af5c  mov     r8d, 82Ch
0x18008af62  lea     rdx, aDumprunningpro_12; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008af69  mov     [rsp+298h+dwCreationDisposition], eax
0x18008af6d  mov     ecx, edi
0x18008af6f  call    AslLogCallPrintf
0x18008af74  jmp     short loc_18008AF97
0x18008af76  cmp     ebx, [rsp+298h+NumberOfBytesWritten]
0x18008af7a  jz      short loc_18008AF97
0x18008af7c  lea     r9, aBytestowriteDo; "BytesToWrite does not match BytesWritte"...
0x18008af83  mov     r8d, 830h
0x18008af89  lea     rdx, aDumprunningpro_12; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008af90  mov     ecx, edi
0x18008af92  call    AslLogCallPrintf
0x18008af97  mov     rcx, r15; hObject
0x18008af9a  call    cs:__imp_CloseHandle
0x18008afa0  test    rsi, rsi
0x18008afa3  jz      short loc_18008AFDD
0x18008afa5  mov     rcx, gs:60h
0x18008afae  mov     r8, rsi; P
0x18008afb1  xor     edx, edx; Flags
0x18008afb3  mov     rcx, [rcx+30h]; HeapHandle
0x18008afb7  call    cs:__imp_RtlFreeHeap
0x18008afbd  jmp     short loc_18008AFDD
0x18008afbf  lea     r9, aNoProcessDllDa; "No process DLL data to save."
0x18008afc6  mov     r8d, 7FDh
0x18008afcc  lea     rdx, aDumprunningpro_12; "DumpRunningProcessesLoadedDllDetector_S"...
0x18008afd3  mov     ecx, 3
0x18008afd8  call    AslLogCallPrintf
0x18008afdd  mov     rcx, [rsp+298h+var_38]
0x18008afe5  xor     rcx, rsp; StackCookie
0x18008afe8  call    __security_check_cookie
0x18008afed  lea     r11, [rsp+298h+var_28]
0x18008aff5  mov     rbx, [r11+38h]
0x18008aff9  mov     rbp, [r11+40h]
0x18008affd  mov     rsp, r11
0x18008b000  pop     r15
0x18008b002  pop     r14
0x18008b004  pop     r12
0x18008b006  pop     rdi
0x18008b007  pop     rsi
0x18008b008  retn
```
