# PrintConfigDataContext::PopulatePrintConfigDataContext(void *,PrintConfigDataContext &)

- ea: `0x180036118`
- end: `0x180036294`
- name: `?PopulatePrintConfigDataContext@PrintConfigDataContext@@SAJPEAXAEAV1@@Z`
- size: `380`
- prototype: `__int64 __fastcall(HANDLE hPrinter, struct _DRIVER_INFO_3W **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18003431c`

## callees

- `0x180002498`
- `0x18000298c`
- `0x180034afc`
- `0x18003563c`
- `0x180036118`
- `0x18003629c`
- `0x180036388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003623c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003623c`
- `WINSPOOL!GetPrinterDriverW` at `0x180036155`
- `WINSPOOL!GetPrinterDriverW` at `0x1800361ca`
- `WINSPOOL!GetPrinterDriverW` at `0x180036155`
- `WINSPOOL!GetPrinterDriverW` at `0x1800361ca`
- `KERNEL32!GetLastError` at `0x180036169`
- `KERNEL32!GetLastError` at `0x1800361e1`
- `KERNEL32!GetLastError` at `0x180036169`
- `KERNEL32!GetLastError` at `0x1800361e1`

## string_xrefs

- `0x180036257`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall PrintConfigDataContext::PopulatePrintConfigDataContext(HANDLE hPrinter, struct _DRIVER_INFO_3W **a2)
{
  signed int PrinterInfo4; // ebx
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
    v5 = (struct _DRIVER_INFO_3W *)operator new(pcbNeeded, (const struct std::nothrow_t *)byte_18006C430);
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
0x180036118  push    rbx
0x18003611a  push    rbp
0x18003611b  push    rsi
0x18003611c  push    rdi
0x18003611d  sub     rsp, 38h
0x180036121  xor     r9d, r9d; pDriverInfo
0x180036124  mov     qword ptr [rdx+8], 0
0x18003612c  lea     rax, [rsp+58h+arg_8]
0x180036131  mov     [rsp+58h+arg_8], 0
0x180036139  mov     rdi, rdx
0x18003613c  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x180036141  xor     edx, edx; pEnvironment
0x180036143  mov     [rsp+58h+cbBuf], 0; cbBuf
0x18003614b  lea     esi, [r9+8]
0x18003614f  mov     rbp, rcx
0x180036152  mov     r8d, esi; Level
0x180036155  call    cs:__imp_GetPrinterDriverW
0x18003615b  test    eax, eax
0x18003615d  jz      short loc_180036169
0x18003615f  mov     ebx, 80004005h
0x180036164  jmp     loc_180036289
0x180036169  call    cs:__imp_GetLastError
0x18003616f  cmp     eax, 7Ah ; 'z'
0x180036172  jnz     short loc_1800361E1
0x180036174  cmp     [rsp+58h+arg_8], 0C8h
0x18003617c  jnb     short loc_180036188
0x18003617e  mov     ebx, 8000FFFFh
0x180036183  jmp     loc_180036289
0x180036188  mov     ecx, [rsp+58h+arg_8]; unsigned __int64
0x18003618c  lea     rdx, byte_18006C430; struct std::nothrow_t *
0x180036193  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036198  mov     [rdi+8], rax
0x18003619c  mov     r9, rax; pDriverInfo
0x18003619f  test    rax, rax
0x1800361a2  jnz     short loc_1800361AE
0x1800361a4  mov     ebx, 8007000Eh
0x1800361a9  jmp     loc_180036289
0x1800361ae  lea     rax, [rsp+58h+arg_8]
0x1800361b3  mov     r8d, esi; Level
0x1800361b6  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x1800361bb  xor     edx, edx; pEnvironment
0x1800361bd  mov     eax, [rsp+58h+arg_8]
0x1800361c1  mov     rcx, rbp; hPrinter
0x1800361c4  mov     [rsp+58h+cbBuf], eax; cbBuf
0x1800361c8  xor     ebx, ebx
0x1800361ca  call    cs:__imp_GetPrinterDriverW
0x1800361d0  test    eax, eax
0x1800361d2  jnz     short loc_1800361F6
0x1800361d4  mov     rcx, [rdi+8]; Block
0x1800361d8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800361dd  mov     [rdi+8], rbx
0x1800361e1  call    cs:__imp_GetLastError
0x1800361e7  mov     ebx, eax
0x1800361e9  test    eax, eax
0x1800361eb  jle     short loc_1800361F6
0x1800361ed  movzx   ebx, ax
0x1800361f0  or      ebx, 80070000h
0x1800361f6  test    ebx, ebx
0x1800361f8  jns     short loc_180036217
0x1800361fa  cmp     ebx, 8007007Ch
0x180036200  jnz     loc_180036289
0x180036206  mov     rdx, rdi; struct _DRIVER_INFO_3W **
0x180036209  mov     rcx, rbp; hPrinter
0x18003620c  call    ?PrivateGetPrinterDriver3@@YAJPEAXPEAPEAU_DRIVER_INFO_3W@@@Z; PrivateGetPrinterDriver3(void *,_DRIVER_INFO_3W * *)
0x180036211  mov     ebx, eax
0x180036213  test    eax, eax
0x180036215  js      short loc_180036289
0x180036217  lea     rdx, [rdi+10h]; struct _PRINTER_INFO_4W **
0x18003621b  mov     rcx, rbp; hPrinter
0x18003621e  call    ?PrivateGetPrinterInfo4@@YAJPEAXPEAPEAU_PRINTER_INFO_4W@@@Z; PrivateGetPrinterInfo4(void *,_PRINTER_INFO_4W * *)
0x180036223  mov     ebx, eax
0x180036225  test    eax, eax
0x180036227  js      short loc_180036289
0x180036229  mov     rcx, [rdi+10h]
0x18003622d  mov     rcx, [rcx]; Str
0x180036230  test    rcx, rcx
0x180036233  jz      short loc_18003626B
0x180036235  lea     rdx, aCsr; "\\\\CSR|"
0x18003623c  call    cs:__imp_wcsstr
0x180036242  test    rax, rax
0x180036245  jz      short loc_18003626B
0x180036247  mov     rcx, [rdi+8]
0x18003624b  test    rcx, rcx
0x18003624e  jnz     short loc_180036253
0x180036250  mov     rcx, [rdi]
0x180036253  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180036257  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x18003625e  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180036263  test    al, al
0x180036265  jz      short loc_18003626B
0x180036267  mov     al, 1
0x180036269  jmp     short loc_18003626D
0x18003626b  xor     al, al
0x18003626d  mov     [rdi+20h], al
0x180036270  test    al, al
0x180036272  jz      short loc_180036289
0x180036274  lea     r8, [rdi+18h]; unsigned __int16 **
0x180036278  mov     rcx, rbp; hPrinter
0x18003627b  mov     qword ptr [r8], 0
0x180036282  call    ?GetPrinterDataString@@YAJPEAXPEBGPEAPEAG@Z; GetPrinterDataString(void *,ushort const *,ushort * *)
0x180036287  mov     ebx, eax
0x180036289  mov     eax, ebx
0x18003628b  add     rsp, 38h
0x18003628f  pop     rdi
0x180036290  pop     rsi
0x180036291  pop     rbp
0x180036292  pop     rbx
0x180036293  retn
```
