# BfsGetVolumeName

- ea: `0x180046374`
- end: `0x180046463`
- name: `BfsGetVolumeName`
- size: `239`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180049234`

## callees

- `0x180046374`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800463bd`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1800463bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046415`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046451`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046415`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180046451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046384`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800463c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046407`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046443`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046384`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800463c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046407`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180046443`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046395`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800463d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180046395`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800463d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800463a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800463e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800463a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800463e9`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800463fd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800463fd`

## pseudocode

```c
WCHAR *__fastcall BfsGetVolumeName(LPCWSTR lpszFileName)
{
  WCHAR *v2; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rdi
  HANDLE v6; // rax
  WCHAR *v7; // rax
  HANDLE v8; // rax
  BOOL v9; // eax
  WCHAR *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  HANDLE v13; // rax

  v2 = 0;
  ProcessHeap = GetProcessHeap();
  v4 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  v5 = v4;
  if ( v4 )
  {
    if ( GetVolumePathNameW(lpszFileName, v4, 0x104u) )
    {
      v6 = GetProcessHeap();
      v7 = (WCHAR *)HeapAlloc(v6, 0, 0x208u);
      v2 = v7;
      if ( v7 )
      {
        if ( GetVolumeNameForVolumeMountPointW(v5, v7, 0x104u) )
        {
          v11 = -1;
          do
            ++v11;
          while ( v2[v11] );
          v12 = (unsigned int)(v11 - 1);
          if ( v2[v12] == 92 )
            v2[v12] = 0;
        }
        else
        {
          v8 = GetProcessHeap();
          v9 = HeapFree(v8, 0, v2);
          v10 = 0;
          if ( !v9 )
            v10 = v2;
          v2 = v10;
        }
      }
      else
      {
        SetLastError(8u);
      }
    }
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v5);
  }
  else
  {
    SetLastError(8u);
  }
  return v2;
}

```

## disassembly

```asm
0x180046374  push    rbx
0x180046376  push    rbp
0x180046377  push    rsi
0x180046378  push    rdi
0x180046379  sub     rsp, 28h
0x18004637d  xor     ebp, ebp
0x18004637f  mov     rsi, rcx
0x180046382  mov     ebx, ebp
0x180046384  call    cs:__imp_GetProcessHeap
0x18004638a  xor     edx, edx; dwFlags
0x18004638c  mov     r8d, 208h; dwBytes
0x180046392  mov     rcx, rax; hHeap
0x180046395  call    cs:__imp_HeapAlloc
0x18004639b  mov     rdi, rax
0x18004639e  test    rax, rax
0x1800463a1  jnz     short loc_1800463B1
0x1800463a3  lea     ecx, [rbp+8]; dwErrCode
0x1800463a6  call    cs:__imp_SetLastError
0x1800463ac  jmp     loc_180046457
0x1800463b1  mov     r8d, 104h; cchBufferLength
0x1800463b7  mov     rdx, rdi; lpszVolumePathName
0x1800463ba  mov     rcx, rsi; lpszFileName
0x1800463bd  call    cs:__imp_GetVolumePathNameW
0x1800463c3  test    eax, eax
0x1800463c5  jz      short loc_180046443
0x1800463c7  call    cs:__imp_GetProcessHeap
0x1800463cd  xor     edx, edx; dwFlags
0x1800463cf  mov     r8d, 208h; dwBytes
0x1800463d5  mov     rcx, rax; hHeap
0x1800463d8  call    cs:__imp_HeapAlloc
0x1800463de  mov     rbx, rax
0x1800463e1  test    rax, rax
0x1800463e4  jnz     short loc_1800463F1
0x1800463e6  lea     ecx, [rax+8]; dwErrCode
0x1800463e9  call    cs:__imp_SetLastError
0x1800463ef  jmp     short loc_180046443
0x1800463f1  mov     r8d, 104h; cchBufferLength
0x1800463f7  mov     rdx, rbx; lpszVolumeName
0x1800463fa  mov     rcx, rdi; lpszVolumeMountPoint
0x1800463fd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180046403  test    eax, eax
0x180046405  jnz     short loc_180046429
0x180046407  call    cs:__imp_GetProcessHeap
0x18004640d  mov     r8, rbx; lpMem
0x180046410  xor     edx, edx; dwFlags
0x180046412  mov     rcx, rax; hHeap
0x180046415  call    cs:__imp_HeapFree
0x18004641b  test    eax, eax
0x18004641d  mov     rcx, rbp
0x180046420  cmovz   rcx, rbx
0x180046424  mov     rbx, rcx
0x180046427  jmp     short loc_180046443
0x180046429  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004642d  inc     rax
0x180046430  cmp     [rbx+rax*2], bp
0x180046434  jnz     short loc_18004642D
0x180046436  dec     eax
0x180046438  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18004643d  jnz     short loc_180046443
0x18004643f  mov     [rbx+rax*2], bp
0x180046443  call    cs:__imp_GetProcessHeap
0x180046449  mov     r8, rdi; lpMem
0x18004644c  xor     edx, edx; dwFlags
0x18004644e  mov     rcx, rax; hHeap
0x180046451  call    cs:__imp_HeapFree
0x180046457  mov     rax, rbx
0x18004645a  add     rsp, 28h
0x18004645e  pop     rdi
0x18004645f  pop     rsi
0x180046460  pop     rbp
0x180046461  pop     rbx
0x180046462  retn
```
