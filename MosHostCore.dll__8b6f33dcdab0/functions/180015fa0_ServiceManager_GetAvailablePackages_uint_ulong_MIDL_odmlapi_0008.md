# ServiceManager::GetAvailablePackages(uint,ulong *,__MIDL_odmlapi_0008 * *)

- ea: `0x180015fa0`
- end: `0x180016043`
- name: `?GetAvailablePackages@ServiceManager@@UEAAJIPEAKPEAPEAU__MIDL_odmlapi_0008@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(ServiceManager *this, unsigned int, unsigned int *, struct __MIDL_odmlapi_0008 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000f388`
- `0x180015fa0`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001602c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001602c`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015fe4`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180015fe4`

## string_xrefs

- `0x180015fd8`: `ServiceManager::GetAvailablePackages`
- `0x180016023`: `ServiceManager::GetAvailablePackages`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetAvailablePackages(
        ServiceManager *this,
        unsigned int a2,
        unsigned int *a3,
        struct __MIDL_odmlapi_0008 **a4)
{
  unsigned int v8; // ebx
  int AvailablePackageList; // eax
  _BYTE v11[56]; // [rsp+20h] [rbp-38h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v11);
  if ( *((_DWORD *)this + 882) == 5 )
  {
    RelockableGate::~RelockableGate((RelockableGate *)v11);
    AvailablePackageList = PackageManager::GetAvailablePackageList((ServiceManager *)((char *)this + 3568), a2, a3, a4);
    if ( AvailablePackageList >= 0 )
      return 0;
    else
      return (unsigned int)ZTraceReportPropagation(
                             AvailablePackageList,
                             "ServiceManager::GetAvailablePackages",
                             1350,
                             this);
  }
  else
  {
    v8 = ZTraceReportOrigination(-2147024875, "ServiceManager::GetAvailablePackages", 1346, this);
    RelockableGate::~RelockableGate((RelockableGate *)v11);
  }
  return v8;
}

```

## disassembly

```asm
0x180015fa0  push    rbx
0x180015fa2  push    rbp
0x180015fa3  push    rsi
0x180015fa4  push    rdi
0x180015fa5  sub     rsp, 38h
0x180015fa9  mov     rdi, r9
0x180015fac  mov     rsi, r8
0x180015faf  mov     ebp, edx
0x180015fb1  mov     rbx, rcx
0x180015fb4  add     rcx, 0D48h
0x180015fbb  lea     rdx, [rsp+58h+var_38]
0x180015fc0  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180015fc5  nop
0x180015fc6  cmp     dword ptr [rbx+0DC8h], 5
0x180015fcd  jz      short loc_180015FF8
0x180015fcf  mov     r9, rbx
0x180015fd2  mov     r8d, 542h
0x180015fd8  lea     rdx, aServicemanager_29; "ServiceManager::GetAvailablePackages"
0x180015fdf  mov     ecx, 80070015h
0x180015fe4  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180015fea  mov     ebx, eax
0x180015fec  lea     rcx, [rsp+58h+var_38]; this
0x180015ff1  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180015ff6  jmp     short loc_180016038
0x180015ff8  lea     rcx, [rsp+58h+var_38]; this
0x180015ffd  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180016002  lea     rcx, [rbx+0DF0h]; this
0x180016009  mov     r9, rdi; struct __MIDL_odmlapi_0008 **
0x18001600c  mov     r8, rsi; unsigned int *
0x18001600f  mov     edx, ebp; unsigned int
0x180016011  call    ?GetAvailablePackageList@PackageManager@@QEAAJIPEAKPEAPEAU__MIDL_odmlapi_0008@@@Z; PackageManager::GetAvailablePackageList(uint,ulong *,__MIDL_odmlapi_0008 * *)
0x180016016  test    eax, eax
0x180016018  jns     short loc_180016036
0x18001601a  mov     r9, rbx
0x18001601d  mov     r8d, 546h
0x180016023  lea     rdx, aServicemanager_29; "ServiceManager::GetAvailablePackages"
0x18001602a  mov     ecx, eax
0x18001602c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180016032  mov     ebx, eax
0x180016034  jmp     short loc_180016038
0x180016036  xor     ebx, ebx
0x180016038  mov     eax, ebx
0x18001603a  add     rsp, 38h
0x18001603e  pop     rdi
0x18001603f  pop     rsi
0x180016040  pop     rbp
0x180016041  pop     rbx
0x180016042  retn
```
