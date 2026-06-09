# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800bedc8`
- end: `0x1800beeeb`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `291`
- prototype: `int __fastcall(void *, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009a7b0`

## callees

- `0x180040aa8`
- `0x1800bedc8`
- `0x1800beef4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bee56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bee56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800beea8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800beed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bee66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800beec4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bee66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800beec4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bee4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bee9e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bee4c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bee9e`

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
0x1800bedc8  mov     [rsp-28h+TokenInformationLength], r8d
0x1800bedcd  mov     [rsp-28h+TokenInformation], rcx
0x1800bedd2  push    rbp
0x1800bedd3  push    rbx
0x1800bedd4  push    rsi
0x1800bedd5  push    rdi
0x1800bedd6  push    r14
0x1800bedd8  mov     rbp, rsp
0x1800beddb  sub     rsp, 30h
0x1800beddf  lea     r8, [rbp+TokenHandle]; void **
0x1800bede3  mov     qword ptr [r9], 0
0x1800bedea  mov     rsi, r9
0x1800beded  mov     [rbp+TokenHandle], 0
0x1800bedf5  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800bedfa  test    eax, eax
0x1800bedfc  js      loc_1800BEEE0
0x1800bee02  mov     r14, [rbp+TokenHandle]
0x1800bee06  lea     r9, [rbp+TokenInformation]; void **
0x1800bee0a  mov     r8d, 800h; unsigned __int64
0x1800bee10  mov     [rbp+TokenInformation], 0
0x1800bee18  mov     edx, 40h ; '@'; unsigned int
0x1800bee1d  mov     [rbp+TokenInformationLength], r8d
0x1800bee21  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800bee26  mov     ebx, eax
0x1800bee28  test    eax, eax
0x1800bee2a  js      loc_1800BEECF
0x1800bee30  mov     rdi, [rbp+TokenInformation]
0x1800bee34  lea     rax, [rbp+TokenInformationLength]
0x1800bee38  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800bee3c  mov     r8, rdi; TokenInformation
0x1800bee3f  mov     edx, 1; TokenInformationClass
0x1800bee44  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800bee49  mov     rcx, r14; TokenHandle
0x1800bee4c  call    cs:__imp_GetTokenInformation
0x1800bee52  test    eax, eax
0x1800bee54  jnz     short loc_1800BEECC
0x1800bee56  call    cs:__imp_GetLastError
0x1800bee5c  mov     ebx, eax
0x1800bee5e  cmp     eax, 7Ah ; 'z'
0x1800bee61  jnz     short loc_1800BEEB0
0x1800bee63  mov     rcx, rdi; hMem
0x1800bee66  call    cs:__imp_LocalFree
0x1800bee6c  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1800bee70  lea     r9, [rbp+TokenInformation]; void **
0x1800bee74  lea     edx, [rbx-3Ah]; unsigned int
0x1800bee77  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800bee7c  mov     rdi, [rbp+TokenInformation]
0x1800bee80  mov     ebx, eax
0x1800bee82  test    eax, eax
0x1800bee84  js      short loc_1800BEEC1
0x1800bee86  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800bee8a  lea     rax, [rbp+TokenInformationLength]
0x1800bee8e  mov     r8, rdi; TokenInformation
0x1800bee91  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800bee96  mov     edx, 1; TokenInformationClass
0x1800bee9b  mov     rcx, r14; TokenHandle
0x1800bee9e  call    cs:__imp_GetTokenInformation
0x1800beea4  test    eax, eax
0x1800beea6  jnz     short loc_1800BEECC
0x1800beea8  call    cs:__imp_GetLastError
0x1800beeae  mov     ebx, eax
0x1800beeb0  test    eax, eax
0x1800beeb2  jle     short loc_1800BEEBD
0x1800beeb4  movzx   ebx, ax
0x1800beeb7  or      ebx, 80070000h
0x1800beebd  test    ebx, ebx
0x1800beebf  jns     short loc_1800BEECC
0x1800beec1  mov     rcx, rdi; hMem
0x1800beec4  call    cs:__imp_LocalFree
0x1800beeca  jmp     short loc_1800BEECF
0x1800beecc  mov     [rsi], rdi
0x1800beecf  mov     rcx, [rbp+TokenHandle]; hObject
0x1800beed3  test    rcx, rcx
0x1800beed6  jz      short loc_1800BEEDE
0x1800beed8  call    cs:__imp_CloseHandle
0x1800beede  mov     eax, ebx
0x1800beee0  add     rsp, 30h
0x1800beee4  pop     r14
0x1800beee6  pop     rdi
0x1800beee7  pop     rsi
0x1800beee8  pop     rbx
0x1800beee9  pop     rbp
0x1800beeea  retn
```
