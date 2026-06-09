# ATL::CSecurityDescriptor::GetTokenSids(void *,void * *,void * *)

- ea: `0x140020ff8`
- end: `0x14002119f`
- name: `?GetTokenSids@CSecurityDescriptor@ATL@@SAJPEAXPEAPEAX1@Z`
- size: `423`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400218d0`

## callees

- `0x14001d4e8`
- `0x14001d50c`
- `0x14001d874`
- `0x140020ff8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400210a7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140021144`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140021168`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002117d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400210a7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140021144`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140021168`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14002117d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140021061`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400210fe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140021061`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400210fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400210ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400210ef`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002104c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140021086`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400210e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140021123`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002104c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140021086`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400210e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140021123`

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
0x140020ff8  mov     [rsp+arg_0], rbx
0x140020ffd  mov     [rsp+arg_10], rbp
0x140021002  push    rsi
0x140021003  push    rdi
0x140021004  push    r14
0x140021006  sub     rsp, 30h
0x14002100a  xor     ebx, ebx
0x14002100c  mov     [rsp+48h+TokenInformationLength], 0
0x140021014  mov     rdi, r8
0x140021017  mov     rsi, rdx
0x14002101a  mov     rbp, rcx
0x14002101d  test    rdx, rdx
0x140021020  jz      short loc_140021025
0x140021022  mov     [rdx], rbx
0x140021025  test    rdi, rdi
0x140021028  jz      short loc_14002102D
0x14002102a  mov     [r8], rbx
0x14002102d  test    rsi, rsi
0x140021030  jz      loc_1400210C7
0x140021036  xor     r9d, r9d; TokenInformationLength
0x140021039  lea     rax, [rsp+48h+TokenInformationLength]
0x14002103e  xor     r8d, r8d; TokenInformation
0x140021041  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140021046  lea     ebx, [r9+1]
0x14002104a  mov     edx, ebx; TokenInformationClass
0x14002104c  call    cs:__imp_GetTokenInformation
0x140021052  call    cs:__imp_GetLastError
0x140021058  cmp     eax, 7Ah ; 'z'
0x14002105b  jnz     short loc_1400210B6
0x14002105d  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x140021061  call    cs:__imp_malloc
0x140021067  mov     r14, rax
0x14002106a  test    rax, rax
0x14002106d  jz      short loc_1400210AF
0x14002106f  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x140021074  lea     rax, [rsp+48h+TokenInformationLength]
0x140021079  mov     r8, r14; TokenInformation
0x14002107c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140021081  mov     edx, ebx; TokenInformationClass
0x140021083  mov     rcx, rbp; TokenHandle
0x140021086  call    cs:__imp_GetTokenInformation
0x14002108c  test    eax, eax
0x14002108e  jz      short loc_14002109D
0x140021090  mov     rdx, [r14]; void *
0x140021093  mov     rcx, rsi; void **
0x140021096  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x14002109b  jmp     short loc_1400210A2
0x14002109d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400210a2  mov     rcx, r14; Block
0x1400210a5  mov     ebx, eax
0x1400210a7  call    cs:__imp_free
0x1400210ad  jmp     short loc_1400210BF
0x1400210af  mov     ebx, 8007000Eh
0x1400210b4  jmp     short loc_1400210BF
0x1400210b6  mov     ecx, eax; unsigned int
0x1400210b8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400210bd  mov     ebx, eax
0x1400210bf  test    ebx, ebx
0x1400210c1  js      loc_140021165
0x1400210c7  test    rdi, rdi
0x1400210ca  jz      loc_14002118A
0x1400210d0  xor     r9d, r9d; TokenInformationLength
0x1400210d3  lea     rax, [rsp+48h+TokenInformationLength]
0x1400210d8  xor     r8d, r8d; TokenInformation
0x1400210db  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1400210e0  mov     rcx, rbp; TokenHandle
0x1400210e3  lea     ebx, [r9+5]
0x1400210e7  mov     edx, ebx; TokenInformationClass
0x1400210e9  call    cs:__imp_GetTokenInformation
0x1400210ef  call    cs:__imp_GetLastError
0x1400210f5  cmp     eax, 7Ah ; 'z'
0x1400210f8  jnz     short loc_140021153
0x1400210fa  mov     ecx, [rsp+48h+TokenInformationLength]; Size
0x1400210fe  call    cs:__imp_malloc
0x140021104  mov     r14, rax
0x140021107  test    rax, rax
0x14002110a  jz      short loc_14002114C
0x14002110c  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x140021111  lea     rax, [rsp+48h+TokenInformationLength]
0x140021116  mov     r8, r14; TokenInformation
0x140021119  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x14002111e  mov     edx, ebx; TokenInformationClass
0x140021120  mov     rcx, rbp; TokenHandle
0x140021123  call    cs:__imp_GetTokenInformation
0x140021129  test    eax, eax
0x14002112b  jz      short loc_14002113A
0x14002112d  mov     rdx, [r14]; void *
0x140021130  mov     rcx, rdi; void **
0x140021133  call    ?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z; ATL::CSecurityDescriptor::CloneSID(void * *,void *)
0x140021138  jmp     short loc_14002113F
0x14002113a  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14002113f  mov     rcx, r14; Block
0x140021142  mov     ebx, eax
0x140021144  call    cs:__imp_free
0x14002114a  jmp     short loc_14002115C
0x14002114c  mov     ebx, 8007000Eh
0x140021151  jmp     short loc_14002115C
0x140021153  mov     ecx, eax; unsigned int
0x140021155  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002115a  mov     ebx, eax
0x14002115c  test    ebx, ebx
0x14002115e  jns     short loc_14002118A
0x140021160  test    rsi, rsi
0x140021163  jz      short loc_14002117A
0x140021165  mov     rcx, [rsi]; Block
0x140021168  call    cs:__imp_free
0x14002116e  mov     qword ptr [rsi], 0
0x140021175  test    rdi, rdi
0x140021178  jz      short loc_14002118A
0x14002117a  mov     rcx, [rdi]; Block
0x14002117d  call    cs:__imp_free
0x140021183  mov     qword ptr [rdi], 0
0x14002118a  mov     rbp, [rsp+48h+arg_10]
0x14002118f  mov     eax, ebx
0x140021191  mov     rbx, [rsp+48h+arg_0]
0x140021196  add     rsp, 30h
0x14002119a  pop     r14
0x14002119c  pop     rdi
0x14002119d  pop     rsi
0x14002119e  retn
```
