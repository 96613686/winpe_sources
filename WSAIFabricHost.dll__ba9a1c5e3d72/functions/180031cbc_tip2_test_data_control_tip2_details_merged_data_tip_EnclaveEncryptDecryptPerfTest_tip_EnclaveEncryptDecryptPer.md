# tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(void)

- ea: `0x180031cbc`
- end: `0x180031d3e`
- name: `??1?$test_data_control@V?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036954`
- `0x1800542b4`

## callees

- `0x1800319dc`
- `0x180031cbc`
- `0x18004ea30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180031d2d`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update((__int64)&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x180031cbc  mov     [rsp+arg_8], rbx
0x180031cc1  push    rdi
0x180031cc2  sub     rsp, 20h
0x180031cc6  mov     rdi, rcx
0x180031cc9  mov     rcx, [rcx]
0x180031ccc  test    rcx, rcx
0x180031ccf  jz      short loc_180031D0A
0x180031cd1  add     rcx, 8
0x180031cd5  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180031cda  mov     rbx, [rdi]
0x180031cdd  mov     qword ptr [rdi], 0
0x180031ce4  test    rbx, rbx
0x180031ce7  jz      short loc_180031D0A
0x180031ce9  or      eax, 0FFFFFFFFh
0x180031cec  lock xadd [rbx+120h], eax
0x180031cf4  cmp     eax, 1
0x180031cf7  jnz     short loc_180031D0A
0x180031cf9  mov     rcx, rbx
0x180031cfc  call    ??1?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(void)
0x180031d01  mov     rcx, rbx; pv
0x180031d04  call    cs:__imp_CoTaskMemFree
0x180031d0a  mov     rbx, [rdi]
0x180031d0d  test    rbx, rbx
0x180031d10  jz      short loc_180031D33
0x180031d12  or      eax, 0FFFFFFFFh
0x180031d15  lock xadd [rbx+120h], eax
0x180031d1d  cmp     eax, 1
0x180031d20  jnz     short loc_180031D33
0x180031d22  mov     rcx, rbx
0x180031d25  call    ??1?$merged_data@U_tip_EnclaveEncryptDecryptPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>::~merged_data<_tip_EnclaveEncryptDecryptPerfTest,_tip_EnclaveEncryptDecryptPerfTest>(void)
0x180031d2a  mov     rcx, rbx; pv
0x180031d2d  call    cs:__imp_CoTaskMemFree
0x180031d33  mov     rbx, [rsp+28h+arg_8]
0x180031d38  add     rsp, 20h
0x180031d3c  pop     rdi
0x180031d3d  retn
```
