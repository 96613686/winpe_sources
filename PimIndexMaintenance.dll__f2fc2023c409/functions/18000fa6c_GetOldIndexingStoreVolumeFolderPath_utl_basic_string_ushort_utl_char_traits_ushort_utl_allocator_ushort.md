# GetOldIndexingStoreVolumeFolderPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18000fa6c`
- end: `0x18000fbc3`
- name: `?GetOldIndexingStoreVolumeFolderPath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `343`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ee40`
- `0x18000fbcc`

## callees

- `0x18000fa6c`
- `0x1800104b8`
- `0x180012540`
- `0x180012618`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbb0`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18000fa96`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18000fa96`

## string_xrefs

- `0x18000fb0f`: `Comms`

## pseudocode

```c
__int64 __fastcall GetOldIndexingStoreVolumeFolderPath(__int64 a1)
{
  HRESULT v2; // eax
  __int64 v3; // r8
  unsigned int v4; // esi
  __int64 v6; // r8
  __int64 v7; // r9
  PWSTR ppszPath; // [rsp+48h] [rbp+10h] BYREF

  ppszPath = 0;
  v2 = SHGetKnownFolderPath(&rfid, 0x4000u, 0, &ppszPath);
  v4 = v2;
  if ( v2 < 0 )
  {
    Log_HREvent_2((unsigned int)v2, 1, v3, 55);
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return v4;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a1,
                           ppszPath) )
  {
    v7 = 57;
LABEL_17:
    Log_HREvent_2(2147942414LL, 0, v6, v7);
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
    return 2147942414LL;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a1,
                           L"\\",
                           1) )
  {
    v7 = 58;
    goto LABEL_17;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a1,
                           L"Comms",
                           5) )
  {
    v7 = 59;
    goto LABEL_17;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a1,
                           L"\\",
                           1) )
  {
    v7 = 60;
    goto LABEL_17;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a1,
                           L"PimIdxMaint",
                           11) )
  {
    v7 = 61;
    goto LABEL_17;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           a1,
                           L"\\",
                           1) )
  {
    v7 = 62;
    goto LABEL_17;
  }
  if ( ppszPath )
    CoTaskMemFree(ppszPath);
  return 0;
}

```

## disassembly

```asm
0x18000fa6c  mov     [rsp+arg_0], rbx
0x18000fa71  push    rsi
0x18000fa72  sub     rsp, 30h
0x18000fa76  mov     rbx, rcx
0x18000fa79  mov     [rsp+38h+ppszPath], 0
0x18000fa82  lea     rcx, rfid; rfid
0x18000fa89  xor     r8d, r8d; hToken
0x18000fa8c  lea     r9, [rsp+38h+ppszPath]; ppszPath
0x18000fa91  mov     edx, 4000h; dwFlags
0x18000fa96  call    cs:__imp_SHGetKnownFolderPath
0x18000fa9c  mov     esi, eax
0x18000fa9e  test    eax, eax
0x18000faa0  jns     short loc_18000FAC9
0x18000faa2  mov     edx, 1
0x18000faa7  mov     ecx, eax
0x18000faa9  lea     r9d, [rdx+36h]
0x18000faad  call    Log_HREvent_2
0x18000fab2  mov     rcx, [rsp+38h+ppszPath]; pv
0x18000fab7  test    rcx, rcx
0x18000faba  jz      short loc_18000FAC2
0x18000fabc  call    cs:__imp_CoTaskMemFree
0x18000fac2  mov     eax, esi
0x18000fac4  jmp     loc_18000FBB8
0x18000fac9  mov     rdx, [rsp+38h+ppszPath]
0x18000face  mov     rcx, rbx
0x18000fad1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000fad6  test    al, al
0x18000fad8  jnz     short loc_18000FAE5
0x18000fada  mov     r9d, 39h ; '9'
0x18000fae0  jmp     loc_18000FB83
0x18000fae5  lea     rsi, asc_180026AD8; "\\"
0x18000faec  mov     r8d, 1
0x18000faf2  mov     rdx, rsi
0x18000faf5  mov     rcx, rbx
0x18000faf8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000fafd  test    al, al
0x18000faff  jnz     short loc_18000FB09
0x18000fb01  mov     r9d, 3Ah ; ':'
0x18000fb07  jmp     short loc_18000FB83
0x18000fb09  mov     r8d, 5
0x18000fb0f  lea     rdx, ?gc_szCommsFolderName@@3QBGB; "Comms"
0x18000fb16  mov     rcx, rbx
0x18000fb19  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000fb1e  test    al, al
0x18000fb20  jnz     short loc_18000FB2A
0x18000fb22  mov     r9d, 3Bh ; ';'
0x18000fb28  jmp     short loc_18000FB83
0x18000fb2a  mov     r8d, 1
0x18000fb30  mov     rdx, rsi
0x18000fb33  mov     rcx, rbx
0x18000fb36  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000fb3b  test    al, al
0x18000fb3d  jnz     short loc_18000FB47
0x18000fb3f  mov     r9d, 3Ch ; '<'
0x18000fb45  jmp     short loc_18000FB83
0x18000fb47  mov     r8d, 0Bh
0x18000fb4d  lea     rdx, szInstanceName; "PimIdxMaint"
0x18000fb54  mov     rcx, rbx
0x18000fb57  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000fb5c  test    al, al
0x18000fb5e  jnz     short loc_18000FB68
0x18000fb60  mov     r9d, 3Dh ; '='
0x18000fb66  jmp     short loc_18000FB83
0x18000fb68  mov     r8d, 1
0x18000fb6e  mov     rdx, rsi
0x18000fb71  mov     rcx, rbx
0x18000fb74  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18000fb79  test    al, al
0x18000fb7b  jnz     short loc_18000FBA6
0x18000fb7d  mov     r9d, 3Eh ; '>'
0x18000fb83  xor     edx, edx
0x18000fb85  mov     ecx, 8007000Eh
0x18000fb8a  call    Log_HREvent_2
0x18000fb8f  mov     rcx, [rsp+38h+ppszPath]; pv
0x18000fb94  test    rcx, rcx
0x18000fb97  jz      short loc_18000FB9F
0x18000fb99  call    cs:__imp_CoTaskMemFree
0x18000fb9f  mov     eax, 8007000Eh
0x18000fba4  jmp     short loc_18000FBB8
0x18000fba6  mov     rcx, [rsp+38h+ppszPath]; pv
0x18000fbab  test    rcx, rcx
0x18000fbae  jz      short loc_18000FBB6
0x18000fbb0  call    cs:__imp_CoTaskMemFree
0x18000fbb6  xor     eax, eax
0x18000fbb8  mov     rbx, [rsp+38h+arg_0]
0x18000fbbd  add     rsp, 30h
0x18000fbc1  pop     rsi
0x18000fbc2  retn
```
