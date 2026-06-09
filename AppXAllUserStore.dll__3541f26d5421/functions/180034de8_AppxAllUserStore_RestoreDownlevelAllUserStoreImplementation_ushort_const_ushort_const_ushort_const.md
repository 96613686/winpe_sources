# AppxAllUserStore::RestoreDownlevelAllUserStoreImplementation(ushort const *,ushort const *,ushort const *)

- ea: `0x180034de8`
- end: `0x180035137`
- name: `?RestoreDownlevelAllUserStoreImplementation@AppxAllUserStore@@YAJPEBG00@Z`
- size: `847`
- prototype: `__int64 __fastcall(AppxAllUserStore *__hidden this, AppxAllUserStore *, char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002fce0`

## callees

- `0x180004920`
- `0x18000ed34`
- `0x180010330`
- `0x180010360`
- `0x1800121d0`
- `0x180016138`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x180026380`
- `0x180032e5c`
- `0x180033bb4`
- `0x180034de8`
- `0x180035140`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034ed5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180034ed5`

## string_xrefs

- `0x180034e4b`: `Path %ls.`
- `0x18003509f`: `RestoreFoldersAndRegistry got %u 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::RestoreDownlevelAllUserStoreImplementation(
        AppxAllUserStore *this,
        AppxAllUserStore *a2,
        char *a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // eax
  int v8; // eax
  struct Common::StringBuffer *v9; // r8
  __int64 v10; // rbx
  int v11; // eax
  struct Common::StringBuffer *v12; // r8
  int v13; // eax
  int v14; // eax
  int v15; // eax
  struct AppxAllUserStore::BasicLogFile *v16; // rbx
  struct AppxAllUserStore::BasicLogFile *v17; // r14
  int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  unsigned __int16 ***v21; // r8
  int bIgnoreCase; // [rsp+20h] [rbp-69h]
  int bIgnoreCasea; // [rsp+20h] [rbp-69h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-69h]
  AppxAllUserStore::Internal *v26; // [rsp+40h] [rbp-49h] BYREF
  __int128 v27; // [rsp+48h] [rbp-41h] BYREF
  int v28; // [rsp+58h] [rbp-31h]
  __int64 v29; // [rsp+60h] [rbp-29h]
  unsigned int v30[2]; // [rsp+68h] [rbp-21h] BYREF
  struct AppxAllUserStore::BasicLogFile *v31[2]; // [rsp+70h] [rbp-19h] BYREF
  int v32; // [rsp+80h] [rbp-9h]
  struct AppxAllUserStore::BasicLogFile *v33[2]; // [rsp+88h] [rbp-1h] BYREF
  int v34; // [rsp+98h] [rbp+Fh]
  GUID ActivityId; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  AppxAllUserStore::ActivityIDScope::ActivityIDScope(&ActivityId);
  v29 = -1;
  v28 = 0;
  v27 = 0;
  v7 = AppxAllUserStore::BasicLogFile::OpenLogFileAlways(
         (AppxAllUserStore::BasicLogFile *)&v27,
         a3,
         (char *)L"RestoreDownlevelAllUserStore.log");
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0xA5E,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)v7,
    (__int64)"Path %ls.",
    a3);
  v8 = AppxAllUserStore::BasicLogFile::WriteMsg(
         (AppxAllUserStore::BasicLogFile *)&v27,
         L"In RestoreDownlevelAllUserStore %ls %ls.",
         this,
         a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA5F,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
  wil::details::g_pfnLoggingCallback = 0;
  AppxAllUserStore::g_logFile = (AppxAllUserStore::BasicLogFile *)&v27;
  wil::SetResultLoggingCallback(lambda_698527d9bc244ffdcc9020db7862c2ad_::_lambda_invoker_cdecl_);
  if ( CompareStringOrdinal((LPCWCH)this, 1, (LPCWCH)a2, 1, 1) == 2 )
  {
    v32 = 0;
    *(_OWORD *)v31 = 0;
    v11 = AppxAllUserStore::NormalizeSystemRoot(this, (Common::StringBuffer *)v31, v9);
    LODWORD(v10) = v11;
    if ( v11 >= 0 )
    {
      v34 = 0;
      *(_OWORD *)v33 = 0;
      v14 = AppxAllUserStore::NormalizeSystemRoot(a2, (Common::StringBuffer *)v33, v12);
      LODWORD(v10) = v14;
      if ( v14 >= 0 )
      {
        v16 = v33[1];
        v17 = v31[1];
        v18 = AppxAllUserStore::BasicLogFile::WriteMsg(
                (AppxAllUserStore::BasicLogFile *)&v27,
                L"Normalized system roots %ls %ls.",
                v31[1],
                v33[1]);
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA7F,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v18,
            bIgnoreCasea);
        if ( v17 || v16 )
        {
          LODWORD(v26) = 0;
          *(_QWORD *)v30 = 0;
          v19 = AppxAllUserStore::Internal::RestoreFoldersAndRegistry(
                  (AppxAllUserStore::Internal *)&v27,
                  v17,
                  v16,
                  (const unsigned __int16 *)&v26,
                  v30);
          v10 = (unsigned int)wil::details::in1diag3::Log_IfFailedMsg(
                                retaddr,
                                (void *)0xA8B,
                                (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
                                (const char *)v19,
                                (__int64)"Src root %ls dst root %ls.",
                                (const char *)v17);
          v20 = AppxAllUserStore::BasicLogFile::WriteMsg(
                  (AppxAllUserStore::BasicLogFile *)&v27,
                  L"RestoreFoldersAndRegistry got %u 0x%0x.",
                  (unsigned int)v26,
                  v10);
          if ( v20 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xA8C,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)(unsigned int)v20,
              bIgnoreCaseb);
          AppxAllUserStore::Internal::FreeFolderArray(
            (AppxAllUserStore::Internal *)(unsigned int)v26,
            (unsigned int)v30,
            v21);
        }
        else
        {
          LODWORD(v10) = -2147024809;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xA81,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)0x80070057LL,
            (int)"Source (%ls) and target (%ls) system roots cannot be the same.",
            (const char *)this,
            a2);
        }
      }
      else
      {
        v15 = AppxAllUserStore::BasicLogFile::WriteMsg(
                (AppxAllUserStore::BasicLogFile *)&v27,
                L"NormalizeSystemRoot uplevel failed, 0x%0x.",
                (unsigned int)v14);
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA7C,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v15,
            bIgnoreCasea);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA7C,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCasea);
      }
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v33);
    }
    else
    {
      v13 = AppxAllUserStore::BasicLogFile::WriteMsg(
              (AppxAllUserStore::BasicLogFile *)&v27,
              L"NormalizeSystemRoot downlevel failed, 0x%0x.",
              (unsigned int)v11);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA78,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v13,
          bIgnoreCasea);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA78,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v10,
        bIgnoreCasea);
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v31);
  }
  else
  {
    LODWORD(v10) = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA72,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)0x80070057LL,
      (int)"Uplevel system root %ls is not on the same volume as the downlevel system root %ls.",
      (const char *)a2,
      this);
  }
  wil::details::g_pfnLoggingCallback = 0;
  AppxAllUserStore::g_logFile = 0;
  AppxAllUserStore::BasicLogFile::~BasicLogFile((AppxAllUserStore::BasicLogFile *)&v27);
  AppxAllUserStore::ActivityIDScope::~ActivityIDScope(&ActivityId);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180034de8  mov     [rsp-8+arg_18], rbx
0x180034ded  push    rbp
0x180034dee  push    rsi
0x180034def  push    rdi
0x180034df0  push    r12
0x180034df2  push    r14
0x180034df4  lea     rbp, [rsp-37h]
0x180034df9  sub     rsp, 0C0h
0x180034e00  mov     rax, cs:__security_cookie
0x180034e07  xor     rax, rsp
0x180034e0a  mov     [rbp+57h+var_28], rax
0x180034e0e  mov     rdi, rcx
0x180034e11  mov     rbx, r8
0x180034e14  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180034e18  mov     rsi, rdx
0x180034e1b  call    ??0ActivityIDScope@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::ActivityIDScope::ActivityIDScope(void)
0x180034e20  xor     eax, eax
0x180034e22  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFFh
0x180034e2a  xorps   xmm0, xmm0
0x180034e2d  mov     [rbp+57h+var_88], eax
0x180034e30  lea     r8, aRestoredownlev_0; "RestoreDownlevelAllUserStore.log"
0x180034e37  mov     rdx, rbx; char *
0x180034e3a  lea     rcx, [rbp+57h+var_98]; this
0x180034e3e  movups  [rbp+57h+var_98], xmm0
0x180034e42  call    ?OpenLogFileAlways@BasicLogFile@AppxAllUserStore@@QEAAJPEBG0@Z; AppxAllUserStore::BasicLogFile::OpenLogFileAlways(ushort const *,ushort const *)
0x180034e47  mov     rcx, [rbp+5Fh]; this
0x180034e4b  lea     rdx, aPathLs; "Path %ls."
0x180034e52  mov     [rsp+0E0h+var_B8], rbx; unsigned __int16 ***
0x180034e57  lea     r12, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180034e5e  mov     qword ptr [rsp+0E0h+bIgnoreCase], rdx; int
0x180034e63  mov     r9d, eax; char *
0x180034e66  mov     edx, 0A5Eh; void *
0x180034e6b  mov     r8, r12; unsigned int
0x180034e6e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034e73  mov     r9, rsi
0x180034e76  lea     rdx, aInRestoredownl; "In RestoreDownlevelAllUserStore %ls %ls"...
0x180034e7d  mov     r8, rdi
0x180034e80  lea     rcx, [rbp+57h+var_98]; this
0x180034e84  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034e89  test    eax, eax
0x180034e8b  jns     short loc_180034EA1
0x180034e8d  mov     rcx, [rbp+5Fh]; this
0x180034e91  mov     r9d, eax; char *
0x180034e94  mov     r8, r12; unsigned int
0x180034e97  mov     edx, 0A5Fh; void *
0x180034e9c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034ea1  lea     rax, [rbp+57h+var_98]
0x180034ea5  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x180034eb0  lea     rcx, _lambda_698527d9bc244ffdcc9020db7862c2ad____lambda_invoker_cdecl_
0x180034eb7  mov     cs:?g_logFile@AppxAllUserStore@@3PEAVBasicLogFile@1@EA, rax; AppxAllUserStore::BasicLogFile * AppxAllUserStore::g_logFile
0x180034ebe  call    ?SetResultLoggingCallback@wil@@YAXP6AXAEBUFailureInfo@1@@_E@Z; wil::SetResultLoggingCallback(void (*)(wil::FailureInfo const &),...)
0x180034ec3  mov     edx, 1; cchCount1
0x180034ec8  mov     r8, rsi; lpString2
0x180034ecb  mov     r9d, edx; cchCount2
0x180034ece  mov     [rsp+0E0h+bIgnoreCase], edx; int
0x180034ed2  mov     rcx, rdi; lpString1
0x180034ed5  call    cs:__imp_CompareStringOrdinal
0x180034edb  cmp     eax, 2
0x180034ede  jz      short loc_180034F14
0x180034ee0  mov     rcx, [rbp+5Fh]; this
0x180034ee4  lea     rax, aUplevelSystemR; "Uplevel system root %ls is not on the s"...
0x180034eeb  mov     [rsp+0E0h+var_B0], rdi
0x180034ef0  mov     ebx, 80070057h
0x180034ef5  mov     r9d, ebx; char *
0x180034ef8  mov     [rsp+0E0h+var_B8], rsi; char *
0x180034efd  mov     r8, r12; unsigned int
0x180034f00  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; int
0x180034f05  mov     edx, 0A72h; void *
0x180034f0a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034f0f  jmp     loc_1800350EA
0x180034f14  xor     eax, eax
0x180034f16  lea     rdx, [rbp+57h+var_70]; Common::StringBuffer *
0x180034f1a  xorps   xmm0, xmm0
0x180034f1d  mov     [rbp+57h+var_60], eax
0x180034f20  mov     rcx, rdi; this
0x180034f23  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180034f27  call    ?NormalizeSystemRoot@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::NormalizeSystemRoot(ushort const *,Common::StringBuffer &)
0x180034f2c  mov     ebx, eax
0x180034f2e  test    eax, eax
0x180034f30  jns     short loc_180034F75
0x180034f32  mov     r8d, eax
0x180034f35  lea     rdx, aNormalizesyste_1; "NormalizeSystemRoot downlevel failed, 0"...
0x180034f3c  lea     rcx, [rbp+57h+var_98]; this
0x180034f40  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034f45  mov     edi, 0A78h
0x180034f4a  test    eax, eax
0x180034f4c  jns     short loc_180034F5F
0x180034f4e  mov     rcx, [rbp+5Fh]; this
0x180034f52  mov     r9d, eax; char *
0x180034f55  mov     r8, r12; unsigned int
0x180034f58  mov     edx, edi; void *
0x180034f5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034f5f  mov     rcx, [rbp+5Fh]; this
0x180034f63  mov     r9d, ebx; char *
0x180034f66  mov     r8, r12; unsigned int
0x180034f69  mov     edx, edi; void *
0x180034f6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034f70  jmp     loc_1800350E1
0x180034f75  xor     eax, eax
0x180034f77  lea     rdx, [rbp+57h+var_58]; Common::StringBuffer *
0x180034f7b  xorps   xmm0, xmm0
0x180034f7e  mov     [rbp+57h+var_48], eax
0x180034f81  mov     rcx, rsi; this
0x180034f84  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180034f88  call    ?NormalizeSystemRoot@AppxAllUserStore@@YAJPEBGAEAVStringBuffer@Common@@@Z; AppxAllUserStore::NormalizeSystemRoot(ushort const *,Common::StringBuffer &)
0x180034f8d  lea     rcx, [rbp+57h+var_98]; this
0x180034f91  mov     ebx, eax
0x180034f93  test    eax, eax
0x180034f95  jns     short loc_180034FD6
0x180034f97  mov     r8d, eax
0x180034f9a  lea     rdx, aNormalizesyste_0; "NormalizeSystemRoot uplevel failed, 0x%"...
0x180034fa1  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034fa6  mov     edi, 0A7Ch
0x180034fab  test    eax, eax
0x180034fad  jns     short loc_180034FC0
0x180034faf  mov     rcx, [rbp+5Fh]; this
0x180034fb3  mov     r9d, eax; char *
0x180034fb6  mov     r8, r12; unsigned int
0x180034fb9  mov     edx, edi; void *
0x180034fbb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180034fc0  mov     rcx, [rbp+5Fh]; this
0x180034fc4  mov     r9d, ebx; char *
0x180034fc7  mov     r8, r12; unsigned int
0x180034fca  mov     edx, edi; void *
0x180034fcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034fd1  jmp     loc_1800350D8
0x180034fd6  mov     rbx, [rbp+57h+var_58+8]
0x180034fda  lea     rdx, aNormalizedSyst; "Normalized system roots %ls %ls."
0x180034fe1  mov     r14, [rbp+57h+var_70+8]
0x180034fe5  mov     r9, rbx
0x180034fe8  mov     r8, r14
0x180034feb  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180034ff0  test    eax, eax
0x180034ff2  jns     short loc_180035008
0x180034ff4  mov     rcx, [rbp+5Fh]; this
0x180034ff8  mov     r9d, eax; char *
0x180034ffb  mov     r8, r12; unsigned int
0x180034ffe  mov     edx, 0A7Fh; void *
0x180035003  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035008  test    r14, r14
0x18003500b  jnz     short loc_180035046
0x18003500d  test    rbx, rbx
0x180035010  jnz     short loc_180035046
0x180035012  mov     rcx, [rbp+5Fh]; this
0x180035016  lea     rax, aSourceLsAndTar; "Source (%ls) and target (%ls) system ro"...
0x18003501d  mov     [rsp+0E0h+var_B0], rsi
0x180035022  mov     ebx, 80070057h
0x180035027  mov     r9d, ebx; char *
0x18003502a  mov     [rsp+0E0h+var_B8], rdi; char *
0x18003502f  mov     r8, r12; unsigned int
0x180035032  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; int
0x180035037  mov     edx, 0A81h; void *
0x18003503c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035041  jmp     loc_1800350D8
0x180035046  lea     rax, [rbp+57h+var_78]
0x18003504a  mov     dword ptr [rbp+57h+var_A0], 0
0x180035051  lea     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x180035055  mov     qword ptr [rsp+0E0h+bIgnoreCase], rax; unsigned int *
0x18003505a  mov     r8, rbx; struct AppxAllUserStore::BasicLogFile *
0x18003505d  mov     qword ptr [rbp+57h+var_78], 0
0x180035065  mov     rdx, r14; struct AppxAllUserStore::BasicLogFile *
0x180035068  lea     rcx, [rbp+57h+var_98]; this
0x18003506c  call    ?RestoreFoldersAndRegistry@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1PEAIPEAPEAPEAG@Z; AppxAllUserStore::Internal::RestoreFoldersAndRegistry(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,uint *,ushort * * *)
0x180035071  mov     rcx, [rbp+5Fh]; this
0x180035075  lea     rdx, aSrcRootLsDstRo_0; "Src root %ls dst root %ls."
0x18003507c  mov     [rsp+0E0h+var_B0], rbx
0x180035081  mov     r9d, eax; char *
0x180035084  mov     [rsp+0E0h+var_B8], r14; char *
0x180035089  mov     r8, r12; unsigned int
0x18003508c  mov     qword ptr [rsp+0E0h+bIgnoreCase], rdx; int
0x180035091  mov     edx, 0A8Bh; void *
0x180035096  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003509b  mov     r8d, dword ptr [rbp+57h+var_A0]
0x18003509f  lea     rdx, aRestorefolders; "RestoreFoldersAndRegistry got %u 0x%0x."
0x1800350a6  mov     r9d, eax
0x1800350a9  lea     rcx, [rbp+57h+var_98]; this
0x1800350ad  mov     ebx, eax
0x1800350af  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x1800350b4  test    eax, eax
0x1800350b6  jns     short loc_1800350CC
0x1800350b8  mov     rcx, [rbp+5Fh]; this
0x1800350bc  mov     r9d, eax; char *
0x1800350bf  mov     r8, r12; unsigned int
0x1800350c2  mov     edx, 0A8Ch; void *
0x1800350c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800350cc  mov     ecx, dword ptr [rbp+57h+var_A0]; this
0x1800350cf  lea     rdx, [rbp+57h+var_78]; unsigned int
0x1800350d3  call    ?FreeFolderArray@Internal@AppxAllUserStore@@YAXIPEAPEAPEAG@Z; AppxAllUserStore::Internal::FreeFolderArray(uint,ushort * * *)
0x1800350d8  lea     rcx, [rbp+57h+var_58]; this
0x1800350dc  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800350e1  lea     rcx, [rbp+57h+var_70]; this
0x1800350e5  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x1800350ea  lea     rcx, [rbp+57h+var_98]; this
0x1800350ee  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x1800350f9  mov     cs:?g_logFile@AppxAllUserStore@@3PEAVBasicLogFile@1@EA, 0; AppxAllUserStore::BasicLogFile * AppxAllUserStore::g_logFile
0x180035104  call    ??1BasicLogFile@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::BasicLogFile::~BasicLogFile(void)
0x180035109  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18003510d  call    ??1ActivityIDScope@AppxAllUserStore@@QEAA@XZ; AppxAllUserStore::ActivityIDScope::~ActivityIDScope(void)
0x180035112  mov     eax, ebx
0x180035114  mov     rcx, [rbp+57h+var_28]
0x180035118  xor     rcx, rsp; StackCookie
0x18003511b  call    __security_check_cookie
0x180035120  mov     rbx, [rsp+0E0h+arg_18]
0x180035128  add     rsp, 0C0h
0x18003512f  pop     r14
0x180035131  pop     r12
0x180035133  pop     rdi
0x180035134  pop     rsi
0x180035135  pop     rbp
0x180035136  retn
```
