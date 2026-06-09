# CempGetTokenHostInfo

- ea: `0x180094d74`
- end: `0x180094f5c`
- name: `CempGetTokenHostInfo`
- size: `488`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007b560`
- `0x180094d14`

## callees

- `0x180031720`
- `0x18005ae90`
- `0x18005ba40`
- `0x18005d2b9`
- `0x180062c40`
- `0x180062c60`
- `0x180094d74`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180094e09`
- `ntdll!NtQueryInformationToken` at `0x180094e5a`
- `ntdll!NtQueryInformationToken` at `0x180094eb8`
- `ntdll!NtQueryInformationToken` at `0x180094e09`
- `ntdll!NtQueryInformationToken` at `0x180094e5a`
- `ntdll!NtQueryInformationToken` at `0x180094eb8`
- `ntdll!RtlLengthSid` at `0x180094e82`
- `ntdll!RtlLengthSid` at `0x180094e82`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x180094eee`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x180094eee`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180094de0`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180094de0`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180094ecc`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180094ecc`

## pseudocode

```c
__int64 __fastcall CempGetTokenHostInfo(HANDLE TokenHandle, __int64 a2)
{
  NTSTATUS KeyFromToken; // ebx
  void **v5; // r14
  void *v6; // rbx
  ULONG v7; // eax
  ULONG TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  int v10; // [rsp+34h] [rbp-CCh] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v12[464]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[68]; // [rsp+210h] [rbp+110h] BYREF
  unsigned int TokenInformation; // [rsp+254h] [rbp+154h] BYREF
  unsigned int v15; // [rsp+258h] [rbp+158h]
  __int64 v16; // [rsp+260h] [rbp+160h] BYREF

  v10 = 0;
  TokenInformationLength = 0;
  memset_0(v12, 0, 0x228u);
  v11 = 464;
  KeyFromToken = PsmGetKeyFromToken(TokenHandle, v12, &v11, 0);
  if ( KeyFromToken >= 0 )
  {
    KeyFromToken = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( (int)(KeyFromToken + 0x80000000) < 0 || KeyFromToken == -1073741789 )
    {
      v5 = (void **)MIDL_user_allocate(TokenInformationLength);
      if ( v5 )
      {
        KeyFromToken = NtQueryInformationToken(
                         TokenHandle,
                         TokenUser,
                         v5,
                         TokenInformationLength,
                         &TokenInformationLength);
        if ( KeyFromToken >= 0 )
        {
          v6 = *v5;
          memset_0(v13, 0, sizeof(v13));
          v7 = RtlLengthSid(v6);
          memcpy_0(v13, v6, v7);
          KeyFromToken = NtQueryInformationToken(
                           TokenHandle,
                           TokenSessionId,
                           &TokenInformation,
                           4u,
                           &TokenInformationLength);
          if ( KeyFromToken >= 0 )
          {
            KeyFromToken = PsmQueryBackgroundActivationType(TokenHandle, &v10);
            if ( KeyFromToken >= 0 )
            {
              v15 = 1 << v10;
              KeyFromToken = RtlQueryTokenHostIdAsUlong64(TokenHandle, &v16);
              if ( KeyFromToken >= 0 )
              {
                CempHostInfoInitialize(v12, v13, TokenInformation, v15, v16, a2);
                KeyFromToken = 0;
              }
            }
          }
        }
        CempHeapFree(v5);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  return (unsigned int)KeyFromToken;
}

```

## disassembly

