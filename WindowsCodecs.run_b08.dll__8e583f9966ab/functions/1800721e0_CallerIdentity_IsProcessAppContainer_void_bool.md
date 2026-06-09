# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x1800721e0`
- end: `0x180072296`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, void *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180071f0c`

## callees

- `0x1800721e0`
- `0x18007229c`
- `0x1801c6210`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007228e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007228e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007223b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007223b`

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
0x1800721e0  mov     [rsp+arg_0], rbx
0x1800721e5  push    rdi
0x1800721e6  sub     rsp, 30h
0x1800721ea  mov     rdi, rdx
0x1800721ed  mov     byte ptr [rdx], 0
0x1800721f0  lea     rdx, [rsp+38h+TokenHandle]; TokenHandle
0x1800721f5  mov     [rsp+38h+TokenHandle], 0
0x1800721fe  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x180072203  mov     ebx, eax
0x180072205  test    eax, eax
0x180072207  jg      short loc_180072276
0x180072209  test    ebx, ebx
0x18007220b  js      short loc_180072251
0x18007220d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180072212  lea     rax, [rsp+38h+arg_10]
0x180072217  mov     r9d, 4; TokenInformationLength
0x18007221d  mov     [rsp+38h+arg_10], 0
0x180072225  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18007222a  mov     [rsp+38h+TokenInformation], 0
0x180072232  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180072237  lea     edx, [r9+19h]; TokenInformationClass
0x18007223b  call    cs:__imp_GetTokenInformation
0x180072241  test    eax, eax
0x180072243  jz      short loc_180072281
0x180072245  xor     ebx, ebx
0x180072247  cmp     [rsp+38h+TokenInformation], 0
0x18007224c  setnz   al
0x18007224f  mov     [rdi], al
0x180072251  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180072256  mov     [rsp+38h+TokenHandle], 0
0x18007225f  lea     rdx, [rcx-1]
0x180072263  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180072267  jbe     short loc_18007228E
0x180072269  mov     eax, ebx
0x18007226b  mov     rbx, [rsp+38h+arg_0]
0x180072270  add     rsp, 30h
0x180072274  pop     rdi
0x180072275  retn
0x180072276  movzx   ebx, ax
0x180072279  or      ebx, 80070000h
0x18007227f  jmp     short loc_180072209
0x180072281  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180072286  mov     ebx, eax
0x180072288  test    eax, eax
0x18007228a  js      short loc_180072251
0x18007228c  jmp     short loc_180072247
0x18007228e  call    cs:__imp_CloseHandle
0x180072294  jmp     short loc_180072269
```
