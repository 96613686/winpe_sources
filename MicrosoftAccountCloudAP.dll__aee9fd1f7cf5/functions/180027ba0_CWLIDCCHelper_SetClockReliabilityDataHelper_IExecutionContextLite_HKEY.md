# CWLIDCCHelper::SetClockReliabilityDataHelper(IExecutionContextLite *,HKEY__ *)

- ea: `0x180027ba0`
- end: `0x180027d24`
- name: `?SetClockReliabilityDataHelper@CWLIDCCHelper@@CAJPEAVIExecutionContextLite@@PEAUHKEY__@@@Z`
- size: `388`
- prototype: `static int(struct IExecutionContextLite *, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180027a54`

## callees

- `0x180008440`
- `0x18000baac`
- `0x1800267c0`
- `0x180026c8c`
- `0x180027ba0`
- `0x18002a0c8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180027c8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180027c8c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180027c08`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180027c08`

## string_xrefs

- `0x180027c44`: `hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_CLOCKTIME_SEC, REG_QWORD, reinterpret_cast<PBYTE>(&currentTime), sizeof(currentTime))`
- `0x180027c72`: `WriteBufferToRegistry wrote current time = %I64d`
- `0x180027cec`: `WriteBufferToRegistry wrote tick count = %I64d`
- `0x180027ccc`: `hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_TICKCOUNT, REG_QWORD, reinterpret_cast<PBYTE>(&ticksSinceBoot), sizeof(ticksSinceBoot))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWLIDCCHelper::SetClockReliabilityDataHelper(struct IExecutionContextLite *a1, HKEY a2)
{
  int v3; // eax
  __int64 v4; // rdx
  int v5; // r8d
  int v6; // eax
  unsigned int v7; // ebx
  char *v9; // [rsp+20h] [rbp-50h]
  unsigned __int8 v10[8]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v11[5]; // [rsp+48h] [rbp-28h] BYREF
  int v12; // [rsp+90h] [rbp+20h] BYREF
  __time64_t Time; // [rsp+A0h] [rbp+30h] BYREF
  struct IExecutionContextLite *v14; // [rsp+A8h] [rbp+38h] BYREF

  v12 = 0;
  v14 = a1;
  v11[0] = "CWLIDCCHelper::SetClockReliabilityDataHelper";
  v11[1] = &v12;
  v11[2] = 0;
  v11[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
    "CWLIDCCHelper::SetClockReliabilityDataHelper",
    (const char *)0x2E4,
    0,
    (const unsigned __int16 *)v9);
  Time = 0;
  _time64(&Time);
  v3 = RegistryHelper::WriteBufferToRegistry(
         (RegistryHelper *)&v14,
         a2,
         0,
         L"ClockTimeSeconds",
         0xBu,
         (unsigned __int8 *)&Time,
         8u);
  v12 = v3;
  if ( v3 >= 0 )
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      0x2F2u,
      L"WriteBufferToRegistry wrote current time = %I64d",
      Time);
    *(_QWORD *)v10 = GetTickCount64();
    v6 = RegistryHelper::WriteBufferToRegistry((RegistryHelper *)&v14, a2, 0, L"TickCount", 0xBu, v10, 8u);
    v12 = v6;
    if ( v6 >= 0 )
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
        0x2FFu,
        L"WriteBufferToRegistry wrote tick count = %I64d",
        *(_QWORD *)v10);
    else
      Telemetry::IfFailExit(
        (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
        "CWLIDCCHelper::SetClockReliabilityDataHelper",
        253,
        v6,
        "hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_TICKCOUNT, REG_QWORD, reinterpret_cast<PBYTE>"
        "(&ticksSinceBoot), sizeof(ticksSinceBoot))");
  }
  else
  {
    Telemetry::IfFailExit(
      (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\wlidcchelper.cpp",
      "CWLIDCCHelper::SetClockReliabilityDataHelper",
      240,
      v3,
      "hr = registryHelper.WriteBufferToRegistry( hKey, nullptr, WLID_REG_CLOCKTIME_SEC, REG_QWORD, reinterpret_cast<PBYT"
      "E>(&currentTime), sizeof(currentTime))");
  }
  v7 = v12;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v11, v4, v5);
  return v7;
}

