# CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)

- ea: `0x140020c20`
- end: `0x140020fb8`
- name: `?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z`
- size: `920`
- prototype: `static int(void *, void *, unsigned int, unsigned int, enum _WER_DUMP_TYPE, unsigned int, struct _EXCEPTION_POINTERS *, struct HPSS__ *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020fc0`
- `0x140023204`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140005498`
- `0x140014474`
- `0x1400144b4`
- `0x140015b40`
- `0x14001af10`
- `0x14001f44c`
- `0x140020c20`
- `0x140022190`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020d77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020d77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140020d45`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x140020d45`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140020c96`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140020c96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020f8d`
- `wer!WerpAddMemoryBlock` at `0x140020f48`
- `wer!WerpAddMemoryBlock` at `0x140020f48`
- `wer!WerpGetExtendedDiagData` at `0x140020f1c`
- `wer!WerpGetExtendedDiagData` at `0x140020f1c`
- `wer!WerpAddRegisteredDataToReport` at `0x140020edb`
- `wer!WerpAddRegisteredDataToReport` at `0x140020edb`
- `wer!WerReportAddDump` at `0x140020e66`
- `wer!WerReportAddDump` at `0x140020e66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CHangReport::_AddWerDumpForProcess(
        void *a1,
        void *a2,
        unsigned int a3,
        DWORD a4,
        WER_DUMP_TYPE dumpType,
        DWORD dwFlags,
        struct _EXCEPTION_POINTERS *a7,
        struct HPSS__ *a8)
{
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  void **v15; // rax
  int ProcessThreads; // eax
  unsigned int v17; // ebx
  CUserModeHangReport *v18; // rcx
  __int64 v19; // rdx
  DWORD v20; // esi
  HANDLE v21; // rax
  HANDLE v22; // rdx
  signed int LastError; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  HREPORT v26; // rbx
  int v27; // eax
  int v28; // eax
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+48h] [rbp-B8h] BYREF
  HREPORT hReportHandle; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  struct _WER_EXCEPTION_INFORMATION pExceptionParam; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v35[72]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v36; // [rsp+2B0h] [rbp+1B0h]

  hReportHandle = a1;
  pExceptionParam = 0;
  memset_0(v35, 0, 0x248u);
  hObject = 0;
  v33 = 0;
  v31 = 0;
  if ( a3 != GetProcessId(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( !a7->ExceptionRecord )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  if ( !a7->ContextRecord )
    MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13, v14);
  pExceptionParam.bClientPointers = 0;
  pExceptionParam.pExceptionPointers = a7;
  if ( a4 )
  {
    v21 = OpenThread(0x48u, 0, a4);
    v22 = hObject;
    hObject = v21;
    if ( (unsigned __int64)v22 + 1 > 1 )
    {
      CloseHandle(v22);
      v21 = hObject;
    }
    if ( (unsigned __int64)v21 + 1 <= 1 )
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids);
      }
      goto LABEL_46;
    }
    v20 = -805306369;
  }
  else
  {
    v15 = (void **)tlx::replace<tlx::file_handle_traits>(&hObject);
    ProcessThreads = GetProcessThreads(a3, 0x48u, v15, 1u, 0);
    v17 = ProcessThreads;
    if ( ProcessThreads < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 101;
LABEL_12:
        WPP_SF_d(
          *((_QWORD *)v18 + 2),
          v19,
          &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
          (unsigned int)ProcessThreads);
        goto LABEL_46;
      }
      goto LABEL_46;
    }
    v20 = -536870913;
    v21 = hObject;
  }
  ProcessThreads = CHangReport::SetHangExceptionInformation(v21, v20, a7);
  v17 = ProcessThreads;
  if ( ProcessThreads >= 0 )
  {
    v35[0] = 584;
    v35[71] = a8;
    v36 = a4;
    ProcessThreads = WerReportAddDump(
                       hReportHandle,
                       a2,
                       hObject,
                       dumpType,
                       &pExceptionParam,
                       (PWER_DUMP_CUSTOM_OPTIONS)((unsigned __int64)v35 & -(__int64)(a8 != 0)),
                       dwFlags);
    v17 = ProcessThreads;
    if ( ProcessThreads >= 0 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_DDqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, v25, a3, a4, a8, v20);
      }
      v26 = hReportHandle;
      v27 = WerpAddRegisteredDataToReport(hReportHandle, a2);
      if ( v27 < 0
        && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
          (unsigned int)v27);
      }
      if ( (int)WerpGetExtendedDiagData(a2, &v33, &v31) >= 0 )
      {
        if ( v33 )
        {
          if ( v31 )
          {
            v28 = WerpAddMemoryBlock(v26, a3);
            if ( v28 < 0
              && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                107,
                &WPP_6c7034e0252a3228ea586abc03935af9_Traceguids,
                (unsigned int)v28);
            }
          }
        }
      }
      v17 = 0;
    }
    else
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 104;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v19 = 103;
      goto LABEL_12;
    }
  }
