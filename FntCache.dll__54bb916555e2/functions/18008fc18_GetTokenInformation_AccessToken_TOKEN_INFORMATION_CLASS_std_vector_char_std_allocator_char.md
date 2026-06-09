# GetTokenInformation(AccessToken &,_TOKEN_INFORMATION_CLASS,std::vector<char,std::allocator<char>> &)

- ea: `0x18008fc18`
- end: `0x18008fd30`
- name: `?GetTokenInformation@@YAXAEAVAccessToken@@W4_TOKEN_INFORMATION_CLASS@@AEAV?$vector@DV?$allocator@D@std@@@std@@@Z`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008fb04`

## callees

- `0x1800217ac`
- `0x18002faf0`
- `0x18008fc18`
- `0x18008fd38`
- `0x1800a1558`
- `0x1800ab180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008fc57`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fc4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fcb6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fc4d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008fcb6`

## pseudocode

```c
BOOL __fastcall GetTokenInformation(HANDLE *a1, __int64 a2, __int64 a3)
{
  signed int LastError; // eax
  __int64 v6; // rsi
  void *v7; // rdx
  unsigned __int64 v8; // rcx
  void *v9; // r8
  HANDLE v10; // rcx
  BOOL result; // eax
  size_t v12; // rax
  unsigned int v13; // edx
  size_t v14; // rbx
  int v15; // [rsp+50h] [rbp+8h] BYREF
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  if ( !GetTokenInformation(*a1, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      else
        v13 = LastError;
      Exception::Exception((Exception *)&v15, v13, LastError);
      LogAndThrow<OSException>(&v15, 0x6E656B6F74LL, 328);
    }
  }
  v6 = *(_QWORD *)(a3 + 8);
  v7 = *(void **)a3;
  v8 = v6 - *(_QWORD *)a3;
  if ( TokenInformationLength < v8 )
  {
    v12 = (size_t)v7 + TokenInformationLength;
  }
  else
  {
    if ( TokenInformationLength <= v8 )
      goto LABEL_7;
    if ( (unsigned __int64)TokenInformationLength > *(_QWORD *)(a3 + 16) - (_QWORD)v7 )
    {
      std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(a3, TokenInformationLength);
      goto LABEL_7;
    }
    v14 = TokenInformationLength - v8;
    memset_0(*(void **)(a3 + 8), 0, v14);
    v12 = v14 + v6;
  }
  *(_QWORD *)(a3 + 8) = v12;
LABEL_7:
  v9 = *(void **)a3;
  v10 = *a1;
  ReturnLength = 0;
  result = GetTokenInformation(v10, TokenUser, v9, TokenInformationLength, &ReturnLength);
  if ( !result )
    OSException::ThrowLastError();
  return result;
}

```

## disassembly

```asm
0x18008fc18  mov     rax, rsp
0x18008fc1b  mov     [rax+18h], rbx
0x18008fc1f  mov     [rax+10h], edx
0x18008fc22  push    rsi
0x18008fc23  push    rdi
0x18008fc24  push    r14
0x18008fc26  sub     rsp, 30h
0x18008fc2a  xor     r9d, r9d; TokenInformationLength
0x18008fc2d  mov     dword ptr [rax+10h], 0
0x18008fc34  mov     rdi, r8
0x18008fc37  lea     rax, [rax+10h]
0x18008fc3b  mov     r14, rcx
0x18008fc3e  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008fc43  mov     rcx, [rcx]; TokenHandle
0x18008fc46  xor     r8d, r8d; TokenInformation
0x18008fc49  lea     edx, [r9+1]; TokenInformationClass
0x18008fc4d  call    cs:__imp_GetTokenInformation
0x18008fc53  test    eax, eax
0x18008fc55  jnz     short loc_18008FC62
0x18008fc57  call    cs:__imp_GetLastError
0x18008fc5d  cmp     eax, 7Ah ; 'z'
0x18008fc60  jnz     short loc_18008FCD8
0x18008fc62  mov     rsi, [rdi+8]
0x18008fc66  mov     rdx, [rdi]
0x18008fc69  mov     rcx, rsi
0x18008fc6c  mov     ebx, [rsp+48h+TokenInformationLength]
0x18008fc70  sub     rcx, rdx
0x18008fc73  cmp     rbx, rcx
0x18008fc76  jb      short loc_18008FCCE
0x18008fc78  jbe     short loc_18008FC94
0x18008fc7a  mov     rax, [rdi+10h]
0x18008fc7e  sub     rax, rdx
0x18008fc81  cmp     rbx, rax
0x18008fc84  jbe     loc_18008FD14
0x18008fc8a  mov     edx, ebx
0x18008fc8c  mov     rcx, rdi
0x18008fc8f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18008fc94  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18008fc99  lea     rax, [rsp+48h+arg_18]
0x18008fc9e  mov     r8, [rdi]; TokenInformation
0x18008fca1  mov     edx, 1; TokenInformationClass
0x18008fca6  mov     rcx, [r14]; TokenHandle
0x18008fca9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18008fcae  mov     [rsp+48h+arg_18], 0
0x18008fcb6  call    cs:__imp_GetTokenInformation
0x18008fcbc  test    eax, eax
0x18008fcbe  jz      short loc_18008FD2A
0x18008fcc0  mov     rbx, [rsp+48h+arg_10]
0x18008fcc5  add     rsp, 30h
0x18008fcc9  pop     r14
0x18008fccb  pop     rdi
0x18008fccc  pop     rsi
0x18008fccd  retn
0x18008fcce  lea     rax, [rdx+rbx]
0x18008fcd2  mov     [rdi+8], rax
0x18008fcd6  jmp     short loc_18008FC94
0x18008fcd8  mov     rbx, 6E656B6F74h
0x18008fce2  test    eax, eax
0x18008fce4  jg      short loc_18008FD09
0x18008fce6  mov     edx, eax; int
0x18008fce8  mov     r8d, eax; unsigned int
0x18008fceb  lea     rcx, [rsp+48h+arg_0]; this
0x18008fcf0  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18008fcf5  mov     r8d, 148h
0x18008fcfb  lea     rcx, [rsp+48h+arg_0]
0x18008fd00  mov     rdx, rbx
0x18008fd03  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18008fd09  movzx   edx, ax
0x18008fd0c  or      edx, 80070000h
0x18008fd12  jmp     short loc_18008FCE8
0x18008fd14  sub     rbx, rcx
0x18008fd17  xor     edx, edx; Val
0x18008fd19  mov     r8, rbx; Size
0x18008fd1c  mov     rcx, rsi; void *
0x18008fd1f  call    memset_0
0x18008fd24  lea     rax, [rbx+rsi]
0x18008fd28  jmp     short loc_18008FCD2
0x18008fd2a  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
