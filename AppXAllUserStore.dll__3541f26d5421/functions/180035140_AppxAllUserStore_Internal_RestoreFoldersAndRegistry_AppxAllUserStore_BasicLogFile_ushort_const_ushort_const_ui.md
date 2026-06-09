# AppxAllUserStore::Internal::RestoreFoldersAndRegistry(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,uint *,ushort * * *)

- ea: `0x180035140`
- end: `0x180035797`
- name: `?RestoreFoldersAndRegistry@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1PEAIPEAPEAPEAG@Z`
- size: `1623`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *this, struct AppxAllUserStore::BasicLogFile *, struct AppxAllUserStore::BasicLogFile *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180034de8`

## callees

- `0x180001b68`
- `0x180001ca4`
- `0x180001da8`
- `0x180001e9c`
- `0x180004920`
- `0x18000ed34`
- `0x180010330`
- `0x180010360`
- `0x180012c3c`
- `0x180016878`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x1800262ec`
- `0x180035140`
- `0x1800357a0`
- `0x180035bc8`
- `0x18004252c`
- `0x18004c9d0`

## import_xrefs

- `msvcrt!wcsstr` at `0x180035328`
- `msvcrt!wcsstr` at `0x180035328`
- `msvcrt!_wcslwr` at `0x180035317`
- `msvcrt!_wcslwr` at `0x180035317`

## string_xrefs

