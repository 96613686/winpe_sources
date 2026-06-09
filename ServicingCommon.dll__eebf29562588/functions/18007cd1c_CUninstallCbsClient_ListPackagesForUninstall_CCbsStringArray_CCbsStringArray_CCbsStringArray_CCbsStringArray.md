# CUninstallCbsClient::ListPackagesForUninstall(CCbsStringArray *,CCbsStringArray *,CCbsStringArray *,CCbsStringArray *)

- ea: `0x18007cd1c`
- end: `0x18007d187`
- name: `?ListPackagesForUninstall@CUninstallCbsClient@@QEAAJPEAVCCbsStringArray@@000@Z`
- size: `1131`
- prototype: `__int64 __fastcall(CUninstallCbsClient *__hidden this, struct CCbsStringArray *, struct CCbsStringArray *, struct CCbsStringArray *, struct CCbsStringArray *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007bdb0`

## callees

- `0x18001e51c`
- `0x18001f708`
- `0x18001fd10`
- `0x180024120`
- `0x1800293a0`
- `0x18002a2c0`
- `0x18003e810`
- `0x180047530`
- `0x18007cd1c`
- `0x18007d464`
- `0x1800a0020`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18007d002`
- `OLE32!CoTaskMemFree` at `0x18007d01b`
- `OLE32!CoTaskMemFree` at `0x18007d069`
- `OLE32!CoTaskMemFree` at `0x18007d082`
- `OLE32!CoTaskMemFree` at `0x18007d0fc`
- `OLE32!CoTaskMemFree` at `0x18007d115`
- `OLE32!CoTaskMemFree` at `0x18007d002`
- `OLE32!CoTaskMemFree` at `0x18007d01b`
- `OLE32!CoTaskMemFree` at `0x18007d069`
- `OLE32!CoTaskMemFree` at `0x18007d082`
- `OLE32!CoTaskMemFree` at `0x18007d0fc`
- `OLE32!CoTaskMemFree` at `0x18007d115`

## string_xrefs

- `0x18007cd9a`: `onecore\base\cbs\uninstall\cbsclient.cpp`
- `0x18007d047`: `onecore\base\cbs\uninstall\cbsclient.cpp`
- `0x18007d0e4`: `onecore\base\cbs\uninstall\cbsclient.cpp`
- `0x18007cf4a`: `Security Update`
- `0x18007cf32`: `Update`

## pseudocode

```c
__int64 __fastcall CUninstallCbsClient::ListPackagesForUninstall(
        CUninstallCbsClient *this,
        struct CCbsStringArray *a2,
        struct CCbsStringArray *a3,
        struct CCbsStringArray *a4,
        struct CCbsStringArray *a5)
{
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v12; // ebx
  __int64 v13; // rdx
  void (*v14)(void); // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64, int *); // rbx
  __int64 v17; // rax
  struct ICbsPackage **v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, __int64); // rbx
  __int64 v21; // rax
  struct ICbsIdentity *v22; // rdi
  __int64 (__fastcall *v23)(struct ICbsIdentity *, __int64); // rbx
  __int64 v24; // rax
  __int64 v25; // rdx
  void (*v26)(void); // rax
  int v28; // [rsp+20h] [rbp-58h]
  wchar_t *Str; // [rsp+30h] [rbp-48h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-40h] BYREF
  __int64 v31; // [rsp+40h] [rbp-38h] BYREF
  struct ICbsIdentity *v32; // [rsp+48h] [rbp-30h] BYREF
  __int64 v33; // [rsp+50h] [rbp-28h] BYREF
  int v34; // [rsp+58h] [rbp-20h] BYREF
  int v35; // [rsp+5Ch] [rbp-1Ch] BYREF
  int v36; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v34 = 0;
  v33 = 0;
  v35 = 0;
  v36 = 0;
  v31 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 1);
  v10 = **v9;
  InitPointer = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v31);
  v12 = v10(v9, &GUID_f112757a_565b_4260_bd05_9fa34417349a, InitPointer);
  if ( v12 < 0 )
  {
    v13 = 330;
    goto LABEL_3;
  }
  if ( v33 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18007D186LL);
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 1) + 56LL))(
          *((_QWORD *)this + 1),
          80,
          &v33);
  if ( v12 < 0 )
  {
    v13 = 336;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
      (const char *)(unsigned int)v12,
      v28);
    if ( v31 )
    {
      v14 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
LABEL_55:
      v14();
      v31 = 0;
    }
    goto LABEL_56;
  }
  while ( 1 )
  {
    v32 = 0;
    String1 = 0;
    Str = 0;
    v15 = v33;
    v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64, int *))(*(_QWORD *)v33 + 24LL);
    v17 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v32);
    v12 = v16(v15, 1, v17, &v34);
    if ( v12 || !v34 )
      break;
    Windows::AutoComPtr<IClassFactory>::Close(this);
    v18 = (struct ICbsPackage **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(this);
    if ( (int)CUninstallCbsClient::OpenPackage(this, v32, v18) >= 0 )
    {
      v19 = *(_QWORD *)this;
      v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(**(_QWORD **)this + 32LL);
      v21 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&String1);
      v12 = v20(v19, 8, v21);
      if ( v12 < 0 )
      {
        v25 = 360;
        goto LABEL_48;
      }
      v22 = v32;
      v23 = *(__int64 (__fastcall **)(struct ICbsIdentity *, __int64))(*(_QWORD *)v32 + 64LL);
      v24 = Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&Str);
      v12 = v23(v22, v24);
      if ( v12 < 0 )
      {
        v25 = 362;
        goto LABEL_48;
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**(_QWORD **)this + 96LL))(*(_QWORD *)this, &v35, &v36);
      if ( v12 < 0 )
      {
        v25 = 364;
        goto LABEL_48;
      }
      if ( v35 < 7 )
      {
        v12 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
          (const char *)0x8000FFFFLL,
          v28);
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
        Windows::AutoComPtr<IClassFactory>::Close(&v32);
        if ( v31 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          v31 = 0;
        }
        if ( v33 )
        {
          v26 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
          goto LABEL_58;
        }
        return (unsigned int)v12;
      }
      if ( wcsicmp(String1, L"Product") )
      {
        if ( wcsicmp(String1, L"Update") && wcsicmp(String1, L"Security Update") )
        {
          if ( wcsicmp(String1, L"Language Pack") )
          {
            if ( wcsicmp(String1, L"OnDemand Pack") )
            {
              v12 = CCbsStringArray::CopyAndAdd(a5, Str);
              if ( v12 < 0 )
              {
                v25 = 393;
                goto LABEL_48;
              }
            }
            else
            {
              v12 = CCbsStringArray::CopyAndAdd(a3, Str);
              if ( v12 < 0 )
              {
                v25 = 389;
                goto LABEL_48;
              }
            }
          }
          else
          {
            v12 = CCbsStringArray::CopyAndAdd(a4, Str);
            if ( v12 < 0 )
            {
              v25 = 385;
              goto LABEL_48;
            }
          }
        }
        else if ( wcsstr(Str, L"-Wrapper") )
        {
          v12 = CCbsStringArray::CopyAndAdd(a5, Str);
          if ( v12 < 0 )
          {
            v25 = 380;
            goto LABEL_48;
          }
        }
      }
      else
      {
        v12 = CCbsStringArray::CopyAndAdd(a2, Str);
        if ( v12 < 0 )
        {
          v25 = 373;
LABEL_48:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v25,
            (unsigned int)"onecore\\base\\cbs\\uninstall\\cbsclient.cpp",
            (const char *)(unsigned int)v12,
            v28);
          break;
        }
      }
    }
    else
    {
      Windows::AutoComPtr<IClassFactory>::Close(&v32);
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
    Windows::AutoComPtr<IClassFactory>::Close(&v32);
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
  Windows::AutoComPtr<IClassFactory>::Close(&v32);
  if ( v31 )
  {
    v14 = *(void (**)(void))(*(_QWORD *)v31 + 16LL);
    goto LABEL_55;
  }
LABEL_56:
  if ( v33 )
  {
    v26 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
LABEL_58:
    v26();
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18007cd1c  push    rbp
0x18007cd1e  push    rbx
0x18007cd1f  push    rsi
0x18007cd20  push    rdi
0x18007cd21  push    r12
0x18007cd23  push    r13
0x18007cd25  push    r14
0x18007cd27  push    r15
0x18007cd29  mov     rbp, rsp
0x18007cd2c  sub     rsp, 78h
0x18007cd30  mov     rax, cs:__security_cookie
0x18007cd37  xor     rax, rsp
0x18007cd3a  mov     [rbp+var_10], rax
0x18007cd3e  mov     r14, [rbp+arg_20]
0x18007cd42  xor     edi, edi
0x18007cd44  mov     [rbp+var_20], edi
0x18007cd47  mov     rsi, rcx
0x18007cd4a  mov     [rbp+var_28], rdi
0x18007cd4e  mov     r13, r9
0x18007cd51  mov     [rbp+var_1C], edi
0x18007cd54  mov     r12, r8
0x18007cd57  mov     [rbp+var_18], edi
0x18007cd5a  mov     r15, rdx
0x18007cd5d  mov     [rbp+var_38], rdi
0x18007cd61  mov     rdi, [rcx+8]
0x18007cd65  lea     rcx, [rbp+var_38]
0x18007cd69  mov     rax, [rdi]
0x18007cd6c  mov     rbx, [rax]
0x18007cd6f  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007cd74  mov     r8, rax
0x18007cd77  lea     rdx, _GUID_f112757a_565b_4260_bd05_9fa34417349a
0x18007cd7e  mov     rax, rbx
0x18007cd81  mov     rcx, rdi
0x18007cd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd89  xor     edi, edi
0x18007cd8b  mov     ebx, eax
0x18007cd8d  test    eax, eax
0x18007cd8f  jns     short loc_18007CDC2
0x18007cd91  mov     edx, 14Ah; void *
0x18007cd96  mov     rcx, [rbp+40h]; this
0x18007cd9a  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007cda1  mov     r9d, ebx; char *
0x18007cda4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cda9  mov     rcx, [rbp+var_38]
0x18007cdad  test    rcx, rcx
0x18007cdb0  jz      loc_18007D147
0x18007cdb6  mov     rdx, [rcx]
0x18007cdb9  mov     rax, [rdx+10h]
0x18007cdbd  jmp     loc_18007D13E
0x18007cdc2  cmp     [rbp+var_28], rdi
0x18007cdc6  jnz     loc_18007D17C
0x18007cdcc  mov     rcx, [rsi+8]
0x18007cdd0  lea     r8, [rbp+var_28]
0x18007cdd4  mov     edx, 50h ; 'P'
0x18007cdd9  mov     rax, [rcx]
0x18007cddc  mov     rax, [rax+38h]
0x18007cde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cde5  mov     ebx, eax
0x18007cde7  test    eax, eax
0x18007cde9  jns     short loc_18007CDF2
0x18007cdeb  mov     edx, 150h
0x18007cdf0  jmp     short loc_18007CD96
0x18007cdf2  mov     [rbp+var_30], rdi
0x18007cdf6  lea     rcx, [rbp+var_30]
0x18007cdfa  mov     [rbp+String1], rdi
0x18007cdfe  mov     [rbp+Str], rdi
0x18007ce02  mov     rdi, [rbp+var_28]
0x18007ce06  mov     rax, [rdi]
0x18007ce09  mov     rbx, [rax+18h]
0x18007ce0d  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007ce12  mov     r8, rax
0x18007ce15  lea     r9, [rbp+var_20]
0x18007ce19  mov     rax, rbx
0x18007ce1c  mov     edx, 1
0x18007ce21  mov     rcx, rdi
0x18007ce24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce29  xor     edi, edi
0x18007ce2b  mov     ebx, eax
0x18007ce2d  test    eax, eax
0x18007ce2f  jnz     loc_18007D0F3
0x18007ce35  cmp     [rbp+var_20], edi
0x18007ce38  jz      loc_18007D0F3
0x18007ce3e  mov     rcx, rsi
0x18007ce41  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007ce46  mov     rcx, rsi
0x18007ce49  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007ce4e  mov     rdx, [rbp+var_30]; struct ICbsIdentity *
0x18007ce52  mov     r8, rax; struct ICbsPackage **
0x18007ce55  mov     rcx, rsi; this
0x18007ce58  call    ?OpenPackage@CUninstallCbsClient@@AEAAJPEAUICbsIdentity@@PEAPEAUICbsPackage@@@Z; CUninstallCbsClient::OpenPackage(ICbsIdentity *,ICbsPackage * *)
0x18007ce5d  test    eax, eax
0x18007ce5f  jns     short loc_18007CE6F
0x18007ce61  lea     rcx, [rbp+var_30]
0x18007ce65  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007ce6a  jmp     loc_18007CFF9
0x18007ce6f  mov     rdi, [rsi]
0x18007ce72  lea     rcx, [rbp+String1]
0x18007ce76  mov     rax, [rdi]
0x18007ce79  mov     rbx, [rax+20h]
0x18007ce7d  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007ce82  mov     r8, rax
0x18007ce85  mov     edx, 8
0x18007ce8a  mov     rax, rbx
0x18007ce8d  mov     rcx, rdi
0x18007ce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce95  xor     edi, edi
0x18007ce97  mov     ebx, eax
0x18007ce99  test    eax, eax
0x18007ce9b  js      loc_18007D0DB
0x18007cea1  mov     rdi, [rbp+var_30]
0x18007cea5  lea     rcx, [rbp+Str]
0x18007cea9  mov     rax, [rdi]
0x18007ceac  mov     rbx, [rax+40h]
0x18007ceb0  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x18007ceb5  mov     rdx, rax
0x18007ceb8  mov     rcx, rdi
0x18007cebb  mov     rax, rbx
0x18007cebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cec3  xor     edi, edi
0x18007cec5  mov     ebx, eax
0x18007cec7  test    eax, eax
0x18007cec9  js      loc_18007D0D4
0x18007cecf  mov     rcx, [rsi]
0x18007ced2  lea     r8, [rbp+var_18]
0x18007ced6  lea     rdx, [rbp+var_1C]
0x18007ceda  mov     rax, [rcx]
0x18007cedd  mov     rax, [rax+60h]
0x18007cee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cee6  mov     ebx, eax
0x18007cee8  test    eax, eax
0x18007ceea  js      loc_18007D0CD
0x18007cef0  cmp     [rbp+var_1C], 7
0x18007cef4  jl      loc_18007D043
0x18007cefa  mov     rcx, [rbp+String1]; String1
0x18007cefe  lea     rdx, aProduct; "Product"
0x18007cf05  call    _wcsicmp
0x18007cf0a  test    eax, eax
0x18007cf0c  jnz     short loc_18007CF2E
0x18007cf0e  mov     rdx, [rbp+Str]; wchar_t *
0x18007cf12  mov     rcx, r15; this
0x18007cf15  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x18007cf1a  mov     ebx, eax
0x18007cf1c  test    eax, eax
0x18007cf1e  jns     loc_18007CFF9
0x18007cf24  mov     edx, 175h
0x18007cf29  jmp     loc_18007D0E0
0x18007cf2e  mov     rcx, [rbp+String1]; String1
0x18007cf32  lea     rdx, aUpdate; "Update"
0x18007cf39  call    _wcsicmp
0x18007cf3e  test    eax, eax
0x18007cf40  jz      loc_18007CFD2
0x18007cf46  mov     rcx, [rbp+String1]; String1
0x18007cf4a  lea     rdx, aSecurityUpdate; "Security Update"
0x18007cf51  call    _wcsicmp
0x18007cf56  test    eax, eax
0x18007cf58  jz      short loc_18007CFD2
0x18007cf5a  mov     rcx, [rbp+String1]; String1
0x18007cf5e  lea     rdx, aLanguagePack; "Language Pack"
0x18007cf65  call    _wcsicmp
0x18007cf6a  test    eax, eax
0x18007cf6c  jnz     short loc_18007CF8A
0x18007cf6e  mov     rdx, [rbp+Str]; wchar_t *
0x18007cf72  mov     rcx, r13; this
0x18007cf75  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x18007cf7a  mov     ebx, eax
0x18007cf7c  test    eax, eax
0x18007cf7e  jns     short loc_18007CFF9
0x18007cf80  mov     edx, 181h
0x18007cf85  jmp     loc_18007D0E0
0x18007cf8a  mov     rcx, [rbp+String1]; String1
0x18007cf8e  lea     rdx, aOndemandPack; "OnDemand Pack"
0x18007cf95  call    _wcsicmp
0x18007cf9a  mov     rdx, [rbp+Str]; wchar_t *
0x18007cf9e  test    eax, eax
0x18007cfa0  jnz     short loc_18007CFBA
0x18007cfa2  mov     rcx, r12; this
0x18007cfa5  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x18007cfaa  mov     ebx, eax
0x18007cfac  test    eax, eax
0x18007cfae  jns     short loc_18007CFF9
0x18007cfb0  mov     edx, 185h
0x18007cfb5  jmp     loc_18007D0E0
0x18007cfba  mov     rcx, r14; this
0x18007cfbd  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x18007cfc2  mov     ebx, eax
0x18007cfc4  test    eax, eax
0x18007cfc6  jns     short loc_18007CFF9
0x18007cfc8  mov     edx, 189h
0x18007cfcd  jmp     loc_18007D0E0
0x18007cfd2  mov     rcx, [rbp+Str]; Str
0x18007cfd6  lea     rdx, aWrapper; "-Wrapper"
0x18007cfdd  call    wcsstr
0x18007cfe2  test    rax, rax
0x18007cfe5  jz      short loc_18007CFF9
0x18007cfe7  mov     rdx, [rbp+Str]; wchar_t *
0x18007cfeb  mov     rcx, r14; this
0x18007cfee  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x18007cff3  mov     ebx, eax
0x18007cff5  test    eax, eax
0x18007cff7  js      short loc_18007D039
0x18007cff9  mov     rcx, [rbp+Str]; pv
0x18007cffd  test    rcx, rcx
0x18007d000  jz      short loc_18007D012
0x18007d002  call    cs:__imp_CoTaskMemFree
0x18007d009  nop     dword ptr [rax+rax+00h]
0x18007d00e  mov     [rbp+Str], rdi
0x18007d012  mov     rcx, [rbp+String1]; pv
0x18007d016  test    rcx, rcx
0x18007d019  jz      short loc_18007D02B
0x18007d01b  call    cs:__imp_CoTaskMemFree
0x18007d022  nop     dword ptr [rax+rax+00h]
0x18007d027  mov     [rbp+String1], rdi
0x18007d02b  lea     rcx, [rbp+var_30]
0x18007d02f  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d034  jmp     loc_18007CDF2
0x18007d039  mov     edx, 17Ch
0x18007d03e  jmp     loc_18007D0E0
0x18007d043  mov     rcx, [rbp+40h]; this
0x18007d047  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007d04e  mov     ebx, 8000FFFFh
0x18007d053  mov     edx, 170h; void *
0x18007d058  mov     r9d, ebx; char *
0x18007d05b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d060  mov     rcx, [rbp+Str]; pv
0x18007d064  test    rcx, rcx
0x18007d067  jz      short loc_18007D079
0x18007d069  call    cs:__imp_CoTaskMemFree
0x18007d070  nop     dword ptr [rax+rax+00h]
0x18007d075  mov     [rbp+Str], rdi
0x18007d079  mov     rcx, [rbp+String1]; pv
0x18007d07d  test    rcx, rcx
0x18007d080  jz      short loc_18007D092
0x18007d082  call    cs:__imp_CoTaskMemFree
0x18007d089  nop     dword ptr [rax+rax+00h]
0x18007d08e  mov     [rbp+String1], rdi
0x18007d092  lea     rcx, [rbp+var_30]
0x18007d096  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d09b  mov     rcx, [rbp+var_38]
0x18007d09f  test    rcx, rcx
0x18007d0a2  jz      short loc_18007D0B4
0x18007d0a4  mov     rax, [rcx]
0x18007d0a7  mov     rax, [rax+10h]
0x18007d0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d0b0  mov     [rbp+var_38], rdi
0x18007d0b4  mov     rcx, [rbp+var_28]
0x18007d0b8  test    rcx, rcx
0x18007d0bb  jz      loc_18007D15C
0x18007d0c1  mov     rdx, [rcx]
0x18007d0c4  mov     rax, [rdx+10h]
0x18007d0c8  jmp     loc_18007D157
0x18007d0cd  mov     edx, 16Ch
0x18007d0d2  jmp     short loc_18007D0E0
0x18007d0d4  mov     edx, 16Ah
0x18007d0d9  jmp     short loc_18007D0E0
0x18007d0db  mov     edx, 168h; void *
0x18007d0e0  mov     rcx, [rbp+40h]; this
0x18007d0e4  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\uninstall\\cbsclien"...
0x18007d0eb  mov     r9d, ebx; char *
0x18007d0ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d0f3  mov     rcx, [rbp+Str]; pv
0x18007d0f7  test    rcx, rcx
0x18007d0fa  jz      short loc_18007D10C
0x18007d0fc  call    cs:__imp_CoTaskMemFree
0x18007d103  nop     dword ptr [rax+rax+00h]
0x18007d108  mov     [rbp+Str], rdi
0x18007d10c  mov     rcx, [rbp+String1]; pv
0x18007d110  test    rcx, rcx
0x18007d113  jz      short loc_18007D125
0x18007d115  call    cs:__imp_CoTaskMemFree
0x18007d11c  nop     dword ptr [rax+rax+00h]
0x18007d121  mov     [rbp+String1], rdi
0x18007d125  lea     rcx, [rbp+var_30]
0x18007d129  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x18007d12e  mov     rcx, [rbp+var_38]
0x18007d132  test    rcx, rcx
0x18007d135  jz      short loc_18007D147
0x18007d137  mov     rax, [rcx]
0x18007d13a  mov     rax, [rax+10h]
0x18007d13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d143  mov     [rbp+var_38], rdi
0x18007d147  mov     rcx, [rbp+var_28]
0x18007d14b  test    rcx, rcx
0x18007d14e  jz      short loc_18007D15C
0x18007d150  mov     rax, [rcx]
0x18007d153  mov     rax, [rax+10h]
0x18007d157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d15c  mov     eax, ebx
0x18007d15e  mov     rcx, [rbp+var_10]
0x18007d162  xor     rcx, rsp; StackCookie
0x18007d165  call    __security_check_cookie
0x18007d16a  add     rsp, 78h
0x18007d16e  pop     r15
0x18007d170  pop     r14
0x18007d172  pop     r13
0x18007d174  pop     r12
0x18007d176  pop     rdi
0x18007d177  pop     rsi
0x18007d178  pop     rbx
0x18007d179  pop     rbp
0x18007d17a  retn
  ... truncated ...
```
