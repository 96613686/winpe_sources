# VFreePDEVData

- ea: `0x180005858`
- end: `0x180005b7e`
- name: `VFreePDEVData`
- size: `806`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180004140`
- `0x180004240`

## callees

- `0x180005858`
- `0x18000b20c`
- `0x180016c84`
- `0x18001b9bc`
- `0x18001e02c`
- `0x18001fba4`
- `0x1800218d4`
- `0x180027c74`
- `0x180029298`
- `0x18005f010`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x180005953`
- `KERNEL32!HeapDestroy` at `0x180005953`
- `KERNEL32!LocalFree` at `0x18000588f`
- `KERNEL32!LocalFree` at `0x1800058d7`
- `KERNEL32!LocalFree` at `0x18000596b`
- `KERNEL32!LocalFree` at `0x18000598f`
- `KERNEL32!LocalFree` at `0x1800059d0`
- `KERNEL32!LocalFree` at `0x1800059f2`
- `KERNEL32!LocalFree` at `0x180005a2d`
- `KERNEL32!LocalFree` at `0x180005a56`
- `KERNEL32!LocalFree` at `0x180005a72`
- `KERNEL32!LocalFree` at `0x180005b16`
- `KERNEL32!LocalFree` at `0x180005b2e`
- `KERNEL32!LocalFree` at `0x180005b46`
- `KERNEL32!LocalFree` at `0x180005b61`
- `KERNEL32!LocalFree` at `0x18000588f`
- `KERNEL32!LocalFree` at `0x1800058d7`
- `KERNEL32!LocalFree` at `0x18000596b`
- `KERNEL32!LocalFree` at `0x18000598f`
- `KERNEL32!LocalFree` at `0x1800059d0`
- `KERNEL32!LocalFree` at `0x1800059f2`
- `KERNEL32!LocalFree` at `0x180005a2d`
- `KERNEL32!LocalFree` at `0x180005a56`
- `KERNEL32!LocalFree` at `0x180005a72`
- `KERNEL32!LocalFree` at `0x180005b16`
- `KERNEL32!LocalFree` at `0x180005b2e`
- `KERNEL32!LocalFree` at `0x180005b46`
- `KERNEL32!LocalFree` at `0x180005b61`
- `GDI32!EngFreeModule` at `0x18000593b`
- `GDI32!EngFreeModule` at `0x18000593b`
- `GDI32!EngDeletePalette` at `0x180005926`
- `GDI32!EngDeletePalette` at `0x180005926`
- `ole32!CoUninitialize` at `0x1800058ac`
- `ole32!CoUninitialize` at `0x1800058ac`

## pseudocode

