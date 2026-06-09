# VsmmMemPartpCreateSecurityDescriptor

- ea: `0x1400a9ad8`
- end: `0x1400a9db5`
- name: `VsmmMemPartpCreateSecurityDescriptor`
- size: `733`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor, PACL Dacl)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400a8228`
- `0x1400a9dbc`

## callees

- `0x140021c60`
- `0x14002f724`
- `0x14009b92c`
- `0x1400a9ad8`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x1400a9be5`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400a9be5`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a9c16`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a9ca6`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a9c16`
- `ntoskrnl!RtlInitializeSidEx` at `0x1400a9ca6`
- `ntoskrnl!RtlCreateAcl` at `0x1400a9b24`
- `ntoskrnl!RtlCreateAcl` at `0x1400a9b24`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a9ba2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a9c59`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a9ce9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a9ba2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a9c59`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400a9ce9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a9d21`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400a9d21`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a9d5c`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400a9d5c`

## string_xrefs

- `0x1400a9b46`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9b81`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9bc4`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9c38`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9c7b`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9cc8`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9d0b`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9d43`: `VsmmMemPartpCreateSecurityDescriptor`
- `0x1400a9d7e`: `VsmmMemPartpCreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall VsmmMemPartpCreateSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, PACL Dacl)
{
  NTSTATUS Acl; // eax
  unsigned int v5; // ebx
  int v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  int v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  ULONG v14; // [rsp+30h] [rbp-39h] BYREF
  int v15; // [rsp+34h] [rbp-35h] BYREF
  __int16 v16; // [rsp+38h] [rbp-31h]
  int v17; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int16 v18; // [rsp+40h] [rbp-29h]
  _BYTE Sid[80]; // [rsp+50h] [rbp-19h] BYREF

  v17 = 0;
  v18 = 1280;
  Acl = RtlCreateAcl(Dacl, 0xECu, 2u);
  v5 = Acl;
  if ( Acl < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      517,
      (unsigned int)Acl);
    return v5;
  }
  v14 = 68;
  v6 = VidSidInitializeVmCompute(Sid, &v14);
  v5 = v6;
  if ( v6 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      530,
      (unsigned int)v6);
    return v5;
  }
  v7 = RtlAddAccessAllowedAce(Dacl, 2u, 1u, Sid);
  v5 = v7;
  if ( v7 < 0 )
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      542,
      (unsigned int)v7);
    return v5;
  }
  v15 = 0;
  v16 = 1280;
  if ( v14 < RtlLengthRequiredSid(2u) )
  {
    v5 = -1073741789;
LABEL_10:
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      553,
      v5);
    return v5;
  }
  v5 = RtlInitializeSidEx(Sid, &v15, 2, 32, 544);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_10;
  v8 = RtlAddAccessAllowedAce(Dacl, 2u, 1u, Sid);
  v5 = v8;
  if ( v8 >= 0 )
  {
    v9 = RtlInitializeSidEx(Sid, &v17, 2, 83, 0);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v10 = RtlAddAccessAllowedAce(Dacl, 2u, 1u, Sid);
      v5 = v10;
      if ( v10 >= 0 )
      {
        v11 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        v5 = v11;
        if ( v11 >= 0 )
        {
          v12 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
          v5 = v12;
          if ( v12 >= 0 )
            return 0;
          else
            VidTraceErrorStatusInternal0(
              "VsmmMemPartpCreateSecurityDescriptor",
              "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
              618,
              (unsigned int)v12);
        }
        else
        {
          VidTraceErrorStatusInternal0(
            "VsmmMemPartpCreateSecurityDescriptor",
            "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
            606,
            (unsigned int)v11);
        }
      }
      else
      {
        VidTraceErrorStatusInternal0(
          "VsmmMemPartpCreateSecurityDescriptor",
          "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
          593,
          (unsigned int)v10);
      }
    }
    else
    {
      VidTraceErrorStatusInternal0(
        "VsmmMemPartpCreateSecurityDescriptor",
        "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
        581,
        (unsigned int)v9);
    }
  }
  else
  {
    VidTraceErrorStatusInternal0(
      "VsmmMemPartpCreateSecurityDescriptor",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c",
      565,
      (unsigned int)v8);
  }
  return v5;
}

