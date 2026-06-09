# HandlePluginUninitialize(void *)

- ea: `0x180009780`
- end: `0x180009823`
- name: `?HandlePluginUninitialize@@YAJPEAX@Z`
- size: `163`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009f10`

## callees

- `0x180001158`
- `0x180008440`
- `0x180008900`
- `0x18000baac`
- `0x18000c7c4`
- `0x180026870`
- `0x180032010`

## string_xrefs

- `0x1800097c6`: `onecoreuap\ds\ext\live\identity\cloudapplugin\msacloudap.cpp`
- `0x18000978f`: `HandlePluginUninitialize`

## pseudocode

```c
__int64 __fastcall HandlePluginUninitialize(void *a1)
{
  __int64 v2; // rdx
  int v3; // r8d
  __int64 v5; // [rsp+20h] [rbp-30h] BYREF
  void *v6; // [rsp+28h] [rbp-28h]
  _QWORD v7[4]; // [rsp+30h] [rbp-20h] BYREF
  int v8; // [rsp+68h] [rbp+18h] BYREF

  v6 = 0;
  v7[0] = "HandlePluginUninitialize";
  v8 = 0;
  v7[2] = 0;
  v7[3] = 0;
  v7[1] = &v8;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\msacloudap.cpp",
    "HandlePluginUninitialize",
    (const char *)0x3DE,
    0,
    (const unsigned __int16 *)&SmartHCRYPTPROV::`vftable');
  (*(void (__fastcall **)(__int64 *))(v5 + 8))(&v5);
  v6 = a1;
  TraceLoggingUnregister_EventUnregister(&dword_18004D048);
  TraceState();
  McGenEventUnregister_EventUnregister();
  LODWORD(a1) = v8;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v7, v2, v3);
  SmartHCRYPTPROV::~SmartHCRYPTPROV((SmartHCRYPTPROV *)&v5);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180009780  mov     [rsp-8+arg_0], rbx
0x180009785  push    rbp
0x180009786  mov     rbp, rsp
0x180009789  sub     rsp, 50h
0x18000978d  xor     eax, eax
0x18000978f  lea     rdx, aHandlepluginun; "HandlePluginUninitialize"
0x180009796  mov     [rbp+var_28], rax
0x18000979a  mov     rbx, rcx
0x18000979d  xor     ecx, ecx
0x18000979f  mov     [rbp+var_20], rdx
0x1800097a3  lea     rax, ??_7SmartHCRYPTPROV@@6B@; const SmartHCRYPTPROV::`vftable'
0x1800097aa  mov     [rbp+arg_8], ecx
0x1800097ad  mov     [rbp+var_30], rax
0x1800097b1  xor     r9d, r9d; unsigned int
0x1800097b4  lea     rax, [rbp+arg_8]
0x1800097b8  mov     [rbp+var_10], rcx
0x1800097bc  mov     [rbp+var_8], rcx
0x1800097c0  mov     r8d, 3DEh; char *
0x1800097c6  lea     rcx, aOnecoreuapDsEx_9; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800097cd  mov     [rbp+var_18], rax
0x1800097d1  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800097d6  mov     rax, [rbp+var_30]
0x1800097da  lea     rcx, [rbp+var_30]
0x1800097de  mov     rax, [rax+8]
0x1800097e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097e7  lea     rcx, dword_18004D048
0x1800097ee  mov     [rbp+var_28], rbx
0x1800097f2  call    TraceLoggingUnregister_EventUnregister
0x1800097f7  call    TraceState
0x1800097fc  call    McGenEventUnregister_EventUnregister
0x180009801  mov     ebx, [rbp+arg_8]
0x180009804  lea     rcx, [rbp+var_20]
0x180009808  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000980d  lea     rcx, [rbp+var_30]; this
0x180009811  call    ??1SmartHCRYPTPROV@@UEAA@XZ; SmartHCRYPTPROV::~SmartHCRYPTPROV(void)
0x180009816  mov     eax, ebx
0x180009818  mov     rbx, [rsp+50h+arg_0]
0x18000981d  add     rsp, 50h
0x180009821  pop     rbp
0x180009822  retn
```
