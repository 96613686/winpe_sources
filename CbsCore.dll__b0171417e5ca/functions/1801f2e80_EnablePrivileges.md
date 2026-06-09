# EnablePrivileges

- ea: `0x1801f2e80`
- end: `0x1801f3093`
- name: `EnablePrivileges`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1801f5628`

## callees

- `0x1800aa134`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1801c48dc`
- `0x1801f2a50`
- `0x1801f2e80`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x1801f2fe7`
- `ntdll!NtAdjustPrivilegesToken` at `0x1801f2fe7`
- `ntdll!NtClose` at `0x1801f2eec`
- `ntdll!NtClose` at `0x1801f3063`
- `ntdll!NtClose` at `0x1801f2eec`
- `ntdll!NtClose` at `0x1801f3063`
- `ntdll!NtOpenProcessToken` at `0x1801f2ebf`
- `ntdll!NtOpenProcessToken` at `0x1801f2ebf`

## string_xrefs

- `0x1801f2f25`: `EnablePrivileges`
- `0x1801f3017`: `EnablePrivileges`
- `0x1801f2f34`: `rgbTokenPrivileges.Allocate( (((LONG)__builtin_offsetof(TOKEN_PRIVILEGES, Privileges)) + (sizeof(((TOKEN_PRIVILEGES *)0)->Privileges))) + sizeof(LUID_AND_ATTRIBUTES[6]))`

## pseudocode

```c
__int64 EnablePrivileges()
{
  NTSTATUS v0; // ebx
  void *v1; // rcx
  NTSTATUS v3; // eax
  PTOKEN_PRIVILEGES v4; // r8
  NTSTATUS v5; // eax
  __int64 v6; // r8
  void *v7; // rcx
  PTOKEN_PRIVILEGES NewState[2]; // [rsp+38h] [rbp-48h] BYREF
  const char *v9; // [rsp+48h] [rbp-38h] BYREF
  const char *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  const char *v12; // [rsp+60h] [rbp-20h]
  void *TokenHandle; // [rsp+68h] [rbp-18h] BYREF
  int v14; // [rsp+70h] [rbp-10h] BYREF

  v14 = 0;
  TokenHandle = 0;
  NewState[0] = 0;
  NewState[1] = 0;
  v0 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20u, &TokenHandle);
  if ( v0 < 0 )
  {
LABEL_2:
    Windows::Auto<Windows::Vector<unsigned char>>::~Auto<Windows::Vector<unsigned char>>(NewState);
    v1 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      TokenHandle = 0;
      NtClose(v1);
    }
    return (unsigned int)v0;
  }
  if ( !Windows::AutoVectorBase<Windows::VectorTraits<unsigned char>,Windows::Auto<Windows::Vector<unsigned char>>>::Allocate(
          NewState,
          88) )
  {
    v11 = 1262;
    v9 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    v10 = "EnablePrivileges";
    v12 = "rgbTokenPrivileges.Allocate( (((LONG)__builtin_offsetof(TOKEN_PRIVILEGES, Privileges)) + (sizeof(((TOKEN_PRIVI"
          "LEGES *)0)->Privileges))) + sizeof(LUID_AND_ATTRIBUTES[6]))";
    v3 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v14,
           &v9);
LABEL_7:
    v0 = v3;
    goto LABEL_2;
  }
  v4 = NewState[0];
  NewState[0]->PrivilegeCount = 6;
  v4->Privileges[0].Luid = (LUID)19LL;
  *(_QWORD *)&v4[1].PrivilegeCount = 17;
  *(_QWORD *)&v4[1].Privileges[0].Attributes = 18;
  *(_QWORD *)&v4[2].Privileges[0].Luid.HighPart = 8;
  v4[3].Privileges[0].Luid = (LUID)20LL;
  v4->Privileges[0].Attributes = 2;
  v4[1].Privileges[0].Luid.HighPart = 2;
  v4[2].Privileges[0].Luid.LowPart = 2;
  v4[3].PrivilegeCount = 2;
  v4[3].Privileges[0].Attributes = 2;
  v4[4].Privileges[0].Luid.HighPart = 2;
  *(_QWORD *)&v4[4].PrivilegeCount = 28;
  v5 = NtAdjustPrivilegesToken(TokenHandle, 0, v4, 0, 0, 0);
  if ( v5 < 0 )
  {
    v11 = 1296;
    v6 = (unsigned int)v5;
LABEL_10:
    v12 = 0;
    v9 = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    v10 = "EnablePrivileges";
    v3 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v14,
           &v9,
           v6);
    goto LABEL_7;
  }
  if ( v5 == 262 )
  {
    v11 = 1300;
    v6 = 3221225569LL;
    goto LABEL_10;
  }
  Windows::Auto<Windows::Vector<unsigned char>>::~Auto<Windows::Vector<unsigned char>>(NewState);
  v7 = TokenHandle;
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    TokenHandle = 0;
    NtClose(v7);
  }
  return 0;
}

