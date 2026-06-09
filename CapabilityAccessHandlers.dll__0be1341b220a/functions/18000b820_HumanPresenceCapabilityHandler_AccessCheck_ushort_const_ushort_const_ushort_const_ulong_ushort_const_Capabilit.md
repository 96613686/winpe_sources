# HumanPresenceCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x18000b820`
- end: `0x18000b972`
- name: `?AccessCheck@HumanPresenceCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(HumanPresenceCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, enum CapabilityHandlerAccessStatus *PropertyBufferSize)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000afe0`
- `0x18000b23c`
- `0x18000b34c`
- `0x18000b820`
- `0x18000d148`
- `0x18000d280`
- `0x18000d5b0`
- `0x18000e2fc`
- `0x18000ed24`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b841`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b921`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b841`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b921`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000b8e9`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000b8e9`

## pseudocode

```c
__int64 __fastcall HumanPresenceCapabilityHandler::AccessCheck(
        HumanPresenceCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        enum CapabilityHandlerAccessStatus *PropertyBufferSize)
{
  enum CapabilityHandlerAccessStatus *v7; // rdi
  ULONGLONG TickCount64; // rbx
  __int64 *v10; // rax
  _QWORD *v11; // rax
  __int64 *v12; // rax
  ULONGLONG v13; // rax
  _DWORD *v14; // rcx
  DEVPROPTYPE PropertyType; // [rsp+30h] [rbp-28h] BYREF
  BYTE PropertyBuffer[4]; // [rsp+34h] [rbp-24h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp-20h] BYREF
  void *v19[3]; // [rsp+40h] [rbp-18h] BYREF

  v7 = PropertyBufferSize;
  v18 = 0;
  *(_DWORD *)PropertyBufferSize = 2;
  TickCount64 = GetTickCount64();
  v10 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(&v18);
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(
    (__int64 *)v19,
    v10);
  *((_QWORD *)v19[0] + 35) = TickCount64;
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(v19);
  if ( v18 && (v18[31] || (v18[9] & 0x100) != 0) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::reset(&v18);
  v11 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(&v18);
  tip2::details::shared_data<0,0,0>::start(*v11 + 8LL, v19);
  PropertyType = 0;
  *(_DWORD *)PropertyBuffer = 0;
  LODWORD(PropertyBufferSize) = 4;
  if ( CM_Get_Device_Interface_PropertyW(
         a4,
         &DEVPKEY_Sensor_HumanPresenceDetectionType,
         &PropertyType,
         PropertyBuffer,
         (PULONG)&PropertyBufferSize,
         0) != 37
    && (_DWORD)PropertyBufferSize
    && PropertyType
    && *(_DWORD *)PropertyBuffer )
  {
    *(_DWORD *)v7 = 1;
  }
  v12 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(&v18);
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(
    (__int64 *)v19,
    v12);
  v13 = GetTickCount64();
  v14 = v19[0];
  *((_QWORD *)v19[0] + 36) = v13;
  v14[68] = *(_DWORD *)v7;
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::close(v19);
  if ( v18 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v18 + 1);
  tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(v19);
  wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>((void **)&v18);
  return 0;
}

```

## disassembly

