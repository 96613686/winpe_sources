# GetCallerPackageCapabilities(AadContextFunctions *,void *,_TOKEN_GROUPS * *)

- ea: `0x180028e50`
- end: `0x180029043`
- name: `?GetCallerPackageCapabilities@@YAJPEAVAadContextFunctions@@PEAXPEAPEAU_TOKEN_GROUPS@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, void *, struct _TOKEN_GROUPS **)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180024314`
- `0x180024910`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180028e50`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180028ed5`
- `ntdll!NtQueryInformationToken` at `0x180028f72`
- `ntdll!NtQueryInformationToken` at `0x180028ed5`
- `ntdll!NtQueryInformationToken` at `0x180028f72`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCallerPackageCapabilities(struct AadContextFunctions *a1, void *a2, struct _TOKEN_GROUPS **a3)
{
  NTSTATUS v6; // eax
  struct _TOKEN_GROUPS *v7; // rdi
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  PULONG ReturnLength; // [rsp+20h] [rbp-60h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-60h]
  int v13; // [rsp+30h] [rbp-50h]
  _BYTE v14[48]; // [rsp+50h] [rbp-30h] BYREF
  NTSTATUS v15; // [rsp+B0h] [rbp+30h] BYREF
  ULONG TokenInformationLength; // [rsp+C8h] [rbp+48h] BYREF

  v15 = 0;
  TokenInformationLength = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v14,
    "login.cpp",
    "GetCallerPackageCapabilities",
    &v15);
  if ( !a1 || !a2 || !a3 )
  {
    v6 = -1073741811;
    v13 = 2563;
    goto LABEL_13;
  }
  *a3 = 0;
  v6 = NtQueryInformationToken(a2, TokenCapabilities, 0, TokenInformationLength, &TokenInformationLength);
  v15 = v6;
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741789 )
  {
    v13 = 2571;
LABEL_14:
    LODWORD(ReturnLength) = v6;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLength, "login.cpp", v13, "NTSTATUS", &base);
    goto LABEL_15;
  }
  v7 = (struct _TOKEN_GROUPS *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, _QWORD))(*(_QWORD *)a1 + 24LL))(
                                 a1,
                                 TokenInformationLength);
  if ( !v7 )
  {
    v6 = -1073741801;
    v13 = 2577;
LABEL_13:
    v15 = v6;
    goto LABEL_14;
  }
  v8 = NtQueryInformationToken(a2, TokenCapabilities, v7, TokenInformationLength, &TokenInformationLength);
  v15 = v8;
  if ( v8 >= 0 )
  {
    *a3 = v7;
  }
  else
  {
    LODWORD(ReturnLengtha) = v8;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, ReturnLengtha, "login.cpp", 2580, "NTSTATUS", &base);
    (*(void (__fastcall **)(struct AadContextFunctions *, struct _TOKEN_GROUPS *))(*(_QWORD *)a1 + 32LL))(a1, v7);
  }
LABEL_15:
  v9 = v15;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v14);
  return v9;
}