```

## disassembly

```asm
0x1801f2e80  mov     [rsp-8+arg_0], rbx
0x1801f2e85  mov     [rsp-8+arg_8], rdi
0x1801f2e8a  push    rbp
0x1801f2e8b  mov     rbp, rsp
0x1801f2e8e  sub     rsp, 80h
0x1801f2e95  mov     rax, cs:__security_cookie
0x1801f2e9c  xor     rax, rsp
0x1801f2e9f  mov     [rbp+var_8], rax
0x1801f2ea3  xor     edi, edi
0x1801f2ea5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801f2ea9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1801f2ead  mov     [rbp+var_10], edi
0x1801f2eb0  mov     [rbp+TokenHandle], rdi
0x1801f2eb4  mov     [rbp+NewState], rdi
0x1801f2eb8  lea     edx, [rdi+20h]; DesiredAccess
0x1801f2ebb  mov     [rbp+var_40], rdi
0x1801f2ebf  call    cs:__imp_NtOpenProcessToken
0x1801f2ec6  nop     dword ptr [rax+rax+00h]
0x1801f2ecb  lea     rcx, [rbp+NewState]
0x1801f2ecf  mov     ebx, eax
0x1801f2ed1  test    eax, eax
0x1801f2ed3  jns     short loc_1801F2EFF
0x1801f2ed5  call    ??1?$Auto@U?$Vector@E@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<uchar>>::~Auto<Windows::Vector<uchar>>(void)
0x1801f2eda  mov     rcx, [rbp+TokenHandle]; Handle
0x1801f2ede  lea     rdx, [rcx-1]
0x1801f2ee2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801f2ee6  ja      short loc_1801F2EF8
0x1801f2ee8  mov     [rbp+TokenHandle], rdi
0x1801f2eec  call    cs:__imp_NtClose
0x1801f2ef3  nop     dword ptr [rax+rax+00h]
0x1801f2ef8  mov     eax, ebx
0x1801f2efa  jmp     loc_1801F3071
0x1801f2eff  mov     edx, 58h ; 'X'
0x1801f2f04  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@E@Windows@@V?$Auto@U?$Vector@E@Windows@@@2@@Windows@@QEAAPEAE_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<uchar>,Windows::Auto<Windows::Vector<uchar>>>::Allocate(unsigned __int64)
0x1801f2f09  test    rax, rax
0x1801f2f0c  jnz     short loc_1801F2F4C
0x1801f2f0e  lea     rax, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f2f15  mov     [rbp+var_28], 4EEh
0x1801f2f1d  mov     [rbp+var_38], rax
0x1801f2f21  lea     rdx, [rbp+var_38]
0x1801f2f25  lea     rax, aEnableprivileg; "EnablePrivileges"
0x1801f2f2c  mov     [rbp+var_30], rax
0x1801f2f30  lea     rcx, [rbp+var_10]
0x1801f2f34  lea     rax, aRgbtokenprivil; "rgbTokenPrivileges.Allocate( (((LONG)__"...
0x1801f2f3b  mov     [rbp+var_20], rax
0x1801f2f3f  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1801f2f44  mov     ebx, eax
0x1801f2f46  lea     rcx, [rbp+NewState]
0x1801f2f4a  jmp     short loc_1801F2ED5
0x1801f2f4c  mov     r8, [rbp+NewState]; NewState
0x1801f2f50  mov     ecx, 2
0x1801f2f55  mov     [rbp+var_50], 13h
0x1801f2f5d  xor     r9d, r9d; BufferLength
0x1801f2f60  mov     rax, [rbp+var_50]
0x1801f2f64  xor     edx, edx; DisableAllPrivileges
0x1801f2f66  mov     [rbp+var_50], 11h
0x1801f2f6e  mov     dword ptr [r8], 6
0x1801f2f75  mov     [r8+4], rax
0x1801f2f79  mov     rax, [rbp+var_50]
0x1801f2f7d  mov     [r8+10h], rax
0x1801f2f81  mov     [rbp+var_50], 12h
0x1801f2f89  mov     rax, [rbp+var_50]
0x1801f2f8d  mov     [r8+1Ch], rax
0x1801f2f91  mov     [rbp+var_50], 8
0x1801f2f99  mov     rax, [rbp+var_50]
0x1801f2f9d  mov     [r8+28h], rax
0x1801f2fa1  mov     [rbp+var_50], 14h
0x1801f2fa9  mov     rax, [rbp+var_50]
0x1801f2fad  mov     [r8+34h], rax
0x1801f2fb1  mov     [r8+0Ch], ecx
0x1801f2fb5  mov     [r8+18h], ecx
0x1801f2fb9  mov     [r8+24h], ecx
0x1801f2fbd  mov     [r8+30h], ecx
0x1801f2fc1  mov     [r8+3Ch], ecx
0x1801f2fc5  mov     [r8+48h], ecx
0x1801f2fc9  mov     [rbp+var_50], 1Ch
0x1801f2fd1  mov     rax, [rbp+var_50]
0x1801f2fd5  mov     [r8+40h], rax
0x1801f2fd9  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1801f2fdd  mov     [rsp+80h+ReturnLength], rdi; ReturnLength
0x1801f2fe2  mov     [rsp+80h+PreviousState], rdi; PreviousState
0x1801f2fe7  call    cs:__imp_NtAdjustPrivilegesToken
0x1801f2fee  nop     dword ptr [rax+rax+00h]
0x1801f2ff3  mov     ecx, eax
0x1801f2ff5  test    eax, eax
0x1801f2ff7  jns     short loc_1801F3030
0x1801f2ff9  mov     [rbp+var_28], 510h
0x1801f3001  mov     r8d, eax
0x1801f3004  lea     rax, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f300b  mov     [rbp+var_20], rdi
0x1801f300f  mov     [rbp+var_38], rax
0x1801f3013  lea     rdx, [rbp+var_38]
0x1801f3017  lea     rax, aEnableprivileg; "EnablePrivileges"
0x1801f301e  lea     rcx, [rbp+var_10]
0x1801f3022  mov     [rbp+var_30], rax
0x1801f3026  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801f302b  jmp     loc_1801F2F44
0x1801f3030  cmp     ecx, 106h
0x1801f3036  jnz     short loc_1801F3048
0x1801f3038  mov     [rbp+var_28], 514h
0x1801f3040  mov     r8d, 0C0000061h
0x1801f3046  jmp     short loc_1801F3004
0x1801f3048  lea     rcx, [rbp+NewState]
0x1801f304c  call    ??1?$Auto@U?$Vector@E@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<uchar>>::~Auto<Windows::Vector<uchar>>(void)
0x1801f3051  mov     rcx, [rbp+TokenHandle]; Handle
0x1801f3055  lea     rax, [rcx-1]
0x1801f3059  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f305d  ja      short loc_1801F306F
0x1801f305f  mov     [rbp+TokenHandle], rdi
0x1801f3063  call    cs:__imp_NtClose
0x1801f306a  nop     dword ptr [rax+rax+00h]
0x1801f306f  xor     eax, eax
0x1801f3071  mov     rcx, [rbp+var_8]
0x1801f3075  xor     rcx, rsp; StackCookie
0x1801f3078  call    __security_check_cookie
0x1801f307d  lea     r11, [rsp+80h+var_s0]
0x1801f3085  mov     rbx, [r11+10h]
0x1801f3089  mov     rdi, [r11+18h]
0x1801f308d  mov     rsp, r11
0x1801f3090  pop     rbp
0x1801f3091  retn
```
