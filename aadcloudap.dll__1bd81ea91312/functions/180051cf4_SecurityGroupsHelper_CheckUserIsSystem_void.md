# SecurityGroupsHelper::CheckUserIsSystem(void *)

- ea: `0x180051cf4`
- end: `0x180051e72`
- name: `?CheckUserIsSystem@SecurityGroupsHelper@@SAJPEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044ce4`
- `0x180046118`
- `0x180049e5c`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x180051cf4`
- `0x180071e14`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180051ddd`
- `ntdll!RtlEqualSid` at `0x180051df2`
- `ntdll!RtlEqualSid` at `0x180051ddd`
- `ntdll!RtlEqualSid` at `0x180051df2`
- `ntdll!NtQueryInformationToken` at `0x180051da1`
- `ntdll!NtQueryInformationToken` at `0x180051da1`

## string_xrefs

- `0x180051d2e`: `SecurityGroupsHelper::CheckUserIsSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SecurityGroupsHelper::CheckUserIsSystem(HANDLE TokenHandle)
{
  NTSTATUS v2; // ecx
  unsigned int v3; // ebx
  PULONG ReturnLength; // [rsp+20h] [rbp-89h]
  int v6; // [rsp+30h] [rbp-79h]
  NTSTATUS v7; // [rsp+50h] [rbp-59h] BYREF
  ULONG v8; // [rsp+54h] [rbp-55h] BYREF
  const char *v9[7]; // [rsp+58h] [rbp-51h] BYREF
  PSID TokenInformation[12]; // [rsp+90h] [rbp-19h] BYREF

  v7 = 0;
  v8 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v9,
    (int)"securitygroupshelper.cpp",
    (int)"SecurityGroupsHelper::CheckUserIsSystem",
    (int)&v7);
  memset_0(TokenInformation, 0, 0x58u);
  if ( !TokenHandle )
  {
    v2 = -1073741811;
    v6 = 54;
LABEL_8:
    v7 = v2;
    goto LABEL_9;
  }
  v2 = NtQueryInformationToken(TokenHandle, TokenUser, TokenInformation, 0x58u, &v8);
  v7 = v2;
  if ( v2 < 0 )
  {
    v6 = 57;
LABEL_9:
    LODWORD(ReturnLength) = v2;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "securitygroupshelper.cpp", v6, "NTSTATUS", &base);
    goto LABEL_10;
  }
  if ( !RtlEqualSid(TokenInformation[0], qword_1800E5410) && !RtlEqualSid(TokenInformation[0], qword_1800E5420) )
  {
    v2 = -1073741790;
    v6 = 62;
    goto LABEL_8;
  }
LABEL_10:
  v3 = v7;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v9);
  return v3;
}

```

## disassembly

```asm
0x180051cf4  mov     [rsp-8+arg_8], rbx
0x180051cf9  mov     [rsp-8+arg_10], rdi
0x180051cfe  push    rbp
0x180051cff  lea     rbp, [rsp-57h]
0x180051d04  sub     rsp, 100h
0x180051d0b  mov     rax, cs:__security_cookie
0x180051d12  xor     rax, rsp
0x180051d15  mov     [rbp+57h+var_10], rax
0x180051d19  mov     rbx, rcx
0x180051d1c  mov     [rbp+57h+var_B0], 0
0x180051d23  mov     [rbp+57h+var_AC], 0
0x180051d2a  lea     r9, [rbp+57h+var_B0]
0x180051d2e  lea     r8, aSecuritygroups_1; "SecurityGroupsHelper::CheckUserIsSystem"
0x180051d35  lea     rdi, aOnecoreuapDsEx_37+21h; "securitygroupshelper.cpp"
0x180051d3c  mov     rdx, rdi
0x180051d3f  lea     rcx, [rbp+57h+var_A8]
0x180051d43  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180051d48  nop
0x180051d49  xor     edx, edx; Val
0x180051d4b  lea     r8d, [rdx+58h]; Size
0x180051d4f  lea     rcx, [rbp+57h+TokenInformation]; void *
0x180051d53  call    memset_0
0x180051d58  test    rbx, rbx
0x180051d5b  jnz     short loc_180051D87
0x180051d5d  mov     ecx, 0C000000Dh
0x180051d62  lea     rax, base
0x180051d69  mov     [rsp+100h+var_C0], rax
0x180051d6e  lea     rax, aNtstatus; "NTSTATUS"
0x180051d75  mov     [rsp+100h+var_C8], rax
0x180051d7a  mov     [rsp+100h+var_D0], 36h ; '6'
0x180051d82  jmp     loc_180051E21
0x180051d87  lea     rax, [rbp+57h+var_AC]
0x180051d8b  mov     [rsp+100h+ReturnLength], rax; ReturnLength
0x180051d90  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180051d96  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180051d9a  lea     edx, [r9-57h]; TokenInformationClass
0x180051d9e  mov     rcx, rbx; TokenHandle
0x180051da1  call    cs:__imp_NtQueryInformationToken
0x180051da7  mov     ecx, eax
0x180051da9  mov     [rbp+57h+var_B0], eax
0x180051dac  test    eax, eax
0x180051dae  jns     short loc_180051DD2
0x180051db0  lea     rax, base
0x180051db7  mov     [rsp+100h+var_C0], rax
0x180051dbc  lea     rax, aNtstatus; "NTSTATUS"
0x180051dc3  mov     [rsp+100h+var_C8], rax
0x180051dc8  mov     [rsp+100h+var_D0], 39h ; '9'
0x180051dd0  jmp     short loc_180051E24
0x180051dd2  lea     rdx, qword_1800E5410; Sid2
0x180051dd9  mov     rcx, [rbp+57h+TokenInformation]; Sid1
0x180051ddd  call    cs:__imp_RtlEqualSid
0x180051de3  test    al, al
0x180051de5  jnz     short loc_180051E43
0x180051de7  lea     rdx, qword_1800E5420; Sid2
0x180051dee  mov     rcx, [rbp+57h+TokenInformation]; Sid1
0x180051df2  call    cs:__imp_RtlEqualSid
0x180051df8  test    al, al
0x180051dfa  jnz     short loc_180051E43
0x180051dfc  mov     ecx, 0C0000022h
0x180051e01  lea     rax, base
0x180051e08  mov     [rsp+100h+var_C0], rax
0x180051e0d  lea     rax, aNtstatus; "NTSTATUS"
0x180051e14  mov     [rsp+100h+var_C8], rax
0x180051e19  mov     [rsp+100h+var_D0], 3Eh ; '>'
0x180051e21  mov     [rbp+57h+var_B0], ecx
0x180051e24  mov     [rsp+100h+var_D8], rdi
0x180051e29  mov     dword ptr [rsp+100h+ReturnLength], ecx
0x180051e2d  mov     ecx, 2
0x180051e32  mov     r9d, ecx
0x180051e35  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180051e3c  xor     edx, edx
0x180051e3e  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180051e43  mov     ebx, [rbp+57h+var_B0]
0x180051e46  lea     rcx, [rbp+57h+var_A8]
0x180051e4a  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180051e4f  mov     eax, ebx
0x180051e51  mov     rcx, [rbp+57h+var_10]
0x180051e55  xor     rcx, rsp; StackCookie
0x180051e58  call    __security_check_cookie
0x180051e5d  lea     r11, [rsp+100h+var_s0]
0x180051e65  mov     rbx, [r11+18h]
0x180051e69  mov     rdi, [r11+20h]
0x180051e6d  mov     rsp, r11
0x180051e70  pop     rbp
0x180051e71  retn
```
