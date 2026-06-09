# WaasMedic::CStackDataResetPlugin::PerformAction(void)

- ea: `0x18003b8c0`
- end: `0x18003bf33`
- name: `?PerformAction@CStackDataResetPlugin@WaasMedic@@UEAAJXZ`
- size: `1651`
- prototype: `__int64 __fastcall(WaasMedic::CStackDataResetPlugin *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800017ac`
- `0x180003bb0`
- `0x180003c3c`
- `0x180004098`
- `0x180005c9c`
- `0x180005d04`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x180025ae0`
- `0x180025d78`
- `0x180026830`
- `0x18002c238`
- `0x18003613c`
- `0x180039dc4`
- `0x18003a4f4`
- `0x18003b8c0`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003b8fb`
- `OLEAUT32!__imp_VariantInit` at `0x18003b8fb`
- `OLEAUT32!__imp_VariantClear` at `0x18003bdd0`
- `OLEAUT32!__imp_VariantClear` at `0x18003bdd0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bc1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bc1a`

## string_xrefs

- `0x18003bafa`: `StackDataResetPlugin`
- `0x18003b99a`: `Attempting to stop service %s`
- `0x18003ba6e`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003ba9f`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003bb46`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003bbba`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003bbf5`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003bc38`: `onecore\enduser\waasmedic\lib\plugins\stackdataresetplugin.cpp`
- `0x18003ba35`: `Unable to stop all the services. Aborting execution. hr = 0x%08x`
- `0x18003bc29`: `Failed to delete Delivery Optimization Jobs regkey`
- `0x18003bbd1`: `%Programdata%\Microsoft\Network\Downloader`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WaasMedic::CStackDataResetPlugin::PerformAction(WaasMedic::CStackDataResetPlugin *this)
{
  unsigned int v2; // edi
  __int64 v3; // rsi
  unsigned int v4; // r14d
  int v5; // r12d
  char v6; // r15
  unsigned __int16 *v7; // rbx
  unsigned __int16 *v8; // r13
  unsigned __int16 *v9; // r8
  bool *v10; // r8
  const unsigned __int16 *v11; // rcx
  int v12; // eax
  const wchar_t *v13; // r9
  unsigned __int16 *v14; // r8
  int v15; // r15d
  int v16; // edi
  WaasMedic::CStackDataResetPlugin *v17; // r13
  unsigned int v18; // eax
  unsigned int SizeOfDatastore; // eax
  __int64 (__fastcall ***v20)(_QWORD, _OWORD *, _OWORD *, int *); // rdi
  __int64 (__fastcall *v21)(_QWORD, _OWORD *, _OWORD *, int *); // rbx
  int v22; // ebx
  int v23; // eax
  WaasMedic::CStackDataResetPlugin *v24; // rcx
  const char *v25; // rbx
  WaasMedic::CStackDataResetPlugin *v26; // rcx
  const char *v27; // rbx
  const char *v28; // rbx
  const struct _tlgProvider_t *v29; // rax
  const struct _tlgProvider_t *v30; // r10
  __int64 v31; // rax
  const unsigned __int16 *v32; // rax
  __int64 v34; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  const char *v36; // [rsp+28h] [rbp-D8h]
  const char *v37; // [rsp+28h] [rbp-D8h]
  const char *v38; // [rsp+28h] [rbp-D8h]
  const char *v39; // [rsp+28h] [rbp-D8h]
  const char *v40; // [rsp+28h] [rbp-D8h]
  char v41; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v42[2]; // [rsp+34h] [rbp-CCh] BYREF
  char v43; // [rsp+38h] [rbp-C8h] BYREF
  int v44; // [rsp+3Ch] [rbp-C4h] BYREF
  int v45; // [rsp+40h] [rbp-C0h] BYREF
  WaasMedic::CStackDataResetPlugin *v46; // [rsp+48h] [rbp-B8h] BYREF
  int v47; // [rsp+50h] [rbp-B0h] BYREF
  int v48[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v49; // [rsp+60h] [rbp-A0h]
  __int128 v50; // [rsp+68h] [rbp-98h]
  __int64 v51; // [rsp+78h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v53[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v54[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v55[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int128 v57; // [rsp+108h] [rbp+8h] BYREF
  __int64 v58; // [rsp+118h] [rbp+18h]
  int *v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]
  __int128 v61; // [rsp+130h] [rbp+30h] BYREF
  __int128 v62; // [rsp+140h] [rbp+40h]
  __int64 v63; // [rsp+150h] [rbp+50h]
  __int128 v64; // [rsp+158h] [rbp+58h] BYREF
  __int64 v65; // [rsp+168h] [rbp+68h]
  int *v66; // [rsp+170h] [rbp+70h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  _QWORD v68[2]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v46 = this;
  v2 = 0;
  VariantInit(&pvarg);
  v50 = 0;
  v51 = 0;
  v49 = 0;
  v48[0] = *((_DWORD *)this + 58);
  v48[1] = 2;
  v3 = -1;
  v44 = -1;
  v42[0] = -1;
  v4 = 1;
  if ( dword_180099220 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_180099220);
    if ( dword_180099220 == -1 )
    {
      memset(v55, 0, sizeof(v55));
      std::wstring::_Construct<1,unsigned short const *>(v55, L"usosvc", 6);
      v56 = 1;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v57, L"dosvc", 5);
      v60 = 2;
      v61 = 0;
      v62 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v61, L"wuauserv", 8);
      v63 = 4;
      v64 = 0;
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v64, L"bits", 4);
      v67 = 8;
      *(_QWORD *)&v53[0] = v55;
      *((_QWORD *)&v53[0] + 1) = v68;
      std::vector<WaasMedic::CSvcUtil::Services>::vector<WaasMedic::CSvcUtil::Services>(v34, v53);
      `eh vector destructor iterator'(v55, 0x28u, 4u, (void (*)(void *))WaasMedic::CSvcUtil::Services::~Services);
      atexit(WaasMedic::CStackDataResetPlugin::PerformAction_::_2_::_dynamic_atexit_destructor_for__servicesToStop__);
      Init_thread_footer(&dword_180099220);
    }
  }
  v5 = 0;
  v41 = 0;
  v6 = 0;
  do
  {
    v8 = *(&xmmword_180099228 + 1);
    v7 = xmmword_180099228;
    if ( xmmword_180099228 != *(&xmmword_180099228 + 1) )
    {
      do
      {
        if ( *((_QWORD *)v7 + 3) <= 7u )
          v9 = v7;
        else
          v9 = *(unsigned __int16 **)v7;
        LogLevelW(4u, L"Attempting to stop service %s", v9);
        if ( *((_QWORD *)v7 + 3) <= 7u )
          v11 = v7;
        else
          v11 = *(const unsigned __int16 **)v7;
        v12 = WaasMedic::CSvcUtil::ServiceStop(v11, 1, v10);
        if ( v2 == 2 )
        {
          if ( v12 < 0 )
            v5 = v12;
          else
            v6 |= *((_BYTE *)v7 + 32);
          v13 = L"not ";
          if ( v12 >= 0 )
            v13 = &word_18006939C;
          if ( *((_QWORD *)v7 + 3) <= 7u )
            v14 = v7;
          else
            v14 = *(unsigned __int16 **)v7;
          LogLevelW(4u, L"%s was %sstopped.", v14, v13);
        }
        v7 += 20;
      }
      while ( v7 != v8 );
      v41 = v6;
    }
    ++v2;
  }
  while ( v2 < 3 );
  v15 = 0;
  if ( v5 >= 0 )
  {
    v18 = WaasMedic::MiscUtil::FreeSpaceInGB(&v44);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xED,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)v18,
      (int)"FreeSpaceInGB failed",
      v36);
    SizeOfDatastore = WaasMedic::MiscUtil::GetSizeOfDatastore(v42);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      (const char *)SizeOfDatastore,
      (int)"GetSizeOfDatastore failed",
      v37);
    v17 = v46;
    v20 = (__int64 (__fastcall ***)(_QWORD, _OWORD *, _OWORD *, int *))*((_QWORD *)v46 + 13);
    v21 = **v20;
    memset(v54, 0, sizeof(v54));
    std::wstring::_Construct<1,unsigned short const *>(v54, L"LowDiskValueInGb", 16);
    memset(v53, 0, sizeof(v53));
    std::wstring::_Construct<1,unsigned short const *>(v53, L"StackDataResetPlugin", 20);
    v22 = v21(v20, v53, v54, v48);
    std::wstring::~wstring(v53);
    std::wstring::~wstring(v54);
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
        (const char *)(unsigned int)v22,
        v35);
      goto LABEL_47;
    }
    v23 = WaasMedic::MiscUtil::ResetDataStore(v48[0]);
    v16 = v23;
    if ( v23 >= 0 )
    {
      LogLevelW(4u, L"Datastore successfully reset");
    }
    else
    {
      v15 = v23;
      LogLevelW(2u, L"Failed to reset datastore. hr = 0x%08x", (unsigned int)v23);
    }
    v25 = (const char *)(unsigned int)WaasMedic::CStackDataResetPlugin::DeleteServiceFolderIfExists(
                                        v24,
                                        L"%windir%\\SoftwareDistribution\\Download");
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      v25,
      (int)"Failed to cleanup software distribution folder",
      v38);
    if ( (int)v25 < 0 )
      v15 = (int)v25;
    v27 = (const char *)(unsigned int)WaasMedic::CStackDataResetPlugin::DeleteServiceFolderIfExists(
                                        v26,
                                        L"%Programdata%\\Microsoft\\Network\\Downloader");
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      v27,
      (int)"Failed to cleanup Bits download folder",
      v39);
    if ( (int)v27 < 0 )
      v15 = (int)v27;
    v28 = (const char *)(unsigned int)RegDeleteTreeW(
                                        HKEY_LOCAL_MACHINE,
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeliveryOptimization\\Jobs");
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\stackdataresetplugin.cpp",
      v28,
      (int)"Failed to delete Delivery Optimization Jobs regkey",
      v40);
    if ( (int)v28 < 0 )
      v15 = (int)v28;
  }
  else
  {
    v16 = 0;
    LogLevelW(2u, L"Unable to stop all the services. Aborting execution. hr = 0x%08x", 0);
    v17 = v46;
  }
  v29 = WaasMedic::TelemetryProvider::Provider();
  v30 = v29;
  if ( *(_DWORD *)v29 > 5u )
  {
    v31 = *((_QWORD *)v29 + 3);
    if ( (*((_QWORD *)v30 + 2) & 0x400000000000LL) != 0 && (v31 & 0x400000000000LL) == v31 )
    {
      v45 = v15;
      v47 = v5;
      v43 = -51 * (((char *)*(&xmmword_180099228 + 1) - (char *)xmmword_180099228) >> 3);
      LODWORD(v46) = v16;
      v32 = (const unsigned __int16 *)((char *)v17 + 120);
      if ( *((_QWORD *)v17 + 18) > 0xFu )
        v32 = *(const unsigned __int16 **)v32;
      *(_QWORD *)&v53[0] = 0x1000000;
      v68[0] = &v45;
      v68[1] = 4;
      v66 = &v47;
      v67 = 4;
      *((_QWORD *)&v64 + 1) = &v41;
      v65 = 1;
      v63 = (__int64)&v43;
      *(_QWORD *)&v64 = 1;
      *(_QWORD *)&v62 = &v46;
      *((_QWORD *)&v62 + 1) = 4;
      *(_QWORD *)&v61 = v42;
      *((_QWORD *)&v61 + 1) = 2;
      v59 = &v44;
      v60 = 4;
      if ( v32 )
      {
        do
          ++v3;
        while ( *((_BYTE *)v32 + v3) );
        v4 = v3 + 1;
      }
      else
      {
        v32 = &qword_180067AD0;
      }
      *((_QWORD *)&v57 + 1) = v32;
      v58 = v4;
      v56 = (__int64)v53;
      *(_QWORD *)&v57 = 8;
      tlgWriteTransfer_EventWriteTransfer(v30, &dword_1800897BC, 0, 0, 11, v55);
    }
  }
  v22 = v15;
