# CCabDecompressor::CabDecompressorFileRead(__int64,void *,uint)

- ea: `0x14002f680`
- end: `0x14002f7f2`
- name: `?CabDecompressorFileRead@CCabDecompressor@@CAI_JPEAXI@Z`
- size: `370`
- prototype: `__int64 __fastcall(INT_PTR hf, _BYTE *pv, UINT cb)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400154b4`
- `0x14002f680`
- `0x140045dc0`
- `0x14004d140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f796`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14002f76b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14002f76b`

## string_xrefs

- `0x14002f6be`: `CabDecompressorFileRead - invalid buffer`
- `0x14002f7b6`: `CabDecompressorFileRead - ReadFile`
- `0x14002f706`: `CabDecompressorFileRead - invalid offset`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::CabDecompressorFileRead(INT_PTR hf, _BYTE *pv, UINT cb)
{
  bool v3; // zf
  _BYTE *v5; // rsi
  __int64 v7; // r14
  UINT v8; // ebx
  UINT v9; // ecx
  UINT v10; // ebx
  __int64 v11; // rcx
  signed int LastError; // eax
  signed int v13; // ecx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-48h]
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF

  v3 = *(_DWORD *)(hf + 16) == 0;
  v5 = pv;
  NumberOfBytesRead = -1;
  if ( v3 )
  {
    v7 = *(_QWORD *)(hf + 8);
    if ( !v7 )
    {
      WUTrace(0, 0, 32, 3, 0, L"CabDecompressorFileRead - invalid buffer");
      return NumberOfBytesRead;
    }
    v9 = *(_DWORD *)(hf + 20);
    v10 = *(_DWORD *)(v7 + 20);
    if ( v9 + cb >= v10 )
    {
      if ( v9 > v10 )
      {
        WUTrace(0, 0, 32, 3, 0, L"CabDecompressorFileRead - invalid offset");
        v8 = -1;
      }
      else
      {
        v8 = v10 - v9;
      }
    }
    else
    {
      v8 = cb;
    }
    NumberOfBytesRead = v8;
    if ( v8 != -1 && v8 == cb )
    {
      memmove(v5, (const void *)(*(_QWORD *)(v7 + 8) + *(unsigned int *)(hf + 20)), v8);
      *(_DWORD *)(hf + 20) += v8;
    }
  }
  else if ( ReadFile(*(HANDLE *)(hf + 8), pv, cb, &NumberOfBytesRead, 0) )
  {
    if ( !*(_DWORD *)(hf + 24) )
      return NumberOfBytesRead;
    v8 = NumberOfBytesRead;
    if ( NumberOfBytesRead )
    {
      v11 = NumberOfBytesRead;
      do
      {
        *v5 = ~*v5;
        ++v5;
        --v11;
      }
      while ( v11 );
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v13 = LastError;
    if ( v13 >= 0 )
      v13 = -2147418113;
    LODWORD(lpOverlapped) = v13;
    WUTrace(0, 0, 32, 3, lpOverlapped, L"CabDecompressorFileRead - ReadFile");
    return (UINT)-1;
  }
  return v8;
}

```

## disassembly

