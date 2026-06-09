# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments(ushort const *,Common::StringBuffer &,Common::StringBuffer &)

- ea: `0x140008ec8`
- end: `0x140009307`
- name: `?GetApplicationAndArguments@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@IEAAXPEBGAEAVStringBuffer@Common@@1@Z`
- size: `1087`
- prototype: `void __fastcall(const unsigned __int16 **this, const unsigned __int16 *, struct Common::StringBuffer *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140008bc4`

## callees

- `0x140007d78`
- `0x14000859c`
- `0x140008610`
- `0x140008ec8`
- `0x140009310`
- `0x14000e1e8`
- `0x14000e708`
- `0x14000e780`

## string_xrefs

- `0x140008f4f`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140008f7f`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140008fa8`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140008fd5`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140008fff`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009025`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x14000904f`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009086`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400090b4`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400090e2`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009110`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x14000915b`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009181`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400091aa`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400091d7`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009201`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009227`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009254`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009287`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400092b1`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetApplicationAndArguments(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        struct Common::StringBuffer *a3,
        struct Common::StringBuffer *a4)
{
  int v8; // eax
  unsigned __int16 v9; // dx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned __int16 v14; // dx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  const unsigned __int16 *MsiExecPath; // rax
  int appended; // eax
  const unsigned __int16 *v21; // rax
  int v22; // eax
  const unsigned __int16 *v23; // rdx
  int v24; // eax
  unsigned __int16 v25; // dx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned __int16 v30; // dx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  _QWORD v35[3]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v36[3]; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v37[2]; // [rsp+50h] [rbp-30h] BYREF
  int v38; // [rsp+60h] [rbp-20h]
  __int128 v39; // [rsp+68h] [rbp-18h] BYREF
  int v40; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v42; // [rsp+A0h] [rbp+20h] BYREF

  *(_OWORD *)v37 = 0;
  v38 = 0;
  v36[1] = v37;
  v36[0] = &Common::StringBufferBuilder::`vftable';
  v36[2] = v37;
  v39 = 0;
  v40 = 0;
  v35[1] = &v39;
  v35[0] = &Common::StringBufferBuilder::`vftable';
  v35[2] = &v39;
  v42 = 0;
  v8 = Common::String::CaseInsensitiveEndsWith(this[4], a2, &v42);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v8,
      v35[0]);
  if ( v42 )
  {
    MsiExecPath = OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetMsiExecPath();
    appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v36, MsiExecPath);
    if ( appended < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)appended,
        v35[0]);
    v21 = OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetMsiExecPath();
    v22 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, v21);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v22,
        v35[0]);
    if ( *((_DWORD *)this + 20) == 2 )
    {
      v23 = L" /feums ";
    }
    else
    {
      v23 = L" /x ";
      if ( *((_DWORD *)this + 20) != 1 )
        v23 = L" /i ";
    }
    v24 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, v23);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v24,
        v35[0]);
    v26 = Common::StringBuilder::AppendChar((Common::StringBuilder *)v35, v25);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x105,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v26,
        v35[0]);
    v27 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, a2);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v27,
        v35[0]);
    v28 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, L"\\");
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v28,
        v35[0]);
    v29 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, this[4]);
    if ( v29 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v29,
        v35[0]);
    v31 = Common::StringBuilder::AppendChar((Common::StringBuilder *)v35, v30);
    if ( v31 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v31,
        v35[0]);
    v32 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, &qword_140010DA8);
    if ( v32 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v32,
        v35[0]);
    if ( *((_DWORD *)this + 12) )
    {
      v33 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, L" ");
      if ( v33 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x111,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
          (const char *)(unsigned int)v33,
          v35[0]);
      v34 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, this[7]);
      if ( v34 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x112,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
          (const char *)(unsigned int)v34,
          v35[0]);
    }
  }
  else
  {
    v10 = Common::StringBuilder::AppendChar((Common::StringBuilder *)v36, v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE2,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v10,
        v35[0]);
    v11 = Common::StringBuilder::AppendString((Common::StringBuilder *)v36, a2);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v11,
        v35[0]);
    v12 = Common::StringBuilder::AppendString((Common::StringBuilder *)v36, L"\\");
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v12,
        v35[0]);
    v13 = Common::StringBuilder::AppendString((Common::StringBuilder *)v36, this[4]);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE5,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v13,
        v35[0]);
    v15 = Common::StringBuilder::AppendChar((Common::StringBuilder *)v36, v14);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v15,
        v35[0]);
    v16 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, v37[1]);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v16,
        v35[0]);
    if ( *((_DWORD *)this + 12) )
    {
      v17 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, L" ");
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
          (const char *)(unsigned int)v17,
          v35[0]);
      v18 = Common::StringBuilder::AppendString((Common::StringBuilder *)v35, this[7]);
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
          (const char *)(unsigned int)v18,
          v35[0]);
    }
  }
  Common::StringBuffer::operator=(a3, v37);
  Common::StringBuffer::operator=(a4, &v39);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v39);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v37);
}

```