```

## disassembly

```asm
0x1400a9ad8  mov     [rsp-8+arg_10], rbx
0x1400a9add  mov     [rsp-8+arg_18], rsi
0x1400a9ae2  push    rbp
0x1400a9ae3  push    rdi
0x1400a9ae4  push    r15
0x1400a9ae6  lea     rbp, [rsp-47h]
0x1400a9aeb  sub     rsp, 0B0h
0x1400a9af2  mov     rax, cs:__security_cookie
0x1400a9af9  xor     rax, rsp
0x1400a9afc  mov     [rbp+57h+var_20], rax
0x1400a9b00  mov     rdi, rdx
0x1400a9b03  mov     [rbp+57h+var_84], 0
0x1400a9b0a  mov     rsi, rcx
0x1400a9b0d  mov     [rbp+57h+var_80], 500h
0x1400a9b13  mov     r15d, 2
0x1400a9b19  mov     rcx, rdi; Acl
0x1400a9b1c  mov     r8d, r15d; AclRevision
0x1400a9b1f  mov     edx, 0ECh; AclLength
0x1400a9b24  call    cs:__imp_RtlCreateAcl
0x1400a9b2b  nop     dword ptr [rax+rax+00h]
0x1400a9b30  mov     ebx, eax
0x1400a9b32  test    eax, eax
0x1400a9b34  jns     short loc_1400A9B57
0x1400a9b36  mov     r9d, eax
0x1400a9b39  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9b40  mov     r8d, 205h
0x1400a9b46  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9b4d  call    VidTraceErrorStatusInternal0
0x1400a9b52  jmp     loc_1400A9D8E
0x1400a9b57  lea     rdx, [rbp+57h+var_90]
0x1400a9b5b  mov     [rbp+57h+var_90], 44h ; 'D'
0x1400a9b62  lea     rcx, [rbp+57h+Sid]
0x1400a9b66  call    VidSidInitializeVmCompute
0x1400a9b6b  mov     ebx, eax
0x1400a9b6d  test    eax, eax
0x1400a9b6f  jns     short loc_1400A9B92
0x1400a9b71  mov     r9d, eax
0x1400a9b74  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9b7b  mov     r8d, 212h
0x1400a9b81  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9b88  call    VidTraceErrorStatusInternal0
0x1400a9b8d  jmp     loc_1400A9D8E
0x1400a9b92  lea     r9, [rbp+57h+Sid]; Sid
0x1400a9b96  mov     r8d, 1; AccessMask
0x1400a9b9c  mov     edx, r15d; AceRevision
0x1400a9b9f  mov     rcx, rdi; Acl
0x1400a9ba2  call    cs:__imp_RtlAddAccessAllowedAce
0x1400a9ba9  nop     dword ptr [rax+rax+00h]
0x1400a9bae  mov     ebx, eax
0x1400a9bb0  test    eax, eax
0x1400a9bb2  jns     short loc_1400A9BD5
0x1400a9bb4  mov     r9d, eax
0x1400a9bb7  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9bbe  mov     r8d, 21Eh
0x1400a9bc4  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9bcb  call    VidTraceErrorStatusInternal0
0x1400a9bd0  jmp     loc_1400A9D8E
0x1400a9bd5  mov     ecx, r15d; SubAuthorityCount
0x1400a9bd8  mov     [rbp+57h+var_8C], 0
0x1400a9bdf  mov     [rbp+57h+var_88], 500h
0x1400a9be5  call    cs:__imp_RtlLengthRequiredSid
0x1400a9bec  nop     dword ptr [rax+rax+00h]
0x1400a9bf1  cmp     [rbp+57h+var_90], eax
0x1400a9bf4  jnb     short loc_1400A9BFD
0x1400a9bf6  mov     ebx, 0C0000023h
0x1400a9bfb  jmp     short loc_1400A9C28
0x1400a9bfd  mov     r9d, 20h ; ' '
0x1400a9c03  mov     dword ptr [rsp+0C0h+var_A0], 220h
0x1400a9c0b  mov     r8d, r15d
0x1400a9c0e  lea     rdx, [rbp+57h+var_8C]
0x1400a9c12  lea     rcx, [rbp+57h+Sid]
0x1400a9c16  call    cs:__imp_RtlInitializeSidEx
0x1400a9c1d  nop     dword ptr [rax+rax+00h]
0x1400a9c22  mov     ebx, eax
0x1400a9c24  test    eax, eax
0x1400a9c26  jns     short loc_1400A9C49
0x1400a9c28  mov     r9d, ebx
0x1400a9c2b  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9c32  mov     r8d, 229h
0x1400a9c38  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9c3f  call    VidTraceErrorStatusInternal0
0x1400a9c44  jmp     loc_1400A9D8E
0x1400a9c49  lea     r9, [rbp+57h+Sid]; Sid
0x1400a9c4d  mov     r8d, 1; AccessMask
0x1400a9c53  mov     edx, r15d; AceRevision
0x1400a9c56  mov     rcx, rdi; Acl
0x1400a9c59  call    cs:__imp_RtlAddAccessAllowedAce
0x1400a9c60  nop     dword ptr [rax+rax+00h]
0x1400a9c65  mov     ebx, eax
0x1400a9c67  test    eax, eax
0x1400a9c69  jns     short loc_1400A9C8C
0x1400a9c6b  mov     r9d, eax
0x1400a9c6e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9c75  mov     r8d, 235h
0x1400a9c7b  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9c82  call    VidTraceErrorStatusInternal0
0x1400a9c87  jmp     loc_1400A9D8E
0x1400a9c8c  mov     r9d, 53h ; 'S'
0x1400a9c92  mov     [rsp+0C0h+var_A0], 0
0x1400a9c9b  mov     r8d, r15d
0x1400a9c9e  lea     rdx, [rbp+57h+var_84]
0x1400a9ca2  lea     rcx, [rbp+57h+Sid]
0x1400a9ca6  call    cs:__imp_RtlInitializeSidEx
0x1400a9cad  nop     dword ptr [rax+rax+00h]
0x1400a9cb2  mov     ebx, eax
0x1400a9cb4  test    eax, eax
0x1400a9cb6  jns     short loc_1400A9CD9
0x1400a9cb8  mov     r9d, eax
0x1400a9cbb  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9cc2  mov     r8d, 245h
0x1400a9cc8  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9ccf  call    VidTraceErrorStatusInternal0
0x1400a9cd4  jmp     loc_1400A9D8E
0x1400a9cd9  lea     r9, [rbp+57h+Sid]; Sid
0x1400a9cdd  mov     r8d, 1; AccessMask
0x1400a9ce3  mov     edx, r15d; AceRevision
0x1400a9ce6  mov     rcx, rdi; Acl
0x1400a9ce9  call    cs:__imp_RtlAddAccessAllowedAce
0x1400a9cf0  nop     dword ptr [rax+rax+00h]
0x1400a9cf5  mov     ebx, eax
0x1400a9cf7  test    eax, eax
0x1400a9cf9  jns     short loc_1400A9D19
0x1400a9cfb  mov     r9d, eax
0x1400a9cfe  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9d05  mov     r8d, 251h
0x1400a9d0b  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9d12  call    VidTraceErrorStatusInternal0
0x1400a9d17  jmp     short loc_1400A9D8E
0x1400a9d19  mov     edx, 1; Revision
0x1400a9d1e  mov     rcx, rsi; SecurityDescriptor
0x1400a9d21  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400a9d28  nop     dword ptr [rax+rax+00h]
0x1400a9d2d  mov     ebx, eax
0x1400a9d2f  test    eax, eax
0x1400a9d31  jns     short loc_1400A9D51
0x1400a9d33  mov     r9d, eax
0x1400a9d36  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9d3d  mov     r8d, 25Eh
0x1400a9d43  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9d4a  call    VidTraceErrorStatusInternal0
0x1400a9d4f  jmp     short loc_1400A9D8E
0x1400a9d51  xor     r9d, r9d; DaclDefaulted
0x1400a9d54  mov     r8, rdi; Dacl
0x1400a9d57  mov     dl, 1; DaclPresent
0x1400a9d59  mov     rcx, rsi; SecurityDescriptor
0x1400a9d5c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400a9d63  nop     dword ptr [rax+rax+00h]
0x1400a9d68  mov     ebx, eax
0x1400a9d6a  test    eax, eax
0x1400a9d6c  jns     short loc_1400A9D8C
0x1400a9d6e  mov     r9d, eax
0x1400a9d71  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a9d78  mov     r8d, 26Ah
0x1400a9d7e  lea     rcx, aVsmmmempartpcr; "VsmmMemPartpCreateSecurityDescriptor"
0x1400a9d85  call    VidTraceErrorStatusInternal0
0x1400a9d8a  jmp     short loc_1400A9D8E
0x1400a9d8c  xor     ebx, ebx
0x1400a9d8e  mov     eax, ebx
0x1400a9d90  mov     rcx, [rbp+57h+var_20]
0x1400a9d94  xor     rcx, rsp; StackCookie
0x1400a9d97  call    __security_check_cookie
0x1400a9d9c  lea     r11, [rsp+0C0h+var_10]
0x1400a9da4  mov     rbx, [r11+30h]
0x1400a9da8  mov     rsi, [r11+38h]
0x1400a9dac  mov     rsp, r11
0x1400a9daf  pop     r15
0x1400a9db1  pop     rdi
0x1400a9db2  pop     rbp
0x1400a9db3  retn
```
