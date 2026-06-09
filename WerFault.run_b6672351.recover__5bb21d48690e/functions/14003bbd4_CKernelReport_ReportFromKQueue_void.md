# CKernelReport::ReportFromKQueue(void)

- ea: `0x14003bbd4`
- end: `0x14003be54`
- name: `?ReportFromKQueue@CKernelReport@@QEAAJXZ`
- size: `640`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140036e5c`
- `0x14003be5c`

## callees

- `0x140002748`
- `0x140005910`
- `0x1400125ec`
- `0x1400149e8`
- `0x1400372dc`
- `0x140037b60`
- `0x140038bd8`
- `0x14003b0a0`
- `0x14003b510`
- `0x14003bbd4`
- `0x14003d048`
- `0x14003da10`
- `0x14003db90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003bccf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003bd6f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003bccf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14003bd6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003be37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003be37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003bdd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005ff4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003bdd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005ff4a`

## pseudocode

```c
__int64 __fastcall CKernelReport::ReportFromKQueue(CKernelReport *this)
{
  CKernelReport *v2; // rcx
  int QueuedReports; // ebx
  const char *v4; // rax
  __int64 v5; // rdx
  CKernelReport *v6; // rcx
  _QWORD **v7; // rbx
  __int64 v8; // rdi
  int v9; // eax
  _QWORD *v10; // rdi
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  HKEY v13; // r14
  _QWORD *i; // rdi
  int v15; // eax
  void *v16; // rcx
  CKernelReport *v17; // rcx
  wil::details *v19; // [rsp+20h] [rbp-38h]
  char *v20; // [rsp+30h] [rbp-28h]
  wil::details::in1diag4 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF
  _QWORD *v23; // [rsp+70h] [rbp+18h]

  hKey = 0;
  QueuedReports = CKernelReport::SetReporting(this, 1);
  if ( QueuedReports < 0 )
  {
    v4 = "Failed to set reporting mode to true";
    v5 = 945;
LABEL_3:
    LODWORD(v19) = QueuedReports;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromKQueue",
      v19,
      (int)v4,
      v20);
    goto LABEL_22;
  }
  QueuedReports = CKernelReport::EnsureKernelQueueRegkeyExists(v2, &hKey);
  if ( QueuedReports < 0 )
  {
    v4 = "EnsureRegkeyExists failed";
    v5 = 953;
    goto LABEL_3;
  }
  CKernelReport::WaitForDumpConversion(v6);
  QueuedReports = CKernelReport::LoadQueuedReports(this, hKey);
  if ( QueuedReports >= 0 )
  {
    v7 = (_QWORD **)((char *)this + 656);
    v8 = *((_QWORD *)this + 82);
    if ( (CKernelReport *)v8 != (CKernelReport *)((char *)this + 656) )
    {
      v9 = CKernelReport::SendReport(this, *(const wchar_t **)(v8 + 16), (const struct _GUID *)(v8 + 56), 0);
      if ( v9 < 0 )
      {
        LODWORD(v19) = v9;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x3DF,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::ReportFromKQueue",
          v19,
          (int)"SendReport failed",
          v20);
      }
      else
      {
        RegDeleteValueW(hKey, *(LPCWSTR *)(v8 + 16));
        v10 = *v7;
        v23 = v10;
        v11 = (_QWORD *)*v10;
        v23 = v11;
        v12 = (_QWORD *)v10[1];
        *v12 = v11;
        v11[1] = v12;
        KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT((KERNEL_QUEUED_REPORT *)(v10 + 2));
        operator delete(v10, (const struct std::nothrow_t *)&std::nothrow);
        --*((_QWORD *)this + 84);
      }
      v13 = hKey;
      for ( i = *v7; i != v7; i = (_QWORD *)*i )
      {
        v15 = CKernelReport::SendReport(this, (const wchar_t *)i[2], (const struct _GUID *)(i + 7), 0x80000000);
        if ( v15 < 0 )
        {
          LODWORD(v19) = v15;
          wil::details::in1diag4::Log_HrMsg(
            retaddr,
            (void *)0x33A,
            (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
            "CKernelReport::AddUnsentReportsToWERQueue",
            v19,
            (int)"SendReport failed for %ws",
            (const char *)i[2]);
        }
        else
        {
          RegDeleteValueW(v13, (LPCWSTR)i[2]);
        }
      }
    }
    QueuedReports = 0;
  }
  else
  {
    LODWORD(v19) = QueuedReports;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x3C9,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
      "CKernelReport::ReportFromKQueue",
      v19,
      (int)"LoadQueuedReports failed",
      v20);
  }
  v16 = (void *)*((_QWORD *)this + 81);
  *((_QWORD *)this + 81) = 0;
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  LODWORD(v19) = 0;
  wil::details::in1diag4::Log_IfFailedMsg(
    retaddr,
    (void *)0x3EC,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
    "CKernelReport::ReportFromKQueue",
    (const char *)v19,
    (int)"Failed to set reporting mode to FALSE",
    v20);
