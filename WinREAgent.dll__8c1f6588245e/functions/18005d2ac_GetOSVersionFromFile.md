# GetOSVersionFromFile

- ea: `0x18005d2ac`
- end: `0x18005d498`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180062898`

## callees

- `0x180012794`
- `0x18005d2ac`
- `0x18006c690`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18005d466`
- `KERNEL32!HeapFree` at `0x18005d466`
- `KERNEL32!HeapAlloc` at `0x18005d3b9`
- `KERNEL32!HeapAlloc` at `0x18005d3b9`
- `KERNEL32!GetProcessHeap` at `0x18005d39c`
- `KERNEL32!GetProcessHeap` at `0x18005d39c`
- `KERNEL32!GetFileAttributesW` at `0x18005d345`
- `KERNEL32!GetFileAttributesW` at `0x18005d345`
- `KERNEL32!GetSystemDirectoryW` at `0x18005d310`
- `KERNEL32!GetSystemDirectoryW` at `0x18005d357`
- `KERNEL32!GetSystemDirectoryW` at `0x18005d310`
- `KERNEL32!GetSystemDirectoryW` at `0x18005d357`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18005d3de`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18005d3de`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18005d38b`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18005d38b`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18005d403`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18005d403`

## string_xrefs

- `0x18005d323`: `\kernel32.dll`
- `0x18005d367`: `\ntdll.dll`

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
0x18005d2ac  push    rbp
0x18005d2ae  push    rbx
0x18005d2af  push    rsi
0x18005d2b0  push    rdi
0x18005d2b1  push    r12
0x18005d2b3  push    r13
0x18005d2b5  push    r14
0x18005d2b7  push    r15
0x18005d2b9  lea     rbp, [rsp-168h]
0x18005d2c1  sub     rsp, 268h
0x18005d2c8  mov     rax, cs:__security_cookie
0x18005d2cf  xor     rax, rsp
0x18005d2d2  mov     [rbp+1A0h+var_50], rax
0x18005d2d9  mov     rax, [rbp+1A0h+arg_20]
0x18005d2e0  mov     r13, rcx
0x18005d2e3  mov     [rsp+2A0h+var_270], rdx
0x18005d2e8  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18005d2ed  mov     edi, 104h
0x18005d2f2  mov     [rsp+2A0h+var_268], rax
0x18005d2f7  mov     edx, edi; uSize
0x18005d2f9  mov     [rsp+2A0h+lpBuffer], 0
0x18005d302  mov     r12, r9
0x18005d305  mov     [rsp+2A0h+puLen], 0
0x18005d30d  mov     r15, r8
0x18005d310  call    cs:__imp_GetSystemDirectoryW
0x18005d316  dec     eax
0x18005d318  lea     esi, [rdi-2]
0x18005d31b  cmp     eax, esi
0x18005d31d  ja      loc_18005D46E
0x18005d323  lea     r8, aKernel32Dll_0; "\\kernel32.dll"
0x18005d32a  mov     edx, edi; unsigned __int64
0x18005d32c  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18005d331  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d336  mov     ebx, eax
0x18005d338  test    eax, eax
0x18005d33a  js      loc_18005D473
0x18005d340  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x18005d345  call    cs:__imp_GetFileAttributesW
0x18005d34b  cmp     eax, 0FFFFFFFFh
0x18005d34e  jnz     short loc_18005D384
0x18005d350  mov     edx, edi; uSize
0x18005d352  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18005d357  call    cs:__imp_GetSystemDirectoryW
0x18005d35d  dec     eax
0x18005d35f  cmp     eax, esi
0x18005d361  ja      loc_18005D46E
0x18005d367  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x18005d36e  mov     edx, edi; unsigned __int64
0x18005d370  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18005d375  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d37a  mov     ebx, eax
0x18005d37c  test    eax, eax
0x18005d37e  js      loc_18005D473
0x18005d384  xor     edx, edx; lpdwHandle
0x18005d386  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18005d38b  call    cs:__imp_GetFileVersionInfoSizeW
0x18005d391  mov     r14d, eax
0x18005d394  test    eax, eax
0x18005d396  jz      loc_18005D46E
0x18005d39c  call    cs:__imp_GetProcessHeap
0x18005d3a2  mov     rsi, rax
0x18005d3a5  test    rax, rax
0x18005d3a8  jz      loc_18005D46E
0x18005d3ae  mov     r8d, r14d; dwBytes
0x18005d3b1  mov     edx, 8; dwFlags
0x18005d3b6  mov     rcx, rax; hHeap
0x18005d3b9  call    cs:__imp_HeapAlloc
0x18005d3bf  mov     rdi, rax
0x18005d3c2  test    rax, rax
0x18005d3c5  jnz     short loc_18005D3D1
0x18005d3c7  mov     ebx, 8007000Eh
0x18005d3cc  jmp     loc_18005D473
0x18005d3d1  mov     r9, rdi; lpData
0x18005d3d4  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18005d3d9  mov     r8d, r14d; dwLen
0x18005d3dc  xor     edx, edx; dwHandle
0x18005d3de  call    cs:__imp_GetFileVersionInfoW
0x18005d3e4  test    eax, eax
0x18005d3e6  jnz     short loc_18005D3EF
0x18005d3e8  mov     ebx, 8000FFFFh
0x18005d3ed  jmp     short loc_18005D45E
0x18005d3ef  lea     r9, [rsp+2A0h+puLen]; puLen
0x18005d3f4  mov     rcx, rdi; pBlock
0x18005d3f7  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x18005d3fc  lea     rdx, SubBlock; "\\"
0x18005d403  call    cs:__imp_VerQueryValueW
0x18005d409  test    eax, eax
0x18005d40b  jz      short loc_18005D3E8
0x18005d40d  mov     rcx, [rsp+2A0h+lpBuffer]
0x18005d412  mov     rdx, [rsp+2A0h+var_270]
0x18005d417  movzx   eax, word ptr [rcx+0Ah]
0x18005d41b  mov     [r13+0], eax
0x18005d41f  movzx   eax, word ptr [rcx+8]
0x18005d423  mov     [rdx], eax
0x18005d425  movzx   r8d, word ptr [rcx+0Eh]
0x18005d42a  mov     rax, [rsp+2A0h+var_268]
0x18005d42f  mov     [rax], r8d
0x18005d432  cmp     r8d, 23F0h
0x18005d439  jnb     short loc_18005D450
0x18005d43b  mov     eax, 0CCCCCCCDh
0x18005d440  mul     r8d
0x18005d443  shr     edx, 3
0x18005d446  lea     eax, [rdx+rdx*4]
0x18005d449  add     eax, eax
0x18005d44b  sub     r8d, eax
0x18005d44e  jmp     short loc_18005D453
0x18005d450  xor     r8d, r8d
0x18005d453  mov     [r15], r8d
0x18005d456  mov     dword ptr [r12], 0
0x18005d45e  mov     r8, rdi; lpMem
0x18005d461  xor     edx, edx; dwFlags
0x18005d463  mov     rcx, rsi; hHeap
0x18005d466  call    cs:__imp_HeapFree
0x18005d46c  jmp     short loc_18005D473
0x18005d46e  mov     ebx, 8000FFFFh
0x18005d473  mov     eax, ebx
0x18005d475  mov     rcx, [rbp+1A0h+var_50]
0x18005d47c  xor     rcx, rsp; StackCookie
0x18005d47f  call    __security_check_cookie
0x18005d484  add     rsp, 268h
0x18005d48b  pop     r15
0x18005d48d  pop     r14
0x18005d48f  pop     r13
0x18005d491  pop     r12
0x18005d493  pop     rdi
0x18005d494  pop     rsi
0x18005d495  pop     rbx
0x18005d496  pop     rbp
0x18005d497  retn
```