- `0x18003534d`: `Path %ls.`
- `0x1800352ce`: `GetSystemSisPath got %ls, 0x%0x.`
- `0x180035182`: `In RestoreFoldersAndRegistry %ls %ls.`
- `0x1800353f2`: `RestoreOneFolderPath %u %ls %u got 0x%0x.`
- `0x18003560d`: `Src root %ls dst root %ls foundDeletedPackages %u.`
- `0x18003563b`: `RestoreRegistryData %u got 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::RestoreFoldersAndRegistry(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *a2,
        struct AppxAllUserStore::BasicLogFile *a3,
        const unsigned __int16 *a4,
        unsigned int *a5)
{
  int v9; // eax
  const unsigned __int16 *v10; // r8
  unsigned __int64 v11; // r13
  int v12; // eax
  unsigned int FoldersToKeepForPBRImplementation; // eax
  __int64 v14; // rbx
  int v15; // eax
  struct Common::StringBuffer *v17; // r8
  int SystemSisPath; // eax
  int v19; // eax
  wchar_t *v20; // rdx
  int v21; // edi
  char *v22; // rcx
  unsigned __int64 v23; // r12
  struct AppxAllUserStore::BasicLogFile *v24; // rbx
  unsigned int v25; // eax
  char *v26; // rbx
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // r9
  AppxAllUserStore::BasicLogFile *v30; // rbx
  int v31; // eax
  const struct _tlgProvider_t *v32; // rax
  int v33; // r8d
  int v34; // r9d
  struct AppxAllUserStore::BasicLogFile *v35; // rcx
  unsigned __int64 v36; // rax
  const struct _tlgProvider_t *v37; // rax
  int v38; // r8d
  int v39; // r9d
  int v40; // eax
  const unsigned __int16 *v41; // r9
  unsigned int v42; // edi
  unsigned int v43; // eax
  int v44; // eax
  const struct _tlgProvider_t *v45; // rax
  int v46; // r8d
  int v47; // r9d
  const struct _tlgProvider_t *v48; // rax
  int v49; // r8d
  int v50; // r9d
  unsigned __int16 *v51; // [rsp+20h] [rbp-B1h]
  int v52; // [rsp+20h] [rbp-B1h]
  int v53; // [rsp+20h] [rbp-B1h]
  bool *v54; // [rsp+28h] [rbp-A9h]
  struct AppxAllUserStore::BasicLogFile *v55; // [rsp+30h] [rbp-A1h]
  unsigned __int16 v56[2]; // [rsp+50h] [rbp-81h] BYREF
  int v57; // [rsp+54h] [rbp-7Dh] BYREF
  int v58; // [rsp+58h] [rbp-79h] BYREF
  char *v59; // [rsp+60h] [rbp-71h] BYREF
  struct AppxAllUserStore::BasicLogFile *v60; // [rsp+68h] [rbp-69h] BYREF
  wchar_t *v61; // [rsp+70h] [rbp-61h] BYREF
  char *v62; // [rsp+78h] [rbp-59h]
  AppxAllUserStore::BasicLogFile *v63; // [rsp+80h] [rbp-51h]
  unsigned int *v64; // [rsp+88h] [rbp-49h]
  bool v65[8]; // [rsp+90h] [rbp-41h] BYREF
  wchar_t *String[2]; // [rsp+98h] [rbp-39h] BYREF
  int v67; // [rsp+A8h] [rbp-29h]
  struct AppxAllUserStore::BasicLogFile *v68; // [rsp+B0h] [rbp-21h] BYREF
  struct AppxAllUserStore::BasicLogFile *v69; // [rsp+B8h] [rbp-19h] BYREF
  GUID ActivityId; // [rsp+C0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v63 = this;
  v64 = a5;
  v9 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In RestoreFoldersAndRegistry %ls %ls.", a2, a3);
  v11 = 0;
  if ( v9 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9C4,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v9,
      (int)v51);
  if ( a3 )
  {
    v12 = AppxAllUserStore::Internal::RemoveFilesAndRegistryData(this, a3, v10);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9CA,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v12,
        (int)v51);
  }
  AppxAllUserStore::ActivityIDScope::ActivityIDScope(&ActivityId);
  FoldersToKeepForPBRImplementation = AppxAllUserStore::GetFoldersToKeepForPBRImplementation(
                                        a2,
                                        a4,
                                        a5,
                                        (unsigned __int16 ***)this,
                                        (struct AppxAllUserStore::BasicLogFile *)v51);
  v14 = (unsigned int)wil::details::in1diag3::Log_IfFailedMsg(
                        retaddr,
                        (void *)0x9D5,
                        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                        (const char *)FoldersToKeepForPBRImplementation,
                        (__int64)"SystemRoot %ls.",
                        (const char *)a2);
  v15 = AppxAllUserStore::BasicLogFile::WriteMsg(
          this,
          L"GetFoldersToKeepForPBR found %u folders, 0x%0x.",
          *(unsigned int *)a4,
          v14);
  if ( v15 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9D6,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v15,
      v52);
  if ( (int)v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D7,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v14,
      v52);
    AppxAllUserStore::ActivityIDScope::~ActivityIDScope(&ActivityId);
    return (unsigned int)v14;
  }
  AppxAllUserStore::ActivityIDScope::~ActivityIDScope(&ActivityId);
  if ( *(_DWORD *)a4 && *(_QWORD *)a5 )
  {
    v67 = 0;
    *(_OWORD *)String = 0;
    SystemSisPath = AppxAllUserStore::GetSystemSisPath(a2, (Common::Deployment::Configuration *)String, v17);
    LODWORD(v14) = SystemSisPath;
    if ( SystemSisPath < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F3,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)SystemSisPath,
        v52);
    v19 = AppxAllUserStore::BasicLogFile::WriteMsg(
            this,
            L"GetSystemSisPath got %ls, 0x%0x.",
            String[1],
            (unsigned int)v14);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F4,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v19,
        v52);
    if ( (int)v14 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9F5,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v14,
        (int)"system root %ls.",
        (const char *)a2);
LABEL_53:
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
      return (unsigned int)v14;
    }
    _wcslwr(String[1]);
    v61 = wcsstr(String[1], L"\\program files");
    v20 = v61;
    if ( !v61 )
    {
      LODWORD(v14) = -2147023728;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x9FD,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)0x80070490LL,
        (int)"Path %ls.",
        (const char *)String[1]);
      goto LABEL_53;
    }
    v21 = 0;
    LOBYTE(v56[0]) = 0;
    v22 = 0;
    v62 = 0;
    v23 = 1;
    if ( *(_DWORD *)a4 )
    {
      do
      {
        v24 = *(struct AppxAllUserStore::BasicLogFile **)(*(_QWORD *)v64 + 8LL * (_QWORD)v22);
        v25 = AppxAllUserStore::Internal::RestoreOneFolderPath(v63, v24, v20, (const unsigned __int16 *)a3, v56);
        v55 = v24;
        v26 = v62;
        LODWORD(v54) = (_DWORD)v62;
        v27 = wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0xA0D,
                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                (const char *)v25,
                (__int64)"Folders[%u]=%ls, src root %ls dst root %ls.",
                (const char *)v54,
                v55,
                a2,
                a3);
        v28 = (unsigned int)v26;
        v52 = LOBYTE(v56[0]);
        v57 = v27;
        v29 = *(_QWORD *)(*(_QWORD *)v64 + 8LL * (_QWORD)v26);
        v30 = v63;
        v31 = AppxAllUserStore::BasicLogFile::WriteMsg(v63, L"RestoreOneFolderPath %u %ls %u got 0x%0x.", v28, v29);
        if ( v31 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA0F,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v31,
            v52);
        if ( v57 < 0 )
        {
          v32 = AppxAllUserStoreTelemetry::Provider();
          if ( *(_DWORD *)v32 > 5u && (unsigned __int8)tlgKeywordOn(v32, 0x400000000000LL, v32) )
          {
            *(_QWORD *)v65 = *(unsigned int *)a4;
            v59 = v62;
            v68 = a3;
            v69 = a2;
            v35 = *(struct AppxAllUserStore::BasicLogFile **)(*(_QWORD *)v64 + 8LL * (_QWORD)v62);
            v58 = v57;
            v60 = v35;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v33,
              (unsigned int)byte_18005CF85,
              v33,
              v34,
              (__int64)&v58,
              (__int64)&v60,
              (__int64)&v59,
              (__int64)v65,
              (__int64)&v69,
              (__int64)&v68);
          }
          if ( v21 >= 0 )
            v21 = v57;
        }
        else
        {
          ++v11;
        }
        v36 = *(unsigned int *)a4;
        v22 = v62 + 1;
        v20 = v61;
        v62 = v22;
      }
      while ( (unsigned __int64)v22 < v36 );
      if ( LOBYTE(v56[0]) )
        v23 = 2;
    }
    else
    {
      v30 = v63;
    }
    if ( v11 < v23 )
    {
      v37 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v37 > 5u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v37, 0x400000000000LL, v37) )
        {
          v59 = (char *)*(unsigned int *)a4;
          v61 = (wchar_t *)a3;
          v60 = a2;
          *(_QWORD *)v65 = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v38,
            (unsigned int)&unk_18005CF30,
            v38,
            v39,
            (__int64)v65,
            (__int64)&v59,
            (__int64)&v60,
            (__int64)&v61);
        }
      }
    }
    v40 = AppxAllUserStore::BasicLogFile::WriteMsg(v30, L"successCount %u.", (unsigned int)v11);
    if ( v40 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA31,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v40,
        v52);
    if ( !v11 )
    {
      if ( v21 < 0 )
      {
        LODWORD(v54) = *(_DWORD *)a4;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xA33,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v21,
          (int)"None of %u folders successfully restored to %ls?!",
          (const char *)v54,
          a3);
      }
      LODWORD(v14) = v21;
      goto LABEL_53;
    }
    v42 = LOBYTE(v56[0]);
    LOBYTE(v41) = v56[0];
    v43 = AppxAllUserStore::Internal::RestoreRegistryData(v30, a2, a3, v41, v52);
    v14 = (unsigned int)wil::details::in1diag3::Log_IfFailedMsg(
                          retaddr,
                          (void *)0xA39,
                          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                          (const char *)v43,
                          (__int64)"Src root %ls dst root %ls foundDeletedPackages %u.",
                          (const char *)a2);
    v44 = AppxAllUserStore::BasicLogFile::WriteMsg(v63, L"RestoreRegistryData %u got 0x%0x.", v42, v14);
    if ( v44 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA3B,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v44,
        v53);
    if ( (int)v14 < 0 )
    {
      v45 = AppxAllUserStoreTelemetry::Provider();
      if ( *(_DWORD *)v45 > 5u && (unsigned __int8)tlgKeywordOn(v45, 0x400000000000LL, v45) )
      {
        v59 = (char *)*(unsigned int *)a4;
        v58 = v42;
        v61 = (wchar_t *)a3;
        v60 = a2;
        v57 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v46,
          (unsigned int)&dword_18005CEBC,
          v46,
          v47,
          (__int64)&v57,
          (__int64)&v59,
          (__int64)&v60,
          (__int64)&v61,
          (__int64)&v58);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA47,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v14,
        v53);
      goto LABEL_53;
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
    return 0;
  }
  else
  {
    v48 = AppxAllUserStoreTelemetry::Provider();
    if ( *(_DWORD *)v48 > 5u && (unsigned __int8)tlgKeywordOn(v48, 0x400000000000LL, v48) )
    {
      v59 = (char *)*(unsigned int *)a4;
      v61 = (wchar_t *)a3;
      v60 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v49,
        (unsigned int)&unk_18005CFE8,
        v49,
        v50,
        (__int64)&v59,
        (__int64)&v60,
        (__int64)&v61);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x180035140  push    rbp
0x180035142  push    rbx
0x180035143  push    rsi
0x180035144  push    rdi
0x180035145  push    r12
0x180035147  push    r13
0x180035149  push    r14
0x18003514b  push    r15
0x18003514d  lea     rbp, [rsp-17h]
0x180035152  sub     rsp, 0E8h
0x180035159  mov     rax, cs:__security_cookie
0x180035160  xor     rax, rsp
0x180035163  mov     [rbp+4Fh+var_48], rax
0x180035167  mov     r12, [rbp+4Fh+arg_20]
0x18003516b  mov     r15, r9
0x18003516e  mov     r9, r8
0x180035171  mov     [rbp+4Fh+var_A0], rcx
0x180035175  mov     rsi, r8
0x180035178  mov     [rbp+4Fh+var_98], r12
0x18003517c  mov     r8, rdx
0x18003517f  mov     r14, rdx
0x180035182  lea     rdx, aInRestorefolde; "In RestoreFoldersAndRegistry %ls %ls."
0x180035189  mov     rdi, rcx
0x18003518c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035191  xor     r13d, r13d
0x180035194  lea     rbx, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003519b  test    eax, eax
0x18003519d  jns     short loc_1800351B3
0x18003519f  mov     rcx, [rbp+57h]; this
0x1800351a3  mov     r9d, eax; char *
0x1800351a6  mov     r8, rbx; unsigned int
0x1800351a9  mov     edx, 9C4h; void *
0x1800351ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800351b3  test    rsi, rsi
0x1800351b6  jz      short loc_1800351DB
0x1800351b8  mov     rdx, rsi; struct AppxAllUserStore::BasicLogFile *
0x1800351bb  mov     rcx, rdi; this
0x1800351be  call    ?RemoveFilesAndRegistryData@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG@Z; AppxAllUserStore::Internal::RemoveFilesAndRegistryData(AppxAllUserStore::BasicLogFile &,ushort const *)
0x1800351c3  test    eax, eax
0x1800351c5  jns     short loc_1800351DB
0x1800351c7  mov     rcx, [rbp+57h]; this
0x1800351cb  mov     r9d, eax; char *
0x1800351ce  mov     r8, rbx; unsigned int
0x1800351d1  mov     edx, 9CAh; void *
0x1800351d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800351db  lea     rcx, [rbp+4Fh+ActivityId]; ActivityId
0x1800351df  call    ??0ActivityIDScope@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::ActivityIDScope::ActivityIDScope(void)
0x1800351e4  mov     r9, rdi; unsigned __int16 ***
0x1800351e7  mov     r8, r12; unsigned int *
0x1800351ea  mov     rdx, r15; unsigned __int16 *
0x1800351ed  mov     rcx, r14; this
0x1800351f0  call    ?GetFoldersToKeepForPBRImplementation@AppxAllUserStore@@YAJPEBGPEAIPEAPEAPEAGPEAVBasicLogFile@1@@Z; AppxAllUserStore::GetFoldersToKeepForPBRImplementation(ushort const *,uint *,ushort * * *,AppxAllUserStore::BasicLogFile *)
0x1800351f5  mov     rcx, [rbp+57h]; this
0x1800351f9  lea     rdx, aSystemrootLs; "SystemRoot %ls."
0x180035200  mov     [rsp+120h+var_F8], r14; bool *
0x180035205  mov     r9d, eax; char *
0x180035208  mov     [rsp+120h+var_100], rdx; int
0x18003520d  mov     r8, rbx; unsigned int
0x180035210  mov     edx, 9D5h; void *
0x180035215  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003521a  mov     r8d, [r15]
0x18003521d  lea     rdx, aGetfolderstoke_0; "GetFoldersToKeepForPBR found %u folders"...
0x180035224  mov     r9d, eax
0x180035227  mov     rcx, rdi; this
0x18003522a  mov     ebx, eax
0x18003522c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035231  test    eax, eax
0x180035233  jns     short loc_18003524D
0x180035235  mov     rcx, [rbp+57h]; this
0x180035239  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180035240  mov     r9d, eax; char *
0x180035243  mov     edx, 9D6h; void *
0x180035248  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003524d  test    ebx, ebx
0x18003524f  jns     short loc_180035279
0x180035251  mov     rcx, [rbp+57h]; this
0x180035255  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003525c  mov     r9d, ebx; char *
0x18003525f  mov     edx, 9D7h; void *
0x180035264  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035269  lea     rcx, [rbp+4Fh+ActivityId]; ActivityId
0x18003526d  call    ??1ActivityIDScope@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::ActivityIDScope::~ActivityIDScope(void)
0x180035272  mov     eax, ebx
0x180035274  jmp     loc_180035777
0x180035279  lea     rcx, [rbp+4Fh+ActivityId]; ActivityId
0x18003527d  call    ??1ActivityIDScope@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::ActivityIDScope::~ActivityIDScope(void)
0x180035282  cmp     [r15], r13d
0x180035285  jz      loc_180035714
0x18003528b  cmp     [r12], r13
0x18003528f  jz      loc_180035714
0x180035295  xorps   xmm0, xmm0
0x180035298  mov     [rbp+4Fh+var_78], r13d
0x18003529c  lea     rdx, [rbp+4Fh+String]; Common::Deployment::Configuration *
0x1800352a0  mov     rcx, r14; this
0x1800352a3  movups  xmmword ptr [rbp+4Fh+String], xmm0
0x1800352a7  call    ?GetSystemSisPath@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetSystemSisPath(ushort const *,Common::StringBuffer &)
0x1800352ac  mov     ebx, eax
0x1800352ae  test    eax, eax
0x1800352b0  jns     short loc_1800352CA
0x1800352b2  mov     rcx, [rbp+57h]; this
0x1800352b6  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800352bd  mov     r9d, eax; char *
0x1800352c0  mov     edx, 9F3h; void *
0x1800352c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800352ca  mov     r8, [rbp+4Fh+String+8]
0x1800352ce  lea     rdx, aGetsystemsispa; "GetSystemSisPath got %ls, 0x%0x."
0x1800352d5  mov     r9d, ebx
0x1800352d8  mov     rcx, rdi; this
0x1800352db  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800352e0  test    eax, eax
0x1800352e2  jns     short loc_1800352FC
0x1800352e4  mov     rcx, [rbp+57h]; this
0x1800352e8  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800352ef  mov     r9d, eax; char *
0x1800352f2  mov     edx, 9F4h; void *
0x1800352f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800352fc  test    ebx, ebx
0x1800352fe  jns     short loc_180035313
0x180035300  mov     [rsp+120h+var_F8], r14
0x180035305  lea     rax, aSystemRootLs; "system root %ls."
0x18003530c  mov     edx, 9F5h
0x180035311  jmp     short loc_180035354
0x180035313  mov     rcx, [rbp+4Fh+String+8]; String
0x180035317  call    cs:__imp__wcslwr
0x18003531d  mov     rcx, [rbp+4Fh+String+8]; Str
0x180035321  lea     rdx, aProgramFiles; "\\program files"
0x180035328  call    cs:__imp_wcsstr
0x18003532e  mov     [rbp+4Fh+var_B0], rax
0x180035332  mov     rdx, rax
0x180035335  test    rax, rax
0x180035338  jnz     short loc_180035371
0x18003533a  mov     rax, [rbp+4Fh+String+8]
0x18003533e  mov     ebx, 80070490h
0x180035343  mov     [rsp+120h+var_F8], rax; char *
0x180035348  mov     edx, 9FDh; void *
0x18003534d  lea     rax, aPathLs; "Path %ls."
0x180035354  mov     rcx, [rbp+57h]; this
0x180035358  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003535f  mov     r9d, ebx; char *
0x180035362  mov     [rsp+120h+var_100], rax; int
0x180035367  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003536c  jmp     loc_1800356F9
0x180035371  xor     edi, edi
0x180035373  mov     byte ptr [rsp+120h+var_D0], r13b
0x180035378  xor     ecx, ecx
0x18003537a  mov     [rbp+4Fh+var_A8], rcx
0x18003537e  lea     r12d, [rdi+1]
0x180035382  cmp     [r15], ecx
0x180035385  jbe     loc_180035512
0x18003538b  mov     rax, [rbp+4Fh+var_98]
0x18003538f  mov     r8, rdx; SubStr
0x180035392  mov     r9, rsi; unsigned __int16 *
0x180035395  mov     rax, [rax]
0x180035398  mov     rbx, [rax+rcx*8]
0x18003539c  lea     rax, [rsp+120h+var_D0]
0x1800353a1  mov     rcx, [rbp+4Fh+var_A0]; this
0x1800353a5  mov     rdx, rbx; Src
0x1800353a8  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x1800353ad  call    ?RestoreOneFolderPath@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG11AEA_N@Z; AppxAllUserStore::Internal::RestoreOneFolderPath(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,ushort const *,bool &)
0x1800353b2  mov     rcx, [rbp+57h]; this
0x1800353b6  lea     rdx, aFoldersULsSrcR; "Folders[%u]=%ls, src root %ls dst root "...
0x1800353bd  mov     [rsp+120h+var_E0], rsi
0x1800353c2  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800353c9  mov     [rsp+120h+var_E8], r14
0x1800353ce  mov     r9d, eax; char *
0x1800353d1  mov     [rsp+120h+var_F0], rbx
0x1800353d6  mov     rbx, [rbp+4Fh+var_A8]
0x1800353da  mov     dword ptr [rsp+120h+var_F8], ebx; char *
0x1800353de  mov     [rsp+120h+var_100], rdx; __int64
0x1800353e3  mov     edx, 0A0Dh; void *
0x1800353e8  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800353ed  movzx   ecx, byte ptr [rsp+120h+var_D0]
0x1800353f2  lea     rdx, aRestoreonefold; "RestoreOneFolderPath %u %ls %u got 0x%0"...
0x1800353f9  mov     r9, [rbp+4Fh+var_98]
0x1800353fd  mov     r8d, ebx
0x180035400  mov     dword ptr [rsp+120h+var_F8], eax
0x180035404  mov     dword ptr [rsp+120h+var_100], ecx; int
0x180035408  mov     [rbp+4Fh+var_CC], eax
0x18003540b  mov     r9, [r9]
0x18003540e  mov     r9, [r9+rbx*8]
0x180035412  mov     rbx, [rbp+4Fh+var_A0]
0x180035416  mov     rcx, rbx; this
0x180035419  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x18003541e  test    eax, eax
0x180035420  jns     short loc_18003543A
0x180035422  mov     rcx, [rbp+57h]; this
0x180035426  lea     r8, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003542d  mov     r9d, eax; char *
0x180035430  mov     edx, 0A0Fh; void *
0x180035435  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003543a  cmp     [rbp+4Fh+var_CC], 0
0x18003543e  jl      short loc_180035448
0x180035440  add     r13, r12
0x180035443  jmp     loc_1800354E8
0x180035448  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x18003544d  mov     r8, rax
0x180035450  mov     ecx, [rax]
0x180035452  cmp     ecx, 5
0x180035455  jbe     loc_1800354E2
0x18003545b  mov     rdx, 400000000000h
0x180035465  mov     rcx, rax
0x180035468  call    _tlgKeywordOn
0x18003546d  test    al, al
0x18003546f  jz      short loc_1800354E2
0x180035471  mov     eax, [r15]
0x180035474  lea     rdx, byte_18005CF85
0x18003547b  mov     rcx, [rbp+4Fh+var_A8]
0x18003547f  mov     qword ptr [rbp+4Fh+var_90], rax
0x180035483  mov     rax, [rbp+4Fh+var_98]
0x180035487  mov     [rbp+4Fh+var_C0], rcx
0x18003548b  mov     [rbp+4Fh+var_70], rsi
0x18003548f  mov     [rbp+4Fh+var_68], r14
0x180035493  mov     rax, [rax]
0x180035496  mov     rcx, [rax+rcx*8]
0x18003549a  mov     eax, [rbp+4Fh+var_CC]
0x18003549d  mov     [rbp+4Fh+var_C8], eax
0x1800354a0  lea     rax, [rbp+4Fh+var_70]
0x1800354a4  mov     [rsp+120h+var_D8], rax
0x1800354a9  lea     rax, [rbp+4Fh+var_68]
0x1800354ad  mov     [rsp+120h+var_E0], rax
0x1800354b2  lea     rax, [rbp+4Fh+var_90]
0x1800354b6  mov     [rsp+120h+var_E8], rax
0x1800354bb  lea     rax, [rbp+4Fh+var_C0]
0x1800354bf  mov     [rsp+120h+var_F0], rax
0x1800354c4  lea     rax, [rbp+4Fh+var_B8]
0x1800354c8  mov     [rsp+120h+var_F8], rax
0x1800354cd  lea     rax, [rbp+4Fh+var_C8]
0x1800354d1  mov     [rbp+4Fh+var_B8], rcx
0x1800354d5  mov     rcx, r8
0x1800354d8  mov     [rsp+120h+var_100], rax
0x1800354dd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U3@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@544@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800354e2  test    edi, edi
0x1800354e4  cmovns  edi, [rbp+4Fh+var_CC]
0x1800354e8  mov     rcx, [rbp+4Fh+var_A8]
0x1800354ec  mov     eax, [r15]
0x1800354ef  add     rcx, r12
0x1800354f2  mov     rdx, [rbp+4Fh+var_B0]
0x1800354f6  mov     [rbp+4Fh+var_A8], rcx
0x1800354fa  cmp     rcx, rax
0x1800354fd  jb      loc_18003538B
0x180035503  cmp     byte ptr [rsp+120h+var_D0], 0
0x180035508  jz      short loc_180035516
0x18003550a  mov     r12d, 2
0x180035510  jmp     short loc_180035516
0x180035512  mov     rbx, [rbp+4Fh+var_A0]
0x180035516  cmp     r13, r12
0x180035519  jnb     short loc_180035586
0x18003551b  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180035520  mov     r8, rax
0x180035523  mov     ecx, [rax]
0x180035525  cmp     ecx, 5
0x180035528  jbe     short loc_180035586
0x18003552a  mov     rdx, 400000000000h
0x180035534  mov     rcx, rax
0x180035537  call    _tlgKeywordOn
0x18003553c  test    al, al
0x18003553e  jz      short loc_180035586
0x180035540  mov     eax, [r15]
0x180035543  lea     rdx, unk_18005CF30
0x18003554a  mov     [rbp+4Fh+var_C0], rax
0x18003554e  mov     rcx, r8
0x180035551  lea     rax, [rbp+4Fh+var_B0]
0x180035555  mov     [rbp+4Fh+var_B0], rsi
0x180035559  mov     [rsp+120h+var_E8], rax
0x18003555e  lea     rax, [rbp+4Fh+var_B8]
0x180035562  mov     [rsp+120h+var_F0], rax
0x180035567  lea     rax, [rbp+4Fh+var_C0]
0x18003556b  mov     [rsp+120h+var_F8], rax
0x180035570  lea     rax, [rbp+4Fh+var_90]
0x180035574  mov     [rsp+120h+var_100], rax; bool
0x180035579  mov     [rbp+4Fh+var_B8], r14
0x18003557d  mov     qword ptr [rbp+4Fh+var_90], r13
0x180035581  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180035586  mov     r8d, r13d
0x180035589  lea     rdx, aSuccesscountU; "successCount %u."
0x180035590  mov     rcx, rbx; this
0x180035593  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180035598  lea     r12, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003559f  test    eax, eax
0x1800355a1  jns     short loc_1800355B7
0x1800355a3  mov     rcx, [rbp+57h]; this
0x1800355a7  mov     r9d, eax; char *
0x1800355aa  mov     r8, r12; unsigned int
0x1800355ad  mov     edx, 0A31h; void *
0x1800355b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800355b7  test    r13, r13
0x1800355ba  jnz     short loc_1800355F3
0x1800355bc  test    edi, edi
0x1800355be  jns     short loc_1800355EC
0x1800355c0  mov     eax, [r15]
0x1800355c3  mov     r9d, edi; char *
0x1800355c6  mov     rcx, [rbp+57h]; this
0x1800355ca  mov     r8, r12; unsigned int
0x1800355cd  mov     [rsp+120h+var_F0], rsi
0x1800355d2  mov     edx, 0A33h; void *
0x1800355d7  mov     dword ptr [rsp+120h+var_F8], eax; char *
0x1800355db  lea     rax, aNoneOfUFolders; "None of %u folders successfully restore"...
0x1800355e2  mov     [rsp+120h+var_100], rax; int
0x1800355e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800355ec  mov     ebx, edi
  ... truncated ...
```
