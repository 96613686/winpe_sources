# PITRTelemetry_CreateSnapshot(ushort const *,_FILETIME,_FILETIME,ulong,_GUID const *,long,__int64)

- ea: `0x18000d750`
- end: `0x18000d92f`
- name: `?PITRTelemetry_CreateSnapshot@@YAXPEBGU_FILETIME@@1KPEBU_GUID@@J_J@Z`
- size: `479`
- prototype: `void __fastcall(const unsigned __int16 *, struct _FILETIME, struct _FILETIME, int, const struct _GUID *, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a4f0`

## callees

- `0x180001008`
- `0x18000bbd0`
- `0x18000d750`
- `0x18000ece8`
- `0x1800107c0`

## pseudocode

```c
void __fastcall PITRTelemetry_CreateSnapshot(
        const unsigned __int16 *a1,
        struct _FILETIME a2,
        struct _FILETIME a3,
        int a4,
        const struct _GUID *a5,
        int a6,
        __int64 a7)
{
  const struct _GUID *v11; // rdx
  __int64 v12; // rax
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME v16; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v17; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+ACh] [rbp-54h]
  struct _FILETIME *v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp-48h]
  struct _FILETIME *v28; // [rsp+C0h] [rbp-40h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  int *v30; // [rsp+D0h] [rbp-30h]
  __int64 v31; // [rsp+D8h] [rbp-28h]
  const struct _GUID *v32; // [rsp+E0h] [rbp-20h]
  __int64 v33; // [rsp+E8h] [rbp-18h]
  int *v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+F8h] [rbp-8h]
  __int64 *v36; // [rsp+100h] [rbp+0h]
  __int64 v37; // [rsp+108h] [rbp+8h]

  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
    || (int)PITRTelemetryInitialize() >= 0 && dword_18001BFA0 && (unsigned int)dword_18001B000 > 4 )
  {
    v11 = (const struct _GUID *)&v19;
    v19 = 0;
    if ( a5 )
      v11 = a5;
    if ( (unsigned int)dword_18001B000 > 4
      && (qword_18001B010 & 0x800000000000LL) != 0
      && (qword_18001B018 & 0x800000000000LL) == qword_18001B018 )
    {
      v15 = a7;
      v13 = a6;
      if ( !a1 )
        a1 = (const unsigned __int16 *)qword_180015BA0;
      v14 = a4;
      v16 = a3;
      v18 = 0x80000000LL;
      v36 = &v15;
      v34 = &v13;
      v30 = &v14;
      v28 = &v16;
      v26 = &v17;
      v12 = -1;
      v17 = a2;
      v37 = 8;
      v35 = 4;
      v32 = v11;
      v33 = 16;
      v31 = 4;
      v29 = 8;
      v27 = 8;
      do
        ++v12;
      while ( a1[v12] );
      v23 = a1;
      v24 = 2 * v12 + 2;
      v25 = 0;
      v21 = &v18;
      v22 = 8;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_18001B000, (int)&unk_180017248, 0, 0, 0xAu, &v20);
    }
  }
}

```

## disassembly

