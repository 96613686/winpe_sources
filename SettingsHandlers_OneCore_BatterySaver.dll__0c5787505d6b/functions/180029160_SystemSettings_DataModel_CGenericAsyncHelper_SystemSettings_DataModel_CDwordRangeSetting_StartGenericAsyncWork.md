# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x180029160`
- end: `0x180029295`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCDwordRangeSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
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
- `0x18001d484`
- `0x180029160`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029206`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029262`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029247`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180029247`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::StartGenericAsyncWork(
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
      return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::DoAsyncWorkInternal(
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
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::ASYNC_PARAMS::`scalar deleting destructor'(v6);
        return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::DoAsyncWorkInternal(
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
0x180029160  push    rbx
0x180029162  push    rsi
0x180029163  push    rdi
0x180029164  push    r14
0x180029166  sub     rsp, 38h
0x18002916a  mov     r14, rdx
0x18002916d  mov     rdi, rcx
0x180029170  mov     eax, 2
0x180029175  xchg    eax, [rcx+0D0h]
0x18002917b  test    eax, eax
0x18002917d  jnz     loc_18002928B
0x180029183  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002918a  lea     ecx, [rax+18h]; unsigned __int64
0x18002918d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029192  mov     rbx, rax
0x180029195  test    rax, rax
0x180029198  jz      loc_180029280
0x18002919e  mov     qword ptr [rax], 0
0x1800291a5  mov     qword ptr [rax+8], 0
0x1800291ad  lea     rcx, [rax+8]
0x1800291b1  mov     rdx, r14
0x1800291b4  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x1800291b9  cmp     [rbx], rdi
0x1800291bc  jz      short loc_1800291EB
0x1800291be  test    rdi, rdi
0x1800291c1  jz      short loc_1800291D3
0x1800291c3  mov     rax, [rdi]
0x1800291c6  mov     rcx, rdi
0x1800291c9  mov     rax, [rax+8]
0x1800291cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291d2  nop
0x1800291d3  mov     rcx, [rbx]
0x1800291d6  mov     [rbx], rdi
0x1800291d9  test    rcx, rcx
0x1800291dc  jz      short loc_1800291EB
0x1800291de  mov     rax, [rcx]
0x1800291e1  mov     rax, [rax+10h]
0x1800291e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291ea  nop
0x1800291eb  mov     qword ptr [rbx+10h], 0
0x1800291f3  lea     rsi, [rdi+0D8h]
0x1800291fa  mov     rcx, [rsi+8]; hHandle
0x1800291fe  test    rcx, rcx
0x180029201  jz      short loc_180029214
0x180029203  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029206  call    cs:__imp_WaitForSingleObject
0x18002920c  mov     rcx, rsi
0x18002920f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180029214  mov     rax, [r14]
0x180029217  mov     dl, 1
0x180029219  mov     rcx, r14
0x18002921c  mov     rax, [rax+0A8h]
0x180029223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029228  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180029231  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180029239  mov     r9, rbx; lpParameter
0x18002923c  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCListSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x180029243  xor     edx, edx; dwStackSize
0x180029245  xor     ecx, ecx; lpThreadAttributes
0x180029247  call    cs:__imp_CreateThread
0x18002924d  mov     rdx, rax
0x180029250  mov     rcx, rsi
0x180029253  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x180029258  cmp     qword ptr [rdi+0E0h], 0
0x180029260  jnz     short loc_18002928B
0x180029262  call    cs:__imp_GetLastError
0x180029268  test    eax, eax
0x18002926a  jle     short loc_180029276
0x18002926c  movzx   eax, ax
0x18002926f  or      eax, 80070000h
0x180029274  test    eax, eax
0x180029276  jns     short loc_18002928B
0x180029278  mov     rcx, rbx; void *
0x18002927b  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCDwordRangeSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x180029280  mov     rdx, r14
0x180029283  mov     rcx, rdi
0x180029286  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCDwordRangeSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CDwordRangeSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x18002928b  add     rsp, 38h
0x18002928f  pop     r14
0x180029291  pop     rdi
0x180029292  pop     rsi
0x180029293  pop     rbx
0x180029294  retn
```