```asm
0x18000b820  push    rbp
0x18000b822  push    rbx
0x18000b823  push    rsi
0x18000b824  push    rdi
0x18000b825  mov     rbp, rsp
0x18000b828  sub     rsp, 58h
0x18000b82c  mov     rdi, qword ptr [rbp+arg_30]
0x18000b830  mov     rsi, r9
0x18000b833  mov     [rbp+var_20], 0
0x18000b83b  mov     dword ptr [rdi], 2
0x18000b841  call    cs:__imp_GetTickCount64
0x18000b847  lea     rcx, [rbp+var_20]
0x18000b84b  mov     rbx, rax
0x18000b84e  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(void)
0x18000b853  mov     rdx, rax
0x18000b856  lea     rcx, [rbp+var_18]
0x18000b85a  call    ??0?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy> const &)
0x18000b85f  mov     rcx, [rbp+var_18]
0x18000b863  mov     [rcx+118h], rbx
0x18000b86a  lea     rcx, [rbp+var_18]
0x18000b86e  call    ??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(void)
0x18000b873  mov     rax, [rbp+var_20]
0x18000b877  test    rax, rax
0x18000b87a  jz      short loc_18000B898
0x18000b87c  cmp     qword ptr [rax+0F8h], 0
0x18000b884  jnz     short loc_18000B88F
0x18000b886  test    dword ptr [rax+48h], 100h
0x18000b88d  jz      short loc_18000B898
0x18000b88f  lea     rcx, [rbp+var_20]
0x18000b893  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::reset(void)
0x18000b898  lea     rcx, [rbp+var_20]
0x18000b89c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(void)
0x18000b8a1  lea     rdx, [rbp+var_18]
0x18000b8a5  mov     rcx, [rax]
0x18000b8a8  add     rcx, 8
0x18000b8ac  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18000b8b1  lea     rax, [rbp+arg_30]
0x18000b8b5  mov     [rsp+58h+ulFlags], 0; ulFlags
0x18000b8bd  lea     r9, [rbp+PropertyBuffer]; PropertyBuffer
0x18000b8c1  mov     [rsp+58h+PropertyBufferSize], rax; PropertyBufferSize
0x18000b8c6  lea     r8, [rbp+PropertyType]; PropertyType
0x18000b8ca  mov     [rbp+PropertyType], 0
0x18000b8d1  lea     rdx, DEVPKEY_Sensor_HumanPresenceDetectionType; PropertyKey
0x18000b8d8  mov     dword ptr [rbp+PropertyBuffer], 0
0x18000b8df  mov     rcx, rsi; pszDeviceInterface
0x18000b8e2  mov     [rbp+arg_30], 4
0x18000b8e9  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18000b8ef  cmp     eax, 25h ; '%'
0x18000b8f2  jz      short loc_18000B90C
0x18000b8f4  cmp     [rbp+arg_30], 0
0x18000b8f8  jz      short loc_18000B90C
0x18000b8fa  cmp     [rbp+PropertyType], 0
0x18000b8fe  jz      short loc_18000B90C
0x18000b900  cmp     dword ptr [rbp+PropertyBuffer], 0
0x18000b904  jz      short loc_18000B90C
0x18000b906  mov     dword ptr [rdi], 1
0x18000b90c  lea     rcx, [rbp+var_20]
0x18000b910  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::ensure_data(void)
0x18000b915  mov     rdx, rax
0x18000b918  lea     rcx, [rbp+var_18]
0x18000b91c  call    ??0?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy> const &)
0x18000b921  call    cs:__imp_GetTickCount64
0x18000b927  mov     rcx, [rbp+var_18]
0x18000b92b  mov     [rcx+120h], rax
0x18000b932  mov     eax, [rdi]
0x18000b934  mov     [rcx+110h], eax
0x18000b93a  lea     rcx, [rbp+var_18]
0x18000b93e  call    ?close@?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::close(void)
0x18000b943  mov     rcx, [rbp+var_20]
0x18000b947  test    rcx, rcx
0x18000b94a  jz      short loc_18000B955
0x18000b94c  add     rcx, 8
0x18000b950  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x18000b955  lea     rcx, [rbp+var_18]
0x18000b959  call    ??1?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>>(void)
0x18000b95e  lea     rcx, [rbp+var_20]
0x18000b962  call    ??1?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>,wil::err_returncode_policy>(void)
0x18000b967  xor     eax, eax
0x18000b969  add     rsp, 58h
0x18000b96d  pop     rdi
0x18000b96e  pop     rsi
0x18000b96f  pop     rbx
0x18000b970  pop     rbp
0x18000b971  retn
```
