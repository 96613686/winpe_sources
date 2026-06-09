# _WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch$39

- ea: `0x18003f2a9`
- end: `0x18003f326`
- name: `_WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch$39`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180029758`
- `0x180039548`
- `0x18003f2a9`
- `0x180041010`

## string_xrefs

- `0x18003f308`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskWlanToCDS::BootstrapProfilesIfNeeded_::_1_::catch_39(__int64 a1, __int64 a2)
{
  int v3; // eax
  const struct _GUID *v4; // rdx
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-38h]

  *(_OWORD *)(a2 + 480) = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a2 + 96) + 48LL))(*(_QWORD *)(a2 + 96), a2 + 480);
  v5 = *(wil::details::in1diag3 **)(a2 + 680);
  if ( v3 < 0 )
  {
    v6 = 612;
LABEL_5:
    wil::details::in1diag3::_Log_Hr(
      v5,
      (void *)v6,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      (const char *)(unsigned int)v3,
      v8);
    return 0;
  }
  v3 = Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser((GUID *)(a2 + 480), v4);
  v5 = *(wil::details::in1diag3 **)(a2 + 680);
  if ( v3 < 0 )
  {
    v6 = 614;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18003f2a9  mov     [rsp+arg_8], rdx
0x18003f2ae  push    rbp
0x18003f2af  sub     rsp, 50h
0x18003f2b3  mov     rbp, rdx
0x18003f2b6  xorps   xmm0, xmm0
0x18003f2b9  movups  xmmword ptr [rbp+1E0h], xmm0
0x18003f2c0  mov     rcx, [rbp+60h]
0x18003f2c4  mov     rax, [rcx]
0x18003f2c7  lea     rdx, [rbp+1E0h]
0x18003f2ce  mov     rax, [rax+30h]
0x18003f2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2d7  mov     rcx, [rbp+2A8h]
0x18003f2de  test    eax, eax
0x18003f2e0  jns     short loc_18003F2E9
0x18003f2e2  mov     edx, 264h
0x18003f2e7  jmp     short loc_18003F305
0x18003f2e9  lea     rcx, [rbp+1E0h]; rguid
0x18003f2f0  call    ?StoreNlmSyncWithNetworkCategoryChangedForCurrentUser@WiFiCloudStore@Internal@Windows@@YAJAEBU_GUID@@@Z; Windows::Internal::WiFiCloudStore::StoreNlmSyncWithNetworkCategoryChangedForCurrentUser(_GUID const &)
0x18003f2f5  mov     rcx, [rbp+2A8h]; this
0x18003f2fc  test    eax, eax
0x18003f2fe  jns     short loc_18003F315
0x18003f300  mov     edx, 266h; void *
0x18003f305  mov     r9d, eax; char *
0x18003f308  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18003f30f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003f314  nop
0x18003f315  mov     rax, 0
0x18003f31f  add     rsp, 50h
0x18003f323  pop     rbp
0x18003f324  retn
```
