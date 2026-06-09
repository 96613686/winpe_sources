# FormModuleFullPathName

- ea: `0x1801ab8e4`
- end: `0x1801aba37`
- name: `FormModuleFullPathName`
- size: `339`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180197df0`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1801ab8e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ab9b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ab9f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ab9b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ab9f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab9c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab9e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801aba0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab9c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801ab9e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801aba0b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1801ab927`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1801ab927`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ab983`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ab983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ab96e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ab96e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab957`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab9a6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab957`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801ab9a6`

## pseudocode

```c
WCHAR *__fastcall FormModuleFullPathName(HMODULE hModule)
{
  WCHAR *v2; // rdi
  DWORD v3; // esi
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  DWORD LastError; // ebx
  WCHAR Filename[264]; // [rsp+20h] [rbp-248h] BYREF

  v2 = 0;
  memset_0(Filename, 0, 0x208u);
  if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
  {
    if ( Filename[0] )
    {
      v3 = 0;
      FullPathNameW = GetFullPathNameW(Filename, 0, 0, 0);
      if ( FullPathNameW )
      {
        ProcessHeap = GetProcessHeap();
        v6 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
        v2 = v6;
        if ( !v6 )
        {
          LastError = 14;
LABEL_7:
          SetLastError(LastError);
          if ( v2 )
            goto LABEL_13;
          goto LABEL_11;
        }
        LastError = 0;
        if ( GetFullPathNameW(Filename, FullPathNameW, v6, 0) )
          goto LABEL_7;
      }
      LastError = GetLastError();
      goto LABEL_7;
    }
    SetLastError(0x57u);
  }
LABEL_11:
  v3 = GetLastError();
  if ( !v3 )
    v3 = 31;
LABEL_13:
  SetLastError(v3);
  return v2;
}

```

## disassembly

```asm
0x1801ab8e4  push    rbx
0x1801ab8e6  push    rbp
0x1801ab8e7  push    rsi
0x1801ab8e8  push    rdi
0x1801ab8e9  sub     rsp, 248h
0x1801ab8f0  mov     rax, cs:__security_cookie
0x1801ab8f7  xor     rax, rsp
0x1801ab8fa  mov     [rsp+268h+var_38], rax
0x1801ab902  mov     rbx, rcx
0x1801ab905  xor     edx, edx; Val
0x1801ab907  lea     rcx, [rsp+268h+Filename]; void *
0x1801ab90c  mov     r8d, 208h; Size
0x1801ab912  xor     edi, edi
0x1801ab914  call    memset_0
0x1801ab919  mov     r8d, 104h; nSize
0x1801ab91f  lea     rdx, [rsp+268h+Filename]; lpFilename
0x1801ab924  mov     rcx, rbx; hModule
0x1801ab927  call    cs:__imp_GetModuleFileNameW
0x1801ab92e  nop     dword ptr [rax+rax+00h]
0x1801ab933  test    eax, eax
0x1801ab935  jz      loc_1801AB9F1
0x1801ab93b  xor     eax, eax
0x1801ab93d  cmp     ax, [rsp+268h+Filename]
0x1801ab942  jz      loc_1801AB9E0
0x1801ab948  xor     r9d, r9d; lpFilePart
0x1801ab94b  lea     rcx, [rsp+268h+Filename]; lpFileName
0x1801ab950  xor     r8d, r8d; lpBuffer
0x1801ab953  xor     edx, edx; nBufferLength
0x1801ab955  xor     esi, esi
0x1801ab957  call    cs:__imp_GetFullPathNameW
0x1801ab95e  nop     dword ptr [rax+rax+00h]
0x1801ab963  mov     ebp, eax
0x1801ab965  test    eax, eax
0x1801ab967  jz      short loc_1801AB9B6
0x1801ab969  mov     ebx, ebp
0x1801ab96b  add     rbx, rbx
0x1801ab96e  call    cs:__imp_GetProcessHeap
0x1801ab975  nop     dword ptr [rax+rax+00h]
0x1801ab97a  mov     r8, rbx; dwBytes
0x1801ab97d  lea     edx, [rdi+8]; dwFlags
0x1801ab980  mov     rcx, rax; hHeap
0x1801ab983  call    cs:__imp_HeapAlloc
0x1801ab98a  nop     dword ptr [rax+rax+00h]
0x1801ab98f  mov     rdi, rax
0x1801ab992  test    rax, rax
0x1801ab995  jz      short loc_1801AB9D9
0x1801ab997  xor     r9d, r9d; lpFilePart
0x1801ab99a  lea     rcx, [rsp+268h+Filename]; lpFileName
0x1801ab99f  mov     r8, rax; lpBuffer
0x1801ab9a2  mov     edx, ebp; nBufferLength
0x1801ab9a4  xor     ebx, ebx
0x1801ab9a6  call    cs:__imp_GetFullPathNameW
0x1801ab9ad  nop     dword ptr [rax+rax+00h]
0x1801ab9b2  test    eax, eax
0x1801ab9b4  jnz     short loc_1801AB9C4
0x1801ab9b6  call    cs:__imp_GetLastError
0x1801ab9bd  nop     dword ptr [rax+rax+00h]
0x1801ab9c2  mov     ebx, eax
0x1801ab9c4  mov     ecx, ebx; dwErrCode
0x1801ab9c6  call    cs:__imp_SetLastError
0x1801ab9cd  nop     dword ptr [rax+rax+00h]
0x1801ab9d2  test    rdi, rdi
0x1801ab9d5  jnz     short loc_1801ABA09
0x1801ab9d7  jmp     short loc_1801AB9F1
0x1801ab9d9  mov     ebx, 0Eh
0x1801ab9de  jmp     short loc_1801AB9C4
0x1801ab9e0  mov     ecx, 57h ; 'W'; dwErrCode
0x1801ab9e5  call    cs:__imp_SetLastError
0x1801ab9ec  nop     dword ptr [rax+rax+00h]
0x1801ab9f1  call    cs:__imp_GetLastError
0x1801ab9f8  nop     dword ptr [rax+rax+00h]
0x1801ab9fd  mov     esi, eax
0x1801ab9ff  mov     eax, 1Fh
0x1801aba04  test    esi, esi
0x1801aba06  cmovz   esi, eax
0x1801aba09  mov     ecx, esi; dwErrCode
0x1801aba0b  call    cs:__imp_SetLastError
0x1801aba12  nop     dword ptr [rax+rax+00h]
0x1801aba17  mov     rax, rdi
0x1801aba1a  mov     rcx, [rsp+268h+var_38]
0x1801aba22  xor     rcx, rsp; StackCookie
0x1801aba25  call    __security_check_cookie
0x1801aba2a  add     rsp, 248h
0x1801aba31  pop     rdi
0x1801aba32  pop     rsi
0x1801aba33  pop     rbp
0x1801aba34  pop     rbx
0x1801aba35  retn
```
