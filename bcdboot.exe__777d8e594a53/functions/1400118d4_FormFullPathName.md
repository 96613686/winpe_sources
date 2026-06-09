# FormFullPathName

- ea: `0x1400118d4`
- end: `0x140011971`
- name: `FormFullPathName`
- size: `157`
- prototype: `WCHAR *__fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011b18`

## callees

- `0x1400118d4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140011950`
- `KERNEL32!SetLastError` at `0x140011960`
- `KERNEL32!SetLastError` at `0x140011950`
- `KERNEL32!SetLastError` at `0x140011960`
- `KERNEL32!GetLastError` at `0x140011946`
- `KERNEL32!GetLastError` at `0x140011946`
- `KERNEL32!HeapAlloc` at `0x140011916`
- `KERNEL32!HeapAlloc` at `0x140011916`
- `KERNEL32!GetProcessHeap` at `0x140011905`
- `KERNEL32!GetProcessHeap` at `0x140011905`
- `KERNEL32!GetFullPathNameW` at `0x1400118f4`
- `KERNEL32!GetFullPathNameW` at `0x140011931`
- `KERNEL32!GetFullPathNameW` at `0x1400118f4`
- `KERNEL32!GetFullPathNameW` at `0x140011931`

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
0x1400118d4  push    rbx
0x1400118d6  push    rbp
0x1400118d7  push    rsi
0x1400118d8  push    rdi
0x1400118d9  sub     rsp, 28h
0x1400118dd  mov     rdi, rcx
0x1400118e0  test    rcx, rcx
0x1400118e3  jz      short loc_14001195B
0x1400118e5  xor     eax, eax
0x1400118e7  cmp     ax, [rcx]
0x1400118ea  jz      short loc_14001195B
0x1400118ec  xor     r9d, r9d; lpFilePart
0x1400118ef  xor     r8d, r8d; lpBuffer
0x1400118f2  xor     edx, edx; nBufferLength
0x1400118f4  call    cs:__imp_GetFullPathNameW
0x1400118fa  mov     ebp, eax
0x1400118fc  test    eax, eax
0x1400118fe  jz      short loc_140011944
0x140011900  mov     ebx, ebp
0x140011902  add     rbx, rbx
0x140011905  call    cs:__imp_GetProcessHeap
0x14001190b  mov     r8, rbx; dwBytes
0x14001190e  mov     edx, 8; dwFlags
0x140011913  mov     rcx, rax; hHeap
0x140011916  call    cs:__imp_HeapAlloc
0x14001191c  mov     rsi, rax
0x14001191f  test    rax, rax
0x140011922  jz      short loc_14001193D
0x140011924  xor     r9d, r9d; lpFilePart
0x140011927  mov     r8, rax; lpBuffer
0x14001192a  mov     edx, ebp; nBufferLength
0x14001192c  mov     rcx, rdi; lpFileName
0x14001192f  xor     ebx, ebx
0x140011931  call    cs:__imp_GetFullPathNameW
0x140011937  test    eax, eax
0x140011939  jnz     short loc_14001194E
0x14001193b  jmp     short loc_140011946
0x14001193d  mov     ebx, 0Eh
0x140011942  jmp     short loc_14001194E
0x140011944  xor     esi, esi
0x140011946  call    cs:__imp_GetLastError
0x14001194c  mov     ebx, eax
0x14001194e  mov     ecx, ebx; dwErrCode
0x140011950  call    cs:__imp_SetLastError
0x140011956  mov     rax, rsi
0x140011959  jmp     short loc_140011968
0x14001195b  mov     ecx, 57h ; 'W'; dwErrCode
0x140011960  call    cs:__imp_SetLastError
0x140011966  xor     eax, eax
0x140011968  add     rsp, 28h
0x14001196c  pop     rdi
0x14001196d  pop     rsi
0x14001196e  pop     rbp
0x14001196f  pop     rbx
0x140011970  retn
```
