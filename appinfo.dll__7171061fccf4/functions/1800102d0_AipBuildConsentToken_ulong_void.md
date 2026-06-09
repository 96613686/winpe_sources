# AipBuildConsentToken(ulong,void * *)

- ea: `0x1800102d0`
- end: `0x180010428`
- name: `?AipBuildConsentToken@@YAKKPEAPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(int, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800290b4`

## callees

- `0x1800102d0`
- `0x180046e50`

## import_xrefs

- `ntdll!NtClose` at `0x1800103dc`
- `ntdll!NtClose` at `0x18001040a`
- `ntdll!NtClose` at `0x1800103dc`
- `ntdll!NtClose` at `0x18001040a`
- `ntdll!RtlNtStatusToDosError` at `0x1800103cb`
- `ntdll!RtlNtStatusToDosError` at `0x1800103cb`
- `ntdll!RtlRemovePrivileges` at `0x1800103bf`
- `ntdll!RtlRemovePrivileges` at `0x1800103bf`
- `ntdll!NtDuplicateToken` at `0x18001038a`
- `ntdll!NtDuplicateToken` at `0x18001038a`
- `ntdll!NtOpenProcessToken` at `0x180010348`
- `ntdll!NtOpenProcessToken` at `0x180010348`
- `ntdll!NtSetInformationToken` at `0x1800103a7`
- `ntdll!NtSetInformationToken` at `0x1800103a7`

## pseudocode

```c
__int64 __fastcall AipBuildConsentToken(int a1, void **a2)
{
  int v3; // eax
  ULONG v4; // ebx
  void *NewTokenHandle; // [rsp+38h] [rbp-29h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-11h] BYREF
  _DWORD v10[6]; // [rsp+80h] [rbp+1Fh] BYREF

  TokenInformation = a1;
  v10[0] = 7;
  TokenHandle = 0;
  NewTokenHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v10[1] = 17;
  v10[2] = 18;
  v10[3] = 23;
  v10[4] = 29;
  v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x1ABu, &TokenHandle);
  if ( v3 >= 0
    && (ObjectAttributes.Length = 48,
        memset(&ObjectAttributes.RootDirectory, 0, 20),
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        v3 = NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenPrimary, &NewTokenHandle),
        v3 >= 0)
    && (v3 = NtSetInformationToken(NewTokenHandle, TokenSessionId, &TokenInformation, 4u), v3 >= 0)
    && (v3 = RtlRemovePrivileges(NewTokenHandle, v10, 5), v3 >= 0) )
  {
    v4 = 0;
    *a2 = NewTokenHandle;
  }
  else
  {
    v4 = RtlNtStatusToDosError(v3);
    if ( !NewTokenHandle )
      goto LABEL_9;
    NtClose(NewTokenHandle);
  }
  NewTokenHandle = 0;
LABEL_9:
  if ( TokenHandle )
    NtClose(TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x1800102d0  mov     r11, rsp
0x1800102d3  push    rbp
0x1800102d4  push    rbx
0x1800102d5  lea     rbp, [r11-5Fh]
0x1800102d9  sub     rsp, 0A8h
0x1800102e0  mov     rax, cs:__security_cookie
0x1800102e7  xor     rax, rsp
0x1800102ea  mov     [rbp+57h+var_20], rax
0x1800102ee  xorps   xmm0, xmm0
0x1800102f1  mov     [r11+18h], rsi
0x1800102f5  mov     [r11-18h], rdi
0x1800102f9  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1800102fd  mov     rdi, rdx
0x180010300  mov     [rbp+57h+TokenInformation], ecx
0x180010303  xor     esi, esi
0x180010305  mov     [rbp+57h+var_38], 7
0x18001030c  mov     edx, 1ABh; DesiredAccess
0x180010311  mov     [rbp+57h+TokenHandle], rsi
0x180010315  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001031c  mov     [rbp+57h+NewTokenHandle], rsi
0x180010320  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180010324  mov     [rbp+57h+var_34], 11h
0x18001032b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001032f  mov     [rbp+57h+var_30], 12h
0x180010336  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001033a  mov     [rbp+57h+var_2C], 17h
0x180010341  mov     [rbp+57h+var_28], 1Dh
0x180010348  call    cs:__imp_NtOpenProcessToken
0x18001034e  test    eax, eax
0x180010350  js      short loc_1800103C9
0x180010352  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x180010356  lea     rax, [rbp+57h+NewTokenHandle]
0x18001035a  xorps   xmm0, xmm0
0x18001035d  mov     [rsp+28h], rax; NewTokenHandle
0x180010362  xor     r9d, r9d; EffectiveOnly
0x180010365  mov     [rsp+0B0h+TokenType], 1; TokenType
0x18001036d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180010371  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180010378  xor     edx, edx; DesiredAccess
0x18001037a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18001037e  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180010381  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180010385  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001038a  call    cs:__imp_NtDuplicateToken
0x180010390  test    eax, eax
0x180010392  js      short loc_1800103C9
0x180010394  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x180010398  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001039c  mov     r9d, 4; TokenInformationLength
0x1800103a2  mov     edx, 0Ch; TokenInformationClass
0x1800103a7  call    cs:__imp_NtSetInformationToken
0x1800103ad  test    eax, eax
0x1800103af  js      short loc_1800103C9
0x1800103b1  mov     rcx, [rbp+57h+NewTokenHandle]
0x1800103b5  lea     rdx, [rbp+57h+var_38]
0x1800103b9  mov     r8d, 5
0x1800103bf  call    cs:__imp_RtlRemovePrivileges
0x1800103c5  test    eax, eax
0x1800103c7  jns     short loc_1800103E4
0x1800103c9  mov     ecx, eax; Status
0x1800103cb  call    cs:__imp_RtlNtStatusToDosError
0x1800103d1  mov     ebx, eax
0x1800103d3  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x1800103d7  test    rcx, rcx
0x1800103da  jz      short loc_1800103F1
0x1800103dc  call    cs:__imp_NtClose
0x1800103e2  jmp     short loc_1800103ED
0x1800103e4  mov     rax, [rbp+57h+NewTokenHandle]
0x1800103e8  mov     ebx, esi
0x1800103ea  mov     [rdi], rax
0x1800103ed  mov     [rbp+57h+NewTokenHandle], rsi
0x1800103f1  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800103f5  mov     rdi, [rsp+0A0h]
0x1800103fd  mov     rsi, [rsp+0B0h+arg_10]
0x180010405  test    rcx, rcx
0x180010408  jz      short loc_180010410
0x18001040a  call    cs:__imp_NtClose
0x180010410  mov     eax, ebx
0x180010412  mov     rcx, [rbp+57h+var_20]
0x180010416  xor     rcx, rsp; StackCookie
0x180010419  call    __security_check_cookie
0x18001041e  add     rsp, 0A8h
0x180010425  pop     rbx
0x180010426  pop     rbp
0x180010427  retn
```
