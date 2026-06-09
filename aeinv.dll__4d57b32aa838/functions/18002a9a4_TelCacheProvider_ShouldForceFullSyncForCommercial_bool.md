# TelCacheProvider::ShouldForceFullSyncForCommercial(bool)

- ea: `0x18002a9a4`
- end: `0x18002ab56`
- name: `?ShouldForceFullSyncForCommercial@TelCacheProvider@@AEAAH_N@Z`
- size: `434`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066814`

## callees

- `0x1800197d4`
- `0x18002a9a4`
- `0x180053728`
- `0x180059920`
- `0x18005a8bc`
- `0x180130010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002aa03`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002aa03`

## string_xrefs

- `0x18002aa22`: `commercialId`
- `0x18002aaed`: `commercialId`
- `0x18002aacf`: `Full sync may be needed because of Commercial 45 day sync policy`
- `0x18002aadc`: `TelCacheProvider::ShouldForceFullSyncForCommercial`
- `0x18002aa72`: `Full sync may be needed because of Commercial ID change`

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
  const char *v12; // r9
  int v13; // r8d
  __int64 v14; // rcx
  const unsigned __int16 *v15; // r8
  int v17; // [rsp+30h] [rbp-49h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-41h] BYREF
  __int64 v19; // [rsp+40h] [rbp-39h] BYREF
  _WORD v20[40]; // [rsp+50h] [rbp-29h] BYREF

  v3 = 0;
  CommercialId = Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId();
  memset_0(v20, 0, sizeof(v20));
  v17 = 40;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = SystemTimeAsFileTime;
  if ( !a2 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _WORD *, int *))(**((_QWORD **)this + 11) + 56LL))(
           *((_QWORD *)this + 11),
           L"commercialId",
           v20,
           &v17);
    v8 = v7;
    if ( v7 == -2147024894 )
      v20[0] = 0;
    v9 = v20;
    do
    {
      v10 = *(unsigned __int16 *)((char *)v9 + (char *)CommercialId - (char *)v20);
      v11 = *v9 - v10;
      if ( v11 )
        break;
      ++v9;
    }
    while ( v10 );
    if ( !v11 )
    {
      if ( !*CommercialId )
        return v3;
      v14 = *((_QWORD *)this + 11);
      v19 = 0;
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *, __int64))(*(_QWORD *)v14 + 64LL))(
             v14,
             L"lastFullSync",
             &v19,
             v8) >= 0 )
      {
        LOBYTE(v3) = (unsigned __int64)(*(_QWORD *)&v6 - v19) > 0x235C7496C000LL;
        if ( (unsigned __int64)(*(_QWORD *)&v6 - v19) <= 0x235C7496C000LL )
          return v3;
        goto LABEL_16;
      }
      v3 = 1;
      v12 = "Full sync may be needed because of Commercial 45 day sync policy";
      v13 = 2018;
      goto LABEL_15;
    }
    v3 = 1;
    if ( (int)v8 >= 0 )
    {
      v12 = "Full sync may be needed because of Commercial ID change";
      v13 = 2004;
LABEL_15:
      AslLogCallPrintf(3, (unsigned int)"TelCacheProvider::ShouldForceFullSyncForCommercial", v13, (_DWORD)v12);
    }
  }
LABEL_16:
  if ( *CommercialId )
    v15 = CommercialId;
  else
    v15 = 0;
  (*(void (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *))(**((_QWORD **)this + 11) + 80LL))(
    *((_QWORD *)this + 11),
    L"commercialId",
    v15);
  (*(void (__fastcall **)(_QWORD, const wchar_t *, struct _FILETIME))(**((_QWORD **)this + 11) + 88LL))(
    *((_QWORD *)this + 11),
    L"lastFullSync",
    v6);
  return v3;
}

