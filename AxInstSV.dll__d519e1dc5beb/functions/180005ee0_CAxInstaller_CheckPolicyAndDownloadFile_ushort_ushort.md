# CAxInstaller::CheckPolicyAndDownloadFile(ushort *,ushort * *)

- ea: `0x180005ee0`
- end: `0x18000636a`
- name: `?CheckPolicyAndDownloadFile@CAxInstaller@@UEAAJPEAGPEAPEAG@Z`
- size: `1162`
- prototype: `__int64 __fastcall(CAxInstaller *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001720`
- `0x1800021b8`
- `0x180003260`
- `0x180005da4`
- `0x180005ee0`
- `0x1800063c4`
- `0x180006518`
- `0x180006e30`
- `0x180006ea0`
- `0x18000725c`
- `0x1800072f4`
- `0x18000d914`
- `0x180011d1c`
- `0x180013460`
- `0x180013f28`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800062d4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800062d4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800062c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006338`
- `OLEAUT32!__imp_SysFreeString` at `0x1800062c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006338`
- `OLEAUT32!__imp_SysStringLen` at `0x180005f80`
- `OLEAUT32!__imp_SysStringLen` at `0x180005f80`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000632d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000632d`
- `ntdll!RtlReleaseResource` at `0x180005fdc`
- `ntdll!RtlReleaseResource` at `0x180005fdc`
- `ntdll!RtlAcquireResourceShared` at `0x180005fa6`
- `ntdll!RtlAcquireResourceShared` at `0x180005fa6`
- `ntdll!RtlNtStatusToDosError` at `0x180006206`
- `ntdll!RtlNtStatusToDosError` at `0x180006206`

## string_xrefs

- `0x18000611d`: `Failed to Re-ACL Verified File for User IE Read with 0x%x`
- `0x180006104`: `Failed to Re-ACL filepath for User and IE Read access. Error 0x%x`

## pseudocode

