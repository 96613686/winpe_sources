# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x18002381c`
- end: `0x180023937`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `283`
- prototype: `int __fastcall(void *, int, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023ba0`

## callees

- `0x18002381c`
- `0x180023970`
- `0x1800239a4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002389b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800238ea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002389b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800238ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023924`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023924`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023910`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002381c  mov     [rsp-28h+TokenInformationLength], r8d
0x180023821  mov     [rsp-28h+TokenInformation], rcx
0x180023826  push    rbp
0x180023827  push    rbx
0x180023828  push    rsi
0x180023829  push    rdi
0x18002382a  push    r14
0x18002382c  mov     rbp, rsp
0x18002382f  sub     rsp, 30h
0x180023833  lea     r8, [rbp+TokenHandle]; void **
0x180023837  mov     qword ptr [r9], 0
0x18002383e  mov     rsi, r9
0x180023841  mov     [rbp+TokenHandle], 0
0x180023849  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x18002384e  test    eax, eax
0x180023850  js      loc_18002392C
0x180023856  mov     r14, [rbp+TokenHandle]
0x18002385a  lea     r9, [rbp+TokenInformation]; void **
0x18002385e  mov     r8d, 800h; unsigned __int64
0x180023864  mov     [rbp+TokenInformation], 0
0x18002386c  mov     [rbp+TokenInformationLength], r8d
0x180023870  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180023875  mov     ebx, eax
0x180023877  test    eax, eax
0x180023879  js      loc_18002391B
0x18002387f  mov     rdi, [rbp+TokenInformation]
0x180023883  lea     rax, [rbp+TokenInformationLength]
0x180023887  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002388b  mov     r8, rdi; TokenInformation
0x18002388e  mov     edx, 1; TokenInformationClass
0x180023893  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180023898  mov     rcx, r14; TokenHandle
0x18002389b  call    cs:__imp_GetTokenInformation
0x1800238a1  test    eax, eax
0x1800238a3  jnz     short loc_180023918
0x1800238a5  call    cs:__imp_GetLastError
0x1800238ab  mov     ebx, eax
0x1800238ad  cmp     eax, 7Ah ; 'z'
0x1800238b0  jnz     short loc_1800238FC
0x1800238b2  mov     rcx, rdi; hMem
0x1800238b5  call    cs:__imp_LocalFree
0x1800238bb  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x1800238bf  lea     r9, [rbp+TokenInformation]; void **
0x1800238c3  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800238c8  mov     rdi, [rbp+TokenInformation]
0x1800238cc  mov     ebx, eax
0x1800238ce  test    eax, eax
0x1800238d0  js      short loc_18002390D
0x1800238d2  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800238d6  lea     rax, [rbp+TokenInformationLength]
0x1800238da  mov     r8, rdi; TokenInformation
0x1800238dd  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800238e2  mov     edx, 1; TokenInformationClass
0x1800238e7  mov     rcx, r14; TokenHandle
0x1800238ea  call    cs:__imp_GetTokenInformation
0x1800238f0  test    eax, eax
0x1800238f2  jnz     short loc_180023918
0x1800238f4  call    cs:__imp_GetLastError
0x1800238fa  mov     ebx, eax
0x1800238fc  test    eax, eax
0x1800238fe  jle     short loc_180023909
0x180023900  movzx   ebx, ax
0x180023903  or      ebx, 80070000h
0x180023909  test    ebx, ebx
0x18002390b  jns     short loc_180023918
0x18002390d  mov     rcx, rdi; hMem
0x180023910  call    cs:__imp_LocalFree
0x180023916  jmp     short loc_18002391B
0x180023918  mov     [rsi], rdi
0x18002391b  mov     rcx, [rbp+TokenHandle]; hObject
0x18002391f  test    rcx, rcx
0x180023922  jz      short loc_18002392A
0x180023924  call    cs:__imp_CloseHandle
0x18002392a  mov     eax, ebx
0x18002392c  add     rsp, 30h
0x180023930  pop     r14
0x180023932  pop     rdi
0x180023933  pop     rsi
0x180023934  pop     rbx
0x180023935  pop     rbp
0x180023936  retn
```
