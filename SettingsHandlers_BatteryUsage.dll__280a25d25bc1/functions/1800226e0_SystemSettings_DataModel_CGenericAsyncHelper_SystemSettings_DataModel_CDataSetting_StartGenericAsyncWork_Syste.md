# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x1800226e0`
- end: `0x180022815`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004976c`
- `0x180049870`

## callees

- `0x1800042d8`
- `0x18000e0f4`
- `0x18000e2fc`
- `0x18000e724`
- `0x18000e798`
- `0x180022628`
- `0x1800226e0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800227c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800227c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022786`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022786`

## pseudocode

```c
signed int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::StartGenericAsyncWork(
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

  result = _InterlockedExchange((volatile __int32 *)(a1 + 208), 2);
  if ( !result )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( !v5 )
      return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(
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
    v9 = *(void **)(a1 + 224);
    if ( v9 )
    {
      WaitForSingleObject(v9, 0xFFFFFFFF);
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(a1 + 216);
    }
    LOBYTE(v7) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 168LL))(a2, v7);
    Thread = CreateThread(
               0,
               0,
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CListSetting>::s_GenericAsyncThread,
               v6,
               0,
               0);
    result = Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(
               a1 + 216,
               Thread);
    if ( !*(_QWORD *)(a1 + 224) )
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
        return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(
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
0x1800226e0  push    rbx
0x1800226e2  push    rsi
0x1800226e3  push    rdi
0x1800226e4  push    r14
0x1800226e6  sub     rsp, 38h
0x1800226ea  mov     r14, rdx
0x1800226ed  mov     rdi, rcx
0x1800226f0  mov     eax, 2
0x1800226f5  xchg    eax, [rcx+0D0h]
0x1800226fb  test    eax, eax
0x1800226fd  jnz     loc_18002280B
0x180022703  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002270a  lea     ecx, [rax+18h]; unsigned __int64
0x18002270d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022712  mov     rbx, rax
0x180022715  test    rax, rax
0x180022718  jz      loc_180022800
0x18002271e  mov     qword ptr [rax], 0
0x180022725  mov     qword ptr [rax+8], 0
0x18002272d  lea     rcx, [rax+8]
0x180022731  mov     rdx, r14
0x180022734  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x180022739  cmp     [rbx], rdi
0x18002273c  jz      short loc_18002276B
0x18002273e  test    rdi, rdi
0x180022741  jz      short loc_180022753
0x180022743  mov     rax, [rdi]
0x180022746  mov     rcx, rdi
0x180022749  mov     rax, [rax+8]
0x18002274d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022752  nop
0x180022753  mov     rcx, [rbx]
0x180022756  mov     [rbx], rdi
0x180022759  test    rcx, rcx
0x18002275c  jz      short loc_18002276B
0x18002275e  mov     rax, [rcx]
0x180022761  mov     rax, [rax+10h]
0x180022765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002276a  nop
0x18002276b  mov     qword ptr [rbx+10h], 0
0x180022773  lea     rsi, [rdi+0D8h]
0x18002277a  mov     rcx, [rsi+8]; hHandle
0x18002277e  test    rcx, rcx
0x180022781  jz      short loc_180022794
0x180022783  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180022786  call    cs:__imp_WaitForSingleObject
0x18002278c  mov     rcx, rsi
0x18002278f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180022794  mov     rax, [r14]
0x180022797  mov     dl, 1
0x180022799  mov     rcx, r14
0x18002279c  mov     rax, [rax+0A8h]
0x1800227a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227a8  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1800227b1  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800227b9  mov     r9, rbx; lpParameter
0x1800227bc  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x1800227c3  xor     edx, edx; dwStackSize
0x1800227c5  xor     ecx, ecx; lpThreadAttributes
0x1800227c7  call    cs:__imp_CreateThread
0x1800227cd  mov     rdx, rax
0x1800227d0  mov     rcx, rsi
0x1800227d3  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x1800227d8  cmp     qword ptr [rdi+0E0h], 0
0x1800227e0  jnz     short loc_18002280B
0x1800227e2  call    cs:__imp_GetLastError
0x1800227e8  test    eax, eax
0x1800227ea  jle     short loc_1800227F6
0x1800227ec  movzx   eax, ax
0x1800227ef  or      eax, 80070000h
0x1800227f4  test    eax, eax
0x1800227f6  jns     short loc_18002280B
0x1800227f8  mov     rcx, rbx; void *
0x1800227fb  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x180022800  mov     rdx, r14
0x180022803  mov     rcx, rdi
0x180022806  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCDataSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDataSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x18002280b  add     rsp, 38h
0x18002280f  pop     r14
0x180022811  pop     rdi
0x180022812  pop     rsi
0x180022813  pop     rbx
0x180022814  retn
```
