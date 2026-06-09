# TelCacheProvider::ShouldForceFullSyncForCommercial(bool)

- ea: `0x18001ac34`
- end: `0x18001ade6`
- name: `?ShouldForceFullSyncForCommercial@TelCacheProvider@@AEAAH_N@Z`
- size: `434`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aa44`

## callees

- `0x180005890`
- `0x180006938`
- `0x180012c20`
- `0x18001ac34`
- `0x1800295dc`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ac93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ac93`

## string_xrefs

- `0x18001acb2`: `commercialId`
- `0x18001ad7d`: `commercialId`
- `0x18001ad02`: `Full sync may be needed because of Commercial ID change`
- `0x18001ad5f`: `Full sync may be needed because of Commercial 45 day sync policy`
- `0x18001ad6c`: `TelCacheProvider::ShouldForceFullSyncForCommercial`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForCommercial(TelCacheProvider *this, char a2)
{
  unsigned int v3; // esi
  const unsigned __int16 *CommercialId; // r14
  struct _FILETIME v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // r9
  unsigned __int16 *v9; // rax
  int v10; // r8d
  int v11; // ecx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  int v15; // [rsp+30h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-41h] BYREF
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  _WORD v18[40]; // [rsp+50h] [rbp-29h] BYREF

  v3 = 0;
  CommercialId = Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId();
  memset_0(v18, 0, sizeof(v18));
  v15 = 40;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = SystemTimeAsFileTime;
  if ( !a2 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, int *))(**((_QWORD **)this + 11) + 56LL))(
           *((_QWORD *)this + 11),
           L"commercialId",
           v18,
           &v15);
    v8 = v7;
    if ( v7 == -2147024894 )
      v18[0] = 0;
    v9 = v18;
    do
    {
      v10 = *(unsigned __int16 *)((char *)v9 + (char *)CommercialId - (char *)v18);
      v11 = *v9 - v10;
      if ( v11 )
        break;
      ++v9;
    }
    while ( v10 );
    if ( v11 )
    {
      v3 = 1;
      if ( (int)v8 >= 0 )
        AslLogCallPrintf(
          3,
          "TelCacheProvider::ShouldForceFullSyncForCommercial",
          2004,
          "Full sync may be needed because of Commercial ID change");
    }
    else
    {
      if ( !*CommercialId )
        return v3;
      v12 = *((_QWORD *)this + 11);
      v17 = 0;
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *, __int64))(*(_QWORD *)v12 + 64LL))(
             v12,
             L"lastFullSync",
             &v17,
             v8) < 0 )
      {
        v3 = 1;
        AslLogCallPrintf(
          3,
          "TelCacheProvider::ShouldForceFullSyncForCommercial",
          2018,
          "Full sync may be needed because of Commercial 45 day sync policy");
      }
      else
      {
        LOBYTE(v3) = (unsigned __int64)(*(_QWORD *)&v6 - v17) > 0x235C7496C000LL;
        if ( (unsigned __int64)(*(_QWORD *)&v6 - v17) <= 0x235C7496C000LL )
          return v3;
      }
    }
  }
  if ( *CommercialId )
    v13 = CommercialId;
  else
    v13 = 0;
  (*(void (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *))(**((_QWORD **)this + 11) + 80LL))(
    *((_QWORD *)this + 11),
    L"commercialId",
    v13);
  (*(void (__fastcall **)(_QWORD, const wchar_t *, struct _FILETIME))(**((_QWORD **)this + 11) + 88LL))(
    *((_QWORD *)this + 11),
    L"lastFullSync",
    v6);
  return v3;
}

