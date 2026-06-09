# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x180017560`
- end: `0x1800176b5`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800042b4`
- `0x1800105a4`
- `0x180010d1c`
- `0x180011844`
- `0x180011ae4`
- `0x180017560`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017607`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001767a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001767a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001764e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001764e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(
        __int64 a1,
        __int64 a2)
{
  HANDLE Thread; // rax
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // rcx
  HANDLE v10; // rbp
  bool v11; // sf

  LODWORD(Thread) = _InterlockedExchange((volatile __int32 *)(a1 + 160), 2);
  if ( !(_DWORD)Thread )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    v6 = v5;
    if ( !v5 )
    {
LABEL_18:
      LODWORD(Thread) = SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(
                          a1,
                          a2);
      return (int)Thread;
    }
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
    v10 = Thread;
    if ( Thread == *(HANDLE *)(a1 + 176) )
    {
      v10 = *(HANDLE *)(a1 + 176);
    }
    else
    {
      LODWORD(Thread) = Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(a1 + 168);
      *(_QWORD *)(a1 + 176) = v10;
    }
    if ( !v10 )
    {
      LODWORD(Thread) = GetLastError();
      v11 = (int)Thread < 0;
      if ( (int)Thread > 0 )
      {
        LODWORD(Thread) = (unsigned __int16)Thread | 0x80070000;
        v11 = (int)Thread < 0;
      }
      if ( v11 )
      {
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(v6);
        goto LABEL_18;
      }
    }
  }
  return (int)Thread;
}

```

## disassembly

```asm
0x180017560  push    rbx
0x180017562  push    rbp
0x180017563  push    rsi
0x180017564  push    rdi
0x180017565  push    r14
0x180017567  sub     rsp, 30h
0x18001756b  mov     r14, rdx
0x18001756e  mov     rdi, rcx
0x180017571  mov     eax, 2
0x180017576  xchg    eax, [rcx+0A0h]
0x18001757c  test    eax, eax
0x18001757e  jnz     loc_1800176A9
0x180017584  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001758b  lea     ecx, [rax+18h]; unsigned __int64
0x18001758e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017593  mov     rbx, rax
0x180017596  test    rax, rax
0x180017599  jz      loc_18001769E
0x18001759f  mov     qword ptr [rax], 0
0x1800175a6  mov     qword ptr [rax+8], 0
0x1800175ae  lea     rcx, [rax+8]
0x1800175b2  mov     rdx, r14
0x1800175b5  call    ??4?$ComPtr@VCSettingBase@DataModel@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@PEAVCSettingBase@DataModel@SystemSettings@@@Z; Microsoft::WRL::ComPtr<SystemSettings::DataModel::CSettingBase>::operator=(SystemSettings::DataModel::CSettingBase *)
0x1800175ba  cmp     [rbx], rdi
0x1800175bd  jz      short loc_1800175EC
0x1800175bf  test    rdi, rdi
0x1800175c2  jz      short loc_1800175D4
0x1800175c4  mov     rax, [rdi]
0x1800175c7  mov     rcx, rdi
0x1800175ca  mov     rax, [rax+8]
0x1800175ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d3  nop
0x1800175d4  mov     rcx, [rbx]
0x1800175d7  mov     [rbx], rdi
0x1800175da  test    rcx, rcx
0x1800175dd  jz      short loc_1800175EC
0x1800175df  mov     rax, [rcx]
0x1800175e2  mov     rax, [rax+10h]
0x1800175e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175eb  nop
0x1800175ec  mov     qword ptr [rbx+10h], 0
0x1800175f4  lea     rsi, [rdi+0A8h]
0x1800175fb  mov     rcx, [rsi+8]; hHandle
0x1800175ff  test    rcx, rcx
0x180017602  jz      short loc_18001761B
0x180017604  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017607  call    cs:__imp_WaitForSingleObject
0x18001760e  nop     dword ptr [rax+rax+00h]
0x180017613  mov     rcx, rsi
0x180017616  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18001761b  mov     rax, [r14]
0x18001761e  mov     dl, 1
0x180017620  mov     rcx, r14
0x180017623  mov     rax, [rax+0A8h]
0x18001762a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001762f  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180017638  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180017640  mov     r9, rbx; lpParameter
0x180017643  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x18001764a  xor     edx, edx; dwStackSize
0x18001764c  xor     ecx, ecx; lpThreadAttributes
0x18001764e  call    cs:__imp_CreateThread
0x180017655  nop     dword ptr [rax+rax+00h]
0x18001765a  mov     rbp, rax
0x18001765d  cmp     rax, [rsi+8]
0x180017661  jz      short loc_180017671
0x180017663  mov     rcx, rsi
0x180017666  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18001766b  mov     [rsi+8], rbp
0x18001766f  jmp     short loc_180017675
0x180017671  mov     rbp, [rsi+8]
0x180017675  test    rbp, rbp
0x180017678  jnz     short loc_1800176A9
0x18001767a  call    cs:__imp_GetLastError
0x180017681  nop     dword ptr [rax+rax+00h]
0x180017686  test    eax, eax
0x180017688  jle     short loc_180017694
0x18001768a  movzx   eax, ax
0x18001768d  or      eax, 80070000h
0x180017692  test    eax, eax
0x180017694  jns     short loc_1800176A9
0x180017696  mov     rcx, rbx; void *
0x180017699  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18001769e  mov     rdx, r14
0x1800176a1  mov     rcx, rdi
0x1800176a4  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x1800176a9  add     rsp, 30h
0x1800176ad  pop     r14
0x1800176af  pop     rdi
0x1800176b0  pop     rsi
0x1800176b1  pop     rbp
0x1800176b2  pop     rbx
0x1800176b3  retn
```
