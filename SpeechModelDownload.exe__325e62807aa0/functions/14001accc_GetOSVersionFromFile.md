# GetOSVersionFromFile

- ea: `0x14001accc`
- end: `0x14001aeb8`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x14001aec0`
- `0x14001b304`

## callees

- `0x140002600`
- `0x140008dd4`
- `0x14001accc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001add9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001add9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001adbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001adbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ae86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001ae86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001ad30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001ad77`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001ad30`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001ad77`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001ad65`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001ad65`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x14001adab`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x14001adab`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x14001adfe`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x14001adfe`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14001ae23`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x14001ae23`

## string_xrefs

- `0x14001ad43`: `\kernel32.dll`
- `0x14001ad87`: `\ntdll.dll`

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
0x14001accc  push    rbp
0x14001acce  push    rbx
0x14001accf  push    rsi
0x14001acd0  push    rdi
0x14001acd1  push    r12
0x14001acd3  push    r13
0x14001acd5  push    r14
0x14001acd7  push    r15
0x14001acd9  lea     rbp, [rsp-168h]
0x14001ace1  sub     rsp, 268h
0x14001ace8  mov     rax, cs:__security_cookie
0x14001acef  xor     rax, rsp
0x14001acf2  mov     [rbp+1A0h+var_50], rax
0x14001acf9  mov     rax, [rbp+1A0h+arg_20]
0x14001ad00  mov     r13, rcx
0x14001ad03  mov     [rsp+2A0h+var_270], rdx
0x14001ad08  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x14001ad0d  mov     edi, 104h
0x14001ad12  mov     [rsp+2A0h+var_268], rax
0x14001ad17  mov     edx, edi; uSize
0x14001ad19  mov     [rsp+2A0h+lpBuffer], 0
0x14001ad22  mov     r12, r9
0x14001ad25  mov     [rsp+2A0h+puLen], 0
0x14001ad2d  mov     r15, r8
0x14001ad30  call    cs:__imp_GetSystemDirectoryW
0x14001ad36  dec     eax
0x14001ad38  lea     esi, [rdi-2]
0x14001ad3b  cmp     eax, esi
0x14001ad3d  ja      loc_14001AE8E
0x14001ad43  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x14001ad4a  mov     edx, edi; unsigned __int64
0x14001ad4c  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x14001ad51  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001ad56  mov     ebx, eax
0x14001ad58  test    eax, eax
0x14001ad5a  js      loc_14001AE93
0x14001ad60  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x14001ad65  call    cs:__imp_GetFileAttributesW
0x14001ad6b  cmp     eax, 0FFFFFFFFh
0x14001ad6e  jnz     short loc_14001ADA4
0x14001ad70  mov     edx, edi; uSize
0x14001ad72  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x14001ad77  call    cs:__imp_GetSystemDirectoryW
0x14001ad7d  dec     eax
0x14001ad7f  cmp     eax, esi
0x14001ad81  ja      loc_14001AE8E
0x14001ad87  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x14001ad8e  mov     edx, edi; unsigned __int64
0x14001ad90  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x14001ad95  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001ad9a  mov     ebx, eax
0x14001ad9c  test    eax, eax
0x14001ad9e  js      loc_14001AE93
0x14001ada4  xor     edx, edx; lpdwHandle
0x14001ada6  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x14001adab  call    cs:__imp_GetFileVersionInfoSizeW
0x14001adb1  mov     r14d, eax
0x14001adb4  test    eax, eax
0x14001adb6  jz      loc_14001AE8E
0x14001adbc  call    cs:__imp_GetProcessHeap
0x14001adc2  mov     rsi, rax
0x14001adc5  test    rax, rax
0x14001adc8  jz      loc_14001AE8E
0x14001adce  mov     r8d, r14d; dwBytes
0x14001add1  mov     edx, 8; dwFlags
0x14001add6  mov     rcx, rax; hHeap
0x14001add9  call    cs:__imp_HeapAlloc
0x14001addf  mov     rdi, rax
0x14001ade2  test    rax, rax
0x14001ade5  jnz     short loc_14001ADF1
0x14001ade7  mov     ebx, 8007000Eh
0x14001adec  jmp     loc_14001AE93
0x14001adf1  mov     r9, rdi; lpData
0x14001adf4  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x14001adf9  mov     r8d, r14d; dwLen
0x14001adfc  xor     edx, edx; dwHandle
0x14001adfe  call    cs:__imp_GetFileVersionInfoW
0x14001ae04  test    eax, eax
0x14001ae06  jnz     short loc_14001AE0F
0x14001ae08  mov     ebx, 8000FFFFh
0x14001ae0d  jmp     short loc_14001AE7E
0x14001ae0f  lea     r9, [rsp+2A0h+puLen]; puLen
0x14001ae14  mov     rcx, rdi; pBlock
0x14001ae17  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x14001ae1c  lea     rdx, SubBlock; "\\"
0x14001ae23  call    cs:__imp_VerQueryValueW
0x14001ae29  test    eax, eax
0x14001ae2b  jz      short loc_14001AE08
0x14001ae2d  mov     rcx, [rsp+2A0h+lpBuffer]
0x14001ae32  mov     rdx, [rsp+2A0h+var_270]
0x14001ae37  movzx   eax, word ptr [rcx+0Ah]
0x14001ae3b  mov     [r13+0], eax
0x14001ae3f  movzx   eax, word ptr [rcx+8]
0x14001ae43  mov     [rdx], eax
0x14001ae45  movzx   r8d, word ptr [rcx+0Eh]
0x14001ae4a  mov     rax, [rsp+2A0h+var_268]
0x14001ae4f  mov     [rax], r8d
0x14001ae52  cmp     r8d, 23F0h
0x14001ae59  jnb     short loc_14001AE70
0x14001ae5b  mov     eax, 0CCCCCCCDh
0x14001ae60  mul     r8d
0x14001ae63  shr     edx, 3
0x14001ae66  lea     eax, [rdx+rdx*4]
0x14001ae69  add     eax, eax
0x14001ae6b  sub     r8d, eax
0x14001ae6e  jmp     short loc_14001AE73
0x14001ae70  xor     r8d, r8d
0x14001ae73  mov     [r15], r8d
0x14001ae76  mov     dword ptr [r12], 0
0x14001ae7e  mov     r8, rdi; lpMem
0x14001ae81  xor     edx, edx; dwFlags
0x14001ae83  mov     rcx, rsi; hHeap
0x14001ae86  call    cs:__imp_HeapFree
0x14001ae8c  jmp     short loc_14001AE93
0x14001ae8e  mov     ebx, 8000FFFFh
0x14001ae93  mov     eax, ebx
0x14001ae95  mov     rcx, [rbp+1A0h+var_50]
0x14001ae9c  xor     rcx, rsp; StackCookie
0x14001ae9f  call    __security_check_cookie
0x14001aea4  add     rsp, 268h
0x14001aeab  pop     r15
0x14001aead  pop     r14
0x14001aeaf  pop     r13
0x14001aeb1  pop     r12
0x14001aeb3  pop     rdi
0x14001aeb4  pop     rsi
0x14001aeb5  pop     rbx
0x14001aeb6  pop     rbp
0x14001aeb7  retn
```
