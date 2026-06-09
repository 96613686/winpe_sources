# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x1800683ec`
- end: `0x180068515`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180068384`

## callees

- `0x180015fd4`
- `0x1800683ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006842c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006842c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068418`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068489`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068418`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068489`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800684ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800684ad`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800684d9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800684d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800684fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800684fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180068503`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068457`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800684bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068457`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800684bc`

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
0x1800683ec  push    rbx
0x1800683ee  push    rsi
0x1800683ef  push    rdi
0x1800683f0  push    r14
0x1800683f2  sub     rsp, 38h
0x1800683f6  xor     r9d, r9d; TokenInformationLength
0x1800683f9  mov     [rsp+58h+TokenInformationLength], 0
0x180068401  mov     r14, rdx
0x180068404  lea     rax, [rsp+58h+TokenInformationLength]
0x180068409  xor     r8d, r8d; TokenInformation
0x18006840c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180068411  mov     rsi, rcx
0x180068414  lea     edx, [r9+1Fh]; TokenInformationClass
0x180068418  call    cs:__imp_GetTokenInformation
0x18006841e  test    eax, eax
0x180068420  jz      short loc_18006842C
0x180068422  mov     ebx, 8000FFFFh
0x180068427  jmp     loc_180068509
0x18006842c  call    cs:__imp_GetLastError
0x180068432  mov     ebx, eax
0x180068434  cmp     eax, 7Ah ; 'z'
0x180068437  jz      short loc_18006844E
0x180068439  test    eax, eax
0x18006843b  jle     short loc_180068446
0x18006843d  movzx   ebx, ax
0x180068440  or      ebx, 80070000h
0x180068446  test    ebx, ebx
0x180068448  js      loc_180068509
0x18006844e  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x180068452  mov     ecx, 40h ; '@'; uFlags
0x180068457  call    cs:__imp_LocalAlloc
0x18006845d  mov     rdi, rax
0x180068460  test    rax, rax
0x180068463  jnz     short loc_18006846F
0x180068465  mov     ebx, 8007000Eh
0x18006846a  jmp     loc_180068509
0x18006846f  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180068474  lea     rax, [rsp+58h+TokenInformationLength]
0x180068479  mov     r8, rdi; TokenInformation
0x18006847c  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180068481  mov     edx, 1Fh; TokenInformationClass
0x180068486  mov     rcx, rsi; TokenHandle
0x180068489  call    cs:__imp_GetTokenInformation
0x18006848f  test    eax, eax
0x180068491  jnz     short loc_18006849E
0x180068493  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180068498  mov     ebx, eax
0x18006849a  test    eax, eax
0x18006849c  js      short loc_180068509
0x18006849e  mov     rcx, [rdi]; pSid
0x1800684a1  test    rcx, rcx
0x1800684a4  jnz     short loc_1800684AD
0x1800684a6  mov     ebx, 80070490h
0x1800684ab  jmp     short loc_180068500
0x1800684ad  call    cs:__imp_GetLengthSid
0x1800684b3  mov     edx, eax; uBytes
0x1800684b5  mov     ecx, 40h ; '@'; uFlags
0x1800684ba  mov     ebx, eax
0x1800684bc  call    cs:__imp_LocalAlloc
0x1800684c2  mov     rsi, rax
0x1800684c5  test    rax, rax
0x1800684c8  jnz     short loc_1800684D1
0x1800684ca  mov     ebx, 8007000Eh
0x1800684cf  jmp     short loc_180068500
0x1800684d1  mov     r8, [rdi]; pSourceSid
0x1800684d4  mov     rdx, rsi; pDestinationSid
0x1800684d7  mov     ecx, ebx; nDestinationSidLength
0x1800684d9  call    cs:__imp_CopySid
0x1800684df  test    eax, eax
0x1800684e1  jz      short loc_1800684E7
0x1800684e3  xor     ebx, ebx
0x1800684e5  jmp     short loc_1800684F2
0x1800684e7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800684ec  mov     ebx, eax
0x1800684ee  test    eax, eax
0x1800684f0  js      short loc_1800684F7
0x1800684f2  mov     [r14], rsi
0x1800684f5  jmp     short loc_180068500
0x1800684f7  mov     rcx, rsi; hMem
0x1800684fa  call    cs:__imp_LocalFree
0x180068500  mov     rcx, rdi; hMem
0x180068503  call    cs:__imp_LocalFree
0x180068509  mov     eax, ebx
0x18006850b  add     rsp, 38h
0x18006850f  pop     r14
0x180068511  pop     rdi
0x180068512  pop     rsi
0x180068513  pop     rbx
0x180068514  retn
```
