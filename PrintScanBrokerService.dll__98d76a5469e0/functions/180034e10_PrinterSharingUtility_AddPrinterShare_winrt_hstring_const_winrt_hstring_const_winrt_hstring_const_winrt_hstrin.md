# PrinterSharingUtility::AddPrinterShare(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)

- ea: `0x180034e10`
- end: `0x180034fee`
- name: `?AddPrinterShare@PrinterSharingUtility@@SAXAEBUhstring@winrt@@0000@Z`
- size: `478`
- prototype: `void __fastcall(const struct winrt::hstring *this, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e460`

## callees

- `0x180003a0c`
- `0x180006b3c`
- `0x18000fa2c`
- `0x18002b28c`
- `0x18002b2cc`
- `0x180030a38`
- `0x180034ddc`
- `0x180034e10`
- `0x1800350f4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180034e5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180034e5f`
- `srvcli!NetShareAdd` at `0x180034f5a`
- `srvcli!NetShareAdd` at `0x180034f5a`

## string_xrefs

- `0x180034e6e`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed!`
- `0x180034e7e`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`
- `0x180034fb1`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`
- `0x180034fdc`: `onecoreuap\printscan\print\printscanbroker\class\printersharingutility.cpp`

## pseudocode

```c
void __fastcall PrinterSharingUtility::AddPrinterShare(
        const struct winrt::hstring *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        const struct winrt::hstring *a4,
        const struct winrt::hstring *a5)
{
  const WCHAR *v9; // rax
  char v10; // bl
  BOOL v11; // eax
  DWORD v12; // edx
  WCHAR *v13; // r10
  BYTE *v14; // r8
  __int64 v15; // rcx
  DWORD v16; // edi
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // eax
  char v20; // dl
  unsigned int v21; // [rsp+20h] [rbp-A1h]
  char *v22; // [rsp+28h] [rbp-99h]
  char *v23; // [rsp+28h] [rbp-99h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-91h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+38h] [rbp-89h] BYREF
  const unsigned __int16 *v26; // [rsp+40h] [rbp-81h] BYREF
  int v27; // [rsp+48h] [rbp-79h]
  const unsigned __int16 *v28; // [rsp+50h] [rbp-71h]
  int v29; // [rsp+5Ch] [rbp-65h]
  int v30; // [rsp+60h] [rbp-61h]
  const unsigned __int16 *v31; // [rsp+68h] [rbp-59h]
  PSECURITY_DESCRIPTOR v32; // [rsp+80h] [rbp-41h]
  BYTE buf[8]; // [rsp+90h] [rbp-31h] BYREF
  int v34; // [rsp+98h] [rbp-29h]
  const unsigned __int16 *v35; // [rsp+A0h] [rbp-21h]
  int v36; // [rsp+ACh] [rbp-15h]
  int v37; // [rsp+B0h] [rbp-11h]
  const unsigned __int16 *v38; // [rsp+B8h] [rbp-9h]
  WCHAR *v39; // [rsp+C8h] [rbp+7h]
  PSECURITY_DESCRIPTOR v40; // [rsp+D8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]
  DWORD parm_err; // [rsp+138h] [rbp+77h] BYREF

  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  v9 = winrt::hstring::c_str(a5);
  v10 = 1;
  v11 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &SecurityDescriptor, &SecurityDescriptorSize);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0x13,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
    (const char *)!v11,
    (bool)"ConvertStringSecurityDescriptorToSecurityDescriptor failed!",
    v22);
  memset_0(&v26, 0, 0x48u);
  memset_0(buf, 0, 0x50u);
  if ( *(_QWORD *)a4 )
  {
    winrt::hstring::c_str(a4);
    v34 = 1;
    v36 = -1;
    v37 = -1;
    *(_QWORD *)buf = winrt::hstring::c_str(this);
    v38 = winrt::hstring::c_str(a2);
    v35 = winrt::hstring::c_str(a3);
    v39 = v13;
    v40 = SecurityDescriptor;
    v14 = buf;
  }
  else
  {
    v27 = 1;
    v29 = -1;
    v30 = -1;
    v26 = winrt::hstring::c_str(this);
    v31 = winrt::hstring::c_str(a2);
    v28 = winrt::hstring::c_str(a3);
    v32 = SecurityDescriptor;
    v14 = (BYTE *)&v26;
  }
  parm_err = 0;
  v16 = NetShareAdd(v13, v12, v14, &parm_err);
  if ( v16 )
  {
    if ( v16 != 87 || parm_err != 1 )
      v10 = 0;
    LOBYTE(v15) = v10;
    LOBYTE(v17) = wil::verify_bool<bool,0>(v15);
    v19 = wil::verify_win32<long>(v18, v17);
    LOBYTE(v21) = v20;
    wil::details::in1diag3::Throw_Win32IfMsg(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
      (const char *)v19,
      v21,
      (bool)"Invalid share name!",
      (const char *)SecurityDescriptor);
    LODWORD(v23) = parm_err;
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\printersharingutility.cpp",
      (const char *)v16,
      (unsigned int)"Failed to share printer! Parameter error %d",
      v23);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
}