```asm
0x14002f680  push    rbx
0x14002f682  push    rbp
0x14002f683  push    rsi
0x14002f684  push    rdi
0x14002f685  push    r14
0x14002f687  sub     rsp, 40h
0x14002f68b  mov     rax, cs:__security_cookie
0x14002f692  xor     rax, rsp
0x14002f695  mov     [rsp+68h+var_30], rax
0x14002f69a  cmp     dword ptr [rcx+10h], 0
0x14002f69e  mov     ebp, r8d
0x14002f6a1  mov     rsi, rdx
0x14002f6a4  mov     [rsp+68h+NumberOfBytesRead], 0FFFFFFFFh
0x14002f6ac  mov     rdi, rcx
0x14002f6af  jnz     loc_14002F759
0x14002f6b5  mov     r14, [rcx+8]
0x14002f6b9  test    r14, r14
0x14002f6bc  jnz     short loc_14002F6E9
0x14002f6be  lea     rax, aCabdecompresso_0; "CabDecompressorFileRead - invalid buffe"...
0x14002f6c5  xor     edx, edx
0x14002f6c7  mov     [rsp+68h+var_40], rax
0x14002f6cc  lea     r9d, [r14+3]
0x14002f6d0  xor     ecx, ecx
0x14002f6d2  mov     [rsp+68h+lpOverlapped], r14
0x14002f6d7  lea     r8d, [r14+20h]
0x14002f6db  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f6e0  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x14002f6e4  jmp     loc_14002F7D8
0x14002f6e9  mov     ecx, [rcx+14h]
0x14002f6ec  mov     ebx, [r14+14h]
0x14002f6f0  lea     eax, [rcx+r8]
0x14002f6f4  cmp     eax, ebx
0x14002f6f6  jnb     short loc_14002F6FC
0x14002f6f8  mov     ebx, ebp
0x14002f6fa  jmp     short loc_14002F72D
0x14002f6fc  cmp     ecx, ebx
0x14002f6fe  ja      short loc_14002F704
0x14002f700  sub     ebx, ecx
0x14002f702  jmp     short loc_14002F72D
0x14002f704  xor     edx, edx
0x14002f706  lea     rax, aCabdecompresso_2; "CabDecompressorFileRead - invalid offse"...
0x14002f70d  mov     [rsp+68h+var_40], rax
0x14002f712  xor     ecx, ecx
0x14002f714  mov     [rsp+68h+lpOverlapped], 0
0x14002f71d  lea     r9d, [rdx+3]
0x14002f721  lea     r8d, [rdx+20h]
0x14002f725  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f72a  or      ebx, 0FFFFFFFFh
0x14002f72d  mov     [rsp+68h+NumberOfBytesRead], ebx
0x14002f731  cmp     ebx, 0FFFFFFFFh
0x14002f734  jz      loc_14002F7D8
0x14002f73a  cmp     ebx, ebp
0x14002f73c  jnz     loc_14002F7D8
0x14002f742  mov     edx, [rdi+14h]
0x14002f745  mov     rcx, rsi; void *
0x14002f748  add     rdx, [r14+8]; Src
0x14002f74c  mov     r8d, ebx; Size
0x14002f74f  call    memmove
0x14002f754  add     [rdi+14h], ebx
0x14002f757  jmp     short loc_14002F7D8
0x14002f759  mov     rcx, [rcx+8]; hFile
0x14002f75d  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14002f762  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14002f76b  call    cs:__imp_ReadFile
0x14002f771  test    eax, eax
0x14002f773  jz      short loc_14002F796
0x14002f775  cmp     dword ptr [rdi+18h], 0
0x14002f779  jz      loc_14002F6E0
0x14002f77f  mov     ebx, [rsp+68h+NumberOfBytesRead]
0x14002f783  test    ebx, ebx
0x14002f785  jz      short loc_14002F7D8
0x14002f787  mov     ecx, ebx
0x14002f789  not     byte ptr [rsi]
0x14002f78b  inc     rsi
0x14002f78e  sub     rcx, 1
0x14002f792  jnz     short loc_14002F789
0x14002f794  jmp     short loc_14002F7D8
0x14002f796  call    cs:__imp_GetLastError
0x14002f79c  movzx   ecx, ax
0x14002f79f  or      ecx, 80070000h
0x14002f7a5  test    eax, eax
0x14002f7a7  cmovle  ecx, eax
0x14002f7aa  mov     eax, 8000FFFFh
0x14002f7af  test    ecx, ecx
0x14002f7b1  cmovns  ecx, eax
0x14002f7b4  xor     edx, edx
0x14002f7b6  lea     rax, aCabdecompresso; "CabDecompressorFileRead - ReadFile"
0x14002f7bd  mov     [rsp+68h+var_40], rax
0x14002f7c2  mov     dword ptr [rsp+68h+lpOverlapped], ecx
0x14002f7c6  xor     ecx, ecx
0x14002f7c8  lea     r9d, [rdx+3]
0x14002f7cc  lea     r8d, [rdx+20h]
0x14002f7d0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002f7d5  or      ebx, 0FFFFFFFFh
0x14002f7d8  mov     eax, ebx
0x14002f7da  mov     rcx, [rsp+68h+var_30]
0x14002f7df  xor     rcx, rsp; StackCookie
0x14002f7e2  call    __security_check_cookie
0x14002f7e7  add     rsp, 40h
0x14002f7eb  pop     r14
0x14002f7ed  pop     rdi
0x14002f7ee  pop     rsi
0x14002f7ef  pop     rbp
0x14002f7f0  pop     rbx
0x14002f7f1  retn
```