```asm
0x18000d750  mov     [rsp-8+arg_0], rbx
0x18000d755  push    rbp
0x18000d756  push    rsi
0x18000d757  push    rdi
0x18000d758  push    r14
0x18000d75a  push    r15
0x18000d75c  lea     rbp, [rsp-20h]
0x18000d761  sub     rsp, 120h
0x18000d768  mov     rax, cs:__security_cookie
0x18000d76f  xor     rax, rsp
0x18000d772  mov     [rbp+40h+var_30], rax
0x18000d776  mov     r14d, r9d
0x18000d779  mov     rdi, r8
0x18000d77c  mov     rbx, rdx
0x18000d77f  mov     rsi, rcx
0x18000d782  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000d789  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000d78e  xor     r15d, r15d
0x18000d791  test    al, al
0x18000d793  jz      short loc_18000D7BE
0x18000d795  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x18000d79a  test    eax, eax
0x18000d79c  js      loc_18000D90C
0x18000d7a2  cmp     cs:dword_18001BFA0, r15d
0x18000d7a9  jz      loc_18000D90C
0x18000d7af  mov     eax, cs:dword_18001B000
0x18000d7b5  cmp     eax, 4
0x18000d7b8  jbe     loc_18000D90C
0x18000d7be  mov     rax, [rbp+40h+arg_20]
0x18000d7c2  lea     rdx, [rsp+140h+var_E8]
0x18000d7c7  test    rax, rax
0x18000d7ca  xorps   xmm0, xmm0
0x18000d7cd  movups  [rsp+140h+var_E8], xmm0
0x18000d7d2  cmovnz  rdx, rax
0x18000d7d6  mov     eax, cs:dword_18001B000
0x18000d7dc  cmp     eax, 4
0x18000d7df  jbe     loc_18000D90C
0x18000d7e5  mov     rcx, cs:qword_18001B018
0x18000d7ec  mov     r8, 800000000000h
0x18000d7f6  mov     rax, cs:qword_18001B010
0x18000d7fd  test    r8, rax
0x18000d800  jz      loc_18000D90C
0x18000d806  mov     rax, rcx
0x18000d809  and     rax, r8
0x18000d80c  cmp     rax, rcx
0x18000d80f  jnz     loc_18000D90C
0x18000d815  mov     rax, [rbp+40h+arg_30]
0x18000d81c  test    rsi, rsi
0x18000d81f  mov     [rsp+140h+var_108], rax
0x18000d824  mov     eax, [rbp+40h+arg_28]
0x18000d827  mov     [rsp+140h+var_110], eax
0x18000d82b  lea     rax, qword_180015BA0
0x18000d832  cmovz   rsi, rax
0x18000d836  mov     [rsp+140h+var_10C], r14d
0x18000d83b  mov     eax, 80000000h
0x18000d840  mov     [rsp+140h+var_100], rdi
0x18000d845  mov     [rsp+140h+var_F0], rax
0x18000d84a  lea     rax, [rsp+140h+var_108]
0x18000d84f  mov     [rbp+40h+var_40], rax
0x18000d853  lea     rax, [rsp+140h+var_110]
0x18000d858  mov     [rbp+40h+var_50], rax
0x18000d85c  lea     rax, [rsp+140h+var_10C]
0x18000d861  mov     [rbp+40h+var_70], rax
0x18000d865  lea     rax, [rsp+140h+var_100]
0x18000d86a  mov     [rbp+40h+var_80], rax
0x18000d86e  lea     rax, [rsp+140h+var_F8]
0x18000d873  mov     [rbp+40h+var_90], rax
0x18000d877  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d87b  mov     [rsp+140h+var_F8], rbx
0x18000d880  mov     [rbp+40h+var_38], 8
0x18000d888  mov     [rbp+40h+var_48], 4
0x18000d890  mov     [rbp+40h+var_60], rdx
0x18000d894  mov     [rbp+40h+var_58], 10h
0x18000d89c  mov     [rbp+40h+var_68], 4
0x18000d8a4  mov     [rbp+40h+var_78], 8
0x18000d8ac  mov     [rbp+40h+var_88], 8
0x18000d8b4  inc     rax
0x18000d8b7  cmp     [rsi+rax*2], r15w
0x18000d8bc  jnz     short loc_18000D8B4
0x18000d8be  lea     eax, ds:2[rax*2]
0x18000d8c5  mov     [rbp+40h+var_A0], rsi
0x18000d8c9  mov     [rbp+40h+var_98], eax
0x18000d8cc  lea     rdx, unk_180017248; int
0x18000d8d3  lea     rax, [rsp+140h+var_F0]
0x18000d8d8  mov     [rbp+40h+var_94], r15d
0x18000d8dc  mov     [rbp+40h+var_B0], rax
0x18000d8e0  lea     rcx, dword_18001B000; int
0x18000d8e7  lea     rax, [rsp+140h+var_D0]
0x18000d8ec  mov     [rbp+40h+var_A8], 8
0x18000d8f4  mov     [rsp+140h+var_118], rax; PEVENT_DATA_DESCRIPTOR
0x18000d8f9  xor     r9d, r9d; int
0x18000d8fc  xor     r8d, r8d; int
0x18000d8ff  mov     [rsp+140h+var_120], 0Ah; ULONG
0x18000d907  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d90c  mov     rcx, [rbp+40h+var_30]
0x18000d910  xor     rcx, rsp; StackCookie
0x18000d913  call    __security_check_cookie
0x18000d918  mov     rbx, [rsp+140h+arg_0]
0x18000d920  add     rsp, 120h
0x18000d927  pop     r15
0x18000d929  pop     r14
0x18000d92b  pop     rdi
0x18000d92c  pop     rsi
0x18000d92d  pop     rbp
0x18000d92e  retn
```
