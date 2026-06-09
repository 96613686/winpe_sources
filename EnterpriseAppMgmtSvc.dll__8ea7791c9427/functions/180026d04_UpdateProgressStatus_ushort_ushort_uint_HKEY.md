# UpdateProgressStatus(ushort *,ushort *,uint,HKEY__ *)

- ea: `0x180026d04`
- end: `0x180027036`
- name: `?UpdateProgressStatus@@YAJPEAG0IPEAUHKEY__@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(BSTR pbstr, unsigned __int16 *, unsigned int, HKEY)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180022aa0`

## callees

- `0x18000139c`
- `0x180001bf4`
- `0x18000cfe8`
- `0x18001c5b8`
- `0x18001d704`
- `0x18001dbc8`
- `0x180022510`
- `0x180026d04`
- `0x1800273c8`
- `0x180029ca0`
- `0x1800315d4`
- `0x180065664`
- `0x180065a64`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026d57`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026de4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026e20`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026d57`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026de4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026e20`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026f41`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026fd9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026f41`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026fd9`
- `OLEAUT32!__imp_SysStringLen` at `0x180026d6a`
- `OLEAUT32!__imp_SysStringLen` at `0x180026d6a`
- `DMCmnUtils!DmRevertToSelf` at `0x180026f22`
- `DMCmnUtils!DmRevertToSelf` at `0x180026fbe`
- `DMCmnUtils!DmRevertToSelf` at `0x180026f22`
- `DMCmnUtils!DmRevertToSelf` at `0x180026fbe`

## string_xrefs

- `0x180026e76`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180026e91`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180026f67`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180026da8`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180026fa5`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UpdateProgressStatus(BSTR pbstr, unsigned __int16 *a2, int a3, HKEY a4)
{
  signed int v7; // ebx
  UINT v8; // eax
  _DWORD *v9; // rax
  void *v10; // rbx
  void *v11; // rax
  _DWORD *v12; // rax
  void *v13; // rbx
  void *v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  HKEY v19; // r8
  int v20; // eax
  int v21; // eax
  __int64 v22; // r8
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  signed int v26; // [rsp+30h] [rbp-D0h] BYREF
  void **v27; // [rsp+38h] [rbp-C8h] BYREF
  char v28; // [rsp+40h] [rbp-C0h]
  __int128 v29; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+58h] [rbp-A8h]
  char v31[8]; // [rsp+60h] [rbp-A0h] BYREF
  char *v32; // [rsp+68h] [rbp-98h]
  void *v33; // [rsp+D0h] [rbp-30h]
  void *v34; // [rsp+110h] [rbp+10h]
  signed int *v35; // [rsp+190h] [rbp+90h]
  __int64 v36; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  if ( !pbstr )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  EnterpriseModernAppManagement::tagProductInfo::tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v31);
  v7 = 0;
  operator delete(v32);
  v32 = 0;
  if ( pbstr )
  {
    v8 = SysStringLen(pbstr);
    if ( v8 <= 0x3FFFFFFF )
    {
      v32 = Common::AutoStringAllocateAndCopy((Common *)pbstr, (const unsigned __int16 *)v8);
      v7 = v32 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v7 = -2147024809;
    }
  }
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17C,
      (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v7);
    goto LABEL_42;
  }
  v9 = operator new(4u);
  v10 = v9;
  if ( v9 )
    *v9 = a3;
  else
    v10 = 0;
  v11 = v34;
  if ( v34 != v10 )
  {
    operator delete(v34);
    v11 = v10;
    v34 = v10;
  }
  if ( !v11 )
    goto LABEL_41;
  v12 = operator new(4u);
  v13 = v12;
  if ( v12 )
    *v12 = 1;
  else
    v13 = 0;
  v14 = v33;
  if ( v33 != v13 )
  {
    operator delete(v33);
    v14 = v13;
    v33 = v13;
  }
  if ( !v14 )
  {
LABEL_41:
    v7 = -2147024882;
    goto LABEL_42;
  }
  v27 = &ImpersonateUserHelper::`vftable';
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v15 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v29, a2);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
      (const char *)(unsigned int)v15,
      v24);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
      (const char *)(unsigned int)v7,
      v25);
