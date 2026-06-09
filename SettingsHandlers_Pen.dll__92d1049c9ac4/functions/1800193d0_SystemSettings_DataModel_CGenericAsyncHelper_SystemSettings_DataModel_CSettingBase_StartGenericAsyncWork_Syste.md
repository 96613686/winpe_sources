# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x1800193d0`
- end: `0x180019505`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
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
- `0x180012914`
- `0x1800193d0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019476`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800194d2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800194b7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800194b7`

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
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
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
0x1800193d0  push    rbx
0x1800193d2  push    rsi
0x1800193d3  push    rdi
0x1800193d4  push    r14
0x1800193d6  sub     rsp, 38h
0x1800193da  mov     r14, rdx
0x1800193dd  mov     rdi, rcx
0x1800193e0  mov     eax, 2
0x1800193e5  xchg    eax, [rcx+0A0h]
0x1800193eb  test    eax, eax
0x1800193ed  jnz     loc_1800194FB
0x1800193f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800193fa  lea     ecx, [rax+18h]; unsigned __int64
0x1800193fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180019402  mov     rbx, rax
0x180019405  test    rax, rax
0x180019408  jz      loc_1800194F0
0x18001940e  mov     qword ptr [rax], 0
0x180019415  mov     qword ptr [rax+8], 0
0x18001941d  lea     rcx, [rax+8]
0x180019421  mov     rdx, r14
0x180019424  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x180019429  cmp     [rbx], rdi
0x18001942c  jz      short loc_18001945B
0x18001942e  test    rdi, rdi
0x180019431  jz      short loc_180019443
0x180019433  mov     rax, [rdi]
0x180019436  mov     rcx, rdi
0x180019439  mov     rax, [rax+8]
0x18001943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019442  nop
0x180019443  mov     rcx, [rbx]
0x180019446  mov     [rbx], rdi
0x180019449  test    rcx, rcx
0x18001944c  jz      short loc_18001945B
0x18001944e  mov     rax, [rcx]
0x180019451  mov     rax, [rax+10h]
0x180019455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001945a  nop
0x18001945b  mov     qword ptr [rbx+10h], 0
0x180019463  lea     rsi, [rdi+0A8h]
0x18001946a  mov     rcx, [rsi+8]; hHandle
0x18001946e  test    rcx, rcx
0x180019471  jz      short loc_180019484
0x180019473  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019476  call    cs:__imp_WaitForSingleObject
0x18001947c  mov     rcx, rsi
0x18001947f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180019484  mov     rax, [r14]
0x180019487  mov     dl, 1
0x180019489  mov     rcx, r14
0x18001948c  mov     rax, [rax+0A8h]
0x180019493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019498  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x1800194a1  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800194a9  mov     r9, rbx; lpParameter
0x1800194ac  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x1800194b3  xor     edx, edx; dwStackSize
0x1800194b5  xor     ecx, ecx; lpThreadAttributes
0x1800194b7  call    cs:__imp_CreateThread
0x1800194bd  mov     rdx, rax
0x1800194c0  mov     rcx, rsi
0x1800194c3  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x1800194c8  cmp     qword ptr [rdi+0B0h], 0
0x1800194d0  jnz     short loc_1800194FB
0x1800194d2  call    cs:__imp_GetLastError
0x1800194d8  test    eax, eax
0x1800194da  jle     short loc_1800194E6
0x1800194dc  movzx   eax, ax
0x1800194df  or      eax, 80070000h
0x1800194e4  test    eax, eax
0x1800194e6  jns     short loc_1800194FB
0x1800194e8  mov     rcx, rbx; Block
0x1800194eb  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x1800194f0  mov     rdx, r14
0x1800194f3  mov     rcx, rdi
0x1800194f6  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x1800194fb  add     rsp, 38h
0x1800194ff  pop     r14
0x180019501  pop     rdi
0x180019502  pop     rsi
0x180019503  pop     rbx
0x180019504  retn
```
