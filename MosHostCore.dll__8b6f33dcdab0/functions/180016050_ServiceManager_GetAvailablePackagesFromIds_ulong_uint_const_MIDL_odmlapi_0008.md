# ServiceManager::GetAvailablePackagesFromIds(ulong,uint const *,__MIDL_odmlapi_0008 * *)

- ea: `0x180016050`
- end: `0x1800160f3`
- name: `?GetAvailablePackagesFromIds@ServiceManager@@UEAAJKPEBIPEAPEAU__MIDL_odmlapi_0008@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(ServiceManager *this, unsigned int, const unsigned int *, struct __MIDL_odmlapi_0008 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000f514`
- `0x180016050`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800160dc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x1800160dc`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180016094`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180016094`

## string_xrefs

- `0x180016088`: `ServiceManager::GetAvailablePackagesFromIds`
- `0x1800160d3`: `ServiceManager::GetAvailablePackagesFromIds`

## pseudocode

```c
__int64 __fastcall ServiceManager::GetAvailablePackagesFromIds(
        ServiceManager *this,
        unsigned int a2,
        const unsigned int *a3,
        struct __MIDL_odmlapi_0008 **a4)
{
  unsigned int v8; // ebx
  int AvailablePackagesFromIds; // eax
  _BYTE v11[56]; // [rsp+20h] [rbp-38h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v11);
  if ( *((_DWORD *)this + 882) == 5 )
  {
    RelockableGate::~RelockableGate((RelockableGate *)v11);
    AvailablePackagesFromIds = PackageManager::GetAvailablePackagesFromIds(
                                 (ServiceManager *)((char *)this + 3568),
                                 a2,
                                 a3,
                                 a4);
    if ( AvailablePackagesFromIds >= 0 )
      return 0;
    else
      return (unsigned int)ZTraceReportPropagation(
                             AvailablePackagesFromIds,
                             "ServiceManager::GetAvailablePackagesFromIds",
                             1371,
                             this);
  }
  else
  {
    v8 = ZTraceReportOrigination(-2147024875, "ServiceManager::GetAvailablePackagesFromIds", 1367, this);
    RelockableGate::~RelockableGate((RelockableGate *)v11);
  }
  return v8;
}

```

## disassembly

```asm
0x180016050  push    rbx
0x180016052  push    rbp
0x180016053  push    rsi
0x180016054  push    rdi
0x180016055  sub     rsp, 38h
0x180016059  mov     rdi, r9
0x18001605c  mov     rsi, r8
0x18001605f  mov     ebp, edx
0x180016061  mov     rbx, rcx
0x180016064  add     rcx, 0D48h
0x18001606b  lea     rdx, [rsp+58h+var_38]
0x180016070  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x180016075  nop
0x180016076  cmp     dword ptr [rbx+0DC8h], 5
0x18001607d  jz      short loc_1800160A8
0x18001607f  mov     r9, rbx
0x180016082  mov     r8d, 557h
0x180016088  lea     rdx, aServicemanager_77; "ServiceManager::GetAvailablePackagesFro"...
0x18001608f  mov     ecx, 80070015h
0x180016094  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001609a  mov     ebx, eax
0x18001609c  lea     rcx, [rsp+58h+var_38]; this
0x1800160a1  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x1800160a6  jmp     short loc_1800160E8
0x1800160a8  lea     rcx, [rsp+58h+var_38]; this
0x1800160ad  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x1800160b2  lea     rcx, [rbx+0DF0h]; this
0x1800160b9  mov     r9, rdi; struct __MIDL_odmlapi_0008 **
0x1800160bc  mov     r8, rsi; unsigned int *
0x1800160bf  mov     edx, ebp; unsigned int
0x1800160c1  call    ?GetAvailablePackagesFromIds@PackageManager@@QEAAJKPEBIPEAPEAU__MIDL_odmlapi_0008@@@Z; PackageManager::GetAvailablePackagesFromIds(ulong,uint const *,__MIDL_odmlapi_0008 * *)
0x1800160c6  test    eax, eax
0x1800160c8  jns     short loc_1800160E6
0x1800160ca  mov     r9, rbx
0x1800160cd  mov     r8d, 55Bh
0x1800160d3  lea     rdx, aServicemanager_77; "ServiceManager::GetAvailablePackagesFro"...
0x1800160da  mov     ecx, eax
0x1800160dc  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x1800160e2  mov     ebx, eax
0x1800160e4  jmp     short loc_1800160E8
0x1800160e6  xor     ebx, ebx
0x1800160e8  mov     eax, ebx
0x1800160ea  add     rsp, 38h
0x1800160ee  pop     rdi
0x1800160ef  pop     rsi
0x1800160f0  pop     rbp
0x1800160f1  pop     rbx
0x1800160f2  retn
```
