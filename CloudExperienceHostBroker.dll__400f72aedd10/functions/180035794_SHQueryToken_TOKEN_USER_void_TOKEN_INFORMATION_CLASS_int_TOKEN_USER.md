# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x180035794`
- end: `0x1800358af`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `283`
- prototype: `int __fastcall(void *, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035a5c`

## callees

- `0x180035794`
- `0x1800358b8`
- `0x1800358ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003581d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003586c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003581d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003586c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003589c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003589c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003582d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035888`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003582d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035888`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035813`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035862`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035813`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035862`

## pseudocode

```c
int __fastcall SHQueryToken<_TOKEN_USER>(void *a1, int a2, DWORD a3, _QWORD *a4)
{
  int result; // eax
  unsigned int v6; // edx
  void *v7; // rcx
  HANDLE v8; // r14
  signed int v9; // ebx
  void *v10; // rdi
  signed int LastError; // eax
  unsigned int v12; // edx
  void *v13; // rcx
  int v14; // eax
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
  v8 = TokenHandle;
  TokenInformation = 0;
  TokenInformationLength = 2048;
  v9 = CTLocalAllocPolicy::Alloc(v7, v6, 0x800u, &TokenInformation);
  if ( v9 >= 0 )
  {
    v10 = TokenInformation;
    if ( GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_12;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError == 122 )
    {
      LocalFree(v10);
      v14 = CTLocalAllocPolicy::Alloc(v13, v12, TokenInformationLength, &TokenInformation);
      v10 = TokenInformation;
      v9 = v14;
      if ( v14 < 0 )
      {
LABEL_11:
        LocalFree(v10);
        goto LABEL_13;
      }
      if ( GetTokenInformation(v8, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      {
LABEL_12:
        *a4 = v10;
        goto LABEL_13;
      }
      LastError = GetLastError();
      v9 = LastError;
    }
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_11;
    goto LABEL_12;
  }
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v9;
}

```

## disassembly

```asm
0x180035794  mov     [rsp-28h+TokenInformationLength], r8d
0x180035799  mov     [rsp-28h+TokenInformation], rcx
0x18003579e  push    rbp
0x18003579f  push    rbx
0x1800357a0  push    rsi
0x1800357a1  push    rdi
0x1800357a2  push    r14
0x1800357a4  mov     rbp, rsp
0x1800357a7  sub     rsp, 30h
0x1800357ab  lea     r8, [rbp+TokenHandle]; void **
0x1800357af  mov     qword ptr [r9], 0
0x1800357b6  mov     rsi, r9
0x1800357b9  mov     [rbp+TokenHandle], 0
0x1800357c1  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1800357c6  test    eax, eax
0x1800357c8  js      loc_1800358A4
0x1800357ce  mov     r14, [rbp+TokenHandle]
0x1800357d2  lea     r9, [rbp+TokenInformation]; void **
0x1800357d6  mov     r8d, 800h; unsigned __int64
0x1800357dc  mov     [rbp+TokenInformation], 0
0x1800357e4  mov     [rbp+TokenInformationLength], r8d
0x1800357e8  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800357ed  mov     ebx, eax
0x1800357ef  test    eax, eax
0x1800357f1  js      loc_180035893
0x1800357f7  mov     rdi, [rbp+TokenInformation]
0x1800357fb  lea     rax, [rbp+TokenInformationLength]
0x1800357ff  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180035803  mov     r8, rdi; TokenInformation
0x180035806  mov     edx, 1; TokenInformationClass
0x18003580b  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180035810  mov     rcx, r14; TokenHandle
0x180035813  call    cs:__imp_GetTokenInformation
0x180035819  test    eax, eax
0x18003581b  jnz     short loc_180035890
0x18003581d  call    cs:__imp_GetLastError
0x180035823  mov     ebx, eax
0x180035825  cmp     eax, 7Ah ; 'z'
0x180035828  jnz     short loc_180035874
0x18003582a  mov     rcx, rdi; hMem
0x18003582d  call    cs:__imp_LocalFree
0x180035833  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x180035837  lea     r9, [rbp+TokenInformation]; void **
0x18003583b  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180035840  mov     rdi, [rbp+TokenInformation]
0x180035844  mov     ebx, eax
0x180035846  test    eax, eax
0x180035848  js      short loc_180035885
0x18003584a  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003584e  lea     rax, [rbp+TokenInformationLength]
0x180035852  mov     r8, rdi; TokenInformation
0x180035855  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18003585a  mov     edx, 1; TokenInformationClass
0x18003585f  mov     rcx, r14; TokenHandle
0x180035862  call    cs:__imp_GetTokenInformation
0x180035868  test    eax, eax
0x18003586a  jnz     short loc_180035890
0x18003586c  call    cs:__imp_GetLastError
0x180035872  mov     ebx, eax
0x180035874  test    eax, eax
0x180035876  jle     short loc_180035881
0x180035878  movzx   ebx, ax
0x18003587b  or      ebx, 80070000h
0x180035881  test    ebx, ebx
0x180035883  jns     short loc_180035890
0x180035885  mov     rcx, rdi; hMem
0x180035888  call    cs:__imp_LocalFree
0x18003588e  jmp     short loc_180035893
0x180035890  mov     [rsi], rdi
0x180035893  mov     rcx, [rbp+TokenHandle]; hObject
0x180035897  test    rcx, rcx
0x18003589a  jz      short loc_1800358A2
0x18003589c  call    cs:__imp_CloseHandle
0x1800358a2  mov     eax, ebx
0x1800358a4  add     rsp, 30h
0x1800358a8  pop     r14
0x1800358aa  pop     rdi
0x1800358ab  pop     rsi
0x1800358ac  pop     rbx
0x1800358ad  pop     rbp
0x1800358ae  retn
```
