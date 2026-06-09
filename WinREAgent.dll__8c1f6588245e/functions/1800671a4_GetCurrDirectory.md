# GetCurrDirectory

- ea: `0x1800671a4`
- end: `0x180067246`
- name: `GetCurrDirectory`
- size: `162`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180065748`

## callees

- `0x1800661c8`
- `0x1800671a4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18006722d`
- `KERNEL32!SetLastError` at `0x18006722d`
- `KERNEL32!HeapFree` at `0x18006720d`
- `KERNEL32!HeapFree` at `0x18006720d`
- `KERNEL32!HeapAlloc` at `0x1800671d9`
- `KERNEL32!HeapAlloc` at `0x1800671d9`
- `KERNEL32!GetProcessHeap` at `0x1800671c8`
- `KERNEL32!GetProcessHeap` at `0x1800671ff`
- `KERNEL32!GetProcessHeap` at `0x1800671c8`
- `KERNEL32!GetProcessHeap` at `0x1800671ff`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800671b7`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800671ee`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800671b7`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800671ee`

## pseudocode

```c
WCHAR *GetCurrDirectory()
{
  DWORD CurrentDirectoryW; // esi
  HANDLE ProcessHeap; // rax
  WCHAR *v2; // rax
  WCHAR *v3; // rbx
  DWORD v4; // edi
  HANDLE v5; // rax

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( CurrentDirectoryW )
  {
    ProcessHeap = GetProcessHeap();
    v2 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * CurrentDirectoryW);
    v3 = v2;
    if ( v2 )
    {
      v4 = 0;
      if ( !GetCurrentDirectoryW(CurrentDirectoryW, v2) )
      {
        v4 = GET_LASTERROR_FORCE();
        v5 = GetProcessHeap();
        if ( HeapFree(v5, 0, v3) )
          v3 = 0;
      }
    }
    else
    {
      v4 = 14;
    }
  }
  else
  {
    v3 = 0;
    v4 = GET_LASTERROR_FORCE();
  }
  SetLastError(v4);
  return v3;
}

```

## disassembly

```asm
0x1800671a4  mov     [rsp+arg_0], rbx
0x1800671a9  mov     [rsp+arg_8], rsi
0x1800671ae  push    rdi
0x1800671af  sub     rsp, 20h
0x1800671b3  xor     edx, edx; lpBuffer
0x1800671b5  xor     ecx, ecx; nBufferLength
0x1800671b7  call    cs:__imp_GetCurrentDirectoryW
0x1800671bd  mov     esi, eax
0x1800671bf  test    eax, eax
0x1800671c1  jz      short loc_180067222
0x1800671c3  mov     ebx, esi
0x1800671c5  add     rbx, rbx
0x1800671c8  call    cs:__imp_GetProcessHeap
0x1800671ce  mov     r8, rbx; dwBytes
0x1800671d1  mov     edx, 8; dwFlags
0x1800671d6  mov     rcx, rax; hHeap
0x1800671d9  call    cs:__imp_HeapAlloc
0x1800671df  mov     rbx, rax
0x1800671e2  test    rax, rax
0x1800671e5  jz      short loc_18006721B
0x1800671e7  mov     rdx, rax; lpBuffer
0x1800671ea  mov     ecx, esi; nBufferLength
0x1800671ec  xor     edi, edi
0x1800671ee  call    cs:__imp_GetCurrentDirectoryW
0x1800671f4  test    eax, eax
0x1800671f6  jnz     short loc_18006722B
0x1800671f8  call    GET_LASTERROR_FORCE
0x1800671fd  mov     edi, eax
0x1800671ff  call    cs:__imp_GetProcessHeap
0x180067205  mov     r8, rbx; lpMem
0x180067208  xor     edx, edx; dwFlags
0x18006720a  mov     rcx, rax; hHeap
0x18006720d  call    cs:__imp_HeapFree
0x180067213  test    eax, eax
0x180067215  jz      short loc_18006722B
0x180067217  xor     ebx, ebx
0x180067219  jmp     short loc_18006722B
0x18006721b  mov     edi, 0Eh
0x180067220  jmp     short loc_18006722B
0x180067222  xor     ebx, ebx
0x180067224  call    GET_LASTERROR_FORCE
0x180067229  mov     edi, eax
0x18006722b  mov     ecx, edi; dwErrCode
0x18006722d  call    cs:__imp_SetLastError
0x180067233  mov     rsi, [rsp+28h+arg_8]
0x180067238  mov     rax, rbx
0x18006723b  mov     rbx, [rsp+28h+arg_0]
0x180067240  add     rsp, 20h
0x180067244  pop     rdi
0x180067245  retn
```
