# DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)

- ea: `0x180012380`
- end: `0x180012531`
- name: `?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z`
- size: `433`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012178`
- `0x18001227c`
- `0x180012538`
- `0x180012c94`
- `0x180013004`
- `0x1800132e4`
- `0x18001364c`

## callees

- `0x1800050b8`
- `0x180012380`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800123e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180012420`
- `OLEAUT32!__imp_SysAllocString` at `0x1800123e3`
- `OLEAUT32!__imp_SysAllocString` at `0x180012420`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124fe`

## string_xrefs

- `0x1800123dc`: `\Microsoft\Windows\DeviceDirectoryClient`
- `0x1800123cb`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800124e1`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800123b4`: `CPR(pwszTaskName)`
- `0x180012407`: `CPR(bszTaskFolder)`
- `0x180012444`: `CPR(bszTaskName)`
- `0x180012483`: `CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcTaskSchedulerWrapper::DeleteTaskIfExists(
        DdcTaskSchedulerWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v5; // ebx
  int v6; // ecx
  OLECHAR *v7; // rsi
  int v8; // edx
  int v9; // ecx
  OLECHAR *v10; // rdi
  int v11; // edx
  int v12; // ecx
  __int64 v13; // rcx
  char v15; // [rsp+20h] [rbp-38h]
  const char *v16; // [rsp+28h] [rbp-30h]
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)this,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        183,
        "CPR(pwszTaskName)");
    goto LABEL_22;
  }
  v7 = SysAllocString(L"\\Microsoft\\Windows\\DeviceDirectoryClient");
  if ( !v7 )
  {
    v5 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        (_DWORD)a2,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        186,
        "CPR(bszTaskFolder)");
    goto LABEL_22;
  }
  v10 = SysAllocString(a3);
  if ( !v10 )
  {
    v5 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        189,
        "CPR(bszTaskName)");
    goto LABEL_20;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, v7, &v17);
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_20;
    v16 = "CHR(m_pTaskService->GetFolder(bszTaskFolder, pTaskFolder.GetAddressOf()))";
    v15 = -65;
    goto LABEL_19;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v17 + 120LL))(v17, v10, 0);
  if ( v5 == -2147024894 )
  {
    v5 = 0;
    goto LABEL_20;
  }
  if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v16 = "CHR(hr)";
    v15 = -53;
LABEL_19:
    McTemplateU0dsqs_EventWriteTransfer(
      v12,
      v11,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
      v15,
      v16);
  }
LABEL_20:
  SysFreeString(v7);
  if ( v10 )
    SysFreeString(v10);
LABEL_22:
  v13 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v13 + 16LL))(v13, a2);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012380  mov     [rsp+arg_8], rdx
