# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x14001d4b0`
- end: `0x14001d562`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `178`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001d730`

## callees

- `0x140013600`
- `0x14001d4b0`
- `0x14001d6c0`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14001d514`
- `ADVAPI32!GetTokenInformation` at `0x14001d514`
- `KERNEL32!CloseHandle` at `0x14001d54f`
- `KERNEL32!CloseHandle` at `0x14001d54f`

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
0x14001d4b0  mov     [rsp+arg_0], rbx
0x14001d4b5  push    rdi
0x14001d4b6  sub     rsp, 30h
0x14001d4ba  mov     rdi, rdx
0x14001d4bd  mov     byte ptr [rdx], 0
0x14001d4c0  lea     rdx, [rsp+38h+TokenHandle]; TokenHandle
0x14001d4c5  mov     [rsp+38h+TokenHandle], 0
0x14001d4ce  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x14001d4d3  mov     ebx, eax
0x14001d4d5  test    eax, eax
0x14001d4d7  jle     short loc_14001D4E2
0x14001d4d9  movzx   ebx, ax
0x14001d4dc  or      ebx, 80070000h
0x14001d4e2  test    ebx, ebx
0x14001d4e4  js      short loc_14001D537
0x14001d4e6  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x14001d4eb  lea     rax, [rsp+38h+arg_10]
0x14001d4f0  mov     r9d, 4; TokenInformationLength
0x14001d4f6  mov     [rsp+38h+arg_10], 0
0x14001d4fe  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x14001d503  mov     [rsp+38h+TokenInformation], 0
0x14001d50b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14001d510  lea     edx, [r9+19h]; TokenInformationClass
0x14001d514  call    cs:__imp_GetTokenInformation
0x14001d51a  test    eax, eax
0x14001d51c  jz      short loc_14001D522
0x14001d51e  xor     ebx, ebx
0x14001d520  jmp     short loc_14001D52D
0x14001d522  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001d527  mov     ebx, eax
0x14001d529  test    eax, eax
0x14001d52b  js      short loc_14001D537
0x14001d52d  cmp     [rsp+38h+TokenInformation], 0
0x14001d532  setnz   al
0x14001d535  mov     [rdi], al
0x14001d537  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x14001d53c  mov     [rsp+38h+TokenHandle], 0
0x14001d545  lea     rdx, [rcx-1]
0x14001d549  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14001d54d  ja      short loc_14001D555
0x14001d54f  call    cs:__imp_CloseHandle
0x14001d555  mov     eax, ebx
0x14001d557  mov     rbx, [rsp+38h+arg_0]
0x14001d55c  add     rsp, 30h
0x14001d560  pop     rdi
0x14001d561  retn
```
