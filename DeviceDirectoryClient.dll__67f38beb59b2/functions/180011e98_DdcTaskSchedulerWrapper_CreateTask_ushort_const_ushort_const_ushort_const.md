# DdcTaskSchedulerWrapper::CreateTask(ushort const *,ushort const *,ushort const *)

- ea: `0x180011e98`
- end: `0x180012171`
- name: `?CreateTask@DdcTaskSchedulerWrapper@@AEAAJPEBG00@Z`
- size: `729`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012c94`
- `0x180013004`
- `0x1800132e4`
- `0x18001364c`

## callees

- `0x1800050b8`
- `0x180011e98`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180011f51`
- `OLEAUT32!__imp_SysAllocString` at `0x180011f91`
- `OLEAUT32!__imp_SysAllocString` at `0x180011fd3`
- `OLEAUT32!__imp_SysAllocString` at `0x180011f51`
- `OLEAUT32!__imp_SysAllocString` at `0x180011f91`
- `OLEAUT32!__imp_SysAllocString` at `0x180011fd3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800120f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180012104`
- `OLEAUT32!__imp_SysFreeString` at `0x180012112`
- `OLEAUT32!__imp_SysFreeString` at `0x1800120f6`
- `OLEAUT32!__imp_SysFreeString` at `0x180012104`
- `OLEAUT32!__imp_SysFreeString` at `0x180012112`
- `OLEAUT32!__imp_VariantInit` at `0x180011ed3`
- `OLEAUT32!__imp_VariantInit` at `0x180011ed3`
- `OLEAUT32!__imp_VariantClear` at `0x18001211c`
- `OLEAUT32!__imp_VariantClear` at `0x18001211c`

## string_xrefs

