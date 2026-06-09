# ServiceManager::DeleteAllMaps(void)

- ea: `0x180014980`
- end: `0x180014a88`
- name: `?DeleteAllMaps@ServiceManager@@UEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180009bb4`
- `0x180009c04`
- `0x18001189c`
- `0x180014980`
- `0x1800228ec`
- `0x1800229b8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014a65`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180014a65`

## string_xrefs

- `0x180014a5e`: `ServiceManager::DeleteAllMaps`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceManager::DeleteAllMaps(ServiceManager *this)
{
  int v2; // r8d
  int v3; // ecx
  unsigned int v4; // edi
  __int64 (__fastcall *v6)(RTL_CONDITION_VARIABLE *); // [rsp+20h] [rbp-20h] BYREF
  __int64 *v7; // [rsp+28h] [rbp-18h]
  _BYTE v8[12]; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+3Ch] [rbp-4h]
  int v10; // [rsp+50h] [rbp+10h] BYREF
  int v11; // [rsp+54h] [rbp+14h]
  __int64 v12; // [rsp+58h] [rbp+18h] BYREF

  CriticalSectionWithConditionVariable::Lock((char *)this + 3400, v8);
  if ( !(unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, 1) )
    __int2c();
  if ( *((_DWORD *)this + 880) || *((_DWORD *)this + 881) )
  {
    v2 = 977;
    v3 = -2147024567;
    goto LABEL_9;
  }
  v10 = 0;
  v11 = 5;
  v6 = (__int64 (__fastcall *)(RTL_CONDITION_VARIABLE *))&v10;
  v7 = &v12;
  if ( (unsigned __int8)ClientsTracker::HasClientsOf((char *)this + 3816, &v6) )
  {
    v2 = 978;
    v3 = -2080374784;
LABEL_9:
    v4 = ZTraceReportOrigination(v3, "ServiceManager::DeleteAllMaps", v2, this);
    goto LABEL_10;
  }
  v4 = 0;
  *((_DWORD *)this + 880) = 5;
  *((_DWORD *)this + 881) = 7;
  v6 = ServiceManager::ClearMapData;
  LODWORD(v7) = 0;
  HIDWORD(v7) = v9;
  Threadpool::QueueThis<ServiceManager>(*((PTP_CALLBACK_ENVIRON *)this + 424));
LABEL_10:
  RelockableGate::~RelockableGate((RelockableGate *)v8);
  return v4;
}

```

## disassembly

```asm
0x180014980  mov     [rsp-8+arg_8], rbx
0x180014985  mov     [rsp-8+arg_10], rdi
0x18001498a  push    rbp
0x18001498b  mov     rbp, rsp
0x18001498e  sub     rsp, 40h
0x180014992  mov     rbx, rcx
0x180014995  add     rcx, 0D48h
0x18001499c  lea     rdx, [rbp+var_10]
0x1800149a0  call    ?Lock@CriticalSectionWithConditionVariable@@QEAA?AVRelockableGate@@XZ; CriticalSectionWithConditionVariable::Lock(void)
0x1800149a5  nop
0x1800149a6  lea     rdi, [rbx+0EE8h]
0x1800149ad  mov     edx, 1
0x1800149b2  mov     rcx, rdi
0x1800149b5  call    ?HasClientsOf@ClientsTracker@@QEAA_NW4MapsClientType@@@Z; ClientsTracker::HasClientsOf(MapsClientType)
0x1800149ba  test    al, al
0x1800149bc  jnz     short loc_1800149C0
0x1800149be  int     2Ch; Windows NT - assertion failure
0x1800149c0  cmp     dword ptr [rbx+0DC0h], 0
0x1800149c7  jnz     loc_180014A50
0x1800149cd  cmp     dword ptr [rbx+0DC4h], 0
0x1800149d4  jnz     short loc_180014A50
0x1800149d6  mov     [rbp+arg_0], 0
0x1800149dd  mov     [rbp+arg_4], 5
0x1800149e4  lea     rax, [rbp+arg_0]
0x1800149e8  mov     [rbp+var_20], rax
0x1800149ec  lea     rax, [rbp+arg_8]
0x1800149f0  mov     [rbp+var_18], rax
0x1800149f4  lea     rdx, [rbp+var_20]
0x1800149f8  mov     rcx, rdi
0x1800149fb  call    ?HasClientsOf@ClientsTracker@@QEAA_NAEBV?$initializer_list@W4MapsClientType@@@std@@@Z; ClientsTracker::HasClientsOf(std::initializer_list<MapsClientType> const &)
0x180014a00  test    al, al
0x180014a02  jz      short loc_180014A11
0x180014a04  mov     r8d, 3D2h
0x180014a0a  mov     ecx, 84000000h
0x180014a0f  jmp     short loc_180014A5B
0x180014a11  xor     edi, edi
0x180014a13  mov     dword ptr [rbx+0DC0h], 5
0x180014a1d  mov     dword ptr [rbx+0DC4h], 7
0x180014a27  lea     rax, ?ClearMapData@ServiceManager@@AEAAJXZ; ServiceManager::ClearMapData(void)
0x180014a2e  mov     [rbp+var_20], rax
0x180014a32  mov     dword ptr [rbp+var_18], edi
0x180014a35  mov     eax, [rbp+var_4]
0x180014a38  mov     dword ptr [rbp+var_18+4], eax
0x180014a3b  lea     r8, [rbp+var_20]
0x180014a3f  mov     rdx, rbx
0x180014a42  mov     rcx, [rbx+0D40h]; pcbe
0x180014a49  call    ??$QueueThis@VServiceManager@@@Threadpool@@QEAAXPEAVServiceManager@@P81@EAAJXZ@Z; Threadpool::QueueThis<ServiceManager>(ServiceManager *,long (ServiceManager::*)(void))
0x180014a4e  jmp     short loc_180014A6D
0x180014a50  mov     r8d, 3D1h
0x180014a56  mov     ecx, 80070149h
0x180014a5b  mov     r9, rbx
0x180014a5e  lea     rdx, aServicemanager_81; "ServiceManager::DeleteAllMaps"
0x180014a65  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180014a6b  mov     edi, eax
0x180014a6d  lea     rcx, [rbp+var_10]; this
0x180014a71  call    ??1RelockableGate@@QEAA@XZ; RelockableGate::~RelockableGate(void)
0x180014a76  mov     eax, edi
0x180014a78  mov     rbx, [rsp+40h+arg_8]
0x180014a7d  mov     rdi, [rsp+40h+arg_10]
0x180014a82  add     rsp, 40h
0x180014a86  pop     rbp
0x180014a87  retn
```
