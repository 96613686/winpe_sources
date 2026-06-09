# AppxAllUserStore::Internal::ProcessDeletedAllUserPackagesFolder(AppxAllUserStore::BasicLogFile &,ushort const *,Common::StringBuffer &)

- ea: `0x180033dcc`
- end: `0x1800340d1`
- name: `?ProcessDeletedAllUserPackagesFolder@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBGAEAVStringBuffer@Common@@@Z`
- size: `773`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *__hidden this, struct AppxAllUserStore::BasicLogFile *Src, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800357a0`

## callees

- `0x1800039e4`
- `0x180004920`
- `0x180006c00`
- `0x180008db0`
- `0x18000ed34`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x180032248`
- `0x180033908`
- `0x180033dcc`
- `0x1800467fc`

## import_xrefs

- `msvcrt!wcsstr` at `0x180033e6b`
- `msvcrt!wcsstr` at `0x180033e6b`
- `msvcrt!_wcslwr` at `0x180033e5d`
- `msvcrt!_wcslwr` at `0x180033e5d`

## string_xrefs

- `0x180033e8e`: `Path %ls.`
- `0x180033df0`: `In ProcessDeletedAllUserPackagesFolder %ls %ls.`
- `0x180033fbd`: `EnumerateDeletedAllUserPackages %ls failed, 0x%0x.`
- `0x180034051`: `MoveDeletedAllUserPackages %u packages from %ls to %ls, 0x%0x.`
- `0x180033e20`: `\DeletedAllUserPackages`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::ProcessDeletedAllUserPackagesFolder(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *Src,
        const unsigned __int16 *a3,
        struct Common::StringBuffer *a4)
{
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rax
  wchar_t *v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  int appended; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  const unsigned __int16 *v19; // rbx
  __int64 v20; // rsi
  unsigned int v21; // eax
  unsigned int v22; // edi
  int v23; // eax
  __int64 v25; // [rsp+20h] [rbp-79h]
  char *v26; // [rsp+28h] [rbp-71h]
  int v27; // [rsp+28h] [rbp-71h]
  unsigned __int16 *Srca[2]; // [rsp+40h] [rbp-59h] BYREF
  int v29; // [rsp+50h] [rbp-49h]
  __int128 v30; // [rsp+58h] [rbp-41h] BYREF
  int v31; // [rsp+68h] [rbp-31h]
  _QWORD v32[2]; // [rsp+70h] [rbp-29h] BYREF
  char *v33; // [rsp+80h] [rbp-19h]
  char v34; // [rsp+88h] [rbp-11h]
  wchar_t *String[2]; // [rsp+90h] [rbp-9h] BYREF
  int v36; // [rsp+A0h] [rbp+7h]
  _QWORD v37[9]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v7 = AppxAllUserStore::BasicLogFile::WriteMsg(
         this,
         L"In ProcessDeletedAllUserPackagesFolder %ls %ls.",
         Src,
         *((_QWORD *)a3 + 1));
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x881,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v7,
      v25);
  v36 = 0;
  *(_OWORD *)String = 0;
  v8 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)String, L"\\DeletedAllUserPackages");
  v9 = v8;
  if ( v8 >= 0 )
  {
    _wcslwr(String[1]);
    v10 = wcsstr(*((const wchar_t **)a3 + 1), String[1]);
    if ( !v10 )
    {
      v9 = -2147418113;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x88B,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Path %ls.",
        *((const char **)a3 + 1));
      goto LABEL_31;
    }
    v11 = v10 + 1;
    if ( *v10 != 92 )
      v11 = v10;
    *v11 = 0;
    v29 = 0;
    v37[1] = Srca;
    v37[0] = &Common::StringBufferBuilder::`vftable';
    v37[2] = Srca;
    *(_OWORD *)Srca = 0;
    v12 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)Srca, (const unsigned __int16 *)Src);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 2202;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v12,
        v25);
LABEL_12:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Srca);
      goto LABEL_31;
    }
    v12 = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBuffer *)Srca);
    v9 = v12;
    if ( v12 < 0 )
    {
      v13 = 2203;
      goto LABEL_11;
    }
    v30 = 0;
    v31 = 0;
    appended = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v30, Srca[1]);
    v9 = appended;
    if ( appended >= 0 )
    {
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v37, L"*");
      v9 = appended;
      if ( appended >= 0 )
      {
        v32[0] = 0;
        v32[1] = 0;
        v33 = 0;
        v34 = 1;
        v16 = AppxAllUserStore::Internal::EnumerateDeletedAllUserPackages(this);
        v9 = v16;
        if ( v16 >= 0 )
        {
          v19 = (const unsigned __int16 *)*((_QWORD *)a3 + 1);
          v20 = *((_QWORD *)&v30 + 1);
          v21 = AppxAllUserStore::Internal::MoveDeletedAllUserPackages(
                  this,
                  *((const unsigned __int16 **)&v30 + 1),
                  v19,
                  (__int64)v32);
          v22 = (unsigned int)v33;
          LODWORD(v26) = (_DWORD)v33;
          v27 = wil::details::in1diag3::Log_IfFailedMsg(
                  retaddr,
                  (void *)0x8AF,
                  (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                  (const char *)v21,
                  (__int64)"Moving %u packages from %ls to %ls.",
                  v26,
                  v20,
                  v19);
          v25 = *((_QWORD *)a3 + 1);
          v9 = v27;
          v23 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  this,
                  L"MoveDeletedAllUserPackages %u packages from %ls to %ls, 0x%0x.",
                  v22,
                  v20);
          if ( v23 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8B1,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)(unsigned int)v23,
              v25);
          if ( v27 >= 0 )
          {
            Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(v32);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v30);
            Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Srca);
            v9 = 0;
            goto LABEL_31;
          }
          v18 = 2226;
        }
        else
        {
          v17 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  this,
                  L"EnumerateDeletedAllUserPackages %ls failed, 0x%0x.",
                  Srca[1],
                  (unsigned int)v16);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8A6,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)(unsigned int)v17,
              v25);
          v18 = 2214;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)v9,
          v25);
        Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(v32);
        goto LABEL_18;
      }
      v15 = 2208;
    }
    else
    {
      v15 = 2207;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)appended,
      v25);
LABEL_18:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v30);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x885,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)(unsigned int)v8,
    v25);
LABEL_31:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
  return v9;
}

```