```asm
0x180094d74  mov     [rsp-8+arg_10], rbx
0x180094d79  push    rbp
0x180094d7a  push    rsi
0x180094d7b  push    rdi
0x180094d7c  push    r14
0x180094d7e  push    r15
0x180094d80  lea     rbp, [rsp-180h]
0x180094d88  sub     rsp, 280h
0x180094d8f  mov     rax, cs:__security_cookie
0x180094d96  xor     rax, rsp
0x180094d99  mov     [rbp+1A0h+var_30], rax
0x180094da0  mov     r15, rdx
0x180094da3  mov     [rsp+2A0h+var_26C], 0
0x180094dab  mov     rdi, rcx
0x180094dae  mov     [rsp+2A0h+TokenInformationLength], 0
0x180094db6  xor     edx, edx; Val
0x180094db8  lea     rcx, [rsp+2A0h+var_260]; void *
0x180094dbd  mov     r8d, 228h; Size
0x180094dc3  call    memset_0
0x180094dc8  xor     r9d, r9d
0x180094dcb  mov     [rsp+2A0h+var_268], 1D0h
0x180094dd3  lea     r8, [rsp+2A0h+var_268]
0x180094dd8  mov     rcx, rdi
0x180094ddb  lea     rdx, [rsp+2A0h+var_260]
0x180094de0  call    cs:__imp_PsmGetKeyFromToken
0x180094de6  mov     ebx, eax
0x180094de8  test    eax, eax
0x180094dea  js      loc_180094F34
0x180094df0  xor     r9d, r9d; TokenInformationLength
0x180094df3  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180094df8  xor     r8d, r8d; TokenInformation
0x180094dfb  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180094e00  mov     rcx, rdi; TokenHandle
0x180094e03  lea     esi, [r9+1]
0x180094e07  mov     edx, esi; TokenInformationClass
0x180094e09  call    cs:__imp_NtQueryInformationToken
0x180094e0f  mov     ecx, 80000000h
0x180094e14  mov     ebx, eax
0x180094e16  add     eax, ecx
0x180094e18  test    ecx, eax
0x180094e1a  jnz     short loc_180094E28
0x180094e1c  cmp     ebx, 0C0000023h
0x180094e22  jnz     loc_180094F34
0x180094e28  mov     ecx, [rsp+2A0h+TokenInformationLength]; size
0x180094e2c  call    MIDL_user_allocate
0x180094e31  mov     r14, rax
0x180094e34  test    rax, rax
0x180094e37  jnz     short loc_180094E43
0x180094e39  mov     ebx, 0C0000017h
0x180094e3e  jmp     loc_180094F34
0x180094e43  mov     r9d, [rsp+2A0h+TokenInformationLength]; TokenInformationLength
0x180094e48  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180094e4d  mov     r8, r14; TokenInformation
0x180094e50  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180094e55  mov     edx, esi; TokenInformationClass
0x180094e57  mov     rcx, rdi; TokenHandle
0x180094e5a  call    cs:__imp_NtQueryInformationToken
0x180094e60  mov     ebx, eax
0x180094e62  test    eax, eax
0x180094e64  js      loc_180094F2C
0x180094e6a  mov     rbx, [r14]
0x180094e6d  lea     rcx, [rbp+1A0h+var_90]; void *
0x180094e74  xor     edx, edx; Val
0x180094e76  lea     r8d, [rdx+44h]; Size
0x180094e7a  call    memset_0
0x180094e7f  mov     rcx, rbx; Sid
0x180094e82  call    cs:__imp_RtlLengthSid
0x180094e88  mov     r8d, eax; Size
0x180094e8b  mov     rdx, rbx; Src
0x180094e8e  lea     rcx, [rbp+1A0h+var_90]; void *
0x180094e95  call    memcpy_0
0x180094e9a  mov     r9d, 4; TokenInformationLength
0x180094ea0  lea     rax, [rsp+2A0h+TokenInformationLength]
0x180094ea5  lea     r8, [rbp+1A0h+TokenInformation]; TokenInformation
0x180094eac  mov     [rsp+2A0h+ReturnLength], rax; ReturnLength
0x180094eb1  mov     rcx, rdi; TokenHandle
0x180094eb4  lea     edx, [r9+8]; TokenInformationClass
0x180094eb8  call    cs:__imp_NtQueryInformationToken
0x180094ebe  mov     ebx, eax
0x180094ec0  test    eax, eax
0x180094ec2  js      short loc_180094F2C
0x180094ec4  lea     rdx, [rsp+2A0h+var_26C]
0x180094ec9  mov     rcx, rdi
0x180094ecc  call    cs:__imp_PsmQueryBackgroundActivationType
0x180094ed2  mov     ebx, eax
0x180094ed4  test    eax, eax
0x180094ed6  js      short loc_180094F2C
0x180094ed8  mov     ecx, [rsp+2A0h+var_26C]
0x180094edc  lea     rdx, [rbp+1A0h+var_40]
0x180094ee3  shl     esi, cl
0x180094ee5  mov     rcx, rdi
0x180094ee8  mov     [rbp+1A0h+var_48], esi
0x180094eee  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x180094ef4  mov     ebx, eax
0x180094ef6  test    eax, eax
0x180094ef8  js      short loc_180094F2C
0x180094efa  mov     rax, [rbp+1A0h+var_40]
0x180094f01  lea     rdx, [rbp+1A0h+var_90]
0x180094f08  mov     r9d, [rbp+1A0h+var_48]
0x180094f0f  lea     rcx, [rsp+2A0h+var_260]
0x180094f14  mov     r8d, [rbp+1A0h+TokenInformation]
0x180094f1b  mov     [rsp+2A0h+var_278], r15
0x180094f20  mov     [rsp+2A0h+ReturnLength], rax
0x180094f25  call    CempHostInfoInitialize
0x180094f2a  xor     ebx, ebx
0x180094f2c  mov     rcx, r14
0x180094f2f  call    CempHeapFree
0x180094f34  mov     eax, ebx
0x180094f36  mov     rcx, [rbp+1A0h+var_30]
0x180094f3d  xor     rcx, rsp; StackCookie
0x180094f40  call    __security_check_cookie
0x180094f45  mov     rbx, [rsp+2A0h+arg_10]
0x180094f4d  add     rsp, 280h
0x180094f54  pop     r15
0x180094f56  pop     r14
0x180094f58  pop     rdi
0x180094f59  pop     rsi
0x180094f5a  pop     rbp
0x180094f5b  retn
```
