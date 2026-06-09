# PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification(void)

- ea: `0x180014814`
- end: `0x1800148ea`
- name: `?TryLaunchUnusedPrinterNotification@PrinterCleanUpUtil@@YAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(PrinterCleanUpUtil *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800066c0`

## callees

- `0x18000670c`
- `0x18000d3d8`
- `0x180011ea8`
- `0x180012f8c`
- `0x180014814`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001485e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001485e`

## string_xrefs

- `0x180014850`: `SYSTEM\CurrentControlSet\Control\Print\PrinterCleanupTask\`
- `0x1800148a2`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x1800148cb`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::TryLaunchUnusedPrinterNotification(PrinterCleanUpUtil *this)
{
  bool *v1; // rdx
  __int64 result; // rax
  int v3; // eax
  const char *v4; // r9
  int v5; // eax
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v8; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  v9 = 8;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SYSTEM\\CurrentControlSet\\Control\\Print\\PrinterCleanupTask\\",
    L"SnoozeDate",
    0x20000048u,
    0,
    &v10,
    &v9);
  if ( v9 && !IsStale(v10, 0x46B8E92D8000uLL) )
    return 0;
  LOBYTE(v8) = 0;
  v3 = PrinterCleanUpUtil::CheckForUnusedRemovablePrinters((PrinterCleanUpUtil *)&v8, v1);
  try
  {
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
        (const char *)(unsigned int)v3,
        v6);
    if ( (_BYTE)v8 )
    {
      v5 = PrinterCleanUpUtil::LaunchUnusedPrinterNotification(retaddr);
      if ( v5 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x120,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
          (const char *)(unsigned int)v5,
          v6);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x124,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x180014814  mov     r11, rsp
0x180014817  sub     rsp, 48h
0x18001481b  mov     qword ptr [r11+18h], 0
0x180014823  mov     [rsp+48h+arg_8], 8
0x18001482b  lea     rax, [r11+10h]
0x18001482f  mov     [r11-18h], rax
0x180014833  lea     rax, [r11+18h]
0x180014837  mov     [r11-20h], rax
0x18001483b  mov     qword ptr [r11-28h], 0
0x180014843  mov     r9d, 20000048h; dwFlags
0x180014849  lea     r8, ValueName; "SnoozeDate"
0x180014850  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x180014857  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001485e  call    cs:__imp_RegGetValueW
0x180014864  cmp     [rsp+48h+arg_8], 0
0x180014869  jz      short loc_180014887
0x18001486b  mov     rdx, 46B8E92D8000h; unsigned __int64
0x180014875  mov     rcx, [rsp+48h+arg_10]; unsigned __int64
0x18001487a  call    ?IsStale@@YA_N_K0@Z; IsStale(unsigned __int64,unsigned __int64)
0x18001487f  test    al, al
0x180014881  jnz     short loc_180014887
0x180014883  xor     eax, eax
0x180014885  jmp     short loc_1800148E4
0x180014887  mov     byte ptr [rsp+48h+arg_0], 0
0x18001488c  lea     rcx, [rsp+48h+arg_0]; this
0x180014891  call    ?CheckForUnusedRemovablePrinters@PrinterCleanUpUtil@@YAJPEA_N@Z; PrinterCleanUpUtil::CheckForUnusedRemovablePrinters(bool *)
0x180014896  mov     rcx, [rsp+48h]; this
0x18001489b  test    eax, eax
0x18001489d  jns     short loc_1800148B3
0x18001489f  mov     r9d, eax; char *
0x1800148a2  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x1800148a9  mov     edx, 11Dh; void *
0x1800148ae  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800148b3  cmp     byte ptr [rsp+48h+arg_0], 0
0x1800148b8  jz      short loc_1800148DC
0x1800148ba  call    ?LaunchUnusedPrinterNotification@PrinterCleanUpUtil@@YAJXZ; PrinterCleanUpUtil::LaunchUnusedPrinterNotification(void)
0x1800148bf  mov     rcx, [rsp+48h]; this
0x1800148c4  test    eax, eax
0x1800148c6  jns     short loc_1800148DC
0x1800148c8  mov     r9d, eax; char *
0x1800148cb  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x1800148d2  mov     edx, 120h; void *
0x1800148d7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800148dc  xor     eax, eax
0x1800148de  jmp     short loc_1800148E4
0x1800148e0  mov     eax, [rsp+48h+arg_0]
0x1800148e4  add     rsp, 48h
0x1800148e8  retn
```
