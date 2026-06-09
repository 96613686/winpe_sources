# CKernelReport::ReportFromKQueue(void)

- ea: `0x140039614`
- end: `0x14003981a`
- name: `?ReportFromKQueue@CKernelReport@@QEAAJXZ`
- size: `518`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x14003494c`
- `0x140039820`

## callees

- `0x140002728`
- `0x140005930`
- `0x140011db4`
- `0x140034d9c`
- `0x1400353c0`
- `0x140035654`
- `0x140036634`
- `0x140038af0`
- `0x140038fd0`
- `0x140039614`
- `0x14003a8fc`
- `0x14003b1ac`
- `0x14003b2fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140039724`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140039724`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003980a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003980a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400397bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005c1c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400397bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005c1c5`

## pseudocode

```c
__int64 __fastcall CKernelReport::ReportFromKQueue(CKernelReport *this)
{
  CKernelReport *v2; // rcx
  int QueuedReports; // ebx
  const char *v4; // rax
  __int64 v5; // rdx
  CKernelReport *v6; // rcx
  __int64 v7; // rbx
  int v8; // eax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdx
  _QWORD *v11; // rax
  void *v12; // rcx
  CKernelReport *v13; // rcx
  wil::details *v15; // [rsp+20h] [rbp-28h]
  char *v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag4 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF
  _QWORD *v19; // [rsp+60h] [rbp+18h]

  hKey = 0;
  QueuedReports = CKernelReport::SetReporting(this, 1);
  if ( QueuedReports < 0 )
  {
    v4 = "Failed to set reporting mode to true";
    v5 = 955;
LABEL_3:
    LODWORD(v15) = QueuedReports;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromKQueue",
      v15,
      (int)v4,
      v16);
    goto LABEL_17;
  }
  QueuedReports = CKernelReport::EnsureKernelQueueRegkeyExists(v2, &hKey);
  if ( QueuedReports < 0 )
  {
    v4 = "EnsureRegkeyExists failed";
    v5 = 963;
    goto LABEL_3;
  }
  CKernelReport::WaitForDumpConversion(v6);
  QueuedReports = CKernelReport::LoadQueuedReports(this, hKey);
  if ( QueuedReports >= 0 )
  {
    v7 = *((_QWORD *)this + 82);
    if ( (CKernelReport *)v7 != (CKernelReport *)((char *)this + 656) )
    {
      *((_DWORD *)this + 184) = *(_DWORD *)(v7 + 72);
      *((_DWORD *)this + 182) = *(_DWORD *)(v7 + 76);
      *((_DWORD *)this + 183) = *(_DWORD *)(v7 + 80);
      v8 = CKernelReport::SendReport(this, *(const wchar_t **)(v7 + 16), (const struct _GUID *)(v7 + 56), 0);
      if ( v8 < 0 )
      {
        LODWORD(v15) = v8;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x3F2,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::ReportFromKQueue",
          v15,
          (int)"SendReport failed",
          v16);
      }
      else
      {
        RegDeleteValueW(hKey, *(LPCWSTR *)(v7 + 16));
        v9 = (_QWORD *)*((_QWORD *)this + 82);
        v19 = v9;
        v10 = (_QWORD *)*v9;
        v19 = v10;
        v11 = (_QWORD *)v9[1];
        *v11 = v10;
        v10[1] = v11;
        KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT((KERNEL_QUEUED_REPORT *)(v9 + 2));
        operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
        --*((_QWORD *)this + 84);
      }
      CKernelReport::AddUnsentReportsToWERQueue(this, hKey);
    }
    QueuedReports = 0;
  }
  else
  {
    LODWORD(v15) = QueuedReports;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x3D3,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromKQueue",
      v15,
      (int)"LoadQueuedReports failed",
      v16);
  }
  v12 = (void *)*((_QWORD *)this + 81);
  *((_QWORD *)this + 81) = 0;
  if ( (unsigned __int64)v12 + 1 > 1 )
    CloseHandle(v12);
  LODWORD(v15) = 0;
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x3FF,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::ReportFromKQueue",
    (const char *)v15,
    (int)"Failed to set reporting mode to FALSE",
    v16);
LABEL_17:
  if ( !UtilIsWinRE() )
    CKernelReport::CheckAndDeleteMemoryDump(v13);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)QueuedReports;
}

