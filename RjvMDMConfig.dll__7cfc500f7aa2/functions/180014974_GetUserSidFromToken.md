# GetUserSidFromToken

- ea: `0x180014974`
- end: `0x180014ab4`
- name: `GetUserSidFromToken`
- size: `320`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800147e8`
- `0x180014abc`

## callees

- `0x180014974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800149ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800149f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014a52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800149f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014a52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800149a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014a2d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800149a3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180014a2d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014a40`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180014a40`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014a6e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180014a6e`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  PSID *v3; // rsi
  void *v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  v5 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v6 = -2147418113;
    goto LABEL_12;
  }
  if ( GetLastError() == 122 )
  {
    v3 = (PSID *)LocalAlloc(0, TokenInformationLength);
    if ( v3 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_4;
      LengthSid = GetLengthSid(*v3);
      v9 = LocalAlloc(0, LengthSid);
      v5 = v9;
      if ( v9 )
      {
        if ( CopySid(LengthSid, v9, *v3) )
        {
          v6 = 0;
          *a2 = v5;
          v5 = 0;
          goto LABEL_12;
        }
        goto LABEL_4;
      }
    }
    v6 = -2147024882;
    goto LABEL_12;
  }
LABEL_4:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  LocalFree(v5);
  LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x180014974  push    rbx
0x180014976  push    rsi
0x180014977  push    rdi
0x180014978  push    r14
0x18001497a  sub     rsp, 38h
0x18001497e  mov     r14, rdx
0x180014981  mov     [rsp+58h+TokenInformationLength], 0
0x180014989  lea     rax, [rsp+58h+TokenInformationLength]
0x18001498e  xor     esi, esi
0x180014990  xor     r9d, r9d; TokenInformationLength
0x180014993  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180014998  xor     r8d, r8d; TokenInformation
0x18001499b  mov     rbx, rcx
0x18001499e  xor     edi, edi
0x1800149a0  lea     edx, [rsi+1]; TokenInformationClass
0x1800149a3  call    cs:__imp_GetTokenInformation
0x1800149aa  nop     dword ptr [rax+rax+00h]
0x1800149af  test    eax, eax
0x1800149b1  jz      short loc_1800149BD
0x1800149b3  mov     ebx, 8000FFFFh
0x1800149b8  jmp     loc_180014A89
0x1800149bd  call    cs:__imp_GetLastError
0x1800149c4  nop     dword ptr [rax+rax+00h]
0x1800149c9  cmp     eax, 7Ah ; 'z'
0x1800149cc  jz      short loc_1800149F2
0x1800149ce  call    cs:__imp_GetLastError
0x1800149d5  nop     dword ptr [rax+rax+00h]
0x1800149da  mov     ebx, eax
0x1800149dc  test    eax, eax
0x1800149de  jle     loc_180014A89
0x1800149e4  movzx   ebx, ax
0x1800149e7  or      ebx, 80070000h
0x1800149ed  jmp     loc_180014A89
0x1800149f2  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x1800149f6  xor     ecx, ecx; uFlags
0x1800149f8  call    cs:__imp_LocalAlloc
0x1800149ff  nop     dword ptr [rax+rax+00h]
0x180014a04  mov     rsi, rax
0x180014a07  test    rax, rax
0x180014a0a  jnz     short loc_180014A13
0x180014a0c  mov     ebx, 8007000Eh
0x180014a11  jmp     short loc_180014A89
0x180014a13  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180014a18  lea     rax, [rsp+58h+TokenInformationLength]
0x180014a1d  mov     r8, rsi; TokenInformation
0x180014a20  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180014a25  mov     edx, 1; TokenInformationClass
0x180014a2a  mov     rcx, rbx; TokenHandle
0x180014a2d  call    cs:__imp_GetTokenInformation
0x180014a34  nop     dword ptr [rax+rax+00h]
0x180014a39  test    eax, eax
0x180014a3b  jz      short loc_1800149CE
0x180014a3d  mov     rcx, [rsi]; pSid
0x180014a40  call    cs:__imp_GetLengthSid
0x180014a47  nop     dword ptr [rax+rax+00h]
0x180014a4c  mov     edx, eax; uBytes
0x180014a4e  xor     ecx, ecx; uFlags
0x180014a50  mov     ebx, eax
0x180014a52  call    cs:__imp_LocalAlloc
0x180014a59  nop     dword ptr [rax+rax+00h]
0x180014a5e  mov     rdi, rax
0x180014a61  test    rax, rax
0x180014a64  jz      short loc_180014A0C
0x180014a66  mov     r8, [rsi]; pSourceSid
0x180014a69  mov     rdx, rax; pDestinationSid
0x180014a6c  mov     ecx, ebx; nDestinationSidLength
0x180014a6e  call    cs:__imp_CopySid
0x180014a75  nop     dword ptr [rax+rax+00h]
0x180014a7a  test    eax, eax
0x180014a7c  jz      loc_1800149CE
0x180014a82  xor     ebx, ebx
0x180014a84  mov     [r14], rdi
0x180014a87  xor     edi, edi
0x180014a89  mov     rcx, rdi; hMem
0x180014a8c  call    cs:__imp_LocalFree
0x180014a93  nop     dword ptr [rax+rax+00h]
0x180014a98  mov     rcx, rsi; hMem
0x180014a9b  call    cs:__imp_LocalFree
0x180014aa2  nop     dword ptr [rax+rax+00h]
0x180014aa7  mov     eax, ebx
0x180014aa9  add     rsp, 38h
0x180014aad  pop     r14
0x180014aaf  pop     rdi
0x180014ab0  pop     rsi
0x180014ab1  pop     rbx
0x180014ab2  retn
```