LABEL_23:
    if ( (unsigned int)dword_18008F0A0 > 5
      && (qword_18008F0B0 & 0x400000000000LL) != 0
      && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
    {
      v26 = v7;
      v35 = &v26;
      v36 = 4;
      v24 = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_18008F0A0, &byte_180082537, 0);
    }
    goto LABEL_27;
  }
  v18 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v27);
  v7 = v18;
  if ( v18 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
      (const char *)(unsigned int)v18,
      v24);
  if ( v7 < 0 )
    goto LABEL_23;
  v20 = EnterpriseModernAppManagement::AddProductInfo(
          (EnterpriseModernAppManagement *)v31,
          (const struct EnterpriseModernAppManagement::tagProductInfo *)0xFFFFFFFF80000001LL,
          v19);
  v7 = v20;
  if ( v20 >= 0 )
  {
LABEL_27:
    if ( v28 )
    {
      v16 = DmRevertToSelf();
      if ( v16 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v17, (const char *)(unsigned int)v16, v24);
    }
    if ( *((_QWORD *)&v29 + 1) )
      operator delete[](*((void **)&v29 + 1));
    goto LABEL_42;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x18B,
    (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v20);
  if ( v28 )
  {
    v21 = DmRevertToSelf();
    if ( v21 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v22, (const char *)(unsigned int)v21, v24);
  }
  if ( *((_QWORD *)&v29 + 1) )
    operator delete[](*((void **)&v29 + 1));
LABEL_42:
  EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026d04  mov     [rsp-8+arg_10], rbx
0x180026d09  mov     [rsp-8+arg_18], rsi
0x180026d0e  push    rbp
0x180026d0f  push    rdi
0x180026d10  push    r14
0x180026d12  lea     rbp, [rsp-0B0h]
0x180026d1a  sub     rsp, 1B0h
0x180026d21  mov     rax, cs:__security_cookie
0x180026d28  xor     rax, rsp
0x180026d2b  mov     [rbp+0C0h+var_20], rax
0x180026d32  mov     esi, r8d
0x180026d35  mov     r14, rdx
0x180026d38  mov     rdi, rcx
0x180026d3b  test    rcx, rcx
0x180026d3e  jnz     short loc_180026D45
0x180026d40  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026d45  lea     rcx, [rsp+1C0h+var_160]; this
0x180026d4a  call    ??0tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::tagProductInfo(void)
0x180026d4f  nop
0x180026d50  xor     ebx, ebx
0x180026d52  mov     rcx, [rsp+1C0h+var_158]
0x180026d57  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026d5d  mov     [rsp+1C0h+var_158], rbx
0x180026d62  test    rdi, rdi
0x180026d65  jz      short loc_180026D9A
0x180026d67  mov     rcx, rdi; pbstr
0x180026d6a  call    cs:__imp_SysStringLen
0x180026d70  cmp     eax, 3FFFFFFFh
0x180026d75  jbe     short loc_180026D7E
0x180026d77  mov     ebx, 80070057h
0x180026d7c  jmp     short loc_180026D9A
0x180026d7e  mov     edx, eax; unsigned __int16 *
0x180026d80  mov     rcx, rdi; this
0x180026d83  call    ?AutoStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z; Common::AutoStringAllocateAndCopy(ushort const *,uint)
0x180026d88  mov     [rsp+1C0h+var_158], rax
0x180026d8d  neg     rax
0x180026d90  sbb     ebx, ebx
0x180026d92  not     ebx
0x180026d94  and     ebx, 8007000Eh
0x180026d9a  mov     rcx, [rbp+0C8h]; this
0x180026da1  test    ebx, ebx
0x180026da3  jns     short loc_180026DBE
0x180026da5  mov     r9d, ebx; char *
0x180026da8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026daf  mov     edx, 17Ch; void *
0x180026db4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026db9  jmp     loc_180026FE7
0x180026dbe  mov     edi, 4
0x180026dc3  mov     ecx, edi; Size
0x180026dc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026dca  mov     rbx, rax
0x180026dcd  test    rax, rax
0x180026dd0  jz      short loc_180026DD6
0x180026dd2  mov     [rax], esi
0x180026dd4  jmp     short loc_180026DD8
0x180026dd6  xor     ebx, ebx
0x180026dd8  mov     rax, [rbp+0C0h+var_B0]
0x180026ddc  cmp     rax, rbx
0x180026ddf  jz      short loc_180026DF1
0x180026de1  mov     rcx, rax
0x180026de4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026dea  mov     rax, rbx
0x180026ded  mov     [rbp+0C0h+var_B0], rbx
0x180026df1  test    rax, rax
0x180026df4  jz      loc_180026FE2
0x180026dfa  mov     rcx, rdi; Size
0x180026dfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026e02  mov     rbx, rax
0x180026e05  test    rax, rax
0x180026e08  jz      short loc_180026E12
0x180026e0a  mov     dword ptr [rax], 1
0x180026e10  jmp     short loc_180026E14
0x180026e12  xor     ebx, ebx
0x180026e14  mov     rax, [rbp+0C0h+var_F0]
0x180026e18  cmp     rax, rbx
0x180026e1b  jz      short loc_180026E2D
0x180026e1d  mov     rcx, rax
0x180026e20  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026e26  mov     rax, rbx
0x180026e29  mov     [rbp+0C0h+var_F0], rbx
0x180026e2d  test    rax, rax
0x180026e30  jz      loc_180026FE2
0x180026e36  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x180026e3d  mov     [rsp+1C0h+var_188], rax
0x180026e42  mov     [rsp+1C0h+var_180], 0
0x180026e47  xor     eax, eax
0x180026e49  xorps   xmm0, xmm0
0x180026e4c  movups  [rsp+1C0h+var_178], xmm0
0x180026e51  mov     [rsp+1C0h+var_168], eax
0x180026e55  mov     rdx, r14; Src
0x180026e58  lea     rcx, [rsp+1C0h+var_178]; this
0x180026e5d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180026e62  mov     ebx, eax
0x180026e64  test    eax, eax
0x180026e66  jns     loc_180026F4D
0x180026e6c  mov     rcx, [rbp+0C8h]; this
0x180026e73  mov     r9d, eax; char *
0x180026e76  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026e7d  mov     edx, 52h ; 'R'; void *
0x180026e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026e87  mov     rcx, [rbp+0C8h]; this
0x180026e8e  mov     r9d, ebx; char *
0x180026e91  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026e98  mov     edx, 43h ; 'C'; void *
0x180026e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026ea2  mov     eax, cs:dword_18008F0A0
0x180026ea8  cmp     eax, 5
0x180026eab  jbe     short loc_180026F1B
0x180026ead  mov     rcx, cs:qword_18008F0B8
0x180026eb4  mov     rax, cs:qword_18008F0B0
0x180026ebb  mov     rdx, 400000000000h
0x180026ec5  test    rdx, rax
0x180026ec8  jz      short loc_180026F1B
0x180026eca  mov     rax, rcx
0x180026ecd  and     rax, rdx
0x180026ed0  cmp     rax, rcx
0x180026ed3  jnz     short loc_180026F1B
0x180026ed5  mov     [rsp+1C0h+var_190], ebx
0x180026ed9  lea     rax, [rsp+1C0h+var_190]
0x180026ede  mov     [rbp+0C0h+var_30], rax
0x180026ee5  mov     [rbp+0C0h+var_28], 4
0x180026ef0  lea     rax, [rbp+0C0h+var_50]
0x180026ef4  mov     [rsp+1C0h+var_198], rax
0x180026ef9  mov     [rsp+1C0h+var_1A0], 3; int
0x180026f01  xor     r9d, r9d
0x180026f04  xor     r8d, r8d
0x180026f07  lea     rdx, byte_180082537
0x180026f0e  lea     rcx, dword_18008F0A0
0x180026f15  call    _tlgWriteTransfer_EventWriteTransfer
0x180026f1a  nop
0x180026f1b  cmp     [rsp+1C0h+var_180], 0
0x180026f20  jz      short loc_180026F37
0x180026f22  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180026f28  mov     rcx, [rbp+0C8h]; this
0x180026f2f  test    eax, eax
0x180026f31  js      loc_180027028
0x180026f37  mov     rcx, qword ptr [rsp+1C0h+var_178+8]
0x180026f3c  test    rcx, rcx
0x180026f3f  jz      short loc_180026F48
0x180026f41  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026f47  nop
0x180026f48  jmp     loc_180026FE7
0x180026f4d  lea     rcx, [rsp+1C0h+var_188]; this
0x180026f52  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x180026f57  mov     ebx, eax
0x180026f59  test    eax, eax
0x180026f5b  jns     short loc_180026F78
0x180026f5d  mov     rcx, [rbp+0C8h]; this
0x180026f64  mov     r9d, eax; char *
0x180026f67  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026f6e  mov     edx, 44h ; 'D'; void *
0x180026f73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f78  test    ebx, ebx
0x180026f7a  js      loc_180026EA2
0x180026f80  mov     rdx, 0FFFFFFFF80000001h; struct EnterpriseModernAppManagement::tagProductInfo *
0x180026f87  lea     rcx, [rsp+1C0h+var_160]; this
0x180026f8c  call    ?AddProductInfo@EnterpriseModernAppManagement@@YAJAEBUtagProductInfo@1@PEAUHKEY__@@@Z; EnterpriseModernAppManagement::AddProductInfo(EnterpriseModernAppManagement::tagProductInfo const &,HKEY__ *)
0x180026f91  mov     ebx, eax
0x180026f93  mov     rcx, [rbp+0C8h]; this
0x180026f9a  test    eax, eax
0x180026f9c  jns     loc_180026F1B
0x180026fa2  mov     r9d, eax; char *
0x180026fa5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026fac  mov     edx, 18Bh; void *
0x180026fb1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026fb6  nop
0x180026fb7  cmp     [rsp+1C0h+var_180], 0
0x180026fbc  jz      short loc_180026FCF
0x180026fbe  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180026fc4  mov     rcx, [rbp+0C8h]; this
0x180026fcb  test    eax, eax
0x180026fcd  js      short loc_18002701A
0x180026fcf  mov     rcx, qword ptr [rsp+1C0h+var_178+8]
0x180026fd4  test    rcx, rcx
0x180026fd7  jz      short loc_180026FE0
0x180026fd9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026fdf  nop
0x180026fe0  jmp     short loc_180026FE7
0x180026fe2  mov     ebx, 8007000Eh
0x180026fe7  lea     rcx, [rsp+1C0h+var_160]; this
0x180026fec  call    ??1tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo(void)
0x180026ff1  mov     eax, ebx
0x180026ff3  mov     rcx, [rbp+0C0h+var_20]
0x180026ffa  xor     rcx, rsp; StackCookie
0x180026ffd  call    __security_check_cookie
0x180027002  lea     r11, [rsp+1C0h+var_10]
0x18002700a  mov     rbx, [r11+30h]
0x18002700e  mov     rsi, [r11+38h]
0x180027012  mov     rsp, r11
0x180027015  pop     r14
0x180027017  pop     rdi
0x180027018  pop     rbp
0x180027019  retn
0x18002701a  mov     r9d, eax; char *
0x18002701d  mov     edx, 4Bh ; 'K'; void *
0x180027022  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180027028  mov     r9d, eax; char *
0x18002702b  mov     edx, 4Bh ; 'K'; void *
0x180027030  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
