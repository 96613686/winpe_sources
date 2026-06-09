# FormFullPathName

- ea: `0x14007448c`
- end: `0x140074529`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140074694`

## callees

- `0x14007448c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400744bd`
- `KERNEL32!GetProcessHeap` at `0x1400744bd`
- `KERNEL32!GetLastError` at `0x1400744fe`
- `KERNEL32!GetLastError` at `0x1400744fe`
- `KERNEL32!SetLastError` at `0x140074508`
- `KERNEL32!SetLastError` at `0x140074518`
- `KERNEL32!SetLastError` at `0x140074508`
- `KERNEL32!SetLastError` at `0x140074518`
- `KERNEL32!HeapAlloc` at `0x1400744ce`
- `KERNEL32!HeapAlloc` at `0x1400744ce`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400744ac`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400744e9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400744ac`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400744e9`

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
0x14007448c  push    rbx
0x14007448e  push    rbp
0x14007448f  push    rsi
0x140074490  push    rdi
0x140074491  sub     rsp, 28h
0x140074495  mov     rdi, rcx
0x140074498  test    rcx, rcx
0x14007449b  jz      short loc_140074513
0x14007449d  xor     eax, eax
0x14007449f  cmp     ax, [rcx]
0x1400744a2  jz      short loc_140074513
0x1400744a4  xor     r9d, r9d; lpFilePart
0x1400744a7  xor     r8d, r8d; lpBuffer
0x1400744aa  xor     edx, edx; nBufferLength
0x1400744ac  call    cs:__imp_GetFullPathNameW
0x1400744b2  mov     ebp, eax
0x1400744b4  test    eax, eax
0x1400744b6  jz      short loc_1400744FC
0x1400744b8  mov     ebx, ebp
0x1400744ba  add     rbx, rbx
0x1400744bd  call    cs:__imp_GetProcessHeap
0x1400744c3  mov     r8, rbx; dwBytes
0x1400744c6  mov     edx, 8; dwFlags
0x1400744cb  mov     rcx, rax; hHeap
0x1400744ce  call    cs:__imp_HeapAlloc
0x1400744d4  mov     rsi, rax
0x1400744d7  test    rax, rax
0x1400744da  jz      short loc_1400744F5
0x1400744dc  xor     r9d, r9d; lpFilePart
0x1400744df  mov     r8, rax; lpBuffer
0x1400744e2  mov     edx, ebp; nBufferLength
0x1400744e4  mov     rcx, rdi; lpFileName
0x1400744e7  xor     ebx, ebx
0x1400744e9  call    cs:__imp_GetFullPathNameW
0x1400744ef  test    eax, eax
0x1400744f1  jnz     short loc_140074506
0x1400744f3  jmp     short loc_1400744FE
0x1400744f5  mov     ebx, 0Eh
0x1400744fa  jmp     short loc_140074506
0x1400744fc  xor     esi, esi
0x1400744fe  call    cs:__imp_GetLastError
0x140074504  mov     ebx, eax
0x140074506  mov     ecx, ebx; dwErrCode
0x140074508  call    cs:__imp_SetLastError
0x14007450e  mov     rax, rsi
0x140074511  jmp     short loc_140074520
0x140074513  mov     ecx, 57h ; 'W'; dwErrCode
0x140074518  call    cs:__imp_SetLastError
0x14007451e  xor     eax, eax
0x140074520  add     rsp, 28h
0x140074524  pop     rdi
0x140074525  pop     rsi
0x140074526  pop     rbp
0x140074527  pop     rbx
0x140074528  retn
```
