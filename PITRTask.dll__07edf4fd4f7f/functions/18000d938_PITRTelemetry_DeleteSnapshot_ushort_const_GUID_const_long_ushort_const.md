# PITRTelemetry_DeleteSnapshot(ushort const *,_GUID const *,long,ushort const *)

- ea: `0x18000d938`
- end: `0x18000da8c`
- name: `?PITRTelemetry_DeleteSnapshot@@YAXPEBGPEBU_GUID@@J0@Z`
- size: `340`
- prototype: `void __fastcall(const unsigned __int16 *, const struct _GUID *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000e16c`

## callees

- `0x180001008`
- `0x18000bbd0`
- `0x18000d938`
- `0x1800107c0`

## pseudocode

```c
void __fastcall PITRTelemetry_DeleteSnapshot(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  const struct _GUID *v6; // r8
  __int64 v7; // rax
  int v8; // [rsp+30h] [rbp-49h] BYREF
  __int64 v9; // [rsp+38h] [rbp-41h] BYREF
  __int128 v10; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v12; // [rsp+70h] [rbp-9h]
  __int64 v13; // [rsp+78h] [rbp-1h]
  const unsigned __int16 *v14; // [rsp+80h] [rbp+7h]
  int v15; // [rsp+88h] [rbp+Fh]
  int v16; // [rsp+8Ch] [rbp+13h]
  const struct _GUID *v17; // [rsp+90h] [rbp+17h]
  __int64 v18; // [rsp+98h] [rbp+1Fh]
  int *v19; // [rsp+A0h] [rbp+27h]
  __int64 v20; // [rsp+A8h] [rbp+2Fh]
  const wchar_t *v21; // [rsp+B0h] [rbp+37h]
  __int64 v22; // [rsp+B8h] [rbp+3Fh]

  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
  {
    v6 = (const struct _GUID *)&v10;
    v10 = 0;
    if ( a2 )
      v6 = a2;
    if ( (unsigned int)dword_18001B000 > 4
      && (qword_18001B010 & 0x800000000000LL) != 0
      && (qword_18001B018 & 0x800000000000LL) == qword_18001B018 )
    {
      v8 = 0;
      v22 = 38;
      if ( !a1 )
        a1 = (const unsigned __int16 *)qword_180015BA0;
      v20 = 4;
      v17 = v6;
      v9 = 0x80000000LL;
      v21 = L"MaintenanceCleanup";
      v19 = &v8;
      v7 = -1;
      v18 = 16;
      do
        ++v7;
      while ( a1[v7] );
      v16 = 0;
      v15 = 2 * v7 + 2;
      v14 = a1;
      v12 = &v9;
      v13 = 8;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_18001B000, (int)&word_1800172DA, 0, 0, 7u, &v11);
    }
  }
}

```

## disassembly

```asm
0x18000d938  mov     [rsp-8+arg_0], rbx
0x18000d93d  mov     [rsp-8+arg_8], rdi
0x18000d942  push    rbp
0x18000d943  lea     rbp, [rsp-57h]
0x18000d948  sub     rsp, 0D0h
0x18000d94f  mov     rax, cs:__security_cookie
0x18000d956  xor     rax, rsp
0x18000d959  mov     [rbp+57h+var_10], rax
0x18000d95d  mov     rdi, rdx
0x18000d960  mov     rbx, rcx
0x18000d963  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000d96a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000d96f  xor     edx, edx
0x18000d971  test    al, al
0x18000d973  jnz     loc_18000DA6B
0x18000d979  mov     eax, cs:dword_18001B000
0x18000d97f  lea     r8, [rbp+57h+var_90]
0x18000d983  test    rdi, rdi
0x18000d986  xorps   xmm0, xmm0
0x18000d989  movups  [rbp+57h+var_90], xmm0
0x18000d98d  cmovnz  r8, rdi
0x18000d991  cmp     eax, 4
0x18000d994  jbe     loc_18000DA6B
0x18000d99a  mov     rcx, cs:qword_18001B018
0x18000d9a1  mov     r9, 800000000000h
0x18000d9ab  mov     rax, cs:qword_18001B010
0x18000d9b2  test    r9, rax
0x18000d9b5  jz      loc_18000DA6B
0x18000d9bb  mov     rax, rcx
0x18000d9be  and     rax, r9
0x18000d9c1  cmp     rax, rcx
0x18000d9c4  jnz     loc_18000DA6B
0x18000d9ca  test    rbx, rbx
0x18000d9cd  mov     [rbp+57h+var_A0], edx
0x18000d9d0  lea     rax, qword_180015BA0
0x18000d9d7  mov     [rbp+57h+var_18], 26h ; '&'
0x18000d9df  cmovz   rbx, rax
0x18000d9e3  mov     [rbp+57h+var_28], 4
0x18000d9eb  mov     eax, 80000000h
0x18000d9f0  mov     [rbp+57h+var_40], r8
0x18000d9f4  mov     [rbp+57h+var_98], rax
0x18000d9f8  lea     rax, aMaintenancecle; "MaintenanceCleanup"
0x18000d9ff  mov     [rbp+57h+var_20], rax
0x18000da03  lea     rax, [rbp+57h+var_A0]
0x18000da07  mov     [rbp+57h+var_30], rax
0x18000da0b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000da0f  mov     [rbp+57h+var_38], 10h
0x18000da17  inc     rax
0x18000da1a  cmp     [rbx+rax*2], dx
0x18000da1e  jnz     short loc_18000DA17
0x18000da20  lea     eax, ds:2[rax*2]
0x18000da27  mov     [rbp+57h+var_44], edx
0x18000da2a  mov     [rbp+57h+var_48], eax
0x18000da2d  lea     rdx, word_1800172DA; int
0x18000da34  lea     rax, [rbp+57h+var_98]
0x18000da38  mov     [rbp+57h+var_50], rbx
0x18000da3c  mov     [rbp+57h+var_60], rax
0x18000da40  lea     rcx, dword_18001B000; int
0x18000da47  lea     rax, [rbp+57h+var_80]
0x18000da4b  mov     [rbp+57h+var_58], 8
0x18000da53  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x18000da58  xor     r9d, r9d; int
0x18000da5b  xor     r8d, r8d; int
0x18000da5e  mov     [rsp+0D0h+var_B0], 7; ULONG
0x18000da66  call    _tlgWriteTransfer_EventWriteTransfer
0x18000da6b  mov     rcx, [rbp+57h+var_10]
0x18000da6f  xor     rcx, rsp; StackCookie
0x18000da72  call    __security_check_cookie
0x18000da77  lea     r11, [rsp+0D0h+var_s0]
0x18000da7f  mov     rbx, [r11+10h]
0x18000da83  mov     rdi, [r11+18h]
0x18000da87  mov     rsp, r11
0x18000da8a  pop     rbp
0x18000da8b  retn
```
