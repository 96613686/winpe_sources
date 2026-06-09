# HumanPresenceCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000b6f0`
- end: `0x18000b811`
- name: `?AccessChanged@HumanPresenceCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `289`
- prototype: `__int64 __fastcall(HumanPresenceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b220`
- `0x18000b314`
- `0x18000b5bc`
- `0x18000b6f0`
- `0x18000d280`
- `0x18000d550`
- `0x18000e2d4`
- `0x18000ed24`
- `0x180012bbc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b70a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b783`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b7c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b70a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b783`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b7c2`

## pseudocode

```c
__int64 __fastcall HumanPresenceCapabilityHandler::AccessChanged(
        HumanPresenceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  ULONGLONG TickCount64; // rbx
  _QWORD *v7; // rax
  ULONGLONG v8; // rbx
  ULONGLONG v9; // rbx
  _QWORD *v11; // [rsp+20h] [rbp-28h] BYREF
  void *v12[4]; // [rsp+28h] [rbp-20h] BYREF

  v11 = 0;
  TickCount64 = GetTickCount64();
  *(_QWORD *)(*tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(
                 (__int64)&v11,
                 (__int64 *)v12)
            + 272) = TickCount64;
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(v12);
  if ( v11 && (v11[31] || (v11[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::reset(&v11);
  v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::ensure_data(&v11);
  tip2::details::shared_data<0,0,0>::start(*v7 + 8LL, v12);
  DeviceHelperAccessCheckRevokeInterfaceHandles((__int64)&GUID_SensorType_Proximity, a3, a4);
  v8 = GetTickCount64();
  *(_QWORD *)(*tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(
                 (__int64)&v11,
                 (__int64 *)v12)
            + 280) = v8;
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(v12);
  DeviceHelperAccessCheckRevokeInterfaceHandles(
    (__int64)&GUID_SensorType_Proximity,
    a3,
    L"Microsoft.humanPresenceSystem_8wekyb3d8bbwe");
  v9 = GetTickCount64();
  *(_QWORD *)(*tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(
                 (__int64)&v11,
                 (__int64 *)v12)
            + 288) = v9;
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(v12);
  if ( v11 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v11 + 1);
  wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>((void **)&v11);
  return 0;
}

```

## disassembly

```asm
0x18000b6f0  push    rbp
0x18000b6f2  push    rbx
0x18000b6f3  push    rsi
0x18000b6f4  push    rdi
0x18000b6f5  mov     rbp, rsp
0x18000b6f8  sub     rsp, 48h
0x18000b6fc  mov     rsi, r9
0x18000b6ff  mov     [rbp+var_28], 0
0x18000b707  mov     rdi, r8
0x18000b70a  call    cs:__imp_GetTickCount64
0x18000b710  lea     rdx, [rbp+var_20]
0x18000b714  mov     rbx, rax
0x18000b717  lea     rcx, [rbp+var_28]
0x18000b71b  call    ??C?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(void)
0x18000b720  mov     rcx, [rax]
0x18000b723  mov     [rcx+110h], rbx
0x18000b72a  lea     rcx, [rbp+var_20]
0x18000b72e  call    ??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(void)
0x18000b733  mov     rax, [rbp+var_28]
0x18000b737  test    rax, rax
0x18000b73a  jz      short loc_18000B758
0x18000b73c  cmp     qword ptr [rax+0F8h], 0
0x18000b744  jnz     short loc_18000B74F
0x18000b746  test    dword ptr [rax+48h], 100h
0x18000b74d  jz      short loc_18000B758
0x18000b74f  lea     rcx, [rbp+var_28]
0x18000b753  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::reset(void)
0x18000b758  lea     rcx, [rbp+var_28]
0x18000b75c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::ensure_data(void)
0x18000b761  lea     rdx, [rbp+var_20]
0x18000b765  mov     rcx, [rax]
0x18000b768  add     rcx, 8
0x18000b76c  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000b771  mov     r8, rsi
0x18000b774  lea     rcx, GUID_SensorType_Proximity
0x18000b77b  mov     rdx, rdi
0x18000b77e  call    DeviceHelperAccessCheckRevokeInterfaceHandles
0x18000b783  call    cs:__imp_GetTickCount64
0x18000b789  lea     rdx, [rbp+var_20]
0x18000b78d  mov     rbx, rax
0x18000b790  lea     rcx, [rbp+var_28]
0x18000b794  call    ??C?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(void)
0x18000b799  lea     rcx, [rbp+var_20]
0x18000b79d  mov     rdx, [rax]
0x18000b7a0  mov     [rdx+118h], rbx
0x18000b7a7  call    ??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(void)
0x18000b7ac  lea     r8, aMicrosoftHuman; "Microsoft.humanPresenceSystem_8wekyb3d8"...
0x18000b7b3  mov     rdx, rdi
0x18000b7b6  lea     rcx, GUID_SensorType_Proximity
0x18000b7bd  call    DeviceHelperAccessCheckRevokeInterfaceHandles
0x18000b7c2  call    cs:__imp_GetTickCount64
0x18000b7c8  lea     rdx, [rbp+var_20]
0x18000b7cc  mov     rbx, rax
0x18000b7cf  lea     rcx, [rbp+var_28]
0x18000b7d3  call    ??C?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(void)
0x18000b7d8  mov     rcx, [rax]
0x18000b7db  mov     [rcx+120h], rbx
0x18000b7e2  lea     rcx, [rbp+var_20]
0x18000b7e6  call    ??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>(void)
0x18000b7eb  mov     rcx, [rbp+var_28]
0x18000b7ef  test    rcx, rcx
0x18000b7f2  jz      short loc_18000B7FD
0x18000b7f4  add     rcx, 8
0x18000b7f8  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18000b7fd  lea     rcx, [rbp+var_28]
0x18000b801  call    ??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>,wil::err_returncode_policy>(void)
0x18000b806  xor     eax, eax
0x18000b808  add     rsp, 48h
0x18000b80c  pop     rdi
0x18000b80d  pop     rsi
0x18000b80e  pop     rbx
0x18000b80f  pop     rbp
0x18000b810  retn
```
