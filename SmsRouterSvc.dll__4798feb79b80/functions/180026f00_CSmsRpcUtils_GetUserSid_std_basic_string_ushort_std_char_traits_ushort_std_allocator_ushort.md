# CSmsRpcUtils::GetUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180026f00`
- end: `0x1800270a7`
- name: `?GetUserSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180009b60`
- `0x180009d50`
- `0x180009f60`
- `0x18000a0c0`
- `0x18000a560`
- `0x18000a6e0`
- `0x18000ab70`
- `0x18000fd94`
- `0x180026640`
- `0x18003c580`

## callees

- `0x180003f50`
- `0x18000498c`
- `0x18000659c`
- `0x180026f00`
- `0x18002723c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027078`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027078`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026f85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026f85`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026f66`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026fa8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026f66`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026fa8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026fbd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026fbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
signed int __fastcall CSmsRpcUtils::GetUserSid(__int64 a1)
{
  PSID *v2; // rbx
  HANDLE v3; // rsi
  signed int result; // eax
  HANDLE v5; // r14
  __int64 v6; // r8
  BOOL v7; // eax
  PSID *v8; // rdi
  HANDLE v9; // rax
  PSID *v10; // r12
  unsigned __int64 v11; // rdx
  char *v12; // r15
  __int64 v13; // rdi
  DWORD TokenInformationLength; // [rsp+88h] [rbp+48h] BYREF
  HANDLE TokenHandle; // [rsp+90h] [rbp+50h] BYREF
  PSID *v16; // [rsp+98h] [rbp+58h]

  TokenInformationLength = 0;
  v2 = 0;
  v16 = 0;
  v3 = 0;
  TokenHandle = 0;
  result = ImpersonateAndGetToken(&TokenHandle);
  if ( result < 0 )
    return result;
  v5 = TokenHandle;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v3 = 0;
    v10 = 0;
    goto LABEL_19;
  }
  if ( GetLastError() != 122 )
  {
    v8 = 0;
    goto LABEL_10;
  }
  v2 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  v16 = v2;
  if ( !GetTokenInformation(v5, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
  {
    v8 = v2;
LABEL_10:
    v9 = 0;
    goto LABEL_11;
  }
  TokenHandle = 0;
  v7 = ConvertSidToStringSidW(*v2, (LPWSTR *)&TokenHandle);
  v3 = TokenHandle;
  if ( !v7 )
  {
    v8 = v2;
    v9 = TokenHandle;
LABEL_11:
    if ( v9 )
      operator delete(v3);
    if ( v8 )
      LocalFree(v2);
    if ( v5 )
      CloseHandle(v5);
    return -2147467259;
  }
  v10 = v2;
LABEL_19:
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)v3 + v11) );
  if ( v11 > *(_QWORD *)(a1 + 24) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      (char **)a1,
      v11,
      v6,
      v3);
  }
  else
  {
    if ( *(_QWORD *)(a1 + 24) <= 7u )
      v12 = (char *)a1;
    else
      v12 = *(char **)a1;
    *(_QWORD *)(a1 + 16) = v11;
    v13 = 2 * v11;
    memmove_0(v12, v3, 2 * v11);
    *(_WORD *)&v12[v13] = 0;
  }
  if ( v10 )
    LocalFree(v2);
  if ( v5 )
    CloseHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x180026f00  mov     [rsp-38h+arg_0], rbx
