# AppxAllUserStore::Internal::RestoreOneFolderPath(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,ushort const *,bool &)

- ea: `0x1800357a0`
- end: `0x180035bc1`
- name: `?RestoreOneFolderPath@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG11AEA_N@Z`
- size: `1057`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *this, struct AppxAllUserStore::BasicLogFile *Src, wchar_t *SubStr, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180035140`

## callees

- `0x180001a70`
- `0x180004920`
- `0x180004b4c`
- `0x180008db0`
- `0x18000ed34`
- `0x180012c3c`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x180033dcc`
- `0x1800357a0`
- `0x18003650c`
- `0x18004abe4`

## import_xrefs

- `msvcrt!wcsstr` at `0x180035838`
- `msvcrt!wcsstr` at `0x1800359b1`
- `msvcrt!wcsstr` at `0x180035838`
- `msvcrt!wcsstr` at `0x1800359b1`
- `msvcrt!_wcslwr` at `0x18003582b`
- `msvcrt!_wcslwr` at `0x1800359a4`
- `msvcrt!_wcslwr` at `0x18003582b`
- `msvcrt!_wcslwr` at `0x1800359a4`

## string_xrefs

- `0x180035854`: `Path %ls.`
- `0x1800357da`: `In RestoreOneFolderPath %ls %ls %ls %u.`
- `0x180035940`: `Path suffix %ls.`
- `0x1800359ba`: `Path %ls %u.`
- `0x180035a41`: `ProcessDeletedAllUserPackagesFolder %ls %ls, 0x%0x.`
- `0x180035b50`: `Hardlinking %ls to %ls got 0x%0x.`
- `0x180035ba6`: `Src path %ls, dst path %ls.`
- `0x18003595a`: `\DeletedAllUserPackages`
- `0x180035ad6`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::RestoreOneFolderPath(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *Src,
        wchar_t *SubStr,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v5; // r15
  int v10; // eax
  int appended; // ebx
  __int64 v12; // rdx
  struct Common::StringBuffer *v13; // rdx
  wchar_t *v14; // rsi
  int v15; // eax
  int v16; // eax
  bool *v17; // r8
  int v18; // eax
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  bool v21; // al
  int v22; // eax
  struct Common::StringBuffer *v23; // r9
  Common::Deployment *v24; // rbx
  unsigned int v25; // eax
  int v26; // eax
  int v28; // eax
  const struct _tlgProvider_t *v29; // rax
  int v30; // r8d
  int v31; // r9d
  int v32; // eax
  const unsigned __int16 *v33; // [rsp+20h] [rbp-61h]
  int v34; // [rsp+20h] [rbp-61h]
  Common::Deployment *v35; // [rsp+40h] [rbp-41h] BYREF
  struct AppxAllUserStore::BasicLogFile *v36; // [rsp+48h] [rbp-39h] BYREF
  Common::Deployment *v37[2]; // [rsp+50h] [rbp-31h] BYREF
  int v38; // [rsp+60h] [rbp-21h]
  wchar_t *SubStra[2]; // [rsp+68h] [rbp-19h] BYREF
  int v40; // [rsp+78h] [rbp-9h]
  wchar_t *String[2]; // [rsp+80h] [rbp-1h] BYREF
  int v42; // [rsp+90h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v5 = a5;
  v33 = a4;
  v10 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In RestoreOneFolderPath %ls %ls %ls %u.", Src, SubStr);
  if ( v10 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8BF,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v10,
      (int)v33);
  v42 = 0;
  *(_OWORD *)String = 0;
  appended = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)String, (const unsigned __int16 *)Src);
  if ( appended >= 0 )
  {
    _wcslwr(String[1]);
    v14 = wcsstr(String[1], SubStr);
    if ( !v14 )
    {
      appended = -2147023728;
      v12 = 2247;
      goto LABEL_7;
    }
    v38 = 0;
    *(_OWORD *)v37 = 0;
    if ( a4 )
    {
      appended = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)v37, a4);
      if ( appended < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x8D3,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)appended,
          (int)"SystemRoot %ls.",
          (const char *)a4);
        goto LABEL_13;
      }
    }
    else
    {
      v15 = AppxAllUserStore::Internal::SetCurrentSystemRootPrefix((AppxAllUserStore::Internal *)v37, v13);
      appended = v15;
      if ( v15 < 0 )
      {
        v16 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"SetCurrentSystemRootPrefix failed, 0x%0x.",
                (unsigned int)v15);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8CF,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v16,
            (int)v33);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8CF,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)appended,
          (int)v33);
        goto LABEL_13;
      }
    }
    appended = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v37, v14);
    if ( appended < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x8D6,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)appended,
        (int)"Path suffix %ls.",
        (const char *)v14);
