# UniDrvUI::PGetFileDirectory(ushort *)

- ea: `0x18010ae90`
- end: `0x18010b07c`
- name: `?PGetFileDirectory@UniDrvUI@@YAPEAGPEAG@Z`
- size: `492`
- prototype: `unsigned __int16 *__fastcall(LPWSTR pName, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18010a2fc`
- `0x18010b24c`

## callees

- `0x18000be0c`
- `0x180102674`
- `0x180106510`
- `0x18010ae90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18010af2d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18010af2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010af73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010afbb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010af73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010afbb`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18010af65`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18010af65`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010af81`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010af97`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010afdf`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010af81`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010af97`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18010afdf`
- `KERNEL32!GetLastError` at `0x18010aed0`
- `KERNEL32!GetLastError` at `0x18010b043`
- `KERNEL32!GetLastError` at `0x18010aed0`
- `KERNEL32!GetLastError` at `0x18010b043`
- `KERNEL32!LocalFree` at `0x18010b067`
- `KERNEL32!LocalFree` at `0x18010b067`
- `KERNEL32!LocalAlloc` at `0x18010aeec`
- `KERNEL32!LocalAlloc` at `0x18010aeec`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010aec2`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010af1c`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010aec2`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18010af1c`

## string_xrefs

- `0x18010b03a`: `Failed to copy Directory %ws\n`
- `0x18010afc1`: `Driver directory contains relative path %ws\n`
- `0x18010afcb`: `UniDrvUI::PGetFileDirectory`
- `0x18010b017`: `UniDrvUI::PGetFileDirectory`
- `0x18010b053`: `UniDrvUI::PGetFileDirectory`
- `0x18010b04c`: `GetPrinterDriverDirectory failed: %d\n`
- `0x18010b010`: `Driver directory is not fully-qualified: %ws\n`

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
  unsigned __int64 v15; // rdi
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
0x18010ae90  mov     rax, rsp
0x18010ae93  mov     [rax+8], rbx
0x18010ae97  push    rbp
0x18010ae98  push    rsi
0x18010ae99  push    rdi
0x18010ae9a  sub     rsp, 30h
0x18010ae9e  xor     ebp, ebp
0x18010aea0  xor     r9d, r9d; pDriverDirectory
0x18010aea3  mov     [rax+10h], ebp
0x18010aea6  xor     edx, edx; pEnvironment
0x18010aea8  mov     [rax+18h], rbp
0x18010aeac  lea     rax, [rax+10h]
0x18010aeb0  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18010aeb5  mov     rsi, rcx
0x18010aeb8  lea     r8d, [rbp+1]; Level
0x18010aebc  mov     [rsp+48h+cbBuf], ebp; cbBuf
0x18010aec0  mov     ebx, ebp
0x18010aec2  call    cs:__imp_GetPrinterDriverDirectoryW
0x18010aec8  test    eax, eax
0x18010aeca  jnz     loc_18010B043
0x18010aed0  call    cs:__imp_GetLastError
0x18010aed6  cmp     eax, 7Ah ; 'z'
0x18010aed9  jnz     loc_18010B043
0x18010aedf  mov     eax, [rsp+48h+arg_8]
0x18010aee3  xor     ecx, ecx; uFlags
0x18010aee5  add     eax, 14h
0x18010aee8  mov     edx, eax; uBytes
0x18010aeea  mov     edi, eax
0x18010aeec  call    cs:__imp_LocalAlloc
0x18010aef2  mov     rbx, rax
0x18010aef5  test    rax, rax
0x18010aef8  jz      loc_18010B043
0x18010aefe  mov     ecx, [rsp+48h+arg_8]
0x18010af02  lea     rax, [rsp+48h+arg_8]
0x18010af07  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x18010af0c  lea     r8d, [rbp+1]; Level
0x18010af10  mov     [rsp+48h+cbBuf], ecx; cbBuf
0x18010af14  mov     r9, rbx; pDriverDirectory
0x18010af17  mov     rcx, rsi; pName
0x18010af1a  xor     edx, edx; pEnvironment
0x18010af1c  call    cs:__imp_GetPrinterDriverDirectoryW
0x18010af22  test    eax, eax
0x18010af24  jz      loc_18010B043
0x18010af2a  mov     rcx, rbx
0x18010af2d  call    cs:__imp__o__wcsdup
0x18010af33  mov     rsi, rax
0x18010af36  test    rax, rax
0x18010af39  jz      loc_18010B03A
0x18010af3f  mov     rcx, rax
0x18010af42  jmp     short loc_18010AF59
0x18010af44  cmp     word ptr [rax], 2Eh ; '.'
0x18010af48  jnz     short loc_18010AF57
0x18010af4a  cmp     word ptr [rax+2], 2Eh ; '.'
0x18010af4f  jnz     short loc_18010AF57
0x18010af51  cmp     [rax+4], bp
0x18010af55  jz      short loc_18010AFB8
0x18010af57  xor     ecx, ecx; String
0x18010af59  lea     r8, [rsp+48h+Context]; Context
0x18010af5e  lea     rdx, Delimiter; "/\\"
0x18010af65  call    cs:__imp_wcstok_s
0x18010af6b  test    rax, rax
0x18010af6e  jnz     short loc_18010AF44
0x18010af70  mov     rcx, rsi; Block
0x18010af73  call    cs:__imp_free
0x18010af79  mov     edx, 5Ch ; '\'; Ch
0x18010af7e  mov     rcx, rbx; Str
0x18010af81  call    cs:__imp_wcsrchr
0x18010af87  mov     rsi, rax
0x18010af8a  mov     edx, 2Fh ; '/'; Ch
0x18010af8f  test    rax, rax
0x18010af92  jz      short loc_18010AFDC
0x18010af94  mov     rcx, rax; Str
0x18010af97  call    cs:__imp_wcsrchr
0x18010af9d  test    rax, rax
0x18010afa0  cmovnz  rsi, rax
0x18010afa4  shr     rdi, 1
0x18010afa7  mov     rax, rsi
0x18010afaa  mov     rcx, rsi
0x18010afad  sub     rax, rbx
0x18010afb0  sar     rax, 1
0x18010afb3  sub     rdi, rax
0x18010afb6  jmp     short loc_18010AFFC
0x18010afb8  mov     rcx, rsi; Block
0x18010afbb  call    cs:__imp_free
0x18010afc1  lea     rdx, aDriverDirector; "Driver directory contains relative path"...
0x18010afc8  mov     r8, rbx
0x18010afcb  lea     rcx, aUnidrvuiPgetfi; "UniDrvUI::PGetFileDirectory"
0x18010afd2  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010afd7  jmp     loc_18010B06D
0x18010afdc  mov     rcx, rbx; Str
0x18010afdf  call    cs:__imp_wcsrchr
0x18010afe5  shr     rdi, 1
0x18010afe8  test    rax, rax
0x18010afeb  jz      short loc_18010B00D
0x18010afed  mov     rcx, rax
0x18010aff0  sub     rcx, rbx
0x18010aff3  sar     rcx, 1
0x18010aff6  sub     rdi, rcx
0x18010aff9  mov     rcx, rax; pszDest
0x18010affc  mov     rdx, rdi; cchDest
0x18010afff  lea     r8, aUnifont_0; "\\unifont\\"
0x18010b006  call    StringCchCopyW
0x18010b00b  jmp     short loc_18010B035
0x18010b00d  mov     r8, rbx
0x18010b010  lea     rdx, aDriverDirector_0; "Driver directory is not fully-qualified"...
0x18010b017  lea     rcx, aUnidrvuiPgetfi; "UniDrvUI::PGetFileDirectory"
0x18010b01e  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010b023  lea     r8, aUnifont_0; "\\unifont\\"
0x18010b02a  mov     rdx, rdi; unsigned __int64
0x18010b02d  mov     rcx, rbx; unsigned __int16 *
0x18010b030  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18010b035  mov     rax, rbx
0x18010b038  jmp     short loc_18010B06F
0x18010b03a  lea     rdx, aFailedToCopyDi; "Failed to copy Directory %ws\n"
0x18010b041  jmp     short loc_18010AFC8
0x18010b043  call    cs:__imp_GetLastError
0x18010b049  mov     r8d, eax
0x18010b04c  lea     rdx, aGetprinterdriv_1; "GetPrinterDriverDirectory failed: %d\n"
0x18010b053  lea     rcx, aUnidrvuiPgetfi; "UniDrvUI::PGetFileDirectory"
0x18010b05a  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18010b05f  test    rbx, rbx
0x18010b062  jz      short loc_18010B06D
0x18010b064  mov     rcx, rbx; hMem
0x18010b067  call    cs:__imp_LocalFree
0x18010b06d  xor     eax, eax
0x18010b06f  mov     rbx, [rsp+48h+arg_0]
0x18010b074  add     rsp, 30h
0x18010b078  pop     rdi
0x18010b079  pop     rsi
0x18010b07a  pop     rbp
0x18010b07b  retn
```
