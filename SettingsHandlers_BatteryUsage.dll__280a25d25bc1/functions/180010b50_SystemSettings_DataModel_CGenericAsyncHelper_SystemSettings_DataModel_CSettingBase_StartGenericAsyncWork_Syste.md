# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x180010b50`
- end: `0x180010c85`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800042d8`
- `0x18000e0f4`
- `0x18000e2fc`
- `0x18000e724`
- `0x18000e798`
- `0x18000e9a4`
- `0x180010b50`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180010c37`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180010c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010bf6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010bf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(
        __int64 a1,
        __int64 a2)
{
  signed int result; // eax
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // rcx
  HANDLE Thread; // rax
  bool v11; // sf

  result = _InterlockedExchange((volatile __int32 *)(a1 + 160), 2);
  if ( !result )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( !v5 )
      return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(
               a1,
               a2);
    *v5 = 0;
    v5[1] = 0;
    Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(v5 + 1, a2);
    if ( *v6 != a1 )
    {
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v8 = *v6;
      *v6 = a1;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v6[2] = 0;
    v9 = *(void **)(a1 + 176);
    if ( v9 )
    {
      WaitForSingleObject(v9, 0xFFFFFFFF);
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(a1 + 168);
    }
    LOBYTE(v7) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 168LL))(a2, v7);
    Thread = CreateThread(
               0,
               0,
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::s_GenericAsyncThread,
               v6,
               0,
               0);
    result = Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(
               a1 + 168,
               Thread);
    if ( !*(_QWORD *)(a1 + 176) )
    {
      result = GetLastError();
      v11 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v11 = result < 0;
      }
      if ( v11 )
      {
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v6);
        return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(
                 a1,
                 a2);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010b50  push    rbx
0x180010b52  push    rsi
0x180010b53  push    rdi
0x180010b54  push    r14
0x180010b56  sub     rsp, 38h
0x180010b5a  mov     r14, rdx
0x180010b5d  mov     rdi, rcx
0x180010b60  mov     eax, 2
0x180010b65  xchg    eax, [rcx+0A0h]
0x180010b6b  test    eax, eax
0x180010b6d  jnz     loc_180010C7B
0x180010b73  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010b7a  lea     ecx, [rax+18h]; unsigned __int64
0x180010b7d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010b82  mov     rbx, rax
0x180010b85  test    rax, rax
0x180010b88  jz      loc_180010C70
0x180010b8e  mov     qword ptr [rax], 0
0x180010b95  mov     qword ptr [rax+8], 0
0x180010b9d  lea     rcx, [rax+8]
0x180010ba1  mov     rdx, r14
0x180010ba4  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x180010ba9  cmp     [rbx], rdi
0x180010bac  jz      short loc_180010BDB
0x180010bae  test    rdi, rdi
0x180010bb1  jz      short loc_180010BC3
0x180010bb3  mov     rax, [rdi]
0x180010bb6  mov     rcx, rdi
0x180010bb9  mov     rax, [rax+8]
0x180010bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bc2  nop
0x180010bc3  mov     rcx, [rbx]
0x180010bc6  mov     [rbx], rdi
0x180010bc9  test    rcx, rcx
0x180010bcc  jz      short loc_180010BDB
0x180010bce  mov     rax, [rcx]
0x180010bd1  mov     rax, [rax+10h]
0x180010bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bda  nop
0x180010bdb  mov     qword ptr [rbx+10h], 0
0x180010be3  lea     rsi, [rdi+0A8h]
0x180010bea  mov     rcx, [rsi+8]; hHandle
0x180010bee  test    rcx, rcx
0x180010bf1  jz      short loc_180010C04
0x180010bf3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010bf6  call    cs:__imp_WaitForSingleObject
0x180010bfc  mov     rcx, rsi
0x180010bff  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180010c04  mov     rax, [r14]
0x180010c07  mov     dl, 1
0x180010c09  mov     rcx, r14
0x180010c0c  mov     rax, [rax+0A8h]
0x180010c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c18  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180010c21  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180010c29  mov     r9, rbx; lpParameter
0x180010c2c  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x180010c33  xor     edx, edx; dwStackSize
0x180010c35  xor     ecx, ecx; lpThreadAttributes
0x180010c37  call    cs:__imp_CreateThread
0x180010c3d  mov     rdx, rax
0x180010c40  mov     rcx, rsi
0x180010c43  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x180010c48  cmp     qword ptr [rdi+0B0h], 0
0x180010c50  jnz     short loc_180010C7B
0x180010c52  call    cs:__imp_GetLastError
0x180010c58  test    eax, eax
0x180010c5a  jle     short loc_180010C66
0x180010c5c  movzx   eax, ax
0x180010c5f  or      eax, 80070000h
0x180010c64  test    eax, eax
0x180010c66  jns     short loc_180010C7B
0x180010c68  mov     rcx, rbx; void *
0x180010c6b  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x180010c70  mov     rdx, r14
0x180010c73  mov     rcx, rdi
0x180010c76  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x180010c7b  add     rsp, 38h
0x180010c7f  pop     r14
0x180010c81  pop     rdi
0x180010c82  pop     rsi
0x180010c83  pop     rbx
0x180010c84  retn
```