```c
__int64 __fastcall CAxInstaller::CheckPolicyAndDownloadFile(
        CAxInstaller *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v6; // r14d
  int v7; // esi
  int v8; // ebx
  unsigned int v9; // r9d
  int v10; // eax
  signed int v11; // ebx
  const struct _EVENT_DESCRIPTOR *v12; // rdi
  HWND v13; // rcx
  unsigned int v14; // r9d
  int v15; // eax
  CAxisServHelper *v16; // rcx
  int v17; // eax
  unsigned __int16 *v18; // r9
  int v19; // ebx
  NTSTATUS v20; // eax
  signed int v21; // eax
  int v22; // eax
  CAxisUrlCache *v23; // rbx
  unsigned __int16 **v24; // rax
  unsigned __int16 *v25; // rax
  unsigned int *v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  unsigned int *v29; // [rsp+28h] [rbp-D8h]
  unsigned int v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v33; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v36; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR psz[264]; // [rsp+70h] [rbp-90h] BYREF

  memset_0(psz, 0, 0x208u);
  v6 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v30 = 0;
  v31 = 0;
  LODWORD(bstrString) = 0;
  v36 = 0;
  AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 4u, L"CheckPolicyAndDownloadFile called");
  psz[0] = 0;
  if ( a2 && SysStringLen(a2) )
  {
    if ( a3 )
      *a3 = 0;
    v7 = 1;
    RtlAcquireResourceShared(&Resource, 1u);
    if ( qword_180021B78 || dword_180021B8C || dword_180021B90 || (v8 = 0, dword_180021B98) )
      v8 = 1;
    RtlReleaseResource(&Resource);
    if ( !v8 )
    {
      if ( !*((_DWORD *)this + 176) )
      {
        v12 = &AXISEVENT_ERROR_POLICY_FAIL;
LABEL_63:
        v11 = -2146762748;
        goto LABEL_64;
      }
      v12 = 0;
LABEL_44:
      v7 = 0;
      v11 = CopyFileToTempDir((const unsigned __int16 *)this + 36, *((unsigned __int16 **)this + 80), psz, v9);
      if ( v11 < 0 )
        goto LABEL_60;
LABEL_45:
      v19 = *((_DWORD *)this + 176);
      v20 = LUAGetUserType(*((void **)this + 85), (int *)&bstrString);
      if ( v20 < 0 )
      {
        v21 = RtlNtStatusToDosError(v20);
        v11 = v21;
        if ( v21 > 0 )
          v11 = (unsigned __int16)v21 | 0x80070000;
        goto LABEL_60;
      }
      if ( (!v7 || (((_DWORD)bstrString - 1) & 0xFFFFFFEE) != 0)
        && (((unsigned int)bstrString & 0xFFFFFFEF) != 0 ? v19 : 0) != 0 )
      {
        v22 = CAxInstaller::WinVerifyFile2(this, a2, psz);
      }
      else
      {
        v22 = CAxInstaller::WinVerifyFile(this, a2, psz);
      }
      v11 = v22;
      if ( v22 < 0 )
      {
        v18 = L"WinVerifyFile Failed with 0x%x";
        goto LABEL_55;
      }
LABEL_26:
      v17 = CAxisServHelper::ReStampFileDacl(v16, psz, qword_180021A98);
      v11 = v17;
      if ( v17 >= 0 )
      {
        v23 = (CAxisUrlCache *)*((_QWORD *)this + 87);
        v24 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, psz);
        v11 = CAxisUrlCache::AddUrlEntry(v23, a2, *v24);
        SysFreeString(bstrString);
        if ( v11 >= 0 )
        {
          if ( !a3 || (v25 = SysAllocString(psz), *a3 = v25, v11 = -2147024882, v25) )
            v11 = 0;
        }
LABEL_60:
        if ( !v12 )
          goto LABEL_65;
        goto LABEL_64;
      }
      LODWORD(v27) = v17;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        8u,
        2u,
        L"Failed to Re-ACL filepath for User and IE Read access. Error 0x%x",
        v27);
      v18 = L"Failed to Re-ACL Verified File for User IE Read with 0x%x";
LABEL_55:
      LODWORD(v27) = v11;
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, v18, v27);
      goto LABEL_60;
    }
    v10 = CPolicyCheck::CheckPolicy((CPolicyCheck *)&unk_180021B00, a2, &v36, &v32, &v33, &v34, &v30);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = &AXISEVENT_ERROR_POLICY_FAIL;
      if ( v10 == -2147023728 )
      {
        if ( !*((_DWORD *)this + 176) )
          goto LABEL_63;
        goto LABEL_44;
      }
LABEL_64:
      AxISEvents::GenerateUrlPolicyEvent((AxISEvents *)&qword_180021AD8, v12, a2, v36);
LABEL_65:
      if ( v11 >= 0 )
        goto LABEL_70;
      goto LABEL_68;
    }
    v11 = CAxInstaller::DownloadFileUsingWinHttp(this, a2, psz, v9, v30);
    if ( v11 < 0 )
    {
      v12 = (const struct _EVENT_DESCRIPTOR *)&AXISEVENT_ERROR_DOWNLOAD;
      goto LABEL_64;
    }
    v15 = VerifyTrust(v13, a2, psz, v14, v28, &v31);
    if ( v15 )
    {
      if ( v15 <= 0 )
      {
        v11 = v15;
        if ( (v15 == -2146762496
           || v15 == -2146762495
           || v15 == -2146762487
           || v15 == -2146762486
           || v15 == -2146762484
           || v15 == -2146762483)
          && v34 == 1 )
        {
          v6 = 1;
          v11 = 0;
        }
      }
      else
      {
        v11 = (unsigned __int16)v15 | 0x80070000;
        v15 = v11;
      }
      LODWORD(v29) = v6;
      LODWORD(v27) = v15;
      AxISEvents::DebugMsg(
        (AxISEvents *)&qword_180021AD8,
        8u,
        4u,
        L"VerifyTrust Failed with 0x%x. Will Prompt user %d",
        v27,
        v29);
    }
    else
    {
      if ( !v31 )
      {
        if ( v33 )
        {
          if ( v33 == 1 )
          {
            v6 = 1;
            goto LABEL_25;
          }
          if ( v33 == 2 )
            goto LABEL_25;
        }
        goto LABEL_21;
      }
      if ( !v32 || v32 - 1 >= 2 )
LABEL_21:
        v11 = -2146762748;
    }
    if ( v11 < 0 )
    {
      v12 = (const struct _EVENT_DESCRIPTOR *)&AXISEVENT_ERROR_POLICY;
      goto LABEL_64;
    }
LABEL_25:
    v12 = (const struct _EVENT_DESCRIPTOR *)&AXISEVENT_ERROR_POLICY_SUCCESS;
    if ( !v6 )
      goto LABEL_26;
    goto LABEL_45;
  }
  v11 = -2147024809;
LABEL_68:
  if ( psz[0] )
    DeleteFileW(psz);
LABEL_70:
  SysFreeString(v36);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005ee0  mov     [rsp-8+arg_18], rbx
0x180005ee5  push    rbp
0x180005ee6  push    rsi
0x180005ee7  push    rdi
0x180005ee8  push    r12
0x180005eea  push    r13
0x180005eec  push    r14
0x180005eee  push    r15
0x180005ef0  lea     rbp, [rsp-190h]
0x180005ef8  sub     rsp, 290h
0x180005eff  mov     rax, cs:__security_cookie
0x180005f06  xor     rax, rsp
0x180005f09  mov     [rbp+1C0h+var_40], rax
0x180005f10  mov     r13, r8
0x180005f13  mov     r12, rdx
0x180005f16  mov     r15, rcx
0x180005f19  xor     edx, edx; Val
0x180005f1b  mov     r8d, 208h; Size
0x180005f21  lea     rcx, [rsp+2C0h+psz]; void *
0x180005f26  call    memset_0
0x180005f2b  xor     r14d, r14d
0x180005f2e  lea     r9, aCheckpolicyand; "CheckPolicyAndDownloadFile called"
0x180005f35  lea     rcx, qword_180021AD8; this
0x180005f3c  mov     [rsp+2C0h+var_278], r14d
0x180005f41  mov     [rsp+2C0h+var_274], r14d
0x180005f46  mov     [rsp+2C0h+var_270], r14d
0x180005f4b  lea     edi, [r14+4]
0x180005f4f  mov     [rsp+2C0h+var_280], r14d
0x180005f54  mov     r8d, edi; unsigned __int8
0x180005f57  mov     [rsp+2C0h+var_27C], r14d
0x180005f5c  lea     edx, [rdi+4]; unsigned int
0x180005f5f  mov     dword ptr [rsp+2C0h+bstrString], r14d
0x180005f64  mov     [rsp+2C0h+var_260], r14
0x180005f69  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180005f6e  mov     [rsp+2C0h+psz], r14w
0x180005f74  test    r12, r12
0x180005f77  jz      loc_18000631B
0x180005f7d  mov     rcx, r12; pbstr
0x180005f80  call    cs:__imp_SysStringLen
0x180005f86  test    eax, eax
0x180005f88  jz      loc_18000631B
0x180005f8e  test    r13, r13
0x180005f91  jz      short loc_180005F97
0x180005f93  mov     [r13+0], r14
0x180005f97  mov     esi, 1
0x180005f9c  lea     rcx, Resource; Resource
0x180005fa3  mov     dl, sil; Wait
0x180005fa6  call    cs:__imp_RtlAcquireResourceShared
0x180005fac  cmp     cs:qword_180021B78, r14
0x180005fb3  ja      short loc_180005FD3
0x180005fb5  cmp     cs:dword_180021B8C, r14d
0x180005fbc  jnz     short loc_180005FD3
0x180005fbe  cmp     cs:dword_180021B90, r14d
0x180005fc5  jnz     short loc_180005FD3
0x180005fc7  cmp     cs:dword_180021B98, r14d
0x180005fce  mov     ebx, r14d
0x180005fd1  jz      short loc_180005FD5
0x180005fd3  mov     ebx, esi
0x180005fd5  lea     rcx, Resource; Resource
0x180005fdc  call    cs:__imp_RtlReleaseResource
0x180005fe2  test    ebx, ebx
0x180005fe4  jz      loc_1800061B1
0x180005fea  lea     rax, [rsp+2C0h+var_280]
0x180005fef  mov     rdx, r12; unsigned __int16 *
0x180005ff2  mov     [rsp+2C0h+var_290], rax; unsigned int *
0x180005ff7  lea     r9, [rsp+2C0h+var_278]; unsigned int *
0x180005ffc  lea     rax, [rsp+2C0h+var_270]
0x180006001  mov     [rsp+2C0h+var_298], rax; unsigned int *
0x180006006  lea     r8, [rsp+2C0h+var_260]; unsigned __int16 **
0x18000600b  lea     rax, [rsp+2C0h+var_274]
0x180006010  lea     rcx, unk_180021B00; this
0x180006017  mov     [rsp+2C0h+var_2A0], rax; unsigned int *
0x18000601c  call    ?CheckPolicy@CPolicyCheck@@QEAAJPEBGPEAPEAGPEAK222@Z; CPolicyCheck::CheckPolicy(ushort const *,ushort * *,ulong *,ulong *,ulong *,ulong *)
0x180006021  mov     ebx, eax
0x180006023  test    eax, eax
0x180006025  jns     short loc_18000604B
0x180006027  lea     rdi, AXISEVENT_ERROR_POLICY_FAIL
0x18000602e  cmp     eax, 80070490h
0x180006033  jnz     loc_1800062FE
0x180006039  cmp     [r15+2C0h], r14d
0x180006040  jnz     loc_1800061C1
0x180006046  jmp     loc_1800062F9
0x18000604b  mov     eax, [rsp+2C0h+var_280]
0x18000604f  lea     r8, [rsp+2C0h+psz]; unsigned __int16 *
0x180006054  mov     rdx, r12; unsigned __int16 *
0x180006057  mov     dword ptr [rsp+2C0h+var_2A0], eax; unsigned int
0x18000605b  mov     rcx, r15; this
0x18000605e  call    ?DownloadFileUsingWinHttp@CAxInstaller@@AEAAJPEAG0KK@Z; CAxInstaller::DownloadFileUsingWinHttp(ushort *,ushort *,ulong,ulong)
0x180006063  mov     ebx, eax
0x180006065  test    eax, eax
0x180006067  jns     short loc_180006075
0x180006069  lea     rdi, AXISEVENT_ERROR_DOWNLOAD
0x180006070  jmp     loc_1800062FE
0x180006075  lea     rax, [rsp+2C0h+var_27C]
0x18000607a  mov     rdx, r12; unsigned __int16 *
0x18000607d  lea     r8, [rsp+2C0h+psz]; unsigned __int16 *
0x180006082  mov     [rsp+2C0h+var_298], rax; int *
0x180006087  call    ?VerifyTrust@@YAJPEAUHWND__@@PEBG1KKPEAH@Z; VerifyTrust(HWND__ *,ushort const *,ushort const *,ulong,ulong,int *)
0x18000608c  test    eax, eax
0x18000608e  jnz     loc_180006130
0x180006094  cmp     [rsp+2C0h+var_27C], r14d
0x180006099  jz      short loc_1800060BD
0x18000609b  mov     eax, [rsp+2C0h+var_278]
0x18000609f  test    eax, eax
0x1800060a1  jz      short loc_1800060B3
0x1800060a3  sub     eax, esi
0x1800060a5  jz      loc_18000619A
0x1800060ab  cmp     eax, esi
0x1800060ad  jz      loc_18000619A
0x1800060b3  mov     ebx, 800B0004h
0x1800060b8  jmp     loc_18000619A
0x1800060bd  mov     eax, [rsp+2C0h+var_274]
0x1800060c1  test    eax, eax
0x1800060c3  jz      short loc_1800060B3
0x1800060c5  sub     eax, esi
0x1800060c7  jz      short loc_18000612B
0x1800060c9  cmp     eax, esi
0x1800060cb  jnz     short loc_1800060B3
0x1800060cd  lea     rdi, AXISEVENT_ERROR_POLICY_SUCCESS
0x1800060d4  test    r14d, r14d
0x1800060d7  jnz     loc_1800061E5
0x1800060dd  xor     r14d, r14d
0x1800060e0  mov     r8, cs:qword_180021A98; struct _ACL *
0x1800060e7  lea     rdx, [rsp+2C0h+psz]; unsigned __int16 *
0x1800060ec  call    ?ReStampFileDacl@CAxisServHelper@@QEAAJPEAGPEAU_ACL@@@Z; CAxisServHelper::ReStampFileDacl(ushort *,_ACL *)
0x1800060f1  mov     ebx, eax
0x1800060f3  test    eax, eax
0x1800060f5  jns     loc_180006295
0x1800060fb  mov     esi, 8
0x180006100  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x180006104  lea     r9, aFailedToReAclF; "Failed to Re-ACL filepath for User and "...
0x18000610b  mov     edx, esi; unsigned int
0x18000610d  lea     rcx, qword_180021AD8; this
0x180006114  lea     r8d, [rsi-6]; unsigned __int8
0x180006118  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000611d  lea     r9, aFailedToReAclV; "Failed to Re-ACL Verified File for User"...
0x180006124  mov     edx, esi
0x180006126  jmp     loc_18000627D
0x18000612b  mov     r14d, esi
0x18000612e  jmp     short loc_1800060CD
0x180006130  jle     short loc_18000613F
0x180006132  movzx   ebx, ax
0x180006135  or      ebx, 80070000h
0x18000613b  mov     eax, ebx
0x18000613d  jmp     short loc_180006176
0x18000613f  mov     ebx, eax
0x180006141  cmp     eax, 800B0100h
0x180006146  jz      short loc_18000616B
0x180006148  cmp     eax, 800B0101h
0x18000614d  jz      short loc_18000616B
0x18000614f  cmp     eax, 800B0109h
0x180006154  jz      short loc_18000616B
0x180006156  cmp     eax, 800B010Ah
0x18000615b  jz      short loc_18000616B
0x18000615d  cmp     eax, 800B010Ch
0x180006162  jz      short loc_18000616B
0x180006164  cmp     eax, 800B010Dh
0x180006169  jnz     short loc_180006176
0x18000616b  cmp     [rsp+2C0h+var_270], esi
0x18000616f  jnz     short loc_180006176
0x180006171  mov     r14d, esi
0x180006174  xor     ebx, ebx
0x180006176  mov     dword ptr [rsp+2C0h+var_298], r14d
0x18000617b  lea     r9, aVerifytrustFai; "VerifyTrust Failed with 0x%x. Will Prom"...
0x180006182  mov     r8d, edi; unsigned __int8
0x180006185  mov     dword ptr [rsp+2C0h+var_2A0], eax
0x180006189  mov     edx, 8; unsigned int
0x18000618e  lea     rcx, qword_180021AD8; this
0x180006195  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000619a  test    ebx, ebx
0x18000619c  jns     loc_1800060CD
0x1800061a2  lea     rdi, AXISEVENT_ERROR_POLICY
0x1800061a9  xor     r14d, r14d
0x1800061ac  jmp     loc_1800062FE
0x1800061b1  cmp     [r15+2C0h], r14d
0x1800061b8  jz      loc_1800062F2
0x1800061be  mov     rdi, r14
0x1800061c1  mov     rdx, [r15+280h]; unsigned __int16 *
0x1800061c8  lea     rcx, [r15+48h]; unsigned __int16 *
0x1800061cc  lea     r8, [rsp+2C0h+psz]; unsigned __int16 *
0x1800061d1  mov     esi, r14d
0x1800061d4  call    ?CopyFileToTempDir@@YAJPEBGPEAG1K@Z; CopyFileToTempDir(ushort const *,ushort *,ushort *,ulong)
0x1800061d9  mov     ebx, eax
0x1800061db  test    eax, eax
0x1800061dd  js      loc_1800062EB
0x1800061e3  jmp     short loc_1800061E8
0x1800061e5  xor     r14d, r14d
0x1800061e8  mov     rcx, [r15+2A8h]
0x1800061ef  lea     rdx, [rsp+2C0h+bstrString]
0x1800061f4  mov     ebx, [r15+2C0h]
0x1800061fb  call    LUAGetUserType
0x180006200  test    eax, eax
0x180006202  jns     short loc_180006224
0x180006204  mov     ecx, eax; Status
0x180006206  call    cs:__imp_RtlNtStatusToDosError
0x18000620c  mov     ebx, eax
0x18000620e  test    eax, eax
0x180006210  jle     loc_1800062EB
0x180006216  movzx   ebx, ax
0x180006219  or      ebx, 80070000h
0x18000621f  jmp     loc_1800062EB
0x180006224  mov     edx, dword ptr [rsp+2C0h+bstrString]
0x180006228  mov     eax, edx
0x18000622a  and     eax, 0FFFFFFEFh
0x18000622d  neg     eax
0x18000622f  sbb     ecx, ecx
0x180006231  and     ecx, ebx
0x180006233  test    esi, esi
0x180006235  jz      short loc_180006241
0x180006237  lea     eax, [rdx-1]
0x18000623a  test    eax, 0FFFFFFEEh
0x18000623f  jz      short loc_180006257
0x180006241  test    ecx, ecx
0x180006243  jz      short loc_180006257
0x180006245  lea     r8, [rsp+2C0h+psz]; unsigned __int16 *
0x18000624a  mov     rdx, r12; unsigned __int16 *
0x18000624d  mov     rcx, r15; this
0x180006250  call    ?WinVerifyFile2@CAxInstaller@@QEAAJPEBG0@Z; CAxInstaller::WinVerifyFile2(ushort const *,ushort const *)
0x180006255  jmp     short loc_180006267
0x180006257  lea     r8, [rsp+2C0h+psz]; unsigned __int16 *
0x18000625c  mov     rdx, r12; unsigned __int16 *
0x18000625f  mov     rcx, r15; this
0x180006262  call    ?WinVerifyFile@CAxInstaller@@QEAAJPEBG0@Z; CAxInstaller::WinVerifyFile(ushort const *,ushort const *)
0x180006267  mov     ebx, eax
0x180006269  test    eax, eax
0x18000626b  jns     loc_1800060E0
0x180006271  lea     r9, aWinverifyfileF; "WinVerifyFile Failed with 0x%x"
0x180006278  mov     edx, 8; unsigned int
0x18000627d  mov     r8d, 2; unsigned __int8
0x180006283  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x180006287  lea     rcx, qword_180021AD8; this
0x18000628e  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180006293  jmp     short loc_1800062EB
0x180006295  mov     rbx, [r15+2B8h]
0x18000629c  lea     rdx, [rsp+2C0h+psz]; unsigned __int16 *
0x1800062a1  lea     rcx, [rsp+2C0h+bstrString]; this
0x1800062a6  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800062ab  mov     rdx, r12; unsigned __int16 *
0x1800062ae  mov     rcx, rbx; this
0x1800062b1  mov     r8, [rax]; unsigned __int16 *
0x1800062b4  call    ?AddUrlEntry@CAxisUrlCache@@QEAAJPEAG0@Z; CAxisUrlCache::AddUrlEntry(ushort *,ushort *)
0x1800062b9  mov     rcx, [rsp+2C0h+bstrString]; bstrString
0x1800062be  mov     ebx, eax
0x1800062c0  call    cs:__imp_SysFreeString
0x1800062c6  test    ebx, ebx
0x1800062c8  js      short loc_1800062EB
0x1800062ca  test    r13, r13
0x1800062cd  jz      short loc_1800062E8
0x1800062cf  lea     rcx, [rsp+2C0h+psz]; psz
0x1800062d4  call    cs:__imp_SysAllocString
0x1800062da  mov     [r13+0], rax
0x1800062de  mov     ebx, 8007000Eh
0x1800062e3  test    rax, rax
0x1800062e6  jz      short loc_1800062EB
0x1800062e8  mov     ebx, r14d
0x1800062eb  test    rdi, rdi
0x1800062ee  jz      short loc_180006315
0x1800062f0  jmp     short loc_1800062FE
0x1800062f2  lea     rdi, AXISEVENT_ERROR_POLICY_FAIL
0x1800062f9  mov     ebx, 800B0004h
0x1800062fe  mov     r9, [rsp+2C0h+var_260]; unsigned __int16 *
0x180006303  lea     rcx, qword_180021AD8; this
0x18000630a  mov     r8, r12; unsigned __int16 *
0x18000630d  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x180006310  call    ?GenerateUrlPolicyEvent@AxISEvents@@QEAAKPEBU_EVENT_DESCRIPTOR@@PEBG1@Z; AxISEvents::GenerateUrlPolicyEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x180006315  test    ebx, ebx
0x180006317  jns     short loc_180006333
0x180006319  jmp     short loc_180006320
0x18000631b  mov     ebx, 80070057h
0x180006320  cmp     r14w, [rsp+2C0h+psz]
0x180006326  jz      short loc_180006333
0x180006328  lea     rcx, [rsp+2C0h+psz]; lpFileName
0x18000632d  call    cs:__imp_DeleteFileW
0x180006333  mov     rcx, [rsp+2C0h+var_260]; bstrString
0x180006338  call    cs:__imp_SysFreeString
0x18000633e  mov     eax, ebx
0x180006340  mov     rcx, [rbp+1C0h+var_40]
0x180006347  xor     rcx, rsp; StackCookie
0x18000634a  call    __security_check_cookie
0x18000634f  mov     rbx, [rsp+2C0h+arg_18]
0x180006357  add     rsp, 290h
0x18000635e  pop     r15
0x180006360  pop     r14
0x180006362  pop     r13
0x180006364  pop     r12
0x180006366  pop     rdi
0x180006367  pop     rsi
0x180006368  pop     rbp
0x180006369  retn
```
