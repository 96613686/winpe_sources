# CreatePrintConfigData(void *,PrintConfigData * *)

- ea: `0x1800246f0`
- end: `0x1800248b0`
- name: `?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(void *, struct PrintConfigData **)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18002431c`
- `0x180024ad4`
- `0x180025dc0`
- `0x18003f860`

## callees

- `0x1800246f0`
- `0x1800248b8`
- `0x1800249c8`
- `0x180024aa0`
- `0x18002d6d8`
- `0x18003540c`
- `0x180045c70`
- `0x18004866c`
- `0x18004a2b8`
- `0x18004a668`
- `0x1800545d4`
- `0x180055c38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002477d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002477d`

## string_xrefs

- `0x180024799`: `PrintConfig.dll`
- `0x180024836`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall CreatePrintConfigData(void *a1, struct PrintConfigData **a2)
{
  int PrinterDriver8; // eax
  signed int PrinterDriver3; // ebx
  char v6; // si
  bool v7; // al
  void *v8; // rdi
  void *v9; // rax
  const wchar_t *v10; // rbx
  wchar_t *v11; // rax
  const wchar_t *v12; // rcx
  signed int v14; // eax
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdx
  __int128 Block; // [rsp+20h] [rbp-38h] BYREF
  struct _PRINTER_INFO_4W *v18[2]; // [rsp+30h] [rbp-28h] BYREF
  char v19; // [rsp+40h] [rbp-18h]
  struct RemotePrintConfigData *v20; // [rsp+A0h] [rbp+48h] BYREF

  v19 = 0;
  Block = 0;
  *(_OWORD *)v18 = 0;
  PrinterDriver8 = PrivateGetPrinterDriver8(a1, (struct _DRIVER_INFO_8W **)&Block + 1);
  PrinterDriver3 = PrinterDriver8;
  v6 = 1;
  if ( PrinterDriver8 < 0
    && (PrinterDriver8 != -2147024772
     || (PrinterDriver3 = PrivateGetPrinterDriver3(a1, (struct _DRIVER_INFO_3W **)&Block), PrinterDriver3 < 0))
    || (PrinterDriver3 = PrivateGetPrinterInfo4(a1, v18), PrinterDriver3 < 0) )
  {
LABEL_16:
    v8 = (void *)*((_QWORD *)&Block + 1);
    LOBYTE(v20) = 1;
    if ( PrinterDriver3 < 0 )
      goto LABEL_13;
    goto LABEL_5;
  }
  v7 = IsGUIDPrinter(v18[0]->pPrinterName);
  v8 = (void *)*((_QWORD *)&Block + 1);
  if ( v7 )
  {
    v15 = Block;
    if ( *((_QWORD *)&Block + 1) )
      v15 = *((_QWORD *)&Block + 1);
    if ( DoesFullPathMatchFile(*(const unsigned __int16 **)(v15 + 40), L"PrintConfig.dll") )
    {
      v19 = 1;
      v18[1] = 0;
      PrinterDriver3 = GetPrinterDataString(a1, v16, (unsigned __int16 **)&v18[1]);
      goto LABEL_16;
    }
  }
  v19 = 0;
  LOBYTE(v20) = 1;
LABEL_5:
  v9 = (void *)Block;
  if ( v8 )
    v9 = v8;
  v10 = (const wchar_t *)*((_QWORD *)v9 + 5);
  v11 = wcsrchr(v10, 0x5Cu);
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v10;
  if ( v12 && !wcsicmp(v12, L"PrintConfig.dll") )
  {
    v14 = IsLocalV4Printer(v18[0]->pPrinterName, a1, (bool *)&v20);
    v6 = (char)v20;
    PrinterDriver3 = v14;
  }
  else
  {
    PrinterDriver3 = 0;
  }
  if ( PrinterDriver3 >= 0 )
  {
    v20 = 0;
    if ( v6 )
      PrinterDriver3 = LocalPrintConfigData::CreateLocalPrintConfigData(
                         a1,
                         (struct PrintConfigDataContext *)&Block,
                         &v20);
    else
      PrinterDriver3 = RemotePrintConfigData::CreateRemotePrintConfigData(
                         a1,
                         (struct PrintConfigDataContext *)&Block,
                         &v20);
    *a2 = v20;
    v8 = (void *)*((_QWORD *)&Block + 1);
  }
LABEL_13:
  operator delete((void *)Block);
  operator delete(v8);
  operator delete(v18[0]);
  operator delete(v18[1]);
  return (unsigned int)PrinterDriver3;
}

