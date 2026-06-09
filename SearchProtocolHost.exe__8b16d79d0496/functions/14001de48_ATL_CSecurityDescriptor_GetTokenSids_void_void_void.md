# ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)

- ea: `0x14001de48`
- end: `0x14001dfef`
- name: `?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001ef3c`

## callees

- `0x1400124cc`
- `0x1400124f0`
- `0x140012ac4`
- `0x14001de48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001def7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001df94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001dfb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001dfcd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001def7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001df94`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001dfb8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001dfcd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001deb1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001df4e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001deb1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001df4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001de9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001ded6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001df39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001df73`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001de9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001ded6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001df39`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001df73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001df3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001df3f`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::GetTokenSids(HANDLE TokenHandle, void **a2, void **a3)
{
  int v3; // ebx
  DWORD LastError; // eax
  void **v8; // r14
  int v9; // eax
  DWORD v10; // eax
  void **v11; // r14
  int v12; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  TokenInformationLength = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 )
    goto LABEL_24;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v8 = (void **)malloc(TokenInformationLength);
    if ( v8 )
    {
      v9 = GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength)
         ? ATL::CSecurityDescriptor::CloneSID(a2, *v8)
         : ResultFromLastError();
      v3 = v9;
      free(v8);
    }
    else
    {
      v3 = -2147024882;
    }
  }
  else
  {
    v3 = ATL::AtlHresultFromWin32(LastError);
  }
  if ( v3 >= 0 )
  {
LABEL_24:
    if ( !a3 )
      return (unsigned int)v3;
    GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &TokenInformationLength);
    v10 = GetLastError();
    if ( v10 == 122 )
    {
      v11 = (void **)malloc(TokenInformationLength);
      if ( v11 )
      {
        v12 = GetTokenInformation(TokenHandle, TokenPrimaryGroup, v11, TokenInformationLength, &TokenInformationLength)
            ? ATL::CSecurityDescriptor::CloneSID(a3, *v11)
            : ResultFromLastError();
        v3 = v12;
        free(v11);
      }
      else
      {
        v3 = -2147024882;
      }
    }
    else
    {
      v3 = ATL::AtlHresultFromWin32(v10);
    }
    if ( v3 >= 0 )
      return (unsigned int)v3;
    if ( !a2 )
    {
LABEL_27:
      free(*a3);
      *a3 = 0;
      return (unsigned int)v3;
    }
  }
  free(*a2);
  *a2 = 0;
  if ( a3 )
    goto LABEL_27;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001de48  mov     [rsp+arg_0], rbx
0x14001de4d  mov     [rsp+arg_10], rbp
0x14001de52  push    rsi
0x14001de53  push    rdi
0x14001de54  push    r14
0x14001de56  sub     rsp, 30h
0x14001de5a  xor     ebx, ebx
0x14001de5c  mov     [rsp+48h+TokenInformationLength], 0
0x14001de64  mov     rdi, r8
0x14001de67  mov     rsi, rdx
0x14001de6a  mov     rbp, rcx
0x14001de6d  test    rdx, rdx
0x14001de70  jz      short loc_14001DE75
0x14001de72  mov     [rdx], rbx
0x14001de75  test    rdi, rdi
0x14001de78  jz      short loc_14001DE7D
0x14001de7a  mov     [r8], rbx
0x14001de7d  test    rsi, rsi
0x14001de80  jz      loc_14001DF17
0x14001de86  xor     r9d, r9d; TokenInformationLength
0x14001de89  lea     rax, [rsp+48h+TokenInformationLength]
0x14001de8e  xor     r8d, r8d; TokenInformation
0x14001de91  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001de96  lea     ebx, [r9+1]
0x14001de9a  mov     edx, ebx; TokenInformationClass
0x14001de9c  call    cs:__imp_GetTokenInformation
0x14001dea2  call    cs:__imp_GetLastError
0x14001dea8  cmp     eax, 7Ah ; 'z'
0x14001deab  jnz     short loc_14001DF06
0x14001dead  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x14001deb1  call    cs:__imp_malloc
0x14001deb7  mov     r14, rax
0x14001deba  test    rax, rax
0x14001debd  jz      short loc_14001DEFF
0x14001debf  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x14001dec4  lea     rax, [rsp+48h+TokenInformationLength]
0x14001dec9  mov     r8, r14; TokenInformation
0x14001decc  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001ded1  mov     edx, ebx; TokenInformationClass
0x14001ded3  mov     rcx, rbp; TokenHandle
0x14001ded6  call    cs:__imp_GetTokenInformation
0x14001dedc  test    eax, eax
0x14001dede  jz      short loc_14001DEED
0x14001dee0  mov     rdx, [r14]; void *
0x14001dee3  mov     rcx, rsi; void **
0x14001dee6  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x14001deeb  jmp     short loc_14001DEF2
0x14001deed  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001def2  mov     rcx, r14; Block
0x14001def5  mov     ebx, eax
0x14001def7  call    cs:__imp_free
0x14001defd  jmp     short loc_14001DF0F
0x14001deff  mov     ebx, 8007000Eh
0x14001df04  jmp     short loc_14001DF0F
0x14001df06  mov     ecx, eax; unsigned int
0x14001df08  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001df0d  mov     ebx, eax
0x14001df0f  test    ebx, ebx
0x14001df11  js      loc_14001DFB5
0x14001df17  test    rdi, rdi
0x14001df1a  jz      loc_14001DFDA
0x14001df20  xor     r9d, r9d; TokenInformationLength
0x14001df23  lea     rax, [rsp+48h+TokenInformationLength]
0x14001df28  xor     r8d, r8d; TokenInformation
0x14001df2b  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001df30  mov     rcx, rbp; TokenHandle
0x14001df33  lea     ebx, [r9+5]
0x14001df37  mov     edx, ebx; TokenInformationClass
0x14001df39  call    cs:__imp_GetTokenInformation
0x14001df3f  call    cs:__imp_GetLastError
0x14001df45  cmp     eax, 7Ah ; 'z'
0x14001df48  jnz     short loc_14001DFA3
0x14001df4a  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x14001df4e  call    cs:__imp_malloc
0x14001df54  mov     r14, rax
0x14001df57  test    rax, rax
0x14001df5a  jz      short loc_14001DF9C
0x14001df5c  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x14001df61  lea     rax, [rsp+48h+TokenInformationLength]
0x14001df66  mov     r8, r14; TokenInformation
0x14001df69  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14001df6e  mov     edx, ebx; TokenInformationClass
0x14001df70  mov     rcx, rbp; TokenHandle
0x14001df73  call    cs:__imp_GetTokenInformation
0x14001df79  test    eax, eax
0x14001df7b  jz      short loc_14001DF8A
0x14001df7d  mov     rdx, [r14]; void *
0x14001df80  mov     rcx, rdi; void **
0x14001df83  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x14001df88  jmp     short loc_14001DF8F
0x14001df8a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001df8f  mov     rcx, r14; Block
0x14001df92  mov     ebx, eax
0x14001df94  call    cs:__imp_free
0x14001df9a  jmp     short loc_14001DFAC
0x14001df9c  mov     ebx, 8007000Eh
0x14001dfa1  jmp     short loc_14001DFAC
0x14001dfa3  mov     ecx, eax; unsigned int
0x14001dfa5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001dfaa  mov     ebx, eax
0x14001dfac  test    ebx, ebx
0x14001dfae  jns     short loc_14001DFDA
0x14001dfb0  test    rsi, rsi
0x14001dfb3  jz      short loc_14001DFCA
0x14001dfb5  mov     rcx, [rsi]; Block
0x14001dfb8  call    cs:__imp_free
0x14001dfbe  mov     qword ptr [rsi], 0
0x14001dfc5  test    rdi, rdi
0x14001dfc8  jz      short loc_14001DFDA
0x14001dfca  mov     rcx, [rdi]; Block
0x14001dfcd  call    cs:__imp_free
0x14001dfd3  mov     qword ptr [rdi], 0
0x14001dfda  mov     rbp, [rsp+48h+arg_10]
0x14001dfdf  mov     eax, ebx
0x14001dfe1  mov     rbx, [rsp+48h+arg_0]
0x14001dfe6  add     rsp, 30h
0x14001dfea  pop     r14
0x14001dfec  pop     rdi
0x14001dfed  pop     rsi
0x14001dfee  retn
```
