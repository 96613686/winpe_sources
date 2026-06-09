# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18000bd80`
- end: `0x18000be9f`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bb60`

## callees

- `0x18000bd80`
- `0x18000bea8`
- `0x18002116c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000be0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000be52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bdca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bdca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bdf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000be87`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bdf4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000be87`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(HANDLE TokenHandle, __int64 a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  __int64 result; // rax
  void *v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  unsigned int v10; // edx
  void *v11; // rcx
  int v12; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a3;
  *a4 = 0;
  hObject = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    result = SHOpenEffectiveToken(0, a2, &hObject);
    if ( (int)result < 0 )
      return result;
    v5 = hObject;
  }
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v7 = TokenInformation;
  if ( !TokenInformation )
  {
    v8 = -2147024882;
    goto LABEL_7;
  }
  v8 = 0;
  if ( !GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v7);
      v12 = CTLocalAllocPolicy::Alloc(v11, v10, TokenInformationLength, &TokenInformation);
      v7 = TokenInformation;
      v8 = v12;
      if ( v12 < 0 )
        goto LABEL_13;
      if ( GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_6;
      LastError = GetLastError();
      v8 = LastError;
    }
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      goto LABEL_6;
LABEL_13:
    LocalFree(v7);
    goto LABEL_7;
  }
LABEL_6:
  *a4 = v7;
LABEL_7:
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bd80  mov     [rsp-28h+TokenInformationLength], r8d
0x18000bd85  push    rbp
0x18000bd86  push    rbx
0x18000bd87  push    rsi
0x18000bd88  push    rdi
0x18000bd89  push    r14
0x18000bd8b  mov     rbp, rsp
0x18000bd8e  sub     rsp, 30h
0x18000bd92  mov     qword ptr [r9], 0
0x18000bd99  mov     r14, r9
0x18000bd9c  mov     [rbp+hObject], 0
0x18000bda4  mov     rsi, rcx
0x18000bda7  test    rcx, rcx
0x18000bdaa  jnz     short loc_18000BDBD
0x18000bdac  lea     r8, [rbp+hObject]; void **
0x18000bdb0  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18000bdb5  test    eax, eax
0x18000bdb7  js      short loc_18000BE12
0x18000bdb9  mov     rsi, [rbp+hObject]
0x18000bdbd  mov     edx, 800h; uBytes
0x18000bdc2  mov     ecx, 40h ; '@'; uFlags
0x18000bdc7  mov     [rbp+TokenInformationLength], edx
0x18000bdca  call    cs:__imp_LocalAlloc
0x18000bdd0  mov     [rbp+TokenInformation], rax
0x18000bdd4  mov     rdi, rax
0x18000bdd7  test    rax, rax
0x18000bdda  jz      short loc_18000BE1D
0x18000bddc  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000bde0  lea     rax, [rbp+TokenInformationLength]
0x18000bde4  xor     ebx, ebx
0x18000bde6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000bdeb  mov     r8, rdi; TokenInformation
0x18000bdee  mov     rcx, rsi; TokenHandle
0x18000bdf1  lea     edx, [rbx+1]; TokenInformationClass
0x18000bdf4  call    cs:__imp_GetTokenInformation
0x18000bdfa  test    eax, eax
0x18000bdfc  jz      short loc_18000BE42
0x18000bdfe  mov     [r14], rdi
0x18000be01  mov     rcx, [rbp+hObject]; hObject
0x18000be05  test    rcx, rcx
0x18000be08  jz      short loc_18000BE10
0x18000be0a  call    cs:__imp_CloseHandle
0x18000be10  mov     eax, ebx
0x18000be12  add     rsp, 30h
0x18000be16  pop     r14
0x18000be18  pop     rdi
0x18000be19  pop     rsi
0x18000be1a  pop     rbx
0x18000be1b  pop     rbp
0x18000be1c  retn
0x18000be1d  mov     ebx, 8007000Eh
0x18000be22  jmp     short loc_18000BE01
0x18000be24  test    ebx, ebx
0x18000be26  jns     short loc_18000BDFE
0x18000be28  mov     rcx, rdi; hMem
0x18000be2b  call    cs:__imp_LocalFree
0x18000be31  jmp     short loc_18000BE01
0x18000be33  test    eax, eax
0x18000be35  jle     short loc_18000BE24
0x18000be37  movzx   ebx, ax
0x18000be3a  or      ebx, 80070000h
0x18000be40  jmp     short loc_18000BE24
0x18000be42  call    cs:__imp_GetLastError
0x18000be48  mov     ebx, eax
0x18000be4a  cmp     eax, 7Ah ; 'z'
0x18000be4d  jnz     short loc_18000BE33
0x18000be4f  mov     rcx, rdi; hMem
0x18000be52  call    cs:__imp_LocalFree
0x18000be58  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18000be5c  lea     r9, [rbp+TokenInformation]; void **
0x18000be60  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000be65  mov     rdi, [rbp+TokenInformation]
0x18000be69  mov     ebx, eax
0x18000be6b  test    eax, eax
0x18000be6d  js      short loc_18000BE28
0x18000be6f  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18000be73  lea     rax, [rbp+TokenInformationLength]
0x18000be77  mov     r8, rdi; TokenInformation
0x18000be7a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18000be7f  mov     edx, 1; TokenInformationClass
0x18000be84  mov     rcx, rsi; TokenHandle
0x18000be87  call    cs:__imp_GetTokenInformation
0x18000be8d  test    eax, eax
0x18000be8f  jnz     loc_18000BDFE
0x18000be95  call    cs:__imp_GetLastError
0x18000be9b  mov     ebx, eax
0x18000be9d  jmp     short loc_18000BE33
```
