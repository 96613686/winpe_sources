# AppxAllUserStore::Internal::AdjustRestoredDeletedPackagePath(AppxAllUserStore::BasicLogFile &,ushort const *,ushort const *,Common::RegistryKey &)

- ea: `0x180031c80`
- end: `0x180031fd8`
- name: `?AdjustRestoredDeletedPackagePath@Internal@AppxAllUserStore@@YAJAEAVBasicLogFile@2@PEBG1AEAVRegistryKey@Common@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(AppxAllUserStore::Internal *this, struct AppxAllUserStore::BasicLogFile *Src, char *, Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017198`

## callees

- `0x1800019a8`
- `0x180004920`
- `0x180005ec8`
- `0x180008db0`
- `0x18000ed34`
- `0x180010384`
- `0x180012c3c`
- `0x180017cd0`
- `0x180017f50`
- `0x180018248`
- `0x18001a6a0`
- `0x18001b3f0`
- `0x180031c80`
- `0x18004682c`
- `0x180046a80`

## import_xrefs

- `msvcrt!wcsstr` at `0x180031db0`
- `msvcrt!wcsstr` at `0x180031db0`
- `msvcrt!_wcslwr` at `0x180031d96`
- `msvcrt!_wcslwr` at `0x180031da3`
- `msvcrt!_wcslwr` at `0x180031d96`
- `msvcrt!_wcslwr` at `0x180031da3`

## string_xrefs

