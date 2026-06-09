# WlanSyncTaskCDSToWlan::IsKnownErrorCondition(std::vector<Windows::Internal::WiFiCloudStore::SyncNeededProfile,std::allocator<Windows::Internal::WiFiCloudStore::SyncNeededProfile>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64,unsigned __int64,_GUID const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileGeneration)

- ea: `0x1800119bc`
- end: `0x180011b8c`
- name: `?IsKnownErrorCondition@WlanSyncTaskCDSToWlan@@SA_NAEBV?$vector@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@V?$allocator@USyncNeededProfile@WiFiCloudStore@Internal@Windows@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@_K22AEBU_GUID@@3W4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800211b0`

## callees

- `0x1800119bc`
- `0x180011b94`
- `0x180011cfc`
- `0x18003a7fc`
- `0x18003a93c`
- `0x18003aaa0`
- `0x18003ba30`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x180011afe`
- `wlanapi!WlanFreeMemory` at `0x180011b24`
- `wlanapi!WlanFreeMemory` at `0x180011b5a`
- `wlanapi!WlanFreeMemory` at `0x180011afe`
- `wlanapi!WlanFreeMemory` at `0x180011b24`
- `wlanapi!WlanFreeMemory` at `0x180011b5a`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180011add`
- `wlanapi!WlanGetProfileMetadataWithProfileGuid` at `0x180011add`

## pseudocode

```c
char WlanSyncTaskCDSToWlan::IsKnownErrorCondition(__int64 *a1, PVOID *a2, ...)
{
  __int64 v2; // rdi
  __int64 v3; // r15
  unsigned __int64 v4; // r14
  PVOID *v5; // rbx
  PVOID v7; // rcx
  PVOID v8; // rcx
  PVOID *p_pMemory; // [rsp+30h] [rbp-28h] BYREF
  va_list v11; // [rsp+38h] [rbp-20h]
  char v12; // [rsp+40h] [rbp-18h]
  PVOID pMemory; // [rsp+98h] [rbp+40h] BYREF
  unsigned __int64 v14; // [rsp+A0h] [rbp+48h] BYREF
  va_list va; // [rsp+A0h] [rbp+48h]
  __int64 v16; // [rsp+A8h] [rbp+50h] BYREF
  va_list va1; // [rsp+A8h] [rbp+50h]
  unsigned __int64 v18; // [rsp+B0h] [rbp+58h]
  GUID *v19; // [rsp+B8h] [rbp+60h]
  __int64 v20; // [rsp+C0h] [rbp+68h]
  __int64 v21; // [rsp+C8h] [rbp+70h] BYREF
  va_list va2; // [rsp+C8h] [rbp+70h]
  va_list va3; // [rsp+D0h] [rbp+78h] BYREF

  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  v18 = va_arg(va2, _QWORD);
  v19 = va_arg(va2, GUID *);
  v20 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v21 = va_arg(va3, _QWORD);
  v2 = *a1;
  v3 = a1[1];
  v4 = v14;
  va_copy(v11, va2);
  v5 = a2;
  p_pMemory = a2;
  while ( v2 != v3 && !(unsigned __int8)lambda_7821ada89498501b865039d2e9279344_::operator()(&p_pMemory, v2) )
    v2 += 48;
  if ( v2 == a1[1] )
  {
    if ( v4 <= v18 )
    {
      p_pMemory = 0;
      LODWORD(v11) = 0;
      if ( Windows::Internal::WiFiCloudStore::TryGetRetryCountForProfile((__int64)v5, v19, 2, v21, (__int64)&p_pMemory)
        && (unsigned int)p_pMemory >= 3 )
      {
        if ( (unsigned __int64)v5[3] > 7 )
          v5 = (PVOID *)*v5;
        p_pMemory = v5;
        WiFiCloudStoreTelemetry::ExhaustedRetryErrorIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
          &p_pMemory,
          (__int64 *)va2);
      }
      else
      {
        p_pMemory = &pMemory;
        pMemory = 0;
        v11 = 0;
        v12 = 1;
        WlanGetProfileMetadataWithProfileGuid(v19, v20, 0, L"Has Connected");
        if ( v12 )
        {
          v7 = *p_pMemory;
          *p_pMemory = v11;
          if ( v7 )
            WlanFreeMemory(v7);
        }
        if ( (unsigned __int64)v5[3] > 7 )
          v5 = (PVOID *)*v5;
        p_pMemory = v5;
        WiFiCloudStoreTelemetry::NeverConnectedErrorIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
          &p_pMemory,
          (__int64 *)va2);
        v8 = pMemory;
        pMemory = 0;
        if ( v8 )
          WlanFreeMemory(v8);
      }
    }
    else
    {
      if ( (unsigned __int64)v5[3] > 7 )
        v5 = (PVOID *)*v5;
      p_pMemory = v5;
      WiFiCloudStoreTelemetry::LocalProfileFromFutureErrorIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &>(
        &p_pMemory,
        (__int64 *)va2,
        (unsigned __int64 *)va,
        (__int64 *)va1);
    }
  }
  else
  {
    if ( (unsigned __int64)v5[3] > 7 )
      v5 = (PVOID *)*v5;
    p_pMemory = v5;
    WiFiCloudStoreTelemetry::RecoverableErrorIdentified<unsigned short const *,enum Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(
      &p_pMemory,
      (__int64 *)va2);
  }
  return 1;
}

```

