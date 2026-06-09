# PrintConfigDataContext::PopulatePrintConfigDataContext(void *,PrintConfigDataContext &)

- ea: `0x18003791c`
- end: `0x180037ab7`
- name: `?PopulatePrintConfigDataContext@PrintConfigDataContext@@SAJPEAXAEAV1@@Z`
- size: `411`
- prototype: `__int64 __fastcall(HANDLE hPrinter, struct _DRIVER_INFO_3W **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180035a2c`

## callees

- `0x1800024d8`
- `0x1800029ec`
- `0x180036224`
- `0x180036dac`
- `0x18003791c`
- `0x180037ac0`
- `0x180037bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180037a58`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180037a58`
- `WINSPOOL!GetPrinterDriverW` at `0x180037959`
- `WINSPOOL!GetPrinterDriverW` at `0x1800379da`
- `WINSPOOL!GetPrinterDriverW` at `0x180037959`
- `WINSPOOL!GetPrinterDriverW` at `0x1800379da`
- `KERNEL32!GetLastError` at `0x180037973`
- `KERNEL32!GetLastError` at `0x1800379f7`
- `KERNEL32!GetLastError` at `0x180037973`
- `KERNEL32!GetLastError` at `0x1800379f7`

## string_xrefs

- `0x180037a79`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall PrintConfigDataContext::PopulatePrintConfigDataContext(HANDLE hPrinter, struct _DRIVER_INFO_3W **a2)
{
  int PrinterInfo4; // ebx
  struct _DRIVER_INFO_3W *v5; // rax
  signed int LastError; // eax
  const unsigned __int16 *v7; // rdx
  const wchar_t *v8; // rcx
  struct _PRINTER_INFO_4W *v9; // rcx
  char v10; // al
  DWORD pcbNeeded; // [rsp+68h] [rbp+10h] BYREF

  a2[1] = 0;
  pcbNeeded = 0;
  if ( GetPrinterDriverW(hPrinter, 0, 8u, 0, 0, &pcbNeeded) )
    return (unsigned int)-2147467259;
  if ( GetLastError() == 122 )
  {
    if ( pcbNeeded < 0xC8 )
      return (unsigned int)-2147418113;
    v5 = (struct _DRIVER_INFO_3W *)operator new(pcbNeeded, (const struct std::nothrow_t *)byte_18006E400);
    a2[1] = v5;
    if ( !v5 )
      return (unsigned int)-2147024882;
    PrinterInfo4 = 0;
    if ( GetPrinterDriverW(hPrinter, 0, 8u, (LPBYTE)v5, pcbNeeded, &pcbNeeded) )
      goto LABEL_12;
    operator delete(a2[1]);
    a2[1] = 0;
  }
  LastError = GetLastError();
  PrinterInfo4 = LastError;
  if ( LastError > 0 )
    PrinterInfo4 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( PrinterInfo4 >= 0
    || PrinterInfo4 == -2147024772 && (PrinterInfo4 = PrivateGetPrinterDriver3(hPrinter, a2), PrinterInfo4 >= 0) )
  {
    PrinterInfo4 = PrivateGetPrinterInfo4(hPrinter, (struct _PRINTER_INFO_4W **)a2 + 2);
    if ( PrinterInfo4 >= 0 )
    {
      v8 = *(const wchar_t **)&a2[2]->cVersion;
      if ( !v8 || !wcsstr(v8, L"\\\\CSR|") )
        goto LABEL_22;
      v9 = (struct _PRINTER_INFO_4W *)a2[1];
      if ( !v9 )
        v9 = (struct _PRINTER_INFO_4W *)*a2;
      if ( DoesFullPathMatchFile(*(const unsigned __int16 **)&v9[1].Attributes, L"PrintConfig.dll") )
        v10 = 1;
      else
LABEL_22:
        v10 = 0;
      *((_BYTE *)a2 + 32) = v10;
      if ( v10 )
      {
        a2[3] = 0;
        return (unsigned int)GetPrinterDataString(hPrinter, v7, (unsigned __int16 **)a2 + 3);
      }
    }
  }
  return (unsigned int)PrinterInfo4;
}

```

## disassembly

