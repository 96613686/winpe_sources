# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x1800635f4`
- end: `0x1800636b7`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `195`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180062a44`

## callees

- `0x1800635f4`
- `0x1800636c0`
- `0x1801c9c54`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800636a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800636a9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006364f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006364f`

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
LABEL_6:
      *a2 = TokenInformation != 0;
      goto LABEL_7;
    }
    Error = ResultFromKnownLastError();
    if ( Error >= 0 )
      goto LABEL_6;
  }
LABEL_7:
  v6 = (char *)TokenHandle;
  TokenHandle = 0;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800635f4  mov     [rsp+arg_0], rbx
0x1800635f9  push    rdi
0x1800635fa  sub     rsp, 30h
0x1800635fe  mov     rdi, rdx
0x180063601  mov     byte ptr [rdx], 0
0x180063604  lea     rdx, [rsp+38h+TokenHandle]; TokenHandle
0x180063609  mov     [rsp+38h+TokenHandle], 0
0x180063612  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x180063617  mov     ebx, eax
0x180063619  test    eax, eax
0x18006361b  jg      short loc_180063691
0x18006361d  test    ebx, ebx
0x18006361f  js      short loc_18006366B
0x180063621  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180063626  lea     rax, [rsp+38h+arg_10]
0x18006362b  mov     r9d, 4; TokenInformationLength
0x180063631  mov     [rsp+38h+arg_10], 0
0x180063639  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18006363e  mov     [rsp+38h+TokenInformation], 0
0x180063646  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18006364b  lea     edx, [r9+19h]; TokenInformationClass
0x18006364f  call    cs:__imp_GetTokenInformation
0x180063656  nop     dword ptr [rax+rax+00h]
0x18006365b  test    eax, eax
0x18006365d  jz      short loc_18006369C
0x18006365f  xor     ebx, ebx
0x180063661  cmp     [rsp+38h+TokenInformation], 0
0x180063666  setnz   al
0x180063669  mov     [rdi], al
0x18006366b  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180063670  mov     [rsp+38h+TokenHandle], 0
0x180063679  lea     rdx, [rcx-1]
0x18006367d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180063681  jbe     short loc_1800636A9
0x180063683  mov     eax, ebx
0x180063685  mov     rbx, [rsp+38h+arg_0]
0x18006368a  add     rsp, 30h
0x18006368e  pop     rdi
0x18006368f  retn
0x180063691  movzx   ebx, ax
0x180063694  or      ebx, 80070000h
0x18006369a  jmp     short loc_18006361D
0x18006369c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800636a1  mov     ebx, eax
0x1800636a3  test    eax, eax
0x1800636a5  js      short loc_18006366B
0x1800636a7  jmp     short loc_180063661
0x1800636a9  call    cs:__imp_CloseHandle
0x1800636b0  nop     dword ptr [rax+rax+00h]
0x1800636b5  jmp     short loc_180063683
```
