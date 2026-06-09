# DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)

- ea: `0x1800126f8`
- end: `0x1800128f3`
- name: `?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z`
- size: `507`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f23c`

## callees

- `0x1800050b8`
- `0x1800126f8`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001272a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001277a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001272a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001277a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001288c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001289a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001288c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001289a`

## string_xrefs

- `0x180012723`: `\Microsoft\Windows\DeviceDirectoryClient`
- `0x180012762`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x18001287d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x18001274e`: `CPR(bszTaskFolder)`
- `0x18001279e`: `CPR(bszTaskName)`
- `0x1800127e1`: `CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))`
- `0x180012866`: `CHR(pRegisteredTask->put_Enabled(fEnabled ? ((VARIANT_BOOL)-1) : ((VARIANT_BOOL)0)))`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DdcTaskSchedulerWrapper::EnableTaskIfExists(
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
  char v16; // [rsp+20h] [rbp-18h]
  const char *v17; // [rsp+28h] [rbp-10h]
  __int64 v18; // [rsp+48h] [rbp+10h] BYREF
  __int64 v19; // [rsp+50h] [rbp+18h] BYREF

  v18 = 0;
  v19 = 0;
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
        135,
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
        138,
        "CPR(bszTaskName)");
    goto LABEL_19;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v6, &v18);
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_19;
    v17 = "CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))";
    v16 = -116;
    goto LABEL_18;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v18 + 104LL))(v18, v10, &v19);
  if ( v7 == -2147024894 )
  {
    v7 = 0;
    goto LABEL_19;
  }
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_19;
    v17 = "CHR(hr)";
    v16 = -104;
    goto LABEL_18;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 88LL))(v19, 0xFFFFFFFFLL);
  if ( v7 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v17 = "CHR(pRegisteredTask->put_Enabled(fEnabled ? ((VARIANT_BOOL)-1) : ((VARIANT_BOOL)0)))";
    v16 = -102;
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
  v13 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800126f8  mov     rax, rsp
0x1800126fb  mov     [rax+8], rbx
0x1800126ff  mov     [rax+20h], rsi
0x180012703  mov     [rax+18h], r8
0x180012707  mov     [rax+10h], rdx
0x18001270b  push    rdi
0x18001270c  sub     rsp, 30h
0x180012710  mov     rbx, rcx
0x180012713  mov     qword ptr [rax+10h], 0
0x18001271b  mov     qword ptr [rax+18h], 0
0x180012723  lea     rcx, psz; "\\Microsoft\\Windows\\DeviceDirectoryCl"...
0x18001272a  call    cs:__imp_SysAllocString
0x180012730  mov     rsi, rax
0x180012733  test    rax, rax
0x180012736  jnz     short loc_180012773
0x180012738  mov     r8d, 8007000Eh
0x18001273e  mov     ebx, r8d
0x180012741  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012748  jz      loc_1800128A1
0x18001274e  lea     rax, aCprBsztaskfold; "CPR(bszTaskFolder)"
0x180012755  mov     [rsp+38h+var_10], rax
0x18001275a  mov     dword ptr [rsp+38h+var_18], 187h
0x180012762  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012769  call    McTemplateU0dsqs_EventWriteTransfer
0x18001276e  jmp     loc_1800128A1
0x180012773  lea     rcx, aRegisterphoneu; "RegisterPhoneUpgrade"
0x18001277a  call    cs:__imp_SysAllocString
0x180012780  mov     rdi, rax
0x180012783  test    rax, rax
0x180012786  jnz     short loc_1800127B7
0x180012788  mov     r8d, 8007000Eh
0x18001278e  mov     ebx, r8d
0x180012791  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012798  jz      loc_180012889
0x18001279e  lea     rax, aCprBsztaskname; "CPR(bszTaskName)"
0x1800127a5  mov     [rsp+38h+var_10], rax
0x1800127aa  mov     dword ptr [rsp+38h+var_18], 18Ah
0x1800127b2  jmp     loc_18001287D
0x1800127b7  mov     rcx, [rbx]
0x1800127ba  mov     rax, [rcx]
0x1800127bd  lea     r8, [rsp+38h+arg_8]
0x1800127c2  mov     rdx, rsi
0x1800127c5  mov     rax, [rax+38h]
0x1800127c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127ce  mov     ebx, eax
0x1800127d0  test    eax, eax
0x1800127d2  jns     short loc_1800127FA
0x1800127d4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800127db  jz      loc_180012889
0x1800127e1  lea     rax, aChrMPtaskservi; "CHR(m_pTaskService->GetFolder(bszTaskFo"...
0x1800127e8  mov     [rsp+38h+var_10], rax
0x1800127ed  mov     dword ptr [rsp+38h+var_18], 18Ch
0x1800127f5  jmp     loc_18001287A
0x1800127fa  mov     rcx, [rsp+38h+arg_8]
0x1800127ff  mov     rax, [rcx]
0x180012802  lea     r8, [rsp+38h+arg_10]
0x180012807  mov     rdx, rdi
0x18001280a  mov     rax, [rax+68h]
0x18001280e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012813  mov     ebx, eax
0x180012815  cmp     eax, 80070002h
0x18001281a  jnz     short loc_180012820
0x18001281c  xor     ebx, ebx
0x18001281e  jmp     short loc_180012889
0x180012820  test    ebx, ebx
0x180012822  jns     short loc_180012843
0x180012824  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001282b  jz      short loc_180012889
0x18001282d  lea     rax, aChrHr; "CHR(hr)"
0x180012834  mov     [rsp+38h+var_10], rax
0x180012839  mov     dword ptr [rsp+38h+var_18], 198h
0x180012841  jmp     short loc_18001287A
0x180012843  mov     rcx, [rsp+38h+arg_10]
0x180012848  mov     rax, [rcx]
0x18001284b  or      edx, 0FFFFFFFFh
0x18001284e  mov     rax, [rax+58h]
0x180012852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012857  mov     ebx, eax
0x180012859  test    eax, eax
0x18001285b  jns     short loc_180012889
0x18001285d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012864  jz      short loc_180012889
0x180012866  lea     rax, aChrPregistered_0; "CHR(pRegisteredTask->put_Enabled(fEnabl"...
0x18001286d  mov     [rsp+38h+var_10], rax
0x180012872  mov     dword ptr [rsp+38h+var_18], 19Ah
0x18001287a  mov     r8d, ebx
0x18001287d  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012884  call    McTemplateU0dsqs_EventWriteTransfer
0x180012889  mov     rcx, rsi; bstrString
0x18001288c  call    cs:__imp_SysFreeString
0x180012892  test    rdi, rdi
0x180012895  jz      short loc_1800128A1
0x180012897  mov     rcx, rdi; bstrString
0x18001289a  call    cs:__imp_SysFreeString
0x1800128a0  nop
0x1800128a1  mov     rcx, [rsp+38h+arg_10]
0x1800128a6  test    rcx, rcx
0x1800128a9  jz      short loc_1800128C1
0x1800128ab  mov     [rsp+38h+arg_10], 0
0x1800128b4  mov     rax, [rcx]
0x1800128b7  mov     rax, [rax+10h]
0x1800128bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128c0  nop
0x1800128c1  mov     rcx, [rsp+38h+arg_8]
0x1800128c6  test    rcx, rcx
0x1800128c9  jz      short loc_1800128E1
0x1800128cb  mov     [rsp+38h+arg_8], 0
0x1800128d4  mov     rax, [rcx]
0x1800128d7  mov     rax, [rax+10h]
0x1800128db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128e0  nop
0x1800128e1  mov     eax, ebx
0x1800128e3  mov     rbx, [rsp+38h+arg_0]
0x1800128e8  mov     rsi, [rsp+38h+arg_18]
0x1800128ed  add     rsp, 30h
0x1800128f1  pop     rdi
0x1800128f2  retn
```
