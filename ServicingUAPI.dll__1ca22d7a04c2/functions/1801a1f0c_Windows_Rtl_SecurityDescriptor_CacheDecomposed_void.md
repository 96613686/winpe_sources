# Windows::Rtl::SecurityDescriptor::CacheDecomposed(void)

- ea: `0x1801a1f0c`
- end: `0x1801a20ed`
- name: `?CacheDecomposed@SecurityDescriptor@Rtl@Windows@@AEAAJXZ`
- size: `481`
- prototype: `__int64 __fastcall(Windows::Rtl::SecurityDescriptor *__hidden this)`
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801a2980`
- `0x1801a2abc`
- `0x1801a2b58`
- `0x1801a2d90`
- `0x1801a32e8`
- `0x1801a3884`

## callees

- `0x1800031d0`
- `0x1800497c0`
- `0x1801a1f0c`
- `0x1801a28c0`

## import_xrefs

- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1801a1ffd`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x1801a1ffd`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1801a2046`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1801a2046`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1801a1fc7`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x1801a1fc7`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1801a2095`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1801a2095`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1801a1f5b`
- `ntdll!RtlGetControlSecurityDescriptor` at `0x1801a1f5b`

## string_xrefs

- `0x1801a1f7c`: `onecore\base\wcp\rtllib\nativelib\security_descriptor.cpp`
- `0x1801a1f92`: `Windows::Rtl::SecurityDescriptor::CacheDecomposed`
- `0x1801a1fe1`: `::RtlGetOwnerSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Owner)), &Defaulted)`
- `0x1801a1f75`: `::RtlGetControlSecurityDescriptor(GetOpaque(), &m_Control, &Revision)`
- `0x1801a2060`: `::RtlGetDaclSecurityDescriptor(GetOpaque(), &Present, &Acl, &Defaulted)`
- `0x1801a2017`: `::RtlGetGroupSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Group)), &Defaulted)`
- `0x1801a20af`: `::RtlGetSaclSecurityDescriptor(GetOpaque(), &Present, &Acl, &Defaulted)`

## pseudocode

