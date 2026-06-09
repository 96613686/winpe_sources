# PackageManagerWrapper::OnCompletedRemovePackageAsync(long,ushort *,ushort *,ushort *,Windows::Foundation::IAsyncOperationWithProgress<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress> *)

- ea: `0x1800255ec`
- end: `0x180025ce5`
- name: `?OnCompletedRemovePackageAsync@PackageManagerWrapper@@QEAAJJPEAG00PEAU?$IAsyncOperationWithProgress@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@@Z`
- size: `1785`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800243b0`

## callees

- `0x1800013a0`
- `0x1800014f0`
- `0x180005ff4`
- `0x18000d3dc`
- `0x18001d65c`
- `0x180023d74`
- `0x1800255ec`
- `0x180029444`
- `0x18002c594`
- `0x18002cb08`
- `0x180030780`
- `0x18006b444`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002574f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025866`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025900`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025a62`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025ab7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025aff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025b54`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025b6e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025c0f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002574f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025866`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025900`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025a62`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025ab7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025aff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025b54`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025b6e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180025c0f`
- `DMCmnUtils!DmRevertToSelf` at `0x18002572a`
- `DMCmnUtils!DmRevertToSelf` at `0x180025841`
- `DMCmnUtils!DmRevertToSelf` at `0x1800258db`
- `DMCmnUtils!DmRevertToSelf` at `0x180025a92`
- `DMCmnUtils!DmRevertToSelf` at `0x180025b2f`
- `DMCmnUtils!DmRevertToSelf` at `0x18002572a`
- `DMCmnUtils!DmRevertToSelf` at `0x180025841`
- `DMCmnUtils!DmRevertToSelf` at `0x1800258db`
- `DMCmnUtils!DmRevertToSelf` at `0x180025a92`
- `DMCmnUtils!DmRevertToSelf` at `0x180025b2f`

## string_xrefs

