# DiagCabOpenFile(char *,int,int,int *,void *)

- ea: `0x180025a40`
- end: `0x180025b35`
- name: `?DiagCabOpenFile@@YA_JPEADHHPEAHPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int OpenFlag, unsigned int, DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800256b0`

## callees

- `0x180025a40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025b05`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ae5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025a7d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025adb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025a7d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180025adb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025a9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025a9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025b0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025b1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025aac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025aac`
- `api-ms-win-crt-stdio-l1-1-0!_wopen` at `0x180025af8`
- `api-ms-win-crt-stdio-l1-1-0!_wopen` at `0x180025af8`

## pseudocode

```c
__int64 __fastcall DiagCabOpenFile(LPCCH lpMultiByteStr, int OpenFlag, unsigned int a3, DWORD *a4)
{
  int v4; // esi
  int v9; // eax
  int cchWideChar; // ebp
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  wchar_t *v14; // rbx
  HANDLE v15; // rax

  v4 = -1;
  v9 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v9;
  if ( v9 )
  {
    v11 = 2LL * (v9 + 1);
    ProcessHeap = GetProcessHeap();
    lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, v11);
    v14 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      if ( MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
      {
        v4 = _wopen(v14, OpenFlag, a3);
        if ( v4 == -1 )
          *a4 = *(_DWORD *)_o__errno();
      }
      else
      {
        *a4 = GetLastError();
      }
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
    }
    else
    {
      *a4 = 14;
    }
  }
  else
  {
    *a4 = GetLastError();
  }
  return v4;
}

```

## disassembly

```asm
0x180025a40  push    rbx
0x180025a42  push    rbp
0x180025a43  push    rsi
0x180025a44  push    rdi
0x180025a45  push    r12
0x180025a47  push    r14
0x180025a49  push    r15
0x180025a4b  sub     rsp, 30h
0x180025a4f  or      esi, 0FFFFFFFFh
0x180025a52  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x180025a5a  mov     r14d, r8d
0x180025a5d  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x180025a66  mov     rdi, r9
0x180025a69  mov     r15d, edx
0x180025a6c  mov     r12, rcx
0x180025a6f  mov     r8, rcx; lpMultiByteStr
0x180025a72  lea     edx, [rsi+9]; dwFlags
0x180025a75  or      r9d, esi; cbMultiByte
0x180025a78  mov     ecx, 0FDE9h; CodePage
0x180025a7d  call    cs:__imp_MultiByteToWideChar
0x180025a83  mov     ebp, eax
0x180025a85  test    eax, eax
0x180025a87  jnz     short loc_180025A96
0x180025a89  call    cs:__imp_GetLastError
0x180025a8f  mov     [rdi], eax
0x180025a91  jmp     loc_180025B23
0x180025a96  inc     eax
0x180025a98  movsxd  rbx, eax
0x180025a9b  add     rbx, rbx
0x180025a9e  call    cs:__imp_GetProcessHeap
0x180025aa4  mov     r8, rbx; dwBytes
0x180025aa7  xor     edx, edx; dwFlags
0x180025aa9  mov     rcx, rax; hHeap
0x180025aac  call    cs:__imp_HeapAlloc
0x180025ab2  mov     rbx, rax
0x180025ab5  test    rax, rax
0x180025ab8  jnz     short loc_180025AC2
0x180025aba  mov     dword ptr [rdi], 0Eh
0x180025ac0  jmp     short loc_180025B23
0x180025ac2  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180025ac6  mov     [rsp+68h+cchWideChar], ebp; cchWideChar
0x180025aca  mov     r8, r12; lpMultiByteStr
0x180025acd  mov     [rsp+68h+lpWideCharStr], rbx; lpWideCharStr
0x180025ad2  mov     ecx, 0FDE9h; CodePage
0x180025ad7  lea     edx, [r9+9]; dwFlags
0x180025adb  call    cs:__imp_MultiByteToWideChar
0x180025ae1  test    eax, eax
0x180025ae3  jnz     short loc_180025AEF
0x180025ae5  call    cs:__imp_GetLastError
0x180025aeb  mov     [rdi], eax
0x180025aed  jmp     short loc_180025B0F
0x180025aef  mov     r8d, r14d
0x180025af2  mov     edx, r15d; OpenFlag
0x180025af5  mov     rcx, rbx; FileName
0x180025af8  call    cs:__imp__wopen
0x180025afe  mov     esi, eax
0x180025b00  cmp     eax, 0FFFFFFFFh
0x180025b03  jnz     short loc_180025B0F
0x180025b05  call    cs:__imp__o__errno
0x180025b0b  mov     ecx, [rax]
0x180025b0d  mov     [rdi], ecx
0x180025b0f  call    cs:__imp_GetProcessHeap
0x180025b15  mov     r8, rbx; lpMem
0x180025b18  xor     edx, edx; dwFlags
0x180025b1a  mov     rcx, rax; hHeap
0x180025b1d  call    cs:__imp_HeapFree
0x180025b23  movsxd  rax, esi
0x180025b26  add     rsp, 30h
0x180025b2a  pop     r15
0x180025b2c  pop     r14
0x180025b2e  pop     r12
0x180025b30  pop     rdi
0x180025b31  pop     rsi
0x180025b32  pop     rbp
0x180025b33  pop     rbx
0x180025b34  retn
```