LABEL_22:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl'::`2'::impl)
    || !UtilIsWinRE() )
  {
    CKernelReport::CheckAndDeleteMemoryDump(v17);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)QueuedReports;
}

```

## disassembly

```asm
0x14003bbd4  mov     [rsp+arg_18], rbx
0x14003bbd9  mov     [rsp+arg_0], rcx
0x14003bbde  push    rsi
0x14003bbdf  push    rdi
0x14003bbe0  push    r14
0x14003bbe2  sub     rsp, 40h
0x14003bbe6  mov     rsi, rcx
0x14003bbe9  mov     [rsp+58h+hKey], 0
0x14003bbf2  mov     edx, 1; int
0x14003bbf7  call    ?SetReporting@CKernelReport@@AEAAJH@Z; CKernelReport::SetReporting(int)
0x14003bbfc  mov     ebx, eax
0x14003bbfe  test    eax, eax
0x14003bc00  jns     short loc_14003BC34
0x14003bc02  lea     rax, aFailedToSetRep; "Failed to set reporting mode to true"
0x14003bc09  mov     edx, 3B1h; void *
0x14003bc0e  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003bc13  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bc1a  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14003bc21  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x14003bc25  mov     rcx, [rsp+58h]; this
0x14003bc2a  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003bc2f  jmp     loc_14003BE0F
0x14003bc34  lea     rdx, [rsp+58h+hKey]; HKEY *
0x14003bc39  call    ?EnsureKernelQueueRegkeyExists@CKernelReport@@AEAAJPEAPEAUHKEY__@@@Z; CKernelReport::EnsureKernelQueueRegkeyExists(HKEY__ * *)
0x14003bc3e  mov     ebx, eax
0x14003bc40  test    eax, eax
0x14003bc42  jns     short loc_14003BC52
0x14003bc44  lea     rax, aEnsureregkeyex; "EnsureRegkeyExists failed"
0x14003bc4b  mov     edx, 3B9h
0x14003bc50  jmp     short loc_14003BC0E
0x14003bc52  call    ?WaitForDumpConversion@CKernelReport@@QEAAJXZ; CKernelReport::WaitForDumpConversion(void)
0x14003bc57  mov     rdx, [rsp+58h+hKey]; HKEY
0x14003bc5c  mov     rcx, rsi; this
0x14003bc5f  call    ?LoadQueuedReports@CKernelReport@@AEAAJPEAUHKEY__@@@Z; CKernelReport::LoadQueuedReports(HKEY__ *)
0x14003bc64  mov     ebx, eax
0x14003bc66  test    eax, eax
0x14003bc68  jns     short loc_14003BC9C
0x14003bc6a  mov     rcx, [rsp+58h]; this
0x14003bc6f  lea     rax, aLoadqueuedrepo; "LoadQueuedReports failed"
0x14003bc76  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003bc7b  mov     dword ptr [rsp+58h+var_38], ebx; wil::details *
0x14003bc7f  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14003bc86  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bc8d  mov     edx, 3C9h; void *
0x14003bc92  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003bc97  jmp     loc_14003BDB6
0x14003bc9c  lea     rbx, [rsi+290h]
0x14003bca3  mov     rdi, [rbx]
0x14003bca6  cmp     rdi, rbx
0x14003bca9  jz      loc_14003BDB4
0x14003bcaf  lea     r8, [rdi+38h]; struct _GUID *
0x14003bcb3  xor     r9d, r9d; unsigned int
0x14003bcb6  mov     rdx, [rdi+10h]; wchar_t *
0x14003bcba  mov     rcx, rsi; this
0x14003bcbd  call    ?SendReport@CKernelReport@@AEAAJPEB_WPEBU_GUID@@K@Z; CKernelReport::SendReport(wchar_t const *,_GUID const *,ulong)
0x14003bcc2  test    eax, eax
0x14003bcc4  js      short loc_14003BD14
0x14003bcc6  mov     rdx, [rdi+10h]; lpValueName
0x14003bcca  mov     rcx, [rsp+58h+hKey]; hKey
0x14003bccf  call    cs:__imp_RegDeleteValueW
0x14003bcd6  nop     dword ptr [rax+rax+00h]
0x14003bcdb  mov     rdi, [rbx]
0x14003bcde  mov     [rsp+58h+arg_10], rdi
0x14003bce3  mov     rdx, [rdi]
0x14003bce6  mov     [rsp+58h+arg_10], rdx
0x14003bceb  mov     rax, [rdi+8]
0x14003bcef  mov     [rax], rdx
0x14003bcf2  mov     [rdx+8], rax
0x14003bcf6  lea     rcx, [rdi+10h]; this
0x14003bcfa  call    ??1KERNEL_QUEUED_REPORT@@QEAA@XZ; KERNEL_QUEUED_REPORT::~KERNEL_QUEUED_REPORT(void)
0x14003bcff  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003bd06  mov     rcx, rdi; void *
0x14003bd09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003bd0e  dec     qword ptr [rbx+10h]
0x14003bd12  jmp     short loc_14003BD41
0x14003bd14  mov     rcx, [rsp+58h]; this
0x14003bd19  lea     rdx, aSendreportFail; "SendReport failed"
0x14003bd20  mov     qword ptr [rsp+58h+var_30], rdx; int
0x14003bd25  mov     dword ptr [rsp+58h+var_38], eax; wil::details *
0x14003bd29  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14003bd30  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bd37  mov     edx, 3DFh; void *
0x14003bd3c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003bd41  mov     r14, [rsp+58h+hKey]
0x14003bd46  mov     rdi, [rbx]
0x14003bd49  cmp     rdi, rbx
0x14003bd4c  jz      short loc_14003BDB4
0x14003bd4e  lea     r8, [rdi+38h]; struct _GUID *
0x14003bd52  mov     r9d, 80000000h; unsigned int
0x14003bd58  mov     rdx, [rdi+10h]; wchar_t *
0x14003bd5c  mov     rcx, rsi; this
0x14003bd5f  call    ?SendReport@CKernelReport@@AEAAJPEB_WPEBU_GUID@@K@Z; CKernelReport::SendReport(wchar_t const *,_GUID const *,ulong)
0x14003bd64  mov     rdx, [rdi+10h]; lpValueName
0x14003bd68  test    eax, eax
0x14003bd6a  js      short loc_14003BD7D
0x14003bd6c  mov     rcx, r14; hKey
0x14003bd6f  call    cs:__imp_RegDeleteValueW
0x14003bd76  nop     dword ptr [rax+rax+00h]
0x14003bd7b  jmp     short loc_14003BDAF
0x14003bd7d  mov     rcx, [rsp+58h]; this
0x14003bd82  mov     [rsp+58h+var_28], rdx; char *
0x14003bd87  lea     rdx, aSendreportFail_0; "SendReport failed for %ws"
0x14003bd8e  mov     qword ptr [rsp+58h+var_30], rdx; int
0x14003bd93  mov     dword ptr [rsp+58h+var_38], eax; wil::details *
0x14003bd97  lea     r9, aCkernelreportA; "CKernelReport::AddUnsentReportsToWERQue"...
0x14003bd9e  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bda5  mov     edx, 33Ah; void *
0x14003bdaa  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003bdaf  mov     rdi, [rdi]
0x14003bdb2  jmp     short loc_14003BD49
0x14003bdb4  xor     ebx, ebx
0x14003bdb6  mov     rcx, [rsi+288h]; hObject
0x14003bdbd  mov     qword ptr [rsi+288h], 0
0x14003bdc8  lea     rax, [rcx+1]
0x14003bdcc  cmp     rax, 1
0x14003bdd0  jbe     short loc_14003BDDE
0x14003bdd2  call    cs:__imp_CloseHandle
0x14003bdd9  nop     dword ptr [rax+rax+00h]
0x14003bdde  mov     rcx, [rsp+58h]; this
0x14003bde3  lea     rax, aFailedToSetRep_0; "Failed to set reporting mode to FALSE"
0x14003bdea  mov     qword ptr [rsp+58h+var_30], rax; int
0x14003bdef  mov     dword ptr [rsp+58h+var_38], 0; char *
0x14003bdf7  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14003bdfe  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14003be05  mov     edx, 3ECh; void *
0x14003be0a  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003be0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::GetImpl(void)'::`2'::impl
0x14003be16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustnessFeature>::__private_IsEnabled(void)
0x14003be1b  test    al, al
0x14003be1d  jz      short loc_14003BE28
0x14003be1f  call    ?UtilIsWinRE@@YA_NXZ; UtilIsWinRE(void)
0x14003be24  test    al, al
0x14003be26  jnz     short loc_14003BE2D
0x14003be28  call    ?CheckAndDeleteMemoryDump@CKernelReport@@AEAAXXZ; CKernelReport::CheckAndDeleteMemoryDump(void)
0x14003be2d  mov     rcx, [rsp+58h+hKey]; hKey
0x14003be32  test    rcx, rcx
0x14003be35  jz      short loc_14003BE43
0x14003be37  call    cs:__imp_RegCloseKey
0x14003be3e  nop     dword ptr [rax+rax+00h]
0x14003be43  mov     eax, ebx
0x14003be45  mov     rbx, [rsp+58h+arg_18]
0x14003be4a  add     rsp, 40h
0x14003be4e  pop     r14
0x14003be50  pop     rdi
0x14003be51  pop     rsi
0x14003be52  retn
0x14005ff21  push    rbp
0x14005ff23  sub     rsp, 40h
0x14005ff27  mov     rbp, rdx
0x14005ff2a  mov     rax, [rbp+60h]
0x14005ff2e  mov     rcx, [rax+288h]; hObject
0x14005ff35  mov     qword ptr [rax+288h], 0
0x14005ff40  lea     rax, [rcx+1]
0x14005ff44  cmp     rax, 1
0x14005ff48  jbe     short loc_14005FF57
0x14005ff4a  call    cs:__imp_CloseHandle
0x14005ff51  nop     dword ptr [rax+rax+00h]
0x14005ff56  nop
0x14005ff57  mov     rcx, [rbp+58h]; this
0x14005ff5b  lea     rax, aFailedToSetRep_0; "Failed to set reporting mode to FALSE"
0x14005ff62  mov     qword ptr [rsp+48h+var_20], rax; int
0x14005ff67  mov     dword ptr [rsp+48h+var_28], 0; char *
0x14005ff6f  lea     r9, aCkernelreportR_1; "CKernelReport::ReportFromKQueue"
0x14005ff76  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x14005ff7d  mov     edx, 3ECh; void *
0x14005ff82  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14005ff87  nop
0x14005ff88  add     rsp, 40h
0x14005ff8c  pop     rbp
0x14005ff8d  retn
```
