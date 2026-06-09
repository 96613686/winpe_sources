# GenericCallPackageHelper::WriteCredentialsByTargetName(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CSecureString &)

- ea: `0x18004a1ac`
- end: `0x18004a64c`
- name: `?WriteCredentialsByTargetName@GenericCallPackageHelper@@CAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAVCSecureString@@@Z`
- size: `1184`
- prototype: `__int64 __fastcall(struct AadContextFunctions *, LPWSTR *, LPWSTR *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18004a654`

## callees

- `0x180003c44`
- `0x180003c50`
- `0x180004a24`
- `0x1800069c0`
- `0x180006ac4`
- `0x180007d7c`
- `0x180007dd4`
- `0x18001502c`
- `0x180042f70`
- `0x180042fb8`
- `0x18004a1ac`
- `0x180071e14`
- `0x180076228`
- `0x1800781d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a613`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a61d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a613`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a577`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18004a55b`
- `api-ms-win-security-credentials-l1-1-0!CredWriteW` at `0x18004a55b`

## string_xrefs

- `0x18004a213`: `GenericCallPackageHelper::WriteCredentialsByTargetName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GenericCallPackageHelper::WriteCredentialsByTargetName(
        struct AadContextFunctions *a1,
        LPWSTR *a2,
        LPWSTR *a3,
        _QWORD *a4)
{
  struct _CREDENTIAL_ATTRIBUTEW *v7; // rbx
  char *v8; // r12
  DWORD v9; // r14d
  BYTE *v10; // rcx
  BYTE *v11; // rdx
  BYTE *v12; // r13
  int v13; // edi
  int v14; // eax
  DWORD v15; // r15d
  bool v16; // zf
  __int64 v17; // rcx
  struct _CREDENTIAL_ATTRIBUTEW *v18; // rsi
  int v19; // eax
  LPWSTR *v20; // rdi
  signed int v21; // eax
  unsigned int v22; // esi
  struct _AP_BLOB *v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+50h] [rbp-B0h]
  struct _CREDENTIAL_ATTRIBUTEW *v26; // [rsp+58h] [rbp-A8h] BYREF
  char *v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v28; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v29; // [rsp+70h] [rbp-90h]
  DWORD v30; // [rsp+78h] [rbp-88h] BYREF
  BYTE *v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  _CREDENTIALW Credential; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[96]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v36; // [rsp+168h] [rbp+68h] BYREF

  v36 = 0;
  memset_0(&Credential, 0, sizeof(Credential));
  v31 = 0;
  v30 = 0;
  v7 = 0;
  v26 = 0;
  v32 = 0;
  v8 = 0;
  v27 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    v34,
    "genericcallpackagehelper.cpp",
    "GenericCallPackageHelper::WriteCredentialsByTargetName",
    &v36);
  if ( *(_DWORD *)(*a4 - 16LL) )
  {
    v29 = 0;
    v28 = 0;
    v13 = StringUtility::Base64Decode(a1, a4, &v28);
    if ( v13 < 0 )
    {
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v13, "genericcallpackagehelper.cpp", 2255, "HRESULT", &base);
      v36 = v13 & 0xAFFFFFFF | 0x40000000;
      PluginLocalFreeApBlob((struct _AP_BLOB *)&v28);
      goto LABEL_29;
    }
    v14 = DPAPIProtect(a1, v29, v28, 0, (struct _AP_BLOB *)&v30);
    v36 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v24) = v14;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "genericcallpackagehelper.cpp", 2256, "NTSTATUS", &base);
      PluginLocalFreeApBlob((struct _AP_BLOB *)&v28);
      goto LABEL_29;
    }
    v9 = v30;
    PluginLocalFreeApBlob((struct _AP_BLOB *)&v28);
    if ( v9 > 0x4000 )
    {
      LODWORD(v24) = -2147187504;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "genericcallpackagehelper.cpp", 2263, "HRESULT", &base);
      v36 = -1073445680;
      goto LABEL_29;
    }
    v10 = v31;
    v12 = v31;
    v11 = v31;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = 0;
  }
  Credential.Type = 1;
  Credential.TargetName = *a3;
  Credential.Persist = 2;
  Credential.UserName = *a2;
  Credential.CredentialBlob = v10;
  Credential.CredentialBlobSize = v9;
  v15 = 0;
  v16 = v9 == 0;
  if ( v9 )
  {
    v15 = (v9 + 255) >> 8;
    v16 = v9 == 0;
  }
  if ( v16 )
    v12 = v11;
  if ( (unsigned __int8)ATL::CAutoVectorPtr<_CREDENTIAL_ATTRIBUTEW>::Allocate(&v26, v15) )
  {
    if ( (unsigned __int8)ATL::CAutoVectorPtr<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Allocate(
                            &v27,
                            v15) )
    {
      Credential.AttributeCount = v15;
      v7 = v26;
      Credential.Attributes = v26;
      v17 = 0;
      v25 = 0;
      v8 = v27;
      if ( v15 )
      {
        v18 = v26;
        do
        {
          v18->Keyword = 0;
          v18->Flags = 0;
          v18->Value = v12;
          v19 = v9;
          if ( v9 >= 0x100 )
            v19 = 256;
          v18->ValueSize = v19;
          v9 -= v19;
          v20 = (LPWSTR *)&v8[8 * v17];
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
            v20,
            L"%s%-d",
            L"Microsoft_WindowsLive:authstate:",
            (unsigned int)v17);
          v18->Keyword = *v20;
          v12 += 256;
          ++v18;
          v17 = (unsigned int)(v25 + 1);
          v25 = v17;
        }
        while ( (unsigned int)v17 < v15 );
      }
      if ( !CredWriteW(&Credential, 0) )
      {
        v21 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
        v36 = v21;
        if ( v21 < 0 )
        {
          LODWORD(v24) = v21;
          WPPTraceLogA(
            2,
            0,
            "%x 0x%08x %s:%u : %s:%ws",
            2,
            v24,
            "genericcallpackagehelper.cpp",
            2319,
            "NTSTATUS",
            &base);
        }
      }
    }
    else
    {
      v36 = -1073741801;
      LODWORD(v24) = -1073741801;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "genericcallpackagehelper.cpp", 2289, "NTSTATUS", &base);
      v7 = v26;
      v8 = v27;
    }
  }
  else
  {
    v36 = -1073741801;
    LODWORD(v24) = -1073741801;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v24, "genericcallpackagehelper.cpp", 2284, "NTSTATUS", &base);
    v7 = v26;
  }