```c
void __fastcall VFreePDEVData(_QWORD *hMem)
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
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !hMem )
    return;
  if ( *((_DWORD *)hMem + 961) )
  {
    v2 = (void *)hMem[433];
    if ( v2 )
    {
      LocalFree(v2);
      hMem[433] = 0;
    }
  }
  else
  {
    VUnloadOemPlugins(hMem);
  }
  if ( (hMem[10] & 0x10) != 0 )
    CoUninitialize();
  v3 = hMem[266];
  if ( v3 )
  {
    if ( !*((_DWORD *)hMem + 961) )
    {
      LocalFree((HLOCAL)hMem[266]);
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
      (__int64)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
      (const char *)(unsigned int)v4);
  }
LABEL_16:
  v6 = (HPALETTE)hMem[15];
  if ( v6 )
    EngDeletePalette(v6);
  v7 = (void *)hMem[13];
  if ( v7 )
    EngFreeModule(v7);
  v8 = (void *)hMem[467];
  if ( v8 )
    HeapDestroy(v8);
  while ( 1 )
  {
    v9 = (_QWORD *)hMem[294];
    if ( !v9 )
      break;
    hMem[294] = *v9;
    LocalFree(v9);
  }
  while ( 1 )
  {
    v10 = (_QWORD *)hMem[295];
    if ( !v10 )
      break;
    hMem[295] = *v10;
    LocalFree(v10);
  }
  DevFontFreeList((__int64)hMem);
  if ( (hMem[93] & 2) == 0 )
  {
    v11 = 0;
    do
    {
      v12 = (void *)hMem[17 * v11 + 100];
      if ( v12 )
        LocalFree(v12);
      ++v11;
    }
    while ( v11 <= *((_DWORD *)hMem + 187) );
  }
  v13 = (void *)hMem[441];
  if ( v13 )
    LocalFree(v13);
  hMem[441] = 0;
  BTermUFL(hMem);
  BDeletePSFonts((__int64)hMem);
  FreeSpecialPSBuffer((__int64)hMem);
  v14 = (void *)hMem[464];
  if ( v14 )
  {
    LocalFree(v14);
    hMem[464] = 0;
  }
  if ( !*((_DWORD *)hMem + 961) )
  {
    v15 = (void *)hMem[11];
    if ( v15 )
      LocalFree(v15);
    v16 = (void *)hMem[87];
    if ( v16 )
      LocalFree(v16);
    goto LABEL_53;
  }
  v17 = InitializeModernPrintConfigHelper();
  if ( v17 >= 0 )
  {
    v17 = ((__int64 (__fastcall *)(_QWORD))g_freePScriptDevMode)(hMem[11]);
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
    (__int64)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
    (const char *)(unsigned int)v17);
LABEL_46:
  v19 = InitializeModernPrintConfigHelper();
  if ( v19 >= 0 )
  {
    if ( !hMem[87] )
      goto LABEL_53;
    v19 = ((__int64 (*)(void))g_freePsRedirectedDriverInfo)();
    if ( v19 >= 0 )
    {
      hMem[87] = 0;
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
    (__int64)"printscan\\print\\drivers\\usermode\\pscript\\virtualprinterutils.cxx",
    (const char *)(unsigned int)v19);
LABEL_53:
  v21 = (void *)hMem[86];
  if ( v21 )
    LocalFree(v21);
  v22 = (void *)hMem[362];
  if ( v22 )
    LocalFree(v22);
  v23 = (void *)hMem[274];
  if ( v23 )
    LocalFree(v23);
  HostFontFree((_QWORD *)hMem[468]);
  LocalFree(hMem);
}

```

## disassembly

