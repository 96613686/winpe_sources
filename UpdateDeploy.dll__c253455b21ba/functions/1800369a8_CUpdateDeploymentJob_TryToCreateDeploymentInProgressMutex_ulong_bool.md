# CUpdateDeploymentJob::TryToCreateDeploymentInProgressMutex(ulong,bool *)

- ea: `0x1800369a8`
- end: `0x180036dc2`
- name: `?TryToCreateDeploymentInProgressMutex@CUpdateDeploymentJob@@AEAAJKPEA_N@Z`
- size: `1050`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002d3d0`
- `0x18002fcbc`

## callees

- `0x180003180`
- `0x18000865c`
- `0x18000c0ac`
- `0x18000c640`
- `0x1800110fc`
- `0x180011b44`
- `0x18001c3cc`
- `0x1800369a8`
- `0x180038d40`
- `0x180061960`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180036afc`
- `RPCRT4!UuidToStringW` at `0x180036afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036d93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036d42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036d93`

## string_xrefs

- `0x1800369ed`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180036b5d`: `Deployment job Id %ws : Mutex with name = %ws, already created in this job. Skip creating another one`
- `0x180036cb7`: `Deployment job Id %ws : Other HANDLE with the same name (%ws) already exist. Allowing deployment to start.`
- `0x180036c8b`: `CUpdateDeploymentJob::TryToCreateDeploymentInProgressMutex`
- `0x180036d62`: `Deployment job Id %ws : Mutex for Deployment job is created.  Mutex = %ws`
- `0x180036b1d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180036c0a`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUpdateDeploymentJob::TryToCreateDeploymentInProgressMutex(
        CUpdateDeploymentJob *this,
        unsigned int a2,
        bool *a3)
{
  const WCHAR *v7; // r14
  __int64 v8; // rax
  unsigned int v9; // ebx
  const WCHAR *v10; // rdx
  int v11; // r15d
  bool v12; // di
  bool v13; // cl
  HANDLE v14; // rbx
  const struct _GUID *v15; // r15
  RPC_STATUS v16; // eax
  signed int v17; // edi
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r8
  int v21; // eax
  const wchar_t *v22; // rax
  __int64 v23; // r9
  HANDLE v24; // r12
  __int64 v25; // rdi
  __int64 v26; // rsi
  void *v27; // rcx
  __int64 v28; // [rsp+20h] [rbp-B9h]
  __int64 v29; // [rsp+30h] [rbp-A9h]
  __int64 v30; // [rsp+30h] [rbp-A9h]
  const WCHAR *v31; // [rsp+38h] [rbp-A1h]
  HANDLE v32; // [rsp+40h] [rbp-99h] BYREF
  __int64 v33; // [rsp+48h] [rbp-91h]
  __int128 v34; // [rsp+50h] [rbp-89h] BYREF
  __int64 v35; // [rsp+60h] [rbp-79h]
  __int64 v36; // [rsp+68h] [rbp-71h]
  __int128 Src; // [rsp+70h] [rbp-69h] BYREF
  __int64 v38; // [rsp+80h] [rbp-59h]
  __int64 v39; // [rsp+88h] [rbp-51h]
  __int128 *v40; // [rsp+90h] [rbp-49h]
  _BYTE v41[80]; // [rsp+A0h] [rbp-39h] BYREF
  RPC_WSTR StringUuid; // [rsp+F0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1874,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80004003LL,
      v28);
    return 2147500035LL;
  }
  *a3 = 0;
  v33 = a2;
  v7 = *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 87) + 8LL * a2) + 568LL);
  if ( v7 )
  {
    v9 = 0;
    if ( *((_DWORD *)this + 172) )
    {
      while ( 1 )
      {
        if ( v9 != a2 && *(_QWORD *)(*((_QWORD *)this + 122) + 8LL * v9) )
        {
          v10 = *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 87) + 8LL * v9) + 568LL);
          v11 = 0;
          v12 = 0;
          if ( v10 )
            v12 = (unsigned int)AsciiStringCompareI(v7, v10) == 0;
          else
            v11 = -2147467261;
          v13 = 0;
          if ( v11 >= 0 )
            v13 = v12;
          if ( v13 )
            break;
        }
        if ( ++v9 >= *((_DWORD *)this + 172) )
          goto LABEL_15;
      }
      v18 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v41, (const struct _GUID *)this + 1);
      WUTrace(
        0,
        0,
        0x1000000,
        4,
        0,
        L"Deployment job Id %ws : Mutex with name = %ws, already created in this job. Skip creating another one",
        v18,
        v7);
      return 0;
    }
LABEL_15:
    v14 = 0;
    v32 = 0;
    StringUuid = 0;
    v15 = (const struct _GUID *)((char *)this + 16);
    v16 = UuidToStringW((const UUID *)this + 1, &StringUuid);
    v17 = v16;
    if ( v16 >= 1 )
      v17 = (unsigned __int16)v16 | 0x80010000;
    if ( v17 >= 0 )
    {
      v40 = &v34;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v19 = -1;
      v20 = -1;
      do
        ++v20;
      while ( v7[v20] );
      std::wstring::_Construct<1,wchar_t const *>(&v34, v7);
      Src = 0;
      v38 = 0;
      v39 = 0;
      do
        ++v19;
      while ( StringUuid[v19] );
      std::wstring::_Construct<1,wchar_t const *>(&Src, StringUuid);
      v21 = mutex::CreatePrivateMutex(&Src, &v34, &v32);
      v17 = v21;
      if ( v21 >= 0 )
      {
        if ( StringUuid )
          XPtrRpcStringFree(StringUuid);
        v17 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
          (const char *)(unsigned int)v21,
          v28);
        if ( StringUuid )
          XPtrRpcStringFree(StringUuid);
      }
      v14 = v32;
      if ( v32 )
      {
        if ( v17 != -2147024713 )
        {
          v24 = v32;
          v14 = 0;
          v25 = *((_QWORD *)this + 122);
          v26 = v33;
          v27 = *(void **)(v25 + 8 * v33);
          if ( v27 )
            CloseHandle(v27);
          *(_QWORD *)(v25 + 8 * v26) = v24;
          v31 = v7;
          v29 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v41, v15);
          v22 = L"Deployment job Id %ws : Mutex for Deployment job is created.  Mutex = %ws";
          v23 = 4;
          goto LABEL_41;
        }
        *a3 = 1;
        v31 = v7;
        v29 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v41, (const struct _GUID *)this + 1);
        v22 = L"Deployment job Id %ws : Another Deployment job is in progress using Mutex = %ws";
LABEL_34:
        v23 = 3;
LABEL_41:
        WUTrace(0, 0, 0x1000000, v23, 0, v22, v29, v31);
LABEL_42:
        if ( v14 )
          CloseHandle(v14);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x123,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
        (const char *)(unsigned int)v17,
        v28);
      if ( StringUuid )
        XPtrRpcStringFree(StringUuid);
    }
    if ( v17 != -2147024890 )
    {
      v30 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v41, (const struct _GUID *)this + 1);
      LODWORD(v28) = v17;
      WUTrace(
        0,
        0,
        0x1000000,
        3,
        v28,
        L"Deployment job Id %ws : Error creating Mutex = %ws with unexpected reason. Allowing deployment to start.",
        v30,
        v7);
      goto LABEL_42;
    }
    WUTrace(
      "CUpdateDeploymentJob::TryToCreateDeploymentInProgressMutex",
      6310,
      32,
      3,
      0,
      L"TelemetryAssert (%ws): %ws",
      L"hr != HRESULT_FROM_WIN32(6L)",
      L"Failed");
    WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
    v31 = v7;
    v29 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v41, (const struct _GUID *)this + 1);
    v22 = L"Deployment job Id %ws : Other HANDLE with the same name (%ws) already exist. Allowing deployment to start.";
    goto LABEL_34;
  }
  v8 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v41, (const struct _GUID *)this + 1);
  WUTrace(0, 0, 0x1000000, 3, 0, L"Deployment job Id %ws : Name of mutex is not set. Skipping Mutex creation", v8);
  return 0;
}

```

