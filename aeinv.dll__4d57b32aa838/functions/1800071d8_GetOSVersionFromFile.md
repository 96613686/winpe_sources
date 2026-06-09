# GetOSVersionFromFile

- ea: `0x1800071d8`
- end: `0x18000740b`
- name: `GetOSVersionFromFile`
- size: `563`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, unsigned int *, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180006d34`

## callees

- `0x1800071d8`
- `0x180007420`
- `0x18004f970`
- `0x180059920`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800072b9`
- `KERNEL32!GetFileAttributesW` at `0x1800072b9`
- `KERNEL32!GetSystemDirectoryW` at `0x180007236`
- `KERNEL32!GetSystemDirectoryW` at `0x1800072cb`
- `KERNEL32!GetSystemDirectoryW` at `0x180007236`
- `KERNEL32!GetSystemDirectoryW` at `0x1800072cb`
- `KERNEL32!GetProcessHeap` at `0x18000730f`
- `KERNEL32!GetProcessHeap` at `0x18000730f`
- `KERNEL32!HeapAlloc` at `0x18000732c`
- `KERNEL32!HeapAlloc` at `0x18000732c`
- `KERNEL32!HeapFree` at `0x1800073d9`
- `KERNEL32!HeapFree` at `0x1800073d9`
- `VERSION!GetFileVersionInfoW` at `0x180007351`
- `VERSION!GetFileVersionInfoW` at `0x180007351`
- `VERSION!GetFileVersionInfoSizeW` at `0x1800072fe`
- `VERSION!GetFileVersionInfoSizeW` at `0x1800072fe`
- `VERSION!VerQueryValueW` at `0x180007376`
- `VERSION!VerQueryValueW` at `0x180007376`

## string_xrefs

