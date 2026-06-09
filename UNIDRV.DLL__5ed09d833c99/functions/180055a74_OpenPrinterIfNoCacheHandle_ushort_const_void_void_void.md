# OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)

- ea: `0x180055a74`
- end: `0x180055b68`
- name: `?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z`
- size: `244`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, void *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180045c70`

## callees

- `0x1800519c4`
- `0x180055a74`
- `0x180077010`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x180055b21`
- `WINSPOOL!OpenPrinterW` at `0x180055b21`
- `KERNEL32!GetLastError` at `0x180055b39`
- `KERNEL32!GetLastError` at `0x180055b39`
- `KERNEL32!FreeLibrary` at `0x180055b03`
- `KERNEL32!FreeLibrary` at `0x180055b03`
- `KERNEL32!GetProcAddress` at `0x180055ac1`
- `KERNEL32!GetProcAddress` at `0x180055ac1`

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
0x180055a74  mov     [rsp+arg_0], rbx
0x180055a79  push    rbp
0x180055a7a  push    rsi
0x180055a7b  push    rdi
0x180055a7c  push    r14
0x180055a7e  push    r15
0x180055a80  sub     rsp, 20h
0x180055a84  mov     rbp, rdx
0x180055a87  mov     [r8], rdx
0x180055a8a  lea     rdx, [rsp+48h+hModule]
0x180055a8f  mov     qword ptr [r9], 0
0x180055a96  mov     rsi, r9
0x180055a99  mov     [rsp+48h+hModule], 0
0x180055aa2  mov     r14, r8
0x180055aa5  mov     r15, rcx
0x180055aa8  call    LoadLibraryFromSystemDirectory
0x180055aad  mov     ebx, eax
0x180055aaf  test    eax, eax
0x180055ab1  js      loc_180055B54
0x180055ab7  mov     rcx, [rsp+48h+hModule]; hModule
0x180055abc  mov     edx, 152h; lpProcName
0x180055ac1  call    cs:__imp_GetProcAddress
0x180055ac8  nop     dword ptr [rax+rax+00h]
0x180055acd  test    rax, rax
0x180055ad0  jz      short loc_180055AFB
0x180055ad2  lea     rdx, [rsp+48h+arg_8]
0x180055ad7  mov     [rsp+48h+arg_8], 0
0x180055adf  mov     rcx, rbp
0x180055ae2  xor     dil, dil
0x180055ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055aea  mov     ebx, eax
0x180055aec  test    eax, eax
0x180055aee  js      short loc_180055AFE
0x180055af0  mov     dil, byte ptr [rsp+48h+arg_8]
0x180055af5  and     dil, 1
0x180055af9  jmp     short loc_180055AFE
0x180055afb  mov     dil, 1
0x180055afe  mov     rcx, [rsp+48h+hModule]; hLibModule
0x180055b03  call    cs:__imp_FreeLibrary
0x180055b0a  nop     dword ptr [rax+rax+00h]
0x180055b0f  test    ebx, ebx
0x180055b11  js      short loc_180055B54
0x180055b13  test    dil, dil
0x180055b16  jz      short loc_180055B54
0x180055b18  xor     r8d, r8d; pDefault
0x180055b1b  mov     rdx, rsi; phPrinter
0x180055b1e  mov     rcx, r15; pPrinterName
0x180055b21  call    cs:__imp_OpenPrinterW
0x180055b28  nop     dword ptr [rax+rax+00h]
0x180055b2d  test    eax, eax
0x180055b2f  jz      short loc_180055B39
0x180055b31  mov     rax, [rsi]
0x180055b34  mov     [r14], rax
0x180055b37  jmp     short loc_180055B54
0x180055b39  call    cs:__imp_GetLastError
0x180055b40  nop     dword ptr [rax+rax+00h]
0x180055b45  mov     ebx, eax
0x180055b47  test    eax, eax
0x180055b49  jle     short loc_180055B54
0x180055b4b  movzx   ebx, ax
0x180055b4e  or      ebx, 80070000h
0x180055b54  mov     eax, ebx
0x180055b56  mov     rbx, [rsp+48h+arg_0]
0x180055b5b  add     rsp, 20h
0x180055b5f  pop     r15
0x180055b61  pop     r14
0x180055b63  pop     rdi
0x180055b64  pop     rsi
0x180055b65  pop     rbp
0x180055b66  retn
```
