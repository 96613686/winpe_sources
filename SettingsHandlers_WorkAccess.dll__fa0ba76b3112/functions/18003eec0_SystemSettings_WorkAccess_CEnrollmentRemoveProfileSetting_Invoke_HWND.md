# SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::Invoke(HWND__ *)

- ea: `0x18003eec0`
- end: `0x18003f057`
- name: `?Invoke@CEnrollmentRemoveProfileSetting@WorkAccess@SystemSettings@@MEAAJPEAUHWND__@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting *this, HWND)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180009e68`
- `0x1800201b0`
- `0x180027a58`
- `0x18003eec0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ef7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ef7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ef65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ef65`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003f028`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003f028`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003efe0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003efe0`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003eeea`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18003eeea`

## string_xrefs

- `0x18003ef01`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003f00a`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::Invoke(
        SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting *this,
        HWND a2)
{
  int PolicyInt; // eax
  unsigned int v4; // ebx
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v8; // rbp
  __int64 v9; // rdx
  const unsigned __int16 *v10; // r9
  int v11; // eax
  __int64 v12; // r9
  struct _TP_WORK *ThreadpoolWork; // rax
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v16; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp+20h] BYREF

  v16 = 0;
  PolicyInt = PolicyManager_GetPolicyInt(L"Experience", L"AllowManualMDMUnenrollment", &v16);
  v4 = PolicyInt;
  if ( PolicyInt < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)PolicyInt,
      v14);
    return v4;
  }
  if ( v16 == 1 && ((1LL << *((_DWORD *)this + 62)) & 0x8000001) != 0 )
  {
    v17 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 216);
    v6 = 2LL * *((_QWORD *)this + 28) + 2;
    ProcessHeap = GetProcessHeap();
    v8 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v6);
    CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v17);
    v17 = v8;
    if ( !v8 )
    {
      v9 = 602;
LABEL_12:
      v4 = -2147467259;
      v12 = 2147500037LL;
      goto LABEL_13;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 216);
    v11 = StringCchCopyW(v8, *((_QWORD *)this + 28) + 1LL, v10);
    v4 = v11;
    if ( v11 < 0 )
    {
      v12 = (unsigned int)v11;
      v9 = 603;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)v12,
        v14);
      CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v17);
      return v4;
    }
    ThreadpoolWork = CreateThreadpoolWork(
                       (PTP_WORK_CALLBACK)SystemSettings::WorkAccess::CEnrollmentRemoveProfileSetting::s_DeviceManagementWorker,
                       v8,
                       0);
    *((_QWORD *)this + 30) = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      v9 = 605;
      goto LABEL_12;
    }
    SubmitThreadpoolWork(ThreadpoolWork);
    v17 = 0;
    CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18003eec0  mov     [rsp+arg_0], rbx
0x18003eec5  push    rbp
0x18003eec6  push    rsi
0x18003eec7  push    rdi; int
0x18003eec8  sub     rsp, 20h
0x18003eecc  mov     rdi, rcx
0x18003eecf  mov     [rsp+38h+arg_10], 0
0x18003eed7  lea     rcx, aExperience; "Experience"
0x18003eede  lea     r8, [rsp+38h+arg_10]
0x18003eee3  lea     rdx, aAllowmanualmdm; "AllowManualMDMUnenrollment"
0x18003eeea  call    cs:__imp_PolicyManager_GetPolicyInt
0x18003eef1  nop     dword ptr [rax+rax+00h]
0x18003eef6  mov     ebx, eax
0x18003eef8  test    eax, eax
0x18003eefa  jns     short loc_18003EF1C
0x18003eefc  mov     rcx, [rsp+38h]; this
0x18003ef01  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003ef08  mov     r9d, eax; char *
0x18003ef0b  mov     edx, 252h; void *
0x18003ef10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ef15  mov     eax, ebx
0x18003ef17  jmp     loc_18003F049
0x18003ef1c  cmp     [rsp+38h+arg_10], 1
0x18003ef21  jnz     loc_18003F047
0x18003ef27  mov     ecx, [rdi+0F8h]
0x18003ef2d  mov     eax, 1
0x18003ef32  shl     rax, cl
0x18003ef35  test    rax, 8000001h
0x18003ef3b  jz      loc_18003F047
0x18003ef41  lea     rsi, [rdi+0D8h]
0x18003ef48  mov     [rsp+38h+arg_18], 0
0x18003ef51  mov     rcx, rsi
0x18003ef54  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003ef59  mov     rax, [rsi+8]
0x18003ef5d  lea     rbx, ds:2[rax*2]
0x18003ef65  call    cs:__imp_GetProcessHeap
0x18003ef6c  nop     dword ptr [rax+rax+00h]
0x18003ef71  mov     r8, rbx; dwBytes
0x18003ef74  mov     edx, 8; dwFlags
0x18003ef79  mov     rcx, rax; hHeap
0x18003ef7c  call    cs:__imp_HeapAlloc
0x18003ef83  nop     dword ptr [rax+rax+00h]
0x18003ef88  lea     rcx, [rsp+38h+arg_18]
0x18003ef8d  mov     rbp, rax
0x18003ef90  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18003ef95  mov     [rsp+38h+arg_18], rbp
0x18003ef9a  test    rbp, rbp
0x18003ef9d  jnz     short loc_18003EFA6
0x18003ef9f  mov     edx, 25Ah
0x18003efa4  jmp     short loc_18003EFFD
0x18003efa6  mov     r9, [rsi]
0x18003efa9  mov     rcx, rsi
0x18003efac  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003efb1  mov     rdx, [rsi+8]
0x18003efb5  mov     r8, r9; unsigned __int16 *
0x18003efb8  inc     rdx; unsigned __int64
0x18003efbb  mov     rcx, rbp; unsigned __int16 *
0x18003efbe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003efc3  mov     ebx, eax
0x18003efc5  test    eax, eax
0x18003efc7  jns     short loc_18003EFD3
0x18003efc9  mov     r9d, eax
0x18003efcc  mov     edx, 25Bh
0x18003efd1  jmp     short loc_18003F005
0x18003efd3  xor     r8d, r8d; pcbe
0x18003efd6  lea     rcx, ?s_DeviceManagementWorker@CEnrollmentRemoveProfileSetting@WorkAccess@SystemSettings@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003efdd  mov     rdx, rbp; pv
0x18003efe0  call    cs:__imp_CreateThreadpoolWork
0x18003efe7  nop     dword ptr [rax+rax+00h]
0x18003efec  mov     [rdi+0F0h], rax
0x18003eff3  test    rax, rax
0x18003eff6  jnz     short loc_18003F025
0x18003eff8  mov     edx, 25Dh; void *
0x18003effd  mov     ebx, 80004005h
0x18003f002  mov     r9d, ebx; char *
0x18003f005  mov     rcx, [rsp+38h]; this
0x18003f00a  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003f011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f016  lea     rcx, [rsp+38h+arg_18]
0x18003f01b  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18003f020  jmp     loc_18003EF15
0x18003f025  mov     rcx, rax; pwk
0x18003f028  call    cs:__imp_SubmitThreadpoolWork
0x18003f02f  nop     dword ptr [rax+rax+00h]
0x18003f034  lea     rcx, [rsp+38h+arg_18]
0x18003f039  mov     [rsp+38h+arg_18], 0
0x18003f042  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18003f047  xor     eax, eax
0x18003f049  mov     rbx, [rsp+38h+arg_0]
0x18003f04e  add     rsp, 20h
0x18003f052  pop     rdi
0x18003f053  pop     rsi
0x18003f054  pop     rbp
0x18003f055  retn
```
