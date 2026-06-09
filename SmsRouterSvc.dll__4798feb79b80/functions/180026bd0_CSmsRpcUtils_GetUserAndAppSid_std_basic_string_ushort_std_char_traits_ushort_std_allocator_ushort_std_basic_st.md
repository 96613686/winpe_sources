# CSmsRpcUtils::GetUserAndAppSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180026bd0`
- end: `0x180026ef7`
- name: `?GetUserAndAppSid@CSmsRpcUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `807`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800267f8`

## callees

- `0x180003f50`
- `0x18000498c`
- `0x18000659c`
- `0x180026bd0`
- `0x18002723c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ed7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026dc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026ed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026da6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026eb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026da6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026db5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026eb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ec8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026c6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026d26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026c6d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026d26`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026c4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026ce6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026d4b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026c4a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026ce6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026d4b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026cab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026d60`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026cab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026d60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsRpcUtils::GetUserAndAppSid(void **a1, void **a2)
{
  PSID *v3; // rbx
  PSID *v4; // rsi
  HANDLE v5; // rdi
  HANDLE v6; // r14
  __int64 result; // rax
  HANDLE v8; // r15
  BOOL v9; // eax
  BOOL v10; // eax
  PSID *v11; // rsi
  HANDLE v12; // rax
  BOOL v13; // eax
  bool v14; // zf
  unsigned __int64 v15; // r12
  unsigned __int64 v16; // rdx
  void *v17; // r9
  void *v18; // rcx
  __int64 v19; // rdi
  const OLECHAR *v20; // r9
  void *v21; // r14
  HANDLE TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  void *Src; // [rsp+38h] [rbp-38h]
  HANDLE v24; // [rsp+40h] [rbp-30h]
  PSID *v25; // [rsp+48h] [rbp-28h]
  PSID *v26; // [rsp+50h] [rbp-20h]
  HANDLE v27; // [rsp+58h] [rbp-18h]
  HANDLE v28; // [rsp+60h] [rbp-10h]
  DWORD TokenInformationLength; // [rsp+C0h] [rbp+50h] BYREF
  int TokenInformation; // [rsp+C8h] [rbp+58h] BYREF

  TokenInformation = 0;
  TokenInformationLength = 0;
  TokenHandle = 0;
  v3 = 0;
  v25 = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v24 = 0;
  v6 = 0;
  v27 = 0;
  result = ImpersonateAndGetToken(&TokenHandle);
  if ( (int)result < 0 )
    return result;
  v8 = TokenHandle;
  v28 = TokenHandle;
  v9 = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  Src = 0;
  if ( v9 )
    goto LABEL_8;
  if ( GetLastError() != 122 )
  {
    v11 = 0;
    goto LABEL_27;
  }
  v3 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
  v25 = v3;
  if ( !GetTokenInformation(v8, TokenUser, v3, TokenInformationLength, &TokenInformationLength) )
  {
    v11 = v3;
LABEL_27:
    v12 = 0;
    goto LABEL_28;
  }
  TokenHandle = 0;
  v10 = ConvertSidToStringSidW(*v3, (LPWSTR *)&TokenHandle);
  v5 = TokenHandle;
  v24 = TokenHandle;
  if ( !v10 )
  {
    v11 = v3;
    v12 = TokenHandle;
LABEL_28:
    if ( v12 )
      operator delete(v5);
    v14 = v11 == 0;
LABEL_20:
    if ( !v14 )
      LocalFree(v3);
    if ( v8 )
      CloseHandle(v8);
    return 2147500037LL;
  }
  Src = TokenHandle;
LABEL_8:
  if ( GetTokenInformation(v8, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength) )
  {
    if ( TokenInformation )
    {
      if ( !GetTokenInformation(v8, TokenAppContainerSid, 0, 0, &TokenInformationLength)
        || (v4 = (PSID *)LocalAlloc(0x40u, TokenInformationLength),
            v26 = v4,
            !GetTokenInformation(v8, TokenAppContainerSid, v4, TokenInformationLength, &TokenInformationLength))
        || (TokenHandle = 0,
            v13 = ConvertSidToStringSidW(*v4, (LPWSTR *)&TokenHandle),
            v6 = TokenHandle,
            v27 = TokenHandle,
            !v13) )
      {
        if ( v6 )
          operator delete(v6);
        if ( v5 )
          operator delete(v5);
        if ( v4 )
          LocalFree(v4);
        v14 = v3 == 0;
        goto LABEL_20;
      }
    }
  }
  v15 = -1;
  v16 = -1;
  v17 = Src;
  do
    ++v16;
  while ( *((_WORD *)Src + v16) );
  if ( v16 > (unsigned __int64)a1[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a1);
  }
  else
  {
    if ( (unsigned __int64)a1[3] <= 7 )
      v18 = a1;
    else
      v18 = *a1;
    Src = v18;
    a1[2] = (void *)v16;
    v19 = 2 * v16;
    memmove_0(v18, v17, 2 * v16);
    *(_WORD *)((char *)Src + v19) = 0;
  }
  v24 = 0;
  v20 = &LocaleName;
  if ( v6 )
    v20 = (const OLECHAR *)v6;
  do
    ++v15;
  while ( v20[v15] );
  if ( v15 > (unsigned __int64)a2[3] )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(a2);
  }
  else
  {
    if ( (unsigned __int64)a2[3] <= 7 )
      v21 = a2;
    else
      v21 = *a2;
    a2[2] = (void *)v15;
    memmove_0(v21, v20, 2 * v15);
    *((_WORD *)v21 + v15) = 0;
  }
  if ( v4 )
    LocalFree(v4);
  if ( v3 )
    LocalFree(v3);
  if ( v8 )
    CloseHandle(v8);
  return 0;
}

```

