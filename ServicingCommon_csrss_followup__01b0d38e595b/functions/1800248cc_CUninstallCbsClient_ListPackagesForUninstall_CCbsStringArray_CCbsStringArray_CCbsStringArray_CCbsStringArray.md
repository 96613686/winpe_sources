# CUninstallCbsClient::ListPackagesForUninstall(CCbsStringArray *,CCbsStringArray *,CCbsStringArray *,CCbsStringArray *)

- ea: `0x1800248cc`
- end: `0x180024c78`
- name: `?ListPackagesForUninstall@CUninstallCbsClient@@QEAAJPEAVCCbsStringArray@@000@Z`
- size: `940`
- prototype: `__int64 __usercall@<rax>(CUninstallCbsClient *__hidden this@<rcx>, struct CCbsStringArray *@<rdx>, struct CCbsStringArray *@<r8>, struct CCbsStringArray *@<r9>, struct CCbsStringArray *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ba20`

## callees

- `0x1800218c0`
- `0x1800248cc`
- `0x180024c80`
- `0x180028030`
- `0x18002d2b0`
- `0x18002e1d0`
- `0x180042bac`
- `0x18004a658`
- `0x18007c504`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180024970`
- `ntdll!RtlRaiseStatus` at `0x180024970`
- `OLE32!CoTaskMemFree` at `0x180024b5c`
- `OLE32!CoTaskMemFree` at `0x180024b75`
- `OLE32!CoTaskMemFree` at `0x180024bf5`
- `OLE32!CoTaskMemFree` at `0x180024c0e`
- `OLE32!CoTaskMemFree` at `0x180024b5c`
- `OLE32!CoTaskMemFree` at `0x180024b75`
- `OLE32!CoTaskMemFree` at `0x180024bf5`
- `OLE32!CoTaskMemFree` at `0x180024c0e`

## string_xrefs

- `0x180024acc`: `Update`
- `0x180024ae0`: `Security Update`

## pseudocode

```c
__int64 __fastcall CUninstallCbsClient::ListPackagesForUninstall(
        CUninstallCbsClient *this,
        struct CCbsStringArray *a2,
        struct CCbsStringArray *a3,
        struct CCbsStringArray *a4,
        struct CCbsStringArray *a5)
{
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, __int64, int *); // rbx
  __int64 v16; // rax
  struct ICbsPackage **v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64); // rbx
  __int64 v20; // rax
  int v21; // eax
  struct ICbsIdentity *v22; // rdi
  __int64 (__fastcall *v23)(struct ICbsIdentity *, __int64); // rbx
  __int64 v24; // rax
  CCbsStringArray *v25; // rcx
  int v26; // eax
  wchar_t *v27; // rdx
  const char *v28; // r9
  __int64 v29; // rdx
  wchar_t *Str; // [rsp+38h] [rbp-39h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-31h] BYREF
  struct ICbsIdentity *v34; // [rsp+48h] [rbp-29h] BYREF
  int v35; // [rsp+50h] [rbp-21h] BYREF
  int v36; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v37; // [rsp+58h] [rbp-19h] BYREF
  int v38; // [rsp+60h] [rbp-11h] BYREF
  __int64 v39; // [rsp+68h] [rbp-9h] BYREF

  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 1);
  v35 = 0;
  v37 = 0;
  v36 = 0;
  v38 = 0;
  v39 = 0;
  v9 = **v5;
  InitPointer = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v39);
  v11 = v9(v5, &GUID_f112757a_565b_4260_bd05_9fa34417349a, InitPointer);
  v12 = v11;
  if ( v11 < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)v11, 1, "Failed querying ICbsSession10 interface.");
    goto LABEL_43;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 1) + 56LL))(
          *((_QWORD *)this + 1),
          80,
          &v37);
  v12 = v13;
  if ( v13 < 0 )
  {
    CBSWdsLog(0x4000000, (unsigned int)v13, 1, "Failed enumerating packages");
    goto LABEL_43;
  }
  while ( 1 )
  {
    v34 = 0;
    String1 = 0;
    Str = 0;
    v14 = v37;
    v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v37 + 24LL);
    v16 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v34);
    v12 = v15(v14, 1, v16, &v35);
    if ( v12 || !v35 )
      break;
    Windows::AutoComPtr<IClassFactory>::Close(this);
    v17 = (struct ICbsPackage **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(this);
    if ( (int)CUninstallCbsClient::OpenPackage(this, v34, v17) < 0 )
    {
      Windows::AutoComPtr<IClassFactory>::Close(&v34);
      goto LABEL_26;
    }
    v18 = *(_QWORD *)this;
    v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)this + 32LL);
    v20 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&String1);
    v21 = v19(v18, 8, v20);
    v12 = v21;
    if ( v21 < 0 )
    {
      v28 = "Failed getting release type for package";
      goto LABEL_36;
    }
    v22 = v34;
    v23 = *(__int64 (__fastcall **)(struct ICbsIdentity *, __int64))(*(_QWORD *)v34 + 64LL);
    v24 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&Str);
    v21 = v23(v22, v24);
    v12 = v21;
    if ( v21 < 0 )
    {
      v28 = "Failed getting Identity as string";
      goto LABEL_36;
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**(_QWORD **)this + 96LL))(*(_QWORD *)this, &v36, &v38);
    v12 = v21;
    if ( v21 < 0 )
    {
      v28 = "Failed getting status for package state query.";
LABEL_36:
      v29 = (unsigned int)v21;
      goto LABEL_37;
    }
    if ( v36 < 7 )
    {
      v12 = -2147418113;
      v28 = "Incorrect package state.";
      v29 = 2147549183LL;
LABEL_37:
      CBSWdsLog(0x4000000, v29, 1, v28);
      break;
    }
    if ( !wcsicmp(String1, L"Product") )
    {
      v25 = a2;
LABEL_24:
      v27 = Str;
      goto LABEL_25;
    }
    if ( !wcsicmp(String1, L"Update") || !wcsicmp(String1, L"Security Update") )
    {
      if ( !wcsstr(Str, L"-Wrapper") )
        goto LABEL_26;
      v25 = a5;
      goto LABEL_24;
    }
    if ( !wcsicmp(String1, L"Language Pack") )
    {
      v25 = a4;
      goto LABEL_24;
    }
    v26 = wcsicmp(String1, L"OnDemand Pack");
    v27 = Str;
    if ( v26 )
      v25 = a5;
    else
      v25 = a3;
