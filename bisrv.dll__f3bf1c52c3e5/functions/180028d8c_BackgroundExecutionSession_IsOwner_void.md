# BackgroundExecutionSession::IsOwner(void *)

- ea: `0x180028d8c`
- end: `0x180028f4a`
- name: `?IsOwner@BackgroundExecutionSession@@QEAA_NPEAX@Z`
- size: `446`
- prototype: `bool(BackgroundExecutionSession *__hidden this, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180027ec0`
- `0x18002823c`
- `0x180038b20`

## callees

- `0x180028d8c`
- `0x180070eec`
- `0x18007109c`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180028db7`
- `ntdll!RtlEqualSid` at `0x180028f2e`
- `ntdll!RtlEqualSid` at `0x180028db7`
- `ntdll!RtlEqualSid` at `0x180028f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028de0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e97`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028ee3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028ee3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028e89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028ed2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028e89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180028ed2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180028f09`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180028f09`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180028e4c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x180028e4c`

## pseudocode

```c
char __fastcall BackgroundExecutionSession::IsOwner(BackgroundExecutionSession *this, void *a2)
{
  bool v2; // di
  char *v3; // r12
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  signed int v8; // eax
  HANDLE v9; // rbx
  void *v10; // r15
  PSID *v11; // r14
  DWORD LengthSid; // ebx
  void *v13; // rax
  void *v14; // rsi
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  if ( a2 )
  {
    v3 = (char *)this + 20;
    if ( RtlEqualSid(a2, (char *)this + 20) )
      return 1;
    TokenHandle = 0;
    if ( (int)UMgrQueryDefaultAccountToken(&TokenHandle) < 0 )
      return v2;
    v9 = TokenHandle;
    v10 = 0;
    if ( TokenHandle )
    {
      TokenInformationLength = 0;
      if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      {
        if ( GetLastError() != 122 )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_23;
        }
        v11 = (PSID *)operator new[](TokenInformationLength);
        if ( v11 )
        {
          if ( GetTokenInformation(v9, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
          {
            LengthSid = GetLengthSid(*v11);
            v13 = operator new[](LengthSid);
            v14 = v13;
            if ( v13 )
            {
              if ( CopySid(LengthSid, v13, *v11) )
              {
                v6 = 0;
                v10 = v14;
              }
              else
              {
                v8 = GetLastError();
                v6 = v8;
                if ( v8 > 0 )
                  v6 = (unsigned __int16)v8 | 0x80070000;
                operator delete(v14);
              }
            }
            else
            {
              v6 = -2147024882;
            }
          }
          else
          {
            v7 = GetLastError();
            v6 = v7;
            if ( v7 > 0 )
              v6 = (unsigned __int16)v7 | 0x80070000;
          }
          operator delete(v11);
LABEL_23:
          if ( v6 >= 0 )
            v2 = RtlEqualSid(v10, v3) != 0;
        }
      }
    }
    operator delete(v10);
  }
  return v2;
}

```

## disassembly

