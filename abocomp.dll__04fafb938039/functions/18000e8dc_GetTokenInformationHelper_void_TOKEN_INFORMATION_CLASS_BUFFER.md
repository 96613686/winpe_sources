# GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,BUFFER *)

- ea: `0x18000e8dc`
- end: `0x18000e996`
- name: `?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAVBUFFER@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, TOKEN_INFORMATION_CLASS TokenInformationClass, struct BUFFER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b770`

## callees

- `0x18000e8dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e933`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e91e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e981`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e91e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e981`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000e94e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000e94e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e8f8`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e95b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e8f8`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000e95b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000e903`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000e966`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000e903`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000e966`

## pseudocode

```c
signed int __fastcall GetTokenInformationHelper(
        HANDLE TokenHandle,
        TOKEN_INFORMATION_CLASS TokenInformationClass,
        struct BUFFER *a3)
{
  DWORD Size; // ebx
  void *Ptr; // rax
  signed int result; // eax
  DWORD v9; // ebx
  void *v10; // rax
  DWORD ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  ReturnLength = 0;
  Size = BUFFER::QuerySize(a3);
  Ptr = BUFFER::QueryPtr(a3);
  if ( GetTokenInformation(TokenHandle, TokenInformationClass, Ptr, Size, &ReturnLength) )
    return 0;
  if ( GetLastError() == 122 && BUFFER::Resize(a3, ReturnLength) )
  {
    v9 = BUFFER::QuerySize(a3);
    v10 = BUFFER::QueryPtr(a3);
    if ( GetTokenInformation(TokenHandle, TokenInformationClass, v10, v9, &ReturnLength) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e8dc  push    rbx
0x18000e8de  push    rbp
0x18000e8df  push    rsi
0x18000e8e0  push    rdi
0x18000e8e1  sub     rsp, 38h
0x18000e8e5  mov     rbp, rcx
0x18000e8e8  mov     [rsp+58h+arg_18], 0
0x18000e8f0  mov     rcx, r8
0x18000e8f3  mov     rdi, r8
0x18000e8f6  mov     esi, edx
0x18000e8f8  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000e8fe  mov     rcx, rdi
0x18000e901  mov     ebx, eax
0x18000e903  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000e909  lea     rcx, [rsp+58h+arg_18]
0x18000e90e  mov     r9d, ebx; TokenInformationLength
0x18000e911  mov     [rsp+58h+ReturnLength], rcx; ReturnLength
0x18000e916  mov     r8, rax; TokenInformation
0x18000e919  mov     rcx, rbp; TokenHandle
0x18000e91c  mov     edx, esi; TokenInformationClass
0x18000e91e  call    cs:__imp_GetTokenInformation
0x18000e924  test    eax, eax
0x18000e926  jnz     short loc_18000E98B
0x18000e928  call    cs:__imp_GetLastError
0x18000e92e  cmp     eax, 7Ah ; 'z'
0x18000e931  jz      short loc_18000E947
0x18000e933  call    cs:__imp_GetLastError
0x18000e939  test    eax, eax
0x18000e93b  jle     short loc_18000E98D
0x18000e93d  movzx   eax, ax
0x18000e940  or      eax, 80070000h
0x18000e945  jmp     short loc_18000E98D
0x18000e947  mov     edx, [rsp+58h+arg_18]
0x18000e94b  mov     rcx, rdi
0x18000e94e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000e954  test    al, al
0x18000e956  jz      short loc_18000E933
0x18000e958  mov     rcx, rdi
0x18000e95b  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x18000e961  mov     rcx, rdi
0x18000e964  mov     ebx, eax
0x18000e966  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000e96c  lea     rcx, [rsp+58h+arg_18]
0x18000e971  mov     r9d, ebx; TokenInformationLength
0x18000e974  mov     [rsp+58h+ReturnLength], rcx; ReturnLength
0x18000e979  mov     r8, rax; TokenInformation
0x18000e97c  mov     rcx, rbp; TokenHandle
0x18000e97f  mov     edx, esi; TokenInformationClass
0x18000e981  call    cs:__imp_GetTokenInformation
0x18000e987  test    eax, eax
0x18000e989  jz      short loc_18000E933
0x18000e98b  xor     eax, eax
0x18000e98d  add     rsp, 38h
0x18000e991  pop     rdi
0x18000e992  pop     rsi
0x18000e993  pop     rbp
0x18000e994  pop     rbx
0x18000e995  retn
```
