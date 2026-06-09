# Windows::Rtl::SecurityDescriptor::CacheDecomposed(void)

- ea: `0x18027e34c`
- end: `0x18027e56c`
- name: `?CacheDecomposed@SecurityDescriptor@Rtl@Windows@@AEAAJXZ`
- size: `544`
- prototype: `__int64 __fastcall(Windows::Rtl::SecurityDescriptor *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18027eecc`
- `0x18027effc`
- `0x18027f0d4`
- `0x18027f254`
- `0x18027f778`
- `0x18027fc04`

## callees

- `0x1800aa1a4`
- `0x1800eb920`
- `0x18027e34c`
- `0x18027ed9c`

## import_xrefs

- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18027e4a5`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18027e4a5`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18027e44c`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x18027e44c`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18027e402`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18027e402`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18027e508`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x18027e508`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18027e39d`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x18027e39d`

## string_xrefs

- `0x18027e3ad`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x18027e412`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x18027e45c`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x18027e4b5`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x18027e518`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x18027e430`: `::RtlGetOwnerSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Owner)), &Defaulted)`
- `0x18027e47a`: `::RtlGetGroupSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Group)), &Defaulted)`
- `0x18027e4d3`: `::RtlGetDaclSecurityDescriptor(GetOpaque(), &Present, &Acl, &Defaulted)`
- `0x18027e536`: `::RtlGetSaclSecurityDescriptor(GetOpaque(), &Present, &Acl, &Defaulted)`
- `0x18027e3c0`: `Windows::Rtl::SecurityDescriptor::CacheDecomposed`
- `0x18027e425`: `Windows::Rtl::SecurityDescriptor::CacheDecomposed`
- `0x18027e46f`: `Windows::Rtl::SecurityDescriptor::CacheDecomposed`
- `0x18027e4c8`: `Windows::Rtl::SecurityDescriptor::CacheDecomposed`
- `0x18027e52b`: `Windows::Rtl::SecurityDescriptor::CacheDecomposed`
- `0x18027e3cb`: `::RtlGetControlSecurityDescriptor(GetOpaque(), &m_Control, &Revision)`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SecurityDescriptor::CacheDecomposed(Windows::Rtl::SecurityDescriptor *this)
{
  struct _SECURITY_DESCRIPTOR *v2; // rax
  NTSTATUS ControlSecurityDescriptor; // eax
  const char *v4; // rcx
  struct _SECURITY_DESCRIPTOR *v6; // rax
  struct _SECURITY_DESCRIPTOR *v7; // rax
  struct _SECURITY_DESCRIPTOR *v8; // rax
  struct _SECURITY_DESCRIPTOR *v9; // rax
  const char *v10; // [rsp+20h] [rbp-48h] BYREF
  const char *v11; // [rsp+28h] [rbp-40h]
  __int64 v12; // [rsp+30h] [rbp-38h]
  const char *v13; // [rsp+38h] [rbp-30h]
  PACL Dacl; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int8 DaclPresent; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int8 OwnerDefaulted[3]; // [rsp+49h] [rbp-1Fh] BYREF
  int v17; // [rsp+4Ch] [rbp-1Ch] BYREF
  ULONG Revision; // [rsp+50h] [rbp-18h] BYREF

  v17 = 0;
  *((_WORD *)this + 13) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  Revision = 0;
  v2 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(v2, (PSECURITY_DESCRIPTOR_CONTROL)this + 13, &Revision);
  if ( ControlSecurityDescriptor < 0 )
  {
    v12 = 1594;
    v10 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v11 = "Windows::Rtl::SecurityDescriptor::CacheDecomposed";
    v4 = "::RtlGetControlSecurityDescriptor(GetOpaque(), &m_Control, &Revision)";
LABEL_3:
    v13 = v4;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v17,
             &v10,
             (unsigned int)ControlSecurityDescriptor);
  }
  OwnerDefaulted[0] = 0;
  v6 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetOwnerSecurityDescriptor(v6, (PSID *)this + 4, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v12 = 1597;
    v10 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v11 = "Windows::Rtl::SecurityDescriptor::CacheDecomposed";
    v4 = "::RtlGetOwnerSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Owner)), &Defaulted)";
    goto LABEL_3;
  }
  v7 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetGroupSecurityDescriptor(v7, (PSID *)this + 5, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v12 = 1598;
    v10 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v11 = "Windows::Rtl::SecurityDescriptor::CacheDecomposed";
    v4 = "::RtlGetGroupSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Group)), &Defaulted)";
    goto LABEL_3;
  }
  Dacl = 0;
  DaclPresent = 0;
  v8 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetDaclSecurityDescriptor(v8, &DaclPresent, &Dacl, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v12 = 1602;
    v10 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v11 = "Windows::Rtl::SecurityDescriptor::CacheDecomposed";
    v4 = "::RtlGetDaclSecurityDescriptor(GetOpaque(), &Present, &Acl, &Defaulted)";
    goto LABEL_3;
  }
  if ( DaclPresent )
    *((_QWORD *)this + 6) = Dacl;
  DaclPresent = 0;
  v9 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetSaclSecurityDescriptor(v9, &DaclPresent, &Dacl, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v12 = 1609;
    v10 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v11 = "Windows::Rtl::SecurityDescriptor::CacheDecomposed";
    v4 = "::RtlGetSaclSecurityDescriptor(GetOpaque(), &Present, &Acl, &Defaulted)";
    goto LABEL_3;
  }
  if ( DaclPresent )
    *((_QWORD *)this + 7) = Dacl;
  return 0;
}

```

