# GetOSVersionFromFile

- ea: `0x18001d9fc`
- end: `0x18001dbe4`
- name: `GetOSVersionFromFile`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18002620c`

## callees

- `0x180004ea0`
- `0x18000d508`
- `0x18001d9fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dae8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dae8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dbb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001db05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001db05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001da60`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001daa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001da60`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001daa5`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001db4f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001db4f`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001db2a`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18001db2a`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001dad7`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18001dad7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001da93`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001da93`

## string_xrefs

- `0x18001da73`: `\kernel32.dll`
- `0x18001dab5`: `\ntdll.dll`

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
0x18001d9fc  push    rbp
0x18001d9fe  push    rbx
0x18001d9ff  push    rsi
0x18001da00  push    rdi
0x18001da01  push    r12
0x18001da03  push    r13
0x18001da05  push    r14
0x18001da07  push    r15
0x18001da09  lea     rbp, [rsp-168h]
0x18001da11  sub     rsp, 268h
0x18001da18  mov     rax, cs:__security_cookie
0x18001da1f  xor     rax, rsp
0x18001da22  mov     [rbp+1A0h+var_50], rax
0x18001da29  mov     rax, [rbp+1A0h+arg_20]
0x18001da30  mov     r13, rcx
0x18001da33  mov     [rsp+2A0h+var_270], rdx
0x18001da38  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18001da3d  mov     edi, 104h
0x18001da42  mov     [rsp+2A0h+var_268], rax
0x18001da47  mov     edx, edi; uSize
0x18001da49  mov     [rsp+2A0h+lpBuffer], 0
0x18001da52  mov     r12, r9
0x18001da55  mov     [rsp+2A0h+puLen], 0
0x18001da5d  mov     r15, r8
0x18001da60  call    cs:__imp_GetSystemDirectoryW
0x18001da66  dec     eax
0x18001da68  lea     esi, [rdi-2]
0x18001da6b  cmp     eax, esi
0x18001da6d  ja      loc_18001DBBA
0x18001da73  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x18001da7a  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001da7f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001da84  mov     ebx, eax
0x18001da86  test    eax, eax
0x18001da88  js      loc_18001DBBF
0x18001da8e  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x18001da93  call    cs:__imp_GetFileAttributesW
0x18001da99  cmp     eax, 0FFFFFFFFh
0x18001da9c  jnz     short loc_18001DAD0
0x18001da9e  mov     edx, edi; uSize
0x18001daa0  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x18001daa5  call    cs:__imp_GetSystemDirectoryW
0x18001daab  dec     eax
0x18001daad  cmp     eax, esi
0x18001daaf  ja      loc_18001DBBA
0x18001dab5  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x18001dabc  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x18001dac1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001dac6  mov     ebx, eax
0x18001dac8  test    eax, eax
0x18001daca  js      loc_18001DBBF
0x18001dad0  xor     edx, edx; lpdwHandle
0x18001dad2  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18001dad7  call    cs:__imp_GetFileVersionInfoSizeW
0x18001dadd  mov     r14d, eax
0x18001dae0  test    eax, eax
0x18001dae2  jz      loc_18001DBBA
0x18001dae8  call    cs:__imp_GetProcessHeap
0x18001daee  mov     rsi, rax
0x18001daf1  test    rax, rax
0x18001daf4  jz      loc_18001DBBA
0x18001dafa  mov     r8d, r14d; dwBytes
0x18001dafd  mov     edx, 8; dwFlags
0x18001db02  mov     rcx, rax; hHeap
0x18001db05  call    cs:__imp_HeapAlloc
0x18001db0b  mov     rdi, rax
0x18001db0e  test    rax, rax
0x18001db11  jnz     short loc_18001DB1D
0x18001db13  mov     ebx, 8007000Eh
0x18001db18  jmp     loc_18001DBBF
0x18001db1d  mov     r9, rdi; lpData
0x18001db20  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18001db25  mov     r8d, r14d; dwLen
0x18001db28  xor     edx, edx; dwHandle
0x18001db2a  call    cs:__imp_GetFileVersionInfoW
0x18001db30  test    eax, eax
0x18001db32  jnz     short loc_18001DB3B
0x18001db34  mov     ebx, 8000FFFFh
0x18001db39  jmp     short loc_18001DBAA
0x18001db3b  lea     r9, [rsp+2A0h+puLen]; puLen
0x18001db40  mov     rcx, rdi; pBlock
0x18001db43  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x18001db48  lea     rdx, SubBlock; "\\"
0x18001db4f  call    cs:__imp_VerQueryValueW
0x18001db55  test    eax, eax
0x18001db57  jz      short loc_18001DB34
0x18001db59  mov     rcx, [rsp+2A0h+lpBuffer]
0x18001db5e  mov     rdx, [rsp+2A0h+var_270]
0x18001db63  movzx   eax, word ptr [rcx+0Ah]
0x18001db67  mov     [r13+0], eax
0x18001db6b  movzx   eax, word ptr [rcx+8]
0x18001db6f  mov     [rdx], eax
0x18001db71  movzx   r8d, word ptr [rcx+0Eh]
0x18001db76  mov     rax, [rsp+2A0h+var_268]
0x18001db7b  mov     [rax], r8d
0x18001db7e  cmp     r8d, 23F0h
0x18001db85  jnb     short loc_18001DB9C
0x18001db87  mov     eax, 0CCCCCCCDh
0x18001db8c  mul     r8d
0x18001db8f  shr     edx, 3
0x18001db92  lea     eax, [rdx+rdx*4]
0x18001db95  add     eax, eax
0x18001db97  sub     r8d, eax
0x18001db9a  jmp     short loc_18001DB9F
0x18001db9c  xor     r8d, r8d
0x18001db9f  mov     [r15], r8d
0x18001dba2  mov     dword ptr [r12], 0
0x18001dbaa  mov     r8, rdi; lpMem
0x18001dbad  xor     edx, edx; dwFlags
0x18001dbaf  mov     rcx, rsi; hHeap
0x18001dbb2  call    cs:__imp_HeapFree
0x18001dbb8  jmp     short loc_18001DBBF
0x18001dbba  mov     ebx, 8000FFFFh
0x18001dbbf  mov     eax, ebx
0x18001dbc1  mov     rcx, [rbp+1A0h+var_50]
0x18001dbc8  xor     rcx, rsp; StackCookie
0x18001dbcb  call    __security_check_cookie
0x18001dbd0  add     rsp, 268h
0x18001dbd7  pop     r15
0x18001dbd9  pop     r14
0x18001dbdb  pop     r13
0x18001dbdd  pop     r12
0x18001dbdf  pop     rdi
0x18001dbe0  pop     rsi
0x18001dbe1  pop     rbx
0x18001dbe2  pop     rbp
0x18001dbe3  retn
```
