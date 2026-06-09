# PrinterSharingUtility::UpdatePrinterShare(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)

- ea: `0x1800352c8`
- end: `0x180035424`
- name: `?UpdatePrinterShare@PrinterSharingUtility@@SAXAEBUhstring@winrt@@0000@Z`
- size: `348`
- prototype: `void __fastcall(const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000f2d0`

## callees

- `0x180003a0c`
- `0x18000fa2c`
- `0x18001d0e4`
- `0x18002b28c`
- `0x180030a38`
- `0x1800352c8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035353`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035353`
- `srvcli!NetShareSetInfo` at `0x1800353da`
- `srvcli!NetShareSetInfo` at `0x1800353da`

## string_xrefs

- `0x180035362`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed!`
- `0x180035372`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`
- `0x1800353fb`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PrinterSharingUtility::UpdatePrinterShare(
        const struct winrt::hstring *a1,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        const struct winrt::hstring *a4,
        const struct winrt::hstring *a5)
{
  WCHAR *v5; // rsi
  const unsigned __int16 *v6; // r14
  const unsigned __int16 *v7; // rdi
  WCHAR *v8; // rbx
  const WCHAR *v9; // rax
  BOOL v10; // eax
  DWORD v11; // eax
  char *v12; // [rsp+28h] [rbp-58h]
  char *v13; // [rsp+28h] [rbp-58h]
  BYTE buf[8]; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+38h] [rbp-48h]
  const unsigned __int16 *v16; // [rsp+40h] [rbp-40h]
  int v17; // [rsp+4Ch] [rbp-34h]
  int v18; // [rsp+50h] [rbp-30h]
  const unsigned __int16 *v19; // [rsp+58h] [rbp-28h]
  WCHAR *v20; // [rsp+68h] [rbp-18h]
  PSECURITY_DESCRIPTOR v21; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  ULONG SecurityDescriptorSize; // [rsp+B0h] [rbp+30h] BYREF
  DWORD parm_err; // [rsp+B8h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C0h] [rbp+40h] BYREF

  if ( *(_QWORD *)a1 )
    v5 = (WCHAR *)winrt::hstring::c_str(a1);
  else
    v5 = 0;
  if ( *(_QWORD *)a2 )
    v6 = winrt::hstring::c_str(a2);
  else
    v6 = 0;
  if ( *(_QWORD *)a3 )
    v7 = winrt::hstring::c_str(a3);
  else
    v7 = 0;
  if ( *(_QWORD *)a4 )
    v8 = (WCHAR *)winrt::hstring::c_str(a4);
  else
    v8 = 0;
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  v9 = winrt::hstring::c_str(a5);
  v10 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &SecurityDescriptor, &SecurityDescriptorSize);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x4C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
    (const char *)!v10,
    (bool)"ConvertStringSecurityDescriptorToSecurityDescriptor failed!",
    v12);
  memset_0(buf, 0, 0x50u);
  v15 = 1;
  v17 = -1;
  v18 = -1;
  *(_QWORD *)buf = v5;
  v19 = v6;
  v16 = v7;
  v20 = v8;
  v21 = SecurityDescriptor;
  parm_err = 0;
  v11 = NetShareSetInfo(v8, v5, 0x1F7u, buf, &parm_err);
  LODWORD(v13) = 0;
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x5A,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
    (const char *)v11,
    (unsigned int)"Failed to set information on the printer share!, Parameter error %d",
    v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
}

```

## disassembly

