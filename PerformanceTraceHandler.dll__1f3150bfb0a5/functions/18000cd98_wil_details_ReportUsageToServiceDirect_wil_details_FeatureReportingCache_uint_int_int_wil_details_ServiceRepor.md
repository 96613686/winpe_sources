# wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)

- ea: `0x18000cd98`
- end: `0x18000ce50`
- name: `?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z`
- size: `184`
- prototype: `__int64 __fastcall(struct wil_details_FeatureReportingCache *, unsigned int, int, int, unsigned int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000cc60`

## callees

- `0x180009044`
- `0x18000c928`
- `0x18000cd98`
- `0x18000ed04`
- `0x18001c010`

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

  v12 = wil_details_FeatureReporting_RecordUsageInCache(v22, a1, a5);
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
0x18000cd98  push    rbx
0x18000cd9a  push    rbp
0x18000cd9b  push    rdi
0x18000cd9c  push    r14
0x18000cd9e  sub     rsp, 68h
0x18000cda2  mov     ebp, edx
0x18000cda4  mov     edi, r8d
0x18000cda7  mov     r8d, [rsp+88h+arg_20]
0x18000cdaf  mov     rdx, rcx
0x18000cdb2  mov     rbx, rcx
0x18000cdb5  mov     r14d, r9d
0x18000cdb8  lea     rcx, [rsp+88h+var_40]
0x18000cdbd  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000cdc2  mov     edx, [rsp+88h+arg_20]
0x18000cdc9  mov     r9, rbx
0x18000cdcc  mov     ecx, ebp
0x18000cdce  movups  xmm1, xmmword ptr [rax]
0x18000cdd1  movsd   xmm0, qword ptr [rax+10h]
0x18000cdd6  lea     rax, [rsp+88h+var_58]
0x18000cddb  movups  xmmword ptr [rsp+88h+var_58], xmm1
0x18000cde0  mov     [rsp+88h+var_68], rax; char *
0x18000cde5  movsd   [rsp+88h+var_48], xmm0
0x18000cdeb  call    ?RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z; wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)
0x18000cdf0  test    edi, edi
0x18000cdf2  jz      short loc_18000CE14
0x18000cdf4  mov     edx, [rsp+88h+arg_20]
0x18000cdfb  mov     ecx, ebp; this
0x18000cdfd  bts     edx, 1Fh
0x18000ce01  test    r14d, r14d
0x18000ce04  cmovz   edx, [rsp+88h+arg_20]; unsigned int
0x18000ce0c  xor     r8d, r8d; unsigned int
0x18000ce0f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000ce14  cmp     dword ptr [rsp+88h+var_48], 0
0x18000ce19  jnz     short loc_18000CE44
0x18000ce1b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000ce22  test    rax, rax
0x18000ce25  jz      short loc_18000CE3D
0x18000ce27  mov     r8b, [rsp+88h+arg_38]
0x18000ce2f  mov     ecx, ebp
0x18000ce31  mov     edx, [rsp+88h+arg_20]
0x18000ce38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce3d  mov     eax, 1
0x18000ce42  jmp     short loc_18000CE46
0x18000ce44  xor     eax, eax
0x18000ce46  add     rsp, 68h
0x18000ce4a  pop     r14
0x18000ce4c  pop     rdi
0x18000ce4d  pop     rbp
0x18000ce4e  pop     rbx
0x18000ce4f  retn
```