## disassembly

```asm
0x180026bd0  mov     [rsp-38h+arg_8], rbx
0x180026bd5  mov     [rsp-38h+arg_0], rcx
0x180026bda  push    rbp
0x180026bdb  push    rsi
0x180026bdc  push    rdi
0x180026bdd  push    r12
0x180026bdf  push    r13
0x180026be1  push    r14
0x180026be3  push    r15
0x180026be5  mov     rbp, rsp
0x180026be8  sub     rsp, 70h
0x180026bec  mov     r13, rdx
0x180026bef  xor     r12d, r12d
0x180026bf2  mov     [rbp+TokenInformation], r12d
0x180026bf6  mov     [rbp+TokenInformationLength], r12d
0x180026bfa  mov     [rbp+TokenHandle], r12
0x180026bfe  mov     ebx, r12d
0x180026c01  mov     [rbp+var_28], rbx
0x180026c05  mov     esi, r12d
0x180026c08  mov     [rbp+var_20], r12
0x180026c0c  mov     edi, r12d
0x180026c0f  mov     [rbp+var_30], r12
0x180026c13  mov     r14d, r12d
0x180026c16  mov     [rbp+var_18], r12
0x180026c1a  lea     rcx, [rbp+TokenHandle]; void **
0x180026c1e  call    ?ImpersonateAndGetToken@@YAJPEAPEAX@Z; ImpersonateAndGetToken(void * *)
0x180026c23  test    eax, eax
0x180026c25  jns     short loc_180026C2C
0x180026c27  jmp     loc_180026EDF
0x180026c2c  mov     r15, [rbp+TokenHandle]
0x180026c30  mov     [rbp+var_10], r15
0x180026c34  lea     rax, [rbp+TokenInformationLength]
0x180026c38  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026c3d  xor     r9d, r9d; TokenInformationLength
0x180026c40  xor     r8d, r8d; TokenInformation
0x180026c43  lea     edx, [r9+1]; TokenInformationClass
0x180026c47  mov     rcx, r15; TokenHandle
0x180026c4a  call    cs:__imp_GetTokenInformation
0x180026c50  mov     [rbp+Src], r12
0x180026c54  test    eax, eax
0x180026c56  jnz     short loc_180026CCC
0x180026c58  call    cs:__imp_GetLastError
0x180026c5e  cmp     eax, 7Ah ; 'z'
0x180026c61  jnz     loc_180026DD9
0x180026c67  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180026c6a  lea     ecx, [rax-3Ah]; uFlags
0x180026c6d  call    cs:__imp_LocalAlloc
0x180026c73  mov     rbx, rax
0x180026c76  mov     [rbp+var_28], rax
0x180026c7a  lea     rax, [rbp+TokenInformationLength]
0x180026c7e  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026c83  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180026c87  mov     r8, rbx; TokenInformation
0x180026c8a  mov     edx, 1; TokenInformationClass
0x180026c8f  mov     rcx, r15; TokenHandle
0x180026c92  call    cs:__imp_GetTokenInformation
0x180026c98  test    eax, eax
0x180026c9a  jz      loc_180026DD4
0x180026ca0  mov     [rbp+TokenHandle], r12
0x180026ca4  lea     rdx, [rbp+TokenHandle]; StringSid
0x180026ca8  mov     rcx, [rbx]; Sid
0x180026cab  call    cs:__imp_ConvertSidToStringSidW
0x180026cb1  mov     rdi, [rbp+TokenHandle]
0x180026cb5  mov     [rbp+var_30], rdi
0x180026cb9  test    eax, eax
0x180026cbb  jnz     short loc_180026CC8
0x180026cbd  mov     rsi, rbx
0x180026cc0  mov     rax, rdi
0x180026cc3  jmp     loc_180026DDF
0x180026cc8  mov     [rbp+Src], rdi
0x180026ccc  lea     rax, [rbp+TokenInformationLength]
0x180026cd0  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026cd5  mov     r9d, 4; TokenInformationLength
0x180026cdb  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180026cdf  lea     edx, [r9+19h]; TokenInformationClass
0x180026ce3  mov     rcx, r15; TokenHandle
0x180026ce6  call    cs:__imp_GetTokenInformation
0x180026cec  test    eax, eax
0x180026cee  jz      loc_180026DF7
0x180026cf4  cmp     [rbp+TokenInformation], r12d
0x180026cf8  jz      loc_180026DF7
0x180026cfe  lea     rax, [rbp+TokenInformationLength]
0x180026d02  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026d07  xor     r9d, r9d; TokenInformationLength
0x180026d0a  xor     r8d, r8d; TokenInformation
0x180026d0d  lea     edx, [r9+1Fh]; TokenInformationClass
0x180026d11  mov     rcx, r15; TokenHandle
0x180026d14  call    cs:__imp_GetTokenInformation
0x180026d1a  test    eax, eax
0x180026d1c  jz      short loc_180026D76
0x180026d1e  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180026d21  mov     ecx, 40h ; '@'; uFlags
0x180026d26  call    cs:__imp_LocalAlloc
0x180026d2c  mov     rsi, rax
0x180026d2f  mov     [rbp+var_20], rax
0x180026d33  lea     rax, [rbp+TokenInformationLength]
0x180026d37  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180026d3c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180026d40  mov     r8, rsi; TokenInformation
0x180026d43  mov     edx, 1Fh; TokenInformationClass
0x180026d48  mov     rcx, r15; TokenHandle
0x180026d4b  call    cs:__imp_GetTokenInformation
0x180026d51  test    eax, eax
0x180026d53  jz      short loc_180026D76
0x180026d55  mov     [rbp+TokenHandle], r12
0x180026d59  lea     rdx, [rbp+TokenHandle]; StringSid
0x180026d5d  mov     rcx, [rsi]; Sid
0x180026d60  call    cs:__imp_ConvertSidToStringSidW
0x180026d66  mov     r14, [rbp+TokenHandle]
0x180026d6a  mov     [rbp+var_18], r14
0x180026d6e  test    eax, eax
0x180026d70  jnz     loc_180026DF7
0x180026d76  mov     r12d, 2
0x180026d7c  test    r14, r14
0x180026d7f  jz      short loc_180026D8D
0x180026d81  mov     edx, r12d
0x180026d84  mov     rcx, r14; Block
0x180026d87  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026d8c  nop
0x180026d8d  test    rdi, rdi
0x180026d90  jz      short loc_180026D9E
0x180026d92  mov     rdx, r12
0x180026d95  mov     rcx, rdi; Block
0x180026d98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026d9d  nop
0x180026d9e  test    rsi, rsi
0x180026da1  jz      short loc_180026DAD
0x180026da3  mov     rcx, rsi; hMem
0x180026da6  call    cs:__imp_LocalFree
0x180026dac  nop
0x180026dad  test    rbx, rbx
0x180026db0  jz      short loc_180026DBC
0x180026db2  mov     rcx, rbx; hMem
0x180026db5  call    cs:__imp_LocalFree
0x180026dbb  nop
0x180026dbc  test    r15, r15
0x180026dbf  jz      short loc_180026DCA
0x180026dc1  mov     rcx, r15; hObject
0x180026dc4  call    cs:__imp_CloseHandle
0x180026dca  mov     eax, 80004005h
0x180026dcf  jmp     loc_180026EDF
0x180026dd4  mov     rsi, rbx
0x180026dd7  jmp     short loc_180026DDC
0x180026dd9  mov     rsi, r12
0x180026ddc  mov     rax, r12
0x180026ddf  test    rax, rax
0x180026de2  jz      short loc_180026DF2
0x180026de4  mov     edx, 2
0x180026de9  mov     rcx, rdi; Block
0x180026dec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026df1  nop
0x180026df2  test    rsi, rsi
0x180026df5  jmp     short loc_180026DB0
0x180026df7  or      r12, 0FFFFFFFFFFFFFFFFh
0x180026dfb  mov     rdx, r12
0x180026dfe  mov     r9, [rbp+Src]
0x180026e02  xor     edi, edi
0x180026e04  inc     rdx
0x180026e07  cmp     [r9+rdx*2], di
0x180026e0c  jnz     short loc_180026E04
0x180026e0e  mov     rax, [rbp+arg_0]
0x180026e12  cmp     rdx, [rax+18h]
0x180026e16  ja      short loc_180026E4C
0x180026e18  cmp     qword ptr [rax+18h], 7
0x180026e1d  jbe     short loc_180026E24
0x180026e1f  mov     rcx, [rax]
0x180026e22  jmp     short loc_180026E27
0x180026e24  mov     rcx, rax; void *
0x180026e27  mov     [rbp+Src], rcx
0x180026e2b  mov     [rax+10h], rdx
0x180026e2f  lea     rdi, [rdx+rdx]
0x180026e33  mov     r8, rdi; Size
0x180026e36  mov     rdx, r9; Src
0x180026e39  call    memmove_0
0x180026e3e  xor     eax, eax
0x180026e40  mov     rcx, [rbp+Src]
0x180026e44  mov     [rdi+rcx], ax
0x180026e48  xor     edi, edi
0x180026e4a  jmp     short loc_180026E54
0x180026e4c  mov     rcx, rax
0x180026e4f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180026e54  mov     [rbp+var_30], rdi
0x180026e58  lea     r9, LocaleName
0x180026e5f  test    r14, r14
0x180026e62  cmovnz  r9, r14
0x180026e66  inc     r12
0x180026e69  cmp     [r9+r12*2], di
0x180026e6e  jnz     short loc_180026E66
0x180026e70  cmp     r12, [r13+18h]
0x180026e74  ja      short loc_180026EA5
0x180026e76  cmp     qword ptr [r13+18h], 7
0x180026e7b  jbe     short loc_180026E83
0x180026e7d  mov     r14, [r13+0]
0x180026e81  jmp     short loc_180026E86
0x180026e83  mov     r14, r13
0x180026e86  mov     [r13+10h], r12
0x180026e8a  lea     rdi, [r12+r12]
0x180026e8e  mov     r8, rdi; Size
0x180026e91  mov     rdx, r9; Src
0x180026e94  mov     rcx, r14; void *
0x180026e97  call    memmove_0
0x180026e9c  xor     eax, eax
0x180026e9e  mov     [rdi+r14], ax
0x180026ea3  jmp     short loc_180026EB1
0x180026ea5  mov     rdx, r12
0x180026ea8  mov     rcx, r13
0x180026eab  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180026eb0  nop
0x180026eb1  test    rsi, rsi
0x180026eb4  jz      short loc_180026EC0
0x180026eb6  mov     rcx, rsi; hMem
0x180026eb9  call    cs:__imp_LocalFree
0x180026ebf  nop
0x180026ec0  test    rbx, rbx
0x180026ec3  jz      short loc_180026ECF
0x180026ec5  mov     rcx, rbx; hMem
0x180026ec8  call    cs:__imp_LocalFree
0x180026ece  nop
0x180026ecf  test    r15, r15
0x180026ed2  jz      short loc_180026EDD
0x180026ed4  mov     rcx, r15; hObject
0x180026ed7  call    cs:__imp_CloseHandle
0x180026edd  xor     eax, eax
0x180026edf  mov     rbx, [rsp+70h+arg_8]
0x180026ee7  add     rsp, 70h
0x180026eeb  pop     r15
0x180026eed  pop     r14
0x180026eef  pop     r13
0x180026ef1  pop     r12
0x180026ef3  pop     rdi
0x180026ef4  pop     rsi
0x180026ef5  pop     rbp
0x180026ef6  retn
```
