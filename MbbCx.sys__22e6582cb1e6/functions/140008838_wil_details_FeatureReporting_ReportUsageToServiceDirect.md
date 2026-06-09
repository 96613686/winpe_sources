# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140008838`
- end: `0x140008912`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000870c`

## callees

- `0x140008430`
- `0x140008838`
- `0x140047e50`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400088e4`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x1400088e4`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  __int64 v6; // rax
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
  v12 = *(_QWORD *)(v6 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(*(unsigned int *)(a1 + 24), a3, 1, *(_QWORD *)(a1 + 8), &v11);
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
0x140008838  push    rbx
0x14000883a  push    rbp
0x14000883b  push    rsi
0x14000883c  push    rdi
0x14000883d  push    r14
0x14000883f  sub     rsp, 70h
0x140008843  mov     rax, cs:__security_cookie
0x14000884a  xor     rax, rsp
0x14000884d  mov     [rsp+98h+var_30], rax
0x140008852  mov     r9, rdx
0x140008855  mov     rbx, rdx
0x140008858  mov     rdx, [rcx+8]
0x14000885c  mov     rbp, rcx
0x14000885f  shr     r9, 20h
0x140008863  lea     rcx, [rsp+98h+var_60]
0x140008868  mov     esi, r8d
0x14000886b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140008870  mov     r14d, 1
0x140008876  movups  xmm1, xmmword ptr [rax]
0x140008879  movups  [rsp+98h+var_48], xmm1
0x14000887e  movsd   xmm0, qword ptr [rax+10h]
0x140008883  mov     rax, cs:g_wil_details_recordFeatureUsage
0x14000888a  movsd   [rsp+98h+var_38], xmm0
0x140008890  test    rax, rax
0x140008893  jz      short loc_1400088B0
0x140008895  mov     r9, [rbp+8]
0x140008899  lea     rcx, [rsp+98h+var_48]
0x14000889e  mov     [rsp+98h+var_78], rcx
0x1400088a3  mov     r8d, r14d
0x1400088a6  mov     ecx, [rbp+18h]
0x1400088a9  mov     edx, esi
0x1400088ab  call    _guard_dispatch_icall
0x1400088b0  bt      ebx, 0Ah
0x1400088b4  jnb     short loc_1400088F0
0x1400088b6  cmp     esi, 0FEh
0x1400088bc  jz      short loc_1400088F0
0x1400088be  mov     eax, [rbp+18h]
0x1400088c1  mov     [rsp+98h+var_68], 0
0x1400088ca  mov     dword ptr [rsp+98h+var_68], eax
0x1400088ce  mov     word ptr [rsp+98h+var_68+4], si
0x1400088d3  bt      ebx, 0Bh
0x1400088d7  jnb     short loc_1400088DF
0x1400088d9  or      word ptr [rsp+98h+var_68+6], r14w
0x1400088df  lea     rcx, [rsp+98h+var_68]
0x1400088e4  call    cs:__imp_RtlNotifyFeatureUsage
0x1400088eb  nop     dword ptr [rax+rax+00h]
0x1400088f0  xor     eax, eax
0x1400088f2  cmp     dword ptr [rsp+98h+var_38], eax
0x1400088f6  setz    al
0x1400088f9  mov     rcx, [rsp+98h+var_30]
0x1400088fe  xor     rcx, rsp; StackCookie
0x140008901  call    __security_check_cookie
0x140008906  add     rsp, 70h
0x14000890a  pop     r14
0x14000890c  pop     rdi
0x14000890d  pop     rsi
0x14000890e  pop     rbp
0x14000890f  pop     rbx
0x140008910  retn
```
