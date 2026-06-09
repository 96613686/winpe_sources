# SHQueryToken<_TOKEN_GROUPS>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_GROUPS * *)

- ea: `0x18001d73c`
- end: `0x18001d864`
- name: `??$SHQueryToken@U_TOKEN_GROUPS@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_GROUPS@@@Z`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e9d8`

## callees

- `0x18001d73c`
- `0x18001db6c`
- `0x18001e7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d821`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d851`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d83d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d7df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d83d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d7c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d817`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d7c5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d817`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_GROUPS>(void *a1, __int64 a2, DWORD a3, _QWORD *a4)
{
  __int64 result; // rax
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
  result = SHOpenEffectiveToken(8u, 0, &TokenHandle);
  if ( (int)result < 0 )
    return result;
  v7 = TokenHandle;
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v8 = CTLocalAllocPolicy::Alloc(v6, 0x40u, 0x800u, &TokenInformation);
  if ( v8 >= 0 )
  {
    v9 = TokenInformation;
    if ( GetTokenInformation(v7, TokenGroups, TokenInformation, TokenInformationLength, &TokenInformationLength) )
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
      if ( GetTokenInformation(v7, TokenGroups, TokenInformation, TokenInformationLength, &TokenInformationLength) )
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
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d73c  mov     [rsp-28h+TokenInformationLength], r8d
0x18001d741  mov     [rsp-28h+TokenInformation], rcx
0x18001d746  push    rbp
0x18001d747  push    rbx
0x18001d748  push    rsi
0x18001d749  push    rdi
0x18001d74a  push    r14
0x18001d74c  mov     rbp, rsp
0x18001d74f  sub     rsp, 30h
0x18001d753  xor     edx, edx; int
0x18001d755  mov     qword ptr [r9], 0
0x18001d75c  lea     r8, [rbp+TokenHandle]; void **
0x18001d760  mov     [rbp+TokenHandle], 0
0x18001d768  mov     rsi, r9
0x18001d76b  lea     ecx, [rdx+8]; DesiredAccess
0x18001d76e  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18001d773  test    eax, eax
0x18001d775  js      loc_18001D859
0x18001d77b  mov     r14, [rbp+TokenHandle]
0x18001d77f  lea     r9, [rbp+TokenInformation]; void **
0x18001d783  mov     r8d, 800h; unsigned __int64
0x18001d789  mov     [rbp+TokenInformation], 0
0x18001d791  mov     edx, 40h ; '@'; unsigned int
0x18001d796  mov     [rbp+TokenInformationLength], r8d
0x18001d79a  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001d79f  mov     ebx, eax
0x18001d7a1  test    eax, eax
0x18001d7a3  js      loc_18001D848
0x18001d7a9  mov     rdi, [rbp+TokenInformation]
0x18001d7ad  lea     rax, [rbp+TokenInformationLength]
0x18001d7b1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001d7b5  mov     r8, rdi; TokenInformation
0x18001d7b8  mov     edx, 2; TokenInformationClass
0x18001d7bd  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001d7c2  mov     rcx, r14; TokenHandle
0x18001d7c5  call    cs:__imp_GetTokenInformation
0x18001d7cb  test    eax, eax
0x18001d7cd  jnz     short loc_18001D845
0x18001d7cf  call    cs:__imp_GetLastError
0x18001d7d5  mov     ebx, eax
0x18001d7d7  cmp     eax, 7Ah ; 'z'
0x18001d7da  jnz     short loc_18001D829
0x18001d7dc  mov     rcx, rdi; hMem
0x18001d7df  call    cs:__imp_LocalFree
0x18001d7e5  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18001d7e9  lea     r9, [rbp+TokenInformation]; void **
0x18001d7ed  lea     edx, [rbx-3Ah]; unsigned int
0x18001d7f0  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001d7f5  mov     rdi, [rbp+TokenInformation]
0x18001d7f9  mov     ebx, eax
0x18001d7fb  test    eax, eax
0x18001d7fd  js      short loc_18001D83A
0x18001d7ff  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18001d803  lea     rax, [rbp+TokenInformationLength]
0x18001d807  mov     r8, rdi; TokenInformation
0x18001d80a  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001d80f  mov     edx, 2; TokenInformationClass
0x18001d814  mov     rcx, r14; TokenHandle
0x18001d817  call    cs:__imp_GetTokenInformation
0x18001d81d  test    eax, eax
0x18001d81f  jnz     short loc_18001D845
0x18001d821  call    cs:__imp_GetLastError
0x18001d827  mov     ebx, eax
0x18001d829  test    eax, eax
0x18001d82b  jle     short loc_18001D836
0x18001d82d  movzx   ebx, ax
0x18001d830  or      ebx, 80070000h
0x18001d836  test    ebx, ebx
0x18001d838  jns     short loc_18001D845
0x18001d83a  mov     rcx, rdi; hMem
0x18001d83d  call    cs:__imp_LocalFree
0x18001d843  jmp     short loc_18001D848
0x18001d845  mov     [rsi], rdi
0x18001d848  mov     rcx, [rbp+TokenHandle]; hObject
0x18001d84c  test    rcx, rcx
0x18001d84f  jz      short loc_18001D857
0x18001d851  call    cs:__imp_CloseHandle
0x18001d857  mov     eax, ebx
0x18001d859  add     rsp, 30h
0x18001d85d  pop     r14
0x18001d85f  pop     rdi
0x18001d860  pop     rsi
0x18001d861  pop     rbx
0x18001d862  pop     rbp
0x18001d863  retn
```
