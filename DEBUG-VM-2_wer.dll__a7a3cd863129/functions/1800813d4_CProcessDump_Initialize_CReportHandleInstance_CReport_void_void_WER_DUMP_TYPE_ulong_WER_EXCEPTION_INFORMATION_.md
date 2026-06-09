# CProcessDump::Initialize(CReportHandleInstance *,CReport *,void *,void *,_WER_DUMP_TYPE,ulong,_WER_EXCEPTION_INFORMATION * const,void * const,ulong)

- ea: `0x1800813d4`
- end: `0x180081a81`
- name: `?Initialize@CProcessDump@@QEAAJPEAVCReportHandleInstance@@PEAVCReport@@PEAX2W4_WER_DUMP_TYPE@@KQEAU_WER_EXCEPTION_INFORMATION@@QEAXK@Z`
- size: `1709`
- prototype: `__int64 __usercall@<rax>(CProcessDump *__hidden this@<rcx>, struct CReportHandleInstance *@<rdx>, struct CReport *@<r8>, void *@<r9>, void *, enum _WER_DUMP_TYPE, unsigned int, struct _WER_EXCEPTION_INFORMATION *const, void *const, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800705a0`
- `0x180081a88`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18000c390`
- `0x1800293ac`
- `0x18002ac84`
- `0x18002bed4`
- `0x18002eb5c`
- `0x1800421c4`
- `0x180049458`
- `0x180050db0`
- `0x1800517cc`
- `0x180051fa4`
- `0x1800813d4`
- `0x180081b60`
- `0x180081cf8`
- `0x180098c88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008171c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180081725`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180081781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008178a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008171c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180081725`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180081781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008178a`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800817d5`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x1800817d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008175d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008175d`
- `ntdll!NtQueryInformationProcess` at `0x1800818cf`
- `ntdll!NtQueryInformationProcess` at `0x1800818cf`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x1800819b5`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerGetFlags` at `0x1800819b5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180081751`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800817b6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180081751`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800817b6`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18008182b`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180081869`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x18008182b`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180081869`
- `ext-ms-win-wer-xbox-l1-1-3!XerEncryptDump` at `0x180081947`
- `ext-ms-win-wer-xbox-l1-1-3!XerEncryptDump` at `0x180081947`

## string_xrefs

- `0x180081619`: `DumpThreadPriority`
- `0x1800816e4`: `DumpWriteBufferSize`
- `0x180081a12`: `Dump file could not be created: UtilGetProtectedProcessInfo failed %08X.`

## pseudocode

```c
signed int __fastcall CProcessDump::Initialize(
        DWORD *this,
        struct CReportHandleInstance *a2,
        struct CReport *a3,
        void *a4,
        void *a5,
        enum _WER_DUMP_TYPE a6,
        unsigned int a7,
        struct _WER_EXCEPTION_INFORMATION *const a8,
        _DWORD *a9,
        unsigned int a10)
{
  _WORD *v11; // rcx
  HANDLE *v12; // r15
  __int64 v13; // rdx
  _OWORD *v14; // rcx
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int64 v26; // rax
  HANDLE *v27; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v29; // rax
  DWORD LastError; // eax
  signed int result; // eax
  HANDLE *v32; // rdi
  HANDLE v33; // rbx
  HANDLE v34; // rax
  char *v35; // rcx
  __int64 v36; // rcx
  bool v37; // cc
  HANDLE v38; // rbx
  NTSTATUS InformationProcess; // eax
  HANDLE v40; // rcx
  HANDLE v41; // rcx
  bool v42; // zf
  int v43; // eax
  int ProtectedProcessInfo; // eax
  BOOL v45; // eax
  struct _CONTEXT *v46; // r9
  DWORD ExceptionCode; // eax
  PEXCEPTION_RECORD ExceptionRecord; // rax
  bool bInheritHandle; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlea; // [rsp+28h] [rbp-D8h]
  bool bInheritHandleb; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlec; // [rsp+28h] [rbp-D8h]
  bool bInheritHandled; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlee; // [rsp+28h] [rbp-D8h]
  bool bInheritHandlef; // [rsp+28h] [rbp-D8h]
  HANDLE hSourceHandle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v57; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hProcess; // [rsp+50h] [rbp-B0h] BYREF
  struct CReportHandleInstance *v59; // [rsp+58h] [rbp-A8h]
  struct CReport *v60; // [rsp+60h] [rbp-A0h]
  _QWORD ProcessInformation[5]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v62; // [rsp+98h] [rbp-68h]
  _BYTE v63[592]; // [rsp+B0h] [rbp-50h] BYREF
  struct _EXCEPTION_RECORD v64; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v65[28]; // [rsp+3A0h] [rbp+2A0h] BYREF
  DWORD v66; // [rsp+3BCh] [rbp+2BCh]
  int v67; // [rsp+3C4h] [rbp+2C4h]
  char v68[524]; // [rsp+454h] [rbp+354h] BYREF

  v60 = a3;
  v59 = a2;
  v57 = a5;
  hProcess = 0;
  hSourceHandle = a4;
  memset_0(v65, 0, 0x2C0u);
  memset_0(ProcessInformation, 0, 0x40u);
  memset_0(&v64, 0, sizeof(v64));
  if ( (unsigned int)(a6 - 1) > 3 || a9 && (((*a9 - 552) & 0xFFFFFFD7) != 0 || *a9 == 592) )
    return -2147024809;
  CProcessDump::Uninitialize((CProcessDump *)this);
  v11 = (_WORD *)*((_QWORD *)this + 3);
  v12 = (HANDLE *)(this + 28);
  *((_QWORD *)this + 4) = v11;
  *v11 = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(this + 28, 0);
  *((_QWORD *)this + 15) = 0;
  this[32] = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(this + 46, 0);
  this[48] = 0;
  memset_0(v63, 0, 0x248u);
  v13 = 4;
  v14 = this + 50;
  v15 = v63;
  do
  {
    v16 = v15[1];
    *v14 = *v15;
    v17 = v15[2];
    v14[1] = v16;
    v18 = v15[3];
    v14[2] = v17;
    v19 = v15[4];
    v14[3] = v18;
    v20 = v15[5];
    v14[4] = v19;
    v21 = v15[6];
    v14[5] = v20;
    v22 = v15[7];
    v15 += 8;
    v14[6] = v21;
    v14[7] = v22;
    v14 += 8;
    --v13;
  }
  while ( v13 );
  v23 = v15[1];
  *v14 = *v15;
  v24 = v15[2];
  v14[1] = v23;
  v25 = v15[3];
  v26 = *((_QWORD *)v15 + 8);
  v14[2] = v24;
  v14[3] = v25;
  *((_QWORD *)v14 + 8) = v26;
  memset_0(this + 196, 0, 0x400u);
  *((_QWORD *)this + 1) = v59;
  *((_QWORD *)this + 2) = v60;
  this[50] = 584;
  this[42] = a6;
  this[43] = a7 & 0x5FFFFFF;
  *((_QWORD *)this + 226) = 0;
  this[454] = 0;
  this[44] = a10;
  *((_OWORD *)this + 114) = 0;
  this[14] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpWait",
               0,
               0,
               bInheritHandle);
  this[15] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpThreadPriority",
               0x80000000,
               0,
               bInheritHandlea);
  this[16] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpProfilingEnabled",
               0,
               0,
               bInheritHandleb) != 0;
  this[17] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpBgPriorityDisabled",
               0,
               0,
               bInheritHandlec) != 0;
  this[18] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpUseTransientFile",
               0xFFFFFFFF,
               0,
               bInheritHandled);
  this[19] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpFailGeneration",
               0,
               0,
               bInheritHandlee) != 0;
  this[20] = UtilRegGetDWORD(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug",
               L"DumpWriteBufferSize",
               0xFFFFFFFF,
               0,
               bInheritHandlef);
  CProcessDump::SetDefaultDumpOptions((CProcessDump *)this);
  if ( hSourceHandle
    && (v27 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(this + 28),
        CurrentProcess = GetCurrentProcess(),
        v29 = GetCurrentProcess(),
        !DuplicateHandle(v29, hSourceHandle, CurrentProcess, v27, 0, 0, 2u))
    || v57
    && (v32 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(this + 46),
        v33 = GetCurrentProcess(),
        v34 = GetCurrentProcess(),
        !DuplicateHandle(v34, v57, v33, v32, 0, 0, 2u)) )
  {
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  v35 = (char *)*((_QWORD *)this + 23);
  if ( v35 != (char *)-1LL && v35 + 1 != (char *)1 )
    this[48] = GetThreadId(v35);
  if ( a9 )
  {
    result = CProcessDump::SetDumpOptions((CProcessDump *)this, a9);
    if ( result < 0 )
      return result;
    if ( !this[48] )
      this[48] = this[194];
  }
  v36 = *((_QWORD *)this + 96);
  if ( !v36 )
  {
    v38 = *v12;
    if ( (unsigned __int64)*v12 + 1 > 1 )
    {
      ProcessInformation[0] = 64;
      InformationProcess = NtQueryInformationProcess(v38, ProcessBasicInformation, ProcessInformation, 0x40u, 0);
      if ( InformationProcess < 0 )
        return InformationProcess | 0x10000000;
      v40 = *v12;
      this[30] = v62;
      LODWORD(hSourceHandle) = 0;
      UtilGetProtectedProcessInfo(v40, (enum _PS_PROTECTED_TYPE *)&hSourceHandle, 0);
      v41 = *v12;
      this[32] = (int)hSourceHandle > 0;
      UtilGetProcessPathFromHandle(v41);
LABEL_29:
      this[21] = this[44] & 0x10000000;
      if ( (unsigned __int8)IsXerTransportEventUploadCompletePresent() )
      {
        if ( this[21]
          || (v42 = (unsigned int)XerEncryptDump(*(_QWORD *)(*((_QWORD *)this + 2) + 560LL), (unsigned int)a6) == 0,
              v43 = 0,
              !v42) )
        {
          v43 = 1;
        }
        this[21] = v43;
      }
      if ( this[32] )
      {
        LODWORD(v57) = 0;
        LODWORD(hSourceHandle) = 0;
        ProtectedProcessInfo = UtilGetProtectedProcessInfo(
                                 v38,
                                 (enum _PS_PROTECTED_TYPE *)&v57,
                                 (enum _PS_PROTECTED_SIGNER *)&hSourceHandle);
        if ( ProtectedProcessInfo < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: UtilGetProtectedProcessInfo failed %08X.",
            (unsigned int)ProtectedProcessInfo);
          return -2147024883;
        }
        v45 = this[21]
           || (_DWORD)v57 == 2
           || (_DWORD)v57 == 1 && (_DWORD)hSourceHandle != 3 && (_DWORD)hSourceHandle != 8;
        this[21] = v45;
      }
      WerGetFlags(v38, this + 31);
      if ( !a8 )
        goto LABEL_54;
      *((struct _WER_EXCEPTION_INFORMATION *)this + 114) = *a8;
      if ( !a8->pExceptionPointers )
        goto LABEL_54;
      if ( a8->bClientPointers && v38 )
      {
        if ( UtilReadExceptionInformationFromExceptionPointer(v38, a8->pExceptionPointers, &v64, v46) >= 0 )
        {
          *((_QWORD *)this + 226) = v64.ExceptionAddress;
          ExceptionCode = v64.ExceptionCode;
LABEL_53:
          this[454] = ExceptionCode;
        }
      }
      else
      {
        ExceptionRecord = a8->pExceptionPointers->ExceptionRecord;
        if ( ExceptionRecord )
        {
          *((_QWORD *)this + 226) = ExceptionRecord->ExceptionAddress;
          ExceptionCode = a8->pExceptionPointers->ExceptionRecord->ExceptionCode;
          goto LABEL_53;
        }
      }
LABEL_54:
      *this = 1;
      return 0;
    }
    return -2147024809;
  }
  result = PssQuerySnapshot(v36, 1, &hProcess);
  if ( result == 1168 )
    return -2147024809;
  v37 = result <= 0;
  if ( !result )
  {
    result = PssQuerySnapshot(*((_QWORD *)this + 96), 0, v65);
    v37 = result <= 0;
    if ( !result )
    {
      v38 = hProcess;
      this[30] = v66;
      this[32] = v67 & 1;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(this + 34, v68);
      goto LABEL_29;
    }
  }
  if ( !v37 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800813d4  mov     [rsp-8+arg_8], rbx
0x1800813d9  push    rbp
0x1800813da  push    rsi
0x1800813db  push    rdi
0x1800813dc  push    r12
0x1800813de  push    r13
0x1800813e0  push    r14
0x1800813e2  push    r15
0x1800813e4  lea     rbp, [rsp-570h]
0x1800813ec  sub     rsp, 670h
0x1800813f3  mov     rax, cs:__security_cookie
0x1800813fa  xor     rax, rsp
0x1800813fd  mov     [rbp+5A0h+var_40], rax
0x180081404  mov     rax, [rbp+5A0h+arg_20]
0x18008140b  mov     rsi, rcx
0x18008140e  mov     r14, [rbp+5A0h+arg_38]
0x180081415  lea     rcx, [rbp+5A0h+var_300]; void *
0x18008141c  mov     r12, [rbp+5A0h+arg_40]
0x180081423  xor     edi, edi
0x180081425  mov     [rsp+6A0h+var_640], r8
0x18008142a  mov     r8d, 2C0h; Size
0x180081430  mov     [rsp+6A0h+var_648], rdx
0x180081435  xor     edx, edx; Val
0x180081437  mov     [rsp+6A0h+var_658], rax
0x18008143c  mov     [rsp+6A0h+hProcess], rdi
0x180081441  mov     [rsp+6A0h+hSourceHandle], r9
0x180081446  call    memset_0
0x18008144b  xor     edx, edx; Val
0x18008144d  lea     r8d, [rdi+40h]; Size
0x180081451  lea     rcx, [rsp+6A0h+ProcessInformation]; void *
0x180081456  call    memset_0
0x18008145b  xor     edx, edx; Val
0x18008145d  lea     rcx, [rbp+5A0h+var_3A0]; void *
0x180081464  mov     r8d, 98h; Size
0x18008146a  call    memset_0
0x18008146f  mov     ebx, [rbp+5A0h+arg_28]
0x180081475  lea     eax, [rbx-1]
0x180081478  cmp     eax, 3
0x18008147b  ja      loc_180081A52
0x180081481  test    r12, r12
0x180081484  jz      short loc_1800814A7
0x180081486  mov     ecx, [r12]
0x18008148a  lea     eax, [rcx-228h]
0x180081490  test    eax, 0FFFFFFD7h
0x180081495  jnz     loc_180081A52
0x18008149b  cmp     ecx, 250h
0x1800814a1  jz      loc_180081A52
0x1800814a7  mov     rcx, rsi; this
0x1800814aa  call    ?Uninitialize@CProcessDump@@QEAAXXZ; CProcessDump::Uninitialize(void)
0x1800814af  mov     rcx, [rsi+18h]
0x1800814b3  lea     r15, [rsi+70h]
0x1800814b7  mov     [rsi+20h], rcx
0x1800814bb  xor     edx, edx
0x1800814bd  mov     [rcx], di
0x1800814c0  mov     rcx, r15
0x1800814c3  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800814c8  lea     r13, [rsi+0B8h]
0x1800814cf  mov     [rsi+78h], rdi
0x1800814d3  mov     rcx, r13
0x1800814d6  mov     [rsi+80h], edi
0x1800814dc  xor     edx, edx
0x1800814de  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800814e3  xor     edx, edx; Val
0x1800814e5  mov     [rsi+0C0h], edi
0x1800814eb  mov     r8d, 248h; Size
0x1800814f1  lea     rcx, [rbp+5A0h+var_5F0]; void *
0x1800814f5  call    memset_0
0x1800814fa  mov     edx, 4
0x1800814ff  lea     rdi, [rsi+0C8h]
0x180081506  mov     rcx, rdi
0x180081509  lea     rax, [rbp+5A0h+var_5F0]
0x18008150d  lea     r8d, [rdx+7Ch]
0x180081511  movups  xmm0, xmmword ptr [rax]
0x180081514  movups  xmm1, xmmword ptr [rax+10h]
0x180081518  movups  xmmword ptr [rcx], xmm0
0x18008151b  movups  xmm0, xmmword ptr [rax+20h]
0x18008151f  movups  xmmword ptr [rcx+10h], xmm1
0x180081523  movups  xmm1, xmmword ptr [rax+30h]
0x180081527  movups  xmmword ptr [rcx+20h], xmm0
0x18008152b  movups  xmm0, xmmword ptr [rax+40h]
0x18008152f  movups  xmmword ptr [rcx+30h], xmm1
0x180081533  movups  xmm1, xmmword ptr [rax+50h]
0x180081537  movups  xmmword ptr [rcx+40h], xmm0
0x18008153b  movups  xmm0, xmmword ptr [rax+60h]
0x18008153f  movups  xmmword ptr [rcx+50h], xmm1
0x180081543  movups  xmm1, xmmword ptr [rax+70h]
0x180081547  add     rax, r8
0x18008154a  movups  xmmword ptr [rcx+60h], xmm0
0x18008154e  movups  xmmword ptr [rcx+70h], xmm1
0x180081552  add     rcx, r8
0x180081555  sub     rdx, 1; Val
0x180081559  jnz     short loc_180081511
0x18008155b  movups  xmm0, xmmword ptr [rax]
0x18008155e  mov     r8d, 400h; Size
0x180081564  movups  xmm1, xmmword ptr [rax+10h]
0x180081568  movups  xmmword ptr [rcx], xmm0
0x18008156b  movups  xmm0, xmmword ptr [rax+20h]
0x18008156f  movups  xmmword ptr [rcx+10h], xmm1
0x180081573  movups  xmm1, xmmword ptr [rax+30h]
0x180081577  mov     rax, [rax+40h]
0x18008157b  movups  xmmword ptr [rcx+20h], xmm0
0x18008157f  movups  xmmword ptr [rcx+30h], xmm1
0x180081583  mov     [rcx+40h], rax
0x180081587  lea     rcx, [rsi+310h]; void *
0x18008158e  call    memset_0
0x180081593  mov     rax, [rsp+6A0h+var_648]
0x180081598  lea     r8, aDumpwait; "DumpWait"
0x18008159f  mov     [rsi+8], rax
0x1800815a3  xor     ecx, ecx
0x1800815a5  mov     rax, [rsp+6A0h+var_640]
0x1800815aa  xorps   xmm0, xmm0
0x1800815ad  mov     [rsi+10h], rax
0x1800815b1  xor     r9d, r9d; unsigned int
0x1800815b4  mov     eax, [rbp+5A0h+arg_30]
0x1800815ba  and     eax, 5FFFFFFh
0x1800815bf  mov     dword ptr [rdi], 248h
0x1800815c5  mov     [rsi+0A8h], ebx
0x1800815cb  mov     rdi, 0FFFFFFFF80000002h
0x1800815d2  mov     [rsi+0ACh], eax
0x1800815d8  lea     rbx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800815df  mov     eax, [rbp+5A0h+arg_48]
0x1800815e5  mov     rdx, rbx; wchar_t *
0x1800815e8  mov     [rsi+710h], rcx
0x1800815ef  mov     [rsi+718h], ecx
0x1800815f5  mov     qword ptr [rsp+6A0h+dwDesiredAccess], rcx; bool *
0x1800815fa  mov     rcx, rdi; HKEY
0x1800815fd  mov     [rsi+0B0h], eax
0x180081603  movdqu  xmmword ptr [rsi+720h], xmm0
0x18008160b  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180081610  mov     r9d, 80000000h; unsigned int
0x180081616  mov     [rsi+38h], eax
0x180081619  lea     r8, aDumpthreadprio; "DumpThreadPriority"
0x180081620  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180081629  mov     rdx, rbx; wchar_t *
0x18008162c  mov     rcx, rdi; HKEY
0x18008162f  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180081634  xor     r9d, r9d; unsigned int
0x180081637  mov     [rsi+3Ch], eax
0x18008163a  lea     r8, aDumpprofilinge; "DumpProfilingEnabled"
0x180081641  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x18008164a  mov     rdx, rbx; wchar_t *
0x18008164d  mov     rcx, rdi; HKEY
0x180081650  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180081655  xor     ecx, ecx
0x180081657  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180081660  test    eax, eax
0x180081662  lea     r8, aDumpbgpriority; "DumpBgPriorityDisabled"
0x180081669  mov     rdx, rbx; wchar_t *
0x18008166c  setnz   cl
0x18008166f  xor     r9d, r9d; unsigned int
0x180081672  mov     [rsi+40h], ecx
0x180081675  mov     rcx, rdi; HKEY
0x180081678  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x18008167d  xor     ecx, ecx
0x18008167f  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x180081688  test    eax, eax
0x18008168a  lea     r8, aDumpusetransie; "DumpUseTransientFile"
0x180081691  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x180081698  setnz   cl
0x18008169b  or      ebx, 0FFFFFFFFh
0x18008169e  mov     [rsi+44h], ecx
0x1800816a1  mov     r9d, ebx; unsigned int
0x1800816a4  mov     rcx, rdi; HKEY
0x1800816a7  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800816ac  xor     r9d, r9d; unsigned int
0x1800816af  mov     [rsi+48h], eax
0x1800816b2  lea     r8, aDumpfailgenera; "DumpFailGeneration"
0x1800816b9  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x1800816c2  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800816c9  mov     rcx, rdi; HKEY
0x1800816cc  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800816d1  xor     ecx, ecx
0x1800816d3  test    eax, eax
0x1800816d5  setnz   cl
0x1800816d8  mov     qword ptr [rsp+6A0h+dwDesiredAccess], 0; bool *
0x1800816e1  mov     [rsi+4Ch], ecx
0x1800816e4  lea     r8, aDumpwritebuffe; "DumpWriteBufferSize"
0x1800816eb  mov     rcx, rdi; HKEY
0x1800816ee  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x1800816f5  mov     r9d, ebx; unsigned int
0x1800816f8  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x1800816fd  mov     rcx, rsi; this
0x180081700  mov     [rsi+50h], eax
0x180081703  call    ?SetDefaultDumpOptions@CProcessDump@@AEAAXXZ; CProcessDump::SetDefaultDumpOptions(void)
0x180081708  xor     edi, edi
0x18008170a  cmp     [rsp+6A0h+hSourceHandle], rdi
0x18008170f  jz      short loc_18008176F
0x180081711  mov     rcx, r15
0x180081714  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180081719  mov     rdi, rax
0x18008171c  call    cs:__imp_GetCurrentProcess
0x180081722  mov     rbx, rax
0x180081725  call    cs:__imp_GetCurrentProcess
0x18008172b  mov     rdx, [rsp+6A0h+hSourceHandle]; hSourceHandle
0x180081730  mov     r9, rdi; lpTargetHandle
0x180081733  mov     [rsp+6A0h+dwOptions], 2; dwOptions
0x18008173b  mov     rcx, rax; hSourceProcessHandle
0x18008173e  mov     dword ptr [rsp+6A0h+bInheritHandle], 0; bInheritHandle
0x180081746  mov     r8, rbx; hTargetProcessHandle
0x180081749  mov     [rsp+6A0h+dwDesiredAccess], 0; dwDesiredAccess
0x180081751  call    cs:__imp_DuplicateHandle
0x180081757  xor     edi, edi
0x180081759  test    eax, eax
0x18008175b  jnz     short loc_18008176F
0x18008175d  call    cs:__imp_GetLastError
0x180081763  mov     ecx, eax; unsigned int
0x180081765  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008176a  jmp     loc_180081A57
0x18008176f  cmp     [rsp+6A0h+var_658], rdi
0x180081774  jz      short loc_1800817C2
0x180081776  mov     rcx, r13
0x180081779  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18008177e  mov     rdi, rax
0x180081781  call    cs:__imp_GetCurrentProcess
0x180081787  mov     rbx, rax
0x18008178a  call    cs:__imp_GetCurrentProcess
0x180081790  mov     rdx, [rsp+6A0h+var_658]; hSourceHandle
0x180081795  mov     r9, rdi; lpTargetHandle
0x180081798  mov     [rsp+6A0h+dwOptions], 2; dwOptions
0x1800817a0  mov     rcx, rax; hSourceProcessHandle
0x1800817a3  mov     dword ptr [rsp+6A0h+bInheritHandle], 0; bInheritHandle
0x1800817ab  mov     r8, rbx; hTargetProcessHandle
0x1800817ae  mov     [rsp+6A0h+dwDesiredAccess], 0; dwDesiredAccess
0x1800817b6  call    cs:__imp_DuplicateHandle
0x1800817bc  xor     edi, edi
0x1800817be  test    eax, eax
0x1800817c0  jz      short loc_18008175D
0x1800817c2  mov     rcx, [r13+0]; Thread
0x1800817c6  mov     r13d, 1
0x1800817cc  lea     rax, [rcx+1]
0x1800817d0  cmp     rax, r13
0x1800817d3  jbe     short loc_1800817E1
0x1800817d5  call    cs:__imp_GetThreadId
0x1800817db  mov     [rsi+0C0h], eax
0x1800817e1  test    r12, r12
0x1800817e4  jz      short loc_18008180D
0x1800817e6  mov     rdx, r12; void *
0x1800817e9  mov     rcx, rsi; this
0x1800817ec  call    ?SetDumpOptions@CProcessDump@@AEAAJPEAX@Z; CProcessDump::SetDumpOptions(void *)
0x1800817f1  test    eax, eax
0x1800817f3  js      loc_180081A57
0x1800817f9  cmp     [rsi+0C0h], edi
0x1800817ff  jnz     short loc_18008180D
0x180081801  mov     eax, [rsi+308h]
0x180081807  mov     [rsi+0C0h], eax
0x18008180d  mov     rcx, [rsi+300h]
0x180081814  test    rcx, rcx
0x180081817  jz      loc_1800818A5
0x18008181d  mov     r9d, 8
0x180081823  lea     r8, [rsp+6A0h+hProcess]
0x180081828  mov     edx, r13d
0x18008182b  call    cs:__imp_PssQuerySnapshot
0x180081831  cmp     eax, 490h
0x180081836  jz      loc_180081A52
0x18008183c  test    eax, eax
0x18008183e  jz      short loc_180081853
0x180081840  jle     loc_180081A57
0x180081846  movzx   eax, ax
0x180081849  or      eax, 80070000h
0x18008184e  jmp     loc_180081A57
0x180081853  mov     rcx, [rsi+300h]
0x18008185a  lea     r8, [rbp+5A0h+var_300]
0x180081861  mov     r9d, 2C0h
0x180081867  xor     edx, edx
0x180081869  call    cs:__imp_PssQuerySnapshot
0x18008186f  test    eax, eax
0x180081871  jnz     short loc_180081840
0x180081873  mov     eax, [rbp+5A0h+var_2E4]
0x180081879  lea     rcx, [rsi+88h]
0x180081880  mov     rbx, [rsp+6A0h+hProcess]
0x180081885  lea     rdx, [rbp+5A0h+var_24C]
0x18008188c  mov     [rsi+78h], eax
0x18008188f  mov     eax, [rbp+5A0h+var_2DC]
0x180081895  and     eax, r13d
0x180081898  mov     [rsi+80h], eax
0x18008189e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800818a3  jmp     short loc_18008191A
0x1800818a5  mov     rbx, [r15]
0x1800818a8  lea     rax, [rbx+1]
0x1800818ac  cmp     rax, r13
0x1800818af  jbe     loc_180081A52
0x1800818b5  mov     r9d, 40h ; '@'; ProcessInformationLength
0x1800818bb  mov     qword ptr [rsp+6A0h+dwDesiredAccess], rdi; ReturnLength
0x1800818c0  lea     r8, [rsp+6A0h+ProcessInformation]; ProcessInformation
0x1800818c5  mov     [rsp+6A0h+ProcessInformation], r9
0x1800818ca  xor     edx, edx; ProcessInformationClass
0x1800818cc  mov     rcx, rbx; ProcessHandle
0x1800818cf  call    cs:__imp_NtQueryInformationProcess
0x1800818d5  test    eax, eax
0x1800818d7  jns     short loc_1800818E2
0x1800818d9  bts     eax, 1Ch
0x1800818dd  jmp     loc_180081A57
0x1800818e2  mov     eax, [rbp+5A0h+var_608]
0x1800818e5  lea     rdx, [rsp+6A0h+hSourceHandle]; enum _PS_PROTECTED_TYPE *
0x1800818ea  mov     rcx, [r15]; void *
0x1800818ed  xor     r8d, r8d; enum _PS_PROTECTED_SIGNER *
0x1800818f0  mov     [rsi+78h], eax
0x1800818f3  mov     dword ptr [rsp+6A0h+hSourceHandle], edi
0x1800818f7  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x1800818fc  cmp     dword ptr [rsp+6A0h+hSourceHandle], edi
  ... truncated ...
```