## disassembly

```asm
0x1800369a8  mov     [rsp-8+arg_18], rbx
0x1800369ad  push    rbp
0x1800369ae  push    rsi
0x1800369af  push    rdi
0x1800369b0  push    r12
0x1800369b2  push    r13
0x1800369b4  push    r14
0x1800369b6  push    r15
0x1800369b8  lea     rbp, [rsp-27h]
0x1800369bd  sub     rsp, 100h
0x1800369c4  mov     rax, cs:__security_cookie
0x1800369cb  xor     rax, rsp
0x1800369ce  mov     [rbp+57h+var_38], rax
0x1800369d2  mov     r13, r8
0x1800369d5  mov     r12d, edx
0x1800369d8  mov     rsi, rcx
0x1800369db  xor     r8d, r8d
0x1800369de  test    r13, r13
0x1800369e1  jnz     short loc_180036A08
0x1800369e3  mov     rcx, [rbp+5Fh]; this
0x1800369e7  mov     r9d, 80004003h; char *
0x1800369ed  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800369f4  mov     edx, 1874h; void *
0x1800369f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800369fe  mov     eax, 80004003h
0x180036a03  jmp     loc_180036D9B
0x180036a08  mov     [r13+0], r8b
0x180036a0c  mov     [rsp+130h+var_E8], r12
0x180036a11  mov     rax, [rcx+2B8h]
0x180036a18  mov     rcx, [rax+r12*8]
0x180036a1c  mov     r14, [rcx+238h]
0x180036a23  test    r14, r14
0x180036a26  jnz     short loc_180036A65
0x180036a28  lea     rdx, [rsi+10h]; struct _GUID *
0x180036a2c  lea     rcx, [rbp+57h+var_90]; this
0x180036a30  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036a35  mov     [rsp+130h+var_100], rax
0x180036a3a  lea     rax, aDeploymentJobI_14; "Deployment job Id %ws : Name of mutex i"...
0x180036a41  mov     [rsp+130h+var_108], rax
0x180036a46  xor     eax, eax
0x180036a48  mov     [rsp+130h+var_110], rax
0x180036a4d  xor     edx, edx
0x180036a4f  xor     ecx, ecx
0x180036a51  lea     r9d, [r14+3]
0x180036a55  mov     r8d, 1000000h
0x180036a5b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180036a60  jmp     loc_180036D99
0x180036a65  mov     ebx, r8d
0x180036a68  mov     r9d, 1
0x180036a6e  cmp     [rsi+2B0h], r8d
0x180036a75  jbe     short loc_180036AE2
0x180036a77  cmp     ebx, r12d
0x180036a7a  jz      short loc_180036AD7
0x180036a7c  mov     ecx, ebx
0x180036a7e  mov     rax, [rsi+3D0h]
0x180036a85  cmp     [rax+rcx*8], r8
0x180036a89  jz      short loc_180036AD7
0x180036a8b  mov     rax, [rsi+2B8h]
0x180036a92  mov     rcx, [rax+rcx*8]
0x180036a96  mov     rdx, [rcx+238h]; lpString2
0x180036a9d  mov     r15d, r8d
0x180036aa0  movzx   edi, r8b
0x180036aa4  test    rdx, rdx
0x180036aa7  jnz     short loc_180036AB1
0x180036aa9  mov     r15d, 80004003h
0x180036aaf  jmp     short loc_180036AC6
0x180036ab1  mov     rcx, r14; lpString1
0x180036ab4  call    ?AsciiStringCompareI@@YAJPEB_W0@Z; AsciiStringCompareI(wchar_t const *,wchar_t const *)
0x180036ab9  xor     r8d, r8d
0x180036abc  test    eax, eax
0x180036abe  lea     r9d, [r8+1]
0x180036ac2  cmovz   edi, r9d
0x180036ac6  mov     ecx, r8d
0x180036ac9  movzx   eax, dil
0x180036acd  test    r15d, r15d
0x180036ad0  cmovns  ecx, eax
0x180036ad3  test    cl, cl
0x180036ad5  jnz     short loc_180036B46
0x180036ad7  add     ebx, r9d
0x180036ada  cmp     ebx, [rsi+2B0h]
0x180036ae0  jb      short loc_180036A77
0x180036ae2  xor     r12d, r12d
0x180036ae5  mov     ebx, r12d
0x180036ae8  mov     [rsp+130h+var_F0], rbx
0x180036aed  mov     [rbp+57h+StringUuid], r12
0x180036af1  lea     r15, [rsi+10h]
0x180036af5  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x180036af9  mov     rcx, r15; Uuid
0x180036afc  call    cs:__imp_UuidToStringW
0x180036b02  mov     edi, eax
0x180036b04  cmp     eax, 1
0x180036b07  jl      short loc_180036B12
0x180036b09  movzx   edi, ax
0x180036b0c  or      edi, 80010000h
0x180036b12  test    edi, edi
0x180036b14  jns     short loc_180036B88
0x180036b16  mov     rcx, [rbp+5Fh]; this
0x180036b1a  mov     r9d, edi; char *
0x180036b1d  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180036b24  mov     edx, 123h; void *
0x180036b29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036b2e  nop
0x180036b2f  mov     rcx, [rbp+57h+StringUuid]; void *
0x180036b33  test    rcx, rcx
0x180036b36  jz      loc_180036C4B
0x180036b3c  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180036b41  jmp     loc_180036C4B
0x180036b46  lea     rdx, [rsi+10h]; struct _GUID *
0x180036b4a  lea     rcx, [rbp+57h+var_90]; this
0x180036b4e  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036b53  mov     [rsp+130h+var_F8], r14
0x180036b58  mov     [rsp+130h+var_100], rax
0x180036b5d  lea     rax, aDeploymentJobI_67; "Deployment job Id %ws : Mutex with name"...
0x180036b64  mov     [rsp+130h+var_108], rax
0x180036b69  xor     eax, eax
0x180036b6b  mov     [rsp+130h+var_110], rax
0x180036b70  xor     edx, edx
0x180036b72  xor     ecx, ecx
0x180036b74  lea     r9d, [rax+4]
0x180036b78  mov     r8d, 1000000h
0x180036b7e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180036b83  jmp     loc_180036D99
0x180036b88  lea     rax, [rsp+130h+var_E0]
0x180036b8d  mov     [rbp+57h+var_A0], rax
0x180036b91  xorps   xmm0, xmm0
0x180036b94  movups  [rsp+130h+var_E0], xmm0
0x180036b99  mov     [rbp+57h+var_D0], r12
0x180036b9d  mov     [rbp+57h+var_C8], r12
0x180036ba1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036ba5  mov     r8, rbx
0x180036ba8  inc     r8
0x180036bab  cmp     [r14+r8*2], r12w
0x180036bb0  jnz     short loc_180036BA8
0x180036bb2  mov     rdx, r14
0x180036bb5  lea     rcx, [rsp+130h+var_E0]
0x180036bba  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180036bbf  nop
0x180036bc0  xorps   xmm0, xmm0
0x180036bc3  movups  [rbp+57h+Src], xmm0
0x180036bc7  mov     [rbp+57h+var_B0], r12
0x180036bcb  mov     [rbp+57h+var_A8], r12
0x180036bcf  mov     rdx, [rbp+57h+StringUuid]
0x180036bd3  inc     rbx
0x180036bd6  cmp     [rdx+rbx*2], r12w
0x180036bdb  jnz     short loc_180036BD3
0x180036bdd  mov     r8, rbx
0x180036be0  lea     rcx, [rbp+57h+Src]
0x180036be4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180036be9  nop
0x180036bea  lea     r8, [rsp+130h+var_F0]
0x180036bef  lea     rdx, [rsp+130h+var_E0]; void *
0x180036bf4  lea     rcx, [rbp+57h+Src]; Src
0x180036bf8  call    ?CreatePrivateMutex@mutex@@YAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV?$XHandleBase@PEAXUNullHandlePolicy@Policies@WuSmartPtr@@@WuSmartPtr@@@Z; mutex::CreatePrivateMutex(std::wstring,std::wstring,WuSmartPtr::XHandleBase<void *,WuSmartPtr::Policies::NullHandlePolicy> &)
0x180036bfd  mov     edi, eax
0x180036bff  test    eax, eax
0x180036c01  jns     short loc_180036C2C
0x180036c03  mov     rcx, [rbp+5Fh]; this
0x180036c07  mov     r9d, eax; char *
0x180036c0a  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180036c11  mov     edx, 124h; void *
0x180036c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c1b  nop
0x180036c1c  mov     rcx, [rbp+57h+StringUuid]; void *
0x180036c20  test    rcx, rcx
0x180036c23  jz      short loc_180036C3D
0x180036c25  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180036c2a  jmp     short loc_180036C3D
0x180036c2c  mov     rcx, [rbp+57h+StringUuid]; void *
0x180036c30  test    rcx, rcx
0x180036c33  jz      short loc_180036C3A
0x180036c35  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180036c3a  mov     edi, r12d
0x180036c3d  mov     rbx, [rsp+130h+var_F0]
0x180036c42  test    rbx, rbx
0x180036c45  jnz     loc_180036CFA
0x180036c4b  cmp     edi, 80070006h
0x180036c51  jnz     short loc_180036CC9
0x180036c53  lea     rax, aFailed; "Failed"
0x180036c5a  mov     [rsp+130h+var_F8], rax
0x180036c5f  lea     rax, aHrHresultFromW; "hr != HRESULT_FROM_WIN32(6L)"
0x180036c66  mov     [rsp+130h+var_100], rax
0x180036c6b  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x180036c72  mov     [rsp+130h+var_108], rax
0x180036c77  mov     [rsp+130h+var_110], r12
0x180036c7c  mov     edx, 18A6h
0x180036c81  mov     r9d, 3
0x180036c87  lea     r8d, [r9+1Dh]
0x180036c8b  lea     rcx, aCupdatedeploym_4; "CUpdateDeploymentJob::TryToCreateDeploy"...
0x180036c92  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180036c97  or      ecx, 0FFFFFFFFh; unsigned int
0x180036c9a  mov     edx, ecx; unsigned int
0x180036c9c  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x180036ca1  mov     rdx, r15; struct _GUID *
0x180036ca4  lea     rcx, [rbp+57h+var_90]; this
0x180036ca8  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036cad  mov     [rsp+130h+var_F8], r14
0x180036cb2  mov     [rsp+130h+var_100], rax
0x180036cb7  lea     rax, aDeploymentJobI_28; "Deployment job Id %ws : Other HANDLE wi"...
0x180036cbe  mov     r9d, 3
0x180036cc4  jmp     loc_180036D71
0x180036cc9  mov     rdx, r15; struct _GUID *
0x180036ccc  lea     rcx, [rbp+57h+var_90]; this
0x180036cd0  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036cd5  mov     [rsp+130h+var_F8], r14
0x180036cda  mov     [rsp+130h+var_100], rax
0x180036cdf  lea     rax, aDeploymentJobI_21; "Deployment job Id %ws : Error creating "...
0x180036ce6  mov     [rsp+130h+var_108], rax
0x180036ceb  mov     dword ptr [rsp+130h+var_110], edi
0x180036cef  mov     r9d, 3
0x180036cf5  jmp     loc_180036D7B
0x180036cfa  cmp     edi, 800700B7h
0x180036d00  jnz     short loc_180036D26
0x180036d02  mov     byte ptr [r13+0], 1
0x180036d07  mov     rdx, r15; struct _GUID *
0x180036d0a  lea     rcx, [rbp+57h+var_90]; this
0x180036d0e  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036d13  mov     [rsp+130h+var_F8], r14
0x180036d18  mov     [rsp+130h+var_100], rax
0x180036d1d  lea     rax, aDeploymentJobI_65; "Deployment job Id %ws : Another Deploym"...
0x180036d24  jmp     short loc_180036CBE
0x180036d26  mov     r12, rbx
0x180036d29  xor     eax, eax
0x180036d2b  mov     ebx, eax
0x180036d2d  mov     rdi, [rsi+3D0h]
0x180036d34  mov     rsi, [rsp+130h+var_E8]
0x180036d39  mov     rcx, [rdi+rsi*8]; hObject
0x180036d3d  test    rcx, rcx
0x180036d40  jz      short loc_180036D48
0x180036d42  call    cs:__imp_CloseHandle
0x180036d48  mov     [rdi+rsi*8], r12
0x180036d4c  mov     rdx, r15; struct _GUID *
0x180036d4f  lea     rcx, [rbp+57h+var_90]; this
0x180036d53  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180036d58  mov     [rsp+130h+var_F8], r14
0x180036d5d  mov     [rsp+130h+var_100], rax
0x180036d62  lea     rax, aDeploymentJobI_69; "Deployment job Id %ws : Mutex for Deplo"...
0x180036d69  xor     r12d, r12d
0x180036d6c  lea     r9d, [r12+4]
0x180036d71  mov     [rsp+130h+var_108], rax
0x180036d76  mov     [rsp+130h+var_110], r12
0x180036d7b  mov     r8d, 1000000h
0x180036d81  xor     edx, edx
0x180036d83  xor     ecx, ecx
0x180036d85  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180036d8a  nop
0x180036d8b  test    rbx, rbx
0x180036d8e  jz      short loc_180036D99
0x180036d90  mov     rcx, rbx; hObject
0x180036d93  call    cs:__imp_CloseHandle
0x180036d99  xor     eax, eax
0x180036d9b  mov     rcx, [rbp+57h+var_38]
0x180036d9f  xor     rcx, rsp; StackCookie
0x180036da2  call    __security_check_cookie
0x180036da7  mov     rbx, [rsp+130h+arg_18]
0x180036daf  add     rsp, 100h
0x180036db6  pop     r15
0x180036db8  pop     r14
0x180036dba  pop     r13
0x180036dbc  pop     r12
0x180036dbe  pop     rdi
0x180036dbf  pop     rsi
0x180036dc0  pop     rbp
0x180036dc1  retn
```
