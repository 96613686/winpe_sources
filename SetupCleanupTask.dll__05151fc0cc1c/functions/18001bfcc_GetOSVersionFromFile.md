# GetOSVersionFromFile

- ea: `0x18001bfcc`
- end: `0x18001c1b8`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180023b14`

## callees

- `0x18001bfcc`
- `0x180022e70`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c030`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c077`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c030`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001c077`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001c065`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001c065`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c0d9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c0d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c0bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c0bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c186`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c186`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001c0ab`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001c0ab`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001c0fe`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001c0fe`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001c123`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001c123`

## string_xrefs

- `0x18001c043`: `\kernel32.dll`
- `0x18001c087`: `\ntdll.dll`

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
0x18001bfcc  push    rbp
0x18001bfce  push    rbx
0x18001bfcf  push    rsi
0x18001bfd0  push    rdi
0x18001bfd1  push    r12
0x18001bfd3  push    r13
0x18001bfd5  push    r14
0x18001bfd7  push    r15
0x18001bfd9  lea     rbp, [rsp-168h]
0x18001bfe1  sub     rsp, 268h
0x18001bfe8  mov     rax, cs:__security_cookie
0x18001bfef  xor     rax, rsp
0x18001bff2  mov     [rbp+1A0h+var_50], rax
0x18001bff9  mov     rax, [rbp+1A0h+arg_20]
0x18001c000  mov     r13, rcx
0x18001c003  mov     [rsp+2A0h+var_270], rdx
0x18001c008  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18001c00d  mov     edi, 104h
0x18001c012  mov     [rsp+2A0h+var_268], rax
0x18001c017  mov     edx, edi; uSize
0x18001c019  mov     [rsp+2A0h+lpBuffer], 0
0x18001c022  mov     r12, r9
0x18001c025  mov     [rsp+2A0h+puLen], 0
0x18001c02d  mov     r15, r8
0x18001c030  call    cs:__imp_GetSystemDirectoryW
0x18001c036  dec     eax
0x18001c038  lea     esi, [rdi-2]
0x18001c03b  cmp     eax, esi
0x18001c03d  ja      loc_18001C18E
0x18001c043  lea     r8, aKernel32Dll_0; "\\kernel32.dll"
0x18001c04a  mov     edx, edi; unsigned __int64
0x18001c04c  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001c051  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c056  mov     ebx, eax
0x18001c058  test    eax, eax
0x18001c05a  js      loc_18001C193
0x18001c060  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x18001c065  call    cs:__imp_GetFileAttributesW
0x18001c06b  cmp     eax, 0FFFFFFFFh
0x18001c06e  jnz     short loc_18001C0A4
0x18001c070  mov     edx, edi; uSize
0x18001c072  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18001c077  call    cs:__imp_GetSystemDirectoryW
0x18001c07d  dec     eax
0x18001c07f  cmp     eax, esi
0x18001c081  ja      loc_18001C18E
0x18001c087  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x18001c08e  mov     edx, edi; unsigned __int64
0x18001c090  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001c095  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c09a  mov     ebx, eax
0x18001c09c  test    eax, eax
0x18001c09e  js      loc_18001C193
0x18001c0a4  xor     edx, edx; lpdwHandle
0x18001c0a6  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18001c0ab  call    cs:__imp_GetFileVersionInfoSizeW
0x18001c0b1  mov     r14d, eax
0x18001c0b4  test    eax, eax
0x18001c0b6  jz      loc_18001C18E
0x18001c0bc  call    cs:__imp_GetProcessHeap
0x18001c0c2  mov     rsi, rax
0x18001c0c5  test    rax, rax
0x18001c0c8  jz      loc_18001C18E
0x18001c0ce  mov     r8d, r14d; dwBytes
0x18001c0d1  mov     edx, 8; dwFlags
0x18001c0d6  mov     rcx, rax; hHeap
0x18001c0d9  call    cs:__imp_HeapAlloc
0x18001c0df  mov     rdi, rax
0x18001c0e2  test    rax, rax
0x18001c0e5  jnz     short loc_18001C0F1
0x18001c0e7  mov     ebx, 8007000Eh
0x18001c0ec  jmp     loc_18001C193
0x18001c0f1  mov     r9, rdi; lpData
0x18001c0f4  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18001c0f9  mov     r8d, r14d; dwLen
0x18001c0fc  xor     edx, edx; dwHandle
0x18001c0fe  call    cs:__imp_GetFileVersionInfoW
0x18001c104  test    eax, eax
0x18001c106  jnz     short loc_18001C10F
0x18001c108  mov     ebx, 8000FFFFh
0x18001c10d  jmp     short loc_18001C17E
0x18001c10f  lea     r9, [rsp+2A0h+puLen]; puLen
0x18001c114  mov     rcx, rdi; pBlock
0x18001c117  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x18001c11c  lea     rdx, pszSrc; "\\"
0x18001c123  call    cs:__imp_VerQueryValueW
0x18001c129  test    eax, eax
0x18001c12b  jz      short loc_18001C108
0x18001c12d  mov     rcx, [rsp+2A0h+lpBuffer]
0x18001c132  mov     rdx, [rsp+2A0h+var_270]
0x18001c137  movzx   eax, word ptr [rcx+0Ah]
0x18001c13b  mov     [r13+0], eax
0x18001c13f  movzx   eax, word ptr [rcx+8]
0x18001c143  mov     [rdx], eax
0x18001c145  movzx   r8d, word ptr [rcx+0Eh]
0x18001c14a  mov     rax, [rsp+2A0h+var_268]
0x18001c14f  mov     [rax], r8d
0x18001c152  cmp     r8d, 23F0h
0x18001c159  jnb     short loc_18001C170
0x18001c15b  mov     eax, 0CCCCCCCDh
0x18001c160  mul     r8d
0x18001c163  shr     edx, 3
0x18001c166  lea     eax, [rdx+rdx*4]
0x18001c169  add     eax, eax
0x18001c16b  sub     r8d, eax
0x18001c16e  jmp     short loc_18001C173
0x18001c170  xor     r8d, r8d
0x18001c173  mov     [r15], r8d
0x18001c176  mov     dword ptr [r12], 0
0x18001c17e  mov     r8, rdi; lpMem
0x18001c181  xor     edx, edx; dwFlags
0x18001c183  mov     rcx, rsi; hHeap
0x18001c186  call    cs:__imp_HeapFree
0x18001c18c  jmp     short loc_18001C193
0x18001c18e  mov     ebx, 8000FFFFh
0x18001c193  mov     eax, ebx
0x18001c195  mov     rcx, [rbp+1A0h+var_50]
0x18001c19c  xor     rcx, rsp; StackCookie
0x18001c19f  call    __security_check_cookie
0x18001c1a4  add     rsp, 268h
0x18001c1ab  pop     r15
0x18001c1ad  pop     r14
0x18001c1af  pop     r13
0x18001c1b1  pop     r12
0x18001c1b3  pop     rdi
0x18001c1b4  pop     rsi
0x18001c1b5  pop     rbx
0x18001c1b6  pop     rbp
0x18001c1b7  retn
```
