# GetFallbackServicingStackDirectory

- ea: `0x14000c6e4`
- end: `0x14000c827`
- name: `GetFallbackServicingStackDirectory`
- size: `323`
- prototype: `__int64 __fastcall(const wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000c3e0`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x14000c6e4`
- `0x140017658`
- `0x14001d404`
- `0x14001f664`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x14000c75a`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x14000c75a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c7cc`

## string_xrefs

- `0x14000c727`: `No servicing stack directory result specified`
- `0x14000c733`: `Fallback servicing stack directory path being retrieved...`
- `0x14000c7e3`: `Failed to get servicing path.`
- `0x14000c77f`: `No valid servicing stack file path found`
- `0x14000c7a6`: `Failed to allocate string for hardcoded servicing stack directory.`
- `0x14000c7b4`: `Fallback servicing stack directory path: %S`

## pseudocode

```c
__int64 __fastcall GetFallbackServicingStackDirectory(const wchar_t **a1)
{
  unsigned int v2; // ebx
  DWORD ModuleFileNameW; // eax
  _WORD *v4; // r9
  int v5; // eax
  signed int LastError; // eax
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Filename, 0, 0x208u);
  if ( a1 )
  {
    *a1 = 0;
    CBSWdsLogLight(0x4000000, 0, 0, "Fallback servicing stack directory path being retrieved...");
    ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
    if ( !ModuleFileNameW || ModuleFileNameW == 260 )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) == 0 )
        v2 = -2147467259;
      CBSWdsLogLight(0x4000000, v2, 1, "Failed to get servicing path.");
    }
    else
    {
      v4 = (_WORD *)FileFromPath(Filename);
      if ( v4 )
      {
        *v4 = 0;
        v5 = SczAllocFromSz(a1, Filename);
        v2 = v5;
        if ( v5 >= 0 )
          CBSWdsLogLight(0x4000000, 0, 0, "Fallback servicing stack directory path: %S", *a1);
        else
          CBSWdsLogLight(
            0x4000000,
            (unsigned int)v5,
            1,
            "Failed to allocate string for hardcoded servicing stack directory.");
      }
      else
      {
        v2 = -2146498560;
        CBSWdsLogLight(0x4000000, 2148468736LL, 1, "No valid servicing stack file path found");
      }
    }
  }
  else
  {
    v2 = -2147467261;
    CBSWdsLogLight(0x4000000, 2147500035LL, 1, "No servicing stack directory result specified");
  }
  return v2;
}

```

## disassembly

```asm
0x14000c6e4  mov     [rsp+arg_8], rbx
0x14000c6e9  push    rsi
0x14000c6ea  sub     rsp, 250h
0x14000c6f1  mov     rax, cs:__security_cookie
0x14000c6f8  xor     rax, rsp
0x14000c6fb  mov     [rsp+258h+var_18], rax
0x14000c703  mov     rsi, rcx
0x14000c706  xor     edx, edx; Val
0x14000c708  lea     rcx, [rsp+258h+Filename]; void *
0x14000c70d  mov     r8d, 208h; Size
0x14000c713  call    memset_0
0x14000c718  mov     ecx, 4000000h
0x14000c71d  test    rsi, rsi
0x14000c720  jnz     short loc_14000C733
0x14000c722  mov     ebx, 80004003h
0x14000c727  lea     r9, aNoServicingSta; "No servicing stack directory result spe"...
0x14000c72e  jmp     loc_14000C7F7
0x14000c733  lea     r9, aFallbackServic_0; "Fallback servicing stack directory path"...
0x14000c73a  mov     qword ptr [rsi], 0
0x14000c741  xor     r8d, r8d
0x14000c744  xor     edx, edx
0x14000c746  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c74b  mov     ebx, 104h
0x14000c750  lea     rdx, [rsp+258h+Filename]; lpFilename
0x14000c755  mov     r8d, ebx; nSize
0x14000c758  xor     ecx, ecx; hModule
0x14000c75a  call    cs:__imp_GetModuleFileNameW
0x14000c760  test    eax, eax
0x14000c762  jz      short loc_14000C7CC
0x14000c764  cmp     eax, ebx
0x14000c766  jz      short loc_14000C7CC
0x14000c768  lea     rcx, [rsp+258h+Filename]
0x14000c76d  call    FileFromPath
0x14000c772  mov     r9, rax
0x14000c775  test    rax, rax
0x14000c778  jnz     short loc_14000C788
0x14000c77a  mov     ebx, 800F0800h
0x14000c77f  lea     r9, aNoValidServici; "No valid servicing stack file path foun"...
0x14000c786  jmp     short loc_14000C7F2
0x14000c788  xor     eax, eax
0x14000c78a  lea     rdx, [rsp+258h+Filename]
0x14000c78f  mov     rcx, rsi
0x14000c792  mov     [r9], ax
0x14000c796  call    SczAllocFromSz
0x14000c79b  mov     ebx, eax
0x14000c79d  mov     ecx, 4000000h
0x14000c7a2  test    eax, eax
0x14000c7a4  jns     short loc_14000C7B1
0x14000c7a6  lea     r9, aFailedToAlloca_11; "Failed to allocate string for hardcoded"...
0x14000c7ad  mov     edx, eax
0x14000c7af  jmp     short loc_14000C7F9
0x14000c7b1  mov     rax, [rsi]
0x14000c7b4  lea     r9, aFallbackServic; "Fallback servicing stack directory path"...
0x14000c7bb  xor     r8d, r8d
0x14000c7be  mov     [rsp+258h+var_238], rax
0x14000c7c3  xor     edx, edx
0x14000c7c5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c7ca  jmp     short loc_14000C804
0x14000c7cc  call    cs:__imp_GetLastError
0x14000c7d2  mov     ebx, eax
0x14000c7d4  test    eax, eax
0x14000c7d6  jle     short loc_14000C7E1
0x14000c7d8  movzx   ebx, ax
0x14000c7db  or      ebx, 80070000h
0x14000c7e1  test    ebx, ebx
0x14000c7e3  lea     r9, aFailedToGetSer; "Failed to get servicing path."
0x14000c7ea  mov     eax, 80004005h
0x14000c7ef  cmovns  ebx, eax
0x14000c7f2  mov     ecx, 4000000h
0x14000c7f7  mov     edx, ebx
0x14000c7f9  mov     r8d, 1
0x14000c7ff  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000c804  mov     eax, ebx
0x14000c806  mov     rcx, [rsp+258h+var_18]
0x14000c80e  xor     rcx, rsp; StackCookie
0x14000c811  call    __security_check_cookie
0x14000c816  mov     rbx, [rsp+258h+arg_8]
0x14000c81e  add     rsp, 250h
0x14000c825  pop     rsi
0x14000c826  retn
```
