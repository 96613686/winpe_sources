# VFreePDEVData

- ea: `0x1800057c4`
- end: `0x180005a83`
- name: `VFreePDEVData`
- size: `703`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800040b0`
- `0x1800041a0`

## callees

- `0x1800057c4`
- `0x18000ae40`
- `0x180016544`
- `0x18001b068`
- `0x18001d5bc`
- `0x18001f020`
- `0x180020c7c`
- `0x180026e80`
- `0x18002826c`
- `0x18005d010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x1800058a1`
- `KERNEL32!HeapDestroy` at `0x1800058a1`
- `KERNEL32!LocalFree` at `0x1800057fb`
- `KERNEL32!LocalFree` at `0x180005837`
- `KERNEL32!LocalFree` at `0x1800058b3`
- `KERNEL32!LocalFree` at `0x1800058d1`
- `KERNEL32!LocalFree` at `0x18000590c`
- `KERNEL32!LocalFree` at `0x180005928`
- `KERNEL32!LocalFree` at `0x18000595d`
- `KERNEL32!LocalFree` at `0x180005980`
- `KERNEL32!LocalFree` at `0x180005996`
- `KERNEL32!LocalFree` at `0x180005a34`
- `KERNEL32!LocalFree` at `0x180005a46`
- `KERNEL32!LocalFree` at `0x180005a58`
- `KERNEL32!LocalFree` at `0x180005a6d`
- `KERNEL32!LocalFree` at `0x1800057fb`
- `KERNEL32!LocalFree` at `0x180005837`
- `KERNEL32!LocalFree` at `0x1800058b3`
- `KERNEL32!LocalFree` at `0x1800058d1`
- `KERNEL32!LocalFree` at `0x18000590c`
- `KERNEL32!LocalFree` at `0x180005928`
- `KERNEL32!LocalFree` at `0x18000595d`
- `KERNEL32!LocalFree` at `0x180005980`
- `KERNEL32!LocalFree` at `0x180005996`
- `KERNEL32!LocalFree` at `0x180005a34`
- `KERNEL32!LocalFree` at `0x180005a46`
- `KERNEL32!LocalFree` at `0x180005a58`
- `KERNEL32!LocalFree` at `0x180005a6d`
- `GDI32!EngFreeModule` at `0x18000588f`
- `GDI32!EngFreeModule` at `0x18000588f`
- `GDI32!EngDeletePalette` at `0x180005880`
- `GDI32!EngDeletePalette` at `0x180005880`
- `ole32!CoUninitialize` at `0x180005812`
- `ole32!CoUninitialize` at `0x180005812`

## pseudocode

```c
void __fastcall VFreePDEVData(HLOCAL hMem)
{
  void *v2; // rcx
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rdx
  HPALETTE v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  unsigned int v11; // edi
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  int v24; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !hMem )
    return;
  if ( *((_DWORD *)hMem + 961) )
  {
    v2 = (void *)*((_QWORD *)hMem + 433);
    if ( v2 )
    {
      LocalFree(v2);
      *((_QWORD *)hMem + 433) = 0;
    }
  }
  else
  {
    VUnloadOemPlugins();
  }
  if ( (*((_BYTE *)hMem + 80) & 0x10) != 0 )
    CoUninitialize();
  v3 = *((_QWORD *)hMem + 266);
  if ( v3 )
  {
    if ( !*((_DWORD *)hMem + 961) )
    {
      LocalFree(*((HLOCAL *)hMem + 266));
      goto LABEL_16;
    }
    v4 = InitializeModernPrintConfigHelper();
    if ( v4 >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(__int64))g_unloadRawPScriptPpdConfig)(v3);
      if ( v4 >= 0 )
        goto LABEL_16;
      v5 = 114;
    }
    else
    {
      v5 = 112;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
      (const char *)(unsigned int)v4,
      v24);
  }