```asm
0x1800352c8  push    rbp
0x1800352ca  push    rbx
0x1800352cb  push    rsi
0x1800352cc  push    rdi
0x1800352cd  push    r14
0x1800352cf  mov     rbp, rsp
0x1800352d2  sub     rsp, 80h
0x1800352d9  cmp     qword ptr [rcx], 0
0x1800352dd  jnz     short loc_1800352E3
0x1800352df  xor     esi, esi
0x1800352e1  jmp     short loc_1800352EB
0x1800352e3  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800352e8  mov     rsi, rax
0x1800352eb  cmp     qword ptr [rdx], 0
0x1800352ef  jnz     short loc_1800352F6
0x1800352f1  xor     r14d, r14d
0x1800352f4  jmp     short loc_180035301
0x1800352f6  mov     rcx, rdx; this
0x1800352f9  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800352fe  mov     r14, rax
0x180035301  cmp     qword ptr [r8], 0
0x180035305  jnz     short loc_18003530B
0x180035307  xor     edi, edi
0x180035309  jmp     short loc_180035316
0x18003530b  mov     rcx, r8; this
0x18003530e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180035313  mov     rdi, rax
0x180035316  cmp     qword ptr [r9], 0
0x18003531a  jnz     short loc_180035320
0x18003531c  xor     ebx, ebx
0x18003531e  jmp     short loc_18003532B
0x180035320  mov     rcx, r9; this
0x180035323  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180035328  mov     rbx, rax
0x18003532b  mov     [rbp+SecurityDescriptorSize], 0
0x180035332  mov     [rbp+SecurityDescriptor], 0
0x18003533a  mov     rcx, [rbp+arg_20]; this
0x18003533e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180035343  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180035347  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18003534b  mov     edx, 1; StringSDRevision
0x180035350  mov     rcx, rax; StringSecurityDescriptor
0x180035353  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180035359  test    eax, eax
0x18003535b  setz    al
0x18003535e  mov     rcx, [rbp+28h]; this
0x180035362  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180035369  mov     [rsp+80h+parm_err], rdx; bool
0x18003536e  movzx   r9d, al; char *
0x180035372  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x180035379  mov     edx, 4Ch ; 'L'; void *
0x18003537e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180035383  xor     edx, edx; Val
0x180035385  lea     r8d, [rdx+50h]; Size
0x180035389  lea     rcx, [rbp+buf]; void *
0x18003538d  call    memset_0
0x180035392  mov     [rbp+var_48], 1
0x180035399  or      eax, 0FFFFFFFFh
0x18003539c  mov     [rbp+var_34], eax
0x18003539f  mov     [rbp+var_30], eax
0x1800353a2  mov     qword ptr [rbp+buf], rsi
0x1800353a6  mov     [rbp+var_28], r14
0x1800353aa  mov     [rbp+var_40], rdi
0x1800353ae  mov     [rbp+var_18], rbx
0x1800353b2  mov     rax, [rbp+SecurityDescriptor]
0x1800353b6  mov     [rbp+var_8], rax
0x1800353ba  mov     [rbp+arg_8], 0
0x1800353c1  lea     rax, [rbp+arg_8]
0x1800353c5  mov     [rsp+80h+parm_err], rax; parm_err
0x1800353ca  lea     r9, [rbp+buf]; buf
0x1800353ce  mov     r8d, 1F7h; level
0x1800353d4  mov     rdx, rsi; netname
0x1800353d7  mov     rcx, rbx; servername
0x1800353da  call    cs:__imp_NetShareSetInfo
0x1800353e0  mov     rcx, [rbp+28h]; this
0x1800353e4  mov     dword ptr [rsp+80h+var_58], 0; char *
0x1800353ec  lea     rdx, aFailedToSetInf; "Failed to set information on the printe"...
0x1800353f3  mov     [rsp+80h+parm_err], rdx; unsigned int
0x1800353f8  mov     r9d, eax; char *
0x1800353fb  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x180035402  mov     edx, 5Ah ; 'Z'; void *
0x180035407  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003540c  nop
0x18003540d  lea     rcx, [rbp+SecurityDescriptor]
0x180035411  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035416  add     rsp, 80h
0x18003541d  pop     r14
0x18003541f  pop     rdi
0x180035420  pop     rsi
0x180035421  pop     rbx
0x180035422  pop     rbp
0x180035423  retn
```