```

## disassembly

```asm
0x1800246f0  push    rbp
0x1800246f2  push    rbx
0x1800246f3  push    rsi
0x1800246f4  push    rdi
0x1800246f5  push    r14
0x1800246f7  push    r15
0x1800246f9  mov     rbp, rsp
0x1800246fc  sub     rsp, 58h
0x180024700  mov     r15, rdx
0x180024703  mov     [rbp+var_18], 0
0x180024707  xorps   xmm0, xmm0
0x18002470a  lea     rdx, [rbp+var_30]; struct _DRIVER_INFO_8W **
0x18002470e  xorps   xmm1, xmm1
0x180024711  mov     r14, rcx
0x180024714  movdqu  xmmword ptr [rbp-38h], xmm0
0x180024719  movdqu  xmmword ptr [rbp+var_28], xmm1
0x18002471e  call    ?PrivateGetPrinterDriver8@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrivateGetPrinterDriver8(void *,_DRIVER_INFO_8W * *)
0x180024723  mov     ebx, eax
0x180024725  mov     sil, 1
0x180024728  test    eax, eax
0x18002472a  js      loc_180024829
0x180024730  lea     rdx, [rbp+var_28]; struct _PRINTER_INFO_4W **
0x180024734  mov     rcx, r14; hPrinter
0x180024737  call    ?PrivateGetPrinterInfo4@@YAJPEAXPEAPEAU_PRINTER_INFO_4W@@@Z; PrivateGetPrinterInfo4(void *,_PRINTER_INFO_4W * *)
0x18002473c  mov     ebx, eax
0x18002473e  test    eax, eax
0x180024740  js      loc_180024817
0x180024746  mov     rcx, [rbp+var_28]
0x18002474a  mov     rcx, [rcx]; unsigned __int16 *
0x18002474d  call    ?IsGUIDPrinter@@YA_NPEBG@Z; IsGUIDPrinter(ushort const *)
0x180024752  mov     rdi, [rbp+var_30]
0x180024756  test    al, al
0x180024758  jnz     loc_180024832
0x18002475e  mov     [rbp+var_18], 0
0x180024762  mov     byte ptr [rbp+arg_10], sil
0x180024766  mov     rax, [rbp+Block]
0x18002476a  test    rdi, rdi
0x18002476d  mov     edx, 5Ch ; '\'; Ch
0x180024772  cmovnz  rax, rdi
0x180024776  mov     rbx, [rax+28h]
0x18002477a  mov     rcx, rbx; Str
0x18002477d  call    cs:__imp_wcsrchr
0x180024784  nop     dword ptr [rax+rax+00h]
0x180024789  test    rax, rax
0x18002478c  lea     rcx, [rax+2]
0x180024790  cmovz   rcx, rbx; String1
0x180024794  test    rcx, rcx
0x180024797  jz      short loc_1800247A9
0x180024799  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800247a0  call    _wcsicmp
0x1800247a5  test    eax, eax
0x1800247a7  jz      short loc_1800247E6
0x1800247a9  xor     ebx, ebx
0x1800247ab  test    ebx, ebx
0x1800247ad  jns     loc_180024871
0x1800247b3  mov     rcx, [rbp+Block]; Block
0x1800247b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800247bc  mov     rcx, rdi; Block
0x1800247bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800247c4  mov     rcx, [rbp+var_28]; Block
0x1800247c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800247cd  mov     rcx, [rbp+var_28+8]; Block
0x1800247d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800247d6  mov     eax, ebx
0x1800247d8  add     rsp, 58h
0x1800247dc  pop     r15
0x1800247de  pop     r14
0x1800247e0  pop     rdi
0x1800247e1  pop     rsi
0x1800247e2  pop     rbx
0x1800247e3  pop     rbp
0x1800247e4  retn
0x1800247e6  mov     rcx, [rbp+var_28]
0x1800247ea  lea     r8, [rbp+arg_10]; bool *
0x1800247ee  mov     rdx, r14; void *
0x1800247f1  mov     rcx, [rcx]; pPrinterName
0x1800247f4  call    ?IsLocalV4Printer@@YAJPEBGPEAXPEA_N@Z; IsLocalV4Printer(ushort const *,void *,bool *)
0x1800247f9  mov     sil, byte ptr [rbp+arg_10]
0x1800247fd  mov     ebx, eax
0x1800247ff  jmp     short loc_1800247AB
0x180024801  lea     rdx, [rbp+Block]; struct _DRIVER_INFO_3W **
0x180024805  mov     rcx, r14; hPrinter
0x180024808  call    ?PrivateGetPrinterDriver3@@YAJPEAXPEAPEAU_DRIVER_INFO_3W@@@Z; PrivateGetPrinterDriver3(void *,_DRIVER_INFO_3W * *)
0x18002480d  mov     ebx, eax
0x18002480f  test    eax, eax
0x180024811  jns     loc_180024730
0x180024817  mov     rdi, [rbp+var_30]
0x18002481b  mov     byte ptr [rbp+arg_10], sil
0x18002481f  test    ebx, ebx
0x180024821  jns     loc_180024766
0x180024827  jmp     short loc_1800247B3
0x180024829  cmp     eax, 8007007Ch
0x18002482e  jnz     short loc_180024817
0x180024830  jmp     short loc_180024801
0x180024832  mov     rcx, [rbp+Block]
0x180024836  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x18002483d  test    rdi, rdi
0x180024840  cmovnz  rcx, rdi
0x180024844  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180024848  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18002484d  test    al, al
0x18002484f  jz      loc_18002475E
0x180024855  lea     r8, [rbp+var_28+8]; unsigned __int16 **
0x180024859  mov     [rbp+var_18], sil
0x18002485d  mov     rcx, r14; hPrinter
0x180024860  mov     [rbp+var_28+8], 0
0x180024868  call    ?GetPrinterDataString@@YAJPEAXPEBGPEAPEAG@Z; GetPrinterDataString(void *,ushort const *,ushort * *)
0x18002486d  mov     ebx, eax
0x18002486f  jmp     short loc_180024817
0x180024871  mov     [rbp+arg_10], 0
0x180024879  lea     r8, [rbp+arg_10]; struct RemotePrintConfigData **
0x18002487d  lea     rdx, [rbp+Block]; struct PrintConfigDataContext *
0x180024881  mov     rcx, r14; void *
0x180024884  test    sil, sil
0x180024887  jz      short loc_180024899
0x180024889  call    ?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; LocalPrintConfigData::CreateLocalPrintConfigData(void *,PrintConfigDataContext &,LocalPrintConfigData * *)
0x18002488e  mov     rcx, [rbp+arg_10]
0x180024892  mov     ebx, eax
0x180024894  mov     [r15], rcx
0x180024897  jmp     short loc_1800248A7
0x180024899  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)
0x18002489e  mov     ebx, eax
0x1800248a0  mov     rax, [rbp+arg_10]
0x1800248a4  mov     [r15], rax
0x1800248a7  mov     rdi, [rbp+var_30]
0x1800248ab  jmp     loc_1800247B3
```
