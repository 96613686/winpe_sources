# CreateMbbSecurityDescriptor(void *)

- ea: `0x14001d774`
- end: `0x14001db3b`
- name: `?CreateMbbSecurityDescriptor@@YAJPEAX@Z`
- size: `967`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14006703c`

## callees

- `0x140001db8`
- `0x14001d774`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!RtlCreateAcl` at `0x14001d9a4`
- `ntoskrnl!RtlCreateAcl` at `0x14001d9a4`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001da70`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14001da70`
- `ntoskrnl!SeExports` at `0x14001d909`
- `ntoskrnl!SeExports` at `0x14001da17`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001d9e6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001da36`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001d9e6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14001da36`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14001d7a6`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14001d7a6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001daa9`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001daa9`
- `ntoskrnl!RtlLengthSid` at `0x14001d8fd`
- `ntoskrnl!RtlLengthSid` at `0x14001d91c`
- `ntoskrnl!RtlLengthSid` at `0x14001d8fd`
- `ntoskrnl!RtlLengthSid` at `0x14001d91c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d866`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d880`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d89a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d8b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d8ce`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d8e8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d866`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d880`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d89a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d8b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d8ce`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14001d8e8`
- `ntoskrnl!RtlInitializeSid` at `0x14001d82c`
- `ntoskrnl!RtlInitializeSid` at `0x14001d82c`
- `ntoskrnl!ExAllocatePool2` at `0x14001d7c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001d937`
- `ntoskrnl!ExAllocatePool2` at `0x14001d7c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001d937`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dafe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dafe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001db0f`

## pseudocode

