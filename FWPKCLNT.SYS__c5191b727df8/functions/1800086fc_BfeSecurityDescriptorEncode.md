# BfeSecurityDescriptorEncode

- ea: `0x1800086fc`
- end: `0x180008804`
- name: `BfeSecurityDescriptorEncode`
- size: `264`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor, __int64, _QWORD *)`
- caller_count: `21`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e6a0`
- `0x18000f240`
- `0x180053660`
- `0x1800539a0`
- `0x180053db0`
- `0x180054000`
- `0x180054670`
- `0x180054d50`
- `0x1800550f0`
- `0x180056260`
- `0x180056770`
- `0x1800568b0`
- `0x180057050`
- `0x1800573a0`
- `0x180057880`
- `0x180057c30`
- `0x180058ee0`
- `0x180066590`
- `0x180066d70`
- `0x1800674f0`
- `0x180067670`

## callees

- `0x180004904`
- `0x180008480`
- `0x1800086fc`
- `0x18000c524`
- `0x18000c9b4`
- `0x1800203c0`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x180008768`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x180008768`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1800087a9`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1800087a9`

## string_xrefs

- `0x1800087de`: `BfeSecurityDescriptorEncode`

## pseudocode

```c
__int64 __fastcall BfeSecurityDescriptorEncode(PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rbx
  ULONG v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  PSECURITY_DESCRIPTOR v12; // rbp
  NTSTATUS v13; // eax
  __int64 v14; // rcx
  PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor; // [rsp+20h] [rbp-48h] BYREF
  ULONG BufferLength; // [rsp+28h] [rbp-40h] BYREF

  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *a3 = 0;
  v6 = 0;
  BufferLength = 0;
  SelfRelativeSecurityDescriptor = 0;
  if ( AbsoluteSecurityDescriptor )
  {
    v8 = RtlLengthSecurityDescriptor(AbsoluteSecurityDescriptor);
    BufferLength = v8;
    if ( *((__int16 *)AbsoluteSecurityDescriptor + 1) < 0 )
    {
      *(_QWORD *)(a2 + 8) = AbsoluteSecurityDescriptor;
LABEL_10:
      *(_DWORD *)a2 = v8;
      return v6;
    }
    v6 = WfpPoolAllocQualified(v8, v9, v10, (__int64 *)&SelfRelativeSecurityDescriptor);
    if ( !v6 )
    {
      v12 = SelfRelativeSecurityDescriptor;
      v13 = RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, SelfRelativeSecurityDescriptor, &BufferLength);
      if ( v13 >= 0 )
      {
        v8 = BufferLength;
        *(_QWORD *)(a2 + 8) = v12;
        *a3 = v12;
        goto LABEL_10;
      }
      v6 = WfpReportSysErrorAsNtStatus(v14, (int)"RtlAbsoluteToSelfRelativeSD", v13);
      if ( !v6 )
        return v6;
    }
    WfpNamedPoolFree(v11, &SelfRelativeSecurityDescriptor);
    WfpReportError(v6, (int)"BfeSecurityDescriptorEncode");
  }
  return v6;
}

```

## disassembly

```asm
0x1800086fc  mov     [rsp+arg_18], rbx
0x180008701  push    rbp
0x180008702  push    rsi
0x180008703  push    rdi
0x180008704  push    r14
0x180008706  push    r15
0x180008708  sub     rsp, 40h
0x18000870c  mov     rax, cs:__security_cookie
0x180008713  xor     rax, rsp
0x180008716  mov     [rsp+68h+var_38], rax
0x18000871b  xor     r15d, r15d
0x18000871e  mov     r14, r8
0x180008721  mov     [rdx], r15d
0x180008724  mov     rdi, rdx
0x180008727  mov     [rdx+8], r15
0x18000872b  mov     rsi, rcx
0x18000872e  mov     [r8], r15
0x180008731  mov     ebx, r15d
0x180008734  mov     [rsp+68h+BufferLength], r15d
0x180008739  mov     [rsp+68h+SelfRelativeSecurityDescriptor], r15
0x18000873e  test    rcx, rcx
0x180008741  jnz     short loc_180008768
0x180008743  mov     rax, rbx
0x180008746  mov     rcx, [rsp+68h+var_38]
0x18000874b  xor     rcx, rsp; StackCookie
0x18000874e  call    __security_check_cookie
0x180008753  mov     rbx, [rsp+68h+arg_18]
0x18000875b  add     rsp, 40h
0x18000875f  pop     r15
0x180008761  pop     r14
0x180008763  pop     rdi
0x180008764  pop     rsi
0x180008765  pop     rbp
0x180008766  retn
0x180008768  call    cs:__imp_RtlLengthSecurityDescriptor
0x18000876f  nop     dword ptr [rax+rax+00h]
0x180008774  mov     [rsp+68h+BufferLength], eax
0x180008778  cmp     [rsi+2], r15w
0x18000877d  jge     short loc_180008785
0x18000877f  mov     [rdi+8], rsi
0x180008783  jmp     short loc_1800087FD
0x180008785  mov     ecx, eax
0x180008787  lea     r9, [rsp+68h+SelfRelativeSecurityDescriptor]
0x18000878c  call    WfpPoolAllocQualified
0x180008791  mov     rbx, rax
0x180008794  test    rax, rax
0x180008797  jnz     short loc_1800087D4
0x180008799  mov     rbp, [rsp+68h+SelfRelativeSecurityDescriptor]
0x18000879e  lea     r8, [rsp+68h+BufferLength]; BufferLength
0x1800087a3  mov     rdx, rbp; SelfRelativeSecurityDescriptor
0x1800087a6  mov     rcx, rsi; AbsoluteSecurityDescriptor
0x1800087a9  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1800087b0  nop     dword ptr [rax+rax+00h]
0x1800087b5  test    eax, eax
0x1800087b7  jns     short loc_1800087F2
0x1800087b9  mov     r8d, eax
0x1800087bc  lea     rdx, aRtlabsolutetos; "RtlAbsoluteToSelfRelativeSD"
0x1800087c3  call    WfpReportSysErrorAsNtStatus
0x1800087c8  mov     rbx, rax
0x1800087cb  test    rax, rax
0x1800087ce  jz      loc_180008743
0x1800087d4  lea     rdx, [rsp+68h+SelfRelativeSecurityDescriptor]
0x1800087d9  call    WfpNamedPoolFree
0x1800087de  lea     rdx, aBfesecuritydes; "BfeSecurityDescriptorEncode"
0x1800087e5  mov     rcx, rbx
0x1800087e8  call    WfpReportError
0x1800087ed  jmp     loc_180008743
0x1800087f2  mov     eax, [rsp+68h+BufferLength]
0x1800087f6  mov     [rdi+8], rbp
0x1800087fa  mov     [r14], rbp
0x1800087fd  mov     [rdi], eax
0x1800087ff  jmp     loc_180008743
```
