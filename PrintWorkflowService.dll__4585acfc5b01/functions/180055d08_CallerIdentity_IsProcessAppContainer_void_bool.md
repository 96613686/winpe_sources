# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x180055d08`
- end: `0x180055dba`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `178`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002d414`

## callees

- `0x1800545a0`
- `0x180055d08`
- `0x180055f18`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180055da7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055d6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180055d6c`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsProcessAppContainer(CallerIdentity *this, bool *a2, void **a3)
{
  signed int v4; // eax
  signed int Error; // ebx
  char *v6; // rcx
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  *a2 = 0;
  TokenHandle = 0;
  v4 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(this, &TokenHandle, a3);
  Error = v4;
  if ( v4 > 0 )
    Error = (unsigned __int16)v4 | 0x80070000;
  if ( Error >= 0 )
  {
    ReturnLength = 0;
    TokenInformation = 0;
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_8;
    }
    *a2 = TokenInformation != 0;
  }
LABEL_8:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180055d08  mov     [rsp+arg_0], rbx
0x180055d0d  push    rdi
0x180055d0e  sub     rsp, 30h
0x180055d12  mov     rdi, rdx
0x180055d15  mov     byte ptr [rdx], 0
0x180055d18  lea     rdx, [rsp+38h+TokenHandle]; TokenHandle
0x180055d1d  mov     [rsp+38h+TokenHandle], 0
0x180055d26  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x180055d2b  mov     ebx, eax
0x180055d2d  test    eax, eax
0x180055d2f  jle     short loc_180055D3A
0x180055d31  movzx   ebx, ax
0x180055d34  or      ebx, 80070000h
0x180055d3a  test    ebx, ebx
0x180055d3c  js      short loc_180055D8F
0x180055d3e  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180055d43  lea     rax, [rsp+38h+arg_10]
0x180055d48  mov     r9d, 4; TokenInformationLength
0x180055d4e  mov     [rsp+38h+arg_10], 0
0x180055d56  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180055d5b  mov     [rsp+38h+TokenInformation], 0
0x180055d63  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180055d68  lea     edx, [r9+19h]; TokenInformationClass
0x180055d6c  call    cs:__imp_GetTokenInformation
0x180055d72  test    eax, eax
0x180055d74  jz      short loc_180055D7A
0x180055d76  xor     ebx, ebx
0x180055d78  jmp     short loc_180055D85
0x180055d7a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055d7f  mov     ebx, eax
0x180055d81  test    eax, eax
0x180055d83  js      short loc_180055D8F
0x180055d85  cmp     [rsp+38h+TokenInformation], 0
0x180055d8a  setnz   al
0x180055d8d  mov     [rdi], al
0x180055d8f  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180055d94  mov     [rsp+38h+TokenHandle], 0
0x180055d9d  lea     rdx, [rcx-1]
0x180055da1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180055da5  ja      short loc_180055DAD
0x180055da7  call    cs:__imp_CloseHandle
0x180055dad  mov     eax, ebx
0x180055daf  mov     rbx, [rsp+38h+arg_0]
0x180055db4  add     rsp, 30h
0x180055db8  pop     rdi
0x180055db9  retn
```
