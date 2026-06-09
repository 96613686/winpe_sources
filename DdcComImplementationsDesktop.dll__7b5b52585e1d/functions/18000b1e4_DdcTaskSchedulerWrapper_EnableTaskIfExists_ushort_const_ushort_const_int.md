# DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)

- ea: `0x18000b1e4`
- end: `0x18000b414`
- name: `?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z`
- size: `560`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003680`

## callees

- `0x1800026ac`
- `0x18000b1e4`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b259`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b296`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b259`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b296`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3b8`

## string_xrefs

- `0x18000b252`: `\Microsoft\Windows\DeviceDirectoryClient`
- `0x18000b241`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x18000b39b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x18000b22b`: `CPR(pwszTaskName)`
- `0x18000b27d`: `CPR(bszTaskFolder)`
- `0x18000b2ba`: `CPR(bszTaskName)`
- `0x18000b2fd`: `CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))`
- `0x18000b384`: `CHR(pRegisteredTask->put_Enabled(fEnabled ? ((VARIANT_BOOL)-1) : ((VARIANT_BOOL)0)))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::EnableTaskIfExists(
        DdcTaskSchedulerWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int v7; // ebx
  int v8; // ecx
  OLECHAR *v9; // rsi
  int v10; // edx
  int v11; // ecx
  OLECHAR *v12; // rdi
  __int64 v13; // rdx
  int v14; // ecx
  __int64 v15; // rcx
  __int64 v16; // rcx
  char v18; // [rsp+20h] [rbp-38h]
  const char *v19; // [rsp+28h] [rbp-30h]
  _QWORD v20[5]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v21; // [rsp+68h] [rbp+10h] BYREF

  v20[0] = 0;
  v21 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        132,
        (__int64)"CPR(pwszTaskName)");
    goto LABEL_25;
  }
  v9 = SysAllocString(L"\\Microsoft\\Windows\\DeviceDirectoryClient");
  if ( !v9 )
  {
    v7 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        (_DWORD)a2,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        135,
        (__int64)"CPR(bszTaskFolder)");
    goto LABEL_25;
  }
  v12 = SysAllocString(a3);
  if ( !v12 )
  {
    v7 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        v10,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        138,
        (__int64)"CPR(bszTaskName)");
    goto LABEL_23;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v9, v20);
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_23;
    v19 = "CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))";
    v18 = -116;
    goto LABEL_22;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(*(_QWORD *)v20[0] + 104LL))(v20[0], v12, &v21);
  if ( v7 == -2147024894 )
  {
    v7 = 0;
    goto LABEL_23;
  }
  if ( v7 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_23;
    v19 = "CHR(hr)";
    v18 = -104;
    goto LABEL_22;
  }
  LOWORD(v13) = -(a4 != 0);
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 88LL))(v21, v13);
  if ( v7 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v19 = "CHR(pRegisteredTask->put_Enabled(fEnabled ? ((VARIANT_BOOL)-1) : ((VARIANT_BOOL)0)))";
    v18 = -102;
LABEL_22:
    McTemplateU0dsqs_EventWriteTransfer(
      v14,
      v13,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
      v18,
      (__int64)v19);
  }
LABEL_23:
  SysFreeString(v9);
  if ( v12 )
    SysFreeString(v12);
