# ShieldProvider::GetWscIniConfiguration

- ea: `0x180011e18`
- end: `0x1800123a2`
- name: `ShieldProvider::GetWscIniConfiguration`
- size: `1418`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013630`

## callees

- `0x180004710`
- `0x180004ae0`
- `0x180004bc0`
- `0x18000d7fc`
- `0x180011e18`
- `0x1800159a0`
- `0x1800da5f4`
- `0x1800dc038`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180011f40`
- `KERNEL32!CloseHandle` at `0x18001200e`
- `KERNEL32!CloseHandle` at `0x180012380`
- `KERNEL32!CloseHandle` at `0x180011f40`
- `KERNEL32!CloseHandle` at `0x18001200e`
- `KERNEL32!CloseHandle` at `0x180012380`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800120bd`
- `KERNEL32!GetPrivateProfileStringW` at `0x18001210d`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012157`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800121a2`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800121ed`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012238`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012283`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800120bd`
- `KERNEL32!GetPrivateProfileStringW` at `0x18001210d`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012157`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800121a2`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800121ed`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012238`
- `KERNEL32!GetPrivateProfileStringW` at `0x180012283`
- `KERNEL32!GetFileSizeEx` at `0x180011f8a`
- `KERNEL32!GetFileSizeEx` at `0x180011f8a`

## string_xrefs

- `0x180011eb2`: `\SecurityProductInformation.ini`
- `0x180012103`: `Company`
- `0x180012130`: `Company : %ls`
- `0x18001214d`: `PathToSignedReportingExe`
- `0x18001217b`: `PathToSignedReportingExe : %ls`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetWscIniConfiguration(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v3; // rax
  unsigned __int64 v4; // r9
  unsigned __int16 v5; // cx
  void *lpFileName; // rbx
  int File; // eax
  const struct std::nothrow_t *v8; // rdx
  unsigned int v9; // edi
  HANDLE v11; // rdi
  const struct std::nothrow_t *v12; // rdx
  unsigned int LastFailure; // eax
  int v14; // esi
  PVOID *v15; // rcx
  DWORD PrivateProfileStringW; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  void *v23; // r13
  void *v24; // r12
  void *v25; // r14
  unsigned __int16 *v26; // rsi
  void *v27; // r15
  const struct std::nothrow_t *v28; // rdx
  unsigned int nSize; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+38h] [rbp-C8h]
  void *v32; // [rsp+40h] [rbp-C0h]
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  void *v36; // [rsp+68h] [rbp-98h] BYREF
  void *v37; // [rsp+70h] [rbp-90h] BYREF
  void *v38; // [rsp+78h] [rbp-88h] BYREF
  void *v39; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v42; // [rsp+98h] [rbp-68h]
  WCHAR ReturnedString[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v44[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v42 = a2;
  *a2 = 0;
  v3 = 0;
  v4 = 0;
  if ( a1 )
  {
    do
    {
      v5 = *(_WORD *)(a1 + 2 * v3);
      if ( v5 == 92 || v5 == 47 )
        v4 = v3;
      v44[v3++] = v5;
    }
    while ( *(_WORD *)(a1 + 2 * v3) && v3 < 0x104 );
    if ( 2 * v4 >= 0x208 )
      goto LABEL_62;
    v44[v4] = 0;
  }
  else
  {
    v44[0] = 0;
  }
  FileSize.QuadPart = 0;
  CommonUtil::NewSprintfW(
    (CommonUtil *)&FileSize,
    (unsigned __int16 **)L"%ls%ls",
    v44,
    L"\\SecurityProductInformation.ini");
  lpFileName = (void *)FileSize.QuadPart;
  hObject = (HANDLE)-1LL;
  File = CommonUtil::UtilCreateFile(
           (CommonUtil *)&hObject,
           (void **)FileSize.QuadPart,
           (const unsigned __int16 *)0x80000000LL,
           1u,
           nSize,
           0,
           v30,
           v31,
           v32);
  v9 = File;
  if ( File < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        WPP_c15b3361942b3cf72eefef62f859076e_Traceguids,
        (unsigned int)File);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    if ( lpFileName )
      operator delete(lpFileName, v8);
    return v9;
  }
  v11 = hObject;
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(hObject, &FileSize) )
  {
    v14 = 0;
    LODWORD(hObject) = 0;
    if ( FileSize.QuadPart > 0x800uLL )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_c15b3361942b3cf72eefef62f859076e_Traceguids,
          (_DWORD)lpFileName,
          0);
      goto LABEL_27;
    }
  }
  else
  {
    LastFailure = HrGetLastFailure();
    v14 = LastFailure;
    LODWORD(hObject) = LastFailure;
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, LastFailure);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 < 0 )
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
        WPP_SF_d(v15[2], 31, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids, (unsigned int)v14);
LABEL_27:
      if ( v11 != (HANDLE)-1LL )
        CloseHandle(v11);
      if ( lpFileName )
        operator delete(lpFileName, v12);
      return (unsigned int)v14;
    }
  }
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  FileSize.QuadPart = 0;
  v35 = 0;
  PrivateProfileStringW = GetPrivateProfileStringW(
                            L"Products",
                            L"Name",
                            L"n/a",
                            ReturnedString,
                            0x104u,
                            (LPCWSTR)lpFileName);
  if ( 2 * (unsigned __int64)PrivateProfileStringW >= 0x20A )
    goto LABEL_62;
  ReturnedString[PrivateProfileStringW] = 0;
  CommonUtil::NewSprintfW((CommonUtil *)&v40, (unsigned __int16 **)L" , Name : %ls", ReturnedString);
  v17 = GetPrivateProfileStringW(L"Products", L"Company", L"n/a", ReturnedString, 0x104u, (LPCWSTR)lpFileName);
  if ( 2 * (unsigned __int64)v17 >= 0x20A )
    goto LABEL_62;
  ReturnedString[v17] = 0;
  CommonUtil::NewSprintfW((CommonUtil *)&v39, (unsigned __int16 **)L"Company : %ls", ReturnedString);
  v18 = GetPrivateProfileStringW(
          L"Products",
          L"PathToSignedReportingExe",
          L"n/a",
          ReturnedString,
          0x104u,
          (LPCWSTR)lpFileName);
  if ( 2 * (unsigned __int64)v18 >= 0x20A )
    goto LABEL_62;
  ReturnedString[v18] = 0;
  CommonUtil::NewSprintfW((CommonUtil *)&v38, (unsigned __int16 **)L"PathToSignedReportingExe : %ls", ReturnedString);
  v19 = GetPrivateProfileStringW(L"Products", L"Version", L"n/a", ReturnedString, 0x104u, (LPCWSTR)lpFileName);
  if ( 2 * (unsigned __int64)v19 >= 0x20A )
    goto LABEL_62;
  ReturnedString[v19] = 0;
  CommonUtil::NewSprintfW((CommonUtil *)&v37, (unsigned __int16 **)L"Version : %ls", ReturnedString);
  v20 = GetPrivateProfileStringW(L"Products", L"Environment", L"n/a", ReturnedString, 0x104u, (LPCWSTR)lpFileName);
  if ( 2 * (unsigned __int64)v20 >= 0x20A
    || (ReturnedString[v20] = 0,
        CommonUtil::NewSprintfW((CommonUtil *)&v36, (unsigned __int16 **)L"Environment : %ls", ReturnedString),
        v21 = GetPrivateProfileStringW(
                L"Products",
                L"Runtime_platform",
                L"n/a",
                ReturnedString,
                0x104u,
                (LPCWSTR)lpFileName),
        2 * (unsigned __int64)v21 >= 0x20A)
    || (ReturnedString[v21] = 0,
        CommonUtil::NewSprintfW((CommonUtil *)&FileSize, (unsigned __int16 **)L"Runtime_platform : %ls", ReturnedString),
        v22 = GetPrivateProfileStringW(L"Products", L"Upgrade", L"n/a", ReturnedString, 0x104u, (LPCWSTR)lpFileName),
        2 * (unsigned __int64)v22 >= 0x20A) )
  {
LABEL_62:
    _report_rangecheckfailure();
  }
  ReturnedString[v22] = 0;
  CommonUtil::NewSprintfW((CommonUtil *)&v35, (unsigned __int16 **)L"Upgrade : %ls", ReturnedString);
  v23 = v36;
  v24 = v37;
  v25 = v39;
  v26 = v40;
  v41 = 0;
  v27 = v38;
  CommonUtil::NewSprintfW(
    (CommonUtil *)&v41,
    (unsigned __int16 **)L"%ls , %ls , %ls , %ls , %ls , %ls , %ls",
    v40,
    v39,
    v38,
    v37,
    v36,
    FileSize.QuadPart,
    v35);
  *v42 = v41;
  if ( v35 )
    operator delete(v35, v28);
  if ( FileSize.QuadPart )
    operator delete((void *)FileSize.QuadPart, v28);
  if ( v23 )
    operator delete(v23, v28);
  if ( v24 )
    operator delete(v24, v28);
  if ( v27 )
    operator delete(v27, v28);
  if ( v25 )
    operator delete(v25, v28);
  if ( v26 )
    operator delete(v26, v28);
  if ( v11 != (HANDLE)-1LL )
    CloseHandle(v11);
  if ( lpFileName )
    operator delete(lpFileName, v28);
  return (unsigned int)hObject;
}

```

