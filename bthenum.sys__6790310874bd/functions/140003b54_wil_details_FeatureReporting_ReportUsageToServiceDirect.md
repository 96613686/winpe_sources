# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x140003b54`
- end: `0x140003c3d`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003a34`

## callees

- `0x140003758`
- `0x140003b54`
- `0x140007d00`
- `0x140007d40`

## import_xrefs

- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140003c08`
- `ntoskrnl!RtlNotifyFeatureUsage` at `0x140003c08`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  __int64 v5; // rax
  __int64 v7; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v8[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         (volatile signed __int32 *)&Feature_56664216__private_reporting,
         a3,
         SHIDWORD(a2));
  v9 = *(_OWORD *)v5;
  v10 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(56664216, a3, 1, &Feature_56664216__private_reporting, &v9);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 56664216;
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
0x140003b54  mov     [rsp+arg_0], rbx
0x140003b59  mov     [rsp+arg_18], rsi
0x140003b5e  push    rdi
0x140003b5f  sub     rsp, 70h
0x140003b63  mov     rax, cs:__security_cookie
0x140003b6a  xor     rax, rsp
0x140003b6d  mov     [rsp+78h+var_10], rax
0x140003b72  mov     r9, rdx
0x140003b75  lea     rcx, [rsp+78h+var_40]
0x140003b7a  mov     rbx, rdx
0x140003b7d  shr     r9, 20h
0x140003b81  mov     rdx, cs:off_140014728
0x140003b88  mov     edi, r8d
0x140003b8b  call    wil_details_FeatureReporting_RecordUsageInCache
0x140003b90  mov     esi, 1
0x140003b95  movups  xmm1, xmmword ptr [rax]
0x140003b98  movups  [rsp+78h+var_28], xmm1
0x140003b9d  movsd   xmm0, qword ptr [rax+10h]
0x140003ba2  mov     rax, cs:g_wil_details_recordFeatureUsage
0x140003ba9  movsd   [rsp+78h+var_18], xmm0
0x140003baf  test    rax, rax
0x140003bb2  jz      short loc_140003BD4
0x140003bb4  mov     r9, cs:off_140014728
0x140003bbb  lea     rcx, [rsp+78h+var_28]
0x140003bc0  mov     [rsp+78h+var_58], rcx
0x140003bc5  mov     r8d, esi
0x140003bc8  mov     ecx, 360A098h
0x140003bcd  mov     edx, edi
0x140003bcf  call    _guard_dispatch_icall
0x140003bd4  bt      ebx, 0Ah
0x140003bd8  jnb     short loc_140003C14
0x140003bda  cmp     edi, 0FEh
0x140003be0  jz      short loc_140003C14
0x140003be2  mov     [rsp+78h+var_48], 0
0x140003beb  mov     dword ptr [rsp+78h+var_48], 360A098h
0x140003bf3  mov     word ptr [rsp+78h+var_48+4], di
0x140003bf8  bt      ebx, 0Bh
0x140003bfc  jnb     short loc_140003C03
0x140003bfe  or      word ptr [rsp+78h+var_48+6], si
0x140003c03  lea     rcx, [rsp+78h+var_48]
0x140003c08  call    cs:__imp_RtlNotifyFeatureUsage
0x140003c0f  nop     dword ptr [rax+rax+00h]
0x140003c14  xor     eax, eax
0x140003c16  cmp     dword ptr [rsp+78h+var_18], eax
0x140003c1a  setz    al
0x140003c1d  mov     rcx, [rsp+78h+var_10]
0x140003c22  xor     rcx, rsp; StackCookie
0x140003c25  call    __security_check_cookie
0x140003c2a  lea     r11, [rsp+78h+var_8]
0x140003c2f  mov     rbx, [r11+10h]
0x140003c33  mov     rsi, [r11+28h]
0x140003c37  mov     rsp, r11
0x140003c3a  pop     rdi
0x140003c3b  retn
```
