# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x1800163d4`
- end: `0x18001648f`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `187`
- prototype: `int __high(struct wil_details_FeatureReportingCache *, unsigned int, int, int, enum wil_details_ServiceReportingKind, unsigned int, unsigned __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180016330`

## callees

- `0x180015394`
- `0x1800163d4`
- `0x1800179b8`
- `0x180019cc8`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall wil::details::ReportUsageToServiceDirect(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v12; // rax
  __int64 v13; // xmm0_8
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned int v16; // r9d
  unsigned int v17; // edx
  char *v19; // [rsp+20h] [rbp-68h]
  char v20[16]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+40h] [rbp-48h]
  _BYTE v22[64]; // [rsp+48h] [rbp-40h] BYREF

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5, 0);
  v13 = *(_QWORD *)(v12 + 16);
  *(_OWORD *)v20 = *(_OWORD *)v12;
  v21 = v13;
  wil::details::RecordFeatureUsageCallback(a2, a5, v14, a1, (RTL_SRWLOCK *)v20);
  if ( a3 )
  {
    v17 = a5 | 0x80000000;
    if ( !a4 )
      v17 = a5;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v17, 0, v16, v19);
  }
  if ( (_DWORD)v21 )
    return 0;
  if ( g_wil_details_realtimeFeatureUsageHook )
  {
    LOBYTE(v15) = a8;
    g_wil_details_realtimeFeatureUsageHook(a2, a5, v15);
  }
  return 1;
}

```

## disassembly

```asm
0x1800163d4  push    rbx
0x1800163d6  push    rbp
0x1800163d7  push    rdi
0x1800163d8  push    r14
0x1800163da  sub     rsp, 68h
0x1800163de  mov     ebp, edx
0x1800163e0  mov     r14d, r9d
0x1800163e3  mov     rdx, rcx
0x1800163e6  mov     edi, r8d
0x1800163e9  mov     r8d, [rsp+88h+arg_20]
0x1800163f1  mov     rbx, rcx
0x1800163f4  lea     rcx, [rsp+88h+var_40]
0x1800163f9  xor     r9d, r9d
0x1800163fc  call    wil_details_FeatureReporting_RecordUsageInCache
0x180016401  mov     edx, [rsp+88h+arg_20]
0x180016408  mov     r9, rbx
0x18001640b  mov     ecx, ebp
0x18001640d  movups  xmm1, xmmword ptr [rax]
0x180016410  movsd   xmm0, qword ptr [rax+10h]
0x180016415  lea     rax, [rsp+88h+var_58]
0x18001641a  movups  xmmword ptr [rsp+88h+var_58], xmm1
0x18001641f  mov     [rsp+88h+var_68], rax; char *
0x180016424  movsd   [rsp+88h+var_48], xmm0
0x18001642a  call    ?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z; wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)
0x18001642f  test    edi, edi
0x180016431  jz      short loc_180016453
0x180016433  mov     edx, [rsp+88h+arg_20]
0x18001643a  mov     ecx, ebp; this
0x18001643c  bts     edx, 1Fh
0x180016440  test    r14d, r14d
0x180016443  cmovz   edx, [rsp+88h+arg_20]; unsigned int
0x18001644b  xor     r8d, r8d; unsigned int
0x18001644e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180016453  cmp     dword ptr [rsp+88h+var_48], 0
0x180016458  jnz     short loc_180016483
0x18001645a  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180016461  test    rax, rax
0x180016464  jz      short loc_18001647C
0x180016466  mov     r8b, [rsp+88h+arg_38]
0x18001646e  mov     ecx, ebp
0x180016470  mov     edx, [rsp+88h+arg_20]
0x180016477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001647c  mov     eax, 1
0x180016481  jmp     short loc_180016485
0x180016483  xor     eax, eax
0x180016485  add     rsp, 68h
0x180016489  pop     r14
0x18001648b  pop     rdi
0x18001648c  pop     rbp
0x18001648d  pop     rbx
0x18001648e  retn
```