```asm
0x18003791c  push    rbx
0x18003791e  push    rbp
0x18003791f  push    rsi
0x180037920  push    rdi
0x180037921  sub     rsp, 38h
0x180037925  xor     r9d, r9d; pDriverInfo
0x180037928  mov     qword ptr [rdx+8], 0
0x180037930  lea     rax, [rsp+58h+arg_8]
0x180037935  mov     [rsp+58h+arg_8], 0
0x18003793d  mov     rdi, rdx
0x180037940  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x180037945  xor     edx, edx; pEnvironment
0x180037947  mov     [rsp+58h+cbBuf], 0; cbBuf
0x18003794f  lea     esi, [r9+8]
0x180037953  mov     rbp, rcx
0x180037956  mov     r8d, esi; Level
0x180037959  call    cs:__imp_GetPrinterDriverW
0x180037960  nop     dword ptr [rax+rax+00h]
0x180037965  test    eax, eax
0x180037967  jz      short loc_180037973
0x180037969  mov     ebx, 80004005h
0x18003796e  jmp     loc_180037AAB
0x180037973  call    cs:__imp_GetLastError
0x18003797a  nop     dword ptr [rax+rax+00h]
0x18003797f  cmp     eax, 7Ah ; 'z'
0x180037982  jnz     short loc_1800379F7
0x180037984  cmp     [rsp+58h+arg_8], 0C8h
0x18003798c  jnb     short loc_180037998
0x18003798e  mov     ebx, 8000FFFFh
0x180037993  jmp     loc_180037AAB
0x180037998  mov     ecx, [rsp+58h+arg_8]; unsigned __int64
0x18003799c  lea     rdx, byte_18006E400; struct std::nothrow_t *
0x1800379a3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800379a8  mov     [rdi+8], rax
0x1800379ac  mov     r9, rax; pDriverInfo
0x1800379af  test    rax, rax
0x1800379b2  jnz     short loc_1800379BE
0x1800379b4  mov     ebx, 8007000Eh
0x1800379b9  jmp     loc_180037AAB
0x1800379be  lea     rax, [rsp+58h+arg_8]
0x1800379c3  mov     r8d, esi; Level
0x1800379c6  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x1800379cb  xor     edx, edx; pEnvironment
0x1800379cd  mov     eax, [rsp+58h+arg_8]
0x1800379d1  mov     rcx, rbp; hPrinter
0x1800379d4  mov     [rsp+58h+cbBuf], eax; cbBuf
0x1800379d8  xor     ebx, ebx
0x1800379da  call    cs:__imp_GetPrinterDriverW
0x1800379e1  nop     dword ptr [rax+rax+00h]
0x1800379e6  test    eax, eax
0x1800379e8  jnz     short loc_180037A12
0x1800379ea  mov     rcx, [rdi+8]; Block
0x1800379ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800379f3  mov     [rdi+8], rbx
0x1800379f7  call    cs:__imp_GetLastError
0x1800379fe  nop     dword ptr [rax+rax+00h]
0x180037a03  mov     ebx, eax
0x180037a05  test    eax, eax
0x180037a07  jle     short loc_180037A12
0x180037a09  movzx   ebx, ax
0x180037a0c  or      ebx, 80070000h
0x180037a12  test    ebx, ebx
0x180037a14  jns     short loc_180037A33
0x180037a16  cmp     ebx, 8007007Ch
0x180037a1c  jnz     loc_180037AAB
0x180037a22  mov     rdx, rdi; struct _DRIVER_INFO_3W **
0x180037a25  mov     rcx, rbp; hPrinter
0x180037a28  call    ?PrivateGetPrinterDriver3@@YAJPEAXPEAPEAU_DRIVER_INFO_3W@@@Z; PrivateGetPrinterDriver3(void *,_DRIVER_INFO_3W * *)
0x180037a2d  mov     ebx, eax
0x180037a2f  test    eax, eax
0x180037a31  js      short loc_180037AAB
0x180037a33  lea     rdx, [rdi+10h]; struct _PRINTER_INFO_4W **
0x180037a37  mov     rcx, rbp; hPrinter
0x180037a3a  call    ?PrivateGetPrinterInfo4@@YAJPEAXPEAPEAU_PRINTER_INFO_4W@@@Z; PrivateGetPrinterInfo4(void *,_PRINTER_INFO_4W * *)
0x180037a3f  mov     ebx, eax
0x180037a41  test    eax, eax
0x180037a43  js      short loc_180037AAB
0x180037a45  mov     rcx, [rdi+10h]
0x180037a49  mov     rcx, [rcx]; Str
0x180037a4c  test    rcx, rcx
0x180037a4f  jz      short loc_180037A8D
0x180037a51  lea     rdx, aCsr; "\\\\CSR|"
0x180037a58  call    cs:__imp_wcsstr
0x180037a5f  nop     dword ptr [rax+rax+00h]
0x180037a64  test    rax, rax
0x180037a67  jz      short loc_180037A8D
0x180037a69  mov     rcx, [rdi+8]
0x180037a6d  test    rcx, rcx
0x180037a70  jnz     short loc_180037A75
0x180037a72  mov     rcx, [rdi]
0x180037a75  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180037a79  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180037a80  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180037a85  test    al, al
0x180037a87  jz      short loc_180037A8D
0x180037a89  mov     al, 1
0x180037a8b  jmp     short loc_180037A8F
0x180037a8d  xor     al, al
0x180037a8f  mov     [rdi+20h], al
0x180037a92  test    al, al
0x180037a94  jz      short loc_180037AAB
0x180037a96  lea     r8, [rdi+18h]; unsigned __int16 **
0x180037a9a  mov     rcx, rbp; hPrinter
0x180037a9d  mov     qword ptr [r8], 0
0x180037aa4  call    ?GetPrinterDataString@@YAJPEAXPEBGPEAPEAG@Z; GetPrinterDataString(void *,ushort const *,ushort * *)
0x180037aa9  mov     ebx, eax
0x180037aab  mov     eax, ebx
0x180037aad  add     rsp, 38h
0x180037ab1  pop     rdi
0x180037ab2  pop     rsi
0x180037ab3  pop     rbp
0x180037ab4  pop     rbx
0x180037ab5  retn
```