LABEL_25:
  v15 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(v15, a2);
  }
  v16 = v20[0];
  if ( v20[0] )
  {
    v20[0] = 0;
    (*(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v16 + 16LL))(v16, a2);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b1e4  mov     r11, rsp
0x18000b1e7  mov     [r11+8], rbx
0x18000b1eb  mov     [r11+18h], rbp
0x18000b1ef  mov     [r11+10h], rdx
0x18000b1f3  push    rsi
0x18000b1f4  push    rdi
0x18000b1f5  push    r14
0x18000b1f7  sub     rsp, 40h
0x18000b1fb  mov     ebp, r9d
0x18000b1fe  mov     rbx, r8
0x18000b201  mov     r14, rcx
0x18000b204  mov     qword ptr [r11-28h], 0
0x18000b20c  mov     qword ptr [r11+10h], 0
0x18000b214  test    r8, r8
0x18000b217  jnz     short loc_18000B252
0x18000b219  mov     ebx, 80070057h
0x18000b21e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000b225  jz      loc_18000B3BF
0x18000b22b  lea     rax, aCprPwsztasknam; "CPR(pwszTaskName)"
0x18000b232  mov     [r11-30h], rax
0x18000b236  mov     dword ptr [rsp+58h+var_38], 184h
0x18000b23e  mov     r8d, ebx
0x18000b241  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000b248  call    McTemplateU0dsqs_EventWriteTransfer
0x18000b24d  jmp     loc_18000B3BF
0x18000b252  lea     rcx, psz; "\\Microsoft\\Windows\\DeviceDirectoryCl"...
0x18000b259  call    cs:__imp_SysAllocString
0x18000b25f  mov     rsi, rax
0x18000b262  test    rax, rax
0x18000b265  jnz     short loc_18000B293
0x18000b267  mov     r8d, 8007000Eh
0x18000b26d  mov     ebx, r8d
0x18000b270  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000b277  jz      loc_18000B3BF
0x18000b27d  lea     rax, aCprBsztaskfold; "CPR(bszTaskFolder)"
0x18000b284  mov     [rsp+58h+var_30], rax
0x18000b289  mov     dword ptr [rsp+58h+var_38], 187h
0x18000b291  jmp     short loc_18000B241
0x18000b293  mov     rcx, rbx; psz
0x18000b296  call    cs:__imp_SysAllocString
0x18000b29c  mov     rdi, rax
0x18000b29f  test    rax, rax
0x18000b2a2  jnz     short loc_18000B2D3
0x18000b2a4  mov     r8d, 8007000Eh
0x18000b2aa  mov     ebx, r8d
0x18000b2ad  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000b2b4  jz      loc_18000B3A7
0x18000b2ba  lea     rax, aCprBsztaskname; "CPR(bszTaskName)"
0x18000b2c1  mov     [rsp+58h+var_30], rax
0x18000b2c6  mov     dword ptr [rsp+58h+var_38], 18Ah
0x18000b2ce  jmp     loc_18000B39B
0x18000b2d3  mov     rcx, [r14]
0x18000b2d6  mov     rax, [rcx]
0x18000b2d9  lea     r8, [rsp+58h+var_28]
0x18000b2de  mov     rdx, rsi
0x18000b2e1  mov     rax, [rax+38h]
0x18000b2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ea  mov     ebx, eax
0x18000b2ec  test    eax, eax
0x18000b2ee  jns     short loc_18000B316
0x18000b2f0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000b2f7  jz      loc_18000B3A7
0x18000b2fd  lea     rax, aChrMPtaskservi; "CHR(m_pTaskService->GetFolder(bszTaskFo"...
0x18000b304  mov     [rsp+58h+var_30], rax
0x18000b309  mov     dword ptr [rsp+58h+var_38], 18Ch
0x18000b311  jmp     loc_18000B398
0x18000b316  mov     rcx, [rsp+58h+var_28]
0x18000b31b  mov     rax, [rcx]
0x18000b31e  lea     r8, [rsp+58h+arg_8]
0x18000b323  mov     rdx, rdi
0x18000b326  mov     rax, [rax+68h]
0x18000b32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b32f  mov     ebx, eax
0x18000b331  cmp     eax, 80070002h
0x18000b336  jnz     short loc_18000B33C
0x18000b338  xor     ebx, ebx
0x18000b33a  jmp     short loc_18000B3A7
0x18000b33c  test    ebx, ebx
0x18000b33e  jns     short loc_18000B35F
0x18000b340  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000b347  jz      short loc_18000B3A7
0x18000b349  lea     rax, aChrHr; "CHR(hr)"
0x18000b350  mov     [rsp+58h+var_30], rax
0x18000b355  mov     dword ptr [rsp+58h+var_38], 198h
0x18000b35d  jmp     short loc_18000B398
0x18000b35f  mov     rcx, [rsp+58h+arg_8]
0x18000b364  mov     rax, [rcx]
0x18000b367  neg     ebp
0x18000b369  sbb     dx, dx
0x18000b36c  mov     rax, [rax+58h]
0x18000b370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b375  mov     ebx, eax
0x18000b377  test    eax, eax
0x18000b379  jns     short loc_18000B3A7
0x18000b37b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000b382  jz      short loc_18000B3A7
0x18000b384  lea     rax, aChrPregistered; "CHR(pRegisteredTask->put_Enabled(fEnabl"...
0x18000b38b  mov     [rsp+58h+var_30], rax
0x18000b390  mov     dword ptr [rsp+58h+var_38], 19Ah
0x18000b398  mov     r8d, ebx
0x18000b39b  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000b3a2  call    McTemplateU0dsqs_EventWriteTransfer
0x18000b3a7  mov     rcx, rsi; bstrString
0x18000b3aa  call    cs:__imp_SysFreeString
0x18000b3b0  test    rdi, rdi
0x18000b3b3  jz      short loc_18000B3BF
0x18000b3b5  mov     rcx, rdi; bstrString
0x18000b3b8  call    cs:__imp_SysFreeString
0x18000b3be  nop
0x18000b3bf  mov     rcx, [rsp+58h+arg_8]
0x18000b3c4  test    rcx, rcx
0x18000b3c7  jz      short loc_18000B3DF
0x18000b3c9  mov     [rsp+58h+arg_8], 0
0x18000b3d2  mov     rax, [rcx]
0x18000b3d5  mov     rax, [rax+10h]
0x18000b3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3de  nop
0x18000b3df  mov     rcx, [rsp+58h+var_28]
0x18000b3e4  test    rcx, rcx
0x18000b3e7  jz      short loc_18000B3FF
0x18000b3e9  mov     [rsp+58h+var_28], 0
0x18000b3f2  mov     rax, [rcx]
0x18000b3f5  mov     rax, [rax+10h]
0x18000b3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3fe  nop
0x18000b3ff  mov     eax, ebx
0x18000b401  mov     rbx, [rsp+58h+arg_0]
0x18000b406  mov     rbp, [rsp+58h+arg_10]
0x18000b40b  add     rsp, 40h
0x18000b40f  pop     r14
0x18000b411  pop     rdi
0x18000b412  pop     rsi
0x18000b413  retn
```
