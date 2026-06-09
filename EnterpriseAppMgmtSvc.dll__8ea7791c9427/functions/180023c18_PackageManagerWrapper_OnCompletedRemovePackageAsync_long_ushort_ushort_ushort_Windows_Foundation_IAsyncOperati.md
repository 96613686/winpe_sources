# PackageManagerWrapper::OnCompletedRemovePackageAsync(long,ushort *,ushort *,ushort *,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *)

- ea: `0x180023c18`
- end: `0x1800242b8`
- name: `?OnCompletedRemovePackageAsync@PackageManagerWrapper@@QEAAJJPEAG00PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@Z`
- size: `1696`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180022b00`

## callees

- `0x18000139c`
- `0x1800014e8`
- `0x180005de8`
- `0x18000cfe8`
- `0x18001c5b8`
- `0x180022510`
- `0x180023c18`
- `0x1800273c8`
- `0x18002a32c`
- `0x18002a83c`
- `0x18002dec8`
- `0x180065a64`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180023d75`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023e80`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023f0e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002406a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800240b3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800240f1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002413a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002414e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800241e9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023d75`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023e80`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180023f0e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002406a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800240b3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800240f1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002413a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002414e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800241e9`
- `DMCmnUtils!DmRevertToSelf` at `0x180023d56`
- `DMCmnUtils!DmRevertToSelf` at `0x180023e61`
- `DMCmnUtils!DmRevertToSelf` at `0x180023eef`
- `DMCmnUtils!DmRevertToSelf` at `0x180024094`
- `DMCmnUtils!DmRevertToSelf` at `0x18002411b`
- `DMCmnUtils!DmRevertToSelf` at `0x180023d56`
- `DMCmnUtils!DmRevertToSelf` at `0x180023e61`
- `DMCmnUtils!DmRevertToSelf` at `0x180023eef`
- `DMCmnUtils!DmRevertToSelf` at `0x180024094`
- `DMCmnUtils!DmRevertToSelf` at `0x18002411b`

## string_xrefs