- `0x180031ca9`: `In AdjustRestoredDeletedPackagePath %ls %ls.`
- `0x180031dc3`: `Path %ls unexpected, 0x%0x.`
- `0x180031e38`: `targetSISPath %ls, AppendString %ls`
- `0x180031e84`: `Path %ls.`
- `0x180031ebb`: `WARNING: adjusted path %ls existence %u, 0x%0x.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::Internal::AdjustRestoredDeletedPackagePath(
        AppxAllUserStore::Internal *this,
        struct AppxAllUserStore::BasicLogFile *Src,
        char *a3,
        Common::RegistryKey *a4)
{
  int v8; // eax
  int StringValue; // eax
  unsigned int v10; // ebx
  int v11; // eax
  const wchar_t *v12; // rbx
  wchar_t *v13; // rsi
  int v14; // eax
  bool *v15; // r8
  const char *v16; // rbx
  unsigned int v17; // eax
  int v18; // eax
  unsigned int v19; // r9d
  int v20; // esi
  int v21; // ebx
  int v22; // eax
  const struct _tlgProvider_t *v23; // rax
  int v24; // r8d
  int v25; // eax
  int v26; // eax
  unsigned int *v28; // [rsp+20h] [rbp-59h]
  int v29; // [rsp+20h] [rbp-59h]
  __int64 v30; // [rsp+20h] [rbp-59h]
  unsigned __int16 v31[2]; // [rsp+40h] [rbp-39h] BYREF
  int v32; // [rsp+44h] [rbp-35h] BYREF
  int v33; // [rsp+48h] [rbp-31h] BYREF
  Common *v34[2]; // [rsp+50h] [rbp-29h] BYREF
  int v35; // [rsp+60h] [rbp-19h]
  wchar_t *String[2]; // [rsp+68h] [rbp-11h] BYREF
  int v37; // [rsp+78h] [rbp-1h]
  Common *v38; // [rsp+80h] [rbp+7h] BYREF
  wchar_t *Str[2]; // [rsp+88h] [rbp+Fh] BYREF
  int v40; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v8 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"In AdjustRestoredDeletedPackagePath %ls %ls.", Src, a3);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x658,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v8,
      (int)v28);
  v40 = 0;
  *(_OWORD *)Str = 0;
  StringValue = Common::RegistryKey::GetStringValue(a4, L"Path", 0x7FFFu, (struct Common::StringBuffer *)Str, v28);
  v10 = StringValue;
  if ( StringValue < 0 )
  {
    v11 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"GetStringValue failed, 0x%0x.", (unsigned int)StringValue);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x65D,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)(unsigned int)v11,
        v29);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65D,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)v10,
      v29);
    goto LABEL_29;
  }
  v37 = 0;
  *(_OWORD *)String = 0;
  v10 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)String, (const unsigned __int16 *)Src);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x662,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)v10,
      (int)"subKeyName %ls.",
      (const char *)Src);
LABEL_9:
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
    goto LABEL_29;
  }
  _wcslwr(String[1]);
  v12 = Str[1];
  _wcslwr(Str[1]);
  v13 = wcsstr(v12, String[1]);
  if ( v13 )
  {
    v35 = 0;
    *(_OWORD *)v34 = 0;
    v10 = Common::PathHelpers::CombinePaths((const unsigned __int16 *)a3, v13, (struct Common::StringBuffer *)v34);
    if ( (v10 & 0x80000000) == 0 )
    {
      v16 = (const char *)v34[1];
      LOBYTE(v31[0]) = 0;
      v17 = Common::FileExists(v34[1], v31, v15);
      v18 = wil::details::in1diag3::Log_IfFailedMsg(
              retaddr,
              (void *)0x676,
              (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
              (const char *)v17,
              (__int64)"Path %ls.",
              v16);
      v20 = v18;
      if ( v18 < 0 || !LOBYTE(v31[0]) )
      {
        v21 = LOBYTE(v31[0]);
        LODWORD(v30) = v18;
        v22 = AppxAllUserStore::BasicLogFile::WriteMsg(
                this,
                L"WARNING: adjusted path %ls existence %u, 0x%0x.",
                v34[1],
                LOBYTE(v31[0]),
                v30);
        if ( v22 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x67A,
            (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
            (const char *)(unsigned int)v22,
            v30);
        v23 = AppxAllUserStoreTelemetry::Provider();
        if ( *(_DWORD *)v23 > 5u && (unsigned __int8)tlgKeywordOn(v23, 0x400000000000LL, v23) )
        {
          v38 = v34[1];
          v32 = v21;
          v33 = v20;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v24,
            (unsigned int)&byte_18005D0BF,
            v24,
            v19,
            (__int64)&v33,
            (__int64)&v32,
            (__int64)&v38);
        }
      }
      v25 = Common::RegistryKey::SetStringValue(a4, L"Path", (const unsigned __int16 *)v34[1], v19);
      v10 = v25;
      if ( v25 >= 0 )
      {
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v34);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
        v10 = 0;
        goto LABEL_29;
      }
      v26 = AppxAllUserStore::BasicLogFile::WriteMsg(
              this,
              L"SetStringValue %ls failed, 0x%0x.",
              v34[1],
              (unsigned int)v25);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x686,
          (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
          (const char *)(unsigned int)v26,
          v30);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x686,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        v30);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x670,
        (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
        (const char *)v10,
        (int)"targetSISPath %ls, AppendString %ls",
        a3,
        v13);
    }
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v34);
    goto LABEL_9;
  }
  v14 = AppxAllUserStore::BasicLogFile::WriteMsg(this, L"Path %ls unexpected, 0x%0x.", v12, 2147549183LL);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x669,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
      (const char *)(unsigned int)v14,
      v29);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x669,
    (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\imageservicingutilities.cpp",
    (const char *)0x8000FFFFLL,
    v29);
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)String);
  v10 = -2147418113;
LABEL_29:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)Str);
  return v10;
}

```

## disassembly

