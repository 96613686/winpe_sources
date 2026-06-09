# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140002708`
- end: `0x1400027e4`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002678`

## callees

- `0x1400024e4`
- `0x140002708`
- `0x140006a20`
- `0x140006a60`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400027b6`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400027b6`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4)
{
  __int16 v5; // bx
  _DWORD *v8; // rax
  int v10; // [rsp+30h] [rbp-68h] BYREF
  int v11; // [rsp+34h] [rbp-64h]
  _BYTE v12[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v13; // [rsp+50h] [rbp-48h] BYREF
  __int64 v14; // [rsp+60h] [rbp-38h]

  v5 = a2;
  v8 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v12,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2),
         a4);
  v13 = *(_OWORD *)v8;
  v14 = *((_QWORD *)v8 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), a3, a4, *(_QWORD *)(a1 + 8), &v13);
  if ( (v5 & 0x400) != 0 && a3 != 254 )
  {
    v10 = *(_DWORD *)(a1 + 24);
    v11 = (unsigned __int16)a3;
    if ( (v5 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
    RtlNotifyFeatureUsage(&v10);
  }
  return (_DWORD)v14 == 0;
}

```

## disassembly

```asm
0x140002708  push    rbx
0x14000270a  push    rbp
0x14000270b  push    rsi
0x14000270c  push    rdi
0x14000270d  push    r14
0x14000270f  sub     rsp, 70h
0x140002713  mov     rax, cs:__security_cookie
0x14000271a  xor     rax, rsp
0x14000271d  mov     [rsp+98h+var_30], rax
0x140002722  mov     r14, r9
0x140002725  mov     rbx, rdx
0x140002728  mov     r9, rdx
0x14000272b  mov     dword ptr [rsp+98h+var_78], r14d
0x140002730  mov     rdx, [rcx+8]
0x140002734  mov     rbp, rcx
0x140002737  shr     r9, 20h
0x14000273b  lea     rcx, [rsp+98h+var_60]
0x140002740  mov     esi, r8d
0x140002743  call    wil_details_FeatureReporting_RecordUsageInCache
0x140002748  movups  xmm1, xmmword ptr [rax]
0x14000274b  movups  [rsp+98h+var_48], xmm1
0x140002750  movsd   xmm0, qword ptr [rax+10h]
0x140002755  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14000275c  movsd   [rsp+98h+var_38], xmm0
0x140002762  test    rax, rax
0x140002765  jz      short loc_140002782
0x140002767  mov     r9, [rbp+8]
0x14000276b  lea     rcx, [rsp+98h+var_48]
0x140002770  mov     [rsp+98h+var_78], rcx
0x140002775  mov     r8d, r14d
0x140002778  mov     ecx, [rbp+18h]
0x14000277b  mov     edx, esi
0x14000277d  call    _guard_dispatch_icall
0x140002782  bt      ebx, 0Ah
0x140002786  jnb     short loc_1400027C2
0x140002788  cmp     esi, 0FEh
0x14000278e  jz      short loc_1400027C2
0x140002790  mov     eax, [rbp+18h]
0x140002793  mov     [rsp+98h+var_68], 0
0x14000279c  mov     dword ptr [rsp+98h+var_68], eax
0x1400027a0  mov     word ptr [rsp+98h+var_68+4], si
0x1400027a5  bt      ebx, 0Bh
0x1400027a9  jnb     short loc_1400027B1
0x1400027ab  or      word ptr [rsp+98h+var_68+6], 1
0x1400027b1  lea     rcx, [rsp+98h+var_68]
0x1400027b6  call    cs:__imp_RtlNotifyFeatureUsage
0x1400027bd  nop     dword ptr [rax+rax+00h]
0x1400027c2  xor     eax, eax
0x1400027c4  cmp     dword ptr [rsp+98h+var_38], eax
0x1400027c8  setz    al
0x1400027cb  mov     rcx, [rsp+98h+var_30]
0x1400027d0  xor     rcx, rsp; StackCookie
0x1400027d3  call    __security_check_cookie
0x1400027d8  add     rsp, 70h
0x1400027dc  pop     r14
0x1400027de  pop     rdi
0x1400027df  pop     rsi
0x1400027e0  pop     rbp
0x1400027e1  pop     rbx
0x1400027e2  retn
```
