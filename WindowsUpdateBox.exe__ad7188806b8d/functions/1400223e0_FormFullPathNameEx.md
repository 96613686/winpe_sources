# FormFullPathNameEx

- ea: `0x1400223e0`
- end: `0x14002258c`
- name: `FormFullPathNameEx`
- size: `428`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001cfa4`

## callees

- `0x1400222e8`
- `0x1400223e0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400224f7`
- `KERNEL32!HeapFree` at `0x14002252a`
- `KERNEL32!HeapFree` at `0x1400224f7`
- `KERNEL32!HeapFree` at `0x14002252a`
- `KERNEL32!HeapAlloc` at `0x14002246a`
- `KERNEL32!HeapAlloc` at `0x14002246a`
- `KERNEL32!GetProcessHeap` at `0x140022453`
- `KERNEL32!GetProcessHeap` at `0x1400224e3`
- `KERNEL32!GetProcessHeap` at `0x140022516`
- `KERNEL32!GetProcessHeap` at `0x140022453`
- `KERNEL32!GetProcessHeap` at `0x1400224e3`
- `KERNEL32!GetProcessHeap` at `0x140022516`
- `KERNEL32!SetCurrentDirectoryW` at `0x14002249b`
- `KERNEL32!SetCurrentDirectoryW` at `0x1400224bb`
- `KERNEL32!SetCurrentDirectoryW` at `0x14002249b`
- `KERNEL32!SetCurrentDirectoryW` at `0x1400224bb`
- `KERNEL32!GetCurrentDirectoryW` at `0x140022436`
- `KERNEL32!GetCurrentDirectoryW` at `0x140022488`
- `KERNEL32!GetCurrentDirectoryW` at `0x140022436`
- `KERNEL32!GetCurrentDirectoryW` at `0x140022488`
- `KERNEL32!GetLastError` at `0x1400224d0`
- `KERNEL32!GetLastError` at `0x140022508`
- `KERNEL32!GetLastError` at `0x140022538`
- `KERNEL32!GetLastError` at `0x1400224d0`
- `KERNEL32!GetLastError` at `0x140022508`
- `KERNEL32!GetLastError` at `0x140022538`
- `KERNEL32!SetLastError` at `0x140022548`
- `KERNEL32!SetLastError` at `0x14002255e`
- `KERNEL32!SetLastError` at `0x140022548`
- `KERNEL32!SetLastError` at `0x14002255e`

## pseudocode

```c
void *__fastcall FormFullPathNameEx(LPCWSTR lpPathName, LPCWSTR lpFileName)
{
  void *v4; // rsi
  DWORD LastError; // edi
  DWORD CurrentDirectoryW; // r15d
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  HANDLE v10; // rax
  HANDLE v11; // rax

  v4 = 0;
  LastError = 0;
  if ( lpFileName && *lpFileName && lpPathName && *lpPathName )
  {
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    if ( CurrentDirectoryW )
    {
      ProcessHeap = GetProcessHeap();
      v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * CurrentDirectoryW);
      v9 = v8;
      if ( v8 )
      {
        if ( GetCurrentDirectoryW(CurrentDirectoryW, v8) && SetCurrentDirectoryW(lpPathName) )
        {
          v4 = (void *)FormFullPathName(lpFileName, 0);
          if ( !SetCurrentDirectoryW(v9) || !v4 )
          {
            LastError = GetLastError();
            if ( v4 )
            {
              v10 = GetProcessHeap();
              HeapFree(v10, 0, v4);
              v4 = 0;
            }
          }
        }
        else
        {
          LastError = GetLastError();
        }
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v9);
      }
    }
    else
    {
      LastError = GetLastError();
    }
    SetLastError(LastError);
    return v4;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x1400223e0  mov     rax, rsp
