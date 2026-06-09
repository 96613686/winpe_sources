# GetOSVersionFromFile

- ea: `0x180041d48`
- end: `0x180041f34`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800476ec`

## callees

- `0x18001c484`
- `0x180041d48`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180041de1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180041de1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041e38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041e38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041e55`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041e55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041f02`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041f02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041dac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041df3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041dac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180041df3`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180041e7a`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180041e7a`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180041e27`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180041e27`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180041e9f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180041e9f`

## string_xrefs

- `0x180041dbf`: `\kernel32.dll`
- `0x180041e03`: `\ntdll.dll`

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
0x180041d48  push    rbp
0x180041d4a  push    rbx
0x180041d4b  push    rsi
0x180041d4c  push    rdi
0x180041d4d  push    r12
0x180041d4f  push    r13
0x180041d51  push    r14
0x180041d53  push    r15
0x180041d55  lea     rbp, [rsp-168h]
0x180041d5d  sub     rsp, 268h
0x180041d64  mov     rax, cs:__security_cookie
0x180041d6b  xor     rax, rsp
0x180041d6e  mov     [rbp+1A0h+var_50], rax
0x180041d75  mov     rax, [rbp+1A0h+arg_20]
0x180041d7c  mov     r13, rcx
0x180041d7f  mov     [rsp+2A0h+var_270], rdx
0x180041d84  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180041d89  mov     edi, 104h
0x180041d8e  mov     [rsp+2A0h+var_268], rax
0x180041d93  mov     edx, edi; uSize
0x180041d95  mov     [rsp+2A0h+lpBuffer], 0
0x180041d9e  mov     r12, r9
0x180041da1  mov     [rsp+2A0h+puLen], 0
0x180041da9  mov     r15, r8
0x180041dac  call    cs:__imp_GetSystemDirectoryW
0x180041db2  dec     eax
0x180041db4  lea     esi, [rdi-2]
0x180041db7  cmp     eax, esi
0x180041db9  ja      loc_180041F0A
0x180041dbf  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x180041dc6  mov     edx, edi; unsigned __int64
0x180041dc8  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180041dcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041dd2  mov     ebx, eax
0x180041dd4  test    eax, eax
0x180041dd6  js      loc_180041F0F
0x180041ddc  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x180041de1  call    cs:__imp_GetFileAttributesW
0x180041de7  cmp     eax, 0FFFFFFFFh
0x180041dea  jnz     short loc_180041E20
0x180041dec  mov     edx, edi; uSize
0x180041dee  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180041df3  call    cs:__imp_GetSystemDirectoryW
0x180041df9  dec     eax
0x180041dfb  cmp     eax, esi
0x180041dfd  ja      loc_180041F0A
0x180041e03  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x180041e0a  mov     edx, edi; unsigned __int64
0x180041e0c  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180041e11  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041e16  mov     ebx, eax
0x180041e18  test    eax, eax
0x180041e1a  js      loc_180041F0F
0x180041e20  xor     edx, edx; lpdwHandle
0x180041e22  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180041e27  call    cs:__imp_GetFileVersionInfoSizeW
0x180041e2d  mov     r14d, eax
0x180041e30  test    eax, eax
0x180041e32  jz      loc_180041F0A
0x180041e38  call    cs:__imp_GetProcessHeap
0x180041e3e  mov     rsi, rax
0x180041e41  test    rax, rax
0x180041e44  jz      loc_180041F0A
0x180041e4a  mov     r8d, r14d; dwBytes
0x180041e4d  mov     edx, 8; dwFlags
0x180041e52  mov     rcx, rax; hHeap
0x180041e55  call    cs:__imp_HeapAlloc
0x180041e5b  mov     rdi, rax
0x180041e5e  test    rax, rax
0x180041e61  jnz     short loc_180041E6D
0x180041e63  mov     ebx, 8007000Eh
0x180041e68  jmp     loc_180041F0F
0x180041e6d  mov     r9, rdi; lpData
0x180041e70  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180041e75  mov     r8d, r14d; dwLen
0x180041e78  xor     edx, edx; dwHandle
0x180041e7a  call    cs:__imp_GetFileVersionInfoW
0x180041e80  test    eax, eax
0x180041e82  jnz     short loc_180041E8B
0x180041e84  mov     ebx, 8000FFFFh
0x180041e89  jmp     short loc_180041EFA
0x180041e8b  lea     r9, [rsp+2A0h+puLen]; puLen
0x180041e90  mov     rcx, rdi; pBlock
0x180041e93  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x180041e98  lea     rdx, pszSrc; "\\"
0x180041e9f  call    cs:__imp_VerQueryValueW
0x180041ea5  test    eax, eax
0x180041ea7  jz      short loc_180041E84
0x180041ea9  mov     rcx, [rsp+2A0h+lpBuffer]
0x180041eae  mov     rdx, [rsp+2A0h+var_270]
0x180041eb3  movzx   eax, word ptr [rcx+0Ah]
0x180041eb7  mov     [r13+0], eax
0x180041ebb  movzx   eax, word ptr [rcx+8]
0x180041ebf  mov     [rdx], eax
0x180041ec1  movzx   r8d, word ptr [rcx+0Eh]
0x180041ec6  mov     rax, [rsp+2A0h+var_268]
0x180041ecb  mov     [rax], r8d
0x180041ece  cmp     r8d, 23F0h
0x180041ed5  jnb     short loc_180041EEC
0x180041ed7  mov     eax, 0CCCCCCCDh
0x180041edc  mul     r8d
0x180041edf  shr     edx, 3
0x180041ee2  lea     eax, [rdx+rdx*4]
0x180041ee5  add     eax, eax
0x180041ee7  sub     r8d, eax
0x180041eea  jmp     short loc_180041EEF
0x180041eec  xor     r8d, r8d
0x180041eef  mov     [r15], r8d
0x180041ef2  mov     dword ptr [r12], 0
0x180041efa  mov     r8, rdi; lpMem
0x180041efd  xor     edx, edx; dwFlags
0x180041eff  mov     rcx, rsi; hHeap
0x180041f02  call    cs:__imp_HeapFree
0x180041f08  jmp     short loc_180041F0F
0x180041f0a  mov     ebx, 8000FFFFh
0x180041f0f  mov     eax, ebx
0x180041f11  mov     rcx, [rbp+1A0h+var_50]
0x180041f18  xor     rcx, rsp; StackCookie
0x180041f1b  call    __security_check_cookie
0x180041f20  add     rsp, 268h
0x180041f27  pop     r15
0x180041f29  pop     r14
0x180041f2b  pop     r13
0x180041f2d  pop     r12
0x180041f2f  pop     rdi
0x180041f30  pop     rsi
0x180041f31  pop     rbx
0x180041f32  pop     rbp
0x180041f33  retn
```