```

## disassembly

```asm
0x180034e10  push    rbp
0x180034e12  push    rbx
0x180034e13  push    rsi
0x180034e14  push    rdi
0x180034e15  push    r14
0x180034e17  push    r15
0x180034e19  lea     rbp, [rsp-27h]
0x180034e1e  sub     rsp, 0E8h
0x180034e25  mov     r15, r9
0x180034e28  mov     rdi, r8
0x180034e2b  mov     rsi, rdx
0x180034e2e  mov     r14, rcx
0x180034e31  mov     [rsp+110h+SecurityDescriptorSize], 0
0x180034e39  mov     [rsp+110h+SecurityDescriptor], 0; char *
0x180034e42  mov     rcx, [rbp+4Fh+arg_20]; this
0x180034e46  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034e4b  lea     r9, [rsp+110h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180034e50  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x180034e55  mov     ebx, 1
0x180034e5a  mov     edx, ebx; StringSDRevision
0x180034e5c  mov     rcx, rax; StringSecurityDescriptor
0x180034e5f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180034e65  test    eax, eax
0x180034e67  setz    al
0x180034e6a  mov     rcx, [rbp+57h]; this
0x180034e6e  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180034e75  mov     qword ptr [rsp+110h+var_F0], rdx; bool
0x180034e7a  movzx   r9d, al; char *
0x180034e7e  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x180034e85  lea     edx, [rbx+12h]; void *
0x180034e88  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180034e8d  xor     edx, edx; Val
0x180034e8f  lea     r8d, [rbx+47h]; Size
0x180034e93  lea     rcx, [rsp+110h+var_D0]; void *
0x180034e98  call    memset_0
0x180034e9d  xor     edx, edx; Val
0x180034e9f  lea     r8d, [rbx+4Fh]; Size
0x180034ea3  lea     rcx, [rbp+4Fh+buf]; void *
0x180034ea7  call    memset_0
0x180034eac  cmp     qword ptr [r15], 0
0x180034eb0  jnz     short loc_180034EFB
0x180034eb2  xor     r10d, r10d
0x180034eb5  mov     edx, 1F6h
0x180034eba  mov     [rbp+4Fh+var_C8], ebx
0x180034ebd  or      eax, 0FFFFFFFFh
0x180034ec0  mov     [rbp+4Fh+var_B4], eax
0x180034ec3  mov     [rbp+4Fh+var_B0], eax
0x180034ec6  mov     rcx, r14; this
0x180034ec9  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034ece  mov     [rsp+110h+var_D0], rax
0x180034ed3  mov     rcx, rsi; this
0x180034ed6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034edb  mov     [rbp+4Fh+var_A8], rax
0x180034edf  mov     rcx, rdi; this
0x180034ee2  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034ee7  mov     [rbp+4Fh+var_C0], rax
0x180034eeb  mov     rax, [rsp+110h+SecurityDescriptor]
0x180034ef0  mov     [rbp+4Fh+var_90], rax
0x180034ef4  lea     r8, [rsp+110h+var_D0]
0x180034ef9  jmp     short loc_180034F4C
0x180034efb  mov     rcx, r15; this
0x180034efe  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034f03  mov     r10, rax
0x180034f06  mov     edx, 1F7h
0x180034f0b  mov     [rbp+4Fh+var_78], ebx
0x180034f0e  or      eax, 0FFFFFFFFh
0x180034f11  mov     [rbp+4Fh+var_64], eax
0x180034f14  mov     [rbp+4Fh+var_60], eax
0x180034f17  mov     rcx, r14; this
0x180034f1a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034f1f  mov     qword ptr [rbp+4Fh+buf], rax
0x180034f23  mov     rcx, rsi; this
0x180034f26  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034f2b  mov     [rbp+4Fh+var_58], rax
0x180034f2f  mov     rcx, rdi; this
0x180034f32  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180034f37  mov     [rbp+4Fh+var_70], rax
0x180034f3b  mov     [rbp+4Fh+var_48], r10
0x180034f3f  mov     rax, [rsp+110h+SecurityDescriptor]
0x180034f44  mov     [rbp+4Fh+var_38], rax
0x180034f48  lea     r8, [rbp+4Fh+buf]; buf
0x180034f4c  mov     [rbp+4Fh+parm_err], 0
0x180034f53  lea     r9, [rbp+4Fh+parm_err]; parm_err
0x180034f57  mov     rcx, r10; servername
0x180034f5a  call    cs:__imp_NetShareAdd
0x180034f60  mov     edi, eax
0x180034f62  test    eax, eax
0x180034f64  jnz     short loc_180034F80
0x180034f66  lea     rcx, [rsp+110h+SecurityDescriptor]
0x180034f6b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180034f70  add     rsp, 0E8h
0x180034f77  pop     r15
0x180034f79  pop     r14
0x180034f7b  pop     rdi
0x180034f7c  pop     rsi
0x180034f7d  pop     rbx
0x180034f7e  pop     rbp
0x180034f7f  retn
0x180034f80  cmp     edi, 57h ; 'W'
0x180034f83  jnz     short loc_180034F8A
0x180034f85  cmp     [rbp+4Fh+parm_err], ebx
0x180034f88  jz      short loc_180034F8C
0x180034f8a  xor     bl, bl
0x180034f8c  mov     cl, bl
0x180034f8e  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x180034f93  mov     dl, al
0x180034f95  call    ??$verify_win32@J@wil@@YAJJ@Z; wil::verify_win32<long>(long)
0x180034f9a  mov     r9d, eax; char *
0x180034f9d  mov     rcx, [rbp+57h]; this
0x180034fa1  lea     rax, aInvalidShareNa; "Invalid share name!"
0x180034fa8  mov     [rsp+110h+var_E8], rax; bool
0x180034fad  mov     [rsp+110h+var_F0], dl; unsigned int
0x180034fb1  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x180034fb8  mov     edx, 3Ah ; ':'; void *
0x180034fbd  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x180034fc2  mov     rcx, [rbp+57h]; this
0x180034fc6  mov     eax, [rbp+4Fh+parm_err]
0x180034fc9  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x180034fcd  lea     rax, aFailedToShareP; "Failed to share printer! Parameter erro"...
0x180034fd4  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x180034fd9  mov     r9d, edi; char *
0x180034fdc  lea     r8, aOnecoreuapPrin_3; "onecoreuap\\printscan\\print\\printscan"...
0x180034fe3  mov     edx, 3Bh ; ';'; void *
0x180034fe8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