```

## disassembly

```asm
0x180027ba0  mov     [rsp-18h+arg_8], rbx
0x180027ba5  push    rbp
0x180027ba6  push    rsi
0x180027ba7  push    rdi
0x180027ba8  mov     rbp, rsp
0x180027bab  sub     rsp, 70h
0x180027baf  mov     rbx, rdx
0x180027bb2  mov     [rbp+arg_0], 0
0x180027bb9  mov     [rbp+arg_18], rcx
0x180027bbd  lea     rsi, aCwlidcchelperS; "CWLIDCCHelper::SetClockReliabilityDataH"...
0x180027bc4  mov     [rbp+var_28], rsi
0x180027bc8  lea     rax, [rbp+arg_0]
0x180027bcc  mov     [rbp+var_20], rax
0x180027bd0  mov     [rbp+var_18], 0
0x180027bd8  mov     [rbp+var_10], 0
0x180027be0  xor     r9d, r9d; unsigned int
0x180027be3  mov     r8d, 2E4h; char *
0x180027be9  mov     rdx, rsi; char *
0x180027bec  lea     rdi, aOnecoreuapDsEx_7; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180027bf3  mov     rcx, rdi; this
0x180027bf6  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180027bfb  nop
0x180027bfc  mov     [rbp+Time], 0
0x180027c04  lea     rcx, [rbp+Time]; Time
0x180027c08  call    cs:__imp__time64
0x180027c0e  mov     [rsp+70h+var_40], 8; unsigned int
0x180027c16  lea     rax, [rbp+Time]
0x180027c1a  mov     [rsp+70h+var_48], rax; unsigned __int8 *
0x180027c1f  mov     dword ptr [rsp+70h+var_50], 0Bh; unsigned int
0x180027c27  lea     r9, aClocktimesecon; "ClockTimeSeconds"
0x180027c2e  xor     r8d, r8d; unsigned __int16 *
0x180027c31  mov     rdx, rbx; HKEY
0x180027c34  lea     rcx, [rbp+arg_18]; this
0x180027c38  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x180027c3d  mov     [rbp+arg_0], eax
0x180027c40  test    eax, eax
0x180027c42  jns     short loc_180027C69
0x180027c44  lea     r8, aHrRegistryhelp; "hr = registryHelper.WriteBufferToRegist"...
0x180027c4b  mov     [rsp+70h+var_50], r8; char *
0x180027c50  mov     r8d, 2F0h; unsigned int
0x180027c56  mov     r9d, eax; int
0x180027c59  mov     rdx, rsi; char *
0x180027c5c  mov     rcx, rdi; char *
0x180027c5f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180027c64  jmp     loc_180027D06
0x180027c69  mov     rax, [rbp+Time]
0x180027c6d  mov     [rsp+70h+var_50], rax
0x180027c72  lea     r9, aWritebuffertor_0; "WriteBufferToRegistry wrote current tim"...
0x180027c79  mov     r8d, 2F2h; unsigned int
0x180027c7f  mov     rdx, rdi; char *
0x180027c82  mov     ecx, 5; unsigned __int8
0x180027c87  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180027c8c  call    cs:__imp_GetTickCount64
0x180027c92  mov     qword ptr [rbp+var_30], rax
0x180027c96  mov     [rsp+70h+var_40], 8; unsigned int
0x180027c9e  lea     rax, [rbp+var_30]
0x180027ca2  mov     [rsp+70h+var_48], rax; unsigned __int8 *
0x180027ca7  mov     dword ptr [rsp+70h+var_50], 0Bh; unsigned int
0x180027caf  lea     r9, aTickcount; "TickCount"
0x180027cb6  xor     r8d, r8d; unsigned __int16 *
0x180027cb9  mov     rdx, rbx; HKEY
0x180027cbc  lea     rcx, [rbp+arg_18]; this
0x180027cc0  call    ?WriteBufferToRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAEK@Z; RegistryHelper::WriteBufferToRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)
0x180027cc5  mov     [rbp+arg_0], eax
0x180027cc8  test    eax, eax
0x180027cca  jns     short loc_180027CE3
0x180027ccc  lea     rcx, aHrRegistryhelp_1; "hr = registryHelper.WriteBufferToRegist"...
0x180027cd3  mov     [rsp+70h+var_50], rcx
0x180027cd8  mov     r8d, 2FDh
0x180027cde  jmp     loc_180027C56
0x180027ce3  mov     rax, qword ptr [rbp+var_30]
0x180027ce7  mov     [rsp+70h+var_50], rax
0x180027cec  lea     r9, aWritebuffertor_1; "WriteBufferToRegistry wrote tick count "...
0x180027cf3  mov     r8d, 2FFh; unsigned int
0x180027cf9  mov     rdx, rdi; char *
0x180027cfc  mov     ecx, 5; unsigned __int8
0x180027d01  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180027d06  mov     ebx, [rbp+arg_0]
0x180027d09  lea     rcx, [rbp+var_28]
0x180027d0d  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180027d12  mov     eax, ebx
0x180027d14  mov     rbx, [rsp+70h+arg_8]
0x180027d1c  add     rsp, 70h
0x180027d20  pop     rdi
0x180027d21  pop     rsi
0x180027d22  pop     rbp
0x180027d23  retn
```
