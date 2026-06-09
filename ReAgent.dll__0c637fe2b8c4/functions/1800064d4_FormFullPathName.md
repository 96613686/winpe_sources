# FormFullPathName

- ea: `0x1800064d4`
- end: `0x180006571`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800067f0`

## callees

- `0x1800064d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006546`
- `KERNEL32!GetLastError` at `0x180006546`
- `KERNEL32!HeapAlloc` at `0x180006516`
- `KERNEL32!HeapAlloc` at `0x180006516`
- `KERNEL32!GetProcessHeap` at `0x180006505`
- `KERNEL32!GetProcessHeap` at `0x180006505`
- `KERNEL32!SetLastError` at `0x180006550`
- `KERNEL32!SetLastError` at `0x180006560`
- `KERNEL32!SetLastError` at `0x180006550`
- `KERNEL32!SetLastError` at `0x180006560`
- `KERNEL32!GetFullPathNameW` at `0x1800064f4`
- `KERNEL32!GetFullPathNameW` at `0x180006531`
- `KERNEL32!GetFullPathNameW` at `0x1800064f4`
- `KERNEL32!GetFullPathNameW` at `0x180006531`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  DWORD LastError; // ebx

  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( FullPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
      v5 = v4;
      if ( v4 )
      {
        LastError = 0;
        if ( !GetFullPathNameW(lpFileName, FullPathNameW, v4, 0) )
          goto LABEL_9;
      }
      else
      {
        LastError = 14;
      }
LABEL_10:
      SetLastError(LastError);
      return v5;
    }
    v5 = 0;
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x1800064d4  push    rbx
0x1800064d6  push    rbp
0x1800064d7  push    rsi
0x1800064d8  push    rdi
0x1800064d9  sub     rsp, 28h
0x1800064dd  mov     rdi, rcx
0x1800064e0  test    rcx, rcx
0x1800064e3  jz      short loc_18000655B
0x1800064e5  xor     eax, eax
0x1800064e7  cmp     ax, [rcx]
0x1800064ea  jz      short loc_18000655B
0x1800064ec  xor     r9d, r9d; lpFilePart
0x1800064ef  xor     r8d, r8d; lpBuffer
0x1800064f2  xor     edx, edx; nBufferLength
0x1800064f4  call    cs:__imp_GetFullPathNameW
0x1800064fa  mov     ebp, eax
0x1800064fc  test    eax, eax
0x1800064fe  jz      short loc_180006544
0x180006500  mov     ebx, ebp
0x180006502  add     rbx, rbx
0x180006505  call    cs:__imp_GetProcessHeap
0x18000650b  mov     r8, rbx; dwBytes
0x18000650e  mov     edx, 8; dwFlags
0x180006513  mov     rcx, rax; hHeap
0x180006516  call    cs:__imp_HeapAlloc
0x18000651c  mov     rsi, rax
0x18000651f  test    rax, rax
0x180006522  jz      short loc_18000653D
0x180006524  xor     r9d, r9d; lpFilePart
0x180006527  mov     r8, rax; lpBuffer
0x18000652a  mov     edx, ebp; nBufferLength
0x18000652c  mov     rcx, rdi; lpFileName
0x18000652f  xor     ebx, ebx
0x180006531  call    cs:__imp_GetFullPathNameW
0x180006537  test    eax, eax
0x180006539  jnz     short loc_18000654E
0x18000653b  jmp     short loc_180006546
0x18000653d  mov     ebx, 0Eh
0x180006542  jmp     short loc_18000654E
0x180006544  xor     esi, esi
0x180006546  call    cs:__imp_GetLastError
0x18000654c  mov     ebx, eax
0x18000654e  mov     ecx, ebx; dwErrCode
0x180006550  call    cs:__imp_SetLastError
0x180006556  mov     rax, rsi
0x180006559  jmp     short loc_180006568
0x18000655b  mov     ecx, 57h ; 'W'; dwErrCode
0x180006560  call    cs:__imp_SetLastError
0x180006566  xor     eax, eax
0x180006568  add     rsp, 28h
0x18000656c  pop     rdi
0x18000656d  pop     rsi
0x18000656e  pop     rbp
0x18000656f  pop     rbx
0x180006570  retn
```