0x180012385  push    rbx
0x180012386  push    rsi
0x180012387  push    rdi
0x180012388  push    r14
0x18001238a  sub     rsp, 38h
0x18001238e  mov     rbx, r8
0x180012391  mov     r14, rcx
0x180012394  mov     [rsp+58h+arg_8], 0
0x18001239d  test    r8, r8
0x1800123a0  jnz     short loc_1800123DC
0x1800123a2  mov     ebx, 80070057h
0x1800123a7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800123ae  jz      loc_180012505
0x1800123b4  lea     rax, aCprPwsztasknam; "CPR(pwszTaskName)"
0x1800123bb  mov     [rsp+58h+var_30], rax
0x1800123c0  mov     dword ptr [rsp+58h+var_38], 1B7h
0x1800123c8  mov     r8d, ebx
0x1800123cb  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800123d2  call    McTemplateU0dsqs_EventWriteTransfer
0x1800123d7  jmp     loc_180012505
0x1800123dc  lea     rcx, psz; "\\Microsoft\\Windows\\DeviceDirectoryCl"...
0x1800123e3  call    cs:__imp_SysAllocString
0x1800123e9  mov     rsi, rax
0x1800123ec  test    rax, rax
0x1800123ef  jnz     short loc_18001241D
0x1800123f1  mov     r8d, 8007000Eh
0x1800123f7  mov     ebx, r8d
0x1800123fa  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012401  jz      loc_180012505
0x180012407  lea     rax, aCprBsztaskfold; "CPR(bszTaskFolder)"
0x18001240e  mov     [rsp+58h+var_30], rax
0x180012413  mov     dword ptr [rsp+58h+var_38], 1BAh
0x18001241b  jmp     short loc_1800123CB
0x18001241d  mov     rcx, rbx; psz
0x180012420  call    cs:__imp_SysAllocString
0x180012426  mov     rdi, rax
0x180012429  test    rax, rax
0x18001242c  jnz     short loc_18001245D
0x18001242e  mov     r8d, 8007000Eh
0x180012434  mov     ebx, r8d
0x180012437  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001243e  jz      loc_1800124ED
0x180012444  lea     rax, aCprBsztaskname; "CPR(bszTaskName)"
0x18001244b  mov     [rsp+58h+var_30], rax
0x180012450  mov     dword ptr [rsp+58h+var_38], 1BDh
0x180012458  jmp     loc_1800124E1
0x18001245d  mov     rcx, [r14]
0x180012460  mov     rax, [rcx]
0x180012463  lea     r8, [rsp+58h+arg_8]
0x180012468  mov     rdx, rsi
0x18001246b  mov     rax, [rax+38h]
0x18001246f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012474  mov     ebx, eax
0x180012476  test    eax, eax
0x180012478  jns     short loc_180012499
0x18001247a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012481  jz      short loc_1800124ED
0x180012483  lea     rax, aChrMPtaskservi; "CHR(m_pTaskService->GetFolder(bszTaskFo"...
0x18001248a  mov     [rsp+58h+var_30], rax
0x18001248f  mov     dword ptr [rsp+58h+var_38], 1BFh
0x180012497  jmp     short loc_1800124DE
0x180012499  mov     rcx, [rsp+58h+arg_8]
0x18001249e  mov     rax, [rcx]
0x1800124a1  xor     r8d, r8d
0x1800124a4  mov     rdx, rdi
0x1800124a7  mov     rax, [rax+78h]
0x1800124ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124b0  mov     ebx, eax
0x1800124b2  cmp     eax, 80070002h
0x1800124b7  jnz     short loc_1800124BD
0x1800124b9  xor     ebx, ebx
0x1800124bb  jmp     short loc_1800124ED
0x1800124bd  test    ebx, ebx
0x1800124bf  jns     short loc_1800124ED
0x1800124c1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800124c8  jz      short loc_1800124ED
0x1800124ca  lea     rax, aChrHr; "CHR(hr)"
0x1800124d1  mov     [rsp+58h+var_30], rax
0x1800124d6  mov     dword ptr [rsp+58h+var_38], 1CBh
0x1800124de  mov     r8d, ebx
0x1800124e1  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800124e8  call    McTemplateU0dsqs_EventWriteTransfer
0x1800124ed  mov     rcx, rsi; bstrString
0x1800124f0  call    cs:__imp_SysFreeString
0x1800124f6  test    rdi, rdi
0x1800124f9  jz      short loc_180012505
0x1800124fb  mov     rcx, rdi; bstrString
0x1800124fe  call    cs:__imp_SysFreeString
0x180012504  nop
0x180012505  mov     rcx, [rsp+58h+arg_8]
0x18001250a  test    rcx, rcx
0x18001250d  jz      short loc_180012525
0x18001250f  mov     [rsp+58h+arg_8], 0
0x180012518  mov     rax, [rcx]
0x18001251b  mov     rax, [rax+10h]
0x18001251f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012524  nop
0x180012525  mov     eax, ebx
0x180012527  add     rsp, 38h
0x18001252b  pop     r14
0x18001252d  pop     rdi
0x18001252e  pop     rsi
0x18001252f  pop     rbx
0x180012530  retn
```
