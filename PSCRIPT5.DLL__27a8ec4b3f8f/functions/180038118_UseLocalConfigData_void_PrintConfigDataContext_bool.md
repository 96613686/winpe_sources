# UseLocalConfigData(void *,PrintConfigDataContext &,bool *)

- ea: `0x180038118`
- end: `0x1800381ed`
- name: `?UseLocalConfigData@@YAJPEAXAEAVPrintConfigDataContext@@PEA_N@Z`
- size: `213`
- prototype: `__int64 __fastcall(void *, struct PrintConfigDataContext *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180035a2c`

## callees

- `0x180036224`
- `0x180037094`
- `0x1800373fc`
- `0x180038118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180038173`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180038173`
- `WINSPOOL!ClosePrinter` at `0x1800381ce`
- `WINSPOOL!ClosePrinter` at `0x1800381ce`

## string_xrefs

- `0x180038140`: `PrintConfig.dll`

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
0x180038118  mov     [rsp+arg_0], rbx
0x18003811d  mov     [rsp+arg_10], rsi
0x180038122  push    rdi
0x180038123  sub     rsp, 20h
0x180038127  mov     rsi, rcx
0x18003812a  mov     rdi, r8
0x18003812d  mov     rcx, [rdx+8]
0x180038131  mov     rbx, rdx
0x180038134  test    rcx, rcx
0x180038137  jnz     short loc_18003813C
0x180038139  mov     rcx, [rdx]
0x18003813c  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180038140  lea     rdx, aPrintconfigDll; "PrintConfig.dll"
0x180038147  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18003814c  test    al, al
0x18003814e  jnz     short loc_18003815A
0x180038150  xor     ebx, ebx
0x180038152  mov     byte ptr [rdi], 1
0x180038155  jmp     loc_1800381DA
0x18003815a  mov     rax, [rbx+10h]
0x18003815e  mov     byte ptr [rdi], 0
0x180038161  mov     rbx, [rax]
0x180038164  test    rbx, rbx
0x180038167  jz      short loc_180038188
0x180038169  lea     rdx, aCsr; "\\\\CSR|"
0x180038170  mov     rcx, rbx; Str
0x180038173  call    cs:__imp_wcsstr
0x18003817a  nop     dword ptr [rax+rax+00h]
0x18003817f  test    rax, rax
0x180038182  jz      short loc_180038188
0x180038184  xor     ebx, ebx
0x180038186  jmp     short loc_1800381DA
0x180038188  lea     r9, [rsp+28h+hPrinter]; void **
0x18003818d  mov     [rsp+28h+arg_8], 0
0x180038196  lea     r8, [rsp+28h+arg_8]; void **
0x18003819b  mov     [rsp+28h+hPrinter], 0
0x1800381a4  mov     rdx, rsi; void *
0x1800381a7  mov     rcx, rbx; pPrinterName
0x1800381aa  call    ?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z; OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)
0x1800381af  mov     ebx, eax
0x1800381b1  test    eax, eax
0x1800381b3  js      short loc_1800381DA
0x1800381b5  mov     rcx, [rsp+28h+arg_8]; hPrinter
0x1800381ba  mov     rdx, rdi; bool *
0x1800381bd  call    ?IsLocalV4Printer@@YAJPEAXPEA_N@Z; IsLocalV4Printer(void *,bool *)
0x1800381c2  mov     rcx, [rsp+28h+hPrinter]; hPrinter
0x1800381c7  mov     ebx, eax
0x1800381c9  test    rcx, rcx
0x1800381cc  jz      short loc_1800381DA
0x1800381ce  call    cs:__imp_ClosePrinter
0x1800381d5  nop     dword ptr [rax+rax+00h]
0x1800381da  mov     rsi, [rsp+28h+arg_10]
0x1800381df  mov     eax, ebx
0x1800381e1  mov     rbx, [rsp+28h+arg_0]
0x1800381e6  add     rsp, 20h
0x1800381ea  pop     rdi
0x1800381eb  retn
```
