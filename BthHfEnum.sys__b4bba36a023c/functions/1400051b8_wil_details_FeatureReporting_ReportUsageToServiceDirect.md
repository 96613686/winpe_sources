# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1400051b8`
- end: `0x140005292`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140005130`

## callees

- `0x140004fac`
- `0x1400051b8`
- `0x14001adc0`
- `0x14001ae00`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140005264`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140005264`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int *v6; // rax
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h]
  _BYTE v10[24]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v11; // [rsp+50h] [rbp-48h] BYREF
  __int64 v12; // [rsp+60h] [rbp-38h]

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v6;
  v12 = *((_QWORD *)v6 + 2);
  if ( *(_QWORD *)&WPP_MAIN_CB.SectorSize )
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int128 *))&WPP_MAIN_CB.SectorSize)(
      *(unsigned int *)(a1 + 24),
      a3,
      1,
      *(_QWORD *)(a1 + 8),
      &v11);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = *(_DWORD *)(a1 + 24);
    v9 = (unsigned __int16)a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    RtlNotifyFeatureUsage(&v8);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x1400051b8  push    rbx
0x1400051ba  push    rbp
0x1400051bb  push    rsi
0x1400051bc  push    rdi
0x1400051bd  push    r14
0x1400051bf  sub     rsp, 70h
0x1400051c3  mov     rax, cs:__security_cookie
0x1400051ca  xor     rax, rsp
0x1400051cd  mov     [rsp+98h+var_30], rax
0x1400051d2  mov     r9, rdx
0x1400051d5  mov     rbx, rdx
0x1400051d8  mov     rdx, [rcx+8]
0x1400051dc  mov     rbp, rcx
0x1400051df  shr     r9, 20h
0x1400051e3  lea     rcx, [rsp+98h+var_60]
0x1400051e8  mov     esi, r8d
0x1400051eb  call    wil_details_FeatureReporting_RecordUsageInCache
0x1400051f0  mov     r14d, 1
0x1400051f6  movups  xmm1, xmmword ptr [rax]
0x1400051f9  movups  [rsp+98h+var_48], xmm1
0x1400051fe  movsd   xmm0, qword ptr [rax+10h]
0x140005203  mov     rax, qword ptr cs:WPP_MAIN_CB.SectorSize
0x14000520a  movsd   [rsp+98h+var_38], xmm0
0x140005210  test    rax, rax
0x140005213  jz      short loc_140005230
0x140005215  mov     r9, [rbp+8]
0x140005219  lea     rcx, [rsp+98h+var_48]
0x14000521e  mov     [rsp+98h+var_78], rcx
0x140005223  mov     r8d, r14d
0x140005226  mov     ecx, [rbp+18h]
0x140005229  mov     edx, esi
0x14000522b  call    _guard_dispatch_icall
0x140005230  bt      ebx, 0Ah
0x140005234  jnb     short loc_140005270
0x140005236  cmp     esi, 0FEh
0x14000523c  jz      short loc_140005270
0x14000523e  mov     eax, [rbp+18h]
0x140005241  mov     [rsp+98h+var_68], 0
0x14000524a  mov     dword ptr [rsp+98h+var_68], eax
0x14000524e  mov     word ptr [rsp+98h+var_68+4], si
0x140005253  bt      ebx, 0Bh
0x140005257  jnb     short loc_14000525F
0x140005259  or      word ptr [rsp+98h+var_68+6], r14w
0x14000525f  lea     rcx, [rsp+98h+var_68]
0x140005264  call    cs:__imp_RtlNotifyFeatureUsage
0x14000526b  nop     dword ptr [rax+rax+00h]
0x140005270  xor     eax, eax
0x140005272  cmp     dword ptr [rsp+98h+var_38], eax
0x140005276  setz    al
0x140005279  mov     rcx, [rsp+98h+var_30]
0x14000527e  xor     rcx, rsp; StackCookie
0x140005281  call    __security_check_cookie
0x140005286  add     rsp, 70h
0x14000528a  pop     r14
0x14000528c  pop     rdi
0x14000528d  pop     rsi
0x14000528e  pop     rbp
0x14000528f  pop     rbx
0x140005290  retn
```
