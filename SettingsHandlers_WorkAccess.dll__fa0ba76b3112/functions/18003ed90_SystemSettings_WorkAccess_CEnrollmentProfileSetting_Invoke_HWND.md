# SystemSettings::WorkAccess::CEnrollmentProfileSetting::Invoke(HWND__ *)

- ea: `0x18003ed90`
- end: `0x18003eeab`
- name: `?Invoke@CEnrollmentProfileSetting@WorkAccess@SystemSettings@@MEAAJPEAUHWND__@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::CEnrollmentProfileSetting *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180009e68`
- `0x1800201b0`
- `0x180027a58`
- `0x18003ed90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003edd7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003edd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003edc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003edc0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ee7e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ee7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003ee54`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003ee54`

## string_xrefs

- `0x18003ee39`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentProfileSetting::Invoke(
        SystemSettings::WorkAccess::CEnrollmentProfileSetting *this,
        HWND a2)
{
  char *v2; // rdi
  SIZE_T v4; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rsi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  const unsigned __int16 *v10; // r9
  int v11; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v16; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 280;
  v16 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount((char *)this + 280);
  v4 = 2LL * *((_QWORD *)v2 + 1) + 2;
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v4);
  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v16);
  v16 = v6;
  if ( v6 )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v2);
    v11 = StringCchCopyW(v6, *((_QWORD *)v2 + 1) + 1LL, v10);
    v7 = v11;
    if ( v11 >= 0 )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         SystemSettings::WorkAccess::CEnrollmentProfileSetting::s_DeviceManagementWorker,
                         v6,
                         0);
      *((_QWORD *)this + 31) = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        v7 = 0;
        v16 = 0;
        goto LABEL_9;
      }
      v7 = -2147467259;
      v8 = 473;
      v9 = 2147500037LL;
    }
    else
    {
      v9 = (unsigned int)v11;
      v8 = 471;
    }
  }
  else
  {
    v7 = -2147467259;
    v8 = 470;
    v9 = 2147500037LL;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
    (const char *)v9,
    v14);
LABEL_9:
  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v16);
  return v7;
}

```

## disassembly

```asm
0x18003ed90  push    rbx
0x18003ed92  push    rbp
0x18003ed93  push    rsi
0x18003ed94  push    rdi
0x18003ed95  sub     rsp, 28h
0x18003ed99  lea     rdi, [rcx+118h]
0x18003eda0  mov     [rsp+48h+arg_0], 0
0x18003eda9  mov     rbp, rcx
0x18003edac  mov     rcx, rdi
0x18003edaf  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003edb4  mov     rax, [rdi+8]
0x18003edb8  lea     rbx, ds:2[rax*2]
0x18003edc0  call    cs:__imp_GetProcessHeap
0x18003edc7  nop     dword ptr [rax+rax+00h]
0x18003edcc  mov     r8, rbx; dwBytes
0x18003edcf  mov     edx, 8; dwFlags
0x18003edd4  mov     rcx, rax; hHeap
0x18003edd7  call    cs:__imp_HeapAlloc
0x18003edde  nop     dword ptr [rax+rax+00h]
0x18003ede3  lea     rcx, [rsp+48h+arg_0]
0x18003ede8  mov     rsi, rax
0x18003edeb  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18003edf0  mov     [rsp+48h+arg_0], rsi
0x18003edf5  test    rsi, rsi
0x18003edf8  jnz     short loc_18003EE09
0x18003edfa  mov     ebx, 80004005h
0x18003edff  mov     edx, 1D6h
0x18003ee04  mov     r9d, ebx
0x18003ee07  jmp     short loc_18003EE34
0x18003ee09  mov     r9, [rdi]
0x18003ee0c  mov     rcx, rdi
0x18003ee0f  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18003ee14  mov     rdx, [rdi+8]
0x18003ee18  mov     r8, r9; unsigned __int16 *
0x18003ee1b  inc     rdx; unsigned __int64
0x18003ee1e  mov     rcx, rsi; unsigned __int16 *
0x18003ee21  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ee26  mov     ebx, eax
0x18003ee28  test    eax, eax
0x18003ee2a  jns     short loc_18003EE47
0x18003ee2c  mov     r9d, eax; char *
0x18003ee2f  mov     edx, 1D7h; void *
0x18003ee34  mov     rcx, [rsp+48h]; this
0x18003ee39  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003ee40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ee45  jmp     short loc_18003EE95
0x18003ee47  xor     r8d, r8d; pcbe
0x18003ee4a  lea     rcx, ?s_DeviceManagementWorker@CEnrollmentProfileSetting@WorkAccess@SystemSettings@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003ee51  mov     rdx, rsi; pv
0x18003ee54  call    cs:__imp_CreateThreadpoolWork
0x18003ee5b  nop     dword ptr [rax+rax+00h]
0x18003ee60  mov     [rbp+0F8h], rax
0x18003ee67  test    rax, rax
0x18003ee6a  jnz     short loc_18003EE7B
0x18003ee6c  mov     ebx, 80004005h
0x18003ee71  mov     edx, 1D9h
0x18003ee76  mov     r9d, ebx
0x18003ee79  jmp     short loc_18003EE34
0x18003ee7b  mov     rcx, rax; pwk
0x18003ee7e  call    cs:__imp_SubmitThreadpoolWork
0x18003ee85  nop     dword ptr [rax+rax+00h]
0x18003ee8a  xor     ebx, ebx
0x18003ee8c  mov     [rsp+48h+arg_0], 0
0x18003ee95  lea     rcx, [rsp+48h+arg_0]
0x18003ee9a  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18003ee9f  mov     eax, ebx
0x18003eea1  add     rsp, 28h
0x18003eea5  pop     rdi
0x18003eea6  pop     rsi
0x18003eea7  pop     rbp
0x18003eea8  pop     rbx
0x18003eea9  retn
```