```asm
0x180031c80  push    rbp
0x180031c82  push    rbx
0x180031c83  push    rsi
0x180031c84  push    rdi
0x180031c85  push    r13
0x180031c87  push    r14
0x180031c89  push    r15
0x180031c8b  lea     rbp, [rsp-27h]
0x180031c90  sub     rsp, 0A0h
0x180031c97  mov     r15, r9
0x180031c9a  mov     r14, r8
0x180031c9d  mov     r9, r8
0x180031ca0  mov     rsi, rdx
0x180031ca3  mov     r8, rdx
0x180031ca6  mov     rdi, rcx
0x180031ca9  lea     rdx, aInAdjustrestor; "In AdjustRestoredDeletedPackagePath %ls"...
0x180031cb0  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180031cb5  lea     r13, aOnecoreAdminAp_10; "onecore\\admin\\appmodel\\appxalluserst"...
0x180031cbc  test    eax, eax
0x180031cbe  jns     short loc_180031CD4
0x180031cc0  mov     rcx, [rbp+5Fh]; this
0x180031cc4  mov     r9d, eax; char *
0x180031cc7  mov     r8, r13; unsigned int
0x180031cca  mov     edx, 658h; void *
0x180031ccf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031cd4  xor     eax, eax
0x180031cd6  lea     r9, [rbp+57h+Str]; struct Common::StringBuffer *
0x180031cda  xorps   xmm0, xmm0
0x180031cdd  mov     [rbp+57h+var_38], eax
0x180031ce0  mov     r8d, 7FFFh; unsigned __int64
0x180031ce6  lea     rdx, aPath; "Path"
0x180031ced  mov     rcx, r15; this
0x180031cf0  movups  xmmword ptr [rbp+57h+Str], xmm0
0x180031cf4  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z; Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)
0x180031cf9  mov     ebx, eax
0x180031cfb  test    eax, eax
0x180031cfd  jns     short loc_180031D41
0x180031cff  mov     r8d, eax
0x180031d02  lea     rdx, aGetstringvalue; "GetStringValue failed, 0x%0x."
0x180031d09  mov     rcx, rdi; this
0x180031d0c  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180031d11  mov     edi, 65Dh
0x180031d16  test    eax, eax
0x180031d18  jns     short loc_180031D2B
0x180031d1a  mov     rcx, [rbp+5Fh]; this
0x180031d1e  mov     r9d, eax; char *
0x180031d21  mov     r8, r13; unsigned int
0x180031d24  mov     edx, edi; void *
0x180031d26  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031d2b  mov     rcx, [rbp+5Fh]; this
0x180031d2f  mov     r9d, ebx; char *
0x180031d32  mov     r8, r13; unsigned int
0x180031d35  mov     edx, edi; void *
0x180031d37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d3c  jmp     loc_180031FBB
0x180031d41  xor     eax, eax
0x180031d43  lea     rcx, [rbp+57h+String]; this
0x180031d47  xorps   xmm0, xmm0
0x180031d4a  mov     [rbp+57h+var_58], eax
0x180031d4d  mov     rdx, rsi; Src
0x180031d50  movups  xmmword ptr [rbp+57h+String], xmm0
0x180031d54  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180031d59  mov     ebx, eax
0x180031d5b  test    eax, eax
0x180031d5d  jns     short loc_180031D92
0x180031d5f  mov     rcx, [rbp+5Fh]; this
0x180031d63  lea     rax, aSubkeynameLs; "subKeyName %ls."
0x180031d6a  mov     [rsp+0D0h+var_A8], rsi; char *
0x180031d6f  mov     r9d, ebx; char *
0x180031d72  mov     r8, r13; unsigned int
0x180031d75  mov     [rsp+0D0h+var_B0], rax; int
0x180031d7a  mov     edx, 662h; void *
0x180031d7f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180031d84  lea     rcx, [rbp+57h+String]; this
0x180031d88  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180031d8d  jmp     loc_180031FBB
0x180031d92  mov     rcx, [rbp+57h+String+8]; String
0x180031d96  call    cs:__imp__wcslwr
0x180031d9c  mov     rbx, [rbp+57h+Str+8]
0x180031da0  mov     rcx, rbx; String
0x180031da3  call    cs:__imp__wcslwr
0x180031da9  mov     rdx, [rbp+57h+String+8]; SubStr
0x180031dad  mov     rcx, rbx; Str
0x180031db0  call    cs:__imp_wcsstr
0x180031db6  mov     rsi, rax
0x180031db9  test    rax, rax
0x180031dbc  jnz     short loc_180031E13
0x180031dbe  mov     esi, 8000FFFFh
0x180031dc3  lea     rdx, aPathLsUnexpect; "Path %ls unexpected, 0x%0x."
0x180031dca  mov     r9d, esi
0x180031dcd  mov     r8, rbx
0x180031dd0  mov     rcx, rdi; this
0x180031dd3  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180031dd8  mov     ebx, 669h
0x180031ddd  test    eax, eax
0x180031ddf  jns     short loc_180031DF2
0x180031de1  mov     rcx, [rbp+5Fh]; this
0x180031de5  mov     r9d, eax; char *
0x180031de8  mov     r8, r13; unsigned int
0x180031deb  mov     edx, ebx; void *
0x180031ded  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031df2  mov     rcx, [rbp+5Fh]; this
0x180031df6  mov     r9d, esi; char *
0x180031df9  mov     r8, r13; unsigned int
0x180031dfc  mov     edx, ebx; void *
0x180031dfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031e03  lea     rcx, [rbp+57h+String]; this
0x180031e07  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180031e0c  mov     ebx, esi
0x180031e0e  jmp     loc_180031FBB
0x180031e13  xor     eax, eax
0x180031e15  lea     r8, [rbp+57h+var_80]; this
0x180031e19  xorps   xmm0, xmm0
0x180031e1c  mov     [rbp+57h+var_70], eax
0x180031e1f  mov     rdx, rsi; unsigned __int16 *
0x180031e22  mov     rcx, r14; Src
0x180031e25  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180031e29  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x180031e2e  mov     ebx, eax
0x180031e30  test    eax, eax
0x180031e32  jns     short loc_180031E6C
0x180031e34  mov     rcx, [rbp+5Fh]; this
0x180031e38  lea     rax, aTargetsispathL; "targetSISPath %ls, AppendString %ls"
0x180031e3f  mov     [rsp+0D0h+var_A0], rsi
0x180031e44  mov     r9d, ebx; char *
0x180031e47  mov     [rsp+0D0h+var_A8], r14; char *
0x180031e4c  mov     r8, r13; unsigned int
0x180031e4f  mov     edx, 670h; void *
0x180031e54  mov     [rsp+0D0h+var_B0], rax; int
0x180031e59  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180031e5e  lea     rcx, [rbp+57h+var_80]; this
0x180031e62  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180031e67  jmp     loc_180031D84
0x180031e6c  mov     rbx, [rbp+57h+var_80+8]
0x180031e70  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x180031e74  mov     rcx, rbx; this
0x180031e77  mov     byte ptr [rbp+57h+var_90], 0
0x180031e7b  call    ?FileExists@Common@@YAJPEBGPEA_N@Z; Common::FileExists(ushort const *,bool *)
0x180031e80  mov     rcx, [rbp+5Fh]; this
0x180031e84  lea     rdx, aPathLs; "Path %ls."
0x180031e8b  mov     [rsp+0D0h+var_A8], rbx; char *
0x180031e90  mov     r9d, eax; char *
0x180031e93  mov     [rsp+0D0h+var_B0], rdx; __int64
0x180031e98  mov     r8, r13; unsigned int
0x180031e9b  mov     edx, 676h; void *
0x180031ea0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180031ea5  movzx   ecx, byte ptr [rbp+57h+var_90]
0x180031ea9  mov     esi, eax
0x180031eab  test    eax, eax
0x180031ead  js      short loc_180031EB7
0x180031eaf  test    cl, cl
0x180031eb1  jnz     loc_180031F48
0x180031eb7  mov     r8, [rbp+57h+var_80+8]
0x180031ebb  lea     rdx, aWarningAdjuste; "WARNING: adjusted path %ls existence %u"...
0x180031ec2  mov     ebx, ecx
0x180031ec4  mov     dword ptr [rsp+0D0h+var_B0], esi; int
0x180031ec8  mov     r9d, ecx
0x180031ecb  mov     rcx, rdi; this
0x180031ece  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180031ed3  test    eax, eax
0x180031ed5  jns     short loc_180031EEB
0x180031ed7  mov     rcx, [rbp+5Fh]; this
0x180031edb  mov     r9d, eax; char *
0x180031ede  mov     r8, r13; unsigned int
0x180031ee1  mov     edx, 67Ah; void *
0x180031ee6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031eeb  call    ?Provider@AppxAllUserStoreTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppxAllUserStoreTelemetry::Provider(void)
0x180031ef0  mov     r8, rax
0x180031ef3  mov     ecx, [rax]
0x180031ef5  cmp     ecx, 5
0x180031ef8  jbe     short loc_180031F48
0x180031efa  mov     rdx, 400000000000h
0x180031f04  mov     rcx, rax
0x180031f07  call    _tlgKeywordOn
0x180031f0c  test    al, al
0x180031f0e  jz      short loc_180031F48
0x180031f10  mov     rcx, [rbp+57h+var_80+8]
0x180031f14  lea     rax, [rbp+57h+var_50]
0x180031f18  mov     [rsp+0D0h+var_A0], rax
0x180031f1d  lea     rdx, byte_18005D0BF
0x180031f24  lea     rax, [rbp+57h+var_8C]
0x180031f28  mov     [rbp+57h+var_50], rcx
0x180031f2c  mov     [rsp+0D0h+var_A8], rax
0x180031f31  mov     rcx, r8
0x180031f34  lea     rax, [rbp+57h+var_88]
0x180031f38  mov     [rbp+57h+var_8C], ebx
0x180031f3b  mov     [rsp+0D0h+var_B0], rax; int
0x180031f40  mov     [rbp+57h+var_88], esi
0x180031f43  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180031f48  mov     r8, [rbp+57h+var_80+8]; unsigned __int16 *
0x180031f4c  lea     rdx, aPath; "Path"
0x180031f53  mov     rcx, r15; this
0x180031f56  call    ?SetStringValue@RegistryKey@Common@@QEAAJPEBG0K@Z; Common::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180031f5b  mov     ebx, eax
0x180031f5d  test    eax, eax
0x180031f5f  jns     short loc_180031FA7
0x180031f61  mov     r8, [rbp+57h+var_80+8]
0x180031f65  lea     rdx, aSetstringvalue; "SetStringValue %ls failed, 0x%0x."
0x180031f6c  mov     r9d, eax
0x180031f6f  mov     rcx, rdi; this
0x180031f72  call    ?WriteMsg@BasicLogFile@AppxAllUserStore@@QEAAJPEBGZZ; AppxAllUserStore::BasicLogFile::WriteMsg(ushort const *,...)
0x180031f77  mov     edi, 686h
0x180031f7c  test    eax, eax
0x180031f7e  jns     short loc_180031F91
0x180031f80  mov     rcx, [rbp+5Fh]; this
0x180031f84  mov     r9d, eax; char *
0x180031f87  mov     r8, r13; unsigned int
0x180031f8a  mov     edx, edi; void *
0x180031f8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031f91  mov     rcx, [rbp+5Fh]; this
0x180031f95  mov     r9d, ebx; char *
0x180031f98  mov     r8, r13; unsigned int
0x180031f9b  mov     edx, edi; void *
0x180031f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031fa2  jmp     loc_180031E5E
0x180031fa7  lea     rcx, [rbp+57h+var_80]; this
0x180031fab  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180031fb0  lea     rcx, [rbp+57h+String]; this
0x180031fb4  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180031fb9  xor     ebx, ebx
0x180031fbb  lea     rcx, [rbp+57h+Str]; this
0x180031fbf  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180031fc4  mov     eax, ebx
0x180031fc6  add     rsp, 0A0h
0x180031fcd  pop     r15
0x180031fcf  pop     r14
0x180031fd1  pop     r13
0x180031fd3  pop     rdi
0x180031fd4  pop     rsi
0x180031fd5  pop     rbx
0x180031fd6  pop     rbp
0x180031fd7  retn
```
