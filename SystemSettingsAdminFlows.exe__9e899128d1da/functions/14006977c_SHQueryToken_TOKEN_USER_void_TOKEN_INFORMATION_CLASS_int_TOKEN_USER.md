# SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)

- ea: `0x14006977c`
- end: `0x14006989c`
- name: `??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(void *, __int64, DWORD, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140024fd4`

## callees

- `0x14006977c`
- `0x1400698a4`
- `0x1400698d8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14006981a`
- `KERNEL32!LocalFree` at `0x140069875`
- `KERNEL32!LocalFree` at `0x14006981a`
- `KERNEL32!LocalFree` at `0x140069875`
- `KERNEL32!CloseHandle` at `0x140069889`
- `KERNEL32!CloseHandle` at `0x140069889`
- `KERNEL32!GetLastError` at `0x14006980a`
- `KERNEL32!GetLastError` at `0x140069859`
- `KERNEL32!GetLastError` at `0x14006980a`
- `KERNEL32!GetLastError` at `0x140069859`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140069800`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006984f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140069800`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006984f`

## pseudocode

```c
__int64 __fastcall SHQueryToken<_TOKEN_USER>(void *a1, __int64 a2, DWORD a3, _QWORD *a4)
{
  __int64 result; // rax
  unsigned int v6; // edx
  void *v7; // rcx
  HANDLE v8; // rsi
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
  result = SHOpenEffectiveToken(8u, 0, &TokenHandle);
  if ( (int)result < 0 )
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
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14006977c  mov     [rsp-28h+TokenInformationLength], r8d
0x140069781  mov     [rsp-28h+TokenInformation], rcx
0x140069786  push    rbp
0x140069787  push    rbx
0x140069788  push    rsi
0x140069789  push    rdi
0x14006978a  push    r14
0x14006978c  mov     rbp, rsp
0x14006978f  sub     rsp, 30h
0x140069793  xor     edx, edx; int
0x140069795  mov     qword ptr [r9], 0
0x14006979c  lea     r8, [rbp+TokenHandle]; void **
0x1400697a0  mov     [rbp+TokenHandle], 0
0x1400697a8  mov     r14, r9
0x1400697ab  lea     ecx, [rdx+8]; DesiredAccess
0x1400697ae  call    ?SHOpenEffectiveToken@@YAJKHPEAPEAX@Z; SHOpenEffectiveToken(ulong,int,void * *)
0x1400697b3  test    eax, eax
0x1400697b5  js      loc_140069891
0x1400697bb  mov     rsi, [rbp+TokenHandle]
0x1400697bf  lea     r9, [rbp+TokenInformation]; void **
0x1400697c3  mov     r8d, 800h; unsigned __int64
0x1400697c9  mov     [rbp+TokenInformation], 0
0x1400697d1  mov     [rbp+TokenInformationLength], r8d
0x1400697d5  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1400697da  mov     ebx, eax
0x1400697dc  test    eax, eax
0x1400697de  js      loc_140069880
0x1400697e4  mov     rdi, [rbp+TokenInformation]
0x1400697e8  lea     rax, [rbp+TokenInformationLength]
0x1400697ec  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1400697f0  mov     r8, rdi; TokenInformation
0x1400697f3  mov     edx, 1; TokenInformationClass
0x1400697f8  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1400697fd  mov     rcx, rsi; TokenHandle
0x140069800  call    cs:__imp_GetTokenInformation
0x140069806  test    eax, eax
0x140069808  jnz     short loc_14006987D
0x14006980a  call    cs:__imp_GetLastError
0x140069810  mov     ebx, eax
0x140069812  cmp     eax, 7Ah ; 'z'
0x140069815  jnz     short loc_140069861
0x140069817  mov     rcx, rdi; hMem
0x14006981a  call    cs:__imp_LocalFree
0x140069820  mov     r8d, [rbp+TokenInformationLength]; unsigned __int64
0x140069824  lea     r9, [rbp+TokenInformation]; void **
0x140069828  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x14006982d  mov     rdi, [rbp+TokenInformation]
0x140069831  mov     ebx, eax
0x140069833  test    eax, eax
0x140069835  js      short loc_140069872
0x140069837  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14006983b  lea     rax, [rbp+TokenInformationLength]
0x14006983f  mov     r8, rdi; TokenInformation
0x140069842  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x140069847  mov     edx, 1; TokenInformationClass
0x14006984c  mov     rcx, rsi; TokenHandle
0x14006984f  call    cs:__imp_GetTokenInformation
0x140069855  test    eax, eax
0x140069857  jnz     short loc_14006987D
0x140069859  call    cs:__imp_GetLastError
0x14006985f  mov     ebx, eax
0x140069861  test    eax, eax
0x140069863  jle     short loc_14006986E
0x140069865  movzx   ebx, ax
0x140069868  or      ebx, 80070000h
0x14006986e  test    ebx, ebx
0x140069870  jns     short loc_14006987D
0x140069872  mov     rcx, rdi; hMem
0x140069875  call    cs:__imp_LocalFree
0x14006987b  jmp     short loc_140069880
0x14006987d  mov     [r14], rdi
0x140069880  mov     rcx, [rbp+TokenHandle]; hObject
0x140069884  test    rcx, rcx
0x140069887  jz      short loc_14006988F
0x140069889  call    cs:__imp_CloseHandle
0x14006988f  mov     eax, ebx
0x140069891  add     rsp, 30h
0x140069895  pop     r14
0x140069897  pop     rdi
0x140069898  pop     rsi
0x140069899  pop     rbx
0x14006989a  pop     rbp
0x14006989b  retn
```