LABEL_16:
  v6 = (HPALETTE)*((_QWORD *)hMem + 15);
  if ( v6 )
    EngDeletePalette(v6);
  v7 = (void *)*((_QWORD *)hMem + 13);
  if ( v7 )
    EngFreeModule(v7);
  v8 = (void *)*((_QWORD *)hMem + 467);
  if ( v8 )
    HeapDestroy(v8);
  while ( 1 )
  {
    v9 = (_QWORD *)*((_QWORD *)hMem + 294);
    if ( !v9 )
      break;
    *((_QWORD *)hMem + 294) = *v9;
    LocalFree(v9);
  }
  while ( 1 )
  {
    v10 = (_QWORD *)*((_QWORD *)hMem + 295);
    if ( !v10 )
      break;
    *((_QWORD *)hMem + 295) = *v10;
    LocalFree(v10);
  }
  DevFontFreeList(hMem);
  if ( (*((_BYTE *)hMem + 744) & 2) == 0 )
  {
    v11 = 0;
    do
    {
      v12 = (void *)*((_QWORD *)hMem + 17 * v11 + 100);
      if ( v12 )
        LocalFree(v12);
      ++v11;
    }
    while ( v11 <= *((_DWORD *)hMem + 187) );
  }
  v13 = (void *)*((_QWORD *)hMem + 441);
  if ( v13 )
    LocalFree(v13);
  *((_QWORD *)hMem + 441) = 0;
  BTermUFL(hMem);
  BDeletePSFonts(hMem);
  FreeSpecialPSBuffer(hMem);
  v14 = (void *)*((_QWORD *)hMem + 464);
  if ( v14 )
  {
    LocalFree(v14);
    *((_QWORD *)hMem + 464) = 0;
  }
  if ( !*((_DWORD *)hMem + 961) )
  {
    v15 = (void *)*((_QWORD *)hMem + 11);
    if ( v15 )
      LocalFree(v15);
    v16 = (void *)*((_QWORD *)hMem + 87);
    if ( v16 )
      LocalFree(v16);
    goto LABEL_53;
  }
  v17 = InitializeModernPrintConfigHelper();
  if ( v17 >= 0 )
  {
    v17 = ((__int64 (__fastcall *)(_QWORD))g_freePScriptDevMode)(*((_QWORD *)hMem + 11));
    if ( v17 >= 0 )
      goto LABEL_46;
    v18 = 139;
  }
  else
  {
    v18 = 138;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v18,
    (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
    (const char *)(unsigned int)v17,
    v24);
LABEL_46:
  v19 = InitializeModernPrintConfigHelper();
  if ( v19 >= 0 )
  {
    if ( !*((_QWORD *)hMem + 87) )
      goto LABEL_53;
    v19 = ((__int64 (*)(void))g_freePsRedirectedDriverInfo)();
    if ( v19 >= 0 )
    {
      *((_QWORD *)hMem + 87) = 0;
      goto LABEL_53;
    }
    v20 = 270;
  }
  else
  {
    v20 = 267;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v20,
    (unsigned int)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
    (const char *)(unsigned int)v19,
    v24);
LABEL_53:
  v21 = (void *)*((_QWORD *)hMem + 86);
  if ( v21 )
    LocalFree(v21);
  v22 = (void *)*((_QWORD *)hMem + 362);
  if ( v22 )
    LocalFree(v22);
  v23 = (void *)*((_QWORD *)hMem + 274);
  if ( v23 )
    LocalFree(v23);
  HostFontFree(*((HLOCAL *)hMem + 468));
  LocalFree(hMem);
}

