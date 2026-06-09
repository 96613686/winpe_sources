# UtilMtxcluIsSameNodeW

- ea: `0x18001ad1c`
- end: `0x18001ae2e`
- name: `UtilMtxcluIsSameNodeW`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180076de0`

## callees

- `0x180003cf0`
- `0x18001ad1c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001ad3a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001ad3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ada1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ada1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ae1d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ae1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adac`

## string_xrefs

- `0x18001ad6f`: `com\complus\dtc\shared\util\basetminstance.cpp`
- `0x18001adf6`: `com\complus\dtc\shared\util\basetminstance.cpp`
- `0x18001ad63`: `Failed to load mtxclu DLL`
- `0x18001ad33`: `mtxclu.dll`

## pseudocode

```c
__int64 __fastcall UtilMtxcluIsSameNodeW(__int64 a1, __int64 a2, __int64 a3)
{
  HMODULE Library; // rax
  HMODULE v7; // rdi
  signed int v8; // eax
  unsigned int v9; // ebx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  const wchar_t *v12; // rax
  __int64 v13; // r9
  __int64 v15; // [rsp+28h] [rbp-40h]

  Library = LoadLibraryExA("mtxclu.dll", 0, 0);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "MtxCluIsSameNodeW");
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(__int64, __int64, __int64))ProcAddress)(a1, a2, a3);
      if ( (v9 & 0x80000000) == 0 )
      {
LABEL_12:
        FreeLibrary(v7);
        return v9;
      }
      v12 = L"Failed in MtxCluIsSameNodeW";
      v13 = 120;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v12 = L"Unable to bind to MtxCluIsSameNodeW";
      v13 = 111;
    }
    LODWORD(v15) = v9;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\basetminstance.cpp",
      v13,
      L"UtilMtxcluIsSameNodeW",
      v15,
      v12);
    goto LABEL_12;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  LODWORD(v15) = v9;
  TraceStringInline(
    7,
    1,
    L"com\\complus\\dtc\\shared\\util\\basetminstance.cpp",
    100,
    L"UtilMtxcluIsSameNodeW",
    v15,
    L"Failed to load mtxclu DLL");
  return v9;
}

```

## disassembly

```asm
0x18001ad1c  push    rbx
0x18001ad1e  push    rbp
0x18001ad1f  push    rsi
0x18001ad20  push    rdi
0x18001ad21  sub     rsp, 48h
0x18001ad25  mov     rbx, r8
0x18001ad28  mov     rsi, rdx
0x18001ad2b  mov     rbp, rcx
0x18001ad2e  xor     r8d, r8d; dwFlags
0x18001ad31  xor     edx, edx; hFile
0x18001ad33  lea     rcx, aMtxcluDll_0; "mtxclu.dll"
0x18001ad3a  call    cs:__imp_LoadLibraryExA
0x18001ad40  mov     rdi, rax
0x18001ad43  test    rax, rax
0x18001ad46  jnz     short loc_18001AD97
0x18001ad48  call    cs:__imp_GetLastError
0x18001ad4e  mov     ebx, eax
0x18001ad50  test    eax, eax
0x18001ad52  jle     short loc_18001AD5D
0x18001ad54  movzx   ebx, ax
0x18001ad57  or      ebx, 80070000h
0x18001ad5d  mov     r9d, 64h ; 'd'
0x18001ad63  lea     rax, aFailedToLoadMt; "Failed to load mtxclu DLL"
0x18001ad6a  mov     [rsp+68h+var_38], rax
0x18001ad6f  lea     r8, aComComplusDtcS_3; "com\\complus\\dtc\\shared\\util\\basetm"...
0x18001ad76  lea     rax, aUtilmtxcluissa; "UtilMtxcluIsSameNodeW"
0x18001ad7d  mov     dword ptr [rsp+68h+var_40], ebx
0x18001ad81  mov     [rsp+68h+var_48], rax
0x18001ad86  lea     edx, [r9-63h]
0x18001ad8a  lea     ecx, [rdx+6]
0x18001ad8d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ad92  jmp     loc_18001AE23
0x18001ad97  lea     rdx, aMtxcluissameno_3; "MtxCluIsSameNodeW"
0x18001ad9e  mov     rcx, rdi; hModule
0x18001ada1  call    cs:__imp_GetProcAddress
0x18001ada7  test    rax, rax
0x18001adaa  jnz     short loc_18001ADD0
0x18001adac  call    cs:__imp_GetLastError
0x18001adb2  mov     ebx, eax
0x18001adb4  test    eax, eax
0x18001adb6  jle     short loc_18001ADC1
0x18001adb8  movzx   ebx, ax
0x18001adbb  or      ebx, 80070000h
0x18001adc1  lea     rax, aUnableToBindTo; "Unable to bind to MtxCluIsSameNodeW"
0x18001adc8  mov     r9d, 6Fh ; 'o'
0x18001adce  jmp     short loc_18001ADF1
0x18001add0  mov     r8, rbx
0x18001add3  mov     rdx, rsi
0x18001add6  mov     rcx, rbp
0x18001add9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adde  mov     ebx, eax
0x18001ade0  test    eax, eax
0x18001ade2  jns     short loc_18001AE1A
0x18001ade4  lea     rax, aFailedInMtxclu; "Failed in MtxCluIsSameNodeW"
0x18001adeb  mov     r9d, 78h ; 'x'
0x18001adf1  mov     [rsp+68h+var_38], rax
0x18001adf6  lea     r8, aComComplusDtcS_3; "com\\complus\\dtc\\shared\\util\\basetm"...
0x18001adfd  mov     edx, 1
0x18001ae02  mov     dword ptr [rsp+68h+var_40], ebx
0x18001ae06  lea     rax, aUtilmtxcluissa; "UtilMtxcluIsSameNodeW"
0x18001ae0d  mov     [rsp+68h+var_48], rax
0x18001ae12  lea     ecx, [rdx+6]
0x18001ae15  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001ae1a  mov     rcx, rdi; hLibModule
0x18001ae1d  call    cs:__imp_FreeLibrary
0x18001ae23  mov     eax, ebx
0x18001ae25  add     rsp, 48h
0x18001ae29  pop     rdi
0x18001ae2a  pop     rsi
0x18001ae2b  pop     rbp
0x18001ae2c  pop     rbx
0x18001ae2d  retn
```