LABEL_25:
    v12 = CCbsStringArray::CopyAndAdd(v25, v27);
    if ( v12 < 0 )
    {
      CBSWdsLog(0x4000000, (unsigned int)v12, 1, "Failed adding package : %ws.", Str);
      break;
    }
LABEL_26:
    if ( Str )
    {
      CoTaskMemFree(Str);
      Str = 0;
    }
    if ( String1 )
    {
      CoTaskMemFree(String1);
      String1 = 0;
    }
    Windows::AutoComPtr<IClassFactory>::Close(&v34);
  }
  if ( Str )
  {
    CoTaskMemFree(Str);
    Str = 0;
  }
  if ( String1 )
  {
    CoTaskMemFree(String1);
    String1 = 0;
  }
  Windows::AutoComPtr<IClassFactory>::Close(&v34);
LABEL_43:
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800248cc  push    rbp
0x1800248ce  push    rbx
0x1800248cf  push    rsi
0x1800248d0  push    rdi
0x1800248d1  push    r12
0x1800248d3  push    r13
0x1800248d5  push    r14
0x1800248d7  push    r15
0x1800248d9  lea     rbp, [rsp-17h]
0x1800248de  sub     rsp, 88h
0x1800248e5  mov     rax, cs:__security_cookie
0x1800248ec  xor     rax, rsp
0x1800248ef  mov     [rbp+4Fh+var_50], rax
0x1800248f3  mov     rdi, [rcx+8]
0x1800248f7  xor     eax, eax
0x1800248f9  mov     r15, [rbp+4Fh+arg_20]
0x1800248fd  mov     r14, rcx
0x180024900  mov     [rbp+4Fh+var_70], eax
0x180024903  lea     rcx, [rbp+4Fh+var_58]
0x180024907  mov     [rbp+4Fh+var_68], rax
0x18002490b  mov     r13, r8
0x18002490e  mov     [rbp+4Fh+var_6C], eax
0x180024911  mov     r12, rdx
0x180024914  mov     [rbp+4Fh+var_60], eax
0x180024917  mov     [rbp+4Fh+var_58], rax
0x18002491b  mov     rax, [rdi]
0x18002491e  mov     [rbp+4Fh+var_90], r9
0x180024922  mov     rbx, [rax]
0x180024925  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18002492a  mov     r8, rax
0x18002492d  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x180024934  mov     rax, rbx
0x180024937  mov     rcx, rdi
0x18002493a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002493f  xor     edi, edi
0x180024941  mov     ebx, eax
0x180024943  test    eax, eax
0x180024945  jns     short loc_180024965
0x180024947  lea     r9, aFailedQuerying; "Failed querying ICbsSession10 interface"...
0x18002494e  mov     r8d, 1
0x180024954  mov     edx, eax
0x180024956  mov     ecx, 4000000h
0x18002495b  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180024960  jmp     loc_180024C27
0x180024965  cmp     [rbp+4Fh+var_68], rdi
0x180024969  jz      short loc_18002497D
0x18002496b  mov     ecx, 0C00000E5h; Status
0x180024970  call    cs:__imp_RtlRaiseStatus
0x180024977  nop     dword ptr [rax+rax+00h]
0x18002497c  int     3; Trap to Debugger
0x18002497d  mov     rcx, [r14+8]
0x180024981  lea     r8, [rbp+4Fh+var_68]
0x180024985  mov     edx, 50h ; 'P'
0x18002498a  mov     rax, [rcx]
0x18002498d  mov     rax, [rax+38h]
0x180024991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024996  mov     ebx, eax
0x180024998  test    eax, eax
0x18002499a  jns     short loc_1800249A5
0x18002499c  lea     r9, aFailedEnumerat; "Failed enumerating packages"
0x1800249a3  jmp     short loc_18002494E
0x1800249a5  mov     esi, 1
0x1800249aa  mov     [rbp+4Fh+var_78], rdi
0x1800249ae  lea     rcx, [rbp+4Fh+var_78]
0x1800249b2  mov     [rbp+4Fh+String1], rdi
0x1800249b6  mov     [rbp+4Fh+Str], rdi
0x1800249ba  mov     rdi, [rbp+4Fh+var_68]
0x1800249be  mov     rax, [rdi]
0x1800249c1  mov     rbx, [rax+18h]
0x1800249c5  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x1800249ca  mov     r8, rax
0x1800249cd  lea     r9, [rbp+4Fh+var_70]
0x1800249d1  mov     rax, rbx
0x1800249d4  mov     edx, esi
0x1800249d6  mov     rcx, rdi
0x1800249d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249de  xor     edi, edi
0x1800249e0  mov     ebx, eax
0x1800249e2  test    eax, eax
0x1800249e4  jnz     loc_180024BEC
0x1800249ea  cmp     [rbp+4Fh+var_70], edi
0x1800249ed  jz      loc_180024BEC
0x1800249f3  mov     rcx, r14
0x1800249f6  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x1800249fb  mov     rcx, r14
0x1800249fe  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x180024a03  mov     rdx, [rbp+4Fh+var_78]; struct ICbsIdentity *
0x180024a07  mov     r8, rax; struct ICbsPackage **
0x180024a0a  mov     rcx, r14; this
0x180024a0d  call    ?OpenPackage@CUninstallCbsClient@@AEAAJPEAUICbsIdentity@@PEAPEAUICbsPackage@@@Z; CUninstallCbsClient::OpenPackage(ICbsIdentity *,ICbsPackage * *)
0x180024a12  test    eax, eax
0x180024a14  jns     short loc_180024A24
0x180024a16  lea     rcx, [rbp+4Fh+var_78]
0x180024a1a  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x180024a1f  jmp     loc_180024B53
0x180024a24  mov     rdi, [r14]
0x180024a27  lea     rcx, [rbp+4Fh+String1]
0x180024a2b  mov     rax, [rdi]
0x180024a2e  mov     rbx, [rax+20h]
0x180024a32  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x180024a37  mov     r8, rax
0x180024a3a  mov     edx, 8
0x180024a3f  mov     rax, rbx
0x180024a42  mov     rcx, rdi
0x180024a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a4a  xor     edi, edi
0x180024a4c  mov     ebx, eax
0x180024a4e  test    eax, eax
0x180024a50  js      loc_180024BD6
0x180024a56  mov     rdi, [rbp+4Fh+var_78]
0x180024a5a  lea     rcx, [rbp+4Fh+Str]
0x180024a5e  mov     rax, [rdi]
0x180024a61  mov     rbx, [rax+40h]
0x180024a65  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x180024a6a  mov     rdx, rax
0x180024a6d  mov     rcx, rdi
0x180024a70  mov     rax, rbx
0x180024a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a78  xor     edi, edi
0x180024a7a  mov     ebx, eax
0x180024a7c  test    eax, eax
0x180024a7e  js      loc_180024BCD
0x180024a84  mov     rcx, [r14]
0x180024a87  lea     r8, [rbp+4Fh+var_60]
0x180024a8b  lea     rdx, [rbp+4Fh+var_6C]
0x180024a8f  mov     rax, [rcx]
0x180024a92  mov     rax, [rax+60h]
0x180024a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a9b  mov     ebx, eax
0x180024a9d  test    eax, eax
0x180024a9f  js      loc_180024BC4
0x180024aa5  cmp     [rbp+4Fh+var_6C], 7
0x180024aa9  jl      loc_180024BB4
0x180024aaf  mov     rcx, [rbp+4Fh+String1]; String1
0x180024ab3  lea     rdx, aProduct; "Product"
0x180024aba  call    _wcsicmp
0x180024abf  test    eax, eax
0x180024ac1  jnz     short loc_180024AC8
0x180024ac3  mov     rcx, r12
0x180024ac6  jmp     short loc_180024B44
0x180024ac8  mov     rcx, [rbp+4Fh+String1]; String1
0x180024acc  lea     rdx, aUpdate; "Update"
0x180024ad3  call    _wcsicmp
0x180024ad8  test    eax, eax
0x180024ada  jz      short loc_180024B2C
0x180024adc  mov     rcx, [rbp+4Fh+String1]; String1
0x180024ae0  lea     rdx, aSecurityUpdate; "Security Update"
0x180024ae7  call    _wcsicmp
0x180024aec  test    eax, eax
0x180024aee  jz      short loc_180024B2C
0x180024af0  mov     rcx, [rbp+4Fh+String1]; String1
0x180024af4  lea     rdx, aLanguagePack; "Language Pack"
0x180024afb  call    _wcsicmp
0x180024b00  test    eax, eax
0x180024b02  jnz     short loc_180024B0A
0x180024b04  mov     rcx, [rbp+4Fh+var_90]
0x180024b08  jmp     short loc_180024B44
0x180024b0a  mov     rcx, [rbp+4Fh+String1]; String1
0x180024b0e  lea     rdx, aOndemandPack; "OnDemand Pack"
0x180024b15  call    _wcsicmp
0x180024b1a  mov     rdx, [rbp+4Fh+Str]
0x180024b1e  test    eax, eax
0x180024b20  jnz     short loc_180024B27
0x180024b22  mov     rcx, r13
0x180024b25  jmp     short loc_180024B48
0x180024b27  mov     rcx, r15
0x180024b2a  jmp     short loc_180024B48
0x180024b2c  mov     rcx, [rbp+4Fh+Str]; Str
0x180024b30  lea     rdx, aWrapper; "-Wrapper"
0x180024b37  call    wcsstr
0x180024b3c  test    rax, rax
0x180024b3f  jz      short loc_180024B53
0x180024b41  mov     rcx, r15; this
0x180024b44  mov     rdx, [rbp+4Fh+Str]; wchar_t *
0x180024b48  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x180024b4d  mov     ebx, eax
0x180024b4f  test    eax, eax
0x180024b51  js      short loc_180024B93
0x180024b53  mov     rcx, [rbp+4Fh+Str]; pv
0x180024b57  test    rcx, rcx
0x180024b5a  jz      short loc_180024B6C
0x180024b5c  call    cs:__imp_CoTaskMemFree
0x180024b63  nop     dword ptr [rax+rax+00h]
0x180024b68  mov     [rbp+4Fh+Str], rdi
0x180024b6c  mov     rcx, [rbp+4Fh+String1]; pv
0x180024b70  test    rcx, rcx
0x180024b73  jz      short loc_180024B85
0x180024b75  call    cs:__imp_CoTaskMemFree
0x180024b7c  nop     dword ptr [rax+rax+00h]
0x180024b81  mov     [rbp+4Fh+String1], rdi
0x180024b85  lea     rcx, [rbp+4Fh+var_78]
0x180024b89  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x180024b8e  jmp     loc_1800249AA
0x180024b93  mov     rax, [rbp+4Fh+Str]
0x180024b97  lea     r9, aFailedAddingPa; "Failed adding package : %ws."
0x180024b9e  mov     r8d, esi
0x180024ba1  mov     [rsp+0C0h+var_A0], rax
0x180024ba6  mov     edx, ebx
0x180024ba8  mov     ecx, 4000000h
0x180024bad  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180024bb2  jmp     short loc_180024BEC
0x180024bb4  mov     ebx, 8000FFFFh
0x180024bb9  lea     r9, aIncorrectPacka; "Incorrect package state."
0x180024bc0  mov     edx, ebx
0x180024bc2  jmp     short loc_180024BDF
0x180024bc4  lea     r9, aFailedGettingS; "Failed getting status for package state"...
0x180024bcb  jmp     short loc_180024BDD
0x180024bcd  lea     r9, aFailedGettingI; "Failed getting Identity as string"
0x180024bd4  jmp     short loc_180024BDD
0x180024bd6  lea     r9, aFailedGettingR; "Failed getting release type for package"
0x180024bdd  mov     edx, eax
0x180024bdf  mov     r8d, esi
0x180024be2  mov     ecx, 4000000h
0x180024be7  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x180024bec  mov     rcx, [rbp+4Fh+Str]; pv
0x180024bf0  test    rcx, rcx
0x180024bf3  jz      short loc_180024C05
0x180024bf5  call    cs:__imp_CoTaskMemFree
0x180024bfc  nop     dword ptr [rax+rax+00h]
0x180024c01  mov     [rbp+4Fh+Str], rdi
0x180024c05  mov     rcx, [rbp+4Fh+String1]; pv
0x180024c09  test    rcx, rcx
0x180024c0c  jz      short loc_180024C1E
0x180024c0e  call    cs:__imp_CoTaskMemFree
0x180024c15  nop     dword ptr [rax+rax+00h]
0x180024c1a  mov     [rbp+4Fh+String1], rdi
0x180024c1e  lea     rcx, [rbp+4Fh+var_78]
0x180024c22  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x180024c27  mov     rcx, [rbp+4Fh+var_58]
0x180024c2b  test    rcx, rcx
0x180024c2e  jz      short loc_180024C40
0x180024c30  mov     rax, [rcx]
0x180024c33  mov     rax, [rax+10h]
0x180024c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c3c  mov     [rbp+4Fh+var_58], rdi
0x180024c40  mov     rcx, [rbp+4Fh+var_68]
0x180024c44  test    rcx, rcx
0x180024c47  jz      short loc_180024C55
0x180024c49  mov     rax, [rcx]
0x180024c4c  mov     rax, [rax+10h]
0x180024c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c55  mov     eax, ebx
0x180024c57  mov     rcx, [rbp+4Fh+var_50]
0x180024c5b  xor     rcx, rsp; StackCookie
0x180024c5e  call    __security_check_cookie
0x180024c63  add     rsp, 88h
0x180024c6a  pop     r15
0x180024c6c  pop     r14
0x180024c6e  pop     r13
0x180024c70  pop     r12
0x180024c72  pop     rdi
0x180024c73  pop     rsi
0x180024c74  pop     rbx
0x180024c75  pop     rbp
0x180024c76  retn
```