LABEL_13:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v37);
      goto LABEL_32;
    }
    if ( !*(_BYTE *)v5 )
    {
      v40 = 0;
      *(_OWORD *)SubStra = 0;
      v18 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)SubStra, L"\\DeletedAllUserPackages");
      appended = v18;
      if ( v18 < 0 )
      {
        v19 = (unsigned int)v18;
        v20 = 2268;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)v19,
          (int)v33);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)SubStra);
        goto LABEL_13;
      }
      _wcslwr(SubStra[1]);
      v21 = wcsstr(v14, SubStra[1]) != 0;
      *(_BYTE *)v5 = v21;
      v22 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Path %ls %u.", v14, v21);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x8E0,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v22,
          (int)v33);
      if ( *(_BYTE *)v5 )
      {
        v24 = v37[1];
        v25 = AppxAllUserStore::Internal::ProcessDeletedAllUserPackagesFolder(
                this,
                Src,
                (const unsigned __int16 *)v37,
                v23);
        LODWORD(v33) = wil::details::in1diag3::Log_IfFailedMsg(
                         retaddr,
                         (void *)0x8E6,
                         (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                         (const char *)v25,
                         (__int64)"Folder %ls target %ls.",
                         (const char *)Src,
                         v24);
        appended = (int)v33;
        v26 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"ProcessDeletedAllUserPackagesFolder %ls %ls, 0x%0x.",
                Src,
                v37[1]);
        if ( v26 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8E8,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v26,
            (int)v33);
        if ( appended < 0 )
        {
          v19 = (unsigned int)appended;
          v20 = 2281;
          goto LABEL_22;
        }
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)SubStra);
LABEL_31:
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v37);
        appended = 0;
        goto LABEL_32;
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)SubStra);
    }
    v28 = Common::Deployment::HardlinkDirectoryTree(Src, v37[1], v17);
    appended = v28;
    if ( v28 >= 0 )
    {
      appended = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
        (const char *)(unsigned int)v28,
        (int)v33);
      v29 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v29 > 5u && (unsigned __int8)tlgKeywordOn(v29, 0x400000000000LL, v29) )
      {
        v35 = v37[1];
        v36 = Src;
        LODWORD(a5) = appended;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v30,
          (unsigned int)&dword_18005D034,
          v30,
          v31,
          (__int64)&a5,
          (__int64)&v36,
          (__int64)&v35);
      }
    }
    LODWORD(v33) = appended;
    v32 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Hardlinking %ls to %ls got 0x%0x.", Src, v37[1], v33);
    if ( v32 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8FE,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v32,
        v34);
    if ( appended < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x8FF,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)appended,
        (int)"Src path %ls, dst path %ls.",
        (const char *)Src,
        v37[1]);
      goto LABEL_13;
    }
    goto LABEL_31;
  }
  v12 = 2243;
LABEL_7:
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)(unsigned int)appended,
    (int)"Path %ls.",
    (const char *)Src);
