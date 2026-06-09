# CreatePrintConfigData(void *,PrintConfigData * *)

- ea: `0x1800241ac`
- end: `0x180024365`
- name: `?CreatePrintConfigData@@YAJPEAXPEAPEAVPrintConfigData@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(void *, struct PrintConfigData **)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180023e18`
- `0x180024554`
- `0x180025780`
- `0x18003e994`

## callees

- `0x1800241ac`
- `0x18002436c`
- `0x18002445c`
- `0x180024528`
- `0x18002ce68`
- `0x180034a60`
- `0x180044998`
- `0x18004723c`
- `0x180048d98`
- `0x180049128`
- `0x180052c40`
- `0x180054150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180024239`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180024239`

## string_xrefs

- `0x18002424f`: `PrintConfig.dll`
- `0x1800242eb`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall CreatePrintConfigData(void *a1, struct PrintConfigData **a2)
{
  int PrinterDriver8; // eax
  int PrinterDriver3; // ebx
  char v6; // si
  bool v7; // al
  void *v8; // rdi
  void *v9; // rax
  const wchar_t *v10; // rbx
  wchar_t *v11; // rax
  const wchar_t *v12; // rcx
  int v14; // eax
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
0x1800241ac  push    rbp
0x1800241ae  push    rbx
0x1800241af  push    rsi
0x1800241b0  push    rdi
0x1800241b1  push    r14
0x1800241b3  push    r15
0x1800241b5  mov     rbp, rsp
0x1800241b8  sub     rsp, 58h
0x1800241bc  mov     r15, rdx
0x1800241bf  mov     [rbp+var_18], 0
0x1800241c3  xorps   xmm0, xmm0
0x1800241c6  lea     rdx, [rbp+var_30]; struct _DRIVER_INFO_8W **
0x1800241ca  xorps   xmm1, xmm1
0x1800241cd  mov     r14, rcx
0x1800241d0  movdqu  xmmword ptr [rbp-38h], xmm0
0x1800241d5  movdqu  xmmword ptr [rbp+var_28], xmm1
0x1800241da  call    ?PrivateGetPrinterDriver8@@YAJPEAXPEAPEAU_DRIVER_INFO_8W@@@Z; PrivateGetPrinterDriver8(void *,_DRIVER_INFO_8W * *)
0x1800241df  mov     ebx, eax
0x1800241e1  mov     sil, 1
0x1800241e4  test    eax, eax
0x1800241e6  js      loc_1800242DE
0x1800241ec  lea     rdx, [rbp+var_28]; struct _PRINTER_INFO_4W **
0x1800241f0  mov     rcx, r14; hPrinter
0x1800241f3  call    ?PrivateGetPrinterInfo4@@YAJPEAXPEAPEAU_PRINTER_INFO_4W@@@Z; PrivateGetPrinterInfo4(void *,_PRINTER_INFO_4W * *)
0x1800241f8  mov     ebx, eax
0x1800241fa  test    eax, eax
0x1800241fc  js      loc_1800242CC
0x180024202  mov     rcx, [rbp+var_28]
0x180024206  mov     rcx, [rcx]; unsigned __int16 *
0x180024209  call    ?IsGUIDPrinter@@YA_NPEBG@Z; IsGUIDPrinter(ushort const *)
0x18002420e  mov     rdi, [rbp+var_30]
0x180024212  test    al, al
0x180024214  jnz     loc_1800242E7
0x18002421a  mov     [rbp+var_18], 0
0x18002421e  mov     byte ptr [rbp+arg_10], sil
0x180024222  mov     rax, [rbp+Block]
0x180024226  test    rdi, rdi
0x180024229  mov     edx, 5Ch ; '\'; Ch
0x18002422e  cmovnz  rax, rdi
0x180024232  mov     rbx, [rax+28h]
0x180024236  mov     rcx, rbx; Str
0x180024239  call    cs:__imp_wcsrchr
0x18002423f  test    rax, rax
0x180024242  lea     rcx, [rax+2]
0x180024246  cmovz   rcx, rbx; String1
0x18002424a  test    rcx, rcx
0x18002424d  jz      short loc_18002425F
0x18002424f  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180024256  call    _wcsicmp
0x18002425b  test    eax, eax
0x18002425d  jz      short loc_18002429B
0x18002425f  xor     ebx, ebx
0x180024261  test    ebx, ebx
0x180024263  jns     loc_180024326
0x180024269  mov     rcx, [rbp+Block]; Block
0x18002426d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024272  mov     rcx, rdi; Block
0x180024275  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002427a  mov     rcx, [rbp+var_28]; Block
0x18002427e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024283  mov     rcx, [rbp+var_28+8]; Block
0x180024287  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002428c  mov     eax, ebx
0x18002428e  add     rsp, 58h
0x180024292  pop     r15
0x180024294  pop     r14
0x180024296  pop     rdi
0x180024297  pop     rsi
0x180024298  pop     rbx
0x180024299  pop     rbp
0x18002429a  retn
0x18002429b  mov     rcx, [rbp+var_28]
0x18002429f  lea     r8, [rbp+arg_10]; bool *
0x1800242a3  mov     rdx, r14; void *
0x1800242a6  mov     rcx, [rcx]; pPrinterName
0x1800242a9  call    ?IsLocalV4Printer@@YAJPEBGPEAXPEA_N@Z; IsLocalV4Printer(ushort const *,void *,bool *)
0x1800242ae  mov     sil, byte ptr [rbp+arg_10]
0x1800242b2  mov     ebx, eax
0x1800242b4  jmp     short loc_180024261
0x1800242b6  lea     rdx, [rbp+Block]; struct _DRIVER_INFO_3W **
0x1800242ba  mov     rcx, r14; hPrinter
0x1800242bd  call    ?PrivateGetPrinterDriver3@@YAJPEAXPEAPEAU_DRIVER_INFO_3W@@@Z; PrivateGetPrinterDriver3(void *,_DRIVER_INFO_3W * *)
0x1800242c2  mov     ebx, eax
0x1800242c4  test    eax, eax
0x1800242c6  jns     loc_1800241EC
0x1800242cc  mov     rdi, [rbp+var_30]
0x1800242d0  mov     byte ptr [rbp+arg_10], sil
0x1800242d4  test    ebx, ebx
0x1800242d6  jns     loc_180024222
0x1800242dc  jmp     short loc_180024269
0x1800242de  cmp     eax, 8007007Ch
0x1800242e3  jnz     short loc_1800242CC
0x1800242e5  jmp     short loc_1800242B6
0x1800242e7  mov     rcx, [rbp+Block]
0x1800242eb  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800242f2  test    rdi, rdi
0x1800242f5  cmovnz  rcx, rdi
0x1800242f9  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1800242fd  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180024302  test    al, al
0x180024304  jz      loc_18002421A
0x18002430a  lea     r8, [rbp+var_28+8]; unsigned __int16 **
0x18002430e  mov     [rbp+var_18], sil
0x180024312  mov     rcx, r14; hPrinter
0x180024315  mov     [rbp+var_28+8], 0
0x18002431d  call    ?GetPrinterDataString@@YAJPEAXPEBGPEAPEAG@Z; GetPrinterDataString(void *,ushort const *,ushort * *)
0x180024322  mov     ebx, eax
0x180024324  jmp     short loc_1800242CC
0x180024326  mov     [rbp+arg_10], 0
0x18002432e  lea     r8, [rbp+arg_10]; struct RemotePrintConfigData **
0x180024332  lea     rdx, [rbp+Block]; struct PrintConfigDataContext *
0x180024336  mov     rcx, r14; void *
0x180024339  test    sil, sil
0x18002433c  jz      short loc_18002434E
0x18002433e  call    ?CreateLocalPrintConfigData@LocalPrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; LocalPrintConfigData::CreateLocalPrintConfigData(void *,PrintConfigDataContext &,LocalPrintConfigData * *)
0x180024343  mov     rcx, [rbp+arg_10]
0x180024347  mov     ebx, eax
0x180024349  mov     [r15], rcx
0x18002434c  jmp     short loc_18002435C
0x18002434e  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXAEAVPrintConfigDataContext@@PEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,PrintConfigDataContext &,RemotePrintConfigData * *)
0x180024353  mov     ebx, eax
0x180024355  mov     rax, [rbp+arg_10]
0x180024359  mov     [r15], rax
0x18002435c  mov     rdi, [rbp+var_30]
0x180024360  jmp     loc_180024269
```
