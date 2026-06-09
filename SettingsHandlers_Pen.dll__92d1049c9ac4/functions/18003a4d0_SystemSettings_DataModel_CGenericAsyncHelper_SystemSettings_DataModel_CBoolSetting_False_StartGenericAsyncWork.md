# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x18003a4d0`
- end: `0x18003a605`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003110`
- `0x180011488`
- `0x1800119dc`
- `0x180012220`
- `0x18001245c`
- `0x1800368d8`
- `0x18003a4d0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a576`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a5d2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003a5b7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003a5b7`

## pseudocode

```c
signed int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>::StartGenericAsyncWork(
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
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( !v5 )
      return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>::DoAsyncWorkInternal(
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
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>::s_GenericAsyncThread,
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
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(v6);
        return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>::DoAsyncWorkInternal(
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
0x18003a4d0  push    rbx
0x18003a4d2  push    rsi
0x18003a4d3  push    rdi
0x18003a4d4  push    r14
0x18003a4d6  sub     rsp, 38h
0x18003a4da  mov     r14, rdx
0x18003a4dd  mov     rdi, rcx
0x18003a4e0  mov     eax, 2
0x18003a4e5  xchg    eax, [rcx+0D0h]
0x18003a4eb  test    eax, eax
0x18003a4ed  jnz     loc_18003A5FB
0x18003a4f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a4fa  lea     ecx, [rax+18h]; unsigned __int64
0x18003a4fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003a502  mov     rbx, rax
0x18003a505  test    rax, rax
0x18003a508  jz      loc_18003A5F0
0x18003a50e  mov     qword ptr [rax], 0
0x18003a515  mov     qword ptr [rax+8], 0
0x18003a51d  lea     rcx, [rax+8]
0x18003a521  mov     rdx, r14
0x18003a524  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18003a529  cmp     [rbx], rdi
0x18003a52c  jz      short loc_18003A55B
0x18003a52e  test    rdi, rdi
0x18003a531  jz      short loc_18003A543
0x18003a533  mov     rax, [rdi]
0x18003a536  mov     rcx, rdi
0x18003a539  mov     rax, [rax+8]
0x18003a53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a542  nop
0x18003a543  mov     rcx, [rbx]
0x18003a546  mov     [rbx], rdi
0x18003a549  test    rcx, rcx
0x18003a54c  jz      short loc_18003A55B
0x18003a54e  mov     rax, [rcx]
0x18003a551  mov     rax, [rax+10h]
0x18003a555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a55a  nop
0x18003a55b  mov     qword ptr [rbx+10h], 0
0x18003a563  lea     rsi, [rdi+0D8h]
0x18003a56a  mov     rcx, [rsi+8]; hHandle
0x18003a56e  test    rcx, rcx
0x18003a571  jz      short loc_18003A584
0x18003a573  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003a576  call    cs:__imp_WaitForSingleObject
0x18003a57c  mov     rcx, rsi
0x18003a57f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003a584  mov     rax, [r14]
0x18003a587  mov     dl, 1
0x18003a589  mov     rcx, r14
0x18003a58c  mov     rax, [rax+0A8h]
0x18003a593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a598  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18003a5a1  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18003a5a9  mov     r9, rbx; lpParameter
0x18003a5ac  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x18003a5b3  xor     edx, edx; dwStackSize
0x18003a5b5  xor     ecx, ecx; lpThreadAttributes
0x18003a5b7  call    cs:__imp_CreateThread
0x18003a5bd  mov     rdx, rax
0x18003a5c0  mov     rcx, rsi
0x18003a5c3  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x18003a5c8  cmp     qword ptr [rdi+0E0h], 0
0x18003a5d0  jnz     short loc_18003A5FB
0x18003a5d2  call    cs:__imp_GetLastError
0x18003a5d8  test    eax, eax
0x18003a5da  jle     short loc_18003A5E6
0x18003a5dc  movzx   eax, ax
0x18003a5df  or      eax, 80070000h
0x18003a5e4  test    eax, eax
0x18003a5e6  jns     short loc_18003A5FB
0x18003a5e8  mov     rcx, rbx; Block
0x18003a5eb  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18003a5f0  mov     rdx, r14
0x18003a5f3  mov     rcx, rdi
0x18003a5f6  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCBoolSetting_False@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CBoolSetting_False>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x18003a5fb  add     rsp, 38h
0x18003a5ff  pop     r14
0x18003a601  pop     rdi
0x18003a602  pop     rsi
0x18003a603  pop     rbx
0x18003a604  retn
```
