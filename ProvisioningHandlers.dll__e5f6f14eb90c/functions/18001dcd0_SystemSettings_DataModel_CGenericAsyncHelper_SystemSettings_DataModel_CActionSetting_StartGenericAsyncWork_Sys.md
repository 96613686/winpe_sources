# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x18001dcd0`
- end: `0x18001de18`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
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
- `0x180013884`
- `0x18001dcd0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dd76`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddde`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ddbd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ddbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::StartGenericAsyncWork(
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

  result = _InterlockedExchange((volatile __int32 *)(a1 + 216), 2);
  if ( !result )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( !v5 )
      return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(
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
    v9 = *(void **)(a1 + 232);
    if ( v9 )
    {
      WaitForSingleObject(v9, 0xFFFFFFFF);
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(a1 + 224);
    }
    LOBYTE(v7) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 168LL))(a2, v7);
    Thread = CreateThread(
               0,
               0,
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::s_GenericAsyncThread,
               v6,
               0,
               0);
    result = Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(
               a1 + 224,
               Thread);
    if ( !*(_QWORD *)(a1 + 232) )
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
        return SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(
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
0x18001dcd0  push    rbx
0x18001dcd2  push    rsi
0x18001dcd3  push    rdi
0x18001dcd4  push    r14
0x18001dcd6  sub     rsp, 38h
0x18001dcda  mov     r14, rdx
0x18001dcdd  mov     rdi, rcx
0x18001dce0  mov     eax, 2
0x18001dce5  xchg    eax, [rcx+0D8h]
0x18001dceb  test    eax, eax
0x18001dced  jnz     loc_18001DE0D
0x18001dcf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001dcfa  lea     ecx, [rax+18h]; unsigned __int64
0x18001dcfd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dd02  mov     rbx, rax
0x18001dd05  test    rax, rax
0x18001dd08  jz      loc_18001DE02
0x18001dd0e  mov     qword ptr [rax], 0
0x18001dd15  mov     qword ptr [rax+8], 0
0x18001dd1d  lea     rcx, [rax+8]
0x18001dd21  mov     rdx, r14
0x18001dd24  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x18001dd29  cmp     [rbx], rdi
0x18001dd2c  jz      short loc_18001DD5B
0x18001dd2e  test    rdi, rdi
0x18001dd31  jz      short loc_18001DD43
0x18001dd33  mov     rax, [rdi]
0x18001dd36  mov     rcx, rdi
0x18001dd39  mov     rax, [rax+8]
0x18001dd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd42  nop
0x18001dd43  mov     rcx, [rbx]
0x18001dd46  mov     [rbx], rdi
0x18001dd49  test    rcx, rcx
0x18001dd4c  jz      short loc_18001DD5B
0x18001dd4e  mov     rax, [rcx]
0x18001dd51  mov     rax, [rax+10h]
0x18001dd55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd5a  nop
0x18001dd5b  mov     qword ptr [rbx+10h], 0
0x18001dd63  lea     rsi, [rdi+0E0h]
0x18001dd6a  mov     rcx, [rsi+8]; hHandle
0x18001dd6e  test    rcx, rcx
0x18001dd71  jz      short loc_18001DD8A
0x18001dd73  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001dd76  call    cs:__imp_WaitForSingleObject
0x18001dd7d  nop     dword ptr [rax+rax+00h]
0x18001dd82  mov     rcx, rsi
0x18001dd85  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18001dd8a  mov     rax, [r14]
0x18001dd8d  mov     dl, 1
0x18001dd8f  mov     rcx, r14
0x18001dd92  mov     rax, [rax+0A8h]
0x18001dd99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd9e  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18001dda7  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18001ddaf  mov     r9, rbx; lpParameter
0x18001ddb2  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x18001ddb9  xor     edx, edx; dwStackSize
0x18001ddbb  xor     ecx, ecx; lpThreadAttributes
0x18001ddbd  call    cs:__imp_CreateThread
0x18001ddc4  nop     dword ptr [rax+rax+00h]
0x18001ddc9  mov     rdx, rax
0x18001ddcc  mov     rcx, rsi
0x18001ddcf  call    ?Attach@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Attach(void *)
0x18001ddd4  cmp     qword ptr [rdi+0E8h], 0
0x18001dddc  jnz     short loc_18001DE0D
0x18001ddde  call    cs:__imp_GetLastError
0x18001dde5  nop     dword ptr [rax+rax+00h]
0x18001ddea  test    eax, eax
0x18001ddec  jle     short loc_18001DDF8
0x18001ddee  movzx   eax, ax
0x18001ddf1  or      eax, 80070000h
0x18001ddf6  test    eax, eax
0x18001ddf8  jns     short loc_18001DE0D
0x18001ddfa  mov     rcx, rbx
0x18001ddfd  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18001de02  mov     rdx, r14
0x18001de05  mov     rcx, rdi
0x18001de08  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCActionSetting@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CActionSetting>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x18001de0d  add     rsp, 38h
0x18001de11  pop     r14
0x18001de13  pop     rdi
0x18001de14  pop     rsi
0x18001de15  pop     rbx
0x18001de16  retn
```