- `0x18002576c`: `Reversed-Domain-Name:com.microsoft.mdm.%s.result`
- `0x180025765`: `EnterpriseAppUninstall`
- `0x180025686`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x1800256a0`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x1800257ca`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x18002579c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002580c`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800258a6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180025a48`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180025ae5`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180025bf0`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180025c4f`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

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
  unsigned int v12; // r8d
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // r8d
  unsigned __int16 *v20; // rcx
  int v22; // eax
  __int64 v23; // rdx
  struct Common::StringBuffer *v24; // r8
  int v25; // r9d
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // r8d
  int PackageFamilyNameFromFullName; // eax
  HKEY v30; // r8
  EnterpriseModernAppManagement *v31; // rdi
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // r8d
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v39; // r8d
  __int64 v40; // rcx
  int v41; // eax
  unsigned __int16 *v42; // rdi
  int v43; // eax
  unsigned __int16 *v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  EnterpriseModernAppManagement **v51; // [rsp+28h] [rbp-D8h]
  __int64 v52; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v53; // [rsp+48h] [rbp-B8h] BYREF
  int v54[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v55; // [rsp+58h] [rbp-A8h] BYREF
  void **v56; // [rsp+60h] [rbp-A0h] BYREF
  char v57; // [rsp+68h] [rbp-98h]
  __int128 v58; // [rsp+70h] [rbp-90h] BYREF
  int v59; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v60[2]; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+98h] [rbp-68h]
  EnterpriseModernAppManagement *v62[2]; // [rsp+A0h] [rbp-60h] BYREF
  int v63; // [rsp+B0h] [rbp-50h]
  unsigned int *v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v66[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v67[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  if ( a3 && a6 )
  {
    v56 = &ImpersonateUserHelper::`vftable';
    v57 = 0;
    v58 = 0;
    v59 = 0;
    v9 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v58, Src);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v15 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v56);
      v10 = v15;
      if ( v15 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
          (const char *)(unsigned int)v15,
          (int)v44);
      if ( (v10 & 0x80000000) == 0 )
      {
        v52 = 0;
        v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a6 + 80LL))(a6, &v52);
        v10 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x45E,
            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v16,
            (int)v44);
          v17 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          }
          if ( v57 )
          {
            v18 = DmRevertToSelf();
            if ( v18 < 0 )
              wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v19, (const char *)(unsigned int)v18, v46);
          }
          v20 = (unsigned __int16 *)*((_QWORD *)&v58 + 1);
          if ( !*((_QWORD *)&v58 + 1) )
            return v10;
          goto LABEL_26;
        }
        *(_OWORD *)v60 = 0;
        v22 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v52 + 56LL))(v52, v60);
        v10 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x461,
            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v22,
            (int)v44);
          v26 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( v57 )
          {
            v27 = DmRevertToSelf();
            if ( v27 < 0 )
              wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v28, (const char *)(unsigned int)v27, v47);
          }
          if ( *((_QWORD *)&v58 + 1) )
            operator delete[](*((void **)&v58 + 1));
          return v10;
        }
        if ( a2 >= 0 )
        {
          if ( (unsigned int)dword_1800950A0 > 5
            && (qword_1800950B0 & 0x400000000000LL) != 0
            && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
          {
            v55 = v60;
            v53 = a2;
            *(_QWORD *)v54 = a3;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              0,
              (unsigned int)byte_18008856B,
              (_DWORD)v24,
              v25,
              (__int64)v54,
              (__int64)&v53,
              (__int64)&v55);
          }
          *(_OWORD *)v62 = 0;
          v63 = 0;
          PackageFamilyNameFromFullName = EnterpriseModernAppManagement::GetPackageFamilyNameFromFullName(
                                            a3,
                                            (Common::StringBuffer *)v62,
                                            v24);
          v31 = v62[1];
          if ( PackageFamilyNameFromFullName < 0 )
          {
            v36 = EnterpriseModernAppManagement::DeleteProductIDKey(
                    (EnterpriseModernAppManagement *)a3,
                    (const unsigned __int16 *)0xFFFFFFFF80000001LL,
                    v30);
            v10 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x475,
                (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\pa"
                              "ckagemanager.cpp",
                (const char *)(unsigned int)v36,
                (int)v44);
              if ( v31 )
                operator delete[](v31);
              v37 = v52;
              if ( v52 )
              {
                v52 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              }
              if ( v57 )
              {
                v38 = DmRevertToSelf();
                if ( v38 < 0 )
                  wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v39, (const char *)(unsigned int)v38, v49);
              }
              if ( *((_QWORD *)&v58 + 1) )
                operator delete[](*((void **)&v58 + 1));
              return v10;
            }
          }
          else
          {
            v32 = EnterpriseModernAppManagement::DeleteProductIDKey(
                    v62[1],
                    (const unsigned __int16 *)0xFFFFFFFF80000001LL,
                    v30);
            v10 = v32;
            if ( v32 < 0 )
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x470,
                (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\pa"
                              "ckagemanager.cpp",
                (const char *)(unsigned int)v32,
                (int)v44);
              if ( v31 )
                operator delete[](v31);
              v33 = v52;
              if ( v52 )
              {
                v52 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              }
              if ( v57 )
              {
                v34 = DmRevertToSelf();
                if ( v34 < 0 )
                  wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v35, (const char *)(unsigned int)v34, v48);
              }
              if ( *((_QWORD *)&v58 + 1) )
                operator delete[](*((void **)&v58 + 1));
              return v10;
            }
          }
          if ( v31 )
            operator delete[](v31);
        }
        else if ( (unsigned int)dword_1800950A0 > 5 )
        {
          v23 = qword_1800950B8;
          if ( (qword_1800950B0 & 0x400000000000LL) != 0 && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
          {
            *(_QWORD *)v54 = v60;
            v53 = a2;
            v55 = (unsigned __int16 **)a3;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
              0,
              (unsigned int)byte_18008871B,
              (_DWORD)v24,
              v25,
              (__int64)&v55,
              (__int64)&v53,
              (__int64)v54);
          }
        }
        v40 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 16LL))(v40, v23);
        }