- `0x180011f4a`: `\Microsoft\Windows\DeviceDirectoryClient`
- `0x180011f08`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800120e7`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x180011ef4`: `CPR(pwszTaskName)`
- `0x180011f75`: `CPR(bszTaskFolder)`
- `0x180011fb7`: `CPR(bszTaskName)`
- `0x180012039`: `CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))`
- `0x180011f34`: `CPR(pwszXml)`
- `0x180011ff7`: `CPR(bszTaskXml)`
- `0x1800120d0`: `CHR(pTaskFolder->RegisterTask( bszTaskName, bszTaskXml, TASK_CREATE_OR_UPDATE, vtEmpty, vtEmpty, TASK_LOGON_SERVICE_ACCOUNT, vtEmpty, pCreatedTask.GetAddressOf() ))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::CreateTask(
        DdcTaskSchedulerWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v7; // edx
  int v8; // ecx
  int v9; // ebx
  int v10; // edx
  int v11; // ecx
  OLECHAR *v12; // r14
  int v13; // edx
  int v14; // ecx
  OLECHAR *v15; // rsi
  OLECHAR *v16; // rdi
  int v17; // edx
  int v18; // ecx
  int v19; // edx
  int v20; // ecx
  __int64 v21; // rcx
  __int64 v22; // rcx
  char v24; // [rsp+20h] [rbp-89h]
  const char *v25; // [rsp+28h] [rbp-81h]
  __int64 v26; // [rsp+50h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-51h] BYREF
  VARIANTARG v28; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v29; // [rsp+90h] [rbp-19h] BYREF
  VARIANTARG v30; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v31; // [rsp+118h] [rbp+6Fh] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v31 = 0;
  v26 = 0;
  VariantInit(&pvarg);
  if ( !a3 )
  {
    v9 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        240,
        (__int64)"CPR(pwszTaskName)");
    goto LABEL_28;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        v7,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        241,
        (__int64)"CPR(pwszXml)");
    goto LABEL_28;
  }
  v12 = SysAllocString(L"\\Microsoft\\Windows\\DeviceDirectoryClient");
  if ( !v12 )
  {
    v9 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        244,
        (__int64)"CPR(bszTaskFolder)");
    goto LABEL_28;
  }
  v15 = SysAllocString(a3);
  if ( !v15 )
  {
    v16 = 0;
    v9 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v14,
        v13,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        247,
        (__int64)"CPR(bszTaskName)");
    goto LABEL_24;
  }
  v16 = SysAllocString(a4);
  if ( !v16 )
  {
    v9 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v18,
        v17,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        250,
        (__int64)"CPR(bszTaskXml)");
    goto LABEL_24;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v12, &v31);
  if ( v9 >= 0 )
  {
    v28 = pvarg;
    v29 = pvarg;
    v30 = pvarg;
    v9 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, OLECHAR *, __int64, VARIANTARG *, VARIANTARG *, int, VARIANTARG *, __int64 *))(*(_QWORD *)v31 + 128LL))(
           v31,
           v15,
           v16,
           6,
           &v30,
           &v29,
           5,
           &v28,
           &v26);
    if ( v9 >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_24;
    v25 = "CHR(pTaskFolder->RegisterTask( bszTaskName, bszTaskXml, TASK_CREATE_OR_UPDATE, vtEmpty, vtEmpty, TASK_LOGON_SE"
          "RVICE_ACCOUNT, vtEmpty, pCreatedTask.GetAddressOf() ))";
    v24 = 7;
    goto LABEL_23;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v25 = "CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))";
    v24 = -4;
LABEL_23:
    McTemplateU0dsqs_EventWriteTransfer(
      v20,
      v19,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
      v24,
      (__int64)v25);
  }
LABEL_24:
  SysFreeString(v12);
  if ( v15 )
    SysFreeString(v15);
  if ( v16 )
    SysFreeString(v16);
LABEL_28:
  VariantClear(&pvarg);
  v21 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011e98  mov     [rsp-8+arg_8], rdx
0x180011e9d  push    rbp
0x180011e9e  push    rbx
0x180011e9f  push    rsi
0x180011ea0  push    rdi
0x180011ea1  push    r14
0x180011ea3  push    r15
0x180011ea5  lea     rbp, [rsp-2Fh]
0x180011eaa  sub     rsp, 0D8h
0x180011eb1  mov     rbx, r9
0x180011eb4  mov     rdi, r8
0x180011eb7  mov     r15, rcx
0x180011eba  xorps   xmm0, xmm0
0x180011ebd  xor     eax, eax
0x180011ebf  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180011ec3  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180011ec7  mov     [rbp+57h+arg_8], rax
0x180011ecb  mov     [rbp+57h+var_B0], rax
0x180011ecf  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180011ed3  call    cs:__imp_VariantInit
0x180011ed9  test    rdi, rdi
0x180011edc  jnz     short loc_180011F19
0x180011ede  mov     r8d, 80070057h
0x180011ee4  mov     ebx, r8d
0x180011ee7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011eee  jz      loc_180012118
0x180011ef4  lea     rax, aCprPwsztasknam; "CPR(pwszTaskName)"
0x180011efb  mov     [rsp+100h+var_D8], rax
0x180011f00  mov     dword ptr [rsp+100h+var_E0], 1F0h
0x180011f08  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180011f0f  call    McTemplateU0dsqs_EventWriteTransfer
0x180011f14  jmp     loc_180012118
0x180011f19  test    rbx, rbx
0x180011f1c  jnz     short loc_180011F4A
0x180011f1e  mov     r8d, 80070057h
0x180011f24  mov     ebx, r8d
0x180011f27  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011f2e  jz      loc_180012118
0x180011f34  lea     rax, aCprPwszxml; "CPR(pwszXml)"
0x180011f3b  mov     [rsp+100h+var_D8], rax
0x180011f40  mov     dword ptr [rsp+100h+var_E0], 1F1h
0x180011f48  jmp     short loc_180011F08
0x180011f4a  lea     rcx, psz; "\\Microsoft\\Windows\\DeviceDirectoryCl"...
0x180011f51  call    cs:__imp_SysAllocString
0x180011f57  mov     r14, rax
0x180011f5a  test    rax, rax
0x180011f5d  jnz     short loc_180011F8E
0x180011f5f  mov     r8d, 8007000Eh
0x180011f65  mov     ebx, r8d
0x180011f68  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011f6f  jz      loc_180012118
0x180011f75  lea     rax, aCprBsztaskfold; "CPR(bszTaskFolder)"
0x180011f7c  mov     [rsp+100h+var_D8], rax
0x180011f81  mov     dword ptr [rsp+100h+var_E0], 1F4h
0x180011f89  jmp     loc_180011F08
0x180011f8e  mov     rcx, rdi; psz
0x180011f91  call    cs:__imp_SysAllocString
0x180011f97  mov     rsi, rax
0x180011f9a  test    rax, rax
0x180011f9d  jnz     short loc_180011FD0
0x180011f9f  xor     edi, edi
0x180011fa1  mov     r8d, 8007000Eh
0x180011fa7  mov     ebx, r8d
0x180011faa  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011fb1  jz      loc_1800120F3
0x180011fb7  lea     rax, aCprBsztaskname; "CPR(bszTaskName)"
0x180011fbe  mov     [rsp+100h+var_D8], rax
0x180011fc3  mov     dword ptr [rsp+100h+var_E0], 1F7h
0x180011fcb  jmp     loc_1800120E7
0x180011fd0  mov     rcx, rbx; psz
0x180011fd3  call    cs:__imp_SysAllocString
0x180011fd9  mov     rdi, rax
0x180011fdc  test    rax, rax
0x180011fdf  jnz     short loc_180012010
0x180011fe1  mov     r8d, 8007000Eh
0x180011fe7  mov     ebx, r8d
0x180011fea  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011ff1  jz      loc_1800120F3
0x180011ff7  lea     rax, aCprBsztaskxml; "CPR(bszTaskXml)"
0x180011ffe  mov     [rsp+100h+var_D8], rax
0x180012003  mov     dword ptr [rsp+100h+var_E0], 1FAh
0x18001200b  jmp     loc_1800120E7
0x180012010  mov     rcx, [r15]
0x180012013  mov     rax, [rcx]
0x180012016  lea     r8, [rbp+57h+arg_8]
0x18001201a  mov     rdx, r14
0x18001201d  mov     rax, [rax+38h]
0x180012021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012026  mov     ebx, eax
0x180012028  test    eax, eax
0x18001202a  jns     short loc_180012052
0x18001202c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012033  jz      loc_1800120F3
0x180012039  lea     rax, aChrMPtaskservi; "CHR(m_pTaskService->GetFolder(bszTaskFo"...
0x180012040  mov     [rsp+100h+var_D8], rax
0x180012045  mov     dword ptr [rsp+100h+var_E0], 1FCh
0x18001204d  jmp     loc_1800120E4
0x180012052  mov     rcx, [rbp+57h+arg_8]
0x180012056  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18001205a  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18001205f  movaps  [rbp+57h+var_90], xmm1
0x180012063  movsd   [rbp+57h+var_80], xmm0
0x180012068  movaps  [rbp+57h+var_70], xmm1
0x18001206c  movsd   [rbp+57h+var_60], xmm0
0x180012071  movaps  [rbp+57h+var_50], xmm1
0x180012075  movsd   [rbp+57h+var_40], xmm0
0x18001207a  mov     rax, [rcx]
0x18001207d  lea     rdx, [rbp+57h+var_B0]
0x180012081  mov     [rsp+100h+var_C0], rdx
0x180012086  lea     rdx, [rbp+57h+var_90]
0x18001208a  mov     [rsp+100h+var_C8], rdx
0x18001208f  mov     [rsp+100h+var_D0], 5
0x180012097  lea     rdx, [rbp+57h+var_70]
0x18001209b  mov     [rsp+100h+var_D8], rdx
0x1800120a0  lea     rdx, [rbp+57h+var_50]
0x1800120a4  mov     [rsp+100h+var_E0], rdx
0x1800120a9  mov     r9d, 6
0x1800120af  mov     r8, rdi
0x1800120b2  mov     rdx, rsi
0x1800120b5  mov     rax, [rax+80h]
0x1800120bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c1  mov     ebx, eax
0x1800120c3  test    eax, eax
0x1800120c5  jns     short loc_1800120F3
0x1800120c7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800120ce  jz      short loc_1800120F3
0x1800120d0  lea     rax, aChrPtaskfolder; "CHR(pTaskFolder->RegisterTask( bszTaskN"...
0x1800120d7  mov     [rsp+100h+var_D8], rax
0x1800120dc  mov     dword ptr [rsp+100h+var_E0], 207h
0x1800120e4  mov     r8d, ebx
0x1800120e7  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800120ee  call    McTemplateU0dsqs_EventWriteTransfer
0x1800120f3  mov     rcx, r14; bstrString
0x1800120f6  call    cs:__imp_SysFreeString
0x1800120fc  test    rsi, rsi
0x1800120ff  jz      short loc_18001210A
0x180012101  mov     rcx, rsi; bstrString
0x180012104  call    cs:__imp_SysFreeString
0x18001210a  test    rdi, rdi
0x18001210d  jz      short loc_180012118
0x18001210f  mov     rcx, rdi; bstrString
0x180012112  call    cs:__imp_SysFreeString
0x180012118  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18001211c  call    cs:__imp_VariantClear
0x180012122  nop
0x180012123  mov     rcx, [rbp+57h+var_B0]
0x180012127  test    rcx, rcx
0x18001212a  jz      short loc_180012141
0x18001212c  mov     [rbp+57h+var_B0], 0
0x180012134  mov     rax, [rcx]
0x180012137  mov     rax, [rax+10h]
0x18001213b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012140  nop
0x180012141  mov     rcx, [rbp+57h+arg_8]
0x180012145  test    rcx, rcx
0x180012148  jz      short loc_18001215F
0x18001214a  mov     [rbp+57h+arg_8], 0
0x180012152  mov     rax, [rcx]
0x180012155  mov     rax, [rax+10h]
0x180012159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001215e  nop
0x18001215f  mov     eax, ebx
0x180012161  add     rsp, 0D8h
0x180012168  pop     r15
0x18001216a  pop     r14
0x18001216c  pop     rdi
0x18001216d  pop     rsi
0x18001216e  pop     rbx
0x18001216f  pop     rbp
0x180012170  retn
```
