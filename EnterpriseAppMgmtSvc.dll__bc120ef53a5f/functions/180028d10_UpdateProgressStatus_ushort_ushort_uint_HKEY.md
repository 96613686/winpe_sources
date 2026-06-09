# UpdateProgressStatus(ushort *,ushort *,uint,HKEY__ *)

- ea: `0x180028d10`
- end: `0x180029073`
- name: `?UpdateProgressStatus@@YAJPEAG0IPEAUHKEY__@@@Z`
- size: `867`
- prototype: `__int64 __fastcall(BSTR pbstr, unsigned __int16 *, unsigned int, HKEY)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180024350`

## callees

- `0x1800013a0`
- `0x180001c24`
- `0x18000d3dc`
- `0x18001d65c`
- `0x18001e9fc`
- `0x18001f048`
- `0x180023d74`
- `0x180028d10`
- `0x180029444`
- `0x18002be98`
- `0x18003442c`
- `0x18006b028`
- `0x18006b444`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180028d63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028dfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028d63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028dfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028e3e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028f6b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002900f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028f6b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002900f`
- `OLEAUT32!__imp_SysStringLen` at `0x180028d7c`
- `OLEAUT32!__imp_SysStringLen` at `0x180028d7c`
- `DMCmnUtils!DmRevertToSelf` at `0x180028f46`
- `DMCmnUtils!DmRevertToSelf` at `0x180028fee`
- `DMCmnUtils!DmRevertToSelf` at `0x180028f46`
- `DMCmnUtils!DmRevertToSelf` at `0x180028fee`

## string_xrefs

- `0x180028e9a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180028eb5`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180028f97`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\ImpersonateUserHelper.h`
- `0x180028dc0`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180028fd5`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UpdateProgressStatus(BSTR pbstr, unsigned __int16 *a2, int a3, HKEY a4)
{
  signed int v7; // ebx
  UINT v8; // eax
  unsigned int v9; // r8d
  _DWORD *v10; // rax
  void *v11; // rbx
  void *v12; // rax
  _DWORD *v13; // rax
  void *v14; // rbx
  void *v15; // rax
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r8d
  int v19; // eax
  HKEY v20; // r8
  int v21; // eax
  int v22; // eax
  unsigned int v23; // r8d
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  signed int v28; // [rsp+30h] [rbp-D0h] BYREF
  void **v29; // [rsp+38h] [rbp-C8h] BYREF
  char v30; // [rsp+40h] [rbp-C0h]
  __int128 v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+58h] [rbp-A8h]
  char v33[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-98h]
  void *v35; // [rsp+D0h] [rbp-30h]
  void *v36; // [rsp+110h] [rbp+10h]
  signed int *v37; // [rsp+190h] [rbp+90h]
  __int64 v38; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  if ( !pbstr )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  EnterpriseModernAppManagement::tagProductInfo::tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v33);
  v7 = 0;
  operator delete(v34);
  v34 = 0;
  if ( pbstr )
  {
    v8 = SysStringLen(pbstr);
    if ( v8 <= 0x3FFFFFFF )
    {
      v34 = Common::AutoStringAllocateAndCopy((Common *)pbstr, (const unsigned __int16 *)v8, v9);
      v7 = v34 == 0 ? 0x8007000E : 0;
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
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)v7,
      v25);
    goto LABEL_42;
  }
  v10 = operator new(4u);
  v11 = v10;
  if ( v10 )
    *v10 = a3;
  else
    v11 = 0;
  v12 = v36;
  if ( v36 != v11 )
  {
    operator delete(v36);
    v12 = v11;
    v36 = v11;
  }
  if ( !v12 )
    goto LABEL_41;
  v13 = operator new(4u);
  v14 = v13;
  if ( v13 )
    *v13 = 1;
  else
    v14 = 0;
  v15 = v35;
  if ( v35 != v14 )
  {
    operator delete(v35);
    v15 = v14;
    v35 = v14;
  }
  if ( !v15 )
  {
LABEL_41:
    v7 = -2147024882;
    goto LABEL_42;
  }
  v29 = &ImpersonateUserHelper::`vftable';
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v16 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v31, a2);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
      (const char *)(unsigned int)v16,
      v25);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
      (const char *)(unsigned int)v7,
      v26);
LABEL_23:
    if ( (unsigned int)dword_1800950A0 > 5
      && (qword_1800950B0 & 0x400000000000LL) != 0
      && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
    {
      v28 = v7;
      v37 = &v28;
      v38 = 4;
      v25 = 3;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800950A0, &byte_18008853F, 0, 0);
    }
    goto LABEL_27;
  }
  v19 = (unsigned int)ImpersonateUserHelper::ImpersonateUser((ImpersonateUser *)&v29);
  v7 = v19;
  if ( v19 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\ImpersonateUserHelper.h",
      (const char *)(unsigned int)v19,
      v25);
  if ( v7 < 0 )
    goto LABEL_23;
  v21 = EnterpriseModernAppManagement::AddProductInfo(
          (EnterpriseModernAppManagement *)v33,
          (const struct EnterpriseModernAppManagement::tagProductInfo *)0xFFFFFFFF80000001LL,
          v20);
  v7 = v21;
  if ( v21 >= 0 )
  {
LABEL_27:
    if ( v30 )
    {
      v17 = DmRevertToSelf();
      if ( v17 < 0 )
        wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v18, (const char *)(unsigned int)v17, v25);
    }
    if ( *((_QWORD *)&v31 + 1) )
      operator delete[](*((void **)&v31 + 1));
    goto LABEL_42;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x18B,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v21,
    v25);
  if ( v30 )
  {
    v22 = DmRevertToSelf();
    if ( v22 < 0 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0x4B, v23, (const char *)(unsigned int)v22, v27);
  }
  if ( *((_QWORD *)&v31 + 1) )
    operator delete[](*((void **)&v31 + 1));
LABEL_42:
  EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180028d10  mov     [rsp-8+arg_10], rbx
0x180028d15  mov     [rsp-8+arg_18], rsi
0x180028d1a  push    rbp
0x180028d1b  push    rdi
0x180028d1c  push    r14
0x180028d1e  lea     rbp, [rsp-0B0h]
0x180028d26  sub     rsp, 1B0h
0x180028d2d  mov     rax, cs:__security_cookie
0x180028d34  xor     rax, rsp
0x180028d37  mov     [rbp+0C0h+var_20], rax
0x180028d3e  mov     esi, r8d
0x180028d41  mov     r14, rdx
0x180028d44  mov     rdi, rcx
0x180028d47  test    rcx, rcx
0x180028d4a  jnz     short loc_180028D51
0x180028d4c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180028d51  lea     rcx, [rsp+1C0h+var_160]; this
0x180028d56  call    ??0tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::tagProductInfo(void)
0x180028d5b  nop
0x180028d5c  xor     ebx, ebx
0x180028d5e  mov     rcx, [rsp+1C0h+var_158]
0x180028d63  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028d6a  nop     dword ptr [rax+rax+00h]
0x180028d6f  mov     [rsp+1C0h+var_158], rbx
0x180028d74  test    rdi, rdi
0x180028d77  jz      short loc_180028DB2
0x180028d79  mov     rcx, rdi; pbstr
0x180028d7c  call    cs:__imp_SysStringLen
0x180028d83  nop     dword ptr [rax+rax+00h]
0x180028d88  cmp     eax, 3FFFFFFFh
0x180028d8d  jbe     short loc_180028D96
0x180028d8f  mov     ebx, 80070057h
0x180028d94  jmp     short loc_180028DB2
0x180028d96  mov     edx, eax; unsigned __int16 *
0x180028d98  mov     rcx, rdi; this
0x180028d9b  call    ?AutoStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z; Common::AutoStringAllocateAndCopy(ushort const *,uint)
0x180028da0  mov     [rsp+1C0h+var_158], rax
0x180028da5  neg     rax
0x180028da8  sbb     ebx, ebx
0x180028daa  not     ebx
0x180028dac  and     ebx, 8007000Eh
0x180028db2  mov     rcx, [rbp+0C8h]; this
0x180028db9  test    ebx, ebx
0x180028dbb  jns     short loc_180028DD6
0x180028dbd  mov     r9d, ebx; char *
0x180028dc0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028dc7  mov     edx, 17Ch; void *
0x180028dcc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028dd1  jmp     loc_180029023
0x180028dd6  mov     edi, 4
0x180028ddb  mov     ecx, edi; Size
0x180028ddd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028de2  mov     rbx, rax
0x180028de5  test    rax, rax
0x180028de8  jz      short loc_180028DEE
0x180028dea  mov     [rax], esi
0x180028dec  jmp     short loc_180028DF0
0x180028dee  xor     ebx, ebx
0x180028df0  mov     rax, [rbp+0C0h+var_B0]
0x180028df4  cmp     rax, rbx
0x180028df7  jz      short loc_180028E0F
0x180028df9  mov     rcx, rax
0x180028dfc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028e03  nop     dword ptr [rax+rax+00h]
0x180028e08  mov     rax, rbx
0x180028e0b  mov     [rbp+0C0h+var_B0], rbx
0x180028e0f  test    rax, rax
0x180028e12  jz      loc_18002901E
0x180028e18  mov     rcx, rdi; Size
0x180028e1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028e20  mov     rbx, rax
0x180028e23  test    rax, rax
0x180028e26  jz      short loc_180028E30
0x180028e28  mov     dword ptr [rax], 1
0x180028e2e  jmp     short loc_180028E32
0x180028e30  xor     ebx, ebx
0x180028e32  mov     rax, [rbp+0C0h+var_F0]
0x180028e36  cmp     rax, rbx
0x180028e39  jz      short loc_180028E51
0x180028e3b  mov     rcx, rax
0x180028e3e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028e45  nop     dword ptr [rax+rax+00h]
0x180028e4a  mov     rax, rbx
0x180028e4d  mov     [rbp+0C0h+var_F0], rbx
0x180028e51  test    rax, rax
0x180028e54  jz      loc_18002901E
0x180028e5a  lea     rax, ??_7ImpersonateUserHelper@@6B@; const ImpersonateUserHelper::`vftable'
0x180028e61  mov     [rsp+1C0h+var_188], rax
0x180028e66  mov     [rsp+1C0h+var_180], 0
0x180028e6b  xor     eax, eax
0x180028e6d  xorps   xmm0, xmm0
0x180028e70  movups  [rsp+1C0h+var_178], xmm0
0x180028e75  mov     [rsp+1C0h+var_168], eax
0x180028e79  mov     rdx, r14; Src
0x180028e7c  lea     rcx, [rsp+1C0h+var_178]; this
0x180028e81  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180028e86  mov     ebx, eax
0x180028e88  test    eax, eax
0x180028e8a  jns     loc_180028F7D
0x180028e90  mov     rcx, [rbp+0C8h]; this
0x180028e97  mov     r9d, eax; char *
0x180028e9a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028ea1  mov     edx, 52h ; 'R'; void *
0x180028ea6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028eab  mov     rcx, [rbp+0C8h]; this
0x180028eb2  mov     r9d, ebx; char *
0x180028eb5  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028ebc  mov     edx, 43h ; 'C'; void *
0x180028ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ec6  mov     eax, cs:dword_1800950A0
0x180028ecc  cmp     eax, 5
0x180028ecf  jbe     short loc_180028F3F
0x180028ed1  mov     rcx, cs:qword_1800950B8
0x180028ed8  mov     rax, cs:qword_1800950B0
0x180028edf  mov     rdx, 400000000000h
0x180028ee9  test    rdx, rax
0x180028eec  jz      short loc_180028F3F
0x180028eee  mov     rax, rcx
0x180028ef1  and     rax, rdx
0x180028ef4  cmp     rax, rcx
0x180028ef7  jnz     short loc_180028F3F
0x180028ef9  mov     [rsp+1C0h+var_190], ebx
0x180028efd  lea     rax, [rsp+1C0h+var_190]
0x180028f02  mov     [rbp+0C0h+var_30], rax
0x180028f09  mov     [rbp+0C0h+var_28], 4
0x180028f14  lea     rax, [rbp+0C0h+var_50]
0x180028f18  mov     [rsp+1C0h+var_198], rax
0x180028f1d  mov     [rsp+1C0h+var_1A0], 3; int
0x180028f25  xor     r9d, r9d
0x180028f28  xor     r8d, r8d
0x180028f2b  lea     rdx, byte_18008853F
0x180028f32  lea     rcx, dword_1800950A0
0x180028f39  call    _tlgWriteTransfer_EventWriteTransfer
0x180028f3e  nop
0x180028f3f  cmp     [rsp+1C0h+var_180], 0
0x180028f44  jz      short loc_180028F61
0x180028f46  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180028f4d  nop     dword ptr [rax+rax+00h]
0x180028f52  mov     rcx, [rbp+0C8h]; this
0x180028f59  test    eax, eax
0x180028f5b  js      loc_180029065
0x180028f61  mov     rcx, qword ptr [rsp+1C0h+var_178+8]
0x180028f66  test    rcx, rcx
0x180028f69  jz      short loc_180028F78
0x180028f6b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028f72  nop     dword ptr [rax+rax+00h]
0x180028f77  nop
0x180028f78  jmp     loc_180029023
0x180028f7d  lea     rcx, [rsp+1C0h+var_188]; this
0x180028f82  call    ?ImpersonateUser@ImpersonateUserHelper@@QEAAJXZ; ImpersonateUserHelper::ImpersonateUser(void)
0x180028f87  mov     ebx, eax
0x180028f89  test    eax, eax
0x180028f8b  jns     short loc_180028FA8
0x180028f8d  mov     rcx, [rbp+0C8h]; this
0x180028f94  mov     r9d, eax; char *
0x180028f97  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028f9e  mov     edx, 44h ; 'D'; void *
0x180028fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028fa8  test    ebx, ebx
0x180028faa  js      loc_180028EC6
0x180028fb0  mov     rdx, 0FFFFFFFF80000001h; struct EnterpriseModernAppManagement::tagProductInfo *
0x180028fb7  lea     rcx, [rsp+1C0h+var_160]; this
0x180028fbc  call    ?AddProductInfo@EnterpriseModernAppManagement@@YAJAEBUtagProductInfo@1@PEAUHKEY__@@@Z; EnterpriseModernAppManagement::AddProductInfo(EnterpriseModernAppManagement::tagProductInfo const &,HKEY__ *)
0x180028fc1  mov     ebx, eax
0x180028fc3  mov     rcx, [rbp+0C8h]; this
0x180028fca  test    eax, eax
0x180028fcc  jns     loc_180028F3F
0x180028fd2  mov     r9d, eax; char *
0x180028fd5  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028fdc  mov     edx, 18Bh; void *
0x180028fe1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028fe6  nop
0x180028fe7  cmp     [rsp+1C0h+var_180], 0
0x180028fec  jz      short loc_180029005
0x180028fee  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x180028ff5  nop     dword ptr [rax+rax+00h]
0x180028ffa  mov     rcx, [rbp+0C8h]; this
0x180029001  test    eax, eax
0x180029003  js      short loc_180029057
0x180029005  mov     rcx, qword ptr [rsp+1C0h+var_178+8]
0x18002900a  test    rcx, rcx
0x18002900d  jz      short loc_18002901C
0x18002900f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180029016  nop     dword ptr [rax+rax+00h]
0x18002901b  nop
0x18002901c  jmp     short loc_180029023
0x18002901e  mov     ebx, 8007000Eh
0x180029023  lea     rcx, [rsp+1C0h+var_160]; this
0x180029028  call    ??1tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo(void)
0x18002902d  mov     eax, ebx
0x18002902f  mov     rcx, [rbp+0C0h+var_20]
0x180029036  xor     rcx, rsp; StackCookie
0x180029039  call    __security_check_cookie
0x18002903e  lea     r11, [rsp+1C0h+var_10]
0x180029046  mov     rbx, [r11+30h]
0x18002904a  mov     rsi, [r11+38h]
0x18002904e  mov     rsp, r11
0x180029051  pop     r14
0x180029053  pop     rdi
0x180029054  pop     rbp
0x180029055  retn
0x180029057  mov     r9d, eax; char *
0x18002905a  mov     edx, 4Bh ; 'K'; void *
0x18002905f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180029065  mov     r9d, eax; char *
0x180029068  mov     edx, 4Bh ; 'K'; void *
0x18002906d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