```c
__int64 __fastcall Windows::Rtl::SecurityDescriptor::CacheDecomposed(Windows::Rtl::SecurityDescriptor *this)
{
  struct _SECURITY_DESCRIPTOR *v2; // rax
  NTSTATUS ControlSecurityDescriptor; // ebx
  const char *v4; // rax
  struct _SECURITY_DESCRIPTOR *v6; // rax
  struct _SECURITY_DESCRIPTOR *v7; // rax
  struct _SECURITY_DESCRIPTOR *v8; // rax
  struct _SECURITY_DESCRIPTOR *v9; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+30h] [rbp-30h]
  const char *v12; // [rsp+38h] [rbp-28h]
  PACL Dacl; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int8 DaclPresent; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int8 OwnerDefaulted[3]; // [rsp+49h] [rbp-17h] BYREF
  ULONG Revision; // [rsp+4Ch] [rbp-14h] BYREF

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
    v11 = 1594;
    v4 = "::RtlGetControlSecurityDescriptor(GetOpaque(), &m_Control, &Revision)";
LABEL_3:
    v12 = v4;
    v10[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_descriptor.cpp";
    v10[1] = "Windows::Rtl::SecurityDescriptor::CacheDecomposed";
    RtlReportErrorOrigination(v10, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)ControlSecurityDescriptor);
    return (unsigned int)ControlSecurityDescriptor;
  }
  OwnerDefaulted[0] = 0;
  v6 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetOwnerSecurityDescriptor(v6, (PSID *)this + 4, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v11 = 1597;
    v4 = "::RtlGetOwnerSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Owner)), &Defaulted)";
    goto LABEL_3;
  }
  v7 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetGroupSecurityDescriptor(v7, (PSID *)this + 5, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v11 = 1598;
    v4 = "::RtlGetGroupSecurityDescriptor(GetOpaque(), reinterpret_cast<PSID*>(const_cast<SID**>(&m_Group)), &Defaulted)";
    goto LABEL_3;
  }
  Dacl = 0;
  DaclPresent = 0;
  v8 = (struct _SECURITY_DESCRIPTOR *)Windows::Rtl::SecurityDescriptor::Get(this);
  ControlSecurityDescriptor = RtlGetDaclSecurityDescriptor(v8, &DaclPresent, &Dacl, OwnerDefaulted);
  if ( ControlSecurityDescriptor < 0 )
  {
    v11 = 1602;
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
    v11 = 1609;
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
0x1801a1f0c  mov     [rsp-18h+arg_8], rbx
0x1801a1f11  mov     [rsp-18h+arg_10], rsi
0x1801a1f16  push    rbp
0x1801a1f17  push    rdi
0x1801a1f18  push    r14
0x1801a1f1a  mov     rbp, rsp
0x1801a1f1d  sub     rsp, 60h
0x1801a1f21  mov     rax, cs:__security_cookie
0x1801a1f28  xor     rax, rsp
0x1801a1f2b  mov     [rbp+var_10], rax
0x1801a1f2f  xor     eax, eax
0x1801a1f31  mov     rdi, rcx
0x1801a1f34  mov     [rcx+1Ah], ax
0x1801a1f38  mov     [rcx+20h], rax
0x1801a1f3c  mov     [rcx+28h], rax
0x1801a1f40  mov     [rcx+30h], rax
0x1801a1f44  mov     [rcx+38h], rax
0x1801a1f48  mov     [rbp+Revision], eax
0x1801a1f4b  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a1f50  lea     r8, [rbp+Revision]; Revision
0x1801a1f54  mov     rcx, rax; SecurityDescriptor
0x1801a1f57  lea     rdx, [rdi+1Ah]; Control
0x1801a1f5b  call    cs:__imp_RtlGetControlSecurityDescriptor
0x1801a1f62  nop     dword ptr [rax+rax+00h]
0x1801a1f67  mov     ebx, eax
0x1801a1f69  test    eax, eax
0x1801a1f6b  jns     short loc_1801A1FB0
0x1801a1f6d  mov     [rbp+var_30], 63Ah
0x1801a1f75  lea     rax, aRtlgetcontrols_1; "::RtlGetControlSecurityDescriptor(GetOp"...
0x1801a1f7c  lea     rcx, aOnecoreBaseWcp_12; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1801a1f83  mov     [rbp+var_28], rax
0x1801a1f87  mov     [rbp+var_40], rcx
0x1801a1f8b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1801a1f92  lea     rcx, aWindowsRtlSecu_3; "Windows::Rtl::SecurityDescriptor::Cache"...
0x1801a1f99  mov     r8d, ebx
0x1801a1f9c  mov     [rbp+var_38], rcx
0x1801a1fa0  lea     rcx, [rbp+var_40]
0x1801a1fa4  call    RtlReportErrorOrigination
0x1801a1fa9  mov     eax, ebx
0x1801a1fab  jmp     loc_1801A20CB
0x1801a1fb0  mov     rcx, rdi; this
0x1801a1fb3  mov     [rbp+OwnerDefaulted], 0
0x1801a1fb7  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a1fbc  lea     r8, [rbp+OwnerDefaulted]; OwnerDefaulted
0x1801a1fc0  mov     rcx, rax; SecurityDescriptor
0x1801a1fc3  lea     rdx, [rdi+20h]; Owner
0x1801a1fc7  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1801a1fce  nop     dword ptr [rax+rax+00h]
0x1801a1fd3  mov     ebx, eax
0x1801a1fd5  test    eax, eax
0x1801a1fd7  jns     short loc_1801A1FEA
0x1801a1fd9  mov     [rbp+var_30], 63Dh
0x1801a1fe1  lea     rax, aRtlgetownersec; "::RtlGetOwnerSecurityDescriptor(GetOpaq"...
0x1801a1fe8  jmp     short loc_1801A1F7C
0x1801a1fea  mov     rcx, rdi; this
0x1801a1fed  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a1ff2  lea     r8, [rbp+OwnerDefaulted]; GroupDefaulted
0x1801a1ff6  mov     rcx, rax; SecurityDescriptor
0x1801a1ff9  lea     rdx, [rdi+28h]; Group
0x1801a1ffd  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x1801a2004  nop     dword ptr [rax+rax+00h]
0x1801a2009  mov     ebx, eax
0x1801a200b  test    eax, eax
0x1801a200d  jns     short loc_1801A2023
0x1801a200f  mov     [rbp+var_30], 63Eh
0x1801a2017  lea     rax, aRtlgetgroupsec; "::RtlGetGroupSecurityDescriptor(GetOpaq"...
0x1801a201e  jmp     loc_1801A1F7C
0x1801a2023  mov     rcx, rdi; this
0x1801a2026  mov     [rbp+Dacl], 0
0x1801a202e  mov     [rbp+DaclPresent], 0
0x1801a2032  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a2037  lea     r9, [rbp+OwnerDefaulted]; DaclDefaulted
0x1801a203b  mov     rcx, rax; SecurityDescriptor
0x1801a203e  lea     r8, [rbp+Dacl]; Dacl
0x1801a2042  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x1801a2046  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1801a204d  nop     dword ptr [rax+rax+00h]
0x1801a2052  mov     ebx, eax
0x1801a2054  test    eax, eax
0x1801a2056  jns     short loc_1801A206C
0x1801a2058  mov     [rbp+var_30], 642h
0x1801a2060  lea     rax, aRtlgetdaclsecu_1; "::RtlGetDaclSecurityDescriptor(GetOpaqu"...
0x1801a2067  jmp     loc_1801A1F7C
0x1801a206c  cmp     [rbp+DaclPresent], 0
0x1801a2070  jz      short loc_1801A207A
0x1801a2072  mov     rax, [rbp+Dacl]
0x1801a2076  mov     [rdi+30h], rax
0x1801a207a  mov     rcx, rdi; this
0x1801a207d  mov     [rbp+DaclPresent], 0
0x1801a2081  call    ?Get@SecurityDescriptor@Rtl@Windows@@QEBAPEBU_SECURITY_DESCRIPTOR@@XZ; Windows::Rtl::SecurityDescriptor::Get(void)
0x1801a2086  lea     r9, [rbp+OwnerDefaulted]; SaclDefaulted
0x1801a208a  mov     rcx, rax; SecurityDescriptor
0x1801a208d  lea     r8, [rbp+Dacl]; Sacl
0x1801a2091  lea     rdx, [rbp+DaclPresent]; SaclPresent
0x1801a2095  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1801a209c  nop     dword ptr [rax+rax+00h]
0x1801a20a1  mov     ebx, eax
0x1801a20a3  test    eax, eax
0x1801a20a5  jns     short loc_1801A20BB
0x1801a20a7  mov     [rbp+var_30], 649h
0x1801a20af  lea     rax, aRtlgetsaclsecu_0; "::RtlGetSaclSecurityDescriptor(GetOpaqu"...
0x1801a20b6  jmp     loc_1801A1F7C
0x1801a20bb  cmp     [rbp+DaclPresent], 0
0x1801a20bf  jz      short loc_1801A20C9
0x1801a20c1  mov     rax, [rbp+Dacl]
0x1801a20c5  mov     [rdi+38h], rax
0x1801a20c9  xor     eax, eax
0x1801a20cb  mov     rcx, [rbp+var_10]
0x1801a20cf  xor     rcx, rsp; StackCookie
0x1801a20d2  call    __security_check_cookie
0x1801a20d7  lea     r11, [rsp+60h+var_s0]
0x1801a20dc  mov     rbx, [r11+28h]
0x1801a20e0  mov     rsi, [r11+30h]
0x1801a20e4  mov     rsp, r11
0x1801a20e7  pop     r14
0x1801a20e9  pop     rdi
0x1801a20ea  pop     rbp
0x1801a20eb  retn
```
