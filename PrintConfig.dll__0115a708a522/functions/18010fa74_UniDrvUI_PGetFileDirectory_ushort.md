# UniDrvUI::PGetFileDirectory(ushort *)

- ea: `0x18010fa74`
- end: `0x18010fcb2`
- name: `?PGetFileDirectory@UniDrvUI@@YAPEAGPEAG@Z`
- size: `574`
- prototype: `unsigned __int16 *__fastcall(LPWSTR pName, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18010f0b4`
- `0x18010fed0`

## callees

- `0x18000be68`
- `0x180107214`
- `0x18010b1e4`
- `0x18010fa74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18010fb29`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18010fb29`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010fb7b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010fbd5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010fb7b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010fbd5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18010fb67`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18010fb67`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010fb8f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010fbab`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010fbff`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010fb8f`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010fbab`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010fbff`
- `KERNEL32!GetLastError` at `0x18010faba`
- `KERNEL32!GetLastError` at `0x18010fc6c`
- `KERNEL32!GetLastError` at `0x18010faba`
- `KERNEL32!GetLastError` at `0x18010fc6c`
- `KERNEL32!LocalFree` at `0x18010fc96`
- `KERNEL32!LocalFree` at `0x18010fc96`
- `KERNEL32!LocalAlloc` at `0x18010fadc`
- `KERNEL32!LocalAlloc` at `0x18010fadc`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010faa6`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010fb12`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010faa6`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010fb12`

## string_xrefs

- `0x18010fbeb`: `UniDrvUI::PGetFileDirectory`
- `0x18010fc3d`: `UniDrvUI::PGetFileDirectory`
- `0x18010fc82`: `UniDrvUI::PGetFileDirectory`
- `0x18010fbe1`: `Driver directory contains relative path %ws\n`
- `0x18010fc7b`: `GetPrinterDriverDirectory failed: %d\n`
- `0x18010fc36`: `Driver directory is not fully-qualified: %ws\n`
- `0x18010fc60`: `Failed to copy Directory %ws\n`

## pseudocode

