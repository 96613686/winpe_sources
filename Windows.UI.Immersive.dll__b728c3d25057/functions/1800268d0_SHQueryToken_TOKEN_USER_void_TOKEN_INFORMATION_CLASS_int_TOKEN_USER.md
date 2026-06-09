# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x1800268d0`
- end: `0x1800269f1`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d4bb4`

## callees

- `0x1800268d0`
- `0x1800269f8`
- `0x180030ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800269de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026965`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026965`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800269c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002691d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002691d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002694b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002699d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002694b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002699d`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(void *a1, DWORD a2, int a3, _QWORD *a4)
{
  __int64 result; // rax
  HANDLE v6; // r14
  void *v7; // rdi
  signed int v8; // ebx
  signed int LastError; // eax
  void *v10; // rcx
  int v11; // eax
  LPVOID TokenInformation; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = a2;
  TokenInformation = a1;
  *a4 = 0;
  TokenHandle = 0;
  result = SHOpenEffectiveToken((__int64)a1, a3, &TokenHandle);
  if ( (int)result < 0 )
    return result;
  v6 = TokenHandle;
  TokenInformationLength = 2048;
  TokenInformation = LocalAlloc(0x40u, 0x800u);
  v7 = TokenInformation;
  if ( !TokenInformation )
  {
    v8 = -2147024882;
    goto LABEL_14;
  }
  v8 = 0;
  if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_12;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 122 )
    goto LABEL_8;
  LocalFree(v7);
  v11 = CTLocalAllocPolicy::Alloc(v10, 0x40u, TokenInformationLength, &TokenInformation);
  v7 = TokenInformation;
  v8 = v11;
  if ( v11 >= 0 )
  {
    if ( GetTokenInformation(v6, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
      goto LABEL_12;
    LastError = GetLastError();
    v8 = LastError;
LABEL_8:
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_11;
LABEL_12:
    *a4 = v7;
    goto LABEL_14;
  }
LABEL_11:
  LocalFree(v7);
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800268d0  mov     [rsp-28h+TokenInformationLength], edx
0x1800268d4  mov     [rsp-28h+TokenInformation], rcx
0x1800268d9  push    rbp
0x1800268da  push    rbx
0x1800268db  push    rsi
0x1800268dc  push    rdi
0x1800268dd  push    r14
0x1800268df  mov     rbp, rsp
0x1800268e2  sub     rsp, 30h
0x1800268e6  mov     edx, r8d; int
0x1800268e9  mov     qword ptr [r9], 0
0x1800268f0  lea     r8, [rbp+TokenHandle]; void **
0x1800268f4  mov     [rbp+TokenHandle], 0
0x1800268fc  mov     rsi, r9
0x1800268ff  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x180026904  test    eax, eax
0x180026906  js      loc_1800269E6
0x18002690c  mov     r14, [rbp+TokenHandle]
0x180026910  mov     edx, 800h; uBytes
0x180026915  mov     ecx, 40h ; '@'; uFlags
0x18002691a  mov     [rbp+TokenInformationLength], edx
0x18002691d  call    cs:__imp_LocalAlloc
0x180026923  mov     [rbp+TokenInformation], rax
0x180026927  mov     rdi, rax
0x18002692a  test    rax, rax
0x18002692d  jz      loc_1800269D0
0x180026933  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180026937  lea     rax, [rbp+TokenInformationLength]
0x18002693b  xor     ebx, ebx
0x18002693d  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180026942  mov     r8, rdi; TokenInformation
0x180026945  mov     rcx, r14; TokenHandle
0x180026948  lea     edx, [rbx+1]; TokenInformationClass
0x18002694b  call    cs:__imp_GetTokenInformation
0x180026951  test    eax, eax
0x180026953  jnz     short loc_1800269CB
0x180026955  call    cs:__imp_GetLastError
0x18002695b  mov     ebx, eax
0x18002695d  cmp     eax, 7Ah ; 'z'
0x180026960  jnz     short loc_1800269AF
0x180026962  mov     rcx, rdi; hMem
0x180026965  call    cs:__imp_LocalFree
0x18002696b  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x18002696f  lea     r9, [rbp+TokenInformation]; void **
0x180026973  lea     edx, [rbx-3Ah]; unsigned int
0x180026976  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002697b  mov     rdi, [rbp+TokenInformation]
0x18002697f  mov     ebx, eax
0x180026981  test    eax, eax
0x180026983  js      short loc_1800269C0
0x180026985  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180026989  lea     rax, [rbp+TokenInformationLength]
0x18002698d  mov     r8, rdi; TokenInformation
0x180026990  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180026995  mov     edx, 1; TokenInformationClass
0x18002699a  mov     rcx, r14; TokenHandle
0x18002699d  call    cs:__imp_GetTokenInformation
0x1800269a3  test    eax, eax
0x1800269a5  jnz     short loc_1800269CB
0x1800269a7  call    cs:__imp_GetLastError
0x1800269ad  mov     ebx, eax
0x1800269af  test    eax, eax
0x1800269b1  jle     short loc_1800269BC
0x1800269b3  movzx   ebx, ax
0x1800269b6  or      ebx, 80070000h
0x1800269bc  test    ebx, ebx
0x1800269be  jns     short loc_1800269CB
0x1800269c0  mov     rcx, rdi; hMem
0x1800269c3  call    cs:__imp_LocalFree
0x1800269c9  jmp     short loc_1800269D5
0x1800269cb  mov     [rsi], rdi
0x1800269ce  jmp     short loc_1800269D5
0x1800269d0  mov     ebx, 8007000Eh
0x1800269d5  mov     rcx, [rbp+TokenHandle]; hObject
0x1800269d9  test    rcx, rcx
0x1800269dc  jz      short loc_1800269E4
0x1800269de  call    cs:__imp_CloseHandle
0x1800269e4  mov     eax, ebx
0x1800269e6  add     rsp, 30h
0x1800269ea  pop     r14
0x1800269ec  pop     rdi
0x1800269ed  pop     rsi
0x1800269ee  pop     rbx
0x1800269ef  pop     rbp
0x1800269f0  retn
```
