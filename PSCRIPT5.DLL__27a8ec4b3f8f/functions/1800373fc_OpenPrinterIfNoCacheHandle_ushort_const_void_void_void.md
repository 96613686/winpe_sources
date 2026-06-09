# OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)

- ea: `0x1800373fc`
- end: `0x1800374f7`
- name: `?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z`
- size: `251`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, void *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180038118`

## callees

- `0x1800352ac`
- `0x1800373fc`
- `0x18005f010`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x1800374b0`
- `WINSPOOL!OpenPrinterW` at `0x1800374b0`
- `KERNEL32!FreeLibrary` at `0x180037492`
- `KERNEL32!FreeLibrary` at `0x180037492`
- `KERNEL32!GetProcAddress` at `0x180037450`
- `KERNEL32!GetProcAddress` at `0x180037450`
- `KERNEL32!GetLastError` at `0x1800374c8`
- `KERNEL32!GetLastError` at `0x1800374c8`

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
0x1800373fc  mov     [rsp+arg_0], rbx
0x180037401  push    rbp
0x180037402  push    rsi
0x180037403  push    rdi
0x180037404  push    r14
0x180037406  push    r15
0x180037408  sub     rsp, 20h
0x18003740c  mov     rbp, rdx
0x18003740f  mov     [r8], rdx
0x180037412  mov     r15, rcx
0x180037415  mov     qword ptr [r9], 0
0x18003741c  lea     rdx, [rsp+48h+hModule]
0x180037421  mov     [rsp+48h+hModule], 0
0x18003742a  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x180037431  mov     rsi, r9
0x180037434  mov     r14, r8
0x180037437  call    LoadLibraryFromSystemDirectory
0x18003743c  mov     ebx, eax
0x18003743e  test    eax, eax
0x180037440  js      loc_1800374E3
0x180037446  mov     rcx, [rsp+48h+hModule]; hModule
0x18003744b  mov     edx, 152h; lpProcName
0x180037450  call    cs:__imp_GetProcAddress
0x180037457  nop     dword ptr [rax+rax+00h]
0x18003745c  test    rax, rax
0x18003745f  jz      short loc_18003748A
0x180037461  lea     rdx, [rsp+48h+arg_8]
0x180037466  mov     [rsp+48h+arg_8], 0
0x18003746e  mov     rcx, rbp
0x180037471  xor     dil, dil
0x180037474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037479  mov     ebx, eax
0x18003747b  test    eax, eax
0x18003747d  js      short loc_18003748D
0x18003747f  mov     dil, byte ptr [rsp+48h+arg_8]
0x180037484  and     dil, 1
0x180037488  jmp     short loc_18003748D
0x18003748a  mov     dil, 1
0x18003748d  mov     rcx, [rsp+48h+hModule]; hLibModule
0x180037492  call    cs:__imp_FreeLibrary
0x180037499  nop     dword ptr [rax+rax+00h]
0x18003749e  test    ebx, ebx
0x1800374a0  js      short loc_1800374E3
0x1800374a2  test    dil, dil
0x1800374a5  jz      short loc_1800374E3
0x1800374a7  xor     r8d, r8d; pDefault
0x1800374aa  mov     rdx, rsi; phPrinter
0x1800374ad  mov     rcx, r15; pPrinterName
0x1800374b0  call    cs:__imp_OpenPrinterW
0x1800374b7  nop     dword ptr [rax+rax+00h]
0x1800374bc  test    eax, eax
0x1800374be  jz      short loc_1800374C8
0x1800374c0  mov     rax, [rsi]
0x1800374c3  mov     [r14], rax
0x1800374c6  jmp     short loc_1800374E3
0x1800374c8  call    cs:__imp_GetLastError
0x1800374cf  nop     dword ptr [rax+rax+00h]
0x1800374d4  mov     ebx, eax
0x1800374d6  test    eax, eax
0x1800374d8  jle     short loc_1800374E3
0x1800374da  movzx   ebx, ax
0x1800374dd  or      ebx, 80070000h
0x1800374e3  mov     eax, ebx
0x1800374e5  mov     rbx, [rsp+48h+arg_0]
0x1800374ea  add     rsp, 20h
0x1800374ee  pop     r15
0x1800374f0  pop     r14
0x1800374f2  pop     rdi
0x1800374f3  pop     rsi
0x1800374f4  pop     rbp
0x1800374f5  retn
```
