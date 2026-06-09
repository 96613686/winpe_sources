# FormFullPathName

- ea: `0x18005f9f8`
- end: `0x18005fa95`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18005fd24`
- `0x1800612f0`
- `0x1800616e8`
- `0x1800623f4`

## callees

- `0x18005f9f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fa3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fa3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fa29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005fa29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fa6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa74`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fa84`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fa18`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fa55`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fa18`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005fa55`

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
0x18005f9f8  push    rbx
0x18005f9fa  push    rbp
0x18005f9fb  push    rsi
0x18005f9fc  push    rdi
0x18005f9fd  sub     rsp, 28h
0x18005fa01  mov     rdi, rcx
0x18005fa04  test    rcx, rcx
0x18005fa07  jz      short loc_18005FA7F
0x18005fa09  xor     eax, eax
0x18005fa0b  cmp     ax, [rcx]
0x18005fa0e  jz      short loc_18005FA7F
0x18005fa10  xor     r9d, r9d; lpFilePart
0x18005fa13  xor     r8d, r8d; lpBuffer
0x18005fa16  xor     edx, edx; nBufferLength
0x18005fa18  call    cs:__imp_GetFullPathNameW
0x18005fa1e  mov     ebp, eax
0x18005fa20  test    eax, eax
0x18005fa22  jz      short loc_18005FA68
0x18005fa24  mov     ebx, ebp
0x18005fa26  add     rbx, rbx
0x18005fa29  call    cs:__imp_GetProcessHeap
0x18005fa2f  mov     r8, rbx; dwBytes
0x18005fa32  mov     edx, 8; dwFlags
0x18005fa37  mov     rcx, rax; hHeap
0x18005fa3a  call    cs:__imp_HeapAlloc
0x18005fa40  mov     rsi, rax
0x18005fa43  test    rax, rax
0x18005fa46  jz      short loc_18005FA61
0x18005fa48  xor     r9d, r9d; lpFilePart
0x18005fa4b  mov     r8, rax; lpBuffer
0x18005fa4e  mov     edx, ebp; nBufferLength
0x18005fa50  mov     rcx, rdi; lpFileName
0x18005fa53  xor     ebx, ebx
0x18005fa55  call    cs:__imp_GetFullPathNameW
0x18005fa5b  test    eax, eax
0x18005fa5d  jnz     short loc_18005FA72
0x18005fa5f  jmp     short loc_18005FA6A
0x18005fa61  mov     ebx, 0Eh
0x18005fa66  jmp     short loc_18005FA72
0x18005fa68  xor     esi, esi
0x18005fa6a  call    cs:__imp_GetLastError
0x18005fa70  mov     ebx, eax
0x18005fa72  mov     ecx, ebx; dwErrCode
0x18005fa74  call    cs:__imp_SetLastError
0x18005fa7a  mov     rax, rsi
0x18005fa7d  jmp     short loc_18005FA8C
0x18005fa7f  mov     ecx, 57h ; 'W'; dwErrCode
0x18005fa84  call    cs:__imp_SetLastError
0x18005fa8a  xor     eax, eax
0x18005fa8c  add     rsp, 28h
0x18005fa90  pop     rdi
0x18005fa91  pop     rsi
0x18005fa92  pop     rbp
0x18005fa93  pop     rbx
0x18005fa94  retn
```