```

## disassembly

```asm
0x18002a9a4  mov     [rsp-8+arg_8], rbx
0x18002a9a9  mov     [rsp-8+arg_10], rsi
0x18002a9ae  push    rbp
0x18002a9af  push    rdi
0x18002a9b0  push    r12
0x18002a9b2  push    r14
0x18002a9b4  push    r15
0x18002a9b6  lea     rbp, [rsp-37h]
0x18002a9bb  sub     rsp, 0B0h
0x18002a9c2  mov     rax, cs:__security_cookie
0x18002a9c9  xor     rax, rsp
0x18002a9cc  mov     [rbp+57h+var_30], rax
0x18002a9d0  xor     r12d, r12d
0x18002a9d3  mov     dil, dl
0x18002a9d6  mov     esi, r12d
0x18002a9d9  mov     r15, rcx
0x18002a9dc  call    ?GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ; Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)
0x18002a9e1  xor     edx, edx; Val
0x18002a9e3  lea     r8d, [r12+50h]; Size
0x18002a9e8  lea     rcx, [rbp+57h+var_80]; void *
0x18002a9ec  mov     r14, rax
0x18002a9ef  call    memset_0
0x18002a9f4  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a9f8  mov     [rbp+57h+var_A0], 28h ; '('
0x18002a9ff  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x18002aa03  call    cs:__imp_GetSystemTimeAsFileTime
0x18002aa09  mov     rbx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18002aa0d  test    dil, dil
0x18002aa10  jnz     loc_18002AAED
0x18002aa16  mov     rcx, [r15+58h]
0x18002aa1a  lea     r9, [rbp+57h+var_A0]
0x18002aa1e  lea     r8, [rbp+57h+var_80]
0x18002aa22  lea     rdx, aCommercialid_0; "commercialId"
0x18002aa29  mov     rax, [rcx]
0x18002aa2c  mov     rax, [rax+38h]
0x18002aa30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa35  mov     r9d, eax
0x18002aa38  cmp     eax, 80070002h
0x18002aa3d  jnz     short loc_18002AA44
0x18002aa3f  mov     [rbp+57h+var_80], r12w
0x18002aa44  lea     rax, [rbp+57h+var_80]
0x18002aa48  mov     rdx, r14
0x18002aa4b  sub     rdx, rax
0x18002aa4e  movzx   ecx, word ptr [rax]
0x18002aa51  movzx   r8d, word ptr [rax+rdx]
0x18002aa56  sub     ecx, r8d
0x18002aa59  jnz     short loc_18002AA64
0x18002aa5b  add     rax, 2
0x18002aa5f  test    r8d, r8d
0x18002aa62  jnz     short loc_18002AA4E
0x18002aa64  test    ecx, ecx
0x18002aa66  jz      short loc_18002AA81
0x18002aa68  mov     esi, 1
0x18002aa6d  test    r9d, r9d
0x18002aa70  js      short loc_18002AAED
0x18002aa72  lea     r9, aFullSyncMayBeN_3; "Full sync may be needed because of Comm"...
0x18002aa79  mov     r8d, 7D4h
0x18002aa7f  jmp     short loc_18002AADC
0x18002aa81  cmp     [r14], r12w
0x18002aa85  jz      loc_18002AB2C
0x18002aa8b  mov     rcx, [r15+58h]
0x18002aa8f  lea     r8, [rbp+57h+var_90]
0x18002aa93  mov     [rbp+57h+var_90], r12
0x18002aa97  lea     rdx, aLastfullsync; "lastFullSync"
0x18002aa9e  mov     rax, [rcx]
0x18002aaa1  mov     rax, [rax+40h]
0x18002aaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaaa  test    eax, eax
0x18002aaac  js      short loc_18002AACA
0x18002aaae  mov     rax, rbx
0x18002aab1  mov     rcx, 235C7496C000h
0x18002aabb  sub     rax, [rbp+57h+var_90]
0x18002aabf  cmp     rax, rcx
0x18002aac2  setnbe  sil
0x18002aac6  ja      short loc_18002AAED
0x18002aac8  jmp     short loc_18002AB2C
0x18002aaca  mov     esi, 1
0x18002aacf  lea     r9, aFullSyncMayBeN; "Full sync may be needed because of Comm"...
0x18002aad6  mov     r8d, 7E2h
0x18002aadc  lea     rdx, aTelcacheprovid_23; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18002aae3  mov     ecx, 3
0x18002aae8  call    AslLogCallPrintf
0x18002aaed  lea     rdx, aCommercialid_0; "commercialId"
0x18002aaf4  mov     rcx, [r15+58h]
0x18002aaf8  mov     rax, [rcx]
0x18002aafb  mov     rax, [rax+50h]
0x18002aaff  cmp     [r14], r12w
0x18002ab03  jz      short loc_18002AB0A
0x18002ab05  mov     r8, r14
0x18002ab08  jmp     short loc_18002AB0D
0x18002ab0a  xor     r8d, r8d
0x18002ab0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab12  mov     rcx, [r15+58h]
0x18002ab16  lea     rdx, aLastfullsync; "lastFullSync"
0x18002ab1d  mov     r8, [rcx]
0x18002ab20  mov     rax, [r8+58h]
0x18002ab24  mov     r8, rbx
0x18002ab27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab2c  mov     eax, esi
0x18002ab2e  mov     rcx, [rbp+57h+var_30]
0x18002ab32  xor     rcx, rsp; StackCookie
0x18002ab35  call    __security_check_cookie
0x18002ab3a  lea     r11, [rsp+0D0h+var_20]
0x18002ab42  mov     rbx, [r11+38h]
0x18002ab46  mov     rsi, [r11+40h]
0x18002ab4a  mov     rsp, r11
0x18002ab4d  pop     r15
0x18002ab4f  pop     r14
0x18002ab51  pop     r12
0x18002ab53  pop     rdi
0x18002ab54  pop     rbp
0x18002ab55  retn
```