## disassembly

```asm
0x18027e34c  push    rbp
0x18027e34e  push    rbx
0x18027e34f  push    rsi
0x18027e350  push    rdi
0x18027e351  push    r14
0x18027e353  push    r15
0x18027e355  mov     rbp, rsp
0x18027e358  sub     rsp, 68h
0x18027e35c  mov     rax, cs:__security_cookie
0x18027e363  xor     rax, rsp
0x18027e366  mov     [rbp+var_10], rax
0x18027e36a  xor     r15d, r15d
0x18027e36d  mov     rdi, rcx
0x18027e370  mov     [rbp+var_1C], r15d
0x18027e374  mov     [rcx+1Ah], r15w
0x18027e379  mov     [rcx+20h], r15
0x18027e37d  mov     [rcx+28h], r15
0x18027e381  mov     [rcx+30h], r15
0x18027e385  mov     [rcx+38h], r15
0x18027e389  mov     [rbp+Revision], r15d
0x18027e38d  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18027e392  lea     r8, [rbp+Revision]; Revision
0x18027e396  mov     rcx, rax; SecurityDescriptor
0x18027e399  lea     rdx, [rdi+1Ah]; Control
0x18027e39d  call    cs:__imp_RtlGetControlSecurityDescriptor
0x18027e3a4  nop     dword ptr [rax+rax+00h]
0x18027e3a9  test    eax, eax
0x18027e3ab  jns     short loc_18027E3EB
0x18027e3ad  lea     rcx, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18027e3b4  mov     [rbp+var_38], 63Ah
0x18027e3bc  mov     [rbp+var_48], rcx
0x18027e3c0  lea     rcx, aWindowsRtlSecu_3; "Windows::Rtl::SecurityDescriptor::Cache"...
0x18027e3c7  mov     [rbp+var_40], rcx
0x18027e3cb  lea     rcx, aRtlgetcontrols_2; "::RtlGetControlSecurityDescriptor(GetOp"...
0x18027e3d2  mov     [rbp+var_30], rcx
0x18027e3d6  lea     rdx, [rbp+var_48]
0x18027e3da  lea     rcx, [rbp+var_1C]
0x18027e3de  mov     r8d, eax
0x18027e3e1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18027e3e6  jmp     loc_18027E552
0x18027e3eb  mov     rcx, rdi; this
0x18027e3ee  mov     [rbp+OwnerDefaulted], r15b
0x18027e3f2  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18027e3f7  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x18027e3fb  mov     rcx, rax; SecurityDescriptor
0x18027e3fe  lea     rdx, [rdi+20h]; Owner
0x18027e402  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18027e409  nop     dword ptr [rax+rax+00h]
0x18027e40e  test    eax, eax
0x18027e410  jns     short loc_18027E439
0x18027e412  lea     rcx, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18027e419  mov     [rbp+var_38], 63Dh
0x18027e421  mov     [rbp+var_48], rcx
0x18027e425  lea     rcx, aWindowsRtlSecu_3; "Windows::Rtl::SecurityDescriptor::Cache"...
0x18027e42c  mov     [rbp+var_40], rcx
0x18027e430  lea     rcx, aRtlgetownersec; "::RtlGetOwnerSecurityDescriptor(GetOpaq"...
0x18027e437  jmp     short loc_18027E3D2
0x18027e439  mov     rcx, rdi; this
0x18027e43c  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18027e441  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x18027e445  mov     rcx, rax; SecurityDescriptor
0x18027e448  lea     rdx, [rdi+28h]; Group
0x18027e44c  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x18027e453  nop     dword ptr [rax+rax+00h]
0x18027e458  test    eax, eax
0x18027e45a  jns     short loc_18027E486
0x18027e45c  lea     rcx, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18027e463  mov     [rbp+var_38], 63Eh
0x18027e46b  mov     [rbp+var_48], rcx
0x18027e46f  lea     rcx, aWindowsRtlSecu_3; "Windows::Rtl::SecurityDescriptor::Cache"...
0x18027e476  mov     [rbp+var_40], rcx
0x18027e47a  lea     rcx, aRtlgetgroupsec; "::RtlGetGroupSecurityDescriptor(GetOpaq"...
0x18027e481  jmp     loc_18027E3D2
0x18027e486  mov     rcx, rdi; this
0x18027e489  mov     [rbp+Dacl], r15
0x18027e48d  mov     [rbp+DaclPresent], r15b
0x18027e491  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18027e496  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x18027e49a  mov     rcx, rax; SecurityDescriptor
0x18027e49d  lea     r8, [rbp+Dacl]; Dacl
0x18027e4a1  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x18027e4a5  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18027e4ac  nop     dword ptr [rax+rax+00h]
0x18027e4b1  test    eax, eax
0x18027e4b3  jns     short loc_18027E4DF
0x18027e4b5  lea     rcx, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18027e4bc  mov     [rbp+var_38], 642h
0x18027e4c4  mov     [rbp+var_48], rcx
0x18027e4c8  lea     rcx, aWindowsRtlSecu_3; "Windows::Rtl::SecurityDescriptor::Cache"...
0x18027e4cf  mov     [rbp+var_40], rcx
0x18027e4d3  lea     rcx, aRtlgetdaclsecu_2; "::RtlGetDaclSecurityDescriptor(GetOpaqu"...
0x18027e4da  jmp     loc_18027E3D2
0x18027e4df  cmp     [rbp+DaclPresent], r15b
0x18027e4e3  jz      short loc_18027E4ED
0x18027e4e5  mov     rax, [rbp+Dacl]
0x18027e4e9  mov     [rdi+30h], rax
0x18027e4ed  mov     rcx, rdi; this
0x18027e4f0  mov     [rbp+DaclPresent], r15b
0x18027e4f4  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x18027e4f9  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x18027e4fd  mov     rcx, rax; SecurityDescriptor
0x18027e500  lea     r8, [rbp+Dacl]; Sacl
0x18027e504  lea     rdx, [rbp+DaclPresent]; SaclPresent
0x18027e508  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x18027e50f  nop     dword ptr [rax+rax+00h]
0x18027e514  test    eax, eax
0x18027e516  jns     short loc_18027E542
0x18027e518  lea     rcx, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18027e51f  mov     [rbp+var_38], 649h
0x18027e527  mov     [rbp+var_48], rcx
0x18027e52b  lea     rcx, aWindowsRtlSecu_3; "Windows::Rtl::SecurityDescriptor::Cache"...
0x18027e532  mov     [rbp+var_40], rcx
0x18027e536  lea     rcx, aRtlgetsaclsecu_1; "::RtlGetSaclSecurityDescriptor(GetOpaqu"...
0x18027e53d  jmp     loc_18027E3D2
0x18027e542  cmp     [rbp+DaclPresent], r15b
0x18027e546  jz      short loc_18027E550
0x18027e548  mov     rax, [rbp+Dacl]
0x18027e54c  mov     [rdi+38h], rax
0x18027e550  xor     eax, eax
0x18027e552  mov     rcx, [rbp+var_10]
0x18027e556  xor     rcx, rsp; StackCookie
0x18027e559  call    __security_check_cookie
0x18027e55e  add     rsp, 68h
0x18027e562  pop     r15
0x18027e564  pop     r14
0x18027e566  pop     rdi
0x18027e567  pop     rsi
0x18027e568  pop     rbx
0x18027e569  pop     rbp
0x18027e56a  retn
```