```

## disassembly

```asm
0x180028e50  mov     [rsp-28h+arg_8], rbx
0x180028e55  push    rbp
0x180028e56  push    rsi
0x180028e57  push    rdi
0x180028e58  push    r12
0x180028e5a  push    r14
0x180028e5c  mov     rbp, rsp
0x180028e5f  sub     rsp, 80h
0x180028e66  mov     rbx, r8
0x180028e69  mov     r14, rdx
0x180028e6c  mov     rsi, rcx
0x180028e6f  mov     [rbp+arg_0], 0
0x180028e76  mov     [rbp+TokenInformationLength], 0
0x180028e7d  lea     r9, [rbp+arg_0]
0x180028e81  lea     r8, aGetcallerpacka_1; "GetCallerPackageCapabilities"
0x180028e88  lea     r12, aOnecoreuapDsEx_25+21h; "login.cpp"
0x180028e8f  mov     rdx, r12
0x180028e92  lea     rcx, [rbp+var_30]
0x180028e96  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180028e9b  nop
0x180028e9c  test    rsi, rsi
0x180028e9f  jz      loc_180028FD7
0x180028ea5  test    r14, r14
0x180028ea8  jz      loc_180028FD7
0x180028eae  test    rbx, rbx
0x180028eb1  jz      loc_180028FD7
0x180028eb7  mov     qword ptr [rbx], 0
0x180028ebe  lea     rax, [rbp+TokenInformationLength]
0x180028ec2  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180028ec7  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180028ecb  xor     r8d, r8d; TokenInformation
0x180028ece  lea     edx, [r8+1Eh]; TokenInformationClass
0x180028ed2  mov     rcx, r14; TokenHandle
0x180028ed5  call    cs:__imp_NtQueryInformationToken
0x180028edb  mov     [rbp+arg_0], eax
0x180028ede  mov     edx, 80000000h
0x180028ee3  lea     ecx, [rax+rdx]
0x180028ee6  test    edx, ecx
0x180028ee8  jnz     short loc_180028F16
0x180028eea  cmp     eax, 0C0000023h
0x180028eef  jz      short loc_180028F16
0x180028ef1  lea     rcx, base
0x180028ef8  mov     [rsp+80h+var_40], rcx
0x180028efd  lea     rcx, aNtstatus; "NTSTATUS"
0x180028f04  mov     [rsp+80h+var_48], rcx
0x180028f09  mov     [rsp+80h+var_50], 0A0Bh
0x180028f11  jmp     loc_180028FFF
0x180028f16  mov     rax, [rsi]
0x180028f19  mov     edx, [rbp+TokenInformationLength]
0x180028f1c  mov     rcx, rsi
0x180028f1f  mov     rax, [rax+18h]
0x180028f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f28  mov     rdi, rax
0x180028f2b  test    rax, rax
0x180028f2e  jnz     short loc_180028F5A
0x180028f30  mov     eax, 0C0000017h
0x180028f35  lea     rcx, base
0x180028f3c  mov     [rsp+80h+var_40], rcx
0x180028f41  lea     rcx, aNtstatus; "NTSTATUS"
0x180028f48  mov     [rsp+80h+var_48], rcx
0x180028f4d  mov     [rsp+80h+var_50], 0A11h
0x180028f55  jmp     loc_180028FFC
0x180028f5a  lea     rax, [rbp+TokenInformationLength]
0x180028f5e  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180028f63  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180028f67  mov     r8, rdi; TokenInformation
0x180028f6a  mov     edx, 1Eh; TokenInformationClass
0x180028f6f  mov     rcx, r14; TokenHandle
0x180028f72  call    cs:__imp_NtQueryInformationToken
0x180028f78  mov     [rbp+arg_0], eax
0x180028f7b  test    eax, eax
0x180028f7d  jns     short loc_180028FD2
0x180028f7f  lea     rcx, base
0x180028f86  mov     [rsp+80h+var_40], rcx
0x180028f8b  lea     rcx, aNtstatus; "NTSTATUS"
0x180028f92  mov     [rsp+80h+var_48], rcx
0x180028f97  mov     [rsp+80h+var_50], 0A14h
0x180028f9f  mov     [rsp+80h+var_58], r12
0x180028fa4  mov     dword ptr [rsp+80h+ReturnLength], eax
0x180028fa8  mov     ecx, 2
0x180028fad  mov     r9d, ecx
0x180028fb0  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180028fb7  xor     edx, edx
0x180028fb9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180028fbe  mov     rax, [rsi]
0x180028fc1  mov     rdx, rdi
0x180028fc4  mov     rcx, rsi
0x180028fc7  mov     rax, [rax+20h]
0x180028fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fd0  jmp     short loc_18002901E
0x180028fd2  mov     [rbx], rdi
0x180028fd5  jmp     short loc_18002901E
0x180028fd7  mov     eax, 0C000000Dh
0x180028fdc  lea     rcx, base
0x180028fe3  mov     [rsp+80h+var_40], rcx
0x180028fe8  lea     rcx, aNtstatus; "NTSTATUS"
0x180028fef  mov     [rsp+80h+var_48], rcx
0x180028ff4  mov     [rsp+80h+var_50], 0A03h
0x180028ffc  mov     [rbp+arg_0], eax
0x180028fff  mov     [rsp+80h+var_58], r12
0x180029004  mov     ecx, 2
0x180029009  mov     dword ptr [rsp+80h+ReturnLength], eax
0x18002900d  mov     r9d, ecx
0x180029010  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180029017  xor     edx, edx
0x180029019  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002901e  mov     ebx, [rbp+arg_0]
0x180029021  lea     rcx, [rbp+var_30]
0x180029025  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18002902a  mov     eax, ebx
0x18002902c  mov     rbx, [rsp+80h+arg_8]
0x180029034  add     rsp, 80h
0x18002903b  pop     r14
0x18002903d  pop     r12
0x18002903f  pop     rdi
0x180029040  pop     rsi
0x180029041  pop     rbp
0x180029042  retn
```