LABEL_9:
        if ( v57 )
        {
          v11 = DmRevertToSelf();
          if ( v11 < 0 )
            wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v12, (const char *)(unsigned int)v11, (int)v44);
        }
        if ( *((_QWORD *)&v58 + 1) )
          operator delete[](*((void **)&v58 + 1));
        if ( !a4 )
          return v10;
        v10 = StringCchPrintfW(
                v67,
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
            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)v10,
            (int)v44);
          return v10;
        }
        v10 = StringCchPrintfW(v66, 0x105u, L"./User/Vendor/MSFT/EnterpriseModernAppManagement/AppManagement/%s", a3);
        v13 = retaddr;
        if ( (v10 & 0x80000000) != 0 )
        {
          v14 = 1161;
          goto LABEL_16;
        }
        *(_OWORD *)v60 = 0;
        v61 = 0;
        v41 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v60, Src);
        v10 = v41;
        if ( v41 >= 0 )
        {
          v42 = v60[1];
          LODWORD(v44) = a2;
          v43 = EnterpriseModernAppManagement::SendOmaDmAlert(a4, v67, v66, v60[1], v44, (int)v51);
          v10 = v43;
          if ( v43 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x48F,
              (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
              (const char *)(unsigned int)v43,
              v50);
          if ( !v42 )
            return v10;
          v20 = v42;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x48D,
            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v41,
            (int)v44);
          v20 = v60[1];
          if ( !v60[1] )
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
        (int)v44);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
        (const char *)v10,
        v45);
    }
    if ( (unsigned int)dword_1800950A0 > 5
      && (qword_1800950B0 & 0x400000000000LL) != 0
      && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
    {
      v53 = v10;
      v64 = &v53;
      v65 = 4;
      v51 = v62;
      LODWORD(v44) = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800950A0, &word_1800885B6, 0, 0);
    }
    goto LABEL_9;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800255ec  mov     [rsp-8+arg_0], rbx