```c
unsigned __int16 *__fastcall UniDrvUI::PGetFileDirectory(LPWSTR pName, unsigned __int16 *a2)
{
  wchar_t *v3; // rbx
  SIZE_T v4; // rdi
  __int64 v5; // rax
  void *v6; // rsi
  wchar_t *i; // rcx
  wchar_t *v8; // rax
  wchar_t *v9; // rax
  wchar_t *v10; // rsi
  wchar_t *v11; // rax
  wchar_t *v12; // rcx
  size_t v13; // rdi
  wchar_t *v14; // rax
  __int64 v15; // rdi
  DWORD LastError; // eax
  DWORD pcbNeeded; // [rsp+58h] [rbp+10h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp+18h] BYREF

  pcbNeeded = 0;
  Context = 0;
  v3 = 0;
  if ( !GetPrinterDriverDirectoryW(pName, 0, 1u, 0, 0, &pcbNeeded)
    && GetLastError() == 122
    && (v4 = pcbNeeded + 20, (v3 = (wchar_t *)LocalAlloc(0, v4)) != 0)
    && GetPrinterDriverDirectoryW(pName, 0, 1u, (LPBYTE)v3, pcbNeeded, &pcbNeeded) )
  {
    v5 = _o__wcsdup(v3);
    v6 = (void *)v5;
    if ( v5 )
    {
      for ( i = (wchar_t *)v5; ; i = 0 )
      {
        v8 = wcstok_s(i, L"/\\", &Context);
        if ( !v8 )
          break;
        if ( *v8 == 46 && v8[1] == 46 && !v8[2] )
        {
          free(v6);
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::PGetFileDirectory",
            L"Driver directory contains relative path %ws\n",
            v3);
          return 0;
        }
      }
      free(v6);
      v9 = wcsrchr(v3, 0x5Cu);
      v10 = v9;
      if ( v9 )
      {
        v11 = wcsrchr(v9, 0x2Fu);
        if ( v11 )
          v10 = v11;
        v12 = v10;
        v13 = (v4 >> 1) - (v10 - v3);
      }
      else
      {
        v14 = wcsrchr(v3, 0x2Fu);
        v15 = v4 >> 1;
        if ( !v14 )
        {
          DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
            "UniDrvUI::PGetFileDirectory",
            L"Driver directory is not fully-qualified: %ws\n",
            v3);
          StringCchCatW(v3, v15, L"\\unifont\\");
          return v3;
        }
        v13 = v15 - (v14 - v3);
        v12 = v14;
      }
      StringCchCopyW(v12, v13, L"\\unifont\\");
      return v3;
    }
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PGetFileDirectory",
      L"Failed to copy Directory %ws\n",
      v3);
  }
  else
  {
    LastError = GetLastError();
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
      "UniDrvUI::PGetFileDirectory",
      L"GetPrinterDriverDirectory failed: %d\n",
      LastError);
    if ( v3 )
      LocalFree(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18010fa74  mov     rax, rsp
0x18010fa77  mov     [rax+8], rbx
0x18010fa7b  push    rbp
0x18010fa7c  push    rsi
0x18010fa7d  push    rdi
0x18010fa7e  sub     rsp, 30h
0x18010fa82  xor     ebp, ebp
0x18010fa84  xor     r9d, r9d; pDriverDirectory
0x18010fa87  mov     [rax+10h], ebp
0x18010fa8a  xor     edx, edx; pEnvironment
0x18010fa8c  mov     [rax+18h], rbp
0x18010fa90  lea     rax, [rax+10h]
0x18010fa94  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18010fa99  mov     rsi, rcx
0x18010fa9c  lea     r8d, [rbp+1]; Level
0x18010faa0  mov     [rsp+48h+cbBuf], ebp; cbBuf
0x18010faa4  mov     ebx, ebp
0x18010faa6  call    cs:__imp_GetPrinterDriverDirectoryW
0x18010faad  nop     dword ptr [rax+rax+00h]
0x18010fab2  test    eax, eax
0x18010fab4  jnz     loc_18010FC6C
0x18010faba  call    cs:__imp_GetLastError
0x18010fac1  nop     dword ptr [rax+rax+00h]
0x18010fac6  cmp     eax, 7Ah ; 'z'
0x18010fac9  jnz     loc_18010FC6C
0x18010facf  mov     eax, [rsp+48h+arg_8]
0x18010fad3  xor     ecx, ecx; uFlags
0x18010fad5  add     eax, 14h
0x18010fad8  mov     edx, eax; uBytes
0x18010fada  mov     edi, eax
0x18010fadc  call    cs:__imp_LocalAlloc
0x18010fae3  nop     dword ptr [rax+rax+00h]
0x18010fae8  mov     rbx, rax
0x18010faeb  test    rax, rax
0x18010faee  jz      loc_18010FC6C
0x18010faf4  mov     ecx, [rsp+48h+arg_8]
0x18010faf8  lea     rax, [rsp+48h+arg_8]
0x18010fafd  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18010fb02  lea     r8d, [rbp+1]; Level
0x18010fb06  mov     [rsp+48h+cbBuf], ecx; cbBuf
0x18010fb0a  mov     r9, rbx; pDriverDirectory
0x18010fb0d  mov     rcx, rsi; pName
0x18010fb10  xor     edx, edx; pEnvironment
0x18010fb12  call    cs:__imp_GetPrinterDriverDirectoryW
0x18010fb19  nop     dword ptr [rax+rax+00h]
0x18010fb1e  test    eax, eax
0x18010fb20  jz      loc_18010FC6C
0x18010fb26  mov     rcx, rbx
0x18010fb29  call    cs:__imp__o__wcsdup
0x18010fb30  nop     dword ptr [rax+rax+00h]
0x18010fb35  mov     rsi, rax
0x18010fb38  test    rax, rax
0x18010fb3b  jz      loc_18010FC60
0x18010fb41  mov     rcx, rax
0x18010fb44  jmp     short loc_18010FB5B
0x18010fb46  cmp     word ptr [rax], 2Eh ; '.'
0x18010fb4a  jnz     short loc_18010FB59
0x18010fb4c  cmp     word ptr [rax+2], 2Eh ; '.'
0x18010fb51  jnz     short loc_18010FB59
0x18010fb53  cmp     [rax+4], bp
0x18010fb57  jz      short loc_18010FBD2
0x18010fb59  xor     ecx, ecx; String
0x18010fb5b  lea     r8, [rsp+48h+Context]; Context
0x18010fb60  lea     rdx, Delimiter; "/\\"
0x18010fb67  call    cs:__imp_wcstok_s
0x18010fb6e  nop     dword ptr [rax+rax+00h]
0x18010fb73  test    rax, rax
0x18010fb76  jnz     short loc_18010FB46
0x18010fb78  mov     rcx, rsi; Block
0x18010fb7b  call    cs:__imp_free
0x18010fb82  nop     dword ptr [rax+rax+00h]
0x18010fb87  mov     edx, 5Ch ; '\'; Ch
0x18010fb8c  mov     rcx, rbx; Str
0x18010fb8f  call    cs:__imp_wcsrchr
0x18010fb96  nop     dword ptr [rax+rax+00h]
0x18010fb9b  mov     rsi, rax
0x18010fb9e  mov     edx, 2Fh ; '/'; Ch
0x18010fba3  test    rax, rax
0x18010fba6  jz      short loc_18010FBFC
0x18010fba8  mov     rcx, rax; Str
0x18010fbab  call    cs:__imp_wcsrchr
0x18010fbb2  nop     dword ptr [rax+rax+00h]
0x18010fbb7  test    rax, rax
0x18010fbba  cmovnz  rsi, rax
0x18010fbbe  shr     rdi, 1
0x18010fbc1  mov     rax, rsi
0x18010fbc4  mov     rcx, rsi
0x18010fbc7  sub     rax, rbx
0x18010fbca  sar     rax, 1
0x18010fbcd  sub     rdi, rax
0x18010fbd0  jmp     short loc_18010FC22
0x18010fbd2  mov     rcx, rsi; Block
0x18010fbd5  call    cs:__imp_free
0x18010fbdc  nop     dword ptr [rax+rax+00h]
0x18010fbe1  lea     rdx, aDriverDirector; "Driver directory contains relative path"...
0x18010fbe8  mov     r8, rbx
0x18010fbeb  lea     rcx, aUnidrvuiPgetfi; "UniDrvUI::PGetFileDirectory"
0x18010fbf2  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010fbf7  jmp     loc_18010FCA2
0x18010fbfc  mov     rcx, rbx; Str
0x18010fbff  call    cs:__imp_wcsrchr
0x18010fc06  nop     dword ptr [rax+rax+00h]
0x18010fc0b  shr     rdi, 1
0x18010fc0e  test    rax, rax
0x18010fc11  jz      short loc_18010FC33
0x18010fc13  mov     rcx, rax
0x18010fc16  sub     rcx, rbx
0x18010fc19  sar     rcx, 1
0x18010fc1c  sub     rdi, rcx
0x18010fc1f  mov     rcx, rax; pszDest
0x18010fc22  mov     rdx, rdi; cchDest
0x18010fc25  lea     r8, aUnifont_0; "\\unifont\\"
0x18010fc2c  call    StringCchCopyW
0x18010fc31  jmp     short loc_18010FC5B
0x18010fc33  mov     r8, rbx
0x18010fc36  lea     rdx, aDriverDirector_0; "Driver directory is not fully-qualified"...
0x18010fc3d  lea     rcx, aUnidrvuiPgetfi; "UniDrvUI::PGetFileDirectory"
0x18010fc44  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010fc49  lea     r8, aUnifont_0; "\\unifont\\"
0x18010fc50  mov     rdx, rdi; unsigned __int64
0x18010fc53  mov     rcx, rbx; unsigned __int16 *
0x18010fc56  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18010fc5b  mov     rax, rbx
0x18010fc5e  jmp     short loc_18010FCA4
0x18010fc60  lea     rdx, aFailedToCopyDi; "Failed to copy Directory %ws\n"
0x18010fc67  jmp     loc_18010FBE8
0x18010fc6c  call    cs:__imp_GetLastError
0x18010fc73  nop     dword ptr [rax+rax+00h]
0x18010fc78  mov     r8d, eax
0x18010fc7b  lea     rdx, aGetprinterdriv_1; "GetPrinterDriverDirectory failed: %d\n"
0x18010fc82  lea     rcx, aUnidrvuiPgetfi; "UniDrvUI::PGetFileDirectory"
0x18010fc89  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010fc8e  test    rbx, rbx
0x18010fc91  jz      short loc_18010FCA2
0x18010fc93  mov     rcx, rbx; hMem
0x18010fc96  call    cs:__imp_LocalFree
0x18010fc9d  nop     dword ptr [rax+rax+00h]
0x18010fca2  xor     eax, eax
0x18010fca4  mov     rbx, [rsp+48h+arg_0]
0x18010fca9  add     rsp, 30h
0x18010fcad  pop     rdi
0x18010fcae  pop     rsi
0x18010fcaf  pop     rbp
0x18010fcb0  retn
```
