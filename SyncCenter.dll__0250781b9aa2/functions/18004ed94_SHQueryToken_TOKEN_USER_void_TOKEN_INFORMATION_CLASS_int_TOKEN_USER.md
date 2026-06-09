# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18004ed94`
- end: `0x18004eeb7`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `291`
- prototype: `int __fastcall(void *, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002649c`

## callees

- `0x180013970`
- `0x18004ed94`
- `0x18004eec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004eea4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004eea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ee90`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ee18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ee6a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ee18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ee6a`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_USER>(void *a1, int a2, DWORD a3, _QWORD *a4)
{
  int result; // eax
  void *v6; // rcx
  HANDLE v7; // r14
  signed int v8; // ebx
  void *v9; // rdi
  signed int LastError; // eax
  void *v11; // rcx
  int v12; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  TokenInformation = a1;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken((unsigned int)a1, a2, &TokenHandle);
  if ( result < 0 )
    return result;
  v7 = TokenHandle;
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v8 = CTLocalAllocPolicy::Alloc(v6, 0x40u, 0x800u, &TokenInformation);
  if ( v8 >= 0 )
  {
    v9 = TokenInformation;
    if ( GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_12;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v9);
      v12 = CTLocalAllocPolicy::Alloc(v11, 0x40u, TokenInformationLength, &TokenInformation);
      v9 = TokenInformation;
      v8 = v12;
      if ( v12 < 0 )
      {
LABEL_11:
        LocalFree(v9);
        goto LABEL_13;
      }
      if ( GetTokenInformation(v7, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
LABEL_12:
        *a4 = v9;
        goto LABEL_13;
      }
      LastError = GetLastError();
      v8 = LastError;
    }
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_11;
    goto LABEL_12;
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x18004ed94  mov     [rsp-28h+TokenInformationLength], r8d
0x18004ed99  mov     [rsp-28h+TokenInformation], rcx
0x18004ed9e  push    rbp
0x18004ed9f  push    rbx
0x18004eda0  push    rsi
0x18004eda1  push    rdi
0x18004eda2  push    r14
0x18004eda4  mov     rbp, rsp
0x18004eda7  sub     rsp, 30h
0x18004edab  lea     r8, [rbp+TokenHandle]; void **
0x18004edaf  mov     qword ptr [r9], 0
0x18004edb6  mov     rsi, r9
0x18004edb9  mov     [rbp+TokenHandle], 0
0x18004edc1  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18004edc6  test    eax, eax
0x18004edc8  js      loc_18004EEAC
0x18004edce  mov     r14, [rbp+TokenHandle]
0x18004edd2  lea     r9, [rbp+TokenInformation]; void **
0x18004edd6  mov     r8d, 800h; unsigned __int64
0x18004eddc  mov     [rbp+TokenInformation], 0
0x18004ede4  mov     edx, 40h ; '@'; unsigned int
0x18004ede9  mov     [rbp+TokenInformationLength], r8d
0x18004eded  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004edf2  mov     ebx, eax
0x18004edf4  test    eax, eax
0x18004edf6  js      loc_18004EE9B
0x18004edfc  mov     rdi, [rbp+TokenInformation]
0x18004ee00  lea     rax, [rbp+TokenInformationLength]
0x18004ee04  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004ee08  mov     r8, rdi; TokenInformation
0x18004ee0b  mov     edx, 1; TokenInformationClass
0x18004ee10  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004ee15  mov     rcx, r14; TokenHandle
0x18004ee18  call    cs:__imp_GetTokenInformation
0x18004ee1e  test    eax, eax
0x18004ee20  jnz     short loc_18004EE98
0x18004ee22  call    cs:__imp_GetLastError
0x18004ee28  mov     ebx, eax
0x18004ee2a  cmp     eax, 7Ah ; 'z'
0x18004ee2d  jnz     short loc_18004EE7C
0x18004ee2f  mov     rcx, rdi; hMem
0x18004ee32  call    cs:__imp_LocalFree
0x18004ee38  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18004ee3c  lea     r9, [rbp+TokenInformation]; void **
0x18004ee40  lea     edx, [rbx-3Ah]; unsigned int
0x18004ee43  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004ee48  mov     rdi, [rbp+TokenInformation]
0x18004ee4c  mov     ebx, eax
0x18004ee4e  test    eax, eax
0x18004ee50  js      short loc_18004EE8D
0x18004ee52  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18004ee56  lea     rax, [rbp+TokenInformationLength]
0x18004ee5a  mov     r8, rdi; TokenInformation
0x18004ee5d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18004ee62  mov     edx, 1; TokenInformationClass
0x18004ee67  mov     rcx, r14; TokenHandle
0x18004ee6a  call    cs:__imp_GetTokenInformation
0x18004ee70  test    eax, eax
0x18004ee72  jnz     short loc_18004EE98
0x18004ee74  call    cs:__imp_GetLastError
0x18004ee7a  mov     ebx, eax
0x18004ee7c  test    eax, eax
0x18004ee7e  jle     short loc_18004EE89
0x18004ee80  movzx   ebx, ax
0x18004ee83  or      ebx, 80070000h
0x18004ee89  test    ebx, ebx
0x18004ee8b  jns     short loc_18004EE98
0x18004ee8d  mov     rcx, rdi; hMem
0x18004ee90  call    cs:__imp_LocalFree
0x18004ee96  jmp     short loc_18004EE9B
0x18004ee98  mov     [rsi], rdi
0x18004ee9b  mov     rcx, [rbp+TokenHandle]; hObject
0x18004ee9f  test    rcx, rcx
0x18004eea2  jz      short loc_18004EEAA
0x18004eea4  call    cs:__imp_CloseHandle
0x18004eeaa  mov     eax, ebx
0x18004eeac  add     rsp, 30h
0x18004eeb0  pop     r14
0x18004eeb2  pop     rdi
0x18004eeb3  pop     rsi
0x18004eeb4  pop     rbx
0x18004eeb5  pop     rbp
0x18004eeb6  retn
```