```

## disassembly

```asm
0x18001ac34  mov     [rsp-8+arg_8], rbx
0x18001ac39  mov     [rsp-8+arg_10], rsi
0x18001ac3e  push    rbp
0x18001ac3f  push    rdi
0x18001ac40  push    r12
0x18001ac42  push    r14
0x18001ac44  push    r15
0x18001ac46  lea     rbp, [rsp-37h]
0x18001ac4b  sub     rsp, 0B0h
0x18001ac52  mov     rax, cs:__security_cookie
0x18001ac59  xor     rax, rsp
0x18001ac5c  mov     [rbp+57h+var_30], rax
0x18001ac60  xor     r12d, r12d
0x18001ac63  mov     dil, dl
0x18001ac66  mov     esi, r12d
0x18001ac69  mov     r15, rcx
0x18001ac6c  call    ?GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ; Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)
0x18001ac71  xor     edx, edx; Val
0x18001ac73  lea     r8d, [r12+50h]; Size
0x18001ac78  lea     rcx, [rbp+57h+var_80]; void *
0x18001ac7c  mov     r14, rax
0x18001ac7f  call    memset_0
0x18001ac84  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001ac88  mov     [rbp+57h+var_A0], 28h ; '('
0x18001ac8f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18001ac93  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ac99  mov     rbx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18001ac9d  test    dil, dil
0x18001aca0  jnz     loc_18001AD7D
0x18001aca6  mov     rcx, [r15+58h]
0x18001acaa  lea     r9, [rbp+57h+var_A0]
0x18001acae  lea     r8, [rbp+57h+var_80]
0x18001acb2  lea     rdx, aCommercialid_0; "commercialId"
0x18001acb9  mov     rax, [rcx]
0x18001acbc  mov     rax, [rax+38h]
0x18001acc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acc5  mov     r9d, eax
0x18001acc8  cmp     eax, 80070002h
0x18001accd  jnz     short loc_18001ACD4
0x18001accf  mov     [rbp+57h+var_80], r12w
0x18001acd4  lea     rax, [rbp+57h+var_80]
0x18001acd8  mov     rdx, r14
0x18001acdb  sub     rdx, rax
0x18001acde  movzx   ecx, word ptr [rax]
0x18001ace1  movzx   r8d, word ptr [rax+rdx]
0x18001ace6  sub     ecx, r8d
0x18001ace9  jnz     short loc_18001ACF4
0x18001aceb  add     rax, 2
0x18001acef  test    r8d, r8d
0x18001acf2  jnz     short loc_18001ACDE
0x18001acf4  test    ecx, ecx
0x18001acf6  jz      short loc_18001AD11
0x18001acf8  mov     esi, 1
0x18001acfd  test    r9d, r9d
0x18001ad00  js      short loc_18001AD7D
0x18001ad02  lea     r9, aFullSyncMayBeN_3; "Full sync may be needed because of Comm"...
0x18001ad09  mov     r8d, 7D4h
0x18001ad0f  jmp     short loc_18001AD6C
0x18001ad11  cmp     [r14], r12w
0x18001ad15  jz      loc_18001ADBC
0x18001ad1b  mov     rcx, [r15+58h]
0x18001ad1f  lea     r8, [rbp+57h+var_90]
0x18001ad23  mov     [rbp+57h+var_90], r12
0x18001ad27  lea     rdx, aLastfullsync; "lastFullSync"
0x18001ad2e  mov     rax, [rcx]
0x18001ad31  mov     rax, [rax+40h]
0x18001ad35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad3a  test    eax, eax
0x18001ad3c  js      short loc_18001AD5A
0x18001ad3e  mov     rax, rbx
0x18001ad41  mov     rcx, 235C7496C000h
0x18001ad4b  sub     rax, [rbp+57h+var_90]
0x18001ad4f  cmp     rax, rcx
0x18001ad52  setnbe  sil
0x18001ad56  jbe     short loc_18001ADBC
0x18001ad58  jmp     short loc_18001AD7D
0x18001ad5a  mov     esi, 1
0x18001ad5f  lea     r9, aFullSyncMayBeN; "Full sync may be needed because of Comm"...
0x18001ad66  mov     r8d, 7E2h
0x18001ad6c  lea     rdx, aTelcacheprovid_23; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18001ad73  mov     ecx, 3
0x18001ad78  call    AslLogCallPrintf
0x18001ad7d  lea     rdx, aCommercialid_0; "commercialId"
0x18001ad84  mov     rcx, [r15+58h]
0x18001ad88  mov     rax, [rcx]
0x18001ad8b  mov     rax, [rax+50h]
0x18001ad8f  cmp     [r14], r12w
0x18001ad93  jz      short loc_18001AD9A
0x18001ad95  mov     r8, r14
0x18001ad98  jmp     short loc_18001AD9D
0x18001ad9a  xor     r8d, r8d
0x18001ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ada2  mov     rcx, [r15+58h]
0x18001ada6  lea     rdx, aLastfullsync; "lastFullSync"
0x18001adad  mov     r8, [rcx]
0x18001adb0  mov     rax, [r8+58h]
0x18001adb4  mov     r8, rbx
0x18001adb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adbc  mov     eax, esi
0x18001adbe  mov     rcx, [rbp+57h+var_30]
0x18001adc2  xor     rcx, rsp; StackCookie
0x18001adc5  call    __security_check_cookie
0x18001adca  lea     r11, [rsp+0D0h+var_20]
0x18001add2  mov     rbx, [r11+38h]
0x18001add6  mov     rsi, [r11+40h]
0x18001adda  mov     rsp, r11
0x18001addd  pop     r15
0x18001addf  pop     r14
0x18001ade1  pop     r12
0x18001ade3  pop     rdi
0x18001ade4  pop     rbp
0x18001ade5  retn
```