```

## disassembly

```asm
0x140039614  mov     [rsp+arg_0], rcx
0x140039619  push    rbx
0x14003961a  push    rsi
0x14003961b  push    rdi; char *
0x14003961c  sub     rsp, 30h
0x140039620  mov     rdi, rcx
0x140039623  mov     [rsp+48h+hKey], 0
0x14003962c  mov     edx, 1; int
0x140039631  call    ?SetReporting@CKernelReport@@AEAAJH@Z; CKernelReport::SetReporting(int)
0x140039636  mov     ebx, eax
0x140039638  test    eax, eax
0x14003963a  jns     short loc_14003966E
0x14003963c  lea     rax, aFailedToSetRep; "Failed to set reporting mode to true"
0x140039643  mov     edx, 3BBh; void *
0x140039648  mov     qword ptr [rsp+48h+var_20], rax; int
0x14003964d  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039654  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14003965b  mov     dword ptr [rsp+48h+var_28], ebx; wil::details *
0x14003965f  mov     rcx, [rsp+48h]; this
0x140039664  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039669  jmp     loc_1400397F2
0x14003966e  lea     rdx, [rsp+48h+hKey]; HKEY *
0x140039673  call    ?EnsureKernelQueueRegkeyExists@CKernelReport@@AEAAJPEAPEAUHKEY__@@@Z; CKernelReport::EnsureKernelQueueRegkeyExists(HKEY__ * *)
0x140039678  mov     ebx, eax
0x14003967a  test    eax, eax
0x14003967c  jns     short loc_14003968C
0x14003967e  lea     rax, aEnsureregkeyex; "EnsureRegkeyExists failed"
0x140039685  mov     edx, 3C3h
0x14003968a  jmp     short loc_140039648
0x14003968c  call    ?WaitForDumpConversion@CKernelReport@@QEAAJXZ; CKernelReport::WaitForDumpConversion(void)
0x140039691  mov     rdx, [rsp+48h+hKey]; HKEY
0x140039696  mov     rcx, rdi; this
0x140039699  call    ?LoadQueuedReports@CKernelReport@@AEAAJPEAUHKEY__@@@Z; CKernelReport::LoadQueuedReports(HKEY__ *)
0x14003969e  mov     ebx, eax
0x1400396a0  test    eax, eax
0x1400396a2  jns     short loc_1400396D6
0x1400396a4  mov     rcx, [rsp+48h]; this
0x1400396a9  lea     rax, aLoadqueuedrepo; "LoadQueuedReports failed"
0x1400396b0  mov     qword ptr [rsp+48h+var_20], rax; int
0x1400396b5  mov     dword ptr [rsp+48h+var_28], ebx; wil::details *
0x1400396b9  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x1400396c0  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400396c7  mov     edx, 3D3h; void *
0x1400396cc  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400396d1  jmp     loc_14003979F
0x1400396d6  lea     rsi, [rdi+290h]
0x1400396dd  mov     rbx, [rsi]
0x1400396e0  cmp     rbx, rsi
0x1400396e3  jz      loc_14003979D
0x1400396e9  mov     eax, [rbx+48h]
0x1400396ec  mov     [rdi+2E0h], eax
0x1400396f2  mov     eax, [rbx+4Ch]
0x1400396f5  mov     [rdi+2D8h], eax
0x1400396fb  mov     eax, [rbx+50h]
0x1400396fe  mov     [rdi+2DCh], eax
0x140039704  lea     r8, [rbx+38h]; struct _GUID *
0x140039708  xor     r9d, r9d; unsigned int
0x14003970b  mov     rdx, [rbx+10h]; wchar_t *
0x14003970f  mov     rcx, rdi; this
0x140039712  call    ?SendReport@CKernelReport@@AEAAJPEB_WPEBU_GUID@@K@Z; CKernelReport::SendReport(wchar_t const *,_GUID const *,ulong)
0x140039717  test    eax, eax
0x140039719  js      short loc_140039763
0x14003971b  mov     rdx, [rbx+10h]; lpValueName
0x14003971f  mov     rcx, [rsp+48h+hKey]; hKey
0x140039724  call    cs:__imp_RegDeleteValueW
0x14003972a  mov     rbx, [rsi]
0x14003972d  mov     [rsp+48h+arg_10], rbx
0x140039732  mov     rdx, [rbx]
0x140039735  mov     [rsp+48h+arg_10], rdx
0x14003973a  mov     rax, [rbx+8]
0x14003973e  mov     [rax], rdx
0x140039741  mov     [rdx+8], rax
0x140039745  lea     rcx, [rbx+10h]; this
0x140039749  call    ??1KERNEL_QUEUED_REPORT@@QEAA@XZ; KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT(void)
0x14003974e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140039755  mov     rcx, rbx; void *
0x140039758  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003975d  dec     qword ptr [rsi+10h]
0x140039761  jmp     short loc_140039790
0x140039763  mov     rcx, [rsp+48h]; this
0x140039768  lea     rdx, aSendreportFail; "SendReport failed"
0x14003976f  mov     qword ptr [rsp+48h+var_20], rdx; int
0x140039774  mov     dword ptr [rsp+48h+var_28], eax; wil::details *
0x140039778  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14003977f  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140039786  mov     edx, 3F2h; void *
0x14003978b  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140039790  mov     rdx, [rsp+48h+hKey]; HKEY
0x140039795  mov     rcx, rdi; this
0x140039798  call    ?AddUnsentReportsToWERQueue@CKernelReport@@AEAAJPEAUHKEY__@@@Z; CKernelReport::AddUnsentReportsToWERQueue(HKEY__ *)
0x14003979d  xor     ebx, ebx
0x14003979f  mov     rcx, [rdi+288h]; hObject
0x1400397a6  mov     qword ptr [rdi+288h], 0
0x1400397b1  lea     rax, [rcx+1]
0x1400397b5  cmp     rax, 1
0x1400397b9  jbe     short loc_1400397C1
0x1400397bb  call    cs:__imp_CloseHandle
0x1400397c1  mov     rcx, [rsp+48h]; this
0x1400397c6  lea     rax, aFailedToSetRep_0; "Failed to set reporting mode to FALSE"
0x1400397cd  mov     qword ptr [rsp+48h+var_20], rax; int
0x1400397d2  mov     dword ptr [rsp+48h+var_28], 0; char *
0x1400397da  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x1400397e1  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x1400397e8  mov     edx, 3FFh; void *
0x1400397ed  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400397f2  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x1400397f7  test    al, al
0x1400397f9  jnz     short loc_140039800
0x1400397fb  call    ?CheckAndDeleteMemoryDump@CKernelReport@@AEAAXXZ; CKernelReport::CheckAndDeleteMemoryDump(void)
0x140039800  mov     rcx, [rsp+48h+hKey]; hKey
0x140039805  test    rcx, rcx
0x140039808  jz      short loc_140039810
0x14003980a  call    cs:__imp_RegCloseKey
0x140039810  mov     eax, ebx
0x140039812  add     rsp, 30h
0x140039816  pop     rdi
0x140039817  pop     rsi
0x140039818  pop     rbx
0x140039819  retn
0x14005c19c  push    rbp; char *
0x14005c19e  sub     rsp, 30h
0x14005c1a2  mov     rbp, rdx
0x14005c1a5  mov     rax, [rbp+50h]
0x14005c1a9  mov     rcx, [rax+288h]; hObject
0x14005c1b0  mov     qword ptr [rax+288h], 0
0x14005c1bb  lea     rax, [rcx+1]
0x14005c1bf  cmp     rax, 1
0x14005c1c3  jbe     short loc_14005C1CC
0x14005c1c5  call    cs:__imp_CloseHandle
0x14005c1cb  nop
0x14005c1cc  mov     rcx, [rbp+48h]; this
0x14005c1d0  lea     rax, aFailedToSetRep_0; "Failed to set reporting mode to FALSE"
0x14005c1d7  mov     qword ptr [rsp+38h+var_10], rax; int
0x14005c1dc  mov     dword ptr [rsp+38h+var_18], 0; char *
0x14005c1e4  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14005c1eb  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14005c1f2  mov     edx, 3FFh; void *
0x14005c1f7  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14005c1fc  nop
0x14005c1fd  add     rsp, 30h
0x14005c201  pop     rbp
0x14005c202  retn
```
