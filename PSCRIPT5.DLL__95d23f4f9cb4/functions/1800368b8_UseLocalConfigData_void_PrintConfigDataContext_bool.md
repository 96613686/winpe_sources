# UseLocalConfigData(void *,PrintConfigDataContext &,bool *)

- ea: `0x1800368b8`
- end: `0x18003697d`
- name: `?UseLocalConfigData@@YAJPEAXAEAVPrintConfigDataContext@@PEA_N@Z`
- size: `197`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18003431c`

## callees

- `0x180034afc`
- `0x1800358fc`
- `0x180035c34`
- `0x1800368b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180036910`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180036910`
- `WINSPOOL!ClosePrinter` at `0x180036965`
- `WINSPOOL!ClosePrinter` at `0x180036965`

## string_xrefs

- `0x1800368e0`: `PrintConfig.dll`

## pseudocode

```c
__int64 __fastcall UseLocalConfigData(void *a1, struct PrintConfigDataContext *a2, bool *a3)
{
  __int64 v5; // rcx
  int v7; // ebx
  const wchar_t **v8; // rax
  WCHAR *v9; // rbx
  HANDLE v11; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hPrinter; // [rsp+48h] [rbp+20h] BYREF

  v5 = *((_QWORD *)a2 + 1);
  if ( !v5 )
    v5 = *(_QWORD *)a2;
  if ( DoesFullPathMatchFile(*(const unsigned __int16 **)(v5 + 40), L"PrintConfig.dll") )
  {
    v8 = (const wchar_t **)*((_QWORD *)a2 + 2);
    *a3 = 0;
    v9 = (WCHAR *)*v8;
    if ( *v8 && wcsstr(*v8, L"\\\\CSR|") )
    {
      return 0;
    }
    else
    {
      v11 = 0;
      hPrinter = 0;
      v7 = OpenPrinterIfNoCacheHandle(v9, a1, &v11, &hPrinter);
      if ( v7 >= 0 )
      {
        v7 = IsLocalV4Printer(v11, a3);
        if ( hPrinter )
          ClosePrinter(hPrinter);
      }
    }
  }
  else
  {
    v7 = 0;
    *a3 = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800368b8  mov     [rsp+arg_0], rbx
0x1800368bd  mov     [rsp+arg_10], rsi
0x1800368c2  push    rdi
0x1800368c3  sub     rsp, 20h
0x1800368c7  mov     rsi, rcx
0x1800368ca  mov     rdi, r8
0x1800368cd  mov     rcx, [rdx+8]
0x1800368d1  mov     rbx, rdx
0x1800368d4  test    rcx, rcx
0x1800368d7  jnz     short loc_1800368DC
0x1800368d9  mov     rcx, [rdx]
0x1800368dc  mov     rcx, [rcx+28h]; unsigned __int16 *
0x1800368e0  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x1800368e7  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x1800368ec  test    al, al
0x1800368ee  jnz     short loc_1800368F7
0x1800368f0  xor     ebx, ebx
0x1800368f2  mov     byte ptr [rdi], 1
0x1800368f5  jmp     short loc_18003696B
0x1800368f7  mov     rax, [rbx+10h]
0x1800368fb  mov     byte ptr [rdi], 0
0x1800368fe  mov     rbx, [rax]
0x180036901  test    rbx, rbx
0x180036904  jz      short loc_18003691F
0x180036906  lea     rdx, aCsr; "\\\\CSR|"
0x18003690d  mov     rcx, rbx; Str
0x180036910  call    cs:__imp_wcsstr
0x180036916  test    rax, rax
0x180036919  jz      short loc_18003691F
0x18003691b  xor     ebx, ebx
0x18003691d  jmp     short loc_18003696B
0x18003691f  lea     r9, [rsp+28h+hPrinter]; void **
0x180036924  mov     [rsp+28h+arg_8], 0
0x18003692d  lea     r8, [rsp+28h+arg_8]; void **
0x180036932  mov     [rsp+28h+hPrinter], 0
0x18003693b  mov     rdx, rsi; void *
0x18003693e  mov     rcx, rbx; pPrinterName
0x180036941  call    ?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z; OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)
0x180036946  mov     ebx, eax
0x180036948  test    eax, eax
0x18003694a  js      short loc_18003696B
0x18003694c  mov     rcx, [rsp+28h+arg_8]; hPrinter
0x180036951  mov     rdx, rdi; bool *
0x180036954  call    ?IsLocalV4Printer@@YAJPEAXPEA_N@Z; IsLocalV4Printer(void *,bool *)
0x180036959  mov     rcx, [rsp+28h+hPrinter]; hPrinter
0x18003695e  mov     ebx, eax
0x180036960  test    rcx, rcx
0x180036963  jz      short loc_18003696B
0x180036965  call    cs:__imp_ClosePrinter
0x18003696b  mov     rsi, [rsp+28h+arg_10]
0x180036970  mov     eax, ebx
0x180036972  mov     rbx, [rsp+28h+arg_0]
0x180036977  add     rsp, 20h
0x18003697b  pop     rdi
0x18003697c  retn
```