## disassembly

```asm
0x140008ec8  mov     [rsp-18h+arg_8], rbx
0x140008ecd  mov     [rsp-18h+arg_10], rsi
0x140008ed2  push    rbp
0x140008ed3  push    rdi
0x140008ed4  push    r14
0x140008ed6  mov     rbp, rsp
0x140008ed9  sub     rsp, 80h
0x140008ee0  mov     rsi, r9
0x140008ee3  mov     r14, r8
0x140008ee6  mov     rdi, rdx
0x140008ee9  mov     rbx, rcx
0x140008eec  xor     eax, eax
0x140008eee  xorps   xmm0, xmm0
0x140008ef1  movups  xmmword ptr [rbp+var_30], xmm0
0x140008ef5  mov     [rbp+var_20], eax
0x140008ef8  lea     rax, [rbp+var_30]
0x140008efc  mov     [rbp+var_40], rax
0x140008f00  lea     rcx, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x140008f07  mov     [rbp+var_48], rcx
0x140008f0b  lea     rax, [rbp+var_30]
0x140008f0f  mov     [rbp+var_38], rax
0x140008f13  xor     eax, eax
0x140008f15  movups  [rbp+var_18], xmm0
0x140008f19  mov     [rbp+var_8], eax
0x140008f1c  lea     rax, [rbp+var_18]
0x140008f20  mov     [rbp+var_58], rax
0x140008f24  mov     [rbp+var_60], rcx
0x140008f28  lea     rax, [rbp+var_18]
0x140008f2c  mov     [rbp+var_50], rax
0x140008f30  mov     [rbp+arg_0], 0
0x140008f37  lea     r8, [rbp+arg_0]; int *
0x140008f3b  mov     rcx, [rbx+20h]; unsigned __int16 *
0x140008f3f  call    ?CaseInsensitiveEndsWith@String@Common@@SAJPEBG0PEAH@Z; Common::String::CaseInsensitiveEndsWith(ushort const *,ushort const *,int *)
0x140008f44  mov     rcx, [rbp+18h]; this
0x140008f48  test    eax, eax
0x140008f4a  jns     short loc_140008F61
0x140008f4c  mov     r9d, eax; char *
0x140008f4f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008f56  mov     edx, 4Fh ; 'O'; void *
0x140008f5b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008f61  cmp     [rbp+arg_0], 0
0x140008f65  jnz     loc_1400090C6
0x140008f6b  lea     rcx, [rbp+var_48]; this
0x140008f6f  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x140008f74  mov     rcx, [rbp+18h]; this
0x140008f78  test    eax, eax
0x140008f7a  jns     short loc_140008F91
0x140008f7c  mov     r9d, eax; char *
0x140008f7f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008f86  mov     edx, 0E2h; void *
0x140008f8b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008f91  mov     rdx, rdi; unsigned __int16 *
0x140008f94  lea     rcx, [rbp+var_48]; this
0x140008f98  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140008f9d  mov     rcx, [rbp+18h]; this
0x140008fa1  test    eax, eax
0x140008fa3  jns     short loc_140008FBA
0x140008fa5  mov     r9d, eax; char *
0x140008fa8  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008faf  mov     edx, 0E3h; void *
0x140008fb4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008fba  lea     rdx, asc_140010DA0; "\\"
0x140008fc1  lea     rcx, [rbp+var_48]; this
0x140008fc5  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140008fca  mov     rcx, [rbp+18h]; this
0x140008fce  test    eax, eax
0x140008fd0  jns     short loc_140008FE7
0x140008fd2  mov     r9d, eax; char *
0x140008fd5  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008fdc  mov     edx, 0E4h; void *
0x140008fe1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008fe7  mov     rdx, [rbx+20h]; unsigned __int16 *
0x140008feb  lea     rcx, [rbp+var_48]; this
0x140008fef  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140008ff4  mov     rcx, [rbp+18h]; this
0x140008ff8  test    eax, eax
0x140008ffa  jns     short loc_140009011
0x140008ffc  mov     r9d, eax; char *
0x140008fff  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009006  mov     edx, 0E5h; void *
0x14000900b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009011  lea     rcx, [rbp+var_48]; this
0x140009015  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x14000901a  mov     rcx, [rbp+18h]; this
0x14000901e  test    eax, eax
0x140009020  jns     short loc_140009037
0x140009022  mov     r9d, eax; char *
0x140009025  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000902c  mov     edx, 0E6h; void *
0x140009031  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009037  mov     rdx, [rbp+var_30+8]; unsigned __int16 *
0x14000903b  lea     rcx, [rbp+var_60]; this
0x14000903f  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140009044  mov     rcx, [rbp+18h]; this
0x140009048  test    eax, eax
0x14000904a  jns     short loc_140009061
0x14000904c  mov     r9d, eax; char *
0x14000904f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009056  mov     edx, 0E9h; void *
0x14000905b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009061  cmp     dword ptr [rbx+30h], 0
0x140009065  jbe     loc_1400092C3
0x14000906b  lea     rdx, asc_140011074; " "
0x140009072  lea     rcx, [rbp+var_60]; this
0x140009076  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x14000907b  mov     rcx, [rbp+18h]; this
0x14000907f  test    eax, eax
0x140009081  jns     short loc_140009098
0x140009083  mov     r9d, eax; char *
0x140009086  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000908d  mov     edx, 0EDh; void *
0x140009092  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009098  mov     rdx, [rbx+38h]; unsigned __int16 *
0x14000909c  lea     rcx, [rbp+var_60]; this
0x1400090a0  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400090a5  mov     rcx, [rbp+18h]; this
0x1400090a9  test    eax, eax
0x1400090ab  jns     loc_1400092C3
0x1400090b1  mov     r9d, eax; char *
0x1400090b4  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400090bb  mov     edx, 0EEh; void *
0x1400090c0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400090c6  call    ?GetMsiExecPath@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@KAPEBGXZ; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetMsiExecPath(void)
0x1400090cb  mov     rdx, rax; unsigned __int16 *
0x1400090ce  lea     rcx, [rbp+var_48]; this
0x1400090d2  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400090d7  mov     rcx, [rbp+18h]; this
0x1400090db  test    eax, eax
0x1400090dd  jns     short loc_1400090F4
0x1400090df  mov     r9d, eax; char *
0x1400090e2  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400090e9  mov     edx, 0F3h; void *
0x1400090ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400090f4  call    ?GetMsiExecPath@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@KAPEBGXZ; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::GetMsiExecPath(void)
0x1400090f9  mov     rdx, rax; unsigned __int16 *
0x1400090fc  lea     rcx, [rbp+var_60]; this
0x140009100  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140009105  mov     rcx, [rbp+18h]; this
0x140009109  test    eax, eax
0x14000910b  jns     short loc_140009122
0x14000910d  mov     r9d, eax; char *
0x140009110  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009117  mov     edx, 0F6h; void *
0x14000911c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009122  cmp     dword ptr [rbx+50h], 2
0x140009126  jnz     short loc_140009131
0x140009128  lea     rdx, aFeums; " /feums "
0x14000912f  jmp     short loc_140009147
0x140009131  lea     rdx, asc_1400110E8; " /x "
0x140009138  lea     rax, aI; " /i "
0x14000913f  cmp     dword ptr [rbx+50h], 1
0x140009143  cmovnz  rdx, rax; unsigned __int16 *
0x140009147  lea     rcx, [rbp+var_60]; this
0x14000914b  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140009150  mov     rcx, [rbp+18h]; this
0x140009154  test    eax, eax
0x140009156  jns     short loc_14000916D
0x140009158  mov     r9d, eax; char *
0x14000915b  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009162  mov     edx, 103h; void *
0x140009167  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000916d  lea     rcx, [rbp+var_60]; this
0x140009171  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x140009176  mov     rcx, [rbp+18h]; this
0x14000917a  test    eax, eax
0x14000917c  jns     short loc_140009193
0x14000917e  mov     r9d, eax; char *
0x140009181  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009188  mov     edx, 105h; void *
0x14000918d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009193  mov     rdx, rdi; unsigned __int16 *
0x140009196  lea     rcx, [rbp+var_60]; this
0x14000919a  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x14000919f  mov     rcx, [rbp+18h]; this
0x1400091a3  test    eax, eax
0x1400091a5  jns     short loc_1400091BC
0x1400091a7  mov     r9d, eax; char *
0x1400091aa  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400091b1  mov     edx, 106h; void *
0x1400091b6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400091bc  lea     rdx, asc_140010DA0; "\\"
0x1400091c3  lea     rcx, [rbp+var_60]; this
0x1400091c7  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400091cc  mov     rcx, [rbp+18h]; this
0x1400091d0  test    eax, eax
0x1400091d2  jns     short loc_1400091E9
0x1400091d4  mov     r9d, eax; char *
0x1400091d7  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400091de  mov     edx, 107h; void *
0x1400091e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400091e9  mov     rdx, [rbx+20h]; unsigned __int16 *
0x1400091ed  lea     rcx, [rbp+var_60]; this
0x1400091f1  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400091f6  mov     rcx, [rbp+18h]; this
0x1400091fa  test    eax, eax
0x1400091fc  jns     short loc_140009213
0x1400091fe  mov     r9d, eax; char *
0x140009201  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009208  mov     edx, 108h; void *
0x14000920d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009213  lea     rcx, [rbp+var_60]; this
0x140009217  call    ?AppendChar@StringBuilder@Common@@QEAAJG@Z; Common::StringBuilder::AppendChar(ushort)
0x14000921c  mov     rcx, [rbp+18h]; this
0x140009220  test    eax, eax
0x140009222  jns     short loc_140009239
0x140009224  mov     r9d, eax; char *
0x140009227  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000922e  mov     edx, 109h; void *
0x140009233  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009239  lea     rdx, qword_140010DA8; unsigned __int16 *
0x140009240  lea     rcx, [rbp+var_60]; this
0x140009244  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x140009249  mov     rcx, [rbp+18h]; this
0x14000924d  test    eax, eax
0x14000924f  jns     short loc_140009266
0x140009251  mov     r9d, eax; char *
0x140009254  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000925b  mov     edx, 10Ch; void *
0x140009260  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009266  cmp     dword ptr [rbx+30h], 0
0x14000926a  jbe     short loc_1400092C3
0x14000926c  lea     rdx, asc_140011074; " "
0x140009273  lea     rcx, [rbp+var_60]; this
0x140009277  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x14000927c  mov     rcx, [rbp+18h]; this
0x140009280  test    eax, eax
0x140009282  jns     short loc_140009299
0x140009284  mov     r9d, eax; char *
0x140009287  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000928e  mov     edx, 111h; void *
0x140009293  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009299  mov     rdx, [rbx+38h]; unsigned __int16 *
0x14000929d  lea     rcx, [rbp+var_60]; this
0x1400092a1  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x1400092a6  mov     rcx, [rbp+18h]; this
0x1400092aa  test    eax, eax
0x1400092ac  jns     short loc_1400092C3
0x1400092ae  mov     r9d, eax; char *
0x1400092b1  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400092b8  mov     edx, 112h; void *
0x1400092bd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400092c3  lea     rdx, [rbp+var_30]
0x1400092c7  mov     rcx, r14
0x1400092ca  call    ??4StringBuffer@Common@@QEAAAEAV01@$$QEAV01@@Z; Common::StringBuffer::operator=(Common::StringBuffer &&)
0x1400092cf  lea     rdx, [rbp+var_18]
0x1400092d3  mov     rcx, rsi
0x1400092d6  call    ??4StringBuffer@Common@@QEAAAEAV01@$$QEAV01@@Z; Common::StringBuffer::operator=(Common::StringBuffer &&)
0x1400092db  nop
0x1400092dc  lea     rcx, [rbp+var_18]; this
0x1400092e0  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1400092e5  nop
0x1400092e6  lea     rcx, [rbp+var_30]; this
0x1400092ea  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1400092ef  lea     r11, [rsp+80h+var_s0]
0x1400092f7  mov     rbx, [r11+28h]
0x1400092fb  mov     rsi, [r11+30h]
0x1400092ff  mov     rsp, r11
0x140009302  pop     r14
0x140009304  pop     rdi
0x140009305  pop     rbp
0x140009306  retn
```
