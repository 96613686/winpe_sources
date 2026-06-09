# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x18001de20`
- end: `0x18001df68`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800034b8`
- `0x180011350`
- `0x180011b04`
- `0x1800125e8`
- `0x180012874`
- `0x18001392c`
- `0x18001de20`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dec6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001df2e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001df0d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001df0d`

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
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(v6);
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
0x18001de20  push    rbx
0x18001de22  push    rsi
0x18001de23  push    rdi
0x18001de24  push    r14
0x18001de26  sub     rsp, 38h
0x18001de2a  mov     r14, rdx
0x18001de2d  mov     rdi, rcx
0x18001de30  mov     eax, 2
0x18001de35  xchg    eax, [rcx+0A0h]
0x18001de3b  test    eax, eax
0x18001de3d  jnz     loc_18001DF5D
0x18001de43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001de4a  lea     ecx, [rax+18h]; unsigned __int64
0x18001de4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001de52  mov     rbx, rax
0x18001de55  test    rax, rax
0x18001de58  jz      loc_18001DF52
0x18001de5e  mov     qword ptr [rax], 0
0x18001de65  mov     qword ptr [rax+8], 0
0x18001de6d  lea     rcx, [rax+8]
0x18001de71  mov     rdx, r14
0x18001de74  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18001de79  cmp     [rbx], rdi
0x18001de7c  jz      short loc_18001DEAB
0x18001de7e  test    rdi, rdi
0x18001de81  jz      short loc_18001DE93
0x18001de83  mov     rax, [rdi]
0x18001de86  mov     rcx, rdi
0x18001de89  mov     rax, [rax+8]
0x18001de8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de92  nop
0x18001de93  mov     rcx, [rbx]
0x18001de96  mov     [rbx], rdi
0x18001de99  test    rcx, rcx
0x18001de9c  jz      short loc_18001DEAB
0x18001de9e  mov     rax, [rcx]
0x18001dea1  mov     rax, [rax+10h]
0x18001dea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deaa  nop
0x18001deab  mov     qword ptr [rbx+10h], 0
0x18001deb3  lea     rsi, [rdi+0A8h]
0x18001deba  mov     rcx, [rsi+8]; hHandle
0x18001debe  test    rcx, rcx
0x18001dec1  jz      short loc_18001DEDA
0x18001dec3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001dec6  call    cs:__imp_WaitForSingleObject
0x18001decd  nop     dword ptr [rax+rax+00h]
0x18001ded2  mov     rcx, rsi
0x18001ded5  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18001deda  mov     rax, [r14]
0x18001dedd  mov     dl, 1
0x18001dedf  mov     rcx, r14
0x18001dee2  mov     rax, [rax+0A8h]
0x18001dee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deee  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18001def7  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001deff  mov     r9, rbx; lpParameter
0x18001df02  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x18001df09  xor     edx, edx; dwStackSize
0x18001df0b  xor     ecx, ecx; lpThreadAttributes
0x18001df0d  call    cs:__imp_CreateThread
0x18001df14  nop     dword ptr [rax+rax+00h]
0x18001df19  mov     rdx, rax
0x18001df1c  mov     rcx, rsi
0x18001df1f  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x18001df24  cmp     qword ptr [rdi+0B0h], 0
0x18001df2c  jnz     short loc_18001DF5D
0x18001df2e  call    cs:__imp_GetLastError
0x18001df35  nop     dword ptr [rax+rax+00h]
0x18001df3a  test    eax, eax
0x18001df3c  jle     short loc_18001DF48
0x18001df3e  movzx   eax, ax
0x18001df41  or      eax, 80070000h
0x18001df46  test    eax, eax
0x18001df48  jns     short loc_18001DF5D
0x18001df4a  mov     rcx, rbx
0x18001df4d  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18001df52  mov     rdx, r14
0x18001df55  mov     rcx, rdi
0x18001df58  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x18001df5d  add     rsp, 38h
0x18001df61  pop     r14
0x18001df63  pop     rdi
0x18001df64  pop     rsi
0x18001df65  pop     rbx
0x18001df66  retn
```
