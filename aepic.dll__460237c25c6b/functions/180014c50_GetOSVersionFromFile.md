# GetOSVersionFromFile

- ea: `0x180014c50`
- end: `0x180014e3c`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18001bc68`

## callees

- `0x180005890`
- `0x18000ca3c`
- `0x180014c50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014d5d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014d5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014d40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014d40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014e0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014e0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014cb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014cfb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014cb4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180014cfb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180014da7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180014da7`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180014d82`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180014d82`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180014d2f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180014d2f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014ce9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014ce9`

## string_xrefs

- `0x180014cc7`: `\kernel32.dll`
- `0x180014d0b`: `\ntdll.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  int v8; // ebx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v11; // rsi
  void *v12; // rax
  void *v13; // rdi
  unsigned __int16 *v14; // rcx
  _DWORD *v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v21; // [rsp+30h] [rbp-D0h]
  unsigned int *v22; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v21 = a2;
  v22 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v8 = StringCchCatW(Buffer, 0x104u, L"\\kernel32.dll");
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147418113;
    v8 = StringCchCatW(Buffer, 0x104u, L"\\ntdll.dll");
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
  if ( !FileVersionInfoSizeW )
    return (unsigned int)-2147418113;
  ProcessHeap = GetProcessHeap();
  v11 = ProcessHeap;
  if ( !ProcessHeap )
    return (unsigned int)-2147418113;
  v12 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
  v13 = v12;
  if ( v12 )
  {
    if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v12) && VerQueryValueW(v13, L"\\", &lpBuffer, &puLen) )
    {
      v14 = (unsigned __int16 *)lpBuffer;
      v15 = v21;
      *a1 = *((unsigned __int16 *)lpBuffer + 5);
      *v15 = v14[4];
      v16 = v14[7];
      *v22 = v16;
      if ( v16 >= 0x23F0 )
        v17 = 0;
      else
        v17 = v16 % 0xA;
      *a3 = v17;
      *a4 = 0;
    }
    else
    {
      v8 = -2147418113;
    }
    HeapFree(v11, 0, v13);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014c50  push    rbp
0x180014c52  push    rbx
0x180014c53  push    rsi
0x180014c54  push    rdi
0x180014c55  push    r12
0x180014c57  push    r13
0x180014c59  push    r14
0x180014c5b  push    r15
0x180014c5d  lea     rbp, [rsp-168h]
0x180014c65  sub     rsp, 268h
0x180014c6c  mov     rax, cs:__security_cookie
0x180014c73  xor     rax, rsp
0x180014c76  mov     [rbp+1A0h+var_50], rax
0x180014c7d  mov     rax, [rbp+1A0h+arg_20]
0x180014c84  mov     r13, rcx
0x180014c87  mov     [rsp+2A0h+var_270], rdx
0x180014c8c  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180014c91  mov     edi, 104h
0x180014c96  mov     [rsp+2A0h+var_268], rax
0x180014c9b  mov     edx, edi; uSize
0x180014c9d  mov     [rsp+2A0h+lpBuffer], 0
0x180014ca6  mov     r12, r9
0x180014ca9  mov     [rsp+2A0h+puLen], 0
0x180014cb1  mov     r15, r8
0x180014cb4  call    cs:__imp_GetSystemDirectoryW
0x180014cba  dec     eax
0x180014cbc  lea     esi, [rdi-2]
0x180014cbf  cmp     eax, esi
0x180014cc1  ja      loc_180014E12
0x180014cc7  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x180014cce  mov     edx, edi; unsigned __int64
0x180014cd0  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180014cd5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014cda  mov     ebx, eax
0x180014cdc  test    eax, eax
0x180014cde  js      loc_180014E17
0x180014ce4  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x180014ce9  call    cs:__imp_GetFileAttributesW
0x180014cef  cmp     eax, 0FFFFFFFFh
0x180014cf2  jnz     short loc_180014D28
0x180014cf4  mov     edx, edi; uSize
0x180014cf6  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180014cfb  call    cs:__imp_GetSystemDirectoryW
0x180014d01  dec     eax
0x180014d03  cmp     eax, esi
0x180014d05  ja      loc_180014E12
0x180014d0b  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x180014d12  mov     edx, edi; unsigned __int64
0x180014d14  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180014d19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014d1e  mov     ebx, eax
0x180014d20  test    eax, eax
0x180014d22  js      loc_180014E17
0x180014d28  xor     edx, edx; lpdwHandle
0x180014d2a  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180014d2f  call    cs:__imp_GetFileVersionInfoSizeW
0x180014d35  mov     r14d, eax
0x180014d38  test    eax, eax
0x180014d3a  jz      loc_180014E12
0x180014d40  call    cs:__imp_GetProcessHeap
0x180014d46  mov     rsi, rax
0x180014d49  test    rax, rax
0x180014d4c  jz      loc_180014E12
0x180014d52  mov     r8d, r14d; dwBytes
0x180014d55  mov     edx, 8; dwFlags
0x180014d5a  mov     rcx, rax; hHeap
0x180014d5d  call    cs:__imp_HeapAlloc
0x180014d63  mov     rdi, rax
0x180014d66  test    rax, rax
0x180014d69  jnz     short loc_180014D75
0x180014d6b  mov     ebx, 8007000Eh
0x180014d70  jmp     loc_180014E17
0x180014d75  mov     r9, rdi; lpData
0x180014d78  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180014d7d  mov     r8d, r14d; dwLen
0x180014d80  xor     edx, edx; dwHandle
0x180014d82  call    cs:__imp_GetFileVersionInfoW
0x180014d88  test    eax, eax
0x180014d8a  jnz     short loc_180014D93
0x180014d8c  mov     ebx, 8000FFFFh
0x180014d91  jmp     short loc_180014E02
0x180014d93  lea     r9, [rsp+2A0h+puLen]; puLen
0x180014d98  mov     rcx, rdi; pBlock
0x180014d9b  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x180014da0  lea     rdx, Source; "\\"
0x180014da7  call    cs:__imp_VerQueryValueW
0x180014dad  test    eax, eax
0x180014daf  jz      short loc_180014D8C
0x180014db1  mov     rcx, [rsp+2A0h+lpBuffer]
0x180014db6  mov     rdx, [rsp+2A0h+var_270]
0x180014dbb  movzx   eax, word ptr [rcx+0Ah]
0x180014dbf  mov     [r13+0], eax
0x180014dc3  movzx   eax, word ptr [rcx+8]
0x180014dc7  mov     [rdx], eax
0x180014dc9  movzx   r8d, word ptr [rcx+0Eh]
0x180014dce  mov     rax, [rsp+2A0h+var_268]
0x180014dd3  mov     [rax], r8d
0x180014dd6  cmp     r8d, 23F0h
0x180014ddd  jnb     short loc_180014DF4
0x180014ddf  mov     eax, 0CCCCCCCDh
0x180014de4  mul     r8d
0x180014de7  shr     edx, 3
0x180014dea  lea     eax, [rdx+rdx*4]
0x180014ded  add     eax, eax
0x180014def  sub     r8d, eax
0x180014df2  jmp     short loc_180014DF7
0x180014df4  xor     r8d, r8d
0x180014df7  mov     [r15], r8d
0x180014dfa  mov     dword ptr [r12], 0
0x180014e02  mov     r8, rdi; lpMem
0x180014e05  xor     edx, edx; dwFlags
0x180014e07  mov     rcx, rsi; hHeap
0x180014e0a  call    cs:__imp_HeapFree
0x180014e10  jmp     short loc_180014E17
0x180014e12  mov     ebx, 8000FFFFh
0x180014e17  mov     eax, ebx
0x180014e19  mov     rcx, [rbp+1A0h+var_50]
0x180014e20  xor     rcx, rsp; StackCookie
0x180014e23  call    __security_check_cookie
0x180014e28  add     rsp, 268h
0x180014e2f  pop     r15
0x180014e31  pop     r14
0x180014e33  pop     r13
0x180014e35  pop     r12
0x180014e37  pop     rdi
0x180014e38  pop     rsi
0x180014e39  pop     rbx
0x180014e3a  pop     rbp
0x180014e3b  retn
```