0x1800255f1  push    rbp
0x1800255f2  push    rsi
0x1800255f3  push    rdi
0x1800255f4  push    r12
0x1800255f6  push    r13
0x1800255f8  push    r14
0x1800255fa  push    r15
0x1800255fc  lea     rbp, [rsp-400h]
0x180025604  sub     rsp, 500h
0x18002560b  mov     rax, cs:__security_cookie
0x180025612  xor     rax, rsp
0x180025615  mov     [rbp+430h+var_40], rax
0x18002561c  mov     r15, r9
0x18002561f  mov     rsi, r8
0x180025622  mov     r14d, edx
0x180025625  mov     r12, [rbp+430h+Src]
0x18002562c  mov     rdi, [rbp+430h+arg_28]
0x180025633  xor     r13d, r13d
0x180025636  test    r8, r8
0x180025639  jz      loc_180025C6F
0x18002563f  test    rdi, rdi
0x180025642  jz      loc_180025C6F
0x180025648  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x18002564f  mov     [rsp+530h+var_4D0], rax
0x180025654  mov     [rsp+530h+var_4C8], r13b
0x180025659  xorps   xmm0, xmm0
0x18002565c  movups  [rsp+530h+var_4C0], xmm0
0x180025661  mov     [rbp+430h+var_4B0], r13d
0x180025665  mov     rdx, r12; Src
0x180025668  lea     rcx, [rsp+530h+var_4C0]; this
0x18002566d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180025672  mov     ebx, eax
0x180025674  test    eax, eax
0x180025676  jns     loc_1800257B0
0x18002567c  mov     rcx, [rbp+438h]; this
0x180025683  mov     r9d, eax; char *
0x180025686  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002568d  lea     edx, [r13+52h]; void *
0x180025691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025696  mov     rcx, [rbp+438h]; this
0x18002569d  mov     r9d, ebx; char *
0x1800256a0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800256a7  lea     edx, [r13+43h]; void *
0x1800256ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256b0  mov     eax, cs:dword_1800950A0
0x1800256b6  cmp     eax, 5
0x1800256b9  jbe     short loc_180025723
0x1800256bb  mov     rdx, cs:qword_1800950B8
0x1800256c2  mov     rax, cs:qword_1800950B0
0x1800256c9  mov     rcx, 400000000000h
0x1800256d3  test    rcx, rax
0x1800256d6  jz      short loc_180025723
0x1800256d8  mov     rax, rdx
0x1800256db  and     rax, rcx
0x1800256de  cmp     rax, rdx
0x1800256e1  jnz     short loc_180025723
0x1800256e3  mov     [rsp+530h+var_4E8], ebx
0x1800256e7  lea     rax, [rsp+530h+var_4E8]
0x1800256ec  mov     [rbp+430h+var_470], rax
0x1800256f0  mov     [rbp+430h+var_468], 4
0x1800256f8  lea     rax, [rbp+430h+var_490]
0x1800256fc  mov     qword ptr [rsp+530h+var_508], rax; int
0x180025701  mov     dword ptr [rsp+530h+var_510], 3; int
0x180025709  xor     r9d, r9d
0x18002570c  xor     r8d, r8d
0x18002570f  lea     rdx, word_1800885B6
0x180025716  lea     rcx, dword_1800950A0
0x18002571d  call    _tlgWriteTransfer_EventWriteTransfer
0x180025722  nop
0x180025723  cmp     [rsp+530h+var_4C8], r13b
0x180025728  jz      short loc_180025745
0x18002572a  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025731  nop     dword ptr [rax+rax+00h]
0x180025736  mov     rcx, [rbp+438h]; this
0x18002573d  test    eax, eax
0x18002573f  js      loc_180025CAD
0x180025745  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x18002574a  test    rcx, rcx
0x18002574d  jz      short loc_18002575C
0x18002574f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180025756  nop     dword ptr [rax+rax+00h]
0x18002575b  nop
0x18002575c  test    r15, r15
0x18002575f  jz      loc_180025873
0x180025765  lea     r9, ?c_EnterpriseAppUninstall@EnterpriseModernAppManagement@@3QBGB; "EnterpriseAppUninstall"
0x18002576c  lea     r8, ?c_AlertTypeFormat@EnterpriseModernAppManagement@@3QBGB; "Reversed-Domain-Name:com.microsoft.mdm."...
0x180025773  mov     edi, 105h
0x180025778  mov     edx, edi; unsigned __int64
0x18002577a  lea     rcx, [rbp+430h+var_250]; unsigned __int16 *
0x180025781  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025786  mov     ebx, eax
0x180025788  mov     rcx, [rbp+438h]; this
0x18002578f  test    eax, eax
0x180025791  jns     loc_180025B9C
0x180025797  mov     edx, 485h; void *
0x18002579c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800257a3  mov     r9d, ebx; char *
0x1800257a6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800257ab  jmp     loc_180025873
0x1800257b0  lea     rcx, [rsp+530h+var_4D0]; this
0x1800257b5  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x1800257ba  mov     ebx, eax
0x1800257bc  test    eax, eax
0x1800257be  jns     short loc_1800257DB
0x1800257c0  mov     rcx, [rbp+438h]; this
0x1800257c7  mov     r9d, eax; char *
0x1800257ca  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800257d1  mov     edx, 44h ; 'D'; void *
0x1800257d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800257db  test    ebx, ebx
0x1800257dd  js      loc_1800256B0
0x1800257e3  mov     [rsp+530h+var_4F0], r13
0x1800257e8  mov     rax, [rdi]
0x1800257eb  lea     rdx, [rsp+530h+var_4F0]
0x1800257f0  mov     rcx, rdi
0x1800257f3  mov     rax, [rax+50h]
0x1800257f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257fc  mov     ebx, eax
0x1800257fe  mov     rcx, [rbp+438h]; this
0x180025805  test    eax, eax
0x180025807  jns     short loc_18002587A
0x180025809  mov     r9d, eax; char *
0x18002580c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180025813  mov     edx, 45Eh; void *
0x180025818  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002581d  nop
0x18002581e  mov     rcx, [rsp+530h+var_4F0]
0x180025823  test    rcx, rcx
0x180025826  jz      short loc_18002583A
0x180025828  mov     [rsp+530h+var_4F0], r13
0x18002582d  mov     rax, [rcx]
0x180025830  mov     rax, [rax+10h]
0x180025834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025839  nop
0x18002583a  cmp     [rsp+530h+var_4C8], r13b
0x18002583f  jz      short loc_18002585C
0x180025841  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025848  nop     dword ptr [rax+rax+00h]
0x18002584d  mov     rcx, [rbp+438h]; this
0x180025854  test    eax, eax
0x180025856  js      loc_180025CBB
0x18002585c  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x180025861  test    rcx, rcx
0x180025864  jz      short loc_180025873
0x180025866  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002586d  nop     dword ptr [rax+rax+00h]
0x180025872  nop
0x180025873  mov     eax, ebx
0x180025875  jmp     loc_180025C74
0x18002587a  xorps   xmm0, xmm0
0x18002587d  movups  xmmword ptr [rbp+430h+var_4A8], xmm0
0x180025881  mov     rcx, [rsp+530h+var_4F0]
0x180025886  mov     rax, [rcx]
0x180025889  lea     rdx, [rbp+430h+var_4A8]
0x18002588d  mov     rax, [rax+38h]
0x180025891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025896  mov     ebx, eax
0x180025898  mov     rcx, [rbp+438h]; this
0x18002589f  test    eax, eax
0x1800258a1  jns     short loc_180025912
0x1800258a3  mov     r9d, eax; char *
0x1800258a6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800258ad  mov     edx, 461h; void *
0x1800258b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800258b7  nop
0x1800258b8  mov     rcx, [rsp+530h+var_4F0]
0x1800258bd  test    rcx, rcx
0x1800258c0  jz      short loc_1800258D4
0x1800258c2  mov     [rsp+530h+var_4F0], r13
0x1800258c7  mov     rax, [rcx]
0x1800258ca  mov     rax, [rax+10h]
0x1800258ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258d3  nop
0x1800258d4  cmp     [rsp+530h+var_4C8], r13b
0x1800258d9  jz      short loc_1800258F6
0x1800258db  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x1800258e2  nop     dword ptr [rax+rax+00h]
0x1800258e7  mov     rcx, [rbp+438h]; this
0x1800258ee  test    eax, eax
0x1800258f0  js      loc_180025CC9
0x1800258f6  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x1800258fb  test    rcx, rcx
0x1800258fe  jz      short loc_18002590D
0x180025900  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180025907  nop     dword ptr [rax+rax+00h]
0x18002590c  nop
0x18002590d  jmp     loc_180025873
0x180025912  mov     eax, cs:dword_1800950A0
0x180025918  test    r14d, r14d
0x18002591b  jns     short loc_180025998
0x18002591d  cmp     eax, 5
0x180025920  jbe     loc_180025B7B
0x180025926  mov     rdx, cs:qword_1800950B8
0x18002592d  mov     rax, cs:qword_1800950B0
0x180025934  mov     rcx, 400000000000h
0x18002593e  test    rcx, rax
0x180025941  jz      loc_180025B7B
0x180025947  mov     rax, rdx
0x18002594a  and     rax, rcx
0x18002594d  cmp     rax, rdx
0x180025950  jnz     loc_180025B7B
0x180025956  lea     rax, [rbp+430h+var_4A8]
0x18002595a  mov     qword ptr [rsp+530h+var_4E0], rax
0x18002595f  mov     [rsp+530h+var_4E8], r14d
0x180025964  mov     [rsp+530h+var_4D8], rsi
0x180025969  lea     rax, [rsp+530h+var_4E0]
0x18002596e  mov     [rsp+530h+var_500], rax
0x180025973  lea     rax, [rsp+530h+var_4E8]
0x180025978  mov     qword ptr [rsp+530h+var_508], rax
0x18002597d  lea     rax, [rsp+530h+var_4D8]
0x180025982  mov     [rsp+530h+var_510], rax
0x180025987  lea     rdx, byte_18008871B
0x18002598e  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180025993  jmp     loc_180025B7B
0x180025998  cmp     eax, 5
0x18002599b  jbe     short loc_180025A02
0x18002599d  mov     rdx, cs:qword_1800950B8
0x1800259a4  mov     rax, cs:qword_1800950B0
0x1800259ab  mov     rcx, 400000000000h
0x1800259b5  test    rcx, rax
0x1800259b8  jz      short loc_180025A02
0x1800259ba  mov     rax, rdx
0x1800259bd  and     rax, rcx
0x1800259c0  cmp     rax, rdx
0x1800259c3  jnz     short loc_180025A02
0x1800259c5  lea     rax, [rbp+430h+var_4A8]
0x1800259c9  mov     [rsp+530h+var_4D8], rax
0x1800259ce  mov     [rsp+530h+var_4E8], r14d
0x1800259d3  mov     qword ptr [rsp+530h+var_4E0], rsi
0x1800259d8  lea     rax, [rsp+530h+var_4D8]
0x1800259dd  mov     [rsp+530h+var_500], rax
0x1800259e2  lea     rax, [rsp+530h+var_4E8]
0x1800259e7  mov     qword ptr [rsp+530h+var_508], rax
0x1800259ec  lea     rax, [rsp+530h+var_4E0]
0x1800259f1  mov     [rsp+530h+var_510], rax; int
0x1800259f6  lea     rdx, byte_18008856B
0x1800259fd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180025a02  xorps   xmm0, xmm0
0x180025a05  movups  xmmword ptr [rbp+430h+var_490], xmm0
0x180025a09  mov     [rbp+430h+var_480], r13d
0x180025a0d  lea     rdx, [rbp+430h+var_490]; this
0x180025a11  mov     rcx, rsi; packageFullName
0x180025a14  call    ?GetPackageFamilyNameFromFullName@EnterpriseModernAppManagement@@YAJPEBGAEAVStringBuffer@Common@@@Z; EnterpriseModernAppManagement::GetPackageFamilyNameFromFullName(ushort const *,Common::StringBuffer &)
0x180025a19  mov     rdi, [rbp+430h+var_490+8]
0x180025a1d  mov     rdx, 0FFFFFFFF80000001h; unsigned __int16 *
0x180025a24  test    eax, eax
0x180025a26  js      loc_180025AC9
0x180025a2c  mov     rcx, rdi; this
0x180025a2f  call    ?DeleteProductIDKey@EnterpriseModernAppManagement@@YAJPEBGPEAUHKEY__@@@Z; EnterpriseModernAppManagement::DeleteProductIDKey(ushort const *,HKEY__ *)
0x180025a34  mov     ebx, eax
0x180025a36  mov     rcx, [rbp+438h]; this
0x180025a3d  test    eax, eax
0x180025a3f  jns     loc_180025B66
0x180025a45  mov     r9d, eax; char *
0x180025a48  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180025a4f  mov     edx, 470h; void *
0x180025a54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025a59  nop
0x180025a5a  test    rdi, rdi
0x180025a5d  jz      short loc_180025A6F
0x180025a5f  mov     rcx, rdi
0x180025a62  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180025a69  nop     dword ptr [rax+rax+00h]
0x180025a6e  nop
0x180025a6f  mov     rcx, [rsp+530h+var_4F0]
0x180025a74  test    rcx, rcx
0x180025a77  jz      short loc_180025A8B
0x180025a79  mov     [rsp+530h+var_4F0], r13
0x180025a7e  mov     rax, [rcx]
0x180025a81  mov     rax, [rax+10h]
0x180025a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a8a  nop
0x180025a8b  cmp     [rsp+530h+var_4C8], r13b
0x180025a90  jz      short loc_180025AAD
0x180025a92  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180025a99  nop     dword ptr [rax+rax+00h]
0x180025a9e  mov     rcx, [rbp+438h]; this
0x180025aa5  test    eax, eax
0x180025aa7  js      loc_180025CD7
0x180025aad  mov     rcx, qword ptr [rsp+530h+var_4C0+8]
0x180025ab2  test    rcx, rcx
0x180025ab5  jz      short loc_180025AC4
0x180025ab7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180025abe  nop     dword ptr [rax+rax+00h]
0x180025ac3  nop
0x180025ac4  jmp     loc_180025873
0x180025ac9  mov     rcx, rsi; this
0x180025acc  call    ?DeleteProductIDKey@EnterpriseModernAppManagement@@YAJPEBGPEAUHKEY__@@@Z; EnterpriseModernAppManagement::DeleteProductIDKey(ushort const *,HKEY__ *)
0x180025ad1  mov     ebx, eax
0x180025ad3  mov     rcx, [rbp+438h]; this
0x180025ada  test    eax, eax
0x180025adc  jns     loc_180025B66
0x180025ae2  mov     r9d, eax; char *
0x180025ae5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180025aec  mov     edx, 475h; void *
0x180025af1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025af6  nop
0x180025af7  test    rdi, rdi
0x180025afa  jz      short loc_180025B0C
  ... truncated ...
```
