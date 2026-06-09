# InitializeWinSpoolFunctions

- ea: `0x140006578`
- end: `0x14000668d`
- name: `InitializeWinSpoolFunctions`
- size: `277`
- prototype: `DWORD __fastcall(HMODULE hModule, FARPROC *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006694`

## callees

- `0x140006578`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000667c`
- `KERNEL32!GetLastError` at `0x14000667c`
- `KERNEL32!GetProcAddress` at `0x14000658f`
- `KERNEL32!GetProcAddress` at `0x1400065a2`
- `KERNEL32!GetProcAddress` at `0x1400065b6`
- `KERNEL32!GetProcAddress` at `0x1400065ca`
- `KERNEL32!GetProcAddress` at `0x1400065de`
- `KERNEL32!GetProcAddress` at `0x1400065f0`
- `KERNEL32!GetProcAddress` at `0x140006602`
- `KERNEL32!GetProcAddress` at `0x140006614`
- `KERNEL32!GetProcAddress` at `0x140006626`
- `KERNEL32!GetProcAddress` at `0x140006638`
- `KERNEL32!GetProcAddress` at `0x14000658f`
- `KERNEL32!GetProcAddress` at `0x1400065a2`
- `KERNEL32!GetProcAddress` at `0x1400065b6`
- `KERNEL32!GetProcAddress` at `0x1400065ca`
- `KERNEL32!GetProcAddress` at `0x1400065de`
- `KERNEL32!GetProcAddress` at `0x1400065f0`
- `KERNEL32!GetProcAddress` at `0x140006602`
- `KERNEL32!GetProcAddress` at `0x140006614`
- `KERNEL32!GetProcAddress` at `0x140006626`
- `KERNEL32!GetProcAddress` at `0x140006638`

## string_xrefs

- `0x140006588`: `OpenPrinterW`

## pseudocode

```c
DWORD __fastcall InitializeWinSpoolFunctions(HMODULE hModule, FARPROC *a2)
{
  FARPROC ProcAddress; // rax

  *a2 = GetProcAddress(hModule, "OpenPrinterW");
  a2[1] = GetProcAddress(hModule, "ClosePrinter");
  a2[4] = GetProcAddress(hModule, "DocumentPropertiesW");
  a2[2] = GetProcAddress(hModule, "SpoolerDevQueryPrintW");
  a2[3] = GetProcAddress(hModule, "SpoolerPrinterEvent");
  a2[5] = GetProcAddress(hModule, (LPCSTR)0xD4);
  a2[6] = GetProcAddress(hModule, (LPCSTR)0xD5);
  a2[7] = GetProcAddress(hModule, (LPCSTR)0xD6);
  a2[8] = GetProcAddress(hModule, (LPCSTR)0xD7);
  ProcAddress = GetProcAddress(hModule, (LPCSTR)0xFB);
  a2[9] = ProcAddress;
  if ( *a2 && a2[1] && a2[4] && a2[3] && a2[2] && a2[5] && a2[6] && a2[7] && ProcAddress )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x140006578  mov     [rsp+arg_0], rbx
0x14000657d  push    rdi
0x14000657e  sub     rsp, 20h
0x140006582  mov     rdi, rdx
0x140006585  mov     rbx, rcx
0x140006588  lea     rdx, aOpenprinterw; "OpenPrinterW"
0x14000658f  call    cs:__imp_GetProcAddress
0x140006595  lea     rdx, aCloseprinter; "ClosePrinter"
0x14000659c  mov     rcx, rbx; hModule
0x14000659f  mov     [rdi], rax
0x1400065a2  call    cs:__imp_GetProcAddress
0x1400065a8  lea     rdx, aDocumentproper; "DocumentPropertiesW"
0x1400065af  mov     rcx, rbx; hModule
0x1400065b2  mov     [rdi+8], rax
0x1400065b6  call    cs:__imp_GetProcAddress
0x1400065bc  lea     rdx, aSpoolerdevquer; "SpoolerDevQueryPrintW"
0x1400065c3  mov     rcx, rbx; hModule
0x1400065c6  mov     [rdi+20h], rax
0x1400065ca  call    cs:__imp_GetProcAddress
0x1400065d0  lea     rdx, aSpoolerprinter; "SpoolerPrinterEvent"
0x1400065d7  mov     rcx, rbx; hModule
0x1400065da  mov     [rdi+10h], rax
0x1400065de  call    cs:__imp_GetProcAddress
0x1400065e4  mov     edx, 0D4h; lpProcName
0x1400065e9  mov     rcx, rbx; hModule
0x1400065ec  mov     [rdi+18h], rax
0x1400065f0  call    cs:__imp_GetProcAddress
0x1400065f6  mov     edx, 0D5h; lpProcName
0x1400065fb  mov     rcx, rbx; hModule
0x1400065fe  mov     [rdi+28h], rax
0x140006602  call    cs:__imp_GetProcAddress
0x140006608  mov     edx, 0D6h; lpProcName
0x14000660d  mov     rcx, rbx; hModule
0x140006610  mov     [rdi+30h], rax
0x140006614  call    cs:__imp_GetProcAddress
0x14000661a  mov     edx, 0D7h; lpProcName
0x14000661f  mov     rcx, rbx; hModule
0x140006622  mov     [rdi+38h], rax
0x140006626  call    cs:__imp_GetProcAddress
0x14000662c  mov     edx, 0FBh; lpProcName
0x140006631  mov     rcx, rbx; hModule
0x140006634  mov     [rdi+40h], rax
0x140006638  call    cs:__imp_GetProcAddress
0x14000663e  xor     ecx, ecx
0x140006640  mov     [rdi+48h], rax
0x140006644  cmp     [rdi], rcx
0x140006647  jz      short loc_14000667C
0x140006649  cmp     [rdi+8], rcx
0x14000664d  jz      short loc_14000667C
0x14000664f  cmp     [rdi+20h], rcx
0x140006653  jz      short loc_14000667C
0x140006655  cmp     [rdi+18h], rcx
0x140006659  jz      short loc_14000667C
0x14000665b  cmp     [rdi+10h], rcx
0x14000665f  jz      short loc_14000667C
0x140006661  cmp     [rdi+28h], rcx
0x140006665  jz      short loc_14000667C
0x140006667  cmp     [rdi+30h], rcx
0x14000666b  jz      short loc_14000667C
0x14000666d  cmp     [rdi+38h], rcx
0x140006671  jz      short loc_14000667C
0x140006673  test    rax, rax
0x140006676  jz      short loc_14000667C
0x140006678  xor     eax, eax
0x14000667a  jmp     short loc_140006682
0x14000667c  call    cs:__imp_GetLastError
0x140006682  mov     rbx, [rsp+28h+arg_0]
0x140006687  add     rsp, 20h
0x14000668b  pop     rdi
0x14000668c  retn
```