0x1400223e3  mov     [rax+8], rbx
0x1400223e7  mov     [rax+10h], rbp
0x1400223eb  mov     [rax+18h], rsi
0x1400223ef  mov     [rax+20h], rdi
0x1400223f3  push    r12
0x1400223f5  push    r14
0x1400223f7  push    r15
0x1400223f9  sub     rsp, 20h
0x1400223fd  xor     r12d, r12d
0x140022400  mov     r14, rdx
0x140022403  mov     rbp, rcx
0x140022406  mov     esi, r12d
0x140022409  mov     edi, r12d
0x14002240c  test    rdx, rdx
0x14002240f  jz      loc_140022559
0x140022415  cmp     r12w, [rdx]
0x140022419  jz      loc_140022559
0x14002241f  test    rcx, rcx
0x140022422  jz      loc_140022559
0x140022428  cmp     r12w, [rcx]
0x14002242c  jz      loc_140022559
0x140022432  xor     edx, edx; lpBuffer
0x140022434  xor     ecx, ecx; nBufferLength
0x140022436  call    cs:__imp_GetCurrentDirectoryW
0x14002243d  nop     dword ptr [rax+rax+00h]
0x140022442  mov     r15d, eax
0x140022445  test    eax, eax
0x140022447  jz      loc_140022538
0x14002244d  mov     ebx, r15d
0x140022450  add     rbx, rbx
0x140022453  call    cs:__imp_GetProcessHeap
0x14002245a  nop     dword ptr [rax+rax+00h]
0x14002245f  mov     r8, rbx; dwBytes
0x140022462  lea     edx, [r12+8]; dwFlags
0x140022467  mov     rcx, rax; hHeap
0x14002246a  call    cs:__imp_HeapAlloc
0x140022471  nop     dword ptr [rax+rax+00h]
0x140022476  mov     rbx, rax
0x140022479  test    rax, rax
0x14002247c  jz      loc_140022546
0x140022482  mov     rdx, rax; lpBuffer
0x140022485  mov     ecx, r15d; nBufferLength
0x140022488  call    cs:__imp_GetCurrentDirectoryW
0x14002248f  nop     dword ptr [rax+rax+00h]
0x140022494  test    eax, eax
0x140022496  jz      short loc_140022508
0x140022498  mov     rcx, rbp; lpPathName
0x14002249b  call    cs:__imp_SetCurrentDirectoryW
0x1400224a2  nop     dword ptr [rax+rax+00h]
0x1400224a7  test    eax, eax
0x1400224a9  jz      short loc_140022508
0x1400224ab  xor     edx, edx; lpFilePart
0x1400224ad  mov     rcx, r14; lpFileName
0x1400224b0  call    FormFullPathName
0x1400224b5  mov     rcx, rbx; lpPathName
0x1400224b8  mov     rsi, rax
0x1400224bb  call    cs:__imp_SetCurrentDirectoryW
0x1400224c2  nop     dword ptr [rax+rax+00h]
0x1400224c7  test    eax, eax
0x1400224c9  jz      short loc_1400224D0
0x1400224cb  test    rsi, rsi
0x1400224ce  jnz     short loc_140022516
0x1400224d0  call    cs:__imp_GetLastError
0x1400224d7  nop     dword ptr [rax+rax+00h]
0x1400224dc  mov     edi, eax
0x1400224de  test    rsi, rsi
0x1400224e1  jz      short loc_140022516
0x1400224e3  call    cs:__imp_GetProcessHeap
0x1400224ea  nop     dword ptr [rax+rax+00h]
0x1400224ef  mov     r8, rsi; lpMem
0x1400224f2  xor     edx, edx; dwFlags
0x1400224f4  mov     rcx, rax; hHeap
0x1400224f7  call    cs:__imp_HeapFree
0x1400224fe  nop     dword ptr [rax+rax+00h]
0x140022503  mov     rsi, r12
0x140022506  jmp     short loc_140022516
0x140022508  call    cs:__imp_GetLastError
0x14002250f  nop     dword ptr [rax+rax+00h]
0x140022514  mov     edi, eax
0x140022516  call    cs:__imp_GetProcessHeap
0x14002251d  nop     dword ptr [rax+rax+00h]
0x140022522  mov     r8, rbx; lpMem
0x140022525  xor     edx, edx; dwFlags
0x140022527  mov     rcx, rax; hHeap
0x14002252a  call    cs:__imp_HeapFree
0x140022531  nop     dword ptr [rax+rax+00h]
0x140022536  jmp     short loc_140022546
0x140022538  call    cs:__imp_GetLastError
0x14002253f  nop     dword ptr [rax+rax+00h]
0x140022544  mov     edi, eax
0x140022546  mov     ecx, edi; dwErrCode
0x140022548  call    cs:__imp_SetLastError
0x14002254f  nop     dword ptr [rax+rax+00h]
0x140022554  mov     rax, rsi
0x140022557  jmp     short loc_14002256C
0x140022559  mov     ecx, 57h ; 'W'; dwErrCode
0x14002255e  call    cs:__imp_SetLastError
0x140022565  nop     dword ptr [rax+rax+00h]
0x14002256a  xor     eax, eax
0x14002256c  mov     rbx, [rsp+38h+arg_0]
0x140022571  mov     rbp, [rsp+38h+arg_8]
0x140022576  mov     rsi, [rsp+38h+arg_10]
0x14002257b  mov     rdi, [rsp+38h+arg_18]
0x140022580  add     rsp, 20h
0x140022584  pop     r15
0x140022586  pop     r14
0x140022588  pop     r12
0x14002258a  retn
```