LABEL_46:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v17;
}

```

## disassembly

```asm
0x140020c20  push    rbp
0x140020c22  push    rbx
0x140020c23  push    rsi
0x140020c24  push    rdi
0x140020c25  push    r12
0x140020c27  push    r13
0x140020c29  push    r14
0x140020c2b  push    r15
0x140020c2d  lea     rbp, [rsp-1D8h]
0x140020c35  sub     rsp, 2D8h
0x140020c3c  mov     rax, cs:__security_cookie
0x140020c43  xor     rax, rsp
0x140020c46  mov     [rbp+210h+var_50], rax
0x140020c4d  mov     r14d, r9d
0x140020c50  mov     r13d, r8d
0x140020c53  mov     r15, rdx
0x140020c56  mov     [rsp+310h+hReportHandle], rcx
0x140020c5b  mov     rdi, [rbp+210h+arg_30]
0x140020c62  mov     r12, [rbp+210h+arg_38]
0x140020c69  xorps   xmm0, xmm0
0x140020c6c  movups  xmmword ptr [rsp+310h+var_2B0.pExceptionPointers], xmm0
0x140020c71  xor     edx, edx; Val
0x140020c73  mov     r8d, 248h; Size
0x140020c79  lea     rcx, [rsp+310h+var_2A0]; void *
0x140020c7e  call    memset_0
0x140020c83  xor     esi, esi
0x140020c85  mov     [rsp+310h+hObject], rsi
0x140020c8a  mov     [rsp+310h+var_2B8], rsi
0x140020c8f  mov     [rsp+310h+var_2C8], esi
0x140020c93  mov     rcx, r15; Process
0x140020c96  call    cs:__imp_GetProcessId
0x140020c9c  cmp     r13d, eax
0x140020c9f  jz      short loc_140020CA6
0x140020ca1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140020ca6  cmp     [rdi], rsi
0x140020ca9  jnz     short loc_140020CB0
0x140020cab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140020cb0  cmp     [rdi+8], rsi
0x140020cb4  jnz     short loc_140020CBB
0x140020cb6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140020cbb  mov     [rsp+310h+var_2B0.bClientPointers], esi
0x140020cbf  mov     [rsp+310h+var_2B0.pExceptionPointers], rdi
0x140020cc4  test    r14d, r14d
0x140020cc7  jnz     short loc_140020D3D
0x140020cc9  lea     rcx, [rsp+310h+hObject]
0x140020cce  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140020cd3  mov     r8, rax; void **
0x140020cd6  mov     [rsp+310h+pExceptionParam], rsi; unsigned int *
0x140020cdb  lea     edx, [r14+48h]; unsigned int
0x140020cdf  lea     r9d, [r14+1]; unsigned int
0x140020ce3  mov     ecx, r13d; unsigned int
0x140020ce6  call    ?GetProcessThreads@@YAJKKPEAPEAXKPEAK@Z; GetProcessThreads(ulong,ulong,void * *,ulong,ulong *)
0x140020ceb  mov     ebx, eax
0x140020ced  test    eax, eax
0x140020cef  jns     short loc_140020D2E
0x140020cf1  lea     rdi, WPP_GLOBAL_Control
0x140020cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140020cff  cmp     rcx, rdi
0x140020d02  jz      loc_140020F7E
0x140020d08  test    byte ptr [rcx+1Ch], 1
0x140020d0c  jz      loc_140020F7E
0x140020d12  lea     edx, [r14+65h]
0x140020d16  mov     r9d, eax
0x140020d19  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020d20  mov     rcx, [rcx+10h]
0x140020d24  call    WPP_SF_d
0x140020d29  jmp     loc_140020F7E
0x140020d2e  mov     esi, 0DFFFFFFFh
0x140020d33  mov     rax, [rsp+310h+hObject]
0x140020d38  jmp     loc_140020DD3
0x140020d3d  mov     r8d, r14d; dwThreadId
0x140020d40  xor     edx, edx; bInheritHandle
0x140020d42  lea     ecx, [rdx+48h]; dwDesiredAccess
0x140020d45  call    cs:__imp_OpenThread
0x140020d4b  mov     rdx, [rsp+310h+hObject]
0x140020d50  mov     [rsp+310h+hObject], rax
0x140020d55  lea     rcx, [rdx+1]
0x140020d59  cmp     rcx, 1
0x140020d5d  jbe     short loc_140020D6D
0x140020d5f  mov     rcx, rdx; hObject
0x140020d62  call    cs:__imp_CloseHandle
0x140020d68  mov     rax, [rsp+310h+hObject]
0x140020d6d  lea     rcx, [rax+1]
0x140020d71  cmp     rcx, 1
0x140020d75  ja      short loc_140020DCE
0x140020d77  call    cs:__imp_GetLastError
0x140020d7d  mov     ebx, eax
0x140020d7f  test    eax, eax
0x140020d81  jle     short loc_140020D8C
0x140020d83  movzx   ebx, ax
0x140020d86  or      ebx, 80070000h
0x140020d8c  lea     rdi, WPP_GLOBAL_Control
0x140020d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d9a  cmp     rcx, rdi
0x140020d9d  jz      loc_140020F7E
0x140020da3  test    byte ptr [rcx+1Ch], 1
0x140020da7  jz      loc_140020F7E
0x140020dad  mov     edx, 66h ; 'f'
0x140020db2  mov     dword ptr [rsp+310h+pExceptionParam], ebx
0x140020db6  mov     r9d, r14d
0x140020db9  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020dc0  mov     rcx, [rcx+10h]
0x140020dc4  call    WPP_SF_Dd
0x140020dc9  jmp     loc_140020F7E
0x140020dce  mov     esi, 0CFFFFFFFh
0x140020dd3  mov     r8, rdi; struct _EXCEPTION_POINTERS *
0x140020dd6  mov     edx, esi; unsigned int
0x140020dd8  mov     rcx, rax; hThread
0x140020ddb  call    ?SetHangExceptionInformation@CHangReport@@CAJPEAXKPEAU_EXCEPTION_POINTERS@@@Z; CHangReport::SetHangExceptionInformation(void *,ulong,_EXCEPTION_POINTERS *)
0x140020de0  mov     ebx, eax
0x140020de2  test    eax, eax
0x140020de4  jns     short loc_140020E11
0x140020de6  lea     rdi, WPP_GLOBAL_Control
0x140020ded  mov     rcx, cs:WPP_GLOBAL_Control
0x140020df4  cmp     rcx, rdi
0x140020df7  jz      loc_140020F7E
0x140020dfd  test    byte ptr [rcx+1Ch], 1
0x140020e01  jz      loc_140020F7E
0x140020e07  mov     edx, 67h ; 'g'
0x140020e0c  jmp     loc_140020D16
0x140020e11  mov     [rsp+310h+var_2A0], 248h
0x140020e1a  mov     [rbp+210h+var_68], r12
0x140020e21  mov     [rbp+210h+var_60], r14d
0x140020e28  mov     rax, r12
0x140020e2b  neg     rax
0x140020e2e  sbb     rcx, rcx
0x140020e31  lea     rax, [rsp+310h+var_2A0]
0x140020e36  and     rcx, rax
0x140020e39  mov     eax, [rbp+210h+arg_28]
0x140020e3f  mov     [rsp+310h+dwFlags], eax; dwFlags
0x140020e43  mov     [rsp+310h+pDumpCustomOptions], rcx; pDumpCustomOptions
0x140020e48  lea     rax, [rsp+310h+var_2B0]
0x140020e4d  mov     [rsp+310h+pExceptionParam], rax; pExceptionParam
0x140020e52  mov     r9d, [rbp+210h+dumpType]; dumpType
0x140020e59  mov     r8, [rsp+310h+hObject]; hThread
0x140020e5e  mov     rdx, r15; hProcess
0x140020e61  mov     rcx, [rsp+310h+hReportHandle]; hReportHandle
0x140020e66  call    cs:__imp_WerReportAddDump
0x140020e6c  mov     ebx, eax
0x140020e6e  test    eax, eax
0x140020e70  jns     short loc_140020E9D
0x140020e72  lea     rdi, WPP_GLOBAL_Control
0x140020e79  mov     rcx, cs:WPP_GLOBAL_Control
0x140020e80  cmp     rcx, rdi
0x140020e83  jz      loc_140020F7E
0x140020e89  test    byte ptr [rcx+1Ch], 1
0x140020e8d  jz      loc_140020F7E
0x140020e93  mov     edx, 68h ; 'h'
0x140020e98  jmp     loc_140020D16
0x140020e9d  lea     rdi, WPP_GLOBAL_Control
0x140020ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140020eab  cmp     rcx, rdi
0x140020eae  jz      short loc_140020ED0
0x140020eb0  test    byte ptr [rcx+1Ch], 4
0x140020eb4  jz      short loc_140020ED0
0x140020eb6  mov     [rsp+310h+dwFlags], esi
0x140020eba  mov     [rsp+310h+pDumpCustomOptions], r12
0x140020ebf  mov     dword ptr [rsp+310h+pExceptionParam], r14d
0x140020ec4  mov     r9d, r13d
0x140020ec7  mov     rcx, [rcx+10h]
0x140020ecb  call    WPP_SF_DDqD
0x140020ed0  mov     rdx, r15
0x140020ed3  mov     rbx, [rsp+310h+hReportHandle]
0x140020ed8  mov     rcx, rbx
0x140020edb  call    cs:__imp_WerpAddRegisteredDataToReport
0x140020ee1  test    eax, eax
0x140020ee3  jns     short loc_140020F0F
0x140020ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x140020eec  cmp     rcx, rdi
0x140020eef  jz      short loc_140020F0F
0x140020ef1  test    byte ptr [rcx+1Ch], 2
0x140020ef5  jz      short loc_140020F0F
0x140020ef7  mov     edx, 6Ah ; 'j'
0x140020efc  mov     r9d, eax
0x140020eff  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020f06  mov     rcx, [rcx+10h]
0x140020f0a  call    WPP_SF_d
0x140020f0f  lea     r8, [rsp+310h+var_2C8]
0x140020f14  lea     rdx, [rsp+310h+var_2B8]
0x140020f19  mov     rcx, r15
0x140020f1c  call    cs:__imp_WerpGetExtendedDiagData
0x140020f22  test    eax, eax
0x140020f24  js      short loc_140020F7C
0x140020f26  mov     r8, [rsp+310h+var_2B8]
0x140020f2b  test    r8, r8
0x140020f2e  jz      short loc_140020F7C
0x140020f30  mov     r9d, [rsp+310h+var_2C8]
0x140020f35  test    r9d, r9d
0x140020f38  jz      short loc_140020F7C
0x140020f3a  mov     dword ptr [rsp+310h+pExceptionParam], 0
0x140020f42  mov     edx, r13d
0x140020f45  mov     rcx, rbx
0x140020f48  call    cs:__imp_WerpAddMemoryBlock
0x140020f4e  test    eax, eax
0x140020f50  jns     short loc_140020F7C
0x140020f52  mov     rcx, cs:WPP_GLOBAL_Control
0x140020f59  cmp     rcx, rdi
0x140020f5c  jz      short loc_140020F7C
0x140020f5e  test    byte ptr [rcx+1Ch], 2
0x140020f62  jz      short loc_140020F7C
0x140020f64  mov     edx, 6Bh ; 'k'
0x140020f69  mov     r9d, eax
0x140020f6c  lea     r8, WPP_6c7034e0252a3228ea586abc03935af9_Traceguids
0x140020f73  mov     rcx, [rcx+10h]
0x140020f77  call    WPP_SF_d
0x140020f7c  xor     ebx, ebx
0x140020f7e  mov     rcx, [rsp+310h+hObject]; hObject
0x140020f83  lea     rax, [rcx+1]
0x140020f87  cmp     rax, 1
0x140020f8b  jbe     short loc_140020F93
0x140020f8d  call    cs:__imp_CloseHandle
0x140020f93  mov     eax, ebx
0x140020f95  mov     rcx, [rbp+210h+var_50]
0x140020f9c  xor     rcx, rsp; StackCookie
0x140020f9f  call    __security_check_cookie
0x140020fa4  add     rsp, 2D8h
0x140020fab  pop     r15
0x140020fad  pop     r14
0x140020faf  pop     r13
0x140020fb1  pop     r12
0x140020fb3  pop     rdi
0x140020fb4  pop     rsi
0x140020fb5  pop     rbx
0x140020fb6  pop     rbp
0x140020fb7  retn
```
