# DdcTaskSchedulerWrapper::RunTaskIfExists(ushort const *,ushort const *)

- ea: `0x180012a60`
- end: `0x180012c8e`
- name: `?RunTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0@Z`
- size: `558`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f23c`

## callees

- `0x1800050b8`
- `0x180012a60`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180012aaa`
- `OLEAUT32!__imp_SysAllocString` at `0x180012afa`
- `OLEAUT32!__imp_SysAllocString` at `0x180012aaa`
- `OLEAUT32!__imp_SysAllocString` at `0x180012afa`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c2f`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c21`
- `OLEAUT32!__imp_SysFreeString` at `0x180012c2f`
- `OLEAUT32!__imp_VariantInit` at `0x180012a9d`
- `OLEAUT32!__imp_VariantInit` at `0x180012a9d`
- `OLEAUT32!__imp_VariantClear` at `0x180012c39`
- `OLEAUT32!__imp_VariantClear` at `0x180012c39`

## string_xrefs

- `0x180012aa3`: `\Microsoft\Windows\DeviceDirectoryClient`
- `0x180012ae2`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x180012c12`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x180012ace`: `CPR(bszTaskFolder)`
- `0x180012b1e`: `CPR(bszTaskName)`
- `0x180012b60`: `CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))`
- `0x180012bfb`: `CHR(pRegisteredTask->Run(vtEmpty, 0))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcTaskSchedulerWrapper::RunTaskIfExists(
        DdcTaskSchedulerWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v4; // edx
  int v5; // ecx
  OLECHAR *v6; // rsi
  int v7; // ebx
  int v8; // edx
  int v9; // ecx
  OLECHAR *v10; // rdi
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char v16; // [rsp+20h] [rbp-50h]
  const char *v17; // [rsp+28h] [rbp-48h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG v19; // [rsp+50h] [rbp-20h] BYREF
  __int64 v20; // [rsp+98h] [rbp+28h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+30h] BYREF

  v20 = 0;
  v21 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = SysAllocString(L"\\Microsoft\\Windows\\DeviceDirectoryClient");
  if ( !v6 )
  {
    v7 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        82,
        "CPR(bszTaskFolder)");
    goto LABEL_21;
  }
  v10 = SysAllocString(L"RegisterPhoneUpgrade");
  if ( !v10 )
  {
    v7 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        85,
        "CPR(bszTaskName)");
    goto LABEL_19;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v6, &v20);
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_19;
    v17 = "CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))";
    v16 = 87;
    goto LABEL_18;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v20 + 104LL))(v20, v10, &v21);
  if ( v7 == -2147024894 )
  {
    v7 = 1;
    goto LABEL_19;
  }
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_19;
    v17 = "CHR(hr)";
    v16 = 97;
    goto LABEL_18;
  }
  v19 = pvarg;
  v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v21 + 96LL))(v21, &v19, 0);
  if ( v7 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v17 = "CHR(pRegisteredTask->Run(vtEmpty, 0))";
    v16 = 99;
LABEL_18:
    McTemplateU0dsqs_EventWriteTransfer(
      v12,
      v11,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
      v16,
      v17);
  }
LABEL_19:
  SysFreeString(v6);
  if ( v10 )
    SysFreeString(v10);
LABEL_21:
  VariantClear(&pvarg);
  v13 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180012a60  mov     [rsp-18h+arg_0], rbx
0x180012a65  mov     [rsp-18h+arg_10], r8
0x180012a6a  mov     [rsp-18h+arg_8], rdx
0x180012a6f  push    rbp
0x180012a70  push    rsi
0x180012a71  push    rdi
0x180012a72  mov     rbp, rsp
0x180012a75  sub     rsp, 70h
0x180012a79  mov     rbx, rcx
0x180012a7c  mov     [rbp+arg_8], 0
0x180012a84  mov     [rbp+arg_10], 0
0x180012a8c  xorps   xmm0, xmm0
0x180012a8f  xor     eax, eax
0x180012a91  movups  xmmword ptr [rbp+pvarg], xmm0
0x180012a95  mov     qword ptr [rbp+pvarg+10h], rax
0x180012a99  lea     rcx, [rbp+pvarg]; pvarg
0x180012a9d  call    cs:__imp_VariantInit
0x180012aa3  lea     rcx, psz; "\\Microsoft\\Windows\\DeviceDirectoryCl"...
0x180012aaa  call    cs:__imp_SysAllocString
0x180012ab0  mov     rsi, rax
0x180012ab3  test    rax, rax
0x180012ab6  jnz     short loc_180012AF3
0x180012ab8  mov     r8d, 8007000Eh
0x180012abe  mov     ebx, r8d
0x180012ac1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012ac8  jz      loc_180012C35
0x180012ace  lea     rax, aCprBsztaskfold; "CPR(bszTaskFolder)"
0x180012ad5  mov     [rsp+70h+var_48], rax
0x180012ada  mov     dword ptr [rsp+70h+var_50], 152h
0x180012ae2  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012ae9  call    McTemplateU0dsqs_EventWriteTransfer
0x180012aee  jmp     loc_180012C35
0x180012af3  lea     rcx, aRegisterphoneu; "RegisterPhoneUpgrade"
0x180012afa  call    cs:__imp_SysAllocString
0x180012b00  mov     rdi, rax
0x180012b03  test    rax, rax
0x180012b06  jnz     short loc_180012B37
0x180012b08  mov     r8d, 8007000Eh
0x180012b0e  mov     ebx, r8d
0x180012b11  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012b18  jz      loc_180012C1E
0x180012b1e  lea     rax, aCprBsztaskname; "CPR(bszTaskName)"
0x180012b25  mov     [rsp+70h+var_48], rax
0x180012b2a  mov     dword ptr [rsp+70h+var_50], 155h
0x180012b32  jmp     loc_180012C12
0x180012b37  mov     rcx, [rbx]
0x180012b3a  mov     rax, [rcx]
0x180012b3d  lea     r8, [rbp+arg_8]
0x180012b41  mov     rdx, rsi
0x180012b44  mov     rax, [rax+38h]
0x180012b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b4d  mov     ebx, eax
0x180012b4f  test    eax, eax
0x180012b51  jns     short loc_180012B79
0x180012b53  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012b5a  jz      loc_180012C1E
0x180012b60  lea     rax, aChrMPtaskservi; "CHR(m_pTaskService->GetFolder(bszTaskFo"...
0x180012b67  mov     [rsp+70h+var_48], rax
0x180012b6c  mov     dword ptr [rsp+70h+var_50], 157h
0x180012b74  jmp     loc_180012C0F
0x180012b79  mov     rcx, [rbp+arg_8]
0x180012b7d  mov     rax, [rcx]
0x180012b80  lea     r8, [rbp+arg_10]
0x180012b84  mov     rdx, rdi
0x180012b87  mov     rax, [rax+68h]
0x180012b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b90  mov     ebx, eax
0x180012b92  cmp     eax, 80070002h
0x180012b97  jnz     short loc_180012BA0
0x180012b99  mov     ebx, 1
0x180012b9e  jmp     short loc_180012C1E
0x180012ba0  test    ebx, ebx
0x180012ba2  jns     short loc_180012BC3
0x180012ba4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012bab  jz      short loc_180012C1E
0x180012bad  lea     rax, aChrHr; "CHR(hr)"
0x180012bb4  mov     [rsp+70h+var_48], rax
0x180012bb9  mov     dword ptr [rsp+70h+var_50], 161h
0x180012bc1  jmp     short loc_180012C0F
0x180012bc3  mov     rcx, [rbp+arg_10]
0x180012bc7  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180012bcb  movaps  [rbp+var_20], xmm0
0x180012bcf  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180012bd4  movsd   [rbp+var_10], xmm1
0x180012bd9  mov     rax, [rcx]
0x180012bdc  xor     r8d, r8d
0x180012bdf  lea     rdx, [rbp+var_20]
0x180012be3  mov     rax, [rax+60h]
0x180012be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bec  mov     ebx, eax
0x180012bee  test    eax, eax
0x180012bf0  jns     short loc_180012C1E
0x180012bf2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012bf9  jz      short loc_180012C1E
0x180012bfb  lea     rax, aChrPregistered; "CHR(pRegisteredTask->Run(vtEmpty, 0))"
0x180012c02  mov     [rsp+70h+var_48], rax
0x180012c07  mov     dword ptr [rsp+70h+var_50], 163h
0x180012c0f  mov     r8d, ebx
0x180012c12  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012c19  call    McTemplateU0dsqs_EventWriteTransfer
0x180012c1e  mov     rcx, rsi; bstrString
0x180012c21  call    cs:__imp_SysFreeString
0x180012c27  test    rdi, rdi
0x180012c2a  jz      short loc_180012C35
0x180012c2c  mov     rcx, rdi; bstrString
0x180012c2f  call    cs:__imp_SysFreeString
0x180012c35  lea     rcx, [rbp+pvarg]; pvarg
0x180012c39  call    cs:__imp_VariantClear
0x180012c3f  nop
0x180012c40  mov     rcx, [rbp+arg_10]
0x180012c44  test    rcx, rcx
0x180012c47  jz      short loc_180012C5E
0x180012c49  mov     [rbp+arg_10], 0
0x180012c51  mov     rax, [rcx]
0x180012c54  mov     rax, [rax+10h]
0x180012c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c5d  nop
0x180012c5e  mov     rcx, [rbp+arg_8]
0x180012c62  test    rcx, rcx
0x180012c65  jz      short loc_180012C7C
0x180012c67  mov     [rbp+arg_8], 0
0x180012c6f  mov     rax, [rcx]
0x180012c72  mov     rax, [rax+10h]
0x180012c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c7b  nop
0x180012c7c  mov     eax, ebx
0x180012c7e  mov     rbx, [rsp+70h+arg_0]
0x180012c86  add     rsp, 70h
0x180012c8a  pop     rdi
0x180012c8b  pop     rsi
0x180012c8c  pop     rbp
0x180012c8d  retn
```