LABEL_47:
  VariantClear(&pvarg);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18003b8c0  push    rbp
0x18003b8c2  push    rbx
0x18003b8c3  push    rsi
0x18003b8c4  push    rdi
0x18003b8c5  push    r12
0x18003b8c7  push    r13
0x18003b8c9  push    r14
0x18003b8cb  push    r15
0x18003b8cd  lea     rbp, [rsp-0A8h]
0x18003b8d5  sub     rsp, 1A8h
0x18003b8dc  mov     rax, cs:__security_cookie
0x18003b8e3  xor     rax, rsp
0x18003b8e6  mov     [rbp+0E0h+var_50], rax
0x18003b8ed  mov     rbx, rcx
0x18003b8f0  mov     [rsp+1E0h+var_198], rcx
0x18003b8f5  xor     edi, edi
0x18003b8f7  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18003b8fb  call    cs:__imp_VariantInit
0x18003b901  nop
0x18003b902  xor     eax, eax
0x18003b904  mov     [rsp+1E0h+var_168], rax
0x18003b909  xorps   xmm1, xmm1
0x18003b90c  movdqu  [rsp+1E0h+var_178], xmm1
0x18003b912  mov     byte ptr [rsp+1E0h+var_168], dil
0x18003b917  mov     [rsp+1E0h+var_180], dil
0x18003b91c  mov     eax, [rbx+0E8h]
0x18003b922  mov     [rsp+1E0h+var_188], eax
0x18003b926  mov     [rsp+1E0h+var_184], 2
0x18003b92e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003b932  mov     [rsp+1E0h+var_1A4], esi
0x18003b936  mov     [rsp+1E0h+var_1AC], si
0x18003b93b  mov     ecx, cs:_tls_index
0x18003b941  mov     rax, gs:58h
0x18003b94a  mov     edx, 10h
0x18003b94f  mov     rax, [rax+rcx*8]
0x18003b953  lea     ebx, [rdi+4]
0x18003b956  lea     r14d, [rdi+1]
0x18003b95a  mov     eax, [rdx+rax]
0x18003b95d  cmp     cs:dword_180099220, eax
0x18003b963  jg      loc_18003BDFB
0x18003b969  mov     r12d, edi
0x18003b96c  mov     [rsp+1E0h+var_1B0], dil
0x18003b971  mov     r15b, dil
0x18003b974  mov     rbx, qword ptr cs:xmmword_180099228
0x18003b97b  mov     r13, qword ptr cs:xmmword_180099228+8
0x18003b982  cmp     rbx, r13
0x18003b985  jz      loc_18003BA1A
0x18003b98b  cmp     qword ptr [rbx+18h], 7
0x18003b990  jbe     short loc_18003B997
0x18003b992  mov     r8, [rbx]
0x18003b995  jmp     short loc_18003B99A
0x18003b997  mov     r8, rbx
0x18003b99a  lea     rdx, aAttemptingToSt; "Attempting to stop service %s"
0x18003b9a1  mov     ecx, 4; unsigned __int8
0x18003b9a6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003b9ab  cmp     qword ptr [rbx+18h], 7
0x18003b9b0  jbe     short loc_18003B9B7
0x18003b9b2  mov     rcx, [rbx]
0x18003b9b5  jmp     short loc_18003B9BA
0x18003b9b7  mov     rcx, rbx; unsigned __int16 *
0x18003b9ba  mov     dl, r14b; bool
0x18003b9bd  call    ?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z; WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)
0x18003b9c2  cmp     edi, 2
0x18003b9c5  jnz     short loc_18003BA08
0x18003b9c7  test    eax, eax
0x18003b9c9  js      short loc_18003B9D1
0x18003b9cb  or      r15b, [rbx+20h]
0x18003b9cf  jmp     short loc_18003B9D4
0x18003b9d1  mov     r12d, eax
0x18003b9d4  lea     rcx, word_18006939C
0x18003b9db  lea     r9, aNot_0; "not "
0x18003b9e2  test    eax, eax
0x18003b9e4  cmovns  r9, rcx
0x18003b9e8  cmp     qword ptr [rbx+18h], 7
0x18003b9ed  jbe     short loc_18003B9F4
0x18003b9ef  mov     r8, [rbx]
0x18003b9f2  jmp     short loc_18003B9F7
0x18003b9f4  mov     r8, rbx
0x18003b9f7  lea     rdx, aSWasSstopped; "%s was %sstopped."
0x18003b9fe  mov     ecx, 4; unsigned __int8
0x18003ba03  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003ba08  add     rbx, 28h ; '('
0x18003ba0c  cmp     rbx, r13
0x18003ba0f  jnz     loc_18003B98B
0x18003ba15  mov     [rsp+1E0h+var_1B0], r15b
0x18003ba1a  add     edi, r14d
0x18003ba1d  cmp     edi, 3
0x18003ba20  jb      loc_18003B974
0x18003ba26  xor     ebx, ebx
0x18003ba28  test    r12d, r12d
0x18003ba2b  mov     r15d, ebx
0x18003ba2e  jns     short loc_18003BA4E
0x18003ba30  mov     edi, ebx
0x18003ba32  xor     r8d, r8d
0x18003ba35  lea     rdx, aUnableToStopAl; "Unable to stop all the services. Aborti"...
0x18003ba3c  lea     ecx, [rbx+2]; unsigned __int8
0x18003ba3f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003ba44  mov     r13, [rsp+1E0h+var_198]
0x18003ba49  jmp     loc_18003BC51
0x18003ba4e  lea     rcx, [rsp+1E0h+var_1A4]; int *
0x18003ba53  call    ?FreeSpaceInGB@MiscUtil@WaasMedic@@SAJAEAH@Z; WaasMedic::MiscUtil::FreeSpaceInGB(int &)
0x18003ba58  mov     rcx, [rbp+0E8h]; this
0x18003ba5f  lea     rdx, aFreespaceingbF; "FreeSpaceInGB failed"
0x18003ba66  mov     qword ptr [rsp+1E0h+var_1C0], rdx; int
0x18003ba6b  mov     r9d, eax; char *
0x18003ba6e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003ba75  mov     edx, 0EDh; void *
0x18003ba7a  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003ba7f  lea     rcx, [rsp+1E0h+var_1AC]; __int16 *
0x18003ba84  call    ?GetSizeOfDatastore@MiscUtil@WaasMedic@@SAJAEAF@Z; WaasMedic::MiscUtil::GetSizeOfDatastore(short &)
0x18003ba89  mov     rcx, [rbp+0E8h]; this
0x18003ba90  lea     rdx, aGetsizeofdatas; "GetSizeOfDatastore failed"
0x18003ba97  mov     qword ptr [rsp+1E0h+var_1C0], rdx; int
0x18003ba9c  mov     r9d, eax; char *
0x18003ba9f  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003baa6  mov     edx, 0EEh; void *
0x18003baab  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003bab0  mov     r13, [rsp+1E0h+var_198]
0x18003bab5  mov     rdi, [r13+68h]
0x18003bab9  mov     rax, [rdi]
0x18003babc  mov     rbx, [rax]
0x18003babf  xorps   xmm0, xmm0
0x18003bac2  movups  [rbp+0E0h+var_120], xmm0
0x18003bac6  xorps   xmm1, xmm1
0x18003bac9  movdqu  [rbp+0E0h+var_110], xmm1
0x18003bace  mov     r8d, 10h
0x18003bad4  lea     rdx, aLowdiskvaluein; "LowDiskValueInGb"
0x18003badb  lea     rcx, [rbp+0E0h+var_120]
0x18003badf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003bae4  nop
0x18003bae5  xorps   xmm0, xmm0
0x18003bae8  movups  [rbp+0E0h+var_140], xmm0
0x18003baec  xorps   xmm1, xmm1
0x18003baef  movdqu  [rbp+0E0h+var_130], xmm1
0x18003baf4  mov     r8d, 14h
0x18003bafa  lea     rdx, aStackdatareset; "StackDataResetPlugin"
0x18003bb01  lea     rcx, [rbp+0E0h+var_140]
0x18003bb05  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003bb0a  nop
0x18003bb0b  lea     r9, [rsp+1E0h+var_188]
0x18003bb10  lea     r8, [rbp+0E0h+var_120]
0x18003bb14  lea     rdx, [rbp+0E0h+var_140]
0x18003bb18  mov     rcx, rdi
0x18003bb1b  mov     rax, rbx
0x18003bb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb23  mov     ebx, eax
0x18003bb25  lea     rcx, [rbp+0E0h+var_140]; void *
0x18003bb29  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bb2e  nop
0x18003bb2f  lea     rcx, [rbp+0E0h+var_120]; void *
0x18003bb33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bb38  test    ebx, ebx
0x18003bb3a  jns     short loc_18003BB5D
0x18003bb3c  mov     rcx, [rbp+0E8h]; this
0x18003bb43  mov     r9d, ebx; char *
0x18003bb46  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003bb4d  mov     edx, 0F0h; void *
0x18003bb52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb57  nop
0x18003bb58  jmp     loc_18003BDCC
0x18003bb5d  mov     ecx, [rsp+1E0h+var_188]; int
0x18003bb61  call    ?ResetDataStore@MiscUtil@WaasMedic@@SAJH@Z; WaasMedic::MiscUtil::ResetDataStore(int)
0x18003bb66  mov     edi, eax
0x18003bb68  test    eax, eax
0x18003bb6a  jns     short loc_18003BB85
0x18003bb6c  mov     r15d, eax
0x18003bb6f  mov     r8d, eax
0x18003bb72  lea     rdx, aFailedToResetD; "Failed to reset datastore. hr = 0x%08x"
0x18003bb79  mov     ecx, 2; unsigned __int8
0x18003bb7e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003bb83  jmp     short loc_18003BB96
0x18003bb85  lea     rdx, aDatastoreSucce; "Datastore successfully reset"
0x18003bb8c  mov     ecx, 4; unsigned __int8
0x18003bb91  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003bb96  lea     rdx, aWindirSoftware; "%windir%\\SoftwareDistribution\\Downloa"...
0x18003bb9d  call    ?DeleteServiceFolderIfExists@CStackDataResetPlugin@WaasMedic@@AEAAJPEBG@Z; WaasMedic::CStackDataResetPlugin::DeleteServiceFolderIfExists(ushort const *)
0x18003bba2  mov     ebx, eax
0x18003bba4  mov     rcx, [rbp+0E8h]; this
0x18003bbab  lea     rax, aFailedToCleanu_0; "Failed to cleanup software distribution"...
0x18003bbb2  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18003bbb7  mov     r9d, ebx; char *
0x18003bbba  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003bbc1  mov     edx, 0FDh; void *
0x18003bbc6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003bbcb  test    ebx, ebx
0x18003bbcd  cmovs   r15d, ebx
0x18003bbd1  lea     rdx, aProgramdataMic; "%Programdata%\\Microsoft\\Network\\Down"...
0x18003bbd8  call    ?DeleteServiceFolderIfExists@CStackDataResetPlugin@WaasMedic@@AEAAJPEBG@Z; WaasMedic::CStackDataResetPlugin::DeleteServiceFolderIfExists(ushort const *)
0x18003bbdd  mov     ebx, eax
0x18003bbdf  mov     rcx, [rbp+0E8h]; this
0x18003bbe6  lea     rax, aFailedToCleanu; "Failed to cleanup Bits download folder"
0x18003bbed  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18003bbf2  mov     r9d, ebx; char *
0x18003bbf5  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003bbfc  mov     edx, 100h; void *
0x18003bc01  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003bc06  test    ebx, ebx
0x18003bc08  cmovs   r15d, ebx
0x18003bc0c  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003bc13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bc1a  call    cs:__imp_RegDeleteTreeW
0x18003bc20  mov     ebx, eax
0x18003bc22  mov     rcx, [rbp+0E8h]; this
0x18003bc29  lea     rax, aFailedToDelete_2; "Failed to delete Delivery Optimization "...
0x18003bc30  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18003bc35  mov     r9d, ebx; char *
0x18003bc38  lea     r8, aOnecoreEnduser; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18003bc3f  mov     edx, 104h; void *
0x18003bc44  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003bc49  test    ebx, ebx
0x18003bc4b  cmovs   r15d, ebx
0x18003bc4f  xor     ebx, ebx
0x18003bc51  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18003bc56  mov     r10, rax
0x18003bc59  mov     ecx, [rax]
0x18003bc5b  cmp     ecx, 5
0x18003bc5e  jbe     loc_18003BDC9
0x18003bc64  mov     rax, [rax+18h]
0x18003bc68  mov     rcx, [r10+10h]
0x18003bc6c  mov     rdx, 400000000000h
0x18003bc76  test    rdx, rcx
0x18003bc79  jz      loc_18003BDC9
0x18003bc7f  mov     rcx, rax
0x18003bc82  and     rcx, rdx
0x18003bc85  cmp     rcx, rax
0x18003bc88  jnz     loc_18003BDC9
0x18003bc8e  mov     [rsp+1E0h+var_1A0], r15d
0x18003bc93  mov     [rsp+1E0h+var_190], r12d
0x18003bc98  mov     al, [rsp+1E0h+var_1B0]
0x18003bc9c  mov     [rsp+1E0h+var_1B0], al
0x18003bca0  mov     rax, qword ptr cs:xmmword_180099228+8
0x18003bca7  sub     rax, qword ptr cs:xmmword_180099228
0x18003bcae  sar     rax, 3
0x18003bcb2  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18003bcbc  imul    rax, rcx
0x18003bcc0  mov     [rsp+1E0h+var_1A8], al
0x18003bcc4  mov     dword ptr [rsp+1E0h+var_198], edi
0x18003bcc8  movzx   eax, [rsp+1E0h+var_1AC]
0x18003bccd  mov     [rsp+1E0h+var_1AC], ax
0x18003bcd2  mov     eax, [rsp+1E0h+var_1A4]
0x18003bcd6  mov     [rsp+1E0h+var_1A4], eax
0x18003bcda  lea     rax, [r13+78h]
0x18003bcde  cmp     qword ptr [rax+18h], 0Fh
0x18003bce3  jbe     short loc_18003BCE8
0x18003bce5  mov     rax, [rax]
0x18003bce8  mov     qword ptr [rbp+0E0h+var_140], 1000000h
0x18003bcf0  lea     rcx, [rsp+1E0h+var_1A0]
0x18003bcf5  mov     [rbp+0E0h+var_60], rcx
0x18003bcfc  mov     [rbp+0E0h+var_58], 4
0x18003bd07  lea     rcx, [rsp+1E0h+var_190]
0x18003bd0c  mov     [rbp+0E0h+var_70], rcx
0x18003bd10  mov     [rbp+0E0h+var_68], 4
0x18003bd18  lea     rcx, [rsp+1E0h+var_1B0]
0x18003bd1d  mov     qword ptr [rbp+0E0h+var_88+8], rcx
0x18003bd21  mov     [rbp+0E0h+var_78], 1
0x18003bd29  lea     rcx, [rsp+1E0h+var_1A8]
0x18003bd2e  mov     [rbp+0E0h+var_90], rcx
0x18003bd32  mov     qword ptr [rbp+0E0h+var_88], 1
0x18003bd3a  lea     rcx, [rsp+1E0h+var_198]
0x18003bd3f  mov     qword ptr [rbp+0E0h+var_A0], rcx
0x18003bd43  mov     qword ptr [rbp+0E0h+var_A0+8], 4
0x18003bd4b  lea     rcx, [rsp+1E0h+var_1AC]
0x18003bd50  mov     qword ptr [rbp+0E0h+var_B0], rcx
0x18003bd54  mov     qword ptr [rbp+0E0h+var_B0+8], 2
0x18003bd5c  lea     rcx, [rsp+1E0h+var_1A4]
0x18003bd61  mov     [rbp+0E0h+var_C0], rcx
0x18003bd65  mov     [rbp+0E0h+var_B8], 4
0x18003bd6d  test    rax, rax
0x18003bd70  jz      short loc_18003BD80
0x18003bd72  inc     rsi
0x18003bd75  cmp     [rax+rsi], bl
0x18003bd78  jnz     short loc_18003BD72
0x18003bd7a  lea     r14d, [rsi+1]
0x18003bd7e  jmp     short loc_18003BD87
0x18003bd80  lea     rax, qword_180067AD0
0x18003bd87  mov     qword ptr [rbp+0E0h+var_D8+8], rax
0x18003bd8b  mov     dword ptr [rbp+0E0h+var_C8], r14d
0x18003bd8f  mov     dword ptr [rbp+0E0h+var_C8+4], ebx
0x18003bd92  lea     rax, [rbp+0E0h+var_140]
0x18003bd96  mov     [rbp+0E0h+var_E0], rax
0x18003bd9a  mov     qword ptr [rbp+0E0h+var_D8], 8
0x18003bda2  lea     rax, [rbp+0E0h+var_100]
0x18003bda6  mov     [rsp+1E0h+var_1B8], rax
0x18003bdab  mov     [rsp+1E0h+var_1C0], 0Bh
0x18003bdb3  xor     r9d, r9d
0x18003bdb6  xor     r8d, r8d
0x18003bdb9  lea     rdx, dword_1800897BC
0x18003bdc0  mov     rcx, r10
0x18003bdc3  call    _tlgWriteTransfer_EventWriteTransfer
0x18003bdc8  nop
0x18003bdc9  mov     ebx, r15d
0x18003bdcc  lea     rcx, [rbp+0E0h+pvarg]; pvarg
0x18003bdd0  call    cs:__imp_VariantClear
0x18003bdd6  mov     eax, ebx
0x18003bdd8  mov     rcx, [rbp+0E0h+var_50]
0x18003bddf  xor     rcx, rsp; StackCookie
0x18003bde2  call    __security_check_cookie
0x18003bde7  add     rsp, 1A8h
0x18003bdee  pop     r15
0x18003bdf0  pop     r14
  ... truncated ...
```
