# HamIsHostBeingDebugged

- ea: `0x180010e20`
- end: `0x180010f3c`
- name: `HamIsHostBeingDebugged`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _BYTE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180010e20`
- `0x18001ad0c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180010e6d`
- `ntdll!RtlLengthSid` at `0x180010ec2`
- `ntdll!RtlLengthSid` at `0x180010e6d`
- `ntdll!RtlLengthSid` at `0x180010ec2`
- `RPCRT4!RpcExceptionFilter` at `0x18001b6c2`
- `RPCRT4!RpcExceptionFilter` at `0x18001b6c2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180010efe`
- `RPCRT4!I_RpcMapWin32Status` at `0x180010efe`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcIsHostBeingDebugged` at `0x180010e9b`
- `ext-ms-win-hostactivitymanager-ham-private-ext-l1-1-0!HampInProcIsHostBeingDebugged` at `0x180010e9b`

## pseudocode

```c
__int64 __fastcall HamIsHostBeingDebugged(_QWORD *a1, __int64 a2, _BYTE *a3)
{
  __int64 v6; // rbx
  int v7; // edi
  int v8; // esi
  __int64 v9; // r14
  ULONG v10; // eax
  int IsHostBeingDebugged; // ecx
  int v12; // r14d
  ULONG v13; // eax
  char v15; // [rsp+80h] [rbp+8h] BYREF
  _BYTE *v16; // [rsp+90h] [rbp+18h]

  v16 = a3;
  v15 = 0;
  v6 = *(_QWORD *)(a2 + 544);
  v7 = *(_DWORD *)(a2 + 536);
  v8 = *(_DWORD *)(a2 + 532);
  if ( a1[1] )
  {
    v9 = a2 + 464;
    v10 = RtlLengthSid((PSID)(a2 + 464));
    IsHostBeingDebugged = HampInProcIsHostBeingDebugged(a1[1], a2, v9, v10, v8, v7, v6, &v15);
  }
  else
  {
    v12 = a2 + 464;
    v13 = RtlLengthSid((PSID)(a2 + 464));
    IsHostBeingDebugged = HamRpcCltIsHostBeingDebugged(*a1, a2, v12, v13, v8, v7, v6, (__int64)&v15);
  }
  if ( IsHostBeingDebugged >= 0 )
    *a3 = v15;
  return (unsigned int)IsHostBeingDebugged;
}

```

## disassembly

```asm
0x180010e20  mov     rax, rsp
0x180010e23  mov     [rax+10h], rbx
0x180010e27  mov     [rax+20h], rsi
0x180010e2b  mov     [rax+18h], r8
0x180010e2f  push    rdi
0x180010e30  push    r12
0x180010e32  push    r13
0x180010e34  push    r14
0x180010e36  push    r15
0x180010e38  sub     rsp, 50h
0x180010e3c  mov     r15, r8
0x180010e3f  mov     r13, rdx
0x180010e42  mov     r12, rcx
0x180010e45  mov     byte ptr [rax+8], 0
0x180010e49  cmp     qword ptr [rcx+8], 0
0x180010e4e  jz      short loc_180010EA5
0x180010e50  mov     rbx, [rdx+220h]
0x180010e57  mov     edi, [rdx+218h]
0x180010e5d  mov     esi, [rdx+214h]
0x180010e63  lea     r14, [rdx+1D0h]
0x180010e6a  mov     rcx, r14; Sid
0x180010e6d  call    cs:__imp_RtlLengthSid
0x180010e73  lea     rcx, [rsp+78h+arg_0]
0x180010e7b  mov     [rsp+78h+var_40], rcx
0x180010e80  mov     [rsp+78h+var_48], rbx
0x180010e85  mov     [rsp+78h+var_50], edi
0x180010e89  mov     [rsp+78h+var_58], esi
0x180010e8d  mov     r9d, eax
0x180010e90  mov     r8, r14
0x180010e93  mov     rdx, r13
0x180010e96  mov     rcx, [r12+8]
0x180010e9b  call    cs:__imp_HampInProcIsHostBeingDebugged
0x180010ea1  mov     ecx, eax
0x180010ea3  jmp     short loc_180010F12
0x180010ea5  mov     rbx, [rdx+220h]
0x180010eac  mov     edi, [rdx+218h]
0x180010eb2  mov     esi, [rdx+214h]
0x180010eb8  lea     r14, [rdx+1D0h]
0x180010ebf  mov     rcx, r14; Sid
0x180010ec2  call    cs:__imp_RtlLengthSid
0x180010ec8  lea     rcx, [rsp+78h+arg_0]
0x180010ed0  mov     [rsp+78h+var_40], rcx
0x180010ed5  mov     [rsp+78h+var_48], rbx
0x180010eda  mov     [rsp+78h+var_50], edi
0x180010ede  mov     [rsp+78h+var_58], esi
0x180010ee2  mov     r9d, eax
0x180010ee5  mov     r8, r14
0x180010ee8  mov     rdx, r13
0x180010eeb  mov     rcx, [r12]
0x180010eef  call    HamRpcCltIsHostBeingDebugged
0x180010ef4  mov     ecx, eax
0x180010ef6  mov     [rsp+78h+var_38], eax
0x180010efa  jmp     short loc_180010F12
0x180010efc  mov     ecx, eax; Status
0x180010efe  call    cs:__imp_I_RpcMapWin32Status
0x180010f04  mov     ecx, eax
0x180010f06  mov     [rsp+78h+var_38], eax
0x180010f0a  mov     r15, [rsp+78h+arg_10]
0x180010f12  test    ecx, ecx
0x180010f14  js      short loc_180010F20
0x180010f16  mov     al, [rsp+78h+arg_0]
0x180010f1d  mov     [r15], al
0x180010f20  mov     eax, ecx
0x180010f22  lea     r11, [rsp+78h+var_28]
0x180010f27  mov     rbx, [r11+38h]
0x180010f2b  mov     rsi, [r11+48h]
0x180010f2f  mov     rsp, r11
0x180010f32  pop     r15
0x180010f34  pop     r14
0x180010f36  pop     r13
0x180010f38  pop     r12
0x180010f3a  pop     rdi
0x180010f3b  retn
0x18001b6b4  push    rbp
0x18001b6b6  sub     rsp, 40h
0x18001b6ba  mov     rbp, rdx
0x18001b6bd  mov     rcx, [rcx]
0x18001b6c0  mov     ecx, [rcx]; ExceptionCode
0x18001b6c2  call    cs:__imp_RpcExceptionFilter
0x18001b6c8  nop
0x18001b6c9  add     rsp, 40h
0x18001b6cd  pop     rbp
0x18001b6ce  retn
```