```asm
0x180005858  test    rcx, rcx
0x18000585b  jz      locret_180005B7C
0x180005861  mov     [rsp+arg_0], rbx
0x180005866  mov     [rsp+arg_8], rbp
0x18000586b  push    rdi; int
0x18000586c  sub     rsp, 20h
0x180005870  cmp     dword ptr [rcx+0F04h], 0
0x180005877  mov     rbx, rcx
0x18000587a  jnz     short loc_180005883
0x18000587c  call    VUnloadOemPlugins
0x180005881  jmp     short loc_1800058A6
0x180005883  mov     rcx, [rcx+0D88h]; hMem
0x18000588a  test    rcx, rcx
0x18000588d  jz      short loc_1800058A6
0x18000588f  call    cs:__imp_LocalFree
0x180005896  nop     dword ptr [rax+rax+00h]
0x18000589b  mov     qword ptr [rbx+0D88h], 0
0x1800058a6  test    byte ptr [rbx+50h], 10h
0x1800058aa  jz      short loc_1800058B8
0x1800058ac  call    cs:__imp_CoUninitialize
0x1800058b3  nop     dword ptr [rax+rax+00h]
0x1800058b8  mov     rdi, [rbx+850h]
0x1800058bf  lea     rbp, aPrintscanPrint; "printscan\\print\\drivers\\usermode\\ps"...
0x1800058c6  test    rdi, rdi
0x1800058c9  jz      short loc_18000591D
0x1800058cb  cmp     dword ptr [rbx+0F04h], 0
0x1800058d2  jnz     short loc_1800058E5
0x1800058d4  mov     rcx, rdi; hMem
0x1800058d7  call    cs:__imp_LocalFree
0x1800058de  nop     dword ptr [rax+rax+00h]
0x1800058e3  jmp     short loc_18000591D
0x1800058e5  call    InitializeModernPrintConfigHelper
0x1800058ea  test    eax, eax
0x1800058ec  jns     short loc_1800058F5
0x1800058ee  mov     edx, 70h ; 'p'
0x1800058f3  jmp     short loc_18000590D
0x1800058f5  mov     rax, cs:?g_unloadRawPScriptPpdConfig@@3P6AJPEAU_RAWBINARYDATA@@@_EEA
0x1800058fc  mov     rcx, rdi
0x1800058ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005904  test    eax, eax
0x180005906  jns     short loc_18000591D
0x180005908  mov     edx, 72h ; 'r'; void *
0x18000590d  mov     rcx, [rsp+28h]; this
0x180005912  mov     r9d, eax; char *
0x180005915  mov     r8, rbp; unsigned int
0x180005918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000591d  mov     rcx, [rbx+78h]; hpal
0x180005921  test    rcx, rcx
0x180005924  jz      short loc_180005932
0x180005926  call    cs:__imp_EngDeletePalette
0x18000592d  nop     dword ptr [rax+rax+00h]
0x180005932  mov     rcx, [rbx+68h]; h
0x180005936  test    rcx, rcx
0x180005939  jz      short loc_180005947
0x18000593b  call    cs:__imp_EngFreeModule
0x180005942  nop     dword ptr [rax+rax+00h]
0x180005947  mov     rcx, [rbx+0E98h]; hHeap
0x18000594e  test    rcx, rcx
0x180005951  jz      short loc_180005977
0x180005953  call    cs:__imp_HeapDestroy
0x18000595a  nop     dword ptr [rax+rax+00h]
0x18000595f  jmp     short loc_180005977
0x180005961  mov     rax, [rcx]
0x180005964  mov     [rbx+930h], rax
0x18000596b  call    cs:__imp_LocalFree
0x180005972  nop     dword ptr [rax+rax+00h]
0x180005977  mov     rcx, [rbx+930h]; hMem
0x18000597e  test    rcx, rcx
0x180005981  jnz     short loc_180005961
0x180005983  jmp     short loc_18000599B
0x180005985  mov     rax, [rcx]
0x180005988  mov     [rbx+938h], rax
0x18000598f  call    cs:__imp_LocalFree
0x180005996  nop     dword ptr [rax+rax+00h]
0x18000599b  mov     rcx, [rbx+938h]; hMem
0x1800059a2  test    rcx, rcx
0x1800059a5  jnz     short loc_180005985
0x1800059a7  mov     rcx, rbx
0x1800059aa  call    DevFontFreeList
0x1800059af  test    byte ptr [rbx+2E8h], 2
0x1800059b6  jnz     short loc_1800059E6
0x1800059b8  xor     edi, edi
0x1800059ba  mov     eax, edi
0x1800059bc  imul    rcx, rax, 88h
0x1800059c3  mov     rcx, [rcx+rbx+320h]; hMem
0x1800059cb  test    rcx, rcx
0x1800059ce  jz      short loc_1800059DC
0x1800059d0  call    cs:__imp_LocalFree
0x1800059d7  nop     dword ptr [rax+rax+00h]
0x1800059dc  inc     edi
0x1800059de  cmp     edi, [rbx+2ECh]
0x1800059e4  jbe     short loc_1800059BA
0x1800059e6  mov     rcx, [rbx+0DC8h]; hMem
0x1800059ed  test    rcx, rcx
0x1800059f0  jz      short loc_1800059FE
0x1800059f2  call    cs:__imp_LocalFree
0x1800059f9  nop     dword ptr [rax+rax+00h]
0x1800059fe  mov     rcx, rbx
0x180005a01  mov     qword ptr [rbx+0DC8h], 0
0x180005a0c  call    BTermUFL
0x180005a11  mov     rcx, rbx
0x180005a14  call    BDeletePSFonts
0x180005a19  mov     rcx, rbx
0x180005a1c  call    FreeSpecialPSBuffer
0x180005a21  mov     rcx, [rbx+0E80h]; hMem
0x180005a28  test    rcx, rcx
0x180005a2b  jz      short loc_180005A44
0x180005a2d  call    cs:__imp_LocalFree
0x180005a34  nop     dword ptr [rax+rax+00h]
0x180005a39  mov     qword ptr [rbx+0E80h], 0
0x180005a44  cmp     dword ptr [rbx+0F04h], 0
0x180005a4b  jnz     short loc_180005A83
0x180005a4d  mov     rcx, [rbx+58h]; hMem
0x180005a51  test    rcx, rcx
0x180005a54  jz      short loc_180005A62
0x180005a56  call    cs:__imp_LocalFree
0x180005a5d  nop     dword ptr [rax+rax+00h]
0x180005a62  mov     rcx, [rbx+2B8h]; hMem
0x180005a69  test    rcx, rcx
0x180005a6c  jz      loc_180005B0A
0x180005a72  call    cs:__imp_LocalFree
0x180005a79  nop     dword ptr [rax+rax+00h]
0x180005a7e  jmp     loc_180005B0A
0x180005a83  call    InitializeModernPrintConfigHelper
0x180005a88  test    eax, eax
0x180005a8a  jns     short loc_180005A93
0x180005a8c  mov     edx, 8Ah
0x180005a91  jmp     short loc_180005AAC
0x180005a93  mov     rcx, [rbx+58h]
0x180005a97  mov     rax, cs:?g_freePScriptDevMode@@3P6AJPEAU_devicemodeW@@@_EEA
0x180005a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa3  test    eax, eax
0x180005aa5  jns     short loc_180005ABC
0x180005aa7  mov     edx, 8Bh; void *
0x180005aac  mov     rcx, [rsp+28h]; this
0x180005ab1  mov     r9d, eax; char *
0x180005ab4  mov     r8, rbp; unsigned int
0x180005ab7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005abc  call    InitializeModernPrintConfigHelper
0x180005ac1  test    eax, eax
0x180005ac3  jns     short loc_180005ADC
0x180005ac5  mov     edx, 10Bh; void *
0x180005aca  mov     rcx, [rsp+28h]; this
0x180005acf  mov     r8, rbp; unsigned int
0x180005ad2  mov     r9d, eax; char *
0x180005ad5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ada  jmp     short loc_180005B0A
0x180005adc  mov     rcx, [rbx+2B8h]
0x180005ae3  test    rcx, rcx
0x180005ae6  jz      short loc_180005B0A
0x180005ae8  mov     rax, cs:?g_freePsRedirectedDriverInfo@@3P6AJPEAU_DRIVER_INFO_3W@@@_EEA
0x180005aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af4  test    eax, eax
0x180005af6  jns     short loc_180005AFF
0x180005af8  mov     edx, 10Eh
0x180005afd  jmp     short loc_180005ACA
0x180005aff  mov     qword ptr [rbx+2B8h], 0
0x180005b0a  mov     rcx, [rbx+2B0h]; hMem
0x180005b11  test    rcx, rcx
0x180005b14  jz      short loc_180005B22
0x180005b16  call    cs:__imp_LocalFree
0x180005b1d  nop     dword ptr [rax+rax+00h]
0x180005b22  mov     rcx, [rbx+0B50h]; hMem
0x180005b29  test    rcx, rcx
0x180005b2c  jz      short loc_180005B3A
0x180005b2e  call    cs:__imp_LocalFree
0x180005b35  nop     dword ptr [rax+rax+00h]
0x180005b3a  mov     rcx, [rbx+890h]; hMem
0x180005b41  test    rcx, rcx
0x180005b44  jz      short loc_180005B52
0x180005b46  call    cs:__imp_LocalFree
0x180005b4d  nop     dword ptr [rax+rax+00h]
0x180005b52  mov     rcx, [rbx+0EA0h]; hMem
0x180005b59  call    HostFontFree
0x180005b5e  mov     rcx, rbx; hMem
0x180005b61  call    cs:__imp_LocalFree
0x180005b68  nop     dword ptr [rax+rax+00h]
0x180005b6d  mov     rbx, [rsp+28h+arg_0]
0x180005b72  mov     rbp, [rsp+28h+arg_8]
0x180005b77  add     rsp, 20h
0x180005b7b  pop     rdi
0x180005b7c  retn
```
