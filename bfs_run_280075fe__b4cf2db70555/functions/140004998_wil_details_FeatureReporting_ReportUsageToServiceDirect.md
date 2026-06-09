# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140004998`
- end: `0x140004a72`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140002760`
- `0x140004910`

## callees

- `0x14000478c`
- `0x140004998`
- `0x140013730`
- `0x140013770`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140004a44`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140004a44`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v5; // esi
  __int64 v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v5 = a3;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(v10, *(_QWORD *)(a1 + 8), a3, HIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *(_QWORD *)(v6 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), v5, 1, *(_QWORD *)(a1 + 8), &v11);
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x140004998  push    rbx
0x14000499a  push    rbp
0x14000499b  push    rsi
0x14000499c  push    rdi
0x14000499d  push    r14
0x14000499f  sub     rsp, 70h
0x1400049a3  mov     rax, cs:__security_cookie
0x1400049aa  xor     rax, rsp
0x1400049ad  mov     [rsp+98h+var_30], rax
0x1400049b2  mov     r9, rdx
0x1400049b5  mov     rbx, rdx
0x1400049b8  mov     rdx, [rcx+8]
0x1400049bc  mov     rbp, rcx
0x1400049bf  shr     r9, 20h
0x1400049c3  lea     rcx, [rsp+98h+var_60]
0x1400049c8  mov     esi, r8d
0x1400049cb  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400049d0  mov     r14d, 1
0x1400049d6  movups  xmm1, xmmword ptr [rax]
0x1400049d9  movups  [rsp+98h+var_48], xmm1
0x1400049de  movsd   xmm0, qword ptr [rax+10h]
0x1400049e3  mov     rax, cs:g_wil_details_recordFeatureUsage
0x1400049ea  movsd   [rsp+98h+var_38], xmm0
0x1400049f0  test    rax, rax
0x1400049f3  jz      short loc_140004A10
0x1400049f5  mov     r9, [rbp+8]
0x1400049f9  lea     rcx, [rsp+98h+var_48]
0x1400049fe  mov     [rsp+98h+var_78], rcx
0x140004a03  mov     r8d, r14d
0x140004a06  mov     ecx, [rbp+18h]
0x140004a09  mov     edx, esi
0x140004a0b  call    _guard_dispatch_icall
0x140004a10  bt      ebx, 0Ah
0x140004a14  jnb     short loc_140004A50
0x140004a16  cmp     esi, 0FEh
0x140004a1c  jz      short loc_140004A50
0x140004a1e  mov     eax, [rbp+18h]
0x140004a21  mov     [rsp+98h+var_68], 0
0x140004a2a  mov     dword ptr [rsp+98h+var_68], eax
0x140004a2e  mov     word ptr [rsp+98h+var_68+4], si
0x140004a33  bt      ebx, 0Bh
0x140004a37  jnb     short loc_140004A3F
0x140004a39  or      word ptr [rsp+98h+var_68+6], r14w
0x140004a3f  lea     rcx, [rsp+98h+var_68]
0x140004a44  call    cs:__imp_RtlNotifyFeatureUsage
0x140004a4b  nop     dword ptr [rax+rax+00h]
0x140004a50  xor     eax, eax
0x140004a52  cmp     dword ptr [rsp+98h+var_38], eax
0x140004a56  setz    al
0x140004a59  mov     rcx, [rsp+98h+var_30]
0x140004a5e  xor     rcx, rsp; StackCookie
0x140004a61  call    __security_check_cookie
0x140004a66  add     rsp, 70h
0x140004a6a  pop     r14
0x140004a6c  pop     rdi
0x140004a6d  pop     rsi
0x140004a6e  pop     rbp
0x140004a6f  pop     rbx
0x140004a70  retn
```
