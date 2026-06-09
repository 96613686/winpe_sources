# OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)

- ea: `0x180053fac`
- end: `0x180054087`
- name: `?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z`
- size: `219`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, void *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180044998`

## callees

- `0x180050254`
- `0x180053fac`
- `0x180075010`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x18005404d`
- `WINSPOOL!OpenPrinterW` at `0x18005404d`
- `KERNEL32!GetLastError` at `0x18005405f`
- `KERNEL32!GetLastError` at `0x18005405f`
- `KERNEL32!FreeLibrary` at `0x180054035`
- `KERNEL32!FreeLibrary` at `0x180054035`
- `KERNEL32!GetProcAddress` at `0x180053ff9`
- `KERNEL32!GetProcAddress` at `0x180053ff9`

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
  v8 = LoadLibraryFromSystemDirectory((__int64)pPrinterName, &hModule);
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
0x180053fac  mov     [rsp+arg_0], rbx
0x180053fb1  push    rbp
0x180053fb2  push    rsi
0x180053fb3  push    rdi
0x180053fb4  push    r14
0x180053fb6  push    r15
0x180053fb8  sub     rsp, 20h
0x180053fbc  mov     rbp, rdx
0x180053fbf  mov     [r8], rdx
0x180053fc2  lea     rdx, [rsp+48h+hModule]
0x180053fc7  mov     qword ptr [r9], 0
0x180053fce  mov     rsi, r9
0x180053fd1  mov     [rsp+48h+hModule], 0
0x180053fda  mov     r14, r8
0x180053fdd  mov     r15, rcx
0x180053fe0  call    LoadLibraryFromSystemDirectory
0x180053fe5  mov     ebx, eax
0x180053fe7  test    eax, eax
0x180053fe9  js      loc_180054074
0x180053fef  mov     rcx, [rsp+48h+hModule]; hModule
0x180053ff4  mov     edx, 152h; lpProcName
0x180053ff9  call    cs:__imp_GetProcAddress
0x180053fff  test    rax, rax
0x180054002  jz      short loc_18005402D
0x180054004  lea     rdx, [rsp+48h+arg_8]
0x180054009  mov     [rsp+48h+arg_8], 0
0x180054011  mov     rcx, rbp
0x180054014  xor     dil, dil
0x180054017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005401c  mov     ebx, eax
0x18005401e  test    eax, eax
0x180054020  js      short loc_180054030
0x180054022  mov     dil, byte ptr [rsp+48h+arg_8]
0x180054027  and     dil, 1
0x18005402b  jmp     short loc_180054030
0x18005402d  mov     dil, 1
0x180054030  mov     rcx, [rsp+48h+hModule]; hLibModule
0x180054035  call    cs:__imp_FreeLibrary
0x18005403b  test    ebx, ebx
0x18005403d  js      short loc_180054074
0x18005403f  test    dil, dil
0x180054042  jz      short loc_180054074
0x180054044  xor     r8d, r8d; pDefault
0x180054047  mov     rdx, rsi; phPrinter
0x18005404a  mov     rcx, r15; pPrinterName
0x18005404d  call    cs:__imp_OpenPrinterW
0x180054053  test    eax, eax
0x180054055  jz      short loc_18005405F
0x180054057  mov     rax, [rsi]
0x18005405a  mov     [r14], rax
0x18005405d  jmp     short loc_180054074
0x18005405f  call    cs:__imp_GetLastError
0x180054065  mov     ebx, eax
0x180054067  test    eax, eax
0x180054069  jle     short loc_180054074
0x18005406b  movzx   ebx, ax
0x18005406e  or      ebx, 80070000h
0x180054074  mov     eax, ebx
0x180054076  mov     rbx, [rsp+48h+arg_0]
0x18005407b  add     rsp, 20h
0x18005407f  pop     r15
0x180054081  pop     r14
0x180054083  pop     rdi
0x180054084  pop     rsi
0x180054085  pop     rbp
0x180054086  retn
```