LABEL_29:
  v22 = v36;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v34);
  if ( v8 )
  {
    `eh vector destructor iterator'(
      v8,
      8u,
      *((_QWORD *)v8 - 1),
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>);
    operator delete(v8 - 8, (const struct std::nothrow_t *)(8LL * *((_QWORD *)v8 - 1) + 8));
  }
  free(0);
  free(v7);
  PluginLsaFreeApBlob((struct _AP_BLOB *)&v30);
  return v22;
}

```

## disassembly

```asm
0x18004a1ac  mov     [rsp-8+arg_0], rbx
0x18004a1b1  mov     [rsp-8+arg_8], rdx
0x18004a1b6  push    rbp
0x18004a1b7  push    rsi
0x18004a1b8  push    rdi
0x18004a1b9  push    r12
0x18004a1bb  push    r13
0x18004a1bd  push    r14
0x18004a1bf  push    r15
0x18004a1c1  lea     rbp, [rsp-10h]
0x18004a1c6  sub     rsp, 110h
0x18004a1cd  mov     rdi, r9
0x18004a1d0  mov     r15, r8
0x18004a1d3  mov     rsi, rcx
0x18004a1d6  mov     [rbp+40h+arg_18], 0
0x18004a1dd  xor     edx, edx; Val
0x18004a1df  lea     r8d, [rdx+50h]; Size
0x18004a1e3  lea     rcx, [rbp+40h+Credential]; void *
0x18004a1e7  call    memset_0
0x18004a1ec  mov     [rbp+40h+var_C0], 0
0x18004a1f4  mov     [rsp+140h+var_C8], 0
0x18004a1fc  xor     ebx, ebx
0x18004a1fe  mov     [rsp+140h+var_E8], rbx
0x18004a203  mov     [rbp+40h+var_B8], rbx
0x18004a207  xor     r12d, r12d
0x18004a20a  mov     [rsp+140h+var_E0], r12
0x18004a20f  lea     r9, [rbp+40h+arg_18]
0x18004a213  lea     r8, aGenericcallpac; "GenericCallPackageHelper::WriteCredenti"...
0x18004a21a  lea     r13, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x18004a221  mov     rdx, r13
0x18004a224  lea     rcx, [rbp+40h+var_60]
0x18004a228  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18004a22d  nop
0x18004a22e  mov     rax, [rdi]
0x18004a231  cmp     [rax-10h], r12d
0x18004a235  jnz     short loc_18004A246
0x18004a237  xor     r14d, r14d
0x18004a23a  xor     ecx, ecx
0x18004a23c  xor     edx, edx
0x18004a23e  xor     r13d, r13d
0x18004a241  jmp     loc_18004A3B5
0x18004a246  mov     [rsp+140h+var_D0], 0
0x18004a24f  mov     [rsp+140h+var_D8], 0
0x18004a257  lea     r8, [rsp+140h+var_D8]
0x18004a25c  mov     rdx, rdi
0x18004a25f  mov     rcx, rsi
0x18004a262  call    ?Base64Decode@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N@Z; StringUtility::Base64Decode(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool)
0x18004a267  mov     edi, eax
0x18004a269  test    eax, eax
0x18004a26b  jns     short loc_18004A2C9
0x18004a26d  lea     rcx, base
0x18004a274  mov     [rsp+140h+var_100], rcx
0x18004a279  lea     rax, aHresult; "HRESULT"
0x18004a280  mov     [rsp+140h+var_108], rax
0x18004a285  mov     [rsp+140h+var_110], 8CFh
0x18004a28d  mov     [rsp+140h+var_118], r13
0x18004a292  mov     dword ptr [rsp+140h+var_120], edi
0x18004a296  mov     esi, 2
0x18004a29b  mov     r9d, esi
0x18004a29e  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004a2a5  xor     edx, edx
0x18004a2a7  mov     ecx, esi
0x18004a2a9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004a2ae  btr     edi, 1Ch
0x18004a2b2  bts     edi, 1Eh
0x18004a2b6  mov     [rbp+40h+arg_18], edi
0x18004a2b9  lea     rcx, [rsp+140h+var_D8]; struct _AP_BLOB *
0x18004a2be  call    ?PluginLocalFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLocalFreeApBlob(_AP_BLOB *)
0x18004a2c3  nop
0x18004a2c4  jmp     loc_18004A5CF
0x18004a2c9  lea     rax, [rsp+140h+var_C8]
0x18004a2ce  mov     [rsp+140h+var_120], rax; struct _AP_BLOB *
0x18004a2d3  xor     r9d, r9d; unsigned __int16 *
0x18004a2d6  mov     r8d, [rsp+140h+var_D8]; unsigned int
0x18004a2db  mov     rdx, [rsp+140h+var_D0]; unsigned __int8 *
0x18004a2e0  mov     rcx, rsi; struct AadContextFunctions *
0x18004a2e3  call    ?DPAPIProtect@@YAJPEAVAadContextFunctions@@PEAEKPEBGPEAU_AP_BLOB@@@Z; DPAPIProtect(AadContextFunctions *,uchar *,ulong,ushort const *,_AP_BLOB *)
0x18004a2e8  mov     [rbp+40h+arg_18], eax
0x18004a2eb  test    eax, eax
0x18004a2ed  jns     short loc_18004A341
0x18004a2ef  lea     rcx, base
0x18004a2f6  mov     [rsp+140h+var_100], rcx
0x18004a2fb  lea     rcx, aNtstatus; "NTSTATUS"
0x18004a302  mov     [rsp+140h+var_108], rcx
0x18004a307  mov     [rsp+140h+var_110], 8D0h
0x18004a30f  mov     [rsp+140h+var_118], r13
0x18004a314  mov     dword ptr [rsp+140h+var_120], eax
0x18004a318  mov     esi, 2
0x18004a31d  mov     r9d, esi
0x18004a320  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004a327  xor     edx, edx
0x18004a329  mov     ecx, esi
0x18004a32b  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004a330  nop
0x18004a331  lea     rcx, [rsp+140h+var_D8]; struct _AP_BLOB *
0x18004a336  call    ?PluginLocalFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLocalFreeApBlob(_AP_BLOB *)
0x18004a33b  nop
0x18004a33c  jmp     loc_18004A5CF
0x18004a341  mov     r14d, [rsp+140h+var_C8]
0x18004a346  lea     rcx, [rsp+140h+var_D8]; struct _AP_BLOB *
0x18004a34b  call    ?PluginLocalFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLocalFreeApBlob(_AP_BLOB *)
0x18004a350  nop
0x18004a351  cmp     r14d, 4000h
0x18004a358  jbe     short loc_18004A3AB
0x18004a35a  lea     rcx, base
0x18004a361  mov     [rsp+140h+var_100], rcx
0x18004a366  lea     rax, aHresult; "HRESULT"
0x18004a36d  mov     [rsp+140h+var_108], rax
0x18004a372  mov     [rsp+140h+var_110], 8D7h
0x18004a37a  mov     [rsp+140h+var_118], r13
0x18004a37f  mov     dword ptr [rsp+140h+var_120], 800484D0h
0x18004a387  mov     esi, 2
0x18004a38c  mov     r9d, esi
0x18004a38f  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004a396  xor     edx, edx
0x18004a398  mov     ecx, esi
0x18004a39a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004a39f  mov     [rbp+40h+arg_18], 0C00484D0h
0x18004a3a6  jmp     loc_18004A5CF
0x18004a3ab  mov     rcx, [rbp+40h+var_C0]
0x18004a3af  mov     r13, rcx
0x18004a3b2  mov     rdx, rcx
0x18004a3b5  mov     [rbp+40h+Credential.Type], 1
0x18004a3bc  mov     rax, [r15]
0x18004a3bf  mov     [rbp+40h+Credential.TargetName], rax
0x18004a3c3  mov     esi, 2
0x18004a3c8  mov     [rbp+40h+Credential.Persist], esi
0x18004a3cb  mov     rax, [rbp+40h+arg_8]
0x18004a3cf  mov     rax, [rax]
0x18004a3d2  mov     [rbp+40h+Credential.UserName], rax
0x18004a3d6  mov     [rbp+40h+Credential.CredentialBlob], rcx
0x18004a3da  mov     [rbp+40h+Credential.CredentialBlobSize], r14d
0x18004a3de  xor     r15d, r15d
0x18004a3e1  test    r14d, r14d
0x18004a3e4  jz      short loc_18004A3F4
0x18004a3e6  lea     r15d, [r14+0FFh]
0x18004a3ed  shr     r15d, 8
0x18004a3f1  test    r14d, r14d
0x18004a3f4  cmovz   r13, rdx
0x18004a3f8  mov     ebx, r15d
0x18004a3fb  mov     edx, r15d
0x18004a3fe  lea     rcx, [rsp+140h+var_E8]
0x18004a403  call    ?Allocate@?$CAutoVectorPtr@U_CREDENTIAL_ATTRIBUTEW@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CREDENTIAL_ATTRIBUTEW>::Allocate(unsigned __int64)
0x18004a408  test    al, al
0x18004a40a  jnz     short loc_18004A461
0x18004a40c  mov     eax, 0C0000017h
0x18004a411  mov     [rbp+40h+arg_18], eax
0x18004a414  lea     rcx, base
0x18004a41b  mov     [rsp+140h+var_100], rcx
0x18004a420  lea     rcx, aNtstatus; "NTSTATUS"
0x18004a427  mov     [rsp+140h+var_108], rcx
0x18004a42c  mov     [rsp+140h+var_110], 8ECh
0x18004a434  lea     rcx, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x18004a43b  mov     [rsp+140h+var_118], rcx
0x18004a440  mov     dword ptr [rsp+140h+var_120], eax
0x18004a444  mov     r9d, esi
0x18004a447  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004a44e  xor     edx, edx
0x18004a450  mov     ecx, esi
0x18004a452  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004a457  mov     rbx, [rsp+140h+var_E8]
0x18004a45c  jmp     loc_18004A5CF
0x18004a461  mov     rdx, rbx
0x18004a464  lea     rcx, [rsp+140h+var_E0]
0x18004a469  call    ?Allocate@?$CAutoVectorPtr@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Allocate(unsigned __int64)
0x18004a46e  test    al, al
0x18004a470  jnz     short loc_18004A4CC
0x18004a472  mov     eax, 0C0000017h
0x18004a477  mov     [rbp+40h+arg_18], eax
0x18004a47a  lea     rcx, base
0x18004a481  mov     [rsp+140h+var_100], rcx
0x18004a486  lea     rcx, aNtstatus; "NTSTATUS"
0x18004a48d  mov     [rsp+140h+var_108], rcx
0x18004a492  mov     [rsp+140h+var_110], 8F1h
0x18004a49a  lea     rcx, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x18004a4a1  mov     [rsp+140h+var_118], rcx
0x18004a4a6  mov     dword ptr [rsp+140h+var_120], eax
0x18004a4aa  mov     r9d, esi
0x18004a4ad  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004a4b4  xor     edx, edx
0x18004a4b6  mov     ecx, esi
0x18004a4b8  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004a4bd  mov     rbx, [rsp+140h+var_E8]
0x18004a4c2  mov     r12, [rsp+140h+var_E0]
0x18004a4c7  jmp     loc_18004A5CF
0x18004a4cc  mov     [rbp+40h+Credential.AttributeCount], r15d
0x18004a4d0  mov     rbx, [rsp+140h+var_E8]
0x18004a4d5  mov     [rbp+40h+Credential.Attributes], rbx
0x18004a4d9  xor     ecx, ecx
0x18004a4db  mov     [rsp+140h+var_F0], ecx
0x18004a4df  mov     r12, [rsp+140h+var_E0]
0x18004a4e4  test    r15d, r15d
0x18004a4e7  jz      short loc_18004A555
0x18004a4e9  mov     edx, 100h
0x18004a4ee  mov     rsi, rbx
0x18004a4f1  mov     qword ptr [rsi], 0
0x18004a4f8  mov     dword ptr [rsi+8], 0
0x18004a4ff  mov     [rsi+10h], r13
0x18004a503  mov     eax, r14d
0x18004a506  cmp     r14d, edx
0x18004a509  cmovnb  eax, edx
0x18004a50c  mov     [rsi+0Ch], eax
0x18004a50f  sub     r14d, eax
0x18004a512  lea     rdi, [r12+rcx*8]
0x18004a516  mov     r9d, ecx
0x18004a519  lea     r8, aMicrosoftWindo; "Microsoft_WindowsLive:authstate:"
0x18004a520  lea     rdx, aSD; "%s%-d"
0x18004a527  mov     rcx, rdi
0x18004a52a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18004a52f  mov     rax, [rdi]
0x18004a532  mov     [rsi], rax
0x18004a535  mov     edx, 100h
0x18004a53a  add     r13, rdx
0x18004a53d  lea     rsi, [rsi+18h]
0x18004a541  mov     ecx, [rsp+140h+var_F0]
0x18004a545  inc     ecx
0x18004a547  mov     [rsp+140h+var_F0], ecx
0x18004a54b  cmp     ecx, r15d
0x18004a54e  jb      short loc_18004A4F1
0x18004a550  mov     esi, 2
0x18004a555  xor     edx, edx; Flags
0x18004a557  lea     rcx, [rbp+40h+Credential]; Credential
0x18004a55b  call    cs:__imp_CredWriteW
0x18004a561  test    eax, eax
0x18004a563  jnz     short loc_18004A5CF
0x18004a565  call    cs:__imp_GetLastError
0x18004a56b  test    eax, eax
0x18004a56d  jg      short loc_18004A577
0x18004a56f  call    cs:__imp_GetLastError
0x18004a575  jmp     short loc_18004A585
0x18004a577  call    cs:__imp_GetLastError
0x18004a57d  movzx   eax, ax
0x18004a580  or      eax, 0C0070000h
0x18004a585  mov     [rbp+40h+arg_18], eax
0x18004a588  test    eax, eax
0x18004a58a  jns     short loc_18004A5CF
0x18004a58c  lea     rcx, base
0x18004a593  mov     [rsp+140h+var_100], rcx
0x18004a598  lea     rcx, aNtstatus; "NTSTATUS"
0x18004a59f  mov     [rsp+140h+var_108], rcx
0x18004a5a4  mov     [rsp+140h+var_110], 90Fh
0x18004a5ac  lea     rcx, aOnecoreuapDsEx_30+21h; "genericcallpackagehelper.cpp"
0x18004a5b3  mov     [rsp+140h+var_118], rcx
0x18004a5b8  mov     dword ptr [rsp+140h+var_120], eax
0x18004a5bc  mov     r9d, esi
0x18004a5bf  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18004a5c6  xor     edx, edx
0x18004a5c8  mov     ecx, esi
0x18004a5ca  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18004a5cf  mov     esi, [rbp+40h+arg_18]
0x18004a5d2  lea     rcx, [rbp+40h+var_60]
0x18004a5d6  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18004a5db  nop
0x18004a5dc  test    r12, r12
0x18004a5df  jz      short loc_18004A611
0x18004a5e1  lea     rdi, [r12-8]
0x18004a5e6  lea     r9, ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; void (*)(void *)
0x18004a5ed  mov     r8, [rdi]; unsigned __int64
0x18004a5f0  mov     edx, 8; unsigned __int64
0x18004a5f5  mov     rcx, r12; void *
0x18004a5f8  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004a5fd  mov     rdx, [rdi]
0x18004a600  lea     rdx, ds:8[rdx*8]; struct std::nothrow_t *
0x18004a608  mov     rcx, rdi; void *
0x18004a60b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004a610  nop
0x18004a611  xor     ecx, ecx; Block
0x18004a613  call    cs:__imp_free
0x18004a619  nop
0x18004a61a  mov     rcx, rbx; Block
0x18004a61d  call    cs:__imp_free
0x18004a623  nop
0x18004a624  lea     rcx, [rsp+140h+var_C8]; struct _AP_BLOB *
0x18004a629  call    ?PluginLsaFreeApBlob@@YAXPEAU_AP_BLOB@@@Z; PluginLsaFreeApBlob(_AP_BLOB *)
0x18004a62e  nop
0x18004a62f  mov     eax, esi
0x18004a631  mov     rbx, [rsp+140h+arg_0]
0x18004a639  add     rsp, 110h
0x18004a640  pop     r15
0x18004a642  pop     r14
0x18004a644  pop     r13
0x18004a646  pop     r12
0x18004a648  pop     rdi
0x18004a649  pop     rsi
0x18004a64a  pop     rbp
0x18004a64b  retn
```
