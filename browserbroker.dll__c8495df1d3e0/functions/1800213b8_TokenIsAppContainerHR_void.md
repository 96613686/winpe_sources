# TokenIsAppContainerHR(void *)

- ea: `0x1800213b8`
- end: `0x180021430`
- name: `?TokenIsAppContainerHR@@YAJPEAX@Z`
- size: `120`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a4fc`

## callees

- `0x1800213b8`
- `0x18002487c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002140e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002140e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800213f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800213f9`

## pseudocode

```c
__int64 __fastcall TokenIsAppContainerHR(HANDLE TokenHandle)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  v2 = 1;
  if ( IsOs_Win8OrGreater() )
  {
    TokenInformation = 0;
    ReturnLength = 4;
    if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      return TokenInformation == 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800213b8  mov     [rsp+arg_0], rbx
0x1800213bd  push    rdi
0x1800213be  sub     rsp, 30h
0x1800213c2  mov     rdi, rcx
0x1800213c5  mov     ebx, 1
0x1800213ca  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x1800213cf  test    al, al
0x1800213d1  jz      short loc_180021423
0x1800213d3  lea     r9d, [rbx+3]; TokenInformationLength
0x1800213d7  mov     [rsp+38h+TokenInformation], 0
0x1800213df  lea     rax, [rsp+38h+arg_10]
0x1800213e4  mov     [rsp+38h+arg_10], r9d
0x1800213e9  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800213ee  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800213f3  lea     edx, [rbx+1Ch]; TokenInformationClass
0x1800213f6  mov     rcx, rdi; TokenHandle
0x1800213f9  call    cs:__imp_GetTokenInformation
0x1800213ff  test    eax, eax
0x180021401  jz      short loc_18002140E
0x180021403  xor     ebx, ebx
0x180021405  cmp     [rsp+38h+TokenInformation], ebx
0x180021409  setz    bl
0x18002140c  jmp     short loc_180021423
0x18002140e  call    cs:__imp_GetLastError
0x180021414  mov     ebx, eax
0x180021416  test    eax, eax
0x180021418  jle     short loc_180021423
0x18002141a  movzx   ebx, ax
0x18002141d  or      ebx, 80070000h
0x180021423  mov     eax, ebx
0x180021425  mov     rbx, [rsp+38h+arg_0]
0x18002142a  add     rsp, 30h
0x18002142e  pop     rdi
0x18002142f  retn
```
