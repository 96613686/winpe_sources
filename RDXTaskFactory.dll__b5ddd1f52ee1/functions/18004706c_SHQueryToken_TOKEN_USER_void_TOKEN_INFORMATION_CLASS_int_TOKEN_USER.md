# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18004706c`
- end: `0x18004718a`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `286`
- prototype: `int __fastcall(HANDLE TokenHandle, unsigned int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047234`

## callees

- `0x18004706c`
- `0x180047190`
- `0x1800471c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047147`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047177`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047177`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800470ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004713d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800470ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004713d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047163`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047108`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047163`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SHQueryToken<_TOKEN_USER>(HANDLE TokenHandle, unsigned int a2, DWORD a3, _QWORD *a4)
{
  HANDLE v5; // rsi
  int result; // eax
  signed int v7; // ebx
  void *v8; // rdi
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
    if ( result < 0 )
      return result;
    v5 = hObject;
  }
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v7 = CTLocalAllocPolicy::Alloc(TokenHandle, a2, 0x800u, &TokenInformation);
  if ( v7 >= 0 )
  {
    v8 = TokenInformation;
    if ( GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_14;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v8);
      v12 = CTLocalAllocPolicy::Alloc(v11, v10, TokenInformationLength, &TokenInformation);
      v8 = TokenInformation;
      v7 = v12;
      if ( v12 < 0 )
      {
LABEL_13:
        LocalFree(v8);
        goto LABEL_15;
      }
      if ( GetTokenInformation(v5, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
LABEL_14:
        *a4 = v8;
        goto LABEL_15;
      }
      LastError = GetLastError();
      v7 = LastError;
    }
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_13;
    goto LABEL_14;
  }
LABEL_15:
  if ( hObject )
    CloseHandle(hObject);
  return v7;
}

```

## disassembly

```asm
0x18004706c  mov     [rsp-28h+TokenInformationLength], r8d
0x180047071  push    rbp
0x180047072  push    rbx
0x180047073  push    rsi
0x180047074  push    rdi
0x180047075  push    r14
0x180047077  mov     rbp, rsp
0x18004707a  sub     rsp, 30h
0x18004707e  mov     qword ptr [r9], 0
0x180047085  mov     r14, r9
0x180047088  mov     [rbp+hObject], 0
0x180047090  mov     rsi, rcx
0x180047093  test    rcx, rcx
0x180047096  jnz     short loc_1800470AD
0x180047098  lea     r8, [rbp+hObject]; void **
0x18004709c  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800470a1  test    eax, eax
0x1800470a3  js      loc_18004717F
0x1800470a9  mov     rsi, [rbp+hObject]
0x1800470ad  mov     r8d, 800h; unsigned __int64
0x1800470b3  mov     [rbp+TokenInformation], 0
0x1800470bb  lea     r9, [rbp+TokenInformation]; void **
0x1800470bf  mov     [rbp+TokenInformationLength], r8d
0x1800470c3  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800470c8  mov     ebx, eax
0x1800470ca  test    eax, eax
0x1800470cc  js      loc_18004716E
0x1800470d2  mov     rdi, [rbp+TokenInformation]
0x1800470d6  lea     rax, [rbp+TokenInformationLength]
0x1800470da  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800470de  mov     r8, rdi; TokenInformation
0x1800470e1  mov     edx, 1; TokenInformationClass
0x1800470e6  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800470eb  mov     rcx, rsi; TokenHandle
0x1800470ee  call    cs:__imp_GetTokenInformation
0x1800470f4  test    eax, eax
0x1800470f6  jnz     short loc_18004716B
0x1800470f8  call    cs:__imp_GetLastError
0x1800470fe  mov     ebx, eax
0x180047100  cmp     eax, 7Ah ; 'z'
0x180047103  jnz     short loc_18004714F
0x180047105  mov     rcx, rdi; hMem
0x180047108  call    cs:__imp_LocalFree
0x18004710e  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180047112  lea     r9, [rbp+TokenInformation]; void **
0x180047116  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18004711b  mov     rdi, [rbp+TokenInformation]
0x18004711f  mov     ebx, eax
0x180047121  test    eax, eax
0x180047123  js      short loc_180047160
0x180047125  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180047129  lea     rax, [rbp+TokenInformationLength]
0x18004712d  mov     r8, rdi; TokenInformation
0x180047130  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180047135  mov     edx, 1; TokenInformationClass
0x18004713a  mov     rcx, rsi; TokenHandle
0x18004713d  call    cs:__imp_GetTokenInformation
0x180047143  test    eax, eax
0x180047145  jnz     short loc_18004716B
0x180047147  call    cs:__imp_GetLastError
0x18004714d  mov     ebx, eax
0x18004714f  test    eax, eax
0x180047151  jle     short loc_18004715C
0x180047153  movzx   ebx, ax
0x180047156  or      ebx, 80070000h
0x18004715c  test    ebx, ebx
0x18004715e  jns     short loc_18004716B
0x180047160  mov     rcx, rdi; hMem
0x180047163  call    cs:__imp_LocalFree
0x180047169  jmp     short loc_18004716E
0x18004716b  mov     [r14], rdi
0x18004716e  mov     rcx, [rbp+hObject]; hObject
0x180047172  test    rcx, rcx
0x180047175  jz      short loc_18004717D
0x180047177  call    cs:__imp_CloseHandle
0x18004717d  mov     eax, ebx
0x18004717f  add     rsp, 30h
0x180047183  pop     r14
0x180047185  pop     rdi
0x180047186  pop     rsi
0x180047187  pop     rbx
0x180047188  pop     rbp
0x180047189  retn
```