- `0x180023d8c`: `Reversed-Domain-Name:com.microsoft.mdm.%s.result`
- `0x180023d85`: `EnterpriseAppUninstall`
- `0x180023cb2`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180023ccc`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180023dea`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180023dbc`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180023e2c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180023eba`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180024050`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800240d7`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800241ca`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180024223`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PackageManagerWrapper::OnCompletedRemovePackageAsync(
        __int64 a1,
        int a2,
        WCHAR *a3,
        EnterpriseModernAppManagement *a4,
        unsigned __int16 *Src,
        __int64 a6)
{
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // r8
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  unsigned __int16 *v20; // rcx
  int v22; // eax
  __int64 v23; // rdx
  struct Common::StringBuffer *v24; // r8
  __int64 v25; // r9
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // r8
  int PackageFamilyNameFromFullName; // eax
  HKEY v30; // r8
  struct Common::RegistryKey *v31; // r9
  EnterpriseModernAppManagement *v32; // rdi
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // r8
  int v37; // eax
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // r8
  __int64 v41; // rcx
  int v42; // eax
  unsigned __int16 *v43; // rdi
  int v44; // eax
  unsigned __int16 *v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  EnterpriseModernAppManagement **v47; // [rsp+28h] [rbp-D8h]
  __int64 v48; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v49; // [rsp+48h] [rbp-B8h] BYREF
  int v50[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v51; // [rsp+58h] [rbp-A8h] BYREF
  void **v52; // [rsp+60h] [rbp-A0h] BYREF
  char v53; // [rsp+68h] [rbp-98h]
  __int128 v54; // [rsp+70h] [rbp-90h] BYREF
  int v55; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v56[2]; // [rsp+88h] [rbp-78h] BYREF
  int v57; // [rsp+98h] [rbp-68h]
  EnterpriseModernAppManagement *v58[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v59; // [rsp+B0h] [rbp-50h]
  unsigned int *v60; // [rsp+C0h] [rbp-40h]
  __int64 v61; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v62[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v63[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  if ( a3 && a6 )
  {
    v52 = &ImpersonateUserHelper::`vftable';
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v9 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v54, Src);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v15 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v52);
      v10 = v15;
      if ( v15 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
          (const char *)(unsigned int)v15,
          (int)v45);
      if ( (v10 & 0x80000000) == 0 )
      {
        v48 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a6 + 80LL))(a6, &v48);
        v10 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x45E,
            (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v16);
          v17 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
          if ( v53 )
          {
            v18 = DmRevertToSelf();
            if ( v18 < 0 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x4B,
                v19,
                (const char *)(unsigned int)v18,
                (int)v45);
          }
          v20 = (unsigned __int16 *)*((_QWORD *)&v54 + 1);
          if ( !*((_QWORD *)&v54 + 1) )
            return v10;
          goto LABEL_26;
        }
        *(_OWORD *)v56 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v48 + 56LL))(v48, v56);
        v10 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x461,
            (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v22);
          v26 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( v53 )
          {
            v27 = DmRevertToSelf();
            if ( v27 < 0 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x4B,
                v28,
                (const char *)(unsigned int)v27,
                (int)v45);
          }
          if ( *((_QWORD *)&v54 + 1) )
            operator delete[](*((void **)&v54 + 1));
          return v10;
        }
        if ( a2 >= 0 )
        {
          if ( (unsigned int)dword_18008F0A0 > 5
            && (qword_18008F0B0 & 0x400000000000LL) != 0
            && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
          {
            v51 = v56;
            v49 = a2;
            *(_QWORD *)v50 = a3;
            v47 = (EnterpriseModernAppManagement **)&v49;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              0x400000000000LL,
              (__int64)byte_180082563,
              (__int64)v24,
              v25,
              v50);
          }
          *(_OWORD *)v58 = 0;
          v59 = 0;
          PackageFamilyNameFromFullName = EnterpriseModernAppManagement::GetPackageFamilyNameFromFullName(
                                            a3,
                                            (Common::StringBuffer *)v58,
                                            v24);
          v32 = v58[1];
          if ( PackageFamilyNameFromFullName < 0 )
          {
            v37 = EnterpriseModernAppManagement::DeleteProductIDKey(
                    (EnterpriseModernAppManagement *)a3,
                    (const unsigned __int16 *)0xFFFFFFFF80000001LL,
                    v30,
                    v31);
            v10 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x475,
                (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
                (const char *)(unsigned int)v37);
              if ( v32 )
                operator delete[](v32);
              v38 = v48;
              if ( v48 )
              {
                v48 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              }
              if ( v53 )
              {
                v39 = DmRevertToSelf();
                if ( v39 < 0 )
                  wil::details::in1diag3::_FailFast_Hr(
                    retaddr,
                    (void *)0x4B,
                    v40,
                    (const char *)(unsigned int)v39,
                    (int)v45);
              }
              if ( *((_QWORD *)&v54 + 1) )
                operator delete[](*((void **)&v54 + 1));
              return v10;
            }
          }
          else
          {
            v33 = EnterpriseModernAppManagement::DeleteProductIDKey(
                    v58[1],
                    (const unsigned __int16 *)0xFFFFFFFF80000001LL,
                    v30,
                    v31);
            v10 = v33;
            if ( v33 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x470,
                (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
                (const char *)(unsigned int)v33);
              if ( v32 )
                operator delete[](v32);
              v34 = v48;
              if ( v48 )
              {
                v48 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              }
              if ( v53 )
              {
                v35 = DmRevertToSelf();
                if ( v35 < 0 )
                  wil::details::in1diag3::_FailFast_Hr(
                    retaddr,
                    (void *)0x4B,
                    v36,
                    (const char *)(unsigned int)v35,
                    (int)v45);
              }
              if ( *((_QWORD *)&v54 + 1) )
                operator delete[](*((void **)&v54 + 1));
              return v10;
            }
          }
          if ( v32 )
            operator delete[](v32);
        }
        else if ( (unsigned int)dword_18008F0A0 > 5 )
        {
          v23 = qword_18008F0B8;
          if ( (qword_18008F0B0 & 0x400000000000LL) != 0 && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
          {
            *(_QWORD *)v50 = v56;
            v49 = a2;
            v51 = (unsigned __int16 **)a3;
            v47 = (EnterpriseModernAppManagement **)&v49;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              0x400000000000LL,
              (__int64)byte_180082713,
              (__int64)v24,
              v25,
              &v51);
          }
        }
        v41 = v48;
        if ( v48 )
        {
          v48 = 0;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v41 + 16LL))(v41, v23);
        }
LABEL_9:
        if ( v53 )
        {
          v11 = DmRevertToSelf();
          if ( v11 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v12, (const char *)(unsigned int)v11, (int)v45);
        }
        if ( *((_QWORD *)&v54 + 1) )
          operator delete[](*((void **)&v54 + 1));
        if ( !a4 )
          return v10;
        v10 = StringCchPrintfW(
                v63,
                0x105u,
                L"Reversed-Domain-Name:com.microsoft.mdm.%s.result",
                L"EnterpriseAppUninstall");
        v13 = retaddr;
        if ( (v10 & 0x80000000) != 0 )
        {
          v14 = 1157;
LABEL_16:
          wil::details::in1diag3::_Log_Hr(
            v13,
            (void *)v14,
            (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)v10);
          return v10;
        }
        v10 = StringCchPrintfW(v62, 0x105u, L"./User/Vendor/MSFT/EnterpriseModernAppManagement/AppManagement/%s", a3);
        v13 = retaddr;
        if ( (v10 & 0x80000000) != 0 )
        {
          v14 = 1161;
          goto LABEL_16;
        }
        *(_OWORD *)v56 = 0;
        v57 = 0;
        v42 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v56, Src);
        v10 = v42;
        if ( v42 >= 0 )
        {
          v43 = v56[1];
          LODWORD(v45) = a2;
          v44 = EnterpriseModernAppManagement::SendOmaDmAlert(a4, v63, v62, v56[1], v45, (int)v47);
          v10 = v44;
          if ( v44 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x48F,
              (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
              (const char *)(unsigned int)v44);
          if ( !v43 )
            return v10;
          v20 = v43;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x48D,
            (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v42);
          v20 = v56[1];
          if ( !v56[1] )
            return v10;
        }
LABEL_26:
        operator delete[](v20);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
        (const char *)(unsigned int)v9,
        (int)v45);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
        (const char *)v10,
        v46);
    }
    if ( (unsigned int)dword_18008F0A0 > 5
      && (qword_18008F0B0 & 0x400000000000LL) != 0
      && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
    {
      v49 = v10;
      v60 = &v49;
      v61 = 4;
      v47 = v58;
      LODWORD(v45) = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_18008F0A0, &word_1800825AE, 0);
    }
    goto LABEL_9;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180023c18  mov     [rsp-8+arg_0], rbx
0x180023c1d  push    rbp
0x180023c1e  push    rsi
0x180023c1f  push    rdi
0x180023c20  push    r12
0x180023c22  push    r13
0x180023c24  push    r14
0x180023c26  push    r15
0x180023c28  lea     rbp, [rsp-400h]
0x180023c30  sub     rsp, 500h
0x180023c37  mov     rax, cs:__security_cookie
0x180023c3e  xor     rax, rsp
0x180023c41  mov     [rbp+430h+var_40], rax
0x180023c48  mov     r15, r9
0x180023c4b  mov     rsi, r8
0x180023c4e  mov     r14d, edx
0x180023c51  mov     r12, [rbp+430h+Src]
0x180023c58  mov     rdi, [rbp+430h+arg_28]
0x180023c5f  xor     r13d, r13d
0x180023c62  test    r8, r8
0x180023c65  jz      loc_180024243
0x180023c6b  test    rdi, rdi
0x180023c6e  jz      loc_180024243
0x180023c74  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x180023c7b  mov     [rsp+530h+var_4D0], rax
0x180023c80  mov     [rsp+530h+var_4C8], r13b
0x180023c85  xorps   xmm0, xmm0
0x180023c88  movups  [rsp+530h+var_4C0], xmm0
0x180023c8d  mov     [rbp+430h+var_4B0], r13d
0x180023c91  mov     rdx, r12; Src
0x180023c94  lea     rcx, [rsp+530h+var_4C0]; this
0x180023c99  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180023c9e  mov     ebx, eax
0x180023ca0  test    eax, eax
0x180023ca2  jns     loc_180023DD0
0x180023ca8  mov     rcx, [rbp+438h]; this
0x180023caf  mov     r9d, eax; char *
0x180023cb2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023cb9  lea     edx, [r13+52h]; void *
0x180023cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cc2  mov     rcx, [rbp+438h]; this
0x180023cc9  mov     r9d, ebx; char *
0x180023ccc  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023cd3  lea     edx, [r13+43h]; void *
0x180023cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023cdc  mov     eax, cs:dword_18008F0A0
0x180023ce2  cmp     eax, 5
0x180023ce5  jbe     short loc_180023D4F
0x180023ce7  mov     rdx, cs:qword_18008F0B8
0x180023cee  mov     rax, cs:qword_18008F0B0
0x180023cf5  mov     rcx, 400000000000h
0x180023cff  test    rcx, rax
0x180023d02  jz      short loc_180023D4F
0x180023d04  mov     rax, rdx
0x180023d07  and     rax, rcx
0x180023d0a  cmp     rax, rdx
0x180023d0d  jnz     short loc_180023D4F
0x180023d0f  mov     [rsp+530h+var_4E8], ebx
0x180023d13  lea     rax, [rsp+530h+var_4E8]
0x180023d18  mov     [rbp+430h+var_470], rax
0x180023d1c  mov     [rbp+430h+var_468], 4
0x180023d24  lea     rax, [rbp+430h+var_490]
0x180023d28  mov     qword ptr [rsp+530h+var_508], rax; int
0x180023d2d  mov     dword ptr [rsp+530h+var_510], 3; int
0x180023d35  xor     r9d, r9d
0x180023d38  xor     r8d, r8d
0x180023d3b  lea     rdx, word_1800825AE
0x180023d42  lea     rcx, dword_18008F0A0
0x180023d49  call    _tlgWriteTransfer_EventWriteTransfer
0x180023d4e  nop
0x180023d4f  cmp     [rsp+530h+var_4C8], r13b
0x180023d54  jz      short loc_180023D6B
0x180023d56  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180023d5c  mov     rcx, [rbp+438h]; this
0x180023d63  test    eax, eax
0x180023d65  js      loc_180024280
0x180023d6b  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x180023d70  test    rcx, rcx
0x180023d73  jz      short loc_180023D7C
0x180023d75  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180023d7b  nop
0x180023d7c  test    r15, r15
0x180023d7f  jz      loc_180023E87
0x180023d85  lea     r9, ?c_EnterpriseAppUninstall@EnterpriseModernAppManagement@@3QBGB; "EnterpriseAppUninstall"
0x180023d8c  lea     r8, ?c_AlertTypeFormat@EnterpriseModernAppManagement@@3QBGB; "Reversed-Domain-Name:com.microsoft.mdm."...
0x180023d93  mov     edi, 105h
0x180023d98  mov     edx, edi; unsigned __int64
0x180023d9a  lea     rcx, [rbp+430h+var_250]; unsigned __int16 *
0x180023da1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023da6  mov     ebx, eax
0x180023da8  mov     rcx, [rbp+438h]; this
0x180023daf  test    eax, eax
0x180023db1  jns     loc_180024176
0x180023db7  mov     edx, 485h; void *
0x180023dbc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023dc3  mov     r9d, ebx; char *
0x180023dc6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023dcb  jmp     loc_180023E87
0x180023dd0  lea     rcx, [rsp+530h+var_4D0]; this
0x180023dd5  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x180023dda  mov     ebx, eax
0x180023ddc  test    eax, eax
0x180023dde  jns     short loc_180023DFB
0x180023de0  mov     rcx, [rbp+438h]; this
0x180023de7  mov     r9d, eax; char *
0x180023dea  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023df1  mov     edx, 44h ; 'D'; void *
0x180023df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023dfb  test    ebx, ebx
0x180023dfd  js      loc_180023CDC
0x180023e03  mov     [rsp+530h+var_4F0], r13
0x180023e08  mov     rax, [rdi]
0x180023e0b  lea     rdx, [rsp+530h+var_4F0]
0x180023e10  mov     rcx, rdi
0x180023e13  mov     rax, [rax+50h]
0x180023e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1c  mov     ebx, eax
0x180023e1e  mov     rcx, [rbp+438h]; this
0x180023e25  test    eax, eax
0x180023e27  jns     short loc_180023E8E
0x180023e29  mov     r9d, eax; char *
0x180023e2c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023e33  mov     edx, 45Eh; void *
0x180023e38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023e3d  nop
0x180023e3e  mov     rcx, [rsp+530h+var_4F0]
0x180023e43  test    rcx, rcx
0x180023e46  jz      short loc_180023E5A
0x180023e48  mov     [rsp+530h+var_4F0], r13
0x180023e4d  mov     rax, [rcx]
0x180023e50  mov     rax, [rax+10h]
0x180023e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e59  nop
0x180023e5a  cmp     [rsp+530h+var_4C8], r13b
0x180023e5f  jz      short loc_180023E76
0x180023e61  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180023e67  mov     rcx, [rbp+438h]; this
0x180023e6e  test    eax, eax
0x180023e70  js      loc_18002428E
0x180023e76  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x180023e7b  test    rcx, rcx
0x180023e7e  jz      short loc_180023E87
0x180023e80  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180023e86  nop
0x180023e87  mov     eax, ebx
0x180023e89  jmp     loc_180024248
0x180023e8e  xorps   xmm0, xmm0
0x180023e91  movups  xmmword ptr [rbp+430h+var_4A8], xmm0
0x180023e95  mov     rcx, [rsp+530h+var_4F0]
0x180023e9a  mov     rax, [rcx]
0x180023e9d  lea     rdx, [rbp+430h+var_4A8]
0x180023ea1  mov     rax, [rax+38h]
0x180023ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eaa  mov     ebx, eax
0x180023eac  mov     rcx, [rbp+438h]; this
0x180023eb3  test    eax, eax
0x180023eb5  jns     short loc_180023F1A
0x180023eb7  mov     r9d, eax; char *
0x180023eba  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180023ec1  mov     edx, 461h; void *
0x180023ec6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023ecb  nop
0x180023ecc  mov     rcx, [rsp+530h+var_4F0]
0x180023ed1  test    rcx, rcx
0x180023ed4  jz      short loc_180023EE8
0x180023ed6  mov     [rsp+530h+var_4F0], r13
0x180023edb  mov     rax, [rcx]
0x180023ede  mov     rax, [rax+10h]
0x180023ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ee7  nop
0x180023ee8  cmp     [rsp+530h+var_4C8], r13b
0x180023eed  jz      short loc_180023F04
0x180023eef  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180023ef5  mov     rcx, [rbp+438h]; this
0x180023efc  test    eax, eax
0x180023efe  js      loc_18002429C
0x180023f04  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x180023f09  test    rcx, rcx
0x180023f0c  jz      short loc_180023F15
0x180023f0e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180023f14  nop
0x180023f15  jmp     loc_180023E87
0x180023f1a  mov     eax, cs:dword_18008F0A0
0x180023f20  test    r14d, r14d
0x180023f23  jns     short loc_180023FA0
0x180023f25  cmp     eax, 5
0x180023f28  jbe     loc_180024155
0x180023f2e  mov     rdx, cs:qword_18008F0B8
0x180023f35  mov     rax, cs:qword_18008F0B0
0x180023f3c  mov     rcx, 400000000000h
0x180023f46  test    rcx, rax
0x180023f49  jz      loc_180024155
0x180023f4f  mov     rax, rdx
0x180023f52  and     rax, rcx
0x180023f55  cmp     rax, rdx
0x180023f58  jnz     loc_180024155
0x180023f5e  lea     rax, [rbp+430h+var_4A8]
0x180023f62  mov     qword ptr [rsp+530h+var_4E0], rax
0x180023f67  mov     [rsp+530h+var_4E8], r14d
0x180023f6c  mov     [rsp+530h+var_4D8], rsi
0x180023f71  lea     rax, [rsp+530h+var_4E0]
0x180023f76  mov     [rsp+530h+var_500], rax
0x180023f7b  lea     rax, [rsp+530h+var_4E8]
0x180023f80  mov     qword ptr [rsp+530h+var_508], rax
0x180023f85  lea     rax, [rsp+530h+var_4D8]
0x180023f8a  mov     [rsp+530h+var_510], rax
0x180023f8f  lea     rdx, byte_180082713
0x180023f96  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180023f9b  jmp     loc_180024155
0x180023fa0  cmp     eax, 5
0x180023fa3  jbe     short loc_18002400A
0x180023fa5  mov     rdx, cs:qword_18008F0B8
0x180023fac  mov     rax, cs:qword_18008F0B0
0x180023fb3  mov     rcx, 400000000000h
0x180023fbd  test    rcx, rax
0x180023fc0  jz      short loc_18002400A
0x180023fc2  mov     rax, rdx
0x180023fc5  and     rax, rcx
0x180023fc8  cmp     rax, rdx
0x180023fcb  jnz     short loc_18002400A
0x180023fcd  lea     rax, [rbp+430h+var_4A8]
0x180023fd1  mov     [rsp+530h+var_4D8], rax
0x180023fd6  mov     [rsp+530h+var_4E8], r14d
0x180023fdb  mov     qword ptr [rsp+530h+var_4E0], rsi
0x180023fe0  lea     rax, [rsp+530h+var_4D8]
0x180023fe5  mov     [rsp+530h+var_500], rax
0x180023fea  lea     rax, [rsp+530h+var_4E8]
0x180023fef  mov     qword ptr [rsp+530h+var_508], rax
0x180023ff4  lea     rax, [rsp+530h+var_4E0]
0x180023ff9  mov     [rsp+530h+var_510], rax; int
0x180023ffe  lea     rdx, byte_180082563
0x180024005  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18002400a  xorps   xmm0, xmm0
0x18002400d  movups  xmmword ptr [rbp+430h+var_490], xmm0
0x180024011  mov     [rbp+430h+var_480], r13d
0x180024015  lea     rdx, [rbp+430h+var_490]; this
0x180024019  mov     rcx, rsi; packageFullName
0x18002401c  call    ?GetPackageFamilyNameFromFullName@EnterpriseModernAppManagement@@YAJPEBGAEAVStringBuffer@Common@@@Z; EnterpriseModernAppManagement::GetPackageFamilyNameFromFullName(ushort const *,Common::StringBuffer &)
0x180024021  mov     rdi, [rbp+430h+var_490+8]
0x180024025  mov     rdx, 0FFFFFFFF80000001h; unsigned __int16 *
0x18002402c  test    eax, eax
0x18002402e  js      loc_1800240BF
0x180024034  mov     rcx, rdi; this
0x180024037  call    ?DeleteProductIDKey@EnterpriseModernAppManagement@@YAJPEBGPEAUHKEY__@@@Z; EnterpriseModernAppManagement::DeleteProductIDKey(ushort const *,HKEY__ *)
0x18002403c  mov     ebx, eax
0x18002403e  mov     rcx, [rbp+438h]; this
0x180024045  test    eax, eax
0x180024047  jns     loc_180024146
0x18002404d  mov     r9d, eax; char *
0x180024050  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180024057  mov     edx, 470h; void *
0x18002405c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024061  nop
0x180024062  test    rdi, rdi
0x180024065  jz      short loc_180024071
0x180024067  mov     rcx, rdi
0x18002406a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180024070  nop
0x180024071  mov     rcx, [rsp+530h+var_4F0]
0x180024076  test    rcx, rcx
0x180024079  jz      short loc_18002408D
0x18002407b  mov     [rsp+530h+var_4F0], r13
0x180024080  mov     rax, [rcx]
0x180024083  mov     rax, [rax+10h]
0x180024087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002408c  nop
0x18002408d  cmp     [rsp+530h+var_4C8], r13b
0x180024092  jz      short loc_1800240A9
0x180024094  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18002409a  mov     rcx, [rbp+438h]; this
0x1800240a1  test    eax, eax
0x1800240a3  js      loc_1800242AA
0x1800240a9  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x1800240ae  test    rcx, rcx
0x1800240b1  jz      short loc_1800240BA
0x1800240b3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800240b9  nop
0x1800240ba  jmp     loc_180023E87
0x1800240bf  mov     rcx, rsi; this
0x1800240c2  call    ?DeleteProductIDKey@EnterpriseModernAppManagement@@YAJPEBGPEAUHKEY__@@@Z; EnterpriseModernAppManagement::DeleteProductIDKey(ushort const *,HKEY__ *)
0x1800240c7  mov     ebx, eax
0x1800240c9  mov     rcx, [rbp+438h]; this
0x1800240d0  test    eax, eax
0x1800240d2  jns     short loc_180024146
0x1800240d4  mov     r9d, eax; char *
0x1800240d7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800240de  mov     edx, 475h; void *
0x1800240e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800240e8  nop
0x1800240e9  test    rdi, rdi
0x1800240ec  jz      short loc_1800240F8
0x1800240ee  mov     rcx, rdi
0x1800240f1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800240f7  nop
0x1800240f8  mov     rcx, [rsp+530h+var_4F0]
0x1800240fd  test    rcx, rcx
0x180024100  jz      short loc_180024114
0x180024102  mov     [rsp+530h+var_4F0], r13
0x180024107  mov     rax, [rcx]
0x18002410a  mov     rax, [rax+10h]
  ... truncated ...
```
