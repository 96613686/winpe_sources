# CiPolicyAdjustToken(void *,ulong,ushort const *)

- ea: `0x180030e20`
- end: `0x180031107`
- name: `?CiPolicyAdjustToken@@YAJPEAXKPEBG@Z`
- size: `743`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ce70`

## callees

- `0x180030e20`
- `0x180046e50`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180030ede`
- `ntdll!RtlEqualUnicodeString` at `0x180030ede`
- `ntdll!RtlReleasePrivilege` at `0x180030ffb`
- `ntdll!RtlReleasePrivilege` at `0x1800310e0`
- `ntdll!RtlReleasePrivilege` at `0x180030ffb`
- `ntdll!RtlReleasePrivilege` at `0x1800310e0`
- `ntdll!RtlInitUnicodeString` at `0x180030ebd`
- `ntdll!RtlInitUnicodeString` at `0x180030f51`
- `ntdll!RtlInitUnicodeString` at `0x180030ebd`
- `ntdll!RtlInitUnicodeString` at `0x180030f51`
- `ntdll!RtlQueryPackageClaims` at `0x180030f39`
- `ntdll!RtlQueryPackageClaims` at `0x180030f39`
- `ntdll!RtlAcquirePrivilege` at `0x180030fca`
- `ntdll!RtlAcquirePrivilege` at `0x1800310b8`
- `ntdll!RtlAcquirePrivilege` at `0x180030fca`
- `ntdll!RtlAcquirePrivilege` at `0x1800310b8`
- `ntdll!NtSetInformationToken` at `0x180030fee`
- `ntdll!NtSetInformationToken` at `0x1800310d3`
- `ntdll!NtSetInformationToken` at `0x180030fee`
- `ntdll!NtSetInformationToken` at `0x1800310d3`

## pseudocode

