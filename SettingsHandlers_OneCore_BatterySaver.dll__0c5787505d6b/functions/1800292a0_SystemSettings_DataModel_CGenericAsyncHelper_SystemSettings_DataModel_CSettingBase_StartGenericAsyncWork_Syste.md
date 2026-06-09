# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x1800292a0`
- end: `0x1800293d5`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a000`
- `0x18001aee0`
- `0x18001b694`
- `0x18001c3d8`
- `0x18001c84c`
- `0x18001d52c`
- `0x1800292a0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029346`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293a2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029387`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029387`

## pseudocode

```c
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
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v6);
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
0x1800292a0  push    rbx
0x1800292a2  push    rsi
0x1800292a3  push    rdi
0x1800292a4  push    r14
0x1800292a6  sub     rsp, 38h
0x1800292aa  mov     r14, rdx
0x1800292ad  mov     rdi, rcx
0x1800292b0  mov     eax, 2
0x1800292b5  xchg    eax, [rcx+0A0h]
0x1800292bb  test    eax, eax
0x1800292bd  jnz     loc_1800293CB
0x1800292c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800292ca  lea     ecx, [rax+18h]; unsigned __int64
0x1800292cd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800292d2  mov     rbx, rax
0x1800292d5  test    rax, rax
0x1800292d8  jz      loc_1800293C0
0x1800292de  mov     qword ptr [rax], 0
0x1800292e5  mov     qword ptr [rax+8], 0
0x1800292ed  lea     rcx, [rax+8]
0x1800292f1  mov     rdx, r14
0x1800292f4  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x1800292f9  cmp     [rbx], rdi
0x1800292fc  jz      short loc_18002932B
0x1800292fe  test    rdi, rdi
0x180029301  jz      short loc_180029313
0x180029303  mov     rax, [rdi]
0x180029306  mov     rcx, rdi
0x180029309  mov     rax, [rax+8]
0x18002930d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029312  nop
0x180029313  mov     rcx, [rbx]
0x180029316  mov     [rbx], rdi
0x180029319  test    rcx, rcx
0x18002931c  jz      short loc_18002932B
0x18002931e  mov     rax, [rcx]
0x180029321  mov     rax, [rax+10h]
0x180029325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002932a  nop
0x18002932b  mov     qword ptr [rbx+10h], 0
0x180029333  lea     rsi, [rdi+0A8h]
0x18002933a  mov     rcx, [rsi+8]; hHandle
0x18002933e  test    rcx, rcx
0x180029341  jz      short loc_180029354
0x180029343  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029346  call    cs:__imp_WaitForSingleObject
0x18002934c  mov     rcx, rsi
0x18002934f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180029354  mov     rax, [r14]
0x180029357  mov     dl, 1
0x180029359  mov     rcx, r14
0x18002935c  mov     rax, [rax+0A8h]
0x180029363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029368  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180029371  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180029379  mov     r9, rbx; lpParameter
0x18002937c  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x180029383  xor     edx, edx; dwStackSize
0x180029385  xor     ecx, ecx; lpThreadAttributes
0x180029387  call    cs:__imp_CreateThread
0x18002938d  mov     rdx, rax
0x180029390  mov     rcx, rsi
0x180029393  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x180029398  cmp     qword ptr [rdi+0B0h], 0
0x1800293a0  jnz     short loc_1800293CB
0x1800293a2  call    cs:__imp_GetLastError
0x1800293a8  test    eax, eax
0x1800293aa  jle     short loc_1800293B6
0x1800293ac  movzx   eax, ax
0x1800293af  or      eax, 80070000h
0x1800293b4  test    eax, eax
0x1800293b6  jns     short loc_1800293CB
0x1800293b8  mov     rcx, rbx; void *
0x1800293bb  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCDwordRangeSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x1800293c0  mov     rdx, r14
0x1800293c3  mov     rcx, rdi
0x1800293c6  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x1800293cb  add     rsp, 38h
0x1800293cf  pop     r14
0x1800293d1  pop     rdi
0x1800293d2  pop     rsi
0x1800293d3  pop     rbx
0x1800293d4  retn
```