```c
__int64 __fastcall CreateMbbSecurityDescriptor(void *a1)
{
  ULONG v1; // eax
  void *Pool2; // rax
  int v3; // edx
  void *v4; // rdi
  NTSTATUS Acl; // ebx
  int v6; // edx
  int v7; // r9d
  ULONG v8; // ebx
  ULONG v9; // ebx
  struct _ACL *v10; // rax
  struct _ACL *v11; // rsi
  int v12; // edx
  int v13; // r9d
  char v15; // [rsp+28h] [rbp-20h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+30h] [rbp-18h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v1 = RtlLengthRequiredSid(6u);
  Pool2 = (void *)ExAllocatePool2(256, v1, 1683505741);
  v4 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlInitializeSid(Pool2, &IdentifierAuthority, 6u);
    if ( Acl < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = 119;
        v15 = Acl;
LABEL_10:
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          11,
          v7,
          (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
          v15);
        goto LABEL_28;
      }
      goto LABEL_28;
    }
    *RtlSubAuthoritySid(v4, 0) = 80;
    *RtlSubAuthoritySid(v4, 1u) = -313110759;
    *RtlSubAuthoritySid(v4, 2u) = 581775623;
    *RtlSubAuthoritySid(v4, 3u) = 1136376035;
    *RtlSubAuthoritySid(v4, 4u) = 2066872258;
    *RtlSubAuthoritySid(v4, 5u) = 409572886;
    v8 = RtlLengthSid(v4);
    v9 = RtlLengthSid(SeExports->SeAliasAdminsSid) + 24 + v8;
    v10 = (struct _ACL *)ExAllocatePool2(256, v9, 1683505741);
    v11 = v10;
    if ( !v10 )
    {
      Acl = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v7 = 120;
        v15 = -102;
        goto LABEL_10;
      }
LABEL_28:
      ExFreePoolWithTag(v4, 0);
      return (unsigned int)Acl;
    }
    Acl = RtlCreateAcl(v10, v9, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, v4);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAce(v11, 2u, 0x1F01FFu, SeExports->SeAliasAdminsSid);
        if ( Acl >= 0 )
        {
          Acl = RtlCreateSecurityDescriptor(&WPP_MAIN_CB.Dpc.DeferredRoutine, 1u);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(&WPP_MAIN_CB.Dpc.DeferredRoutine, 1u, v11, 0);
            if ( Acl >= 0 )
              goto LABEL_28;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v13 = 125;
              goto LABEL_26;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v13 = 124;
            goto LABEL_26;
          }
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v13 = 123;
          goto LABEL_26;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v13 = 122;
        goto LABEL_26;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 121;
LABEL_26:
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        11,
        v13,
        (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
        Acl);
    }
    ExFreePoolWithTag(v11, 0);
    goto LABEL_28;
  }
  Acl = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      11,
      118,
      (__int64)WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids,
      154);
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14001d774  mov     [rsp+arg_0], rbx
0x14001d779  mov     [rsp+arg_8], rsi
0x14001d77e  push    rdi
0x14001d77f  sub     rsp, 40h
0x14001d783  mov     rax, cs:__security_cookie
0x14001d78a  xor     rax, rsp
0x14001d78d  mov     [rsp+48h+var_10], rax
0x14001d792  mov     ecx, 6; SubAuthorityCount
0x14001d797  mov     dword ptr [rsp+48h+IdentifierAuthority.Value], 0
0x14001d79f  mov     word ptr [rsp+48h+IdentifierAuthority.Value+4], 500h
0x14001d7a6  call    cs:__imp_RtlLengthRequiredSid
0x14001d7ad  nop     dword ptr [rax+rax+00h]
0x14001d7b2  mov     esi, 6458424Dh
0x14001d7b7  mov     edx, eax
0x14001d7b9  mov     r8d, esi
0x14001d7bc  mov     ecx, 100h
0x14001d7c1  call    cs:__imp_ExAllocatePool2
0x14001d7c8  nop     dword ptr [rax+rax+00h]
0x14001d7cd  mov     rdi, rax
0x14001d7d0  test    rax, rax
0x14001d7d3  jnz     short loc_14001D821
0x14001d7d5  mov     ebx, 0C000009Ah
0x14001d7da  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d7e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d7e8  jz      loc_14001DB1B
0x14001d7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d7f5  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001d7fc  lea     r9d, [rdi+76h]
0x14001d800  mov     dword ptr [rsp+48h+var_20], 0C000009Ah
0x14001d808  lea     r8d, [rdi+0Bh]
0x14001d80c  mov     [rsp+48h+var_28], rax
0x14001d811  mov     dl, 2
0x14001d813  mov     rcx, [rcx+40h]
0x14001d817  call    WPP_RECORDER_SF_d
0x14001d81c  jmp     loc_14001DB1B
0x14001d821  mov     r8b, 6; SubAuthorityCount
0x14001d824  lea     rdx, [rsp+48h+IdentifierAuthority]; IdentifierAuthority
0x14001d829  mov     rcx, rdi; Sid
0x14001d82c  call    cs:__imp_RtlInitializeSid
0x14001d833  nop     dword ptr [rax+rax+00h]
0x14001d838  mov     ebx, eax
0x14001d83a  test    eax, eax
0x14001d83c  jns     short loc_14001D861
0x14001d83e  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d845  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d84c  jz      loc_14001DB0A
0x14001d852  mov     r9d, 77h ; 'w'
0x14001d858  mov     dword ptr [rsp+48h+var_20], ebx
0x14001d85c  jmp     loc_14001D970
0x14001d861  xor     edx, edx; SubAuthority
0x14001d863  mov     rcx, rdi; Sid
0x14001d866  call    cs:__imp_RtlSubAuthoritySid
0x14001d86d  nop     dword ptr [rax+rax+00h]
0x14001d872  mov     edx, 1; SubAuthority
0x14001d877  mov     rcx, rdi; Sid
0x14001d87a  mov     dword ptr [rax], 50h ; 'P'
0x14001d880  call    cs:__imp_RtlSubAuthoritySid
0x14001d887  nop     dword ptr [rax+rax+00h]
0x14001d88c  mov     edx, 2; SubAuthority
0x14001d891  mov     rcx, rdi; Sid
0x14001d894  mov     dword ptr [rax], 0ED564F19h
0x14001d89a  call    cs:__imp_RtlSubAuthoritySid
0x14001d8a1  nop     dword ptr [rax+rax+00h]
0x14001d8a6  mov     edx, 3; SubAuthority
0x14001d8ab  mov     rcx, rdi; Sid
0x14001d8ae  mov     dword ptr [rax], 22AD3107h
0x14001d8b4  call    cs:__imp_RtlSubAuthoritySid
0x14001d8bb  nop     dword ptr [rax+rax+00h]
0x14001d8c0  mov     edx, 4; SubAuthority
0x14001d8c5  mov     rcx, rdi; Sid
0x14001d8c8  mov     dword ptr [rax], 43BBB8E3h
0x14001d8ce  call    cs:__imp_RtlSubAuthoritySid
0x14001d8d5  nop     dword ptr [rax+rax+00h]
0x14001d8da  mov     edx, 5; SubAuthority
0x14001d8df  mov     rcx, rdi; Sid
0x14001d8e2  mov     dword ptr [rax], 7B31F7C2h
0x14001d8e8  call    cs:__imp_RtlSubAuthoritySid
0x14001d8ef  nop     dword ptr [rax+rax+00h]
0x14001d8f4  mov     rcx, rdi; Sid
0x14001d8f7  mov     dword ptr [rax], 18699616h
0x14001d8fd  call    cs:__imp_RtlLengthSid
0x14001d904  nop     dword ptr [rax+rax+00h]
0x14001d909  mov     rdx, cs:__imp_SeExports
0x14001d910  mov     ebx, eax
0x14001d912  mov     rcx, [rdx]
0x14001d915  mov     rcx, [rcx+110h]; Sid
0x14001d91c  call    cs:__imp_RtlLengthSid
0x14001d923  nop     dword ptr [rax+rax+00h]
0x14001d928  mov     r8d, esi
0x14001d92b  mov     ecx, 100h
0x14001d930  add     eax, 18h
0x14001d933  add     ebx, eax
0x14001d935  mov     edx, ebx
0x14001d937  call    cs:__imp_ExAllocatePool2
0x14001d93e  nop     dword ptr [rax+rax+00h]
0x14001d943  mov     rsi, rax
0x14001d946  test    rax, rax
0x14001d949  jnz     short loc_14001D999
0x14001d94b  mov     ebx, 0C000009Ah
0x14001d950  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d957  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d95e  jz      loc_14001DB0A
0x14001d964  lea     r9d, [rsi+78h]
0x14001d968  mov     dword ptr [rsp+48h+var_20], 0C000009Ah
0x14001d970  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d977  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001d97e  mov     r8d, 0Bh
0x14001d984  mov     [rsp+48h+var_28], rax
0x14001d989  mov     dl, 2
0x14001d98b  mov     rcx, [rcx+40h]
0x14001d98f  call    WPP_RECORDER_SF_d
0x14001d994  jmp     loc_14001DB0A
0x14001d999  mov     r8d, 2; AclRevision
0x14001d99f  mov     edx, ebx; AclLength
0x14001d9a1  mov     rcx, rsi; Acl
0x14001d9a4  call    cs:__imp_RtlCreateAcl
0x14001d9ab  nop     dword ptr [rax+rax+00h]
0x14001d9b0  mov     ebx, eax
0x14001d9b2  test    eax, eax
0x14001d9b4  jns     short loc_14001D9D5
0x14001d9b6  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d9bd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001d9c4  jz      loc_14001DAF9
0x14001d9ca  mov     r9d, 79h ; 'y'
0x14001d9d0  jmp     loc_14001DAD1
0x14001d9d5  mov     r9, rdi; Sid
0x14001d9d8  mov     edx, 2; AceRevision
0x14001d9dd  mov     r8d, 1F01FFh; AccessMask
0x14001d9e3  mov     rcx, rsi; Acl
0x14001d9e6  call    cs:__imp_RtlAddAccessAllowedAce
0x14001d9ed  nop     dword ptr [rax+rax+00h]
0x14001d9f2  mov     ebx, eax
0x14001d9f4  test    eax, eax
0x14001d9f6  jns     short loc_14001DA17
0x14001d9f8  lea     rax, WPP_RECORDER_INITIALIZED
0x14001d9ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001da06  jz      loc_14001DAF9
0x14001da0c  mov     r9d, 7Ah ; 'z'
0x14001da12  jmp     loc_14001DAD1
0x14001da17  mov     rax, cs:__imp_SeExports
0x14001da1e  mov     edx, 2; AceRevision
0x14001da23  mov     r8d, 1F01FFh; AccessMask
0x14001da29  mov     rcx, rsi; Acl
0x14001da2c  mov     r9, [rax]
0x14001da2f  mov     r9, [r9+110h]; Sid
0x14001da36  call    cs:__imp_RtlAddAccessAllowedAce
0x14001da3d  nop     dword ptr [rax+rax+00h]
0x14001da42  mov     ebx, eax
0x14001da44  test    eax, eax
0x14001da46  jns     short loc_14001DA64
0x14001da48  lea     rax, WPP_RECORDER_INITIALIZED
0x14001da4f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001da56  jz      loc_14001DAF9
0x14001da5c  mov     r9d, 7Bh ; '{'
0x14001da62  jmp     short loc_14001DAD1
0x14001da64  mov     edx, 1; Revision
0x14001da69  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SecurityDescriptor
0x14001da70  call    cs:__imp_RtlCreateSecurityDescriptor
0x14001da77  nop     dword ptr [rax+rax+00h]
0x14001da7c  mov     ebx, eax
0x14001da7e  test    eax, eax
0x14001da80  jns     short loc_14001DA9A
0x14001da82  lea     rax, WPP_RECORDER_INITIALIZED
0x14001da89  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001da90  jz      short loc_14001DAF9
0x14001da92  mov     r9d, 7Ch ; '|'
0x14001da98  jmp     short loc_14001DAD1
0x14001da9a  xor     r9d, r9d; DaclDefaulted
0x14001da9d  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SecurityDescriptor
0x14001daa4  mov     r8, rsi; Dacl
0x14001daa7  mov     dl, 1; DaclPresent
0x14001daa9  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14001dab0  nop     dword ptr [rax+rax+00h]
0x14001dab5  mov     ebx, eax
0x14001dab7  test    eax, eax
0x14001dab9  jns     short loc_14001DB0A
0x14001dabb  lea     rax, WPP_RECORDER_INITIALIZED
0x14001dac2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001dac9  jz      short loc_14001DAF9
0x14001dacb  mov     r9d, 7Dh ; '}'
0x14001dad1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dad8  lea     rax, WPP_dce8bfe23d3239629ed9d053a5b71e5e_Traceguids
0x14001dadf  mov     dword ptr [rsp+48h+var_20], ebx
0x14001dae3  mov     r8d, 0Bh
0x14001dae9  mov     dl, 2
0x14001daeb  mov     [rsp+48h+var_28], rax
0x14001daf0  mov     rcx, [rcx+40h]
0x14001daf4  call    WPP_RECORDER_SF_d
0x14001daf9  xor     edx, edx; Tag
0x14001dafb  mov     rcx, rsi; P
0x14001dafe  call    cs:__imp_ExFreePoolWithTag
0x14001db05  nop     dword ptr [rax+rax+00h]
0x14001db0a  xor     edx, edx; Tag
0x14001db0c  mov     rcx, rdi; P
0x14001db0f  call    cs:__imp_ExFreePoolWithTag
0x14001db16  nop     dword ptr [rax+rax+00h]
0x14001db1b  mov     eax, ebx
0x14001db1d  mov     rcx, [rsp+48h+var_10]
0x14001db22  xor     rcx, rsp; StackCookie
0x14001db25  call    __security_check_cookie
0x14001db2a  mov     rbx, [rsp+48h+arg_0]
0x14001db2f  mov     rsi, [rsp+48h+arg_8]
0x14001db34  add     rsp, 40h
0x14001db38  pop     rdi
0x14001db39  retn
```
