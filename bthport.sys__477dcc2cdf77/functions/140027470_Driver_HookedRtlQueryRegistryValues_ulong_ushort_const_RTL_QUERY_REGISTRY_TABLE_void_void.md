# Driver::HookedRtlQueryRegistryValues(ulong,ushort const *,_RTL_QUERY_REGISTRY_TABLE *,void *,void *)

- ea: `0x140027470`
- end: `0x1400275d6`
- name: `?HookedRtlQueryRegistryValues@Driver@@CAJKPEBGPEAU_RTL_QUERY_REGISTRY_TABLE@@PEAX2@Z`
- size: `358`
- prototype: `static int(unsigned int, const unsigned __int16 *, struct _RTL_QUERY_REGISTRY_TABLE *, void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x140005608`
- `0x140027470`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x1400274a3`
- `ntoskrnl!_wcsicmp` at `0x1400274e8`
- `ntoskrnl!_wcsicmp` at `0x1400274a3`
- `ntoskrnl!_wcsicmp` at `0x1400274e8`
- `ntoskrnl!EtwTelemetryCoverageReport` at `0x14002758e`
- `ntoskrnl!EtwTelemetryCoverageReport` at `0x14002758e`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400275c0`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400275c0`

## string_xrefs

- `0x140027499`: `\REGISTRY\Machine\System\CurrentControlSet\SERVICES\BtFilter\Parameters`

## pseudocode

```c
__int64 __fastcall Driver::HookedRtlQueryRegistryValues(
        unsigned int a1,
        const unsigned __int16 *a2,
        struct _RTL_QUERY_REGISTRY_TABLE *a3,
        void *a4,
        void *a5)
{
  wchar_t *Name; // rcx
  int v10; // edx

  if ( a1 != 0x80000000 )
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  if ( !a2 )
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  if ( _wcsicmp(a2, L"\\REGISTRY\\Machine\\System\\CurrentControlSet\\SERVICES\\BtFilter\\Parameters") )
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  if ( !a3 )
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  if ( a3->QueryRoutine )
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  if ( a3->Flags != 32 )
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  Name = a3->Name;
  if ( !Name
    || _wcsicmp(Name, L"BtFilterSSEnable")
    || !a3->EntryContext
    || a3->DefaultType != 4
    || a3[1].QueryRoutine
    || a3[1].Name )
  {
    return RtlQueryRegistryValuesEx(a1, a2, a3, a4, a5);
  }
  LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    1,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    1,
    41,
    (__int64)WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids);
  if ( (unsigned int)dword_140197194 < MEMORY[0xFFFFF7800000037C] )
    EtwTelemetryCoverageReport(&off_140197188);
  *(_DWORD *)a3->EntryContext = 0;
  return 0;
}

```

## disassembly

```asm
0x140027470  push    rbx
0x140027472  push    rbp
0x140027473  push    rsi
0x140027474  push    rdi
0x140027475  sub     rsp, 48h
0x140027479  mov     rbp, r9
0x14002747c  mov     rbx, r8
0x14002747f  mov     rdi, rdx
0x140027482  mov     esi, ecx
0x140027484  cmp     ecx, 80000000h
0x14002748a  jnz     loc_1400275A8
0x140027490  test    rdx, rdx
0x140027493  jz      loc_1400275A8
0x140027499  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\Machine\\System\\CurrentCon"...
0x1400274a0  mov     rcx, rdi; Str1
0x1400274a3  call    cs:__imp__wcsicmp
0x1400274aa  nop     dword ptr [rax+rax+00h]
0x1400274af  test    eax, eax
0x1400274b1  jnz     loc_1400275A8
0x1400274b7  test    rbx, rbx
0x1400274ba  jz      loc_1400275A8
0x1400274c0  cmp     qword ptr [rbx], 0
0x1400274c4  jnz     loc_1400275A8
0x1400274ca  cmp     dword ptr [rbx+8], 20h ; ' '
0x1400274ce  jnz     loc_1400275A8
0x1400274d4  mov     rcx, [rbx+10h]; Str1
0x1400274d8  test    rcx, rcx
0x1400274db  jz      loc_1400275A8
0x1400274e1  lea     rdx, aBtfilterssenab; "BtFilterSSEnable"
0x1400274e8  call    cs:__imp__wcsicmp
0x1400274ef  nop     dword ptr [rax+rax+00h]
0x1400274f4  test    eax, eax
0x1400274f6  jnz     loc_1400275A8
0x1400274fc  cmp     qword ptr [rbx+18h], 0
0x140027501  jz      loc_1400275A8
0x140027507  cmp     dword ptr [rbx+20h], 4
0x14002750b  jnz     loc_1400275A8
0x140027511  cmp     qword ptr [rbx+38h], 0
0x140027516  jnz     loc_1400275A8
0x14002751c  cmp     qword ptr [rbx+48h], 0
0x140027521  jnz     loc_1400275A8
0x140027527  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002752e  mov     r8d, 1
0x140027534  mov     eax, [rcx+2Ch]
0x140027537  test    r8b, al
0x14002753a  jz      short loc_140027547
0x14002753c  cmp     byte ptr [rcx+29h], 4
0x140027540  jb      short loc_140027547
0x140027542  mov     dl, r8b
0x140027545  jmp     short loc_140027549
0x140027547  xor     dl, dl
0x140027549  mov     r9, [rcx+40h]
0x14002754d  lea     rax, WPP_be9d3a7d8b8032943ffc7d9cff556632_Traceguids
0x140027554  mov     rcx, [rcx+18h]
0x140027558  mov     [rsp+68h+var_30], rax
0x14002755d  mov     [rsp+68h+var_38], 29h ; ')'
0x140027564  mov     [rsp+68h+var_40], r8d
0x140027569  mov     byte ptr [rsp+68h+var_48], 4
0x14002756e  call    WPP_RECORDER_AND_TRACE_SF_
0x140027573  mov     rax, 0FFFFF7800000037Ch; __annotation("Debug", "TelemetryCoverage", "Bluetooth_CompatShims_RegistryQueryShimInvoked")
0x14002757d  mov     eax, [rax]
0x14002757f  cmp     cs:dword_140197194, eax
0x140027585  jnb     short loc_14002759A
0x140027587  lea     rcx, off_140197188; "Bluetooth_CompatShims_RegistryQueryShim"...
0x14002758e  call    cs:__imp_EtwTelemetryCoverageReport
0x140027595  nop     dword ptr [rax+rax+00h]
0x14002759a  mov     rax, [rbx+18h]
0x14002759e  mov     dword ptr [rax], 0
0x1400275a4  xor     eax, eax
0x1400275a6  jmp     short loc_1400275CC
0x1400275a8  mov     rax, [rsp+68h+arg_20]
0x1400275b0  mov     r9, rbp
0x1400275b3  mov     r8, rbx
0x1400275b6  mov     [rsp+68h+var_48], rax
0x1400275bb  mov     rdx, rdi
0x1400275be  mov     ecx, esi
0x1400275c0  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400275c7  nop     dword ptr [rax+rax+00h]
0x1400275cc  add     rsp, 48h
0x1400275d0  pop     rdi
0x1400275d1  pop     rsi
0x1400275d2  pop     rbp
0x1400275d3  pop     rbx
0x1400275d4  retn
```
