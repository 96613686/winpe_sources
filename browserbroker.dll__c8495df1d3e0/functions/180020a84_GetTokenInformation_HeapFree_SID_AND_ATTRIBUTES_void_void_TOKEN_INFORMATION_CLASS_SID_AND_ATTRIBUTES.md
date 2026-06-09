# GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(void *,void *,_TOKEN_INFORMATION_CLASS,_SID_AND_ATTRIBUTES * *)

- ea: `0x180020a84`
- end: `0x180020b4a`
- name: `??$GetTokenInformation_HeapFree@U_SID_AND_ATTRIBUTES@@@@YAJPEAX0W4_TOKEN_INFORMATION_CLASS@@PEAPEAU_SID_AND_ATTRIBUTES@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(HANDLE hHeap, HANDLE TokenHandle, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021100`

## callees

- `0x18000a2dc`
- `0x180020658`
- `0x180020a84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ac3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020ad8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020ad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b20`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020ab9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020b00`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020ab9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020b00`

## pseudocode

```c
__int64 __fastcall GetTokenInformation_HeapFree<_SID_AND_ATTRIBUTES>(
        HANDLE hHeap,
        HANDLE TokenHandle,
        __int64 a3,
        _QWORD *a4)
{
  DWORD LastError; // eax
  void *v8; // rdi
  unsigned int ErrorError; // ebx
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    return (unsigned int)-2147418113;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v8 = HeapAlloc(hHeap, 0, TokenInformationLength);
      if ( v8 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength) )
        {
          *a4 = v8;
          return 0;
        }
        else
        {
          ErrorError = HRESULTFromLastErrorError();
          HeapFree(hHeap, 0, v8);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)HRESULTFromWin32ErrorError(LastError);
    }
  }
  return ErrorError;
}

```

## disassembly

```asm
0x180020a84  mov     [rsp+TokenInformationLength], r8d
0x180020a89  push    rbx
0x180020a8a  push    rbp
0x180020a8b  push    rsi
0x180020a8c  push    rdi
0x180020a8d  sub     rsp, 38h
0x180020a91  mov     rbp, rdx
0x180020a94  mov     [rsp+58h+TokenInformationLength], 0
0x180020a9c  mov     rbx, r9
0x180020a9f  lea     rax, [rsp+58h+TokenInformationLength]
0x180020aa4  xor     r9d, r9d; TokenInformationLength
0x180020aa7  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180020aac  mov     rsi, rcx
0x180020aaf  xor     r8d, r8d; TokenInformation
0x180020ab2  mov     rcx, rbp; TokenHandle
0x180020ab5  lea     edx, [r9+1]; TokenInformationClass
0x180020ab9  call    cs:__imp_GetTokenInformation
0x180020abf  test    eax, eax
0x180020ac1  jnz     short loc_180020B3A
0x180020ac3  call    cs:__imp_GetLastError
0x180020ac9  cmp     eax, 7Ah ; 'z'
0x180020acc  jnz     short loc_180020B2F
0x180020ace  mov     r8d, [rsp+58h+TokenInformationLength]; dwBytes
0x180020ad3  xor     edx, edx; dwFlags
0x180020ad5  mov     rcx, rsi; hHeap
0x180020ad8  call    cs:__imp_HeapAlloc
0x180020ade  mov     rdi, rax
0x180020ae1  test    rax, rax
0x180020ae4  jz      short loc_180020B28
0x180020ae6  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180020aeb  lea     rax, [rsp+58h+TokenInformationLength]
0x180020af0  mov     r8, rdi; TokenInformation
0x180020af3  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180020af8  mov     edx, 1; TokenInformationClass
0x180020afd  mov     rcx, rbp; TokenHandle
0x180020b00  call    cs:__imp_GetTokenInformation
0x180020b06  test    eax, eax
0x180020b08  jz      short loc_180020B11
0x180020b0a  mov     [rbx], rdi
0x180020b0d  xor     ebx, ebx
0x180020b0f  jmp     short loc_180020B3F
0x180020b11  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180020b16  mov     r8, rdi; lpMem
0x180020b19  xor     edx, edx; dwFlags
0x180020b1b  mov     rcx, rsi; hHeap
0x180020b1e  mov     ebx, eax
0x180020b20  call    cs:__imp_HeapFree
0x180020b26  jmp     short loc_180020B3F
0x180020b28  mov     ebx, 8007000Eh
0x180020b2d  jmp     short loc_180020B3F
0x180020b2f  mov     ecx, eax; unsigned int
0x180020b31  call    ?HRESULTFromWin32ErrorError@@YAJK@Z; HRESULTFromWin32ErrorError(ulong)
0x180020b36  mov     ebx, eax
0x180020b38  jmp     short loc_180020B3F
0x180020b3a  mov     ebx, 8000FFFFh
0x180020b3f  mov     eax, ebx
0x180020b41  add     rsp, 38h
0x180020b45  pop     rdi
0x180020b46  pop     rsi
0x180020b47  pop     rbp
0x180020b48  pop     rbx
0x180020b49  retn
```
