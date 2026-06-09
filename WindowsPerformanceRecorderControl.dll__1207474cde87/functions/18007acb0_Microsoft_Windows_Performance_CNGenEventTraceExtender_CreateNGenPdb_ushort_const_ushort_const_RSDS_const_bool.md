# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)

- ea: `0x18007acb0`
- end: `0x18007aef5`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z`
- size: `581`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this, const unsigned __int16 *, const unsigned __int16 *, const struct _RSDS *, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18007aa54`

## callees

- `0x180008330`
- `0x18000a154`
- `0x1800102d8`
- `0x1800131a0`
- `0x18001c820`
- `0x1800251b0`
- `0x180035004`
- `0x18004aaa4`
- `0x18004ece0`
- `0x18007a728`
- `0x18007a7dc`
- `0x18007acb0`
- `0x18007aefc`
- `0x18007afc0`
- `0x18007b0c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18007acf7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18007ad08`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18007acf7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18007ad08`

## string_xrefs

- `0x18007adf9`: `%wsngen.exe createpdb %ws %ws`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _RSDS *a4,
        bool a5)
{
  const char *v9; // rdi
  char *v10; // rbx
  char *v11; // rax
  const char *v12; // r15
  int v13; // ecx
  unsigned __int16 *v14; // rbx
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v15; // rcx
  int v16; // ebx
  unsigned __int16 *Buffer; // rax
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v19; // rcx
  int v20; // eax
  __int64 v21; // r8
  int v22; // edi
  Microsoft::Windows::Performance::CNGenEventTraceExtender *v23; // rcx
  int v24; // eax
  unsigned int v25; // [rsp+30h] [rbp-61h] BYREF
  __int64 v26; // [rsp+38h] [rbp-59h] BYREF
  unsigned __int16 *v27; // [rsp+40h] [rbp-51h] BYREF
  int v28; // [rsp+48h] [rbp-49h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-41h] BYREF
  __int64 v30; // [rsp+58h] [rbp-39h]
  char v31[16]; // [rsp+60h] [rbp-31h] BYREF
  int *v32; // [rsp+70h] [rbp-21h]
  __int64 v33; // [rsp+78h] [rbp-19h]
  unsigned int *v34; // [rsp+80h] [rbp-11h]
  __int64 v35; // [rsp+88h] [rbp-9h]

  v30 = -2;
  v9 = (char *)a4 + 24;
  v10 = strrchr((const char *)a4 + 24, 47);
  v11 = strrchr(v9, 92);
  if ( v10 > v11 )
    v11 = v10;
  v12 = v11 + 1;
  if ( !v11 )
    v12 = v9;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
    v13,
    (unsigned int)&v27,
    (_DWORD)a2,
    (_DWORD)v12,
    (__int64)a4);
  ATL::CSimpleStringT<unsigned short,0>::Append(&v27, L"\\");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(&v27, v12);
  v14 = v27;
  if ( !Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v15, v27) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v26,
      L"%wsngen.exe createpdb %ws %ws",
      *((_QWORD *)this + a5 + 5),
      a3,
      a2);
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(
        Microsoft_Windows_XPerfCore_ETWProvider_Context,
        TraceMerge_NGEN_CreatingPDB_Start,
        v26);
    v25 = 0;
    Buffer = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v26);
    v20 = Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(v19, Buffer, &v25);
    v22 = v20;
    if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    {
      v29 = v25;
      v28 = v20;
      v32 = &v28;
      v33 = 4;
      v34 = &v29;
      v35 = 4;
      McGenEventWrite_EventWriteTransfer(
        Microsoft_Windows_XPerfCore_ETWProvider_Context,
        TraceMerge_NGEN_CreatingPDB_Stop,
        v21,
        3,
        v31);
    }
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v26);
    if ( v22 < 0 )
    {
      v16 = v22;
      goto LABEL_11;
    }
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                         (char *)this + 56,
                         a2) )
    {
      if ( Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(v23, v14) )
      {
        v24 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4);
        if ( v24 < 0 )
        {
          v16 = v24;
          goto LABEL_11;
        }
      }
    }
    goto LABEL_10;
  }
  if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      Microsoft_Windows_XPerfCore_ETWProvider_Context,
      TraceMerge_NGEN_CandidateEncountered_ExistingPDB,
      v14);
  if ( !(unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
                        (char *)this + 56,
                        a2)
    || (v16 = Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(this, v14, v12, a4), v16 >= 0) )
  {
LABEL_10:
    v16 = 0;
  }
LABEL_11:
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v27);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18007acb0  push    rbp
0x18007acb2  push    rbx
0x18007acb3  push    rsi
0x18007acb4  push    rdi
0x18007acb5  push    r12
0x18007acb7  push    r13
0x18007acb9  push    r14
0x18007acbb  push    r15
0x18007acbd  lea     rbp, [rsp-17h]
0x18007acc2  sub     rsp, 0A8h
0x18007acc9  mov     [rbp+4Fh+var_88], 0FFFFFFFFFFFFFFFEh
0x18007acd1  mov     rax, cs:__security_cookie
0x18007acd8  xor     rax, rsp
0x18007acdb  mov     [rbp+4Fh+var_50], rax
0x18007acdf  mov     r13, r9
0x18007ace2  mov     r12, r8
0x18007ace5  mov     r14, rdx
0x18007ace8  mov     rsi, rcx
0x18007aceb  lea     rdi, [r9+18h]
0x18007acef  mov     edx, 2Fh ; '/'; Ch
0x18007acf4  mov     rcx, rdi; Str
0x18007acf7  call    cs:__imp_strrchr
0x18007acfd  mov     rbx, rax
0x18007ad00  mov     edx, 5Ch ; '\'; Ch
0x18007ad05  mov     rcx, rdi; Str
0x18007ad08  call    cs:__imp_strrchr
0x18007ad0e  cmp     rbx, rax
0x18007ad11  cmova   rax, rbx
0x18007ad15  lea     r15, [rax+1]
0x18007ad19  test    rax, rax
0x18007ad1c  cmovz   r15, rdi
0x18007ad20  lea     rcx, [rbp+4Fh+var_A0]; void *
0x18007ad24  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18007ad29  nop
0x18007ad2a  mov     [rsp+0E0h+var_C0], r13
0x18007ad2f  mov     r9, r15
0x18007ad32  mov     r8, r14
0x18007ad35  lea     rdx, [rbp+4Fh+var_A0]
0x18007ad39  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x18007ad3e  lea     rdx, SubBlock; "\\"
0x18007ad45  lea     rcx, [rbp+4Fh+var_A0]
0x18007ad49  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18007ad4e  mov     rdx, r15
0x18007ad51  lea     rcx, [rbp+4Fh+var_A0]
0x18007ad55  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x18007ad5a  mov     rbx, [rbp+4Fh+var_A0]
0x18007ad5e  mov     rdx, rbx; unsigned __int16 *
0x18007ad61  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18007ad66  test    al, al
0x18007ad68  jz      short loc_18007ADDD
0x18007ad6a  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18007ad71  jz      short loc_18007AD89
0x18007ad73  mov     r8, rbx
0x18007ad76  lea     rdx, TraceMerge_NGEN_CandidateEncountered_ExistingPDB
0x18007ad7d  lea     rcx, Microsoft_Windows_XPerfCore_ETWProvider_Context
0x18007ad84  call    McTemplateU0z_EventWriteTransfer
0x18007ad89  lea     rcx, [rsi+38h]
0x18007ad8d  mov     rdx, r14
0x18007ad90  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18007ad95  test    eax, eax
0x18007ad97  jz      short loc_18007ADB0
0x18007ad99  mov     r9, r13; struct _RSDS *
0x18007ad9c  mov     r8, r15; char *
0x18007ad9f  mov     rdx, rbx; unsigned __int16 *
0x18007ada2  mov     rcx, rsi; this
0x18007ada5  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x18007adaa  mov     ebx, eax
0x18007adac  test    eax, eax
0x18007adae  js      short loc_18007ADB2
0x18007adb0  xor     ebx, ebx
0x18007adb2  lea     rcx, [rbp+4Fh+var_A0]; this
0x18007adb6  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007adbb  mov     eax, ebx
0x18007adbd  mov     rcx, [rbp+4Fh+var_50]
0x18007adc1  xor     rcx, rsp; StackCookie
0x18007adc4  call    __security_check_cookie
0x18007adc9  add     rsp, 0A8h
0x18007add0  pop     r15
0x18007add2  pop     r14
0x18007add4  pop     r13
0x18007add6  pop     r12
0x18007add8  pop     rdi
0x18007add9  pop     rsi
0x18007adda  pop     rbx
0x18007addb  pop     rbp
0x18007addc  retn
0x18007addd  lea     rcx, [rbp+4Fh+var_A8]; void *
0x18007ade1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18007ade6  nop
0x18007ade7  movzx   r8d, [rbp+4Fh+arg_20]
0x18007adec  mov     [rsp+0E0h+var_C0], r14
0x18007adf1  mov     r9, r12
0x18007adf4  mov     r8, [rsi+r8*8+28h]
0x18007adf9  lea     rdx, aWsngenExeCreat; "%wsngen.exe createpdb %ws %ws"
0x18007ae00  lea     rcx, [rbp+4Fh+var_A8]
0x18007ae04  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18007ae09  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18007ae10  jz      short loc_18007AE29
0x18007ae12  mov     r8, [rbp+4Fh+var_A8]
0x18007ae16  lea     rdx, TraceMerge_NGEN_CreatingPDB_Start
0x18007ae1d  lea     rcx, Microsoft_Windows_XPerfCore_ETWProvider_Context
0x18007ae24  call    McTemplateU0z_EventWriteTransfer
0x18007ae29  mov     [rbp+4Fh+var_B0], 0
0x18007ae30  lea     rcx, [rbp+4Fh+var_A8]
0x18007ae34  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18007ae39  mov     rdx, rax; unsigned __int16 *
0x18007ae3c  lea     r8, [rbp+4Fh+var_B0]; unsigned int *
0x18007ae40  call    ?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)
0x18007ae45  mov     edi, eax
0x18007ae47  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x18007ae4e  jz      short loc_18007AE9C
0x18007ae50  mov     ecx, [rbp+4Fh+var_B0]
0x18007ae53  mov     [rbp+4Fh+var_90], ecx
0x18007ae56  mov     [rbp+4Fh+var_98], eax
0x18007ae59  lea     rax, [rbp+4Fh+var_98]
0x18007ae5d  mov     [rbp+4Fh+var_70], rax
0x18007ae61  mov     [rbp+4Fh+var_68], 4
0x18007ae69  lea     rax, [rbp+4Fh+var_90]
0x18007ae6d  mov     [rbp+4Fh+var_60], rax
0x18007ae71  mov     [rbp+4Fh+var_58], 4
0x18007ae79  lea     rax, [rbp+4Fh+var_80]
0x18007ae7d  mov     [rsp+0E0h+var_C0], rax
0x18007ae82  mov     r9d, 3
0x18007ae88  lea     rdx, TraceMerge_NGEN_CreatingPDB_Stop
0x18007ae8f  lea     rcx, Microsoft_Windows_XPerfCore_ETWProvider_Context
0x18007ae96  call    McGenEventWrite_EventWriteTransfer
0x18007ae9b  nop
0x18007ae9c  lea     rcx, [rbp+4Fh+var_A8]; this
0x18007aea0  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18007aea5  test    edi, edi
0x18007aea7  jns     short loc_18007AEB0
0x18007aea9  mov     ebx, edi
0x18007aeab  jmp     loc_18007ADB2
0x18007aeb0  lea     rcx, [rsi+38h]
0x18007aeb4  mov     rdx, r14
0x18007aeb7  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18007aebc  test    eax, eax
0x18007aebe  jz      loc_18007ADB0
0x18007aec4  mov     rdx, rbx; unsigned __int16 *
0x18007aec7  call    ?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)
0x18007aecc  test    al, al
0x18007aece  jz      loc_18007ADB0
0x18007aed4  mov     r9, r13; struct _RSDS *
0x18007aed7  mov     r8, r15; char *
0x18007aeda  mov     rdx, rbx; unsigned __int16 *
0x18007aedd  mov     rcx, rsi; this
0x18007aee0  call    ?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)
0x18007aee5  test    eax, eax
0x18007aee7  jns     loc_18007ADB0
0x18007aeed  mov     ebx, eax
0x18007aeef  jmp     loc_18007ADB2
```