LABEL_32:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800357a0  push    rbp
0x1800357a2  push    rbx
0x1800357a3  push    rsi
0x1800357a4  push    rdi
0x1800357a5  push    r12
0x1800357a7  push    r14
0x1800357a9  push    r15
0x1800357ab  lea     rbp, [rsp-1Fh]
0x1800357b0  sub     rsp, 0A0h
0x1800357b7  mov     r15, [rbp+4Fh+arg_20]
0x1800357bb  mov     r14, r9
0x1800357be  mov     rsi, r8
0x1800357c1  mov     rdi, rdx
0x1800357c4  mov     r12, rcx
0x1800357c7  movzx   eax, byte ptr [r15]
0x1800357cb  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800357cf  mov     [rsp+0D0h+var_B0], r9; int
0x1800357d4  mov     r9, r8
0x1800357d7  mov     r8, rdx
0x1800357da  lea     rdx, aInRestoreonefo; "In RestoreOneFolderPath %ls %ls %ls %u."
0x1800357e1  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800357e6  test    eax, eax
0x1800357e8  jns     short loc_180035802
0x1800357ea  mov     rcx, [rbp+57h]; this
0x1800357ee  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800357f5  mov     r9d, eax; char *
0x1800357f8  mov     edx, 8BFh; void *
0x1800357fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035802  xor     eax, eax
0x180035804  lea     rcx, [rbp+4Fh+String]; this
0x180035808  xorps   xmm0, xmm0
0x18003580b  mov     [rbp+4Fh+var_40], eax
0x18003580e  mov     rdx, rdi; Src
0x180035811  movups  xmmword ptr [rbp+4Fh+String], xmm0
0x180035815  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18003581a  mov     ebx, eax
0x18003581c  test    eax, eax
0x18003581e  jns     short loc_180035827
0x180035820  mov     edx, 8C3h
0x180035825  jmp     short loc_180035850
0x180035827  mov     rcx, [rbp+4Fh+String+8]; String
0x18003582b  call    cs:__imp__wcslwr
0x180035831  mov     rcx, [rbp+4Fh+String+8]; Str
0x180035835  mov     rdx, rsi; SubStr
0x180035838  call    cs:__imp_wcsstr
0x18003583e  mov     rsi, rax
0x180035841  test    rax, rax
0x180035844  jnz     short loc_180035879
0x180035846  mov     ebx, 80070490h
0x18003584b  mov     edx, 8C7h; void *
0x180035850  mov     rcx, [rbp+57h]; this
0x180035854  lea     rax, aPathLs; "Path %ls."
0x18003585b  mov     [rsp+0D0h+var_A8], rdi; char *
0x180035860  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035867  mov     r9d, ebx; char *
0x18003586a  mov     [rsp+0D0h+var_B0], rax; int
0x18003586f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035874  jmp     loc_180035A9A
0x180035879  xor     eax, eax
0x18003587b  lea     rcx, [rbp+4Fh+var_80]; this
0x18003587f  mov     [rbp+4Fh+var_70], eax
0x180035882  xorps   xmm0, xmm0
0x180035885  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x180035889  test    r14, r14
0x18003588c  jnz     short loc_1800358F0
0x18003588e  call    ?SetCurrentSystemRootPrefix@Internal@AppxAllUserStore@@YAJAEAVStringBuffer@Common@@@Z; AppxAllUserStore::Internal::SetCurrentSystemRootPrefix(Common::StringBuffer &)
0x180035893  mov     ebx, eax
0x180035895  test    eax, eax
0x180035897  jns     loc_180035929
0x18003589d  mov     r8d, eax
0x1800358a0  lea     rdx, aSetcurrentsyst; "SetCurrentSystemRootPrefix failed, 0x%0"...
0x1800358a7  mov     rcx, r12; this
0x1800358aa  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800358af  mov     edi, 8CFh
0x1800358b4  test    eax, eax
0x1800358b6  jns     short loc_1800358CD
0x1800358b8  mov     rcx, [rbp+57h]; this
0x1800358bc  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800358c3  mov     r9d, eax; char *
0x1800358c6  mov     edx, edi; void *
0x1800358c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800358cd  mov     rcx, [rbp+57h]; this
0x1800358d1  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800358d8  mov     r9d, ebx; char *
0x1800358db  mov     edx, edi; void *
0x1800358dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358e2  lea     rcx, [rbp+4Fh+var_80]; this
0x1800358e6  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800358eb  jmp     loc_180035A9A
0x1800358f0  mov     rdx, r14; Src
0x1800358f3  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800358f8  mov     ebx, eax
0x1800358fa  test    eax, eax
0x1800358fc  jns     short loc_180035929
0x1800358fe  mov     [rsp+0D0h+var_A8], r14; char *
0x180035903  lea     rax, aSystemrootLs; "SystemRoot %ls."
0x18003590a  mov     edx, 8D3h; void *
0x18003590f  mov     rcx, [rbp+57h]; this
0x180035913  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003591a  mov     r9d, ebx; char *
0x18003591d  mov     [rsp+0D0h+var_B0], rax; int
0x180035922  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035927  jmp     short loc_1800358E2
0x180035929  mov     rdx, rsi; unsigned __int16 *
0x18003592c  lea     rcx, [rbp+4Fh+var_80]; struct Common::StringBuffer *
0x180035930  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x180035935  mov     ebx, eax
0x180035937  test    eax, eax
0x180035939  jns     short loc_18003594E
0x18003593b  mov     [rsp+0D0h+var_A8], rsi
0x180035940  lea     rax, aPathSuffixLs; "Path suffix %ls."
0x180035947  mov     edx, 8D6h
0x18003594c  jmp     short loc_18003590F
0x18003594e  cmp     byte ptr [r15], 0
0x180035952  jnz     loc_180035AC0
0x180035958  xor     eax, eax
0x18003595a  lea     rdx, aDeletedalluser; "\\DeletedAllUserPackages"
0x180035961  xorps   xmm0, xmm0
0x180035964  mov     [rbp+4Fh+var_58], eax
0x180035967  lea     rcx, [rbp+4Fh+SubStr]; this
0x18003596b  movups  xmmword ptr [rbp+4Fh+SubStr], xmm0
0x18003596f  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180035974  mov     ebx, eax
0x180035976  test    eax, eax
0x180035978  jns     short loc_1800359A0
0x18003597a  mov     r9d, eax; char *
0x18003597d  mov     edx, 8DCh; void *
0x180035982  mov     rcx, [rbp+57h]; this
0x180035986  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003598d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035992  lea     rcx, [rbp+4Fh+SubStr]; this
0x180035996  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18003599b  jmp     loc_1800358E2
0x1800359a0  mov     rcx, [rbp+4Fh+SubStr+8]; String
0x1800359a4  call    cs:__imp__wcslwr
0x1800359aa  mov     rdx, [rbp+4Fh+SubStr+8]; SubStr
0x1800359ae  mov     rcx, rsi; Str
0x1800359b1  call    cs:__imp_wcsstr
0x1800359b7  mov     r8, rsi
0x1800359ba  lea     rdx, aPathLsU; "Path %ls %u."
0x1800359c1  test    rax, rax
0x1800359c4  mov     rcx, r12; this
0x1800359c7  setnz   al
0x1800359ca  movzx   r9d, al
0x1800359ce  mov     [r15], al
0x1800359d1  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800359d6  test    eax, eax
0x1800359d8  jns     short loc_1800359F2
0x1800359da  mov     rcx, [rbp+57h]; this
0x1800359de  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800359e5  mov     r9d, eax; char *
0x1800359e8  mov     edx, 8E0h; void *
0x1800359ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800359f2  cmp     byte ptr [r15], 0
0x1800359f6  jz      loc_180035AB7
0x1800359fc  mov     rbx, [rbp+4Fh+var_80+8]
0x180035a00  lea     r8, [rbp+4Fh+var_80]; unsigned __int16 *
0x180035a04  mov     rdx, rdi; Src
0x180035a07  mov     rcx, r12; this
0x180035a0a  call    ?ProcessDeletedAllUserPackagesFolder@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::Internal::ProcessDeletedAllUserPackagesFolder(AppxAllUserStore::BasicLogFile &,ushort const *,Common::StringBuffer &)
0x180035a0f  mov     rcx, [rbp+57h]; this
0x180035a13  lea     rdx, aFolderLsTarget; "Folder %ls target %ls."
0x180035a1a  mov     [rsp+0D0h+var_A0], rbx
0x180035a1f  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035a26  mov     [rsp+0D0h+var_A8], rdi; char *
0x180035a2b  mov     r9d, eax; char *
0x180035a2e  mov     [rsp+0D0h+var_B0], rdx; __int64
0x180035a33  mov     edx, 8E6h; void *
0x180035a38  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180035a3d  mov     r9, [rbp+4Fh+var_80+8]
0x180035a41  lea     rdx, aProcessdeleted_0; "ProcessDeletedAllUserPackagesFolder %ls"...
0x180035a48  mov     r8, rdi
0x180035a4b  mov     dword ptr [rsp+0D0h+var_B0], eax; int
0x180035a4f  mov     rcx, r12; this
0x180035a52  mov     ebx, eax
0x180035a54  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035a59  test    eax, eax
0x180035a5b  jns     short loc_180035A75
0x180035a5d  mov     rcx, [rbp+57h]; this
0x180035a61  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035a68  mov     r9d, eax; char *
0x180035a6b  mov     edx, 8E8h; void *
0x180035a70  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035a75  test    ebx, ebx
0x180035a77  jns     short loc_180035A86
0x180035a79  mov     r9d, ebx
0x180035a7c  mov     edx, 8E9h
0x180035a81  jmp     loc_180035982
0x180035a86  lea     rcx, [rbp+4Fh+SubStr]; this
0x180035a8a  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180035a8f  lea     rcx, [rbp+4Fh+var_80]; this
0x180035a93  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180035a98  xor     ebx, ebx
0x180035a9a  lea     rcx, [rbp+4Fh+String]; this
0x180035a9e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180035aa3  mov     eax, ebx
0x180035aa5  add     rsp, 0A0h
0x180035aac  pop     r15
0x180035aae  pop     r14
0x180035ab0  pop     r12
0x180035ab2  pop     rdi
0x180035ab3  pop     rsi
0x180035ab4  pop     rbx
0x180035ab5  pop     rbp
0x180035ab6  retn
0x180035ab7  lea     rcx, [rbp+4Fh+SubStr]; this
0x180035abb  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180035ac0  mov     rdx, [rbp+4Fh+var_80+8]; Common::Deployment *
0x180035ac4  mov     rcx, rdi; this
0x180035ac7  call    ?HardlinkDirectoryTree@Deployment@Common@@YAJPEBG0_N@Z; Common::Deployment::HardlinkDirectoryTree(ushort const *,ushort const *,bool)
0x180035acc  mov     ebx, eax
0x180035ace  test    eax, eax
0x180035ad0  jns     short loc_180035B4A
0x180035ad2  mov     rcx, [rbp+57h]; this
0x180035ad6  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x180035add  mov     r9d, eax; char *
0x180035ae0  mov     edx, 9Fh; void *
0x180035ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035aea  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180035aef  mov     r8, rax
0x180035af2  mov     ecx, [rax]
0x180035af4  cmp     ecx, 5
0x180035af7  jbe     short loc_180035B4C
0x180035af9  mov     rdx, 400000000000h
0x180035b03  mov     rcx, rax
0x180035b06  call    _tlgKeywordOn
0x180035b0b  test    al, al
0x180035b0d  jz      short loc_180035B4C
0x180035b0f  mov     rcx, [rbp+4Fh+var_80+8]
0x180035b13  lea     rax, [rbp+4Fh+var_90]
0x180035b17  mov     [rsp+0D0h+var_A0], rax
0x180035b1c  lea     rdx, dword_18005D034
0x180035b23  lea     rax, [rbp+4Fh+var_88]
0x180035b27  mov     [rbp+4Fh+var_90], rcx
0x180035b2b  mov     [rsp+0D0h+var_A8], rax
0x180035b30  mov     rcx, r8
0x180035b33  lea     rax, [rbp+4Fh+arg_20]
0x180035b37  mov     [rbp+4Fh+var_88], rdi
0x180035b3b  mov     [rsp+0D0h+var_B0], rax
0x180035b40  mov     dword ptr [rbp+4Fh+arg_20], ebx
0x180035b43  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180035b48  jmp     short loc_180035B4C
0x180035b4a  xor     ebx, ebx
0x180035b4c  mov     r9, [rbp+4Fh+var_80+8]
0x180035b50  lea     rdx, aHardlinkingLsT; "Hardlinking %ls to %ls got 0x%0x."
0x180035b57  mov     r8, rdi
0x180035b5a  mov     dword ptr [rsp+0D0h+var_B0], ebx; int
0x180035b5e  mov     rcx, r12; this
0x180035b61  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035b66  test    eax, eax
0x180035b68  jns     short loc_180035B82
0x180035b6a  mov     rcx, [rbp+57h]; this
0x180035b6e  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035b75  mov     r9d, eax; char *
0x180035b78  mov     edx, 8FEh; void *
0x180035b7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035b82  test    ebx, ebx
0x180035b84  jns     loc_180035A8F
0x180035b8a  mov     rax, [rbp+4Fh+var_80+8]
0x180035b8e  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035b95  mov     rcx, [rbp+57h]; this
0x180035b99  mov     r9d, ebx; char *
0x180035b9c  mov     [rsp+0D0h+var_A0], rax
0x180035ba1  mov     edx, 8FFh; void *
0x180035ba6  lea     rax, aSrcPathLsDstPa; "Src path %ls, dst path %ls."
0x180035bad  mov     [rsp+0D0h+var_A8], rdi; char *
0x180035bb2  mov     [rsp+0D0h+var_B0], rax; int
0x180035bb7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035bbc  jmp     loc_1800358E2
```