- `0x18000729e`: `\kernel32.dll`
- `0x1800072dc`: `\ntdll.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  __int64 v8; // rdx
  WCHAR *v9; // rax
  HRESULT v10; // ebx
  __int64 v11; // r8
  unsigned __int64 v12; // rdx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v15; // rsi
  void *v16; // rax
  void *v17; // rdi
  unsigned __int16 *v18; // rcx
  _DWORD *v19; // rdx
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  size_t v23; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD *v26; // [rsp+40h] [rbp-C0h]
  unsigned int *v27; // [rsp+48h] [rbp-B8h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v26 = a2;
  v27 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v8 = 260;
  v9 = Buffer;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
    return (unsigned int)v10;
  v11 = (260 - v8) & -(__int64)(v8 != 0);
  v10 = StringCopyWorkerW(&Buffer[v11], 260 - v11, 0, L"\\kernel32.dll", v23);
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147418113;
    v10 = StringCchCatW(Buffer, v12, L"\\ntdll.dll");
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
  if ( !FileVersionInfoSizeW )
    return (unsigned int)-2147418113;
  ProcessHeap = GetProcessHeap();
  v15 = ProcessHeap;
  if ( !ProcessHeap )
    return (unsigned int)-2147418113;
  v16 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
  v17 = v16;
  if ( v16 )
  {
    if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v16) && VerQueryValueW(v17, L"\\", &lpBuffer, &puLen) )
    {
      v18 = (unsigned __int16 *)lpBuffer;
      v19 = v26;
      *a1 = *((unsigned __int16 *)lpBuffer + 5);
      *v19 = v18[4];
      v20 = v18[7];
      *v27 = v20;
      if ( v20 >= 0x23F0 )
        v21 = 0;
      else
        v21 = v20 % 0xA;
      *a3 = v21;
      *a4 = 0;
    }
    else
    {
      v10 = -2147418113;
    }
    HeapFree(v15, 0, v17);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800071d8  push    rbp
0x1800071da  push    rbx
0x1800071db  push    rsi
0x1800071dc  push    rdi
0x1800071dd  push    r12
0x1800071df  push    r13
0x1800071e1  push    r14
0x1800071e3  push    r15
0x1800071e5  lea     rbp, [rsp-178h]
0x1800071ed  sub     rsp, 278h
0x1800071f4  mov     rax, cs:__security_cookie
0x1800071fb  xor     rax, rsp
0x1800071fe  mov     [rbp+1B0h+var_50], rax
0x180007205  mov     rax, [rbp+1B0h+arg_20]
0x18000720c  mov     r13, rcx
0x18000720f  mov     [rsp+2B0h+var_270], rdx
0x180007214  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x180007219  xor     edi, edi
0x18000721b  mov     [rsp+2B0h+var_268], rax
0x180007220  mov     esi, 104h
0x180007225  mov     [rsp+2B0h+lpBuffer], rdi
0x18000722a  mov     edx, esi; uSize
0x18000722c  mov     [rsp+2B0h+puLen], edi
0x180007230  mov     r12, r9
0x180007233  mov     r15, r8
0x180007236  call    cs:__imp_GetSystemDirectoryW
0x18000723c  dec     eax
0x18000723e  lea     r14d, [rsi-2]
0x180007242  cmp     eax, r14d
0x180007245  ja      loc_1800073E1
0x18000724b  mov     edx, esi
0x18000724d  lea     rax, [rsp+2B0h+Buffer]
0x180007252  cmp     [rax], di
0x180007255  jz      short loc_180007261
0x180007257  add     rax, 2
0x18000725b  sub     rdx, 1
0x18000725f  jnz     short loc_180007252
0x180007261  mov     rax, rdx
0x180007264  mov     rcx, rsi
0x180007267  neg     rax
0x18000726a  mov     rax, rdx
0x18000726d  sbb     ebx, ebx
0x18000726f  sub     rcx, rdx
0x180007272  not     ebx
0x180007274  and     ebx, 80070057h
0x18000727a  neg     rax
0x18000727d  sbb     r8, r8
0x180007280  and     r8, rcx
0x180007283  test    rdx, rdx
0x180007286  jz      loc_1800073E6
0x18000728c  mov     rdx, rsi
0x18000728f  lea     rcx, [rsp+2B0h+Buffer]
0x180007294  sub     rdx, r8; cchDest
0x180007297  lea     rcx, [rcx+r8*2]; pszDest
0x18000729b  xor     r8d, r8d; pcchNewDestLength
0x18000729e  lea     r9, aKernel32Dll_0; "\\kernel32.dll"
0x1800072a5  call    StringCopyWorkerW
0x1800072aa  mov     ebx, eax
0x1800072ac  test    eax, eax
0x1800072ae  js      loc_1800073E6
0x1800072b4  lea     rcx, [rsp+2B0h+Buffer]; lpFileName
0x1800072b9  call    cs:__imp_GetFileAttributesW
0x1800072bf  cmp     eax, 0FFFFFFFFh
0x1800072c2  jnz     short loc_1800072F7
0x1800072c4  mov     edx, esi; uSize
0x1800072c6  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x1800072cb  call    cs:__imp_GetSystemDirectoryW
0x1800072d1  dec     eax
0x1800072d3  cmp     eax, r14d
0x1800072d6  ja      loc_1800073E1
0x1800072dc  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x1800072e3  lea     rcx, [rsp+2B0h+Buffer]; unsigned __int16 *
0x1800072e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800072ed  mov     ebx, eax
0x1800072ef  test    eax, eax
0x1800072f1  js      loc_1800073E6
0x1800072f7  xor     edx, edx; lpdwHandle
0x1800072f9  lea     rcx, [rsp+2B0h+Buffer]; lptstrFilename
0x1800072fe  call    cs:__imp_GetFileVersionInfoSizeW
0x180007304  mov     r14d, eax
0x180007307  test    eax, eax
0x180007309  jz      loc_1800073E1
0x18000730f  call    cs:__imp_GetProcessHeap
0x180007315  mov     rsi, rax
0x180007318  test    rax, rax
0x18000731b  jz      loc_1800073E1
0x180007321  mov     r8d, r14d; dwBytes
0x180007324  mov     edx, 8; dwFlags
0x180007329  mov     rcx, rax; hHeap
0x18000732c  call    cs:__imp_HeapAlloc
0x180007332  mov     rdi, rax
0x180007335  test    rax, rax
0x180007338  jnz     short loc_180007344
0x18000733a  mov     ebx, 8007000Eh
0x18000733f  jmp     loc_1800073E6
0x180007344  mov     r9, rdi; lpData
0x180007347  lea     rcx, [rsp+2B0h+Buffer]; lptstrFilename
0x18000734c  mov     r8d, r14d; dwLen
0x18000734f  xor     edx, edx; dwHandle
0x180007351  call    cs:__imp_GetFileVersionInfoW
0x180007357  test    eax, eax
0x180007359  jnz     short loc_180007362
0x18000735b  mov     ebx, 8000FFFFh
0x180007360  jmp     short loc_1800073D1
0x180007362  lea     r9, [rsp+2B0h+puLen]; puLen
0x180007367  mov     rcx, rdi; pBlock
0x18000736a  lea     r8, [rsp+2B0h+lpBuffer]; lplpBuffer
0x18000736f  lea     rdx, SubBlock; "\\"
0x180007376  call    cs:__imp_VerQueryValueW
0x18000737c  test    eax, eax
0x18000737e  jz      short loc_18000735B
0x180007380  mov     rcx, [rsp+2B0h+lpBuffer]
0x180007385  mov     rdx, [rsp+2B0h+var_270]
0x18000738a  movzx   eax, word ptr [rcx+0Ah]
0x18000738e  mov     [r13+0], eax
0x180007392  movzx   eax, word ptr [rcx+8]
0x180007396  mov     [rdx], eax
0x180007398  movzx   r8d, word ptr [rcx+0Eh]
0x18000739d  mov     rax, [rsp+2B0h+var_268]
0x1800073a2  mov     [rax], r8d
0x1800073a5  cmp     r8d, 23F0h
0x1800073ac  jnb     short loc_1800073C3
0x1800073ae  mov     eax, 0CCCCCCCDh
0x1800073b3  mul     r8d
0x1800073b6  shr     edx, 3
0x1800073b9  lea     eax, [rdx+rdx*4]
0x1800073bc  add     eax, eax
0x1800073be  sub     r8d, eax
0x1800073c1  jmp     short loc_1800073C6
0x1800073c3  xor     r8d, r8d
0x1800073c6  mov     [r15], r8d
0x1800073c9  mov     dword ptr [r12], 0
0x1800073d1  mov     r8, rdi; lpMem
0x1800073d4  xor     edx, edx; dwFlags
0x1800073d6  mov     rcx, rsi; hHeap
0x1800073d9  call    cs:__imp_HeapFree
0x1800073df  jmp     short loc_1800073E6
0x1800073e1  mov     ebx, 8000FFFFh
0x1800073e6  mov     eax, ebx
0x1800073e8  mov     rcx, [rbp+1B0h+var_50]
0x1800073ef  xor     rcx, rsp; StackCookie
0x1800073f2  call    __security_check_cookie
0x1800073f7  add     rsp, 278h
0x1800073fe  pop     r15
0x180007400  pop     r14
0x180007402  pop     r13
0x180007404  pop     r12
0x180007406  pop     rdi
0x180007407  pop     rsi
0x180007408  pop     rbx
0x180007409  pop     rbp
0x18000740a  retn
```
