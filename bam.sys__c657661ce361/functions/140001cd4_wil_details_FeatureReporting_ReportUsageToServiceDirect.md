# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140001cd4`
- end: `0x140001dbd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140001c58`

## callees

- `0x140001ad4`
- `0x140001cd4`
- `0x1400026d0`
- `0x140002710`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140001d88`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140001d88`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  _DWORD *v5; // rax
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         (volatile signed __int32 *)&Feature_UserPresenceThrottling__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *((_QWORD *)v5 + 2);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(42995998, a3, 1, &Feature_UserPresenceThrottling__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 42995998;
    WORD2(v7) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v7) |= 1u;
    RtlNotifyFeatureUsage(&v7);
  }
  return (_DWORD)v10 == 0;
}

```

## disassembly

```asm
0x140001cd4  mov     [rsp+arg_0], rbx
0x140001cd9  mov     [rsp+arg_18], rsi
0x140001cde  push    rdi
0x140001cdf  sub     rsp, 70h
0x140001ce3  mov     rax, cs:__security_cookie
0x140001cea  xor     rax, rsp
0x140001ced  mov     [rsp+78h+var_10], rax
0x140001cf2  mov     r9, rdx
0x140001cf5  lea     rcx, [rsp+78h+var_40]
0x140001cfa  mov     rbx, rdx
0x140001cfd  shr     r9, 20h
0x140001d01  mov     rdx, cs:off_140006B78
0x140001d08  mov     edi, r8d
0x140001d0b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140001d10  mov     esi, 1
0x140001d15  movups  xmm1, xmmword ptr [rax]
0x140001d18  movups  [rsp+78h+var_28], xmm1
0x140001d1d  movsd   xmm0, qword ptr [rax+10h]
0x140001d22  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140001d29  movsd   [rsp+78h+var_18], xmm0
0x140001d2f  test    rax, rax
0x140001d32  jz      short loc_140001D54
0x140001d34  mov     r9, cs:off_140006B78
0x140001d3b  lea     rcx, [rsp+78h+var_28]
0x140001d40  mov     [rsp+78h+var_58], rcx
0x140001d45  mov     r8d, esi
0x140001d48  mov     ecx, 290111Eh
0x140001d4d  mov     edx, edi
0x140001d4f  call    _guard_dispatch_icall
0x140001d54  bt      ebx, 0Ah
0x140001d58  jnb     short loc_140001D94
0x140001d5a  cmp     edi, 0FEh
0x140001d60  jz      short loc_140001D94
0x140001d62  mov     [rsp+78h+var_48], 0
0x140001d6b  mov     dword ptr [rsp+78h+var_48], 290111Eh
0x140001d73  mov     word ptr [rsp+78h+var_48+4], di
0x140001d78  bt      ebx, 0Bh
0x140001d7c  jnb     short loc_140001D83
0x140001d7e  or      word ptr [rsp+78h+var_48+6], si
0x140001d83  lea     rcx, [rsp+78h+var_48]
0x140001d88  call    cs:__imp_RtlNotifyFeatureUsage
0x140001d8f  nop     dword ptr [rax+rax+00h]
0x140001d94  xor     eax, eax
0x140001d96  cmp     dword ptr [rsp+78h+var_18], eax
0x140001d9a  setz    al
0x140001d9d  mov     rcx, [rsp+78h+var_10]
0x140001da2  xor     rcx, rsp; StackCookie
0x140001da5  call    __security_check_cookie
0x140001daa  lea     r11, [rsp+78h+var_8]
0x140001daf  mov     rbx, [r11+10h]
0x140001db3  mov     rsi, [r11+28h]
0x140001db7  mov     rsp, r11
0x140001dba  pop     rdi
0x140001dbb  retn
```
