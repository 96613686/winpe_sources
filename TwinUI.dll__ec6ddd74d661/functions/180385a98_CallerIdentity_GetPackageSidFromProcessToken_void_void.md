# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x180385a98`
- end: `0x180385bfc`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `356`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f2720`
- `0x1803a231c`

## callees

- `0x18002fc18`
- `0x180385a98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180385ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180385ade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180385bd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180385be3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180385bd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180385be3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180385b0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180385b8a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180385b0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180385b8a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180385b75`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180385b75`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180385ac4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180385b47`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180385ac4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180385b47`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180385bad`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180385bad`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  signed int Error; // ebx
  signed int LastError; // eax
  PSID *v7; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  void *v10; // rsi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError == 122 )
    goto LABEL_24;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( Error >= 0 )
  {
LABEL_24:
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v7 )
      return (unsigned int)-2147024882;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( *v7 )
      {
        LengthSid = GetLengthSid(*v7);
        v9 = LocalAlloc(0x40u, LengthSid);
        v10 = v9;
        if ( v9 )
        {
          if ( CopySid(LengthSid, v9, *v7) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v10);
              goto LABEL_20;
            }
          }
          *a2 = v10;
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147023728;
      }
LABEL_20:
      LocalFree(v7);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180385a98  push    rbx
0x180385a9a  push    rsi
0x180385a9b  push    rdi
0x180385a9c  push    r14
0x180385a9e  sub     rsp, 38h
0x180385aa2  xor     r9d, r9d; TokenInformationLength
0x180385aa5  mov     [rsp+58h+TokenInformationLength], 0
0x180385aad  mov     r14, rdx
0x180385ab0  lea     rax, [rsp+58h+TokenInformationLength]
0x180385ab5  xor     r8d, r8d; TokenInformation
0x180385ab8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180385abd  mov     rsi, rcx
0x180385ac0  lea     edx, [r9+1Fh]; TokenInformationClass
0x180385ac4  call    cs:__imp_GetTokenInformation
0x180385acb  nop     dword ptr [rax+rax+00h]
0x180385ad0  test    eax, eax
0x180385ad2  jz      short loc_180385ADE
0x180385ad4  mov     ebx, 8000FFFFh
0x180385ad9  jmp     loc_180385BEF
0x180385ade  call    cs:__imp_GetLastError
0x180385ae5  nop     dword ptr [rax+rax+00h]
0x180385aea  mov     ebx, eax
0x180385aec  cmp     eax, 7Ah ; 'z'
0x180385aef  jz      short loc_180385B06
0x180385af1  test    eax, eax
0x180385af3  jle     short loc_180385AFE
0x180385af5  movzx   ebx, ax
0x180385af8  or      ebx, 80070000h
0x180385afe  test    ebx, ebx
0x180385b00  js      loc_180385BEF
0x180385b06  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x180385b0a  mov     ecx, 40h ; '@'; uFlags
0x180385b0f  call    cs:__imp_LocalAlloc
0x180385b16  nop     dword ptr [rax+rax+00h]
0x180385b1b  mov     rdi, rax
0x180385b1e  test    rax, rax
0x180385b21  jnz     short loc_180385B2D
0x180385b23  mov     ebx, 8007000Eh
0x180385b28  jmp     loc_180385BEF
0x180385b2d  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180385b32  lea     rax, [rsp+58h+TokenInformationLength]
0x180385b37  mov     r8, rdi; TokenInformation
0x180385b3a  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180385b3f  mov     edx, 1Fh; TokenInformationClass
0x180385b44  mov     rcx, rsi; TokenHandle
0x180385b47  call    cs:__imp_GetTokenInformation
0x180385b4e  nop     dword ptr [rax+rax+00h]
0x180385b53  test    eax, eax
0x180385b55  jnz     short loc_180385B66
0x180385b57  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180385b5c  mov     ebx, eax
0x180385b5e  test    eax, eax
0x180385b60  js      loc_180385BEF
0x180385b66  mov     rcx, [rdi]; pSid
0x180385b69  test    rcx, rcx
0x180385b6c  jnz     short loc_180385B75
0x180385b6e  mov     ebx, 80070490h
0x180385b73  jmp     short loc_180385BE0
0x180385b75  call    cs:__imp_GetLengthSid
0x180385b7c  nop     dword ptr [rax+rax+00h]
0x180385b81  mov     edx, eax; uBytes
0x180385b83  mov     ecx, 40h ; '@'; uFlags
0x180385b88  mov     ebx, eax
0x180385b8a  call    cs:__imp_LocalAlloc
0x180385b91  nop     dword ptr [rax+rax+00h]
0x180385b96  mov     rsi, rax
0x180385b99  test    rax, rax
0x180385b9c  jnz     short loc_180385BA5
0x180385b9e  mov     ebx, 8007000Eh
0x180385ba3  jmp     short loc_180385BE0
0x180385ba5  mov     r8, [rdi]; pSourceSid
0x180385ba8  mov     rdx, rsi; pDestinationSid
0x180385bab  mov     ecx, ebx; nDestinationSidLength
0x180385bad  call    cs:__imp_CopySid
0x180385bb4  nop     dword ptr [rax+rax+00h]
0x180385bb9  test    eax, eax
0x180385bbb  jz      short loc_180385BC1
0x180385bbd  xor     ebx, ebx
0x180385bbf  jmp     short loc_180385BCC
0x180385bc1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180385bc6  mov     ebx, eax
0x180385bc8  test    eax, eax
0x180385bca  js      short loc_180385BD1
0x180385bcc  mov     [r14], rsi
0x180385bcf  jmp     short loc_180385BE0
0x180385bd1  mov     rcx, rsi; hMem
0x180385bd4  call    cs:__imp_LocalFree
0x180385bdb  nop     dword ptr [rax+rax+00h]
0x180385be0  mov     rcx, rdi; hMem
0x180385be3  call    cs:__imp_LocalFree
0x180385bea  nop     dword ptr [rax+rax+00h]
0x180385bef  mov     eax, ebx
0x180385bf1  add     rsp, 38h
0x180385bf5  pop     r14
0x180385bf7  pop     rdi
0x180385bf8  pop     rsi
0x180385bf9  pop     rbx
0x180385bfa  retn
```