## disassembly

```asm
0x180033dcc  push    rbp
0x180033dce  push    rbx
0x180033dcf  push    rsi
0x180033dd0  push    rdi
0x180033dd1  push    r13
0x180033dd3  push    r14
0x180033dd5  push    r15
0x180033dd7  lea     rbp, [rsp-27h]
0x180033ddc  sub     rsp, 0C0h
0x180033de3  mov     r9, [r8+8]
0x180033de7  mov     r15, r8
0x180033dea  mov     r8, rdx
0x180033ded  mov     rdi, rdx
0x180033df0  lea     rdx, aInProcessdelet; "In ProcessDeletedAllUserPackagesFolder "...
0x180033df7  mov     r14, rcx
0x180033dfa  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033dff  lea     r13, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180033e06  test    eax, eax
0x180033e08  jns     short loc_180033E1E
0x180033e0a  mov     rcx, [rbp+5Fh]; this
0x180033e0e  mov     r9d, eax; char *
0x180033e11  mov     r8, r13; unsigned int
0x180033e14  mov     edx, 881h; void *
0x180033e19  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033e1e  xor     eax, eax
0x180033e20  lea     rdx, aDeletedalluser; "\\DeletedAllUserPackages"
0x180033e27  xorps   xmm0, xmm0
0x180033e2a  mov     [rbp+57h+var_50], eax
0x180033e2d  lea     rcx, [rbp+57h+String]; this
0x180033e31  movups  xmmword ptr [rbp+57h+String], xmm0
0x180033e35  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180033e3a  mov     ebx, eax
0x180033e3c  test    eax, eax
0x180033e3e  jns     short loc_180033E59
0x180033e40  mov     rcx, [rbp+5Fh]; this
0x180033e44  mov     r9d, eax; char *
0x180033e47  mov     r8, r13; unsigned int
0x180033e4a  mov     edx, 885h; void *
0x180033e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033e54  jmp     loc_1800340B4
0x180033e59  mov     rcx, [rbp+57h+String+8]; String
0x180033e5d  call    cs:__imp__wcslwr
0x180033e63  mov     rdx, [rbp+57h+String+8]; SubStr
0x180033e67  mov     rcx, [r15+8]; Str
0x180033e6b  call    cs:__imp_wcsstr
0x180033e71  test    rax, rax
0x180033e74  jnz     short loc_180033EA9
0x180033e76  mov     rax, [r15+8]
0x180033e7a  mov     ebx, 8000FFFFh
0x180033e7f  mov     rcx, [rbp+5Fh]; this
0x180033e83  mov     r9d, ebx; char *
0x180033e86  mov     [rsp+0F0h+var_C8], rax; char *
0x180033e8b  mov     r8, r13; unsigned int
0x180033e8e  lea     rax, aPathLs; "Path %ls."
0x180033e95  mov     edx, 88Bh; void *
0x180033e9a  mov     [rsp+0F0h+var_D0], rax; int
0x180033e9f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033ea4  jmp     loc_1800340B4
0x180033ea9  cmp     word ptr [rax], 5Ch ; '\'
0x180033ead  lea     rcx, [rax+2]
0x180033eb1  xorps   xmm0, xmm0
0x180033eb4  mov     rdx, rdi; Src
0x180033eb7  cmovnz  rcx, rax
0x180033ebb  xor     eax, eax
0x180033ebd  mov     [rcx], ax
0x180033ec0  lea     rcx, [rbp+57h+Src]; this
0x180033ec4  mov     [rbp+57h+var_A0], eax
0x180033ec7  lea     rax, [rbp+57h+Src]
0x180033ecb  mov     [rbp+57h+var_40], rax
0x180033ecf  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180033ed6  mov     [rbp+57h+var_48], rax
0x180033eda  lea     rax, [rbp+57h+Src]
0x180033ede  mov     [rbp+57h+var_38], rax
0x180033ee2  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180033ee6  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180033eeb  mov     ebx, eax
0x180033eed  test    eax, eax
0x180033eef  jns     short loc_180033F13
0x180033ef1  mov     edx, 89Ah; void *
0x180033ef6  mov     rcx, [rbp+5Fh]; this
0x180033efa  mov     r8, r13; unsigned int
0x180033efd  mov     r9d, eax; char *
0x180033f00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f05  lea     rcx, [rbp+57h+Src]; this
0x180033f09  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033f0e  jmp     loc_1800340B4
0x180033f13  lea     rcx, [rbp+57h+Src]; struct Common::StringBuffer *
0x180033f17  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBuffer *)
0x180033f1c  mov     ebx, eax
0x180033f1e  test    eax, eax
0x180033f20  jns     short loc_180033F29
0x180033f22  mov     edx, 89Bh
0x180033f27  jmp     short loc_180033EF6
0x180033f29  mov     rdx, [rbp+57h+Src+8]; Src
0x180033f2d  lea     rcx, [rbp+57h+var_98]; this
0x180033f31  xor     eax, eax
0x180033f33  xorps   xmm0, xmm0
0x180033f36  movups  [rbp+57h+var_98], xmm0
0x180033f3a  mov     [rbp+57h+var_88], eax
0x180033f3d  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180033f42  mov     ebx, eax
0x180033f44  test    eax, eax
0x180033f46  jns     short loc_180033F67
0x180033f48  mov     edx, 89Fh; void *
0x180033f4d  mov     rcx, [rbp+5Fh]; this
0x180033f51  mov     r8, r13; unsigned int
0x180033f54  mov     r9d, eax; char *
0x180033f57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033f5c  lea     rcx, [rbp+57h+var_98]; this
0x180033f60  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180033f65  jmp     short loc_180033F05
0x180033f67  lea     rdx, asc_180053710; "*"
0x180033f6e  lea     rcx, [rbp+57h+var_48]; this
0x180033f72  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180033f77  mov     ebx, eax
0x180033f79  test    eax, eax
0x180033f7b  jns     short loc_180033F84
0x180033f7d  mov     edx, 8A0h
0x180033f82  jmp     short loc_180033F4D
0x180033f84  lea     r8, [rbp+57h+var_80]
0x180033f88  mov     [rbp+57h+var_80], 0
0x180033f90  lea     rdx, [rbp+57h+Src]
0x180033f94  mov     [rbp+57h+var_78], 0
0x180033f9c  mov     rcx, r14; this
0x180033f9f  mov     [rbp+57h+var_70], 0
0x180033fa7  mov     [rbp+57h+var_68], 1
0x180033fab  call    ?EnumerateDeletedAllUserPackages@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@AEAVStringBuffer@Common@@AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@5@@Z; AppxAllUserStore::Internal::EnumerateDeletedAllUserPackages(AppxAllUserStore::BasicLogFile &,Common::StringBuffer &,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x180033fb0  mov     ebx, eax
0x180033fb2  mov     rcx, r14; this
0x180033fb5  test    eax, eax
0x180033fb7  jns     short loc_180034005
0x180033fb9  mov     r8, [rbp+57h+Src+8]
0x180033fbd  lea     rdx, aEnumeratedelet; "EnumerateDeletedAllUserPackages %ls fai"...
0x180033fc4  mov     r9d, eax
0x180033fc7  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180033fcc  mov     edi, 8A6h
0x180033fd1  test    eax, eax
0x180033fd3  jns     short loc_180033FE6
0x180033fd5  mov     rcx, [rbp+5Fh]; this
0x180033fd9  mov     r9d, eax; char *
0x180033fdc  mov     r8, r13; unsigned int
0x180033fdf  mov     edx, edi; void *
0x180033fe1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180033fe6  mov     edx, edi; void *
0x180033fe8  mov     rcx, [rbp+5Fh]; this
0x180033fec  mov     r8, r13; unsigned int
0x180033fef  mov     r9d, ebx; char *
0x180033ff2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ff7  lea     rcx, [rbp+57h+var_80]
0x180033ffb  call    ??1?$Array@U_SharedPackageContainerInfo@AppxAllUserStore@@V?$ContainerOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_SharedPackageContainerInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@QEAA@XZ; Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(void)
0x180034000  jmp     loc_180033F5C
0x180034005  mov     rbx, [r15+8]
0x180034009  lea     r9, [rbp+57h+var_80]
0x18003400d  mov     rsi, qword ptr [rbp+57h+var_98+8]
0x180034011  mov     r8, rbx
0x180034014  mov     rdx, rsi
0x180034017  call    ?MoveDeletedAllUserPackages@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1AEAV?$Array@GV?$ContainerOperations@GG@Common@@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@G@2@V?$ArrayOperations@GVNoKey@Common@@@2@@Common@@@Z; AppxAllUserStore::Internal::MoveDeletedAllUserPackages(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,Common::Array<ushort,Common::ContainerOperations<ushort,ushort>,Common::NoKey,Common::ContainerOperations<Common::NoKey,ushort>,Common::ArrayOperations<ushort,Common::NoKey>> &)
0x18003401c  mov     edi, dword ptr [rbp+57h+var_70]
0x18003401f  lea     rdx, aMovingUPackage; "Moving %u packages from %ls to %ls."
0x180034026  mov     rcx, [rbp+5Fh]; this
0x18003402a  mov     r9d, eax; char *
0x18003402d  mov     [rsp+0F0h+var_B8], rbx
0x180034032  mov     r8, r13; unsigned int
0x180034035  mov     [rsp+0F0h+var_C0], rsi
0x18003403a  mov     dword ptr [rsp+0F0h+var_C8], edi; char *
0x18003403e  mov     [rsp+0F0h+var_D0], rdx; __int64
0x180034043  mov     edx, 8AFh; void *
0x180034048  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003404d  mov     rcx, [r15+8]
0x180034051  lea     rdx, aMovedeletedall; "MoveDeletedAllUserPackages %u packages "...
0x180034058  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18003405c  mov     r9, rsi
0x18003405f  mov     [rsp+0F0h+var_D0], rcx; int
0x180034064  mov     r8d, edi
0x180034067  mov     rcx, r14; this
0x18003406a  mov     ebx, eax
0x18003406c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034071  test    eax, eax
0x180034073  jns     short loc_180034089
0x180034075  mov     rcx, [rbp+5Fh]; this
0x180034079  mov     r9d, eax; char *
0x18003407c  mov     r8, r13; unsigned int
0x18003407f  mov     edx, 8B1h; void *
0x180034084  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034089  test    ebx, ebx
0x18003408b  jns     short loc_180034097
0x18003408d  mov     edx, 8B2h
0x180034092  jmp     loc_180033FE8
0x180034097  lea     rcx, [rbp+57h+var_80]
0x18003409b  call    ??1?$Array@U_SharedPackageContainerInfo@AppxAllUserStore@@V?$ContainerOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@U12@@Common@@VNoKey@4@V?$ContainerOperations@VNoKey@Common@@U_SharedPackageContainerInfo@AppxAllUserStore@@@4@V?$ArrayOperations@U_SharedPackageContainerInfo@AppxAllUserStore@@VNoKey@Common@@@4@@Common@@QEAA@XZ; Common::Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>::~Array<AppxAllUserStore::_SharedPackageContainerInfo,Common::ContainerOperations<AppxAllUserStore::_SharedPackageContainerInfo,AppxAllUserStore::_SharedPackageContainerInfo>,Common::NoKey,Common::ContainerOperations<Common::NoKey,AppxAllUserStore::_SharedPackageContainerInfo>,Common::ArrayOperations<AppxAllUserStore::_SharedPackageContainerInfo,Common::NoKey>>(void)
0x1800340a0  lea     rcx, [rbp+57h+var_98]; this
0x1800340a4  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800340a9  lea     rcx, [rbp+57h+Src]; this
0x1800340ad  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800340b2  xor     ebx, ebx
0x1800340b4  lea     rcx, [rbp+57h+String]; this
0x1800340b8  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800340bd  mov     eax, ebx
0x1800340bf  add     rsp, 0C0h
0x1800340c6  pop     r15
0x1800340c8  pop     r14
0x1800340ca  pop     r13
0x1800340cc  pop     rdi
0x1800340cd  pop     rsi
0x1800340ce  pop     rbx
0x1800340cf  pop     rbp
0x1800340d0  retn
```