```

## disassembly

```asm
0x1800057c4  test    rcx, rcx
0x1800057c7  jz      locret_180005A82
0x1800057cd  mov     [rsp+arg_0], rbx
0x1800057d2  mov     [rsp+arg_8], rbp
0x1800057d7  push    rdi; int
0x1800057d8  sub     rsp, 20h
0x1800057dc  cmp     dword ptr [rcx+0F04h], 0
0x1800057e3  mov     rbx, rcx
0x1800057e6  jnz     short loc_1800057EF
0x1800057e8  call    VUnloadOemPlugins
0x1800057ed  jmp     short loc_18000580C
0x1800057ef  mov     rcx, [rcx+0D88h]; hMem
0x1800057f6  test    rcx, rcx
0x1800057f9  jz      short loc_18000580C
0x1800057fb  call    cs:__imp_LocalFree
0x180005801  mov     qword ptr [rbx+0D88h], 0
0x18000580c  test    byte ptr [rbx+50h], 10h
0x180005810  jz      short loc_180005818
0x180005812  call    cs:__imp_CoUninitialize
0x180005818  mov     rdi, [rbx+850h]
0x18000581f  lea     rbp, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x180005826  test    rdi, rdi
0x180005829  jz      short loc_180005877
0x18000582b  cmp     dword ptr [rbx+0F04h], 0
0x180005832  jnz     short loc_18000583F
0x180005834  mov     rcx, rdi; hMem
0x180005837  call    cs:__imp_LocalFree
0x18000583d  jmp     short loc_180005877
0x18000583f  call    InitializeModernPrintConfigHelper
0x180005844  test    eax, eax
0x180005846  jns     short loc_18000584F
0x180005848  mov     edx, 70h ; 'p'
0x18000584d  jmp     short loc_180005867
0x18000584f  mov     rax, cs:?g_unloadRawPScriptPpdConfig@@3P6AJPEAU_RAWBINARYDATA@@@_EEA
0x180005856  mov     rcx, rdi
0x180005859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000585e  test    eax, eax
0x180005860  jns     short loc_180005877
0x180005862  mov     edx, 72h ; 'r'; void *
0x180005867  mov     rcx, [rsp+28h]; this
0x18000586c  mov     r9d, eax; char *
0x18000586f  mov     r8, rbp; unsigned int
0x180005872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005877  mov     rcx, [rbx+78h]; hpal
0x18000587b  test    rcx, rcx
0x18000587e  jz      short loc_180005886
0x180005880  call    cs:__imp_EngDeletePalette
0x180005886  mov     rcx, [rbx+68h]; h
0x18000588a  test    rcx, rcx
0x18000588d  jz      short loc_180005895
0x18000588f  call    cs:__imp_EngFreeModule
0x180005895  mov     rcx, [rbx+0E98h]; hHeap
0x18000589c  test    rcx, rcx
0x18000589f  jz      short loc_1800058B9
0x1800058a1  call    cs:__imp_HeapDestroy
0x1800058a7  jmp     short loc_1800058B9
0x1800058a9  mov     rax, [rcx]
0x1800058ac  mov     [rbx+930h], rax
0x1800058b3  call    cs:__imp_LocalFree
0x1800058b9  mov     rcx, [rbx+930h]; hMem
0x1800058c0  test    rcx, rcx
0x1800058c3  jnz     short loc_1800058A9
0x1800058c5  jmp     short loc_1800058D7
0x1800058c7  mov     rax, [rcx]
0x1800058ca  mov     [rbx+938h], rax
0x1800058d1  call    cs:__imp_LocalFree
0x1800058d7  mov     rcx, [rbx+938h]; hMem
0x1800058de  test    rcx, rcx
0x1800058e1  jnz     short loc_1800058C7
0x1800058e3  mov     rcx, rbx
0x1800058e6  call    DevFontFreeList
0x1800058eb  test    byte ptr [rbx+2E8h], 2
0x1800058f2  jnz     short loc_18000591C
0x1800058f4  xor     edi, edi
0x1800058f6  mov     eax, edi
0x1800058f8  imul    rcx, rax, 88h
0x1800058ff  mov     rcx, [rcx+rbx+320h]; hMem
0x180005907  test    rcx, rcx
0x18000590a  jz      short loc_180005912
0x18000590c  call    cs:__imp_LocalFree
0x180005912  inc     edi
0x180005914  cmp     edi, [rbx+2ECh]
0x18000591a  jbe     short loc_1800058F6
0x18000591c  mov     rcx, [rbx+0DC8h]; hMem
0x180005923  test    rcx, rcx
0x180005926  jz      short loc_18000592E
0x180005928  call    cs:__imp_LocalFree
0x18000592e  mov     rcx, rbx
0x180005931  mov     qword ptr [rbx+0DC8h], 0
0x18000593c  call    BTermUFL
0x180005941  mov     rcx, rbx
0x180005944  call    BDeletePSFonts
0x180005949  mov     rcx, rbx
0x18000594c  call    FreeSpecialPSBuffer
0x180005951  mov     rcx, [rbx+0E80h]; hMem
0x180005958  test    rcx, rcx
0x18000595b  jz      short loc_18000596E
0x18000595d  call    cs:__imp_LocalFree
0x180005963  mov     qword ptr [rbx+0E80h], 0
0x18000596e  cmp     dword ptr [rbx+0F04h], 0
0x180005975  jnz     short loc_1800059A1
0x180005977  mov     rcx, [rbx+58h]; hMem
0x18000597b  test    rcx, rcx
0x18000597e  jz      short loc_180005986
0x180005980  call    cs:__imp_LocalFree
0x180005986  mov     rcx, [rbx+2B8h]; hMem
0x18000598d  test    rcx, rcx
0x180005990  jz      loc_180005A28
0x180005996  call    cs:__imp_LocalFree
0x18000599c  jmp     loc_180005A28
0x1800059a1  call    InitializeModernPrintConfigHelper
0x1800059a6  test    eax, eax
0x1800059a8  jns     short loc_1800059B1
0x1800059aa  mov     edx, 8Ah
0x1800059af  jmp     short loc_1800059CA
0x1800059b1  mov     rcx, [rbx+58h]
0x1800059b5  mov     rax, cs:?g_freePScriptDevMode@@3P6AJPEAU_devicemodeW@@@_EEA
0x1800059bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059c1  test    eax, eax
0x1800059c3  jns     short loc_1800059DA
0x1800059c5  mov     edx, 8Bh; void *
0x1800059ca  mov     rcx, [rsp+28h]; this
0x1800059cf  mov     r9d, eax; char *
0x1800059d2  mov     r8, rbp; unsigned int
0x1800059d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059da  call    InitializeModernPrintConfigHelper
0x1800059df  test    eax, eax
0x1800059e1  jns     short loc_1800059FA
0x1800059e3  mov     edx, 10Bh; void *
0x1800059e8  mov     rcx, [rsp+28h]; this
0x1800059ed  mov     r8, rbp; unsigned int
0x1800059f0  mov     r9d, eax; char *
0x1800059f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059f8  jmp     short loc_180005A28
0x1800059fa  mov     rcx, [rbx+2B8h]
0x180005a01  test    rcx, rcx
0x180005a04  jz      short loc_180005A28
0x180005a06  mov     rax, cs:?g_freePsRedirectedDriverInfo@@3P6AJPEAU_DRIVER_INFO_3W@@@_EEA
0x180005a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a12  test    eax, eax
0x180005a14  jns     short loc_180005A1D
0x180005a16  mov     edx, 10Eh
0x180005a1b  jmp     short loc_1800059E8
0x180005a1d  mov     qword ptr [rbx+2B8h], 0
0x180005a28  mov     rcx, [rbx+2B0h]; hMem
0x180005a2f  test    rcx, rcx
0x180005a32  jz      short loc_180005A3A
0x180005a34  call    cs:__imp_LocalFree
0x180005a3a  mov     rcx, [rbx+0B50h]; hMem
0x180005a41  test    rcx, rcx
0x180005a44  jz      short loc_180005A4C
0x180005a46  call    cs:__imp_LocalFree
0x180005a4c  mov     rcx, [rbx+890h]; hMem
0x180005a53  test    rcx, rcx
0x180005a56  jz      short loc_180005A5E
0x180005a58  call    cs:__imp_LocalFree
0x180005a5e  mov     rcx, [rbx+0EA0h]; hMem
0x180005a65  call    HostFontFree
0x180005a6a  mov     rcx, rbx; hMem
0x180005a6d  call    cs:__imp_LocalFree
0x180005a73  mov     rbx, [rsp+28h+arg_0]
0x180005a78  mov     rbp, [rsp+28h+arg_8]
0x180005a7d  add     rsp, 20h
0x180005a81  pop     rdi
0x180005a82  retn
```