## disassembly

```asm
0x1800119bc  mov     [rsp-30h+arg_18], r9
0x1800119c1  mov     [rsp-30h+arg_10], r8
0x1800119c6  push    rbp
0x1800119c7  push    rbx
0x1800119c8  push    rsi
0x1800119c9  push    rdi
0x1800119ca  push    r14
0x1800119cc  push    r15
0x1800119ce  mov     rbp, rsp
0x1800119d1  sub     rsp, 58h
0x1800119d5  mov     rdi, [rcx]
0x1800119d8  lea     rax, [rbp+arg_38]
0x1800119dc  mov     r15, [rcx+8]
0x1800119e0  mov     r14, r8
0x1800119e3  mov     [rbp+var_20], rax
0x1800119e7  mov     rbx, rdx
0x1800119ea  mov     rsi, rcx
0x1800119ed  mov     [rbp+var_28], rdx
0x1800119f1  jmp     short loc_180011A07
0x1800119f3  mov     rdx, rdi
0x1800119f6  lea     rcx, [rbp+var_28]
0x1800119fa  call    _lambda_7821ada89498501b865039d2e9279344___operator__
0x1800119ff  test    al, al
0x180011a01  jnz     short loc_180011A0C
0x180011a03  add     rdi, 30h ; '0'
0x180011a07  cmp     rdi, r15
0x180011a0a  jnz     short loc_1800119F3
0x180011a0c  cmp     rdi, [rsi+8]
0x180011a10  jnz     loc_180011B62
0x180011a16  cmp     r14, [rbp+arg_20]
0x180011a1a  jbe     short loc_180011A44
0x180011a1c  cmp     qword ptr [rbx+18h], 7
0x180011a21  jbe     short loc_180011A26
0x180011a23  mov     rbx, [rbx]
0x180011a26  lea     r9, [rbp+arg_18]
0x180011a2a  mov     [rbp+var_28], rbx
0x180011a2e  lea     r8, [rbp+arg_10]
0x180011a32  lea     rdx, [rbp+arg_38]
0x180011a36  lea     rcx, [rbp+var_28]
0x180011a3a  call    ??$LocalProfileFromFutureErrorIdentified@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_KAEB_K@WiFiCloudStoreTelemetry@@SAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@AEB_K2@Z; WiFiCloudStoreTelemetry::LocalProfileFromFutureErrorIdentified<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &,unsigned __int64 const &,unsigned __int64 const &)
0x180011a3f  jmp     loc_180011B7D
0x180011a44  mov     r9d, dword ptr [rbp+arg_38]
0x180011a48  xor     eax, eax
0x180011a4a  mov     rdx, [rbp+arg_28]
0x180011a4e  mov     r8d, 2
0x180011a54  mov     [rbp+var_28], rax
0x180011a58  mov     rcx, rbx
0x180011a5b  mov     dword ptr [rbp+var_20], eax
0x180011a5e  lea     rax, [rbp+var_28]
0x180011a62  mov     [rsp+58h+var_38], rax
0x180011a67  call    ?TryGetRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEAURetryStatistics@123@@Z; Windows::Internal::WiFiCloudStore::TryGetRetryCountForProfile(std::wstring const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,Windows::Internal::WiFiCloudStore::RetryStatistics *)
0x180011a6c  test    al, al
0x180011a6e  jz      short loc_180011A96
0x180011a70  cmp     dword ptr [rbp+var_28], 3
0x180011a74  jb      short loc_180011A96
0x180011a76  cmp     qword ptr [rbx+18h], 7
0x180011a7b  jbe     short loc_180011A80
0x180011a7d  mov     rbx, [rbx]
0x180011a80  lea     rdx, [rbp+arg_38]
0x180011a84  mov     [rbp+var_28], rbx
0x180011a88  lea     rcx, [rbp+var_28]
0x180011a8c  call    ??$ExhaustedRetryErrorIdentified@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@WiFiCloudStoreTelemetry@@SAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; WiFiCloudStoreTelemetry::ExhaustedRetryErrorIdentified<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x180011a91  jmp     loc_180011B7D
0x180011a96  mov     rdx, [rbp+arg_30]
0x180011a9a  lea     rax, [rbp+pMemory]
0x180011a9e  mov     rcx, [rbp+arg_28]
0x180011aa2  lea     r9, aHasConnected; "Has Connected"
0x180011aa9  mov     [rbp+var_28], rax
0x180011aad  xor     r8d, r8d
0x180011ab0  lea     rax, [rbp+var_20]
0x180011ab4  mov     [rbp+pMemory], 0
0x180011abc  mov     [rsp+58h+var_30], rax
0x180011ac1  lea     rax, [rbp+arg_0]
0x180011ac5  mov     [rsp+58h+var_38], rax
0x180011aca  mov     [rbp+arg_0], 0
0x180011ad1  mov     [rbp+var_20], 0
0x180011ad9  mov     [rbp+var_18], 1
0x180011add  call    cs:__imp_WlanGetProfileMetadataWithProfileGuid
0x180011ae3  cmp     [rbp+var_18], 0
0x180011ae7  mov     edi, eax
0x180011ae9  jz      short loc_180011B04
0x180011aeb  mov     r8, [rbp+var_28]
0x180011aef  mov     rdx, [rbp+var_20]
0x180011af3  mov     rcx, [r8]; pMemory
0x180011af6  mov     [r8], rdx
0x180011af9  test    rcx, rcx
0x180011afc  jz      short loc_180011B04
0x180011afe  call    cs:__imp_WlanFreeMemory
0x180011b04  test    edi, edi
0x180011b06  jnz     short loc_180011B2E
0x180011b08  cmp     [rbp+arg_0], 4
0x180011b0c  jnz     short loc_180011B2E
0x180011b0e  mov     rcx, [rbp+pMemory]; pMemory
0x180011b12  cmp     dword ptr [rcx], 1
0x180011b15  jnz     short loc_180011B2E
0x180011b17  mov     [rbp+pMemory], 0
0x180011b1f  test    rcx, rcx
0x180011b22  jz      short loc_180011B2A
0x180011b24  call    cs:__imp_WlanFreeMemory
0x180011b2a  xor     al, al
0x180011b2c  jmp     short loc_180011B7F
0x180011b2e  cmp     qword ptr [rbx+18h], 7
0x180011b33  jbe     short loc_180011B38
0x180011b35  mov     rbx, [rbx]
0x180011b38  lea     rdx, [rbp+arg_38]
0x180011b3c  mov     [rbp+var_28], rbx
0x180011b40  lea     rcx, [rbp+var_28]
0x180011b44  call    ??$NeverConnectedErrorIdentified@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@WiFiCloudStoreTelemetry@@SAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; WiFiCloudStoreTelemetry::NeverConnectedErrorIdentified<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x180011b49  mov     rcx, [rbp+pMemory]; pMemory
0x180011b4d  mov     [rbp+pMemory], 0
0x180011b55  test    rcx, rcx
0x180011b58  jz      short loc_180011B7D
0x180011b5a  call    cs:__imp_WlanFreeMemory
0x180011b60  jmp     short loc_180011B7D
0x180011b62  cmp     qword ptr [rbx+18h], 7
0x180011b67  jbe     short loc_180011B6C
0x180011b69  mov     rbx, [rbx]
0x180011b6c  lea     rdx, [rbp+arg_38]
0x180011b70  mov     [rbp+var_28], rbx
0x180011b74  lea     rcx, [rbp+var_28]
0x180011b78  call    ??$RecoverableErrorIdentified@PEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@WiFiCloudStoreTelemetry@@SAX$$QEAPEBGAEBW4ProfileGeneration@WiFiCloudStore@Internal@Windows@@@Z; WiFiCloudStoreTelemetry::RecoverableErrorIdentified<ushort const *,Windows::Internal::WiFiCloudStore::ProfileGeneration const &>(ushort const * &&,Windows::Internal::WiFiCloudStore::ProfileGeneration const &)
0x180011b7d  mov     al, 1
0x180011b7f  add     rsp, 58h
0x180011b83  pop     r15
0x180011b85  pop     r14
0x180011b87  pop     rdi
0x180011b88  pop     rsi
0x180011b89  pop     rbx
0x180011b8a  pop     rbp
0x180011b8b  retn
```
