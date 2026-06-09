# telemetryutil::etl::TelemetrySession::BuildTraceFilePath(ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x18000fe60`
- end: `0x18000ff4a`
- name: `?BuildTraceFilePath@TelemetrySession@etl@telemetryutil@@CAJPEBG0PEAG_K@Z`
- size: `234`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000ff50`

## callees

- `0x180009620`
- `0x1800096e4`
- `0x18000bbd0`
- `0x18000fe60`

## pseudocode

```c
__int64 __fastcall telemetryutil::etl::TelemetrySession::BuildTraceFilePath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v7; // r8
  unsigned __int16 *v8; // rax
  __int64 v9; // r9
  int v10; // eax
  unsigned int v11; // ecx

  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    return 2147942450LL;
  if ( !a1 || !a2 || !a3 )
    return 2147500035LL;
  result = StringCchCopyW(a3, 0x400u, a1);
  if ( (int)result >= 0 )
  {
    v7 = 1024;
    v8 = a3;
    do
    {
      if ( !*v8 )
        break;
      ++v8;
      --v7;
    }
    while ( v7 );
    result = v7 == 0 ? 0x80070057 : 0;
    v9 = (1024 - v7) & -(__int64)(v7 != 0);
    if ( v7 )
    {
      if ( !v9 || a3[v9 - 1] == 92 || (result = StringCchCatW(a3, 0x400u, L"\\"), (int)result >= 0) )
      {
        v10 = StringCchCatW(a3, 0x400u, a2);
        v11 = 0;
        if ( v10 < 0 )
          return (unsigned int)v10;
        return v11;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fe60  push    rbx
0x18000fe62  push    rbp
0x18000fe63  push    rsi
0x18000fe64  push    rdi
0x18000fe65  sub     rsp, 28h
0x18000fe69  mov     rbx, r8
0x18000fe6c  mov     rsi, rdx
0x18000fe6f  mov     rdi, rcx
0x18000fe72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000fe79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000fe7e  xor     ebp, ebp
0x18000fe80  test    al, al
0x18000fe82  jz      loc_18000FF3C
0x18000fe88  test    rdi, rdi
0x18000fe8b  jz      loc_18000FF35
0x18000fe91  test    rsi, rsi
0x18000fe94  jz      loc_18000FF35
0x18000fe9a  test    rbx, rbx
0x18000fe9d  jz      loc_18000FF35
0x18000fea3  mov     r8, rdi; unsigned __int16 *
0x18000fea6  mov     rcx, rbx; unsigned __int16 *
0x18000fea9  mov     edi, 400h
0x18000feae  mov     edx, edi; unsigned __int64
0x18000feb0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000feb5  test    eax, eax
0x18000feb7  js      loc_18000FF41
0x18000febd  mov     r8d, edi
0x18000fec0  mov     rax, rbx
0x18000fec3  cmp     [rax], bp
0x18000fec6  jz      short loc_18000FED2
0x18000fec8  add     rax, 2
0x18000fecc  sub     r8, 1
0x18000fed0  jnz     short loc_18000FEC3
0x18000fed2  mov     rax, r8
0x18000fed5  mov     rdx, rdi
0x18000fed8  neg     rax
0x18000fedb  mov     rcx, r8
0x18000fede  sbb     eax, eax
0x18000fee0  sub     rdx, r8
0x18000fee3  not     eax
0x18000fee5  and     eax, 80070057h
0x18000feea  neg     rcx
0x18000feed  sbb     r9, r9
0x18000fef0  and     r9, rdx
0x18000fef3  test    r8, r8
0x18000fef6  jz      short loc_18000FF41
0x18000fef8  test    r9, r9
0x18000fefb  jz      short loc_18000FF1C
0x18000fefd  cmp     word ptr [rbx+r9*2-2], 5Ch ; '\'
0x18000ff04  jz      short loc_18000FF1C
0x18000ff06  lea     r8, asc_180014F80; "\\"
0x18000ff0d  mov     rdx, rdi; unsigned __int64
0x18000ff10  mov     rcx, rbx; unsigned __int16 *
0x18000ff13  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ff18  test    eax, eax
0x18000ff1a  js      short loc_18000FF41
0x18000ff1c  mov     r8, rsi; unsigned __int16 *
0x18000ff1f  mov     rdx, rdi; unsigned __int64
0x18000ff22  mov     rcx, rbx; unsigned __int16 *
0x18000ff25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ff2a  test    eax, eax
0x18000ff2c  mov     ecx, ebp
0x18000ff2e  cmovs   ecx, eax
0x18000ff31  mov     eax, ecx
0x18000ff33  jmp     short loc_18000FF41
0x18000ff35  mov     eax, 80004003h
0x18000ff3a  jmp     short loc_18000FF41
0x18000ff3c  mov     eax, 80070032h
0x18000ff41  add     rsp, 28h
0x18000ff45  pop     rdi
0x18000ff46  pop     rsi
0x18000ff47  pop     rbp
0x18000ff48  pop     rbx
0x18000ff49  retn
```