```asm
0x180028d8c  mov     [rsp+arg_0], rbx
0x180028d91  mov     [rsp+arg_18], rbp
0x180028d96  push    rsi
0x180028d97  push    rdi
0x180028d98  push    r12
0x180028d9a  push    r14
0x180028d9c  push    r15
0x180028d9e  sub     rsp, 30h
0x180028da2  xor     dil, dil
0x180028da5  mov     rax, rdx
0x180028da8  test    rdx, rdx
0x180028dab  jz      short loc_180028DC6
0x180028dad  lea     r12, [rcx+14h]
0x180028db1  mov     rcx, rax; Sid1
0x180028db4  mov     rdx, r12; Sid2
0x180028db7  call    cs:__imp_RtlEqualSid
0x180028dbd  test    al, al
0x180028dbf  jz      short loc_180028E3E
0x180028dc1  mov     edi, 1
0x180028dc6  mov     rbx, [rsp+58h+arg_0]
0x180028dcb  mov     al, dil
0x180028dce  mov     rbp, [rsp+58h+arg_18]
0x180028dd3  add     rsp, 30h
0x180028dd7  pop     r15
0x180028dd9  pop     r14
0x180028ddb  pop     r12
0x180028ddd  pop     rdi
0x180028dde  pop     rsi
0x180028ddf  retn
0x180028de0  call    cs:__imp_GetLastError
0x180028de6  mov     ebx, eax
0x180028de8  test    eax, eax
0x180028dea  jle     loc_180028F24
0x180028df0  movzx   ebx, ax
0x180028df3  or      ebx, 80070000h
0x180028df9  jmp     loc_180028F24
0x180028dfe  call    cs:__imp_GetLastError
0x180028e04  mov     ebx, eax
0x180028e06  test    eax, eax
0x180028e08  jle     loc_180028F1C
0x180028e0e  movzx   ebx, ax
0x180028e11  or      ebx, 80070000h
0x180028e17  jmp     loc_180028F1C
0x180028e1c  call    cs:__imp_GetLastError
0x180028e22  mov     ebx, eax
0x180028e24  test    eax, eax
0x180028e26  jle     short loc_180028E31
0x180028e28  movzx   ebx, ax
0x180028e2b  or      ebx, 80070000h
0x180028e31  mov     rcx, rsi; Block
0x180028e34  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028e39  jmp     loc_180028F1C
0x180028e3e  lea     rcx, [rsp+58h+TokenHandle]
0x180028e43  mov     [rsp+58h+TokenHandle], 0
0x180028e4c  call    cs:__imp_UMgrQueryDefaultAccountToken
0x180028e52  test    eax, eax
0x180028e54  js      loc_180028DC6
0x180028e5a  mov     rbx, [rsp+58h+TokenHandle]
0x180028e5f  xor     r15d, r15d
0x180028e62  test    rbx, rbx
0x180028e65  jz      loc_180028F3D
0x180028e6b  lea     rax, [rsp+58h+TokenInformationLength]
0x180028e70  mov     [rsp+58h+TokenInformationLength], r15d
0x180028e75  lea     ebp, [r15+1]
0x180028e79  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180028e7e  mov     edx, ebp; TokenInformationClass
0x180028e80  xor     r9d, r9d; TokenInformationLength
0x180028e83  xor     r8d, r8d; TokenInformation
0x180028e86  mov     rcx, rbx; TokenHandle
0x180028e89  call    cs:__imp_GetTokenInformation
0x180028e8f  test    eax, eax
0x180028e91  jnz     loc_180028F3D
0x180028e97  call    cs:__imp_GetLastError
0x180028e9d  cmp     eax, 7Ah ; 'z'
0x180028ea0  jnz     loc_180028DE0
0x180028ea6  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x180028eaa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028eaf  mov     r14, rax
0x180028eb2  test    rax, rax
0x180028eb5  jz      loc_180028F3D
0x180028ebb  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180028ec0  lea     rax, [rsp+58h+TokenInformationLength]
0x180028ec5  mov     r8, r14; TokenInformation
0x180028ec8  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180028ecd  mov     edx, ebp; TokenInformationClass
0x180028ecf  mov     rcx, rbx; TokenHandle
0x180028ed2  call    cs:__imp_GetTokenInformation
0x180028ed8  test    eax, eax
0x180028eda  jz      loc_180028DFE
0x180028ee0  mov     rcx, [r14]; pSid
0x180028ee3  call    cs:__imp_GetLengthSid
0x180028ee9  mov     ecx, eax; unsigned __int64
0x180028eeb  mov     ebx, eax
0x180028eed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028ef2  mov     rsi, rax
0x180028ef5  test    rax, rax
0x180028ef8  jnz     short loc_180028F01
0x180028efa  mov     ebx, 8007000Eh
0x180028eff  jmp     short loc_180028F1C
0x180028f01  mov     r8, [r14]; pSourceSid
0x180028f04  mov     rdx, rsi; pDestinationSid
0x180028f07  mov     ecx, ebx; nDestinationSidLength
0x180028f09  call    cs:__imp_CopySid
0x180028f0f  test    eax, eax
0x180028f11  jz      loc_180028E1C
0x180028f17  xor     ebx, ebx
0x180028f19  mov     r15, rsi
0x180028f1c  mov     rcx, r14; Block
0x180028f1f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028f24  test    ebx, ebx
0x180028f26  js      short loc_180028F3D
0x180028f28  mov     rdx, r12; Sid2
0x180028f2b  mov     rcx, r15; Sid1
0x180028f2e  call    cs:__imp_RtlEqualSid
0x180028f34  test    al, al
0x180028f36  movzx   edi, dil
0x180028f3a  cmovnz  edi, ebp
0x180028f3d  mov     rcx, r15; Block
0x180028f40  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028f45  jmp     loc_180028DC6
```
