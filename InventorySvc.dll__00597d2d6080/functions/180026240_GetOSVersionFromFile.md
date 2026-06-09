# GetOSVersionFromFile

- ea: `0x180026240`
- end: `0x180026428`
- name: `GetOSVersionFromFile`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18002d4d4`

## callees

- `0x180002bf0`
- `0x18000f698`
- `0x180026240`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002632c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002632c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026349`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180026349`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800263f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800263f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800262a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800262e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800262a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800262e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800262d7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800262d7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180026393`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180026393`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18002631b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18002631b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18002636e`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18002636e`

## string_xrefs

- `0x1800262b7`: `\kernel32.dll`
- `0x1800262f9`: `\ntdll.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  unsigned __int64 v8; // rdx
  int v9; // ebx
  unsigned __int64 v10; // rdx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v13; // rsi
  void *v14; // rax
  void *v15; // rdi
  unsigned __int16 *v16; // rcx
  _DWORD *v17; // rdx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v23; // [rsp+30h] [rbp-D0h]
  unsigned int *v24; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v23 = a2;
  v24 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v9 = StringCchCatW(Buffer, v8, L"\\kernel32.dll");
  if ( v9 < 0 )
    return (unsigned int)v9;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147418113;
    v9 = StringCchCatW(Buffer, v10, L"\\ntdll.dll");
    if ( v9 < 0 )
      return (unsigned int)v9;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
  if ( !FileVersionInfoSizeW )
    return (unsigned int)-2147418113;
  ProcessHeap = GetProcessHeap();
  v13 = ProcessHeap;
  if ( !ProcessHeap )
    return (unsigned int)-2147418113;
  v14 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
  v15 = v14;
  if ( v14 )
  {
    if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v14) && VerQueryValueW(v15, L"\\", &lpBuffer, &puLen) )
    {
      v16 = (unsigned __int16 *)lpBuffer;
      v17 = v23;
      *a1 = *((unsigned __int16 *)lpBuffer + 5);
      *v17 = v16[4];
      v18 = v16[7];
      *v24 = v18;
      if ( v18 >= 0x23F0 )
        v19 = 0;
      else
        v19 = v18 % 0xA;
      *a3 = v19;
      *a4 = 0;
    }
    else
    {
      v9 = -2147418113;
    }
    HeapFree(v13, 0, v15);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026240  push    rbp