```c
__int64 __fastcall CiPolicyAdjustToken(HANDLE TokenHandle, int a2, const unsigned __int16 *a3)
{
  unsigned int i; // ebx
  NTSTATUS v6; // ebx
  int v7; // eax
  int v8; // edi
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+48h] [rbp-B8h] BYREF
  PVOID ReturnedState; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v13[5]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 TokenInformation; // [rsp+88h] [rbp-78h] BYREF
  __int64 v15; // [rsp+98h] [rbp-68h]
  __int64 v16; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v17[2]; // [rsp+A8h] [rbp-58h] BYREF
  const WCHAR *v18; // [rsp+B0h] [rbp-50h]
  int v19; // [rsp+B8h] [rbp-48h]
  const wchar_t *v20; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING DestinationString[2]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SourceString[128]; // [rsp+F0h] [rbp-10h] BYREF

  v17[0] = 1835034;
  v19 = 655368;
  v15 = 0;
  v20 = L"MCPB";
  v18 = L"TRUSTEDLAUNCH";
  memset(DestinationString, 0, sizeof(DestinationString));
  v10 = 0x700000000LL;
  memset(v13, 0, sizeof(v13));
  ReturnedState = 0;
  v11 = 0;
  TokenInformation = 0;
  RtlInitUnicodeString(DestinationString, L"TRUSTEDLAUNCH");
  for ( i = 0; i < 2; ++i )
  {
    if ( RtlEqualUnicodeString(DestinationString, (PCUNICODE_STRING)&v17[4 * i], 0) )
      break;
  }
  if ( i == 2 )
  {
    return (unsigned int)-1073741583;
  }
  else
  {
    v16 = 256;
    v6 = RtlQueryPackageClaims(TokenHandle, SourceString, &v16, 0, 0, 0, 0, 0, v10, v11, *((_QWORD *)&v11 + 1));
    if ( v6 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString[1], SourceString);
      HIDWORD(v13[0]) = v15;
      LODWORD(v10) = 3;
      LOWORD(v13[2]) = 3;
      v13[1] = L"WIN://CIPOLICY";
      *((_QWORD *)&v11 + 1) = v13;
      LODWORD(v13[0]) = 1966108;
      *(_QWORD *)&TokenInformation = &v11;
      v13[4] = 0;
      *((_QWORD *)&TokenInformation + 1) = &v10;
      LODWORD(v13[3]) = 0;
      *(_QWORD *)&v11 = 0x100000001LL;
      v6 = RtlAcquirePrivilege((PULONG)&v10 + 1, 1u, 2u, &ReturnedState);
      if ( v6 >= 0 )
      {
        v6 = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
        RtlReleasePrivilege(ReturnedState);
        if ( (int)(v6 + 0x80000000) < 0 || v6 == -1073741275 )
        {
          v7 = 0;
          if ( a2 )
          {
            v8 = a2 - 1;
            if ( v8 )
            {
              if ( v8 != 1 )
                return (unsigned int)-1073741811;
              v7 = 1;
            }
            else
            {
              v7 = 128;
            }
          }
          HIDWORD(v13[0]) = v15;
          HIDWORD(v13[2]) = v7;
          v13[1] = L"WIN://CIPOLICY";
          *((_QWORD *)&v11 + 1) = v13;
          LOWORD(v13[2]) = 3;
          *(_QWORD *)&TokenInformation = &v11;
          v13[4] = DestinationString;
          LODWORD(v10) = 2;
          LODWORD(v13[0]) = 1966108;
          LODWORD(v13[3]) = 2;
          *(_QWORD *)&v11 = 0x100000001LL;
          *((_QWORD *)&TokenInformation + 1) = &v10;
          v6 = RtlAcquirePrivilege((PULONG)&v10 + 1, 1u, 2u, &ReturnedState);
          if ( v6 >= 0 )
          {
            v6 = NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
            RtlReleasePrivilege(ReturnedState);
          }
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030e20  push    rbp
0x180030e22  push    rbx
0x180030e23  push    rsi
0x180030e24  push    rdi
0x180030e25  push    r13
0x180030e27  push    r15
0x180030e29  lea     rbp, [rsp-108h]
0x180030e31  sub     rsp, 208h
0x180030e38  mov     rax, cs:__security_cookie
0x180030e3f  xor     rax, rsp
0x180030e42  mov     [rbp+130h+var_40], rax
0x180030e49  xorps   xmm0, xmm0
0x180030e4c  mov     [rbp+130h+var_188], 1C001Ah
0x180030e53  xor     eax, eax
0x180030e55  mov     [rbp+130h+var_178], 0A0008h
0x180030e5c  mov     [rbp+130h+var_198], rax
0x180030e60  mov     edi, edx
0x180030e62  lea     rax, aMcpb; "MCPB"
0x180030e69  mov     [rsp+230h+Privilege], 7
0x180030e71  mov     [rbp+130h+var_170], rax
0x180030e75  lea     rdx, aTrustedlaunch; "TRUSTEDLAUNCH"
0x180030e7c  xor     eax, eax
0x180030e7e  mov     [rbp+130h+var_180], rdx
0x180030e82  mov     rsi, rcx
0x180030e85  mov     [rbp+130h+DestinationString.Length], ax
0x180030e89  xorps   xmm1, xmm1
0x180030e8c  mov     [rsp+230h+var_1F0], eax
0x180030e90  movups  xmmword ptr [rbp+130h+DestinationString.MaximumLength], xmm0
0x180030e94  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x180030e98  mov     word ptr [rsp+230h+var_1D0], ax
0x180030e9d  movups  xmmword ptr [rsp+230h+var_1BE], xmm0
0x180030ea2  mov     qword ptr [rbp+130h+var_1BE+0Eh], rax
0x180030ea6  mov     [rsp+230h+ReturnedState], rax
0x180030eab  movups  xmmword ptr [rbp+130h+var_158.Length], xmm0
0x180030eaf  movups  xmmword ptr [rsp+230h+var_1D0+2], xmm0
0x180030eb4  movups  [rsp+230h+var_1E8], xmm0
0x180030eb9  movups  [rbp+130h+TokenInformation], xmm1
0x180030ebd  call    cs:__imp_RtlInitUnicodeString
0x180030ec3  xor     ebx, ebx
0x180030ec5  lea     r15d, [rbx+1]
0x180030ec9  movsxd  rax, ebx
0x180030ecc  lea     rdx, [rbp+130h+var_188]
0x180030ed0  shl     rax, 4
0x180030ed4  lea     rcx, [rbp+130h+DestinationString]; String1
0x180030ed8  add     rdx, rax; String2
0x180030edb  xor     r8d, r8d; CaseInsensitive
0x180030ede  call    cs:__imp_RtlEqualUnicodeString
0x180030ee4  test    al, al
0x180030ee6  jnz     short loc_180030EF0
0x180030ee8  add     ebx, r15d
0x180030eeb  cmp     ebx, 2
0x180030eee  jb      short loc_180030EC9
0x180030ef0  cmp     ebx, 2
0x180030ef3  jnz     short loc_180030EFF
0x180030ef5  mov     ebx, 0C00000F1h
0x180030efa  jmp     loc_1800310E6
0x180030eff  mov     [rsp+230h+var_1F8], 0
0x180030f08  lea     r8, [rbp+130h+var_190]
0x180030f0c  mov     [rsp+230h+var_200], 0
0x180030f15  lea     rdx, [rbp+130h+SourceString]
0x180030f19  mov     [rsp+230h+var_208], 0
0x180030f22  xor     r9d, r9d
0x180030f25  mov     rcx, rsi
0x180030f28  mov     [rsp+230h+var_210], 0
0x180030f31  mov     [rbp+130h+var_190], 100h
0x180030f39  call    cs:__imp_RtlQueryPackageClaims
0x180030f3f  mov     ebx, eax
0x180030f41  test    eax, eax
0x180030f43  js      loc_1800310E6
0x180030f49  lea     rdx, [rbp+130h+SourceString]; SourceString
0x180030f4d  lea     rcx, [rbp+130h+var_158]; DestinationString
0x180030f51  call    cs:__imp_RtlInitUnicodeString
0x180030f57  mov     rcx, [rbp+130h+var_198]
0x180030f5b  lea     r9, [rsp+230h+ReturnedState]; ReturnedState
0x180030f60  mov     eax, 3
0x180030f65  mov     [rsp+230h+var_1CC], ecx
0x180030f69  mov     [rsp+230h+var_1F0], eax
0x180030f6d  lea     rcx, aWinCipolicy; "WIN://CIPOLICY"
0x180030f74  mov     [rsp+230h+var_1C0], ax
0x180030f79  mov     r8d, 2; Flags
0x180030f7f  lea     rax, [rsp+230h+var_1D0]
0x180030f84  mov     [rsp+230h+var_1C8], rcx
0x180030f89  mov     qword ptr [rsp+230h+var_1E8+8], rax
0x180030f8e  lea     rcx, [rsp+230h+Privilege]; Privilege
0x180030f93  lea     rax, [rsp+230h+var_1E8]
0x180030f98  mov     [rsp+230h+var_1D0], 1E001Ch
0x180030fa0  mov     qword ptr [rbp+130h+TokenInformation], rax
0x180030fa4  mov     edx, r15d; NumPriv
0x180030fa7  lea     rax, [rsp+230h+var_1F0]
0x180030fac  mov     qword ptr [rbp+130h+var_1BE+0Eh], 0
0x180030fb4  mov     qword ptr [rbp+130h+TokenInformation+8], rax
0x180030fb8  mov     dword ptr [rsp+230h+var_1BE+6], 0
0x180030fc0  mov     dword ptr [rsp+230h+var_1E8], r15d
0x180030fc5  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x180030fca  call    cs:__imp_RtlAcquirePrivilege
0x180030fd0  mov     ebx, eax
0x180030fd2  test    eax, eax
0x180030fd4  js      loc_1800310E6
0x180030fda  mov     r13d, 10h
0x180030fe0  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x180030fe4  mov     r9d, r13d; TokenInformationLength
0x180030fe7  mov     rcx, rsi; TokenHandle
0x180030fea  lea     edx, [r13+17h]; TokenInformationClass
0x180030fee  call    cs:__imp_NtSetInformationToken
0x180030ff4  mov     rcx, [rsp+230h+ReturnedState]; ReturnedState
0x180030ff9  mov     ebx, eax
0x180030ffb  call    cs:__imp_RtlReleasePrivilege
0x180031001  mov     ecx, 80000000h
0x180031006  lea     eax, [rbx+rcx]
0x180031009  test    ecx, eax
0x18003100b  jnz     short loc_180031019
0x18003100d  cmp     ebx, 0C0000225h
0x180031013  jnz     loc_1800310E6
0x180031019  xor     eax, eax
0x18003101b  test    edi, edi
0x18003101d  jz      short loc_18003103D
0x18003101f  sub     edi, r15d
0x180031022  jz      short loc_180031038
0x180031024  cmp     edi, r15d
0x180031027  jz      short loc_180031033
0x180031029  mov     ebx, 0C000000Dh
0x18003102e  jmp     loc_1800310E6
0x180031033  mov     eax, r15d
0x180031036  jmp     short loc_18003103D
0x180031038  mov     eax, 80h
0x18003103d  mov     rcx, [rbp+130h+var_198]
0x180031041  lea     r9, [rsp+230h+ReturnedState]; ReturnedState
0x180031046  mov     [rsp+230h+var_1CC], ecx
0x18003104a  mov     r8d, 2; Flags
0x180031050  mov     dword ptr [rsp+230h+var_1BE+2], eax
0x180031054  lea     rcx, aWinCipolicy; "WIN://CIPOLICY"
0x18003105b  mov     [rsp+230h+var_1C8], rcx
0x180031060  lea     rax, [rsp+230h+var_1D0]
0x180031065  mov     qword ptr [rsp+230h+var_1E8+8], rax
0x18003106a  mov     ecx, 3
0x18003106f  mov     [rsp+230h+var_1C0], cx
0x180031074  lea     rax, [rsp+230h+var_1E8]
0x180031079  lea     rcx, [rbp+130h+DestinationString]
0x18003107d  mov     qword ptr [rbp+130h+TokenInformation], rax
0x180031081  mov     qword ptr [rbp+130h+var_1BE+0Eh], rcx
0x180031085  lea     rax, [rsp+230h+var_1F0]
0x18003108a  lea     rcx, [rsp+230h+Privilege]; Privilege
0x18003108f  mov     [rsp+230h+var_1F0], 2
0x180031097  mov     edx, r15d; NumPriv
0x18003109a  mov     [rsp+230h+var_1D0], 1E001Ch
0x1800310a2  mov     dword ptr [rsp+230h+var_1BE+6], 2
0x1800310aa  mov     dword ptr [rsp+230h+var_1E8], r15d
0x1800310af  mov     dword ptr [rsp+230h+var_1E8+4], r15d
0x1800310b4  mov     qword ptr [rbp+130h+TokenInformation+8], rax
0x1800310b8  call    cs:__imp_RtlAcquirePrivilege
0x1800310be  mov     ebx, eax
0x1800310c0  test    eax, eax
0x1800310c2  js      short loc_1800310E6
0x1800310c4  mov     r9d, r13d; TokenInformationLength
0x1800310c7  lea     r8, [rbp+130h+TokenInformation]; TokenInformation
0x1800310cb  mov     edx, 27h ; '''; TokenInformationClass
0x1800310d0  mov     rcx, rsi; TokenHandle
0x1800310d3  call    cs:__imp_NtSetInformationToken
0x1800310d9  mov     rcx, [rsp+230h+ReturnedState]; ReturnedState
0x1800310de  mov     ebx, eax
0x1800310e0  call    cs:__imp_RtlReleasePrivilege
0x1800310e6  mov     eax, ebx
0x1800310e8  mov     rcx, [rbp+130h+var_40]
0x1800310ef  xor     rcx, rsp; StackCookie
0x1800310f2  call    __security_check_cookie
0x1800310f7  add     rsp, 208h
0x1800310fe  pop     r15
0x180031100  pop     r13
0x180031102  pop     rdi
0x180031103  pop     rsi
0x180031104  pop     rbx
0x180031105  pop     rbp
0x180031106  retn
```
