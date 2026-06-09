# FormFullPathName

- ea: `0x1400222e8`
- end: `0x1400223d7`
- name: `FormFullPathName`
- size: `239`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPWSTR *lpFilePart)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400223e0`
- `0x140022c14`
- `0x140026104`
- `0x140026684`
- `0x14002840c`

## callees

- `0x1400222e8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140022351`
- `KERNEL32!HeapAlloc` at `0x140022351`
- `KERNEL32!GetProcessHeap` at `0x14002233c`
- `KERNEL32!GetProcessHeap` at `0x14002233c`
- `KERNEL32!GetLastError` at `0x140022380`
- `KERNEL32!GetLastError` at `0x140022380`
- `KERNEL32!GetFullPathNameW` at `0x140022325`
- `KERNEL32!GetFullPathNameW` at `0x140022370`
- `KERNEL32!GetFullPathNameW` at `0x140022325`
- `KERNEL32!GetFullPathNameW` at `0x140022370`
- `KERNEL32!SetLastError` at `0x140022390`
- `KERNEL32!SetLastError` at `0x1400223ad`
- `KERNEL32!SetLastError` at `0x140022390`
- `KERNEL32!SetLastError` at `0x1400223ad`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName, LPWSTR *lpFilePart)
{
  DWORD LastError; // edi
  WCHAR *v5; // rbx
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax

  LastError = 0;
  v5 = 0;
  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( !FullPathNameW )
      goto LABEL_6;
    ProcessHeap = GetProcessHeap();
    v8 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
    v5 = v8;
    if ( !v8 )
    {
      LastError = 14;
      goto LABEL_7;
    }
    if ( !GetFullPathNameW(lpFileName, FullPathNameW, v8, lpFilePart) )
LABEL_6:
      LastError = GetLastError();
LABEL_7:
    SetLastError(LastError);
    return v5;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x1400222e8  mov     rax, rsp
0x1400222eb  mov     [rax+8], rbx
0x1400222ef  mov     [rax+10h], rbp
0x1400222f3  mov     [rax+18h], rsi
0x1400222f7  mov     [rax+20h], rdi
0x1400222fb  push    r14
0x1400222fd  sub     rsp, 20h
0x140022301  xor     edi, edi
0x140022303  mov     r14, rdx
0x140022306  mov     rsi, rcx
0x140022309  mov     ebx, edi
0x14002230b  test    rcx, rcx
0x14002230e  jz      loc_1400223A8
0x140022314  cmp     di, [rcx]
0x140022317  jz      loc_1400223A8
0x14002231d  xor     r9d, r9d; lpFilePart
0x140022320  xor     r8d, r8d; lpBuffer
0x140022323  xor     edx, edx; nBufferLength
0x140022325  call    cs:__imp_GetFullPathNameW
0x14002232c  nop     dword ptr [rax+rax+00h]
0x140022331  mov     ebp, eax
0x140022333  test    eax, eax
0x140022335  jz      short loc_140022380
0x140022337  mov     ebx, ebp
0x140022339  add     rbx, rbx
0x14002233c  call    cs:__imp_GetProcessHeap
0x140022343  nop     dword ptr [rax+rax+00h]
0x140022348  mov     r8, rbx; dwBytes
0x14002234b  lea     edx, [rdi+8]; dwFlags
0x14002234e  mov     rcx, rax; hHeap
0x140022351  call    cs:__imp_HeapAlloc
0x140022358  nop     dword ptr [rax+rax+00h]
0x14002235d  mov     rbx, rax
0x140022360  test    rax, rax
0x140022363  jz      short loc_1400223A1
0x140022365  mov     r9, r14; lpFilePart
0x140022368  mov     r8, rax; lpBuffer
0x14002236b  mov     edx, ebp; nBufferLength
0x14002236d  mov     rcx, rsi; lpFileName
0x140022370  call    cs:__imp_GetFullPathNameW
0x140022377  nop     dword ptr [rax+rax+00h]
0x14002237c  test    eax, eax
0x14002237e  jnz     short loc_14002238E
0x140022380  call    cs:__imp_GetLastError
0x140022387  nop     dword ptr [rax+rax+00h]
0x14002238c  mov     edi, eax
0x14002238e  mov     ecx, edi; dwErrCode
0x140022390  call    cs:__imp_SetLastError
0x140022397  nop     dword ptr [rax+rax+00h]
0x14002239c  mov     rax, rbx
0x14002239f  jmp     short loc_1400223BB
0x1400223a1  mov     edi, 0Eh
0x1400223a6  jmp     short loc_14002238E
0x1400223a8  mov     ecx, 57h ; 'W'; dwErrCode
0x1400223ad  call    cs:__imp_SetLastError
0x1400223b4  nop     dword ptr [rax+rax+00h]
0x1400223b9  xor     eax, eax
0x1400223bb  mov     rbx, [rsp+28h+arg_0]
0x1400223c0  mov     rbp, [rsp+28h+arg_8]
0x1400223c5  mov     rsi, [rsp+28h+arg_10]
0x1400223ca  mov     rdi, [rsp+28h+arg_18]
0x1400223cf  add     rsp, 20h
0x1400223d3  pop     r14
0x1400223d5  retn
```
