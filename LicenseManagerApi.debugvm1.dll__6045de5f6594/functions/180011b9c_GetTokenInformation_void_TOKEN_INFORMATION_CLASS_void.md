# GetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x180011b9c`
- end: `0x180011c54`
- name: `?GetTokenInformation@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f060`

## callees

- `0x180011b9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011bf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011bf7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011c05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011bdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180011bdc`

## pseudocode

```c
__int64 __fastcall GetTokenInformation(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS a2, void **a3)
{
  DWORD v3; // r9d
  DWORD LastError; // ebx
  void *v5; // rsi
  int v6; // edi
  bool v9; // cc
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  LastError = 0;
  v5 = 0;
  ReturnLength = 0;
  v6 = 0;
  while ( 1 )
  {
    v9 = (int)LastError <= 0;
    if ( LastError )
      break;
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, v3, &ReturnLength) )
    {
      *a3 = v5;
      return LastError;
    }
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v10 = ReturnLength;
      ProcessHeap = GetProcessHeap();
      v5 = HeapAlloc(ProcessHeap, 0, v10);
      if ( v5 )
        LastError = 0;
      else
        LastError = GetLastError();
    }
    if ( (unsigned int)++v6 >= 2 )
    {
      v9 = (int)LastError <= 0;
      break;
    }
    v3 = ReturnLength;
  }
  if ( !v9 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x180011b9c  mov     rax, rsp
0x180011b9f  mov     [rax+8], rbx
0x180011ba3  mov     [rax+18h], rbp
0x180011ba7  mov     [rax+10h], edx
0x180011baa  push    rsi
0x180011bab  push    rdi
0x180011bac  push    r14
0x180011bae  sub     rsp, 30h
0x180011bb2  xor     r9d, r9d; TokenInformationLength
0x180011bb5  xor     ebx, ebx
0x180011bb7  xor     esi, esi
0x180011bb9  mov     [rax+10h], r9d
0x180011bbd  xor     edi, edi
0x180011bbf  mov     r14, r8
0x180011bc2  mov     rbp, rcx
0x180011bc5  test    ebx, ebx
0x180011bc7  jnz     short loc_180011C34
0x180011bc9  lea     rax, [rsp+48h+arg_8]
0x180011bce  mov     r8, rsi; TokenInformation
0x180011bd1  lea     edx, [rbx+1]; TokenInformationClass
0x180011bd4  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180011bd9  mov     rcx, rbp; TokenHandle
0x180011bdc  call    cs:__imp_GetTokenInformation
0x180011be2  test    eax, eax
0x180011be4  jnz     short loc_180011C2D
0x180011be6  call    cs:__imp_GetLastError
0x180011bec  mov     ebx, eax
0x180011bee  cmp     eax, 7Ah ; 'z'
0x180011bf1  jnz     short loc_180011C1F
0x180011bf3  mov     ebx, [rsp+48h+arg_8]
0x180011bf7  call    cs:__imp_GetProcessHeap
0x180011bfd  mov     r8d, ebx; dwBytes
0x180011c00  xor     edx, edx; dwFlags
0x180011c02  mov     rcx, rax; hHeap
0x180011c05  call    cs:__imp_HeapAlloc
0x180011c0b  mov     rsi, rax
0x180011c0e  test    rax, rax
0x180011c11  jz      short loc_180011C17
0x180011c13  xor     ebx, ebx
0x180011c15  jmp     short loc_180011C1F
0x180011c17  call    cs:__imp_GetLastError
0x180011c1d  mov     ebx, eax
0x180011c1f  inc     edi
0x180011c21  cmp     edi, 2
0x180011c24  jnb     short loc_180011C32
0x180011c26  mov     r9d, [rsp+48h+arg_8]
0x180011c2b  jmp     short loc_180011BC5
0x180011c2d  mov     [r14], rsi
0x180011c30  jmp     short loc_180011C3F
0x180011c32  test    ebx, ebx
0x180011c34  jle     short loc_180011C3F
0x180011c36  movzx   ebx, bx
0x180011c39  or      ebx, 80070000h
0x180011c3f  mov     rbp, [rsp+48h+arg_10]
0x180011c44  mov     eax, ebx
0x180011c46  mov     rbx, [rsp+48h+arg_0]
0x180011c4b  add     rsp, 30h
0x180011c4f  pop     r14
0x180011c51  pop     rdi
0x180011c52  pop     rsi
0x180011c53  retn
```
