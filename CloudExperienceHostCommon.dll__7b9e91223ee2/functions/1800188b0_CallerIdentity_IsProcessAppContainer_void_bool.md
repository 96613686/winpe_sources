# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x1800188b0`
- end: `0x180018962`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `178`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800cbc78`

## callees

- `0x1800188b0`
- `0x180018968`
- `0x1800cbce4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001894f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001894f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018914`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018914`

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
0x1800188b0  mov     [rsp+arg_0], rbx
0x1800188b5  push    rdi
0x1800188b6  sub     rsp, 30h
0x1800188ba  mov     rdi, rdx
0x1800188bd  mov     byte ptr [rdx], 0
0x1800188c0  lea     rdx, [rsp+38h+TokenHandle]; TokenHandle
0x1800188c5  mov     [rsp+38h+TokenHandle], 0
0x1800188ce  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x1800188d3  mov     ebx, eax
0x1800188d5  test    eax, eax
0x1800188d7  jle     short loc_1800188E2
0x1800188d9  movzx   ebx, ax
0x1800188dc  or      ebx, 80070000h
0x1800188e2  test    ebx, ebx
0x1800188e4  js      short loc_180018937
0x1800188e6  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800188eb  lea     rax, [rsp+38h+arg_10]
0x1800188f0  mov     r9d, 4; TokenInformationLength
0x1800188f6  mov     [rsp+38h+arg_10], 0
0x1800188fe  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180018903  mov     [rsp+38h+TokenInformation], 0
0x18001890b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180018910  lea     edx, [r9+19h]; TokenInformationClass
0x180018914  call    cs:__imp_GetTokenInformation
0x18001891a  test    eax, eax
0x18001891c  jz      short loc_180018922
0x18001891e  xor     ebx, ebx
0x180018920  jmp     short loc_18001892D
0x180018922  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180018927  mov     ebx, eax
0x180018929  test    eax, eax
0x18001892b  js      short loc_180018937
0x18001892d  cmp     [rsp+38h+TokenInformation], 0
0x180018932  setnz   al
0x180018935  mov     [rdi], al
0x180018937  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18001893c  mov     [rsp+38h+TokenHandle], 0
0x180018945  lea     rdx, [rcx-1]
0x180018949  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001894d  ja      short loc_180018955
0x18001894f  call    cs:__imp_CloseHandle
0x180018955  mov     eax, ebx
0x180018957  mov     rbx, [rsp+38h+arg_0]
0x18001895c  add     rsp, 30h
0x180018960  pop     rdi
0x180018961  retn
```