## disassembly

```asm
0x180011e18  push    rbp
0x180011e1a  push    rbx
0x180011e1b  push    rsi
0x180011e1c  push    rdi
0x180011e1d  push    r12
0x180011e1f  push    r13
0x180011e21  push    r14
0x180011e23  push    r15
0x180011e25  lea     rbp, [rsp-3D8h]
0x180011e2d  sub     rsp, 4D8h
0x180011e34  mov     rax, cs:__security_cookie
0x180011e3b  xor     rax, rsp
0x180011e3e  mov     [rbp+410h+var_50], rax
0x180011e45  xor     r15d, r15d
0x180011e48  mov     [rbp+410h+var_478], rdx
0x180011e4c  mov     [rdx], r15
0x180011e4f  mov     r8, rcx
0x180011e52  mov     eax, r15d
0x180011e55  mov     r9d, r15d
0x180011e58  mov     r12d, 104h
0x180011e5e  test    rcx, rcx
0x180011e61  jz      short loc_180011EAA
0x180011e63  movzx   ecx, word ptr [r8+rax*2]
0x180011e68  cmp     cx, 5Ch ; '\'
0x180011e6c  jz      short loc_180011E74
0x180011e6e  cmp     cx, 2Fh ; '/'
0x180011e72  jnz     short loc_180011E77
0x180011e74  mov     r9, rax
0x180011e77  mov     [rbp+rax*2+410h+var_260], cx
0x180011e7f  inc     rax
0x180011e82  cmp     [r8+rax*2], r15w
0x180011e87  jz      short loc_180011E8E
0x180011e89  cmp     rax, r12
0x180011e8c  jb      short loc_180011E63
0x180011e8e  lea     rcx, [r9+r9]
0x180011e92  cmp     rcx, 208h
0x180011e99  jnb     loc_18001239C
0x180011e9f  mov     [rbp+rcx+410h+var_260], r15w
0x180011ea8  jmp     short loc_180011EB2
0x180011eaa  mov     [rbp+410h+var_260], r15w
0x180011eb2  lea     r9, aSecurityproduc; "\\SecurityProductInformation.ini"
0x180011eb9  mov     qword ptr [rsp+510h+FileSize], r15
0x180011ebe  lea     r8, [rbp+410h+var_260]; unsigned __int16 *
0x180011ec5  lea     rdx, aLsLs_2; "%ls%ls"
0x180011ecc  lea     rcx, [rsp+510h+FileSize]; this
0x180011ed1  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180011ed6  mov     rbx, qword ptr [rsp+510h+FileSize]
0x180011edb  lea     rcx, [rsp+510h+hObject]; this
0x180011ee0  or      r13, 0FFFFFFFFFFFFFFFFh
0x180011ee4  mov     dword ptr [rsp+510h+lpFileName], r15d; unsigned int
0x180011ee9  mov     r8d, 80000000h; unsigned __int16 *
0x180011eef  mov     [rsp+510h+hObject], r13
0x180011ef4  mov     rdx, rbx; void **
0x180011ef7  lea     r9d, [r13+2]; unsigned int
0x180011efb  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x180011f00  mov     edi, eax
0x180011f02  test    eax, eax
0x180011f04  jns     short loc_180011F78
0x180011f06  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f0d  lea     r14, WPP_GLOBAL_Control
0x180011f14  cmp     rcx, r14
0x180011f17  jz      short loc_180011F36
0x180011f19  test    byte ptr [rcx+1Ch], 1
0x180011f1d  jz      short loc_180011F36
0x180011f1f  mov     rcx, [rcx+10h]
0x180011f23  lea     edx, [r13+1Fh]
0x180011f27  mov     r9d, eax
0x180011f2a  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x180011f31  call    WPP_SF_d
0x180011f36  mov     rcx, [rsp+510h+hObject]; hObject
0x180011f3b  cmp     rcx, r13
0x180011f3e  jz      short loc_180011F46
0x180011f40  call    cs:__imp_CloseHandle
0x180011f46  test    rbx, rbx
0x180011f49  jz      short loc_180011F53
0x180011f4b  mov     rcx, rbx; void *
0x180011f4e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011f53  mov     eax, edi
0x180011f55  mov     rcx, [rbp+410h+var_50]
0x180011f5c  xor     rcx, rsp; StackCookie
0x180011f5f  call    __security_check_cookie
0x180011f64  add     rsp, 4D8h
0x180011f6b  pop     r15
0x180011f6d  pop     r14
0x180011f6f  pop     r13
0x180011f71  pop     r12
0x180011f73  pop     rdi
0x180011f74  pop     rsi
0x180011f75  pop     rbx
0x180011f76  pop     rbp
0x180011f77  retn
0x180011f78  mov     rdi, [rsp+510h+hObject]
0x180011f7d  lea     rdx, [rsp+510h+FileSize]; lpFileSize
0x180011f82  mov     rcx, rdi; hFile
0x180011f85  mov     qword ptr [rsp+510h+FileSize], r15
0x180011f8a  call    cs:__imp_GetFileSizeEx
0x180011f90  test    eax, eax
0x180011f92  jnz     loc_180012028
0x180011f98  call    HrGetLastFailure
0x180011f9d  mov     esi, eax
0x180011f9f  mov     dword ptr [rsp+510h+hObject], eax
0x180011fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011faa  lea     r14, WPP_GLOBAL_Control
0x180011fb1  cmp     rcx, r14
0x180011fb4  jz      short loc_180011FDB
0x180011fb6  test    byte ptr [rcx+1Ch], 1
0x180011fba  jz      short loc_180011FDB
0x180011fbc  mov     rcx, [rcx+10h]
0x180011fc0  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x180011fc7  mov     edx, 2Dh ; '-'
0x180011fcc  mov     r9d, eax
0x180011fcf  call    WPP_SF_d
0x180011fd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011fdb  test    esi, esi
0x180011fdd  jns     loc_180012073
0x180011fe3  cmp     rcx, r14
0x180011fe6  jz      short loc_180012006
0x180011fe8  test    byte ptr [rcx+1Ch], 1
0x180011fec  jz      short loc_180012006
0x180011fee  mov     rcx, [rcx+10h]
0x180011ff2  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x180011ff9  mov     edx, 1Fh
0x180011ffe  mov     r9d, esi
0x180012001  call    WPP_SF_d
0x180012006  cmp     rdi, r13
0x180012009  jz      short loc_180012014
0x18001200b  mov     rcx, rdi; hObject
0x18001200e  call    cs:__imp_CloseHandle
0x180012014  test    rbx, rbx
0x180012017  jz      short loc_180012021
0x180012019  mov     rcx, rbx; void *
0x18001201c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012021  mov     eax, esi
0x180012023  jmp     loc_180011F55
0x180012028  cmp     qword ptr [rsp+510h+FileSize], 800h
0x180012031  mov     esi, r15d
0x180012034  mov     dword ptr [rsp+510h+hObject], r15d
0x180012039  jbe     short loc_180012073
0x18001203b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012042  lea     r14, WPP_GLOBAL_Control
0x180012049  cmp     rcx, r14
0x18001204c  jz      short loc_180012006
0x18001204e  test    byte ptr [rcx+1Ch], 1
0x180012052  jz      short loc_180012006
0x180012054  mov     rcx, [rcx+10h]
0x180012058  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x18001205f  mov     edx, 20h ; ' '
0x180012064  mov     [rsp+510h+nSize], r15d
0x180012069  mov     r9, rbx
0x18001206c  call    WPP_SF_Sd
0x180012071  jmp     short loc_180012006
0x180012073  lea     rsi, Default; "n/a"
0x18001207a  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x18001207f  lea     r14, AppName; "Products"
0x180012086  mov     [rbp+410h+var_488], r15
0x18001208a  mov     r8, rsi; lpDefault
0x18001208d  mov     [rbp+410h+var_490], r15
0x180012091  mov     rcx, r14; lpAppName
0x180012094  mov     [rsp+510h+var_498], r15
0x180012099  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x18001209d  mov     [rsp+510h+var_4A0], r15
0x1800120a2  lea     rdx, KeyName; "Name"
0x1800120a9  mov     [rsp+510h+var_4A8], r15
0x1800120ae  mov     qword ptr [rsp+510h+FileSize], r15
0x1800120b3  mov     [rsp+510h+var_4B0], r15
0x1800120b8  mov     [rsp+510h+nSize], r12d; nSize
0x1800120bd  call    cs:__imp_GetPrivateProfileStringW
0x1800120c3  mov     eax, eax
0x1800120c5  mov     r13d, 20Ah
0x1800120cb  lea     rcx, [rax+rax]
0x1800120cf  cmp     rcx, r13
0x1800120d2  jnb     loc_18001239C
0x1800120d8  mov     [rbp+rcx+410h+ReturnedString], r15w
0x1800120de  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x1800120e2  lea     rcx, [rbp+410h+var_488]; this
0x1800120e6  lea     rdx, aNameLs; " , Name : %ls"
0x1800120ed  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800120f2  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x1800120f6  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x1800120fb  mov     r8, rsi; lpDefault
0x1800120fe  mov     [rsp+510h+nSize], r12d; nSize
0x180012103  lea     rdx, aCompany; "Company"
0x18001210a  mov     rcx, r14; lpAppName
0x18001210d  call    cs:__imp_GetPrivateProfileStringW
0x180012113  mov     eax, eax
0x180012115  lea     rcx, [rax+rax]
0x180012119  cmp     rcx, r13
0x18001211c  jnb     loc_18001239C
0x180012122  mov     [rbp+rcx+410h+ReturnedString], r15w
0x180012128  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x18001212c  lea     rcx, [rbp+410h+var_490]; this
0x180012130  lea     rdx, aCompanyLs; "Company : %ls"
0x180012137  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18001213c  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x180012140  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x180012145  mov     r8, rsi; lpDefault
0x180012148  mov     [rsp+510h+nSize], r12d; nSize
0x18001214d  lea     rdx, aPathtosignedre; "PathToSignedReportingExe"
0x180012154  mov     rcx, r14; lpAppName
0x180012157  call    cs:__imp_GetPrivateProfileStringW
0x18001215d  mov     eax, eax
0x18001215f  lea     rcx, [rax+rax]
0x180012163  cmp     rcx, r13
0x180012166  jnb     loc_18001239C
0x18001216c  mov     [rbp+rcx+410h+ReturnedString], r15w
0x180012172  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x180012176  lea     rcx, [rsp+510h+var_498]; this
0x18001217b  lea     rdx, aPathtosignedre_0; "PathToSignedReportingExe : %ls"
0x180012182  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180012187  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x18001218b  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x180012190  mov     r8, rsi; lpDefault
0x180012193  mov     [rsp+510h+nSize], r12d; nSize
0x180012198  lea     rdx, aVersion; "Version"
0x18001219f  mov     rcx, r14; lpAppName
0x1800121a2  call    cs:__imp_GetPrivateProfileStringW
0x1800121a8  mov     eax, eax
0x1800121aa  lea     rcx, [rax+rax]
0x1800121ae  cmp     rcx, r13
0x1800121b1  jnb     loc_18001239C
0x1800121b7  mov     [rbp+rcx+410h+ReturnedString], r15w
0x1800121bd  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x1800121c1  lea     rcx, [rsp+510h+var_4A0]; this
0x1800121c6  lea     rdx, aVersionLs; "Version : %ls"
0x1800121cd  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800121d2  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x1800121d6  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x1800121db  mov     r8, rsi; lpDefault
0x1800121de  mov     [rsp+510h+nSize], r12d; nSize
0x1800121e3  lea     rdx, aEnvironment; "Environment"
0x1800121ea  mov     rcx, r14; lpAppName
0x1800121ed  call    cs:__imp_GetPrivateProfileStringW
0x1800121f3  mov     eax, eax
0x1800121f5  lea     rcx, [rax+rax]
0x1800121f9  cmp     rcx, r13
0x1800121fc  jnb     loc_18001239C
0x180012202  mov     [rbp+rcx+410h+ReturnedString], r15w
0x180012208  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x18001220c  lea     rcx, [rsp+510h+var_4A8]; this
0x180012211  lea     rdx, aEnvironmentLs; "Environment : %ls"
0x180012218  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18001221d  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x180012221  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x180012226  mov     r8, rsi; lpDefault
0x180012229  mov     [rsp+510h+nSize], r12d; nSize
0x18001222e  lea     rdx, aRuntimePlatfor; "Runtime_platform"
0x180012235  mov     rcx, r14; lpAppName
0x180012238  call    cs:__imp_GetPrivateProfileStringW
0x18001223e  mov     eax, eax
0x180012240  lea     rdx, [rax+rax]
0x180012244  cmp     rdx, r13
0x180012247  jnb     loc_18001239C
0x18001224d  mov     [rbp+rdx+410h+ReturnedString], r15w
0x180012253  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x180012257  lea     rdx, aRuntimePlatfor_0; "Runtime_platform : %ls"
0x18001225e  lea     rcx, [rsp+510h+FileSize]; this
0x180012263  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180012268  lea     r9, [rbp+410h+ReturnedString]; lpReturnedString
0x18001226c  mov     [rsp+510h+lpFileName], rbx; lpFileName
0x180012271  mov     r8, rsi; lpDefault
0x180012274  mov     [rsp+510h+nSize], r12d; nSize
0x180012279  lea     rdx, aUpgrade; "Upgrade"
0x180012280  mov     rcx, r14; lpAppName
0x180012283  call    cs:__imp_GetPrivateProfileStringW
0x180012289  mov     eax, eax
0x18001228b  lea     rcx, [rax+rax]
0x18001228f  cmp     rcx, r13
0x180012292  jnb     loc_18001239C
0x180012298  mov     [rbp+rcx+410h+ReturnedString], r15w
0x18001229e  lea     r8, [rbp+410h+ReturnedString]; unsigned __int16 *
0x1800122a2  lea     rcx, [rsp+510h+var_4B0]; this
0x1800122a7  lea     rdx, aUpgradeLs; "Upgrade : %ls"
0x1800122ae  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800122b3  mov     rax, [rsp+510h+var_4B0]
0x1800122b8  lea     rdx, aLsLsLsLsLsLsLs; "%ls , %ls , %ls , %ls , %ls , %ls , %ls"
0x1800122bf  mov     r13, [rsp+510h+var_4A8]
0x1800122c4  lea     rcx, [rbp+410h+var_480]; this
0x1800122c8  mov     r12, [rsp+510h+var_4A0]
0x1800122cd  mov     r14, [rbp+410h+var_490]
0x1800122d1  mov     rsi, [rbp+410h+var_488]
0x1800122d5  mov     r9, r14
0x1800122d8  mov     [rsp+510h+var_4D0], rax
0x1800122dd  mov     r8, rsi; unsigned __int16 *
0x1800122e0  mov     rax, qword ptr [rsp+510h+FileSize]
0x1800122e5  mov     [rsp+510h+var_4D8], rax
0x1800122ea  mov     [rbp+410h+var_480], r15
0x1800122ee  mov     r15, [rsp+510h+var_498]
0x1800122f3  mov     [rsp+510h+var_4E0], r13
0x1800122f8  mov     [rsp+510h+lpFileName], r12
0x1800122fd  mov     qword ptr [rsp+510h+nSize], r15
0x180012302  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x180012307  mov     rax, [rbp+410h+var_480]
0x18001230b  mov     rcx, [rbp+410h+var_478]
0x18001230f  mov     [rcx], rax
0x180012312  mov     rax, [rsp+510h+var_4B0]
0x180012317  test    rax, rax
0x18001231a  jz      short loc_180012324
0x18001231c  mov     rcx, rax; void *
0x18001231f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180012324  mov     rax, qword ptr [rsp+510h+FileSize]
  ... truncated ...
```
