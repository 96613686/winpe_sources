# OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)

- ea: `0x180035c34`
- end: `0x180035d16`
- name: `?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z`
- size: `226`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, void *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800368b8`

## callees

- `0x180033bc8`
- `0x180035c34`
- `0x18005d010`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180035cdc`
- `WINSPOOL!OpenPrinterW` at `0x180035cdc`
- `KERNEL32!FreeLibrary` at `0x180035cc4`
- `KERNEL32!FreeLibrary` at `0x180035cc4`
- `KERNEL32!GetProcAddress` at `0x180035c88`
- `KERNEL32!GetProcAddress` at `0x180035c88`
- `KERNEL32!GetLastError` at `0x180035cee`
- `KERNEL32!GetLastError` at `0x180035cee`

## pseudocode

```c
__int64 __fastcall OpenPrinterIfNoCacheHandle(LPWSTR pPrinterName, void *a2, void **a3, void **a4)
{
  int v8; // ebx
  FARPROC ProcAddress; // rax
  char v10; // di
  signed int LastError; // eax
  int v13; // [rsp+58h] [rbp+10h] BYREF
  HMODULE hModule; // [rsp+60h] [rbp+18h] BYREF

  *a3 = a2;
  *a4 = 0;
  hModule = 0;
  v8 = LoadLibraryFromSystemDirectory(L"winspool.drv", &hModule);
  if ( v8 >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, (LPCSTR)0x152);
    if ( ProcAddress )
    {
      v13 = 0;
      v10 = 0;
      v8 = ((__int64 (__fastcall *)(void *, int *))ProcAddress)(a2, &v13);
      if ( v8 >= 0 )
        v10 = v13 & 1;
    }
    else
    {
      v10 = 1;
    }
    FreeLibrary(hModule);
    if ( v8 >= 0 && v10 )
    {
      if ( OpenPrinterW(pPrinterName, a4, 0) )
      {
        *a3 = *a4;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180035c34  mov     [rsp+arg_0], rbx
0x180035c39  push    rbp
0x180035c3a  push    rsi
0x180035c3b  push    rdi
0x180035c3c  push    r14
0x180035c3e  push    r15
0x180035c40  sub     rsp, 20h
0x180035c44  mov     rbp, rdx
0x180035c47  mov     [r8], rdx
0x180035c4a  mov     r15, rcx
0x180035c4d  mov     qword ptr [r9], 0
0x180035c54  lea     rdx, [rsp+48h+hModule]
0x180035c59  mov     [rsp+48h+hModule], 0
0x180035c62  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x180035c69  mov     rsi, r9
0x180035c6c  mov     r14, r8
0x180035c6f  call    LoadLibraryFromSystemDirectory
0x180035c74  mov     ebx, eax
0x180035c76  test    eax, eax
0x180035c78  js      loc_180035D03
0x180035c7e  mov     rcx, [rsp+48h+hModule]; hModule
0x180035c83  mov     edx, 152h; lpProcName
0x180035c88  call    cs:__imp_GetProcAddress
0x180035c8e  test    rax, rax
0x180035c91  jz      short loc_180035CBC
0x180035c93  lea     rdx, [rsp+48h+arg_8]
0x180035c98  mov     [rsp+48h+arg_8], 0
0x180035ca0  mov     rcx, rbp
0x180035ca3  xor     dil, dil
0x180035ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cab  mov     ebx, eax
0x180035cad  test    eax, eax
0x180035caf  js      short loc_180035CBF
0x180035cb1  mov     dil, byte ptr [rsp+48h+arg_8]
0x180035cb6  and     dil, 1
0x180035cba  jmp     short loc_180035CBF
0x180035cbc  mov     dil, 1
0x180035cbf  mov     rcx, [rsp+48h+hModule]; hLibModule
0x180035cc4  call    cs:__imp_FreeLibrary
0x180035cca  test    ebx, ebx
0x180035ccc  js      short loc_180035D03
0x180035cce  test    dil, dil
0x180035cd1  jz      short loc_180035D03
0x180035cd3  xor     r8d, r8d; pDefault
0x180035cd6  mov     rdx, rsi; phPrinter
0x180035cd9  mov     rcx, r15; pPrinterName
0x180035cdc  call    cs:__imp_OpenPrinterW
0x180035ce2  test    eax, eax
0x180035ce4  jz      short loc_180035CEE
0x180035ce6  mov     rax, [rsi]
0x180035ce9  mov     [r14], rax
0x180035cec  jmp     short loc_180035D03
0x180035cee  call    cs:__imp_GetLastError
0x180035cf4  mov     ebx, eax
0x180035cf6  test    eax, eax
0x180035cf8  jle     short loc_180035D03
0x180035cfa  movzx   ebx, ax
0x180035cfd  or      ebx, 80070000h
0x180035d03  mov     eax, ebx
0x180035d05  mov     rbx, [rsp+48h+arg_0]
0x180035d0a  add     rsp, 20h
0x180035d0e  pop     r15
0x180035d10  pop     r14
0x180035d12  pop     rdi
0x180035d13  pop     rsi
0x180035d14  pop     rbp
0x180035d15  retn
```