0x180026242  push    rbx
0x180026243  push    rsi
0x180026244  push    rdi
0x180026245  push    r12
0x180026247  push    r13
0x180026249  push    r14
0x18002624b  push    r15
0x18002624d  lea     rbp, [rsp-168h]
0x180026255  sub     rsp, 268h
0x18002625c  mov     rax, cs:__security_cookie
0x180026263  xor     rax, rsp
0x180026266  mov     [rbp+1A0h+var_50], rax
0x18002626d  mov     rax, [rbp+1A0h+arg_20]
0x180026274  mov     r13, rcx
0x180026277  mov     [rsp+2A0h+var_270], rdx
0x18002627c  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180026281  mov     edi, 104h
0x180026286  mov     [rsp+2A0h+var_268], rax
0x18002628b  mov     edx, edi; uSize
0x18002628d  mov     [rsp+2A0h+lpBuffer], 0
0x180026296  mov     r12, r9
0x180026299  mov     [rsp+2A0h+puLen], 0
0x1800262a1  mov     r15, r8
0x1800262a4  call    cs:__imp_GetSystemDirectoryW
0x1800262aa  dec     eax
0x1800262ac  lea     esi, [rdi-2]
0x1800262af  cmp     eax, esi
0x1800262b1  ja      loc_1800263FE
0x1800262b7  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x1800262be  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x1800262c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800262c8  mov     ebx, eax
0x1800262ca  test    eax, eax
0x1800262cc  js      loc_180026403
0x1800262d2  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x1800262d7  call    cs:__imp_GetFileAttributesW
0x1800262dd  cmp     eax, 0FFFFFFFFh
0x1800262e0  jnz     short loc_180026314
0x1800262e2  mov     edx, edi; uSize
0x1800262e4  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800262e9  call    cs:__imp_GetSystemDirectoryW
0x1800262ef  dec     eax
0x1800262f1  cmp     eax, esi
0x1800262f3  ja      loc_1800263FE
0x1800262f9  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x180026300  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180026305  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002630a  mov     ebx, eax
0x18002630c  test    eax, eax
0x18002630e  js      loc_180026403
0x180026314  xor     edx, edx; lpdwHandle
0x180026316  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18002631b  call    cs:__imp_GetFileVersionInfoSizeW
0x180026321  mov     r14d, eax
0x180026324  test    eax, eax
0x180026326  jz      loc_1800263FE
0x18002632c  call    cs:__imp_GetProcessHeap
0x180026332  mov     rsi, rax
0x180026335  test    rax, rax
0x180026338  jz      loc_1800263FE
0x18002633e  mov     r8d, r14d; dwBytes
0x180026341  mov     edx, 8; dwFlags
0x180026346  mov     rcx, rax; hHeap
0x180026349  call    cs:__imp_HeapAlloc
0x18002634f  mov     rdi, rax
0x180026352  test    rax, rax
0x180026355  jnz     short loc_180026361
0x180026357  mov     ebx, 8007000Eh
0x18002635c  jmp     loc_180026403
0x180026361  mov     r9, rdi; lpData
0x180026364  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180026369  mov     r8d, r14d; dwLen
0x18002636c  xor     edx, edx; dwHandle
0x18002636e  call    cs:__imp_GetFileVersionInfoW
0x180026374  test    eax, eax
0x180026376  jnz     short loc_18002637F
0x180026378  mov     ebx, 8000FFFFh
0x18002637d  jmp     short loc_1800263EE
0x18002637f  lea     r9, [rsp+2A0h+puLen]; puLen
0x180026384  mov     rcx, rdi; pBlock
0x180026387  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x18002638c  lea     rdx, SubBlock; "\\"
0x180026393  call    cs:__imp_VerQueryValueW
0x180026399  test    eax, eax
0x18002639b  jz      short loc_180026378
0x18002639d  mov     rcx, [rsp+2A0h+lpBuffer]
0x1800263a2  mov     rdx, [rsp+2A0h+var_270]
0x1800263a7  movzx   eax, word ptr [rcx+0Ah]
0x1800263ab  mov     [r13+0], eax
0x1800263af  movzx   eax, word ptr [rcx+8]
0x1800263b3  mov     [rdx], eax
0x1800263b5  movzx   r8d, word ptr [rcx+0Eh]
0x1800263ba  mov     rax, [rsp+2A0h+var_268]
0x1800263bf  mov     [rax], r8d
0x1800263c2  cmp     r8d, 23F0h
0x1800263c9  jnb     short loc_1800263E0
0x1800263cb  mov     eax, 0CCCCCCCDh
0x1800263d0  mul     r8d
0x1800263d3  shr     edx, 3
0x1800263d6  lea     eax, [rdx+rdx*4]
0x1800263d9  add     eax, eax
0x1800263db  sub     r8d, eax
0x1800263de  jmp     short loc_1800263E3
0x1800263e0  xor     r8d, r8d
0x1800263e3  mov     [r15], r8d
0x1800263e6  mov     dword ptr [r12], 0
0x1800263ee  mov     r8, rdi; lpMem
0x1800263f1  xor     edx, edx; dwFlags
0x1800263f3  mov     rcx, rsi; hHeap
0x1800263f6  call    cs:__imp_HeapFree
0x1800263fc  jmp     short loc_180026403
0x1800263fe  mov     ebx, 8000FFFFh
0x180026403  mov     eax, ebx
0x180026405  mov     rcx, [rbp+1A0h+var_50]
0x18002640c  xor     rcx, rsp; StackCookie
0x18002640f  call    __security_check_cookie
0x180026414  add     rsp, 268h
0x18002641b  pop     r15
0x18002641d  pop     r14
0x18002641f  pop     r13
0x180026421  pop     r12
0x180026423  pop     rdi
0x180026424  pop     rsi
0x180026425  pop     rbx
0x180026426  pop     rbp
0x180026427  retn
```
