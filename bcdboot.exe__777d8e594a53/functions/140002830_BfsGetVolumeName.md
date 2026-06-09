# BfsGetVolumeName

- ea: `0x140002830`
- end: `0x14000291f`
- name: `BfsGetVolumeName`
- size: `239`
- prototype: `WCHAR *__fastcall(LPCWSTR lpszFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140009fd4`

## callees

- `0x140002830`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140002862`
- `KERNEL32!SetLastError` at `0x1400028a5`
- `KERNEL32!SetLastError` at `0x140002862`
- `KERNEL32!SetLastError` at `0x1400028a5`
- `KERNEL32!HeapFree` at `0x1400028d1`
- `KERNEL32!HeapFree` at `0x14000290d`
- `KERNEL32!HeapFree` at `0x1400028d1`
- `KERNEL32!HeapFree` at `0x14000290d`
- `KERNEL32!HeapAlloc` at `0x140002851`
- `KERNEL32!HeapAlloc` at `0x140002894`
- `KERNEL32!HeapAlloc` at `0x140002851`
- `KERNEL32!HeapAlloc` at `0x140002894`
- `KERNEL32!GetProcessHeap` at `0x140002840`
- `KERNEL32!GetProcessHeap` at `0x140002883`
- `KERNEL32!GetProcessHeap` at `0x1400028c3`
- `KERNEL32!GetProcessHeap` at `0x1400028ff`
- `KERNEL32!GetProcessHeap` at `0x140002840`
- `KERNEL32!GetProcessHeap` at `0x140002883`
- `KERNEL32!GetProcessHeap` at `0x1400028c3`
- `KERNEL32!GetProcessHeap` at `0x1400028ff`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1400028b9`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1400028b9`
- `KERNEL32!GetVolumePathNameW` at `0x140002879`
- `KERNEL32!GetVolumePathNameW` at `0x140002879`

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
0x140002830  push    rbx
0x140002832  push    rbp
0x140002833  push    rsi
0x140002834  push    rdi
0x140002835  sub     rsp, 28h
0x140002839  xor     ebp, ebp
0x14000283b  mov     rsi, rcx
0x14000283e  mov     ebx, ebp
0x140002840  call    cs:__imp_GetProcessHeap
0x140002846  xor     edx, edx; dwFlags
0x140002848  mov     r8d, 208h; dwBytes
0x14000284e  mov     rcx, rax; hHeap
0x140002851  call    cs:__imp_HeapAlloc
0x140002857  mov     rdi, rax
0x14000285a  test    rax, rax
0x14000285d  jnz     short loc_14000286D
0x14000285f  lea     ecx, [rbp+8]; dwErrCode
0x140002862  call    cs:__imp_SetLastError
0x140002868  jmp     loc_140002913
0x14000286d  mov     r8d, 104h; cchBufferLength
0x140002873  mov     rdx, rdi; lpszVolumePathName
0x140002876  mov     rcx, rsi; lpszFileName
0x140002879  call    cs:__imp_GetVolumePathNameW
0x14000287f  test    eax, eax
0x140002881  jz      short loc_1400028FF
0x140002883  call    cs:__imp_GetProcessHeap
0x140002889  xor     edx, edx; dwFlags
0x14000288b  mov     r8d, 208h; dwBytes
0x140002891  mov     rcx, rax; hHeap
0x140002894  call    cs:__imp_HeapAlloc
0x14000289a  mov     rbx, rax
0x14000289d  test    rax, rax
0x1400028a0  jnz     short loc_1400028AD
0x1400028a2  lea     ecx, [rax+8]; dwErrCode
0x1400028a5  call    cs:__imp_SetLastError
0x1400028ab  jmp     short loc_1400028FF
0x1400028ad  mov     r8d, 104h; cchBufferLength
0x1400028b3  mov     rdx, rbx; lpszVolumeName
0x1400028b6  mov     rcx, rdi; lpszVolumeMountPoint
0x1400028b9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400028bf  test    eax, eax
0x1400028c1  jnz     short loc_1400028E5
0x1400028c3  call    cs:__imp_GetProcessHeap
0x1400028c9  mov     r8, rbx; lpMem
0x1400028cc  xor     edx, edx; dwFlags
0x1400028ce  mov     rcx, rax; hHeap
0x1400028d1  call    cs:__imp_HeapFree
0x1400028d7  test    eax, eax
0x1400028d9  mov     rcx, rbp
0x1400028dc  cmovz   rcx, rbx
0x1400028e0  mov     rbx, rcx
0x1400028e3  jmp     short loc_1400028FF
0x1400028e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400028e9  inc     rax
0x1400028ec  cmp     [rbx+rax*2], bp
0x1400028f0  jnz     short loc_1400028E9
0x1400028f2  dec     eax
0x1400028f4  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x1400028f9  jnz     short loc_1400028FF
0x1400028fb  mov     [rbx+rax*2], bp
0x1400028ff  call    cs:__imp_GetProcessHeap
0x140002905  mov     r8, rdi; lpMem
0x140002908  xor     edx, edx; dwFlags
0x14000290a  mov     rcx, rax; hHeap
0x14000290d  call    cs:__imp_HeapFree
0x140002913  mov     rax, rbx
0x140002916  add     rsp, 28h
0x14000291a  pop     rdi
0x14000291b  pop     rsi
0x14000291c  pop     rbp
0x14000291d  pop     rbx
0x14000291e  retn
```
