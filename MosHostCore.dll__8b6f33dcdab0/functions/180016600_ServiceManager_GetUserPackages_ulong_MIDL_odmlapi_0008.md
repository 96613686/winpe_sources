# ServiceManager::GetUserPackages(ulong *,__MIDL_odmlapi_0008 * *)

- ea: `0x180016600`
- end: `0x1800166a0`
- name: `?GetUserPackages@ServiceManager@@UEAAJPEAKPEAPEAU__MIDL_odmlapi_0008@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(ServiceManager *this, unsigned int *, struct __MIDL_odmlapi_0008 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000fbcc`
- `0x180016600`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001667a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001667a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180016648`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180016648`

## string_xrefs

- `0x18001663c`: `ServiceManager::GetUserPackages`
- `0x180016671`: `ServiceManager::GetUserPackages`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetUserPackages(
        ServiceManager *this,
        unsigned int *a2,
        struct __MIDL_odmlapi_0008 **a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int UserPackageList; // eax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v10);
  if ( *((_DWORD *)this + 882) == 5 )
  {
    UserPackageList = PackageManager::GetUserPackageList((ServiceManager *)((char *)this + 3568), a2, a3);
    if ( UserPackageList >= 0 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v6 = ZTraceReportPropagation(UserPackageList, "ServiceManager::GetUserPackages", 1329, this);
  }
  else
  {
    v6 = ZTraceReportOrigination(-2147024875, "ServiceManager::GetUserPackages", 1327, this);
  }
  v7 = v6;
LABEL_7:
  RelockableGate::~RelockableGate((RelockableGate *)v10);
  return v7;
}

```

## disassembly

```asm
0x180016600  mov     [rsp+arg_0], rbx
0x180016605  mov     [rsp+arg_8], rsi
0x18001660a  push    rdi
0x18001660b  sub     rsp, 30h
0x18001660f  mov     rdi, r8
0x180016612  mov     rsi, rdx
0x180016615  mov     rbx, rcx
0x180016618  add     rcx, 0D48h
0x18001661f  lea     rdx, [rsp+38h+var_18]
0x180016624  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180016629  nop
0x18001662a  cmp     dword ptr [rbx+0DC8h], 5
0x180016631  jz      short loc_180016652
0x180016633  mov     r9, rbx
0x180016636  mov     r8d, 52Fh
0x18001663c  lea     rdx, aServicemanager_4; "ServiceManager::GetUserPackages"
0x180016643  mov     ecx, 80070015h
0x180016648  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001664e  mov     ebx, eax
0x180016650  jmp     short loc_180016684
0x180016652  lea     rcx, [rbx+0DF0h]; this
0x180016659  mov     r8, rdi; struct __MIDL_odmlapi_0008 **
0x18001665c  mov     rdx, rsi; unsigned int *
0x18001665f  call    ?GetUserPackageList@PackageManager@@QEAAJPEAKPEAPEAU__MIDL_odmlapi_0008@@@Z; PackageManager::GetUserPackageList(ulong *,__MIDL_odmlapi_0008 * *)
0x180016664  test    eax, eax
0x180016666  jns     short loc_180016682
0x180016668  mov     r9, rbx
0x18001666b  mov     r8d, 531h
0x180016671  lea     rdx, aServicemanager_4; "ServiceManager::GetUserPackages"
0x180016678  mov     ecx, eax
0x18001667a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016680  jmp     short loc_18001664E
0x180016682  xor     ebx, ebx
0x180016684  lea     rcx, [rsp+38h+var_18]; this
0x180016689  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x18001668e  mov     eax, ebx
0x180016690  mov     rbx, [rsp+38h+arg_0]
0x180016695  mov     rsi, [rsp+38h+arg_8]
0x18001669a  add     rsp, 30h
0x18001669e  pop     rdi
0x18001669f  retn
```