0x180026f05  push    rbp
0x180026f06  push    rsi
0x180026f07  push    rdi
0x180026f08  push    r12
0x180026f0a  push    r13
0x180026f0c  push    r14
0x180026f0e  push    r15
0x180026f10  mov     rbp, rsp
0x180026f13  sub     rsp, 40h
0x180026f17  mov     rdi, rcx
0x180026f1a  xor     r13d, r13d
0x180026f1d  mov     [rbp+TokenInformationLength], r13d
0x180026f21  mov     ebx, r13d
0x180026f24  mov     [rbp+arg_18], rbx
0x180026f28  mov     esi, r13d
0x180026f2b  mov     [rbp+var_10], r13
0x180026f2f  mov     [rbp+TokenHandle], r13
0x180026f33  lea     rcx, [rbp+TokenHandle]; void **
0x180026f37  call    ?ImpersonateAndGetToken@@YAJPEAPEAX@Z; ImpersonateAndGetToken(void * *)
0x180026f3c  test    eax, eax
0x180026f3e  jns     short loc_180026F45
0x180026f40  jmp     loc_18002708F
0x180026f45  mov     r14, [rbp+TokenHandle]
0x180026f49  mov     [rbp+var_8], r14
0x180026f4d  lea     rax, [rbp+TokenInformationLength]
0x180026f51  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180026f56  xor     r9d, r9d; TokenInformationLength
0x180026f59  xor     r8d, r8d; TokenInformation
0x180026f5c  lea     r15d, [r9+1]
0x180026f60  mov     edx, r15d; TokenInformationClass
0x180026f63  mov     rcx, r14; TokenHandle
0x180026f66  call    cs:__imp_GetTokenInformation
0x180026f6c  test    eax, eax
0x180026f6e  jnz     loc_18002701E
0x180026f74  call    cs:__imp_GetLastError
0x180026f7a  cmp     eax, 7Ah ; 'z'
0x180026f7d  jnz     short loc_180026FE1
0x180026f7f  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180026f82  lea     ecx, [rax-3Ah]; uFlags
0x180026f85  call    cs:__imp_LocalAlloc
0x180026f8b  mov     rbx, rax
0x180026f8e  mov     [rbp+arg_18], rax
0x180026f92  lea     rax, [rbp+TokenInformationLength]
0x180026f96  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180026f9b  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180026f9f  mov     r8, rbx; TokenInformation
0x180026fa2  mov     edx, r15d; TokenInformationClass
0x180026fa5  mov     rcx, r14; TokenHandle
0x180026fa8  call    cs:__imp_GetTokenInformation
0x180026fae  test    eax, eax
0x180026fb0  jz      short loc_180026FDC
0x180026fb2  mov     [rbp+TokenHandle], r13
0x180026fb6  lea     rdx, [rbp+TokenHandle]; StringSid
0x180026fba  mov     rcx, [rbx]; Sid
0x180026fbd  call    cs:__imp_ConvertSidToStringSidW
0x180026fc3  mov     rsi, [rbp+TokenHandle]
0x180026fc7  mov     [rbp+var_10], rsi
0x180026fcb  test    eax, eax
0x180026fcd  jnz     short loc_180026FD7
0x180026fcf  mov     rdi, rbx
0x180026fd2  mov     rax, rsi
0x180026fd5  jmp     short loc_180026FE7
0x180026fd7  mov     r12, rbx
0x180026fda  jmp     short loc_180027024
0x180026fdc  mov     rdi, rbx
0x180026fdf  jmp     short loc_180026FE4
0x180026fe1  mov     rdi, r13
0x180026fe4  mov     rax, r13
0x180026fe7  test    rax, rax
0x180026fea  jz      short loc_180026FFA
0x180026fec  mov     edx, 2
0x180026ff1  mov     rcx, rsi; Block
0x180026ff4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026ff9  nop
0x180026ffa  test    rdi, rdi
0x180026ffd  jz      short loc_180027009
0x180026fff  mov     rcx, rbx; hMem
0x180027002  call    cs:__imp_LocalFree
0x180027008  nop
0x180027009  test    r14, r14
0x18002700c  jz      short loc_180027017
0x18002700e  mov     rcx, r14; hObject
0x180027011  call    cs:__imp_CloseHandle
0x180027017  mov     eax, 80004005h
0x18002701c  jmp     short loc_18002708F
0x18002701e  mov     rsi, r13
0x180027021  mov     r12, r13
0x180027024  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180027028  inc     rdx
0x18002702b  cmp     [rsi+rdx*2], r13w
0x180027030  jnz     short loc_180027028
0x180027032  cmp     rdx, [rdi+18h]
0x180027036  ja      short loc_180027064
0x180027038  cmp     qword ptr [rdi+18h], 7
0x18002703d  jbe     short loc_180027044
0x18002703f  mov     r15, [rdi]
0x180027042  jmp     short loc_180027047
0x180027044  mov     r15, rdi
0x180027047  mov     [rdi+10h], rdx
0x18002704b  lea     rdi, [rdx+rdx]
0x18002704f  mov     r8, rdi; Size
0x180027052  mov     rdx, rsi; Src
0x180027055  mov     rcx, r15; void *
0x180027058  call    memmove_0
0x18002705d  mov     [rdi+r15], r13w
0x180027062  jmp     short loc_180027070
0x180027064  mov     r9, rsi
0x180027067  mov     rcx, rdi
0x18002706a  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002706f  nop
0x180027070  test    r12, r12
0x180027073  jz      short loc_18002707F
0x180027075  mov     rcx, rbx; hMem
0x180027078  call    cs:__imp_LocalFree
0x18002707e  nop
0x18002707f  test    r14, r14
0x180027082  jz      short loc_18002708D
0x180027084  mov     rcx, r14; hObject
0x180027087  call    cs:__imp_CloseHandle
0x18002708d  xor     eax, eax
0x18002708f  mov     rbx, [rsp+40h+arg_0]
0x180027097  add     rsp, 40h
0x18002709b  pop     r15
0x18002709d  pop     r14
0x18002709f  pop     r13
0x1800270a1  pop     r12
0x1800270a3  pop     rdi
0x1800270a4  pop     rsi
0x1800270a5  pop     rbp
0x1800270a6  retn
```
