# SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(SystemSettings::DataModel::CSettingBase *)

- ea: `0x18003e3b0`
- end: `0x18003e51b`
- name: `?StartGenericAsyncWork@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@UEAAXPEAVCSettingBase@23@@Z`
- size: `363`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000398c`
- `0x180015e78`
- `0x18003bb3c`
- `0x18003beb8`
- `0x18003e3b0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e480`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003e480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e4e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e4e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e4c1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e4c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::StartGenericAsyncWork(
        __int64 a1,
        __int64 a2)
{
  HANDLE Thread; // rax
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  HANDLE v11; // r14
  bool v12; // sf

  LODWORD(Thread) = _InterlockedExchange((volatile __int32 *)(a1 + 160), 2);
  if ( !(_DWORD)Thread )
  {
    v5 = (__int64 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v5;
    if ( !v5 )
    {
LABEL_23:
      LODWORD(Thread) = SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(
                          a1,
                          a2);
      return (int)Thread;
    }
    *v5 = 0;
    v5[1] = 0;
    if ( v5[1] != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
      v8 = v7[1];
      v7[1] = a2;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( *v7 != a1 )
    {
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
      v9 = *v7;
      *v7 = a1;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v7[2] = 0;
    v10 = *(void **)(a1 + 176);
    if ( v10 )
    {
      WaitForSingleObject(v10, 0xFFFFFFFF);
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(a1 + 168);
    }
    LOBYTE(v6) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 168LL))(a2, v6);
    Thread = CreateThread(
               0,
               0,
               SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::s_GenericAsyncThread,
               v7,
               0,
               0);
    v11 = Thread;
    if ( Thread == *(HANDLE *)(a1 + 176) )
    {
      v11 = *(HANDLE *)(a1 + 176);
    }
    else
    {
      LODWORD(Thread) = Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(a1 + 168);
      *(_QWORD *)(a1 + 176) = v11;
    }
    if ( !v11 )
    {
      LODWORD(Thread) = GetLastError();
      v12 = (int)Thread < 0;
      if ( (int)Thread > 0 )
      {
        LODWORD(Thread) = (unsigned __int16)Thread | 0x80070000;
        v12 = (int)Thread < 0;
      }
      if ( v12 )
      {
        SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(v7);
        goto LABEL_23;
      }
    }
  }
  return (int)Thread;
}

```

## disassembly

```asm
0x18003e3b0  push    rbx
0x18003e3b2  push    rbp
0x18003e3b3  push    rsi
0x18003e3b4  push    rdi
0x18003e3b5  push    r14
0x18003e3b7  sub     rsp, 30h
0x18003e3bb  mov     rsi, rdx
0x18003e3be  mov     rdi, rcx
0x18003e3c1  mov     eax, 2
0x18003e3c6  xchg    eax, [rcx+0A0h]
0x18003e3cc  test    eax, eax
0x18003e3ce  jnz     loc_18003E510
0x18003e3d4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e3db  lea     ecx, [rax+18h]; unsigned __int64
0x18003e3de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e3e3  mov     rbx, rax
0x18003e3e6  test    rax, rax
0x18003e3e9  jz      loc_18003E505
0x18003e3ef  mov     qword ptr [rax], 0
0x18003e3f6  mov     qword ptr [rax+8], 0
0x18003e3fe  cmp     [rax+8], rsi
0x18003e402  jz      short loc_18003E433
0x18003e404  test    rsi, rsi
0x18003e407  jz      short loc_18003E419
0x18003e409  mov     rax, [rsi]
0x18003e40c  mov     rcx, rsi
0x18003e40f  mov     rax, [rax+8]
0x18003e413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e418  nop
0x18003e419  mov     rcx, [rbx+8]
0x18003e41d  mov     [rbx+8], rsi
0x18003e421  test    rcx, rcx
0x18003e424  jz      short loc_18003E433
0x18003e426  mov     rax, [rcx]
0x18003e429  mov     rax, [rax+10h]
0x18003e42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e432  nop
0x18003e433  cmp     [rbx], rdi
0x18003e436  jz      short loc_18003E465
0x18003e438  test    rdi, rdi
0x18003e43b  jz      short loc_18003E44D
0x18003e43d  mov     rax, [rdi]
0x18003e440  mov     rcx, rdi
0x18003e443  mov     rax, [rax+8]
0x18003e447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e44c  nop
0x18003e44d  mov     rcx, [rbx]
0x18003e450  mov     [rbx], rdi
0x18003e453  test    rcx, rcx
0x18003e456  jz      short loc_18003E465
0x18003e458  mov     rax, [rcx]
0x18003e45b  mov     rax, [rax+10h]
0x18003e45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e464  nop
0x18003e465  mov     qword ptr [rbx+10h], 0
0x18003e46d  lea     rbp, [rdi+0A8h]
0x18003e474  mov     rcx, [rbp+8]; hHandle
0x18003e478  test    rcx, rcx
0x18003e47b  jz      short loc_18003E48E
0x18003e47d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003e480  call    cs:__imp_WaitForSingleObject
0x18003e486  mov     rcx, rbp
0x18003e489  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003e48e  mov     rax, [rsi]
0x18003e491  mov     dl, 1
0x18003e493  mov     rcx, rsi
0x18003e496  mov     rax, [rax+0A8h]
0x18003e49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4a2  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18003e4ab  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18003e4b3  mov     r9, rbx; lpParameter
0x18003e4b6  lea     r8, ?s_GenericAsyncThread@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@CAKPEAX@Z; lpStartAddress
0x18003e4bd  xor     edx, edx; dwStackSize
0x18003e4bf  xor     ecx, ecx; lpThreadAttributes
0x18003e4c1  call    cs:__imp_CreateThread
0x18003e4c7  mov     r14, rax
0x18003e4ca  cmp     rax, [rbp+8]
0x18003e4ce  jz      short loc_18003E4DE
0x18003e4d0  mov     rcx, rbp
0x18003e4d3  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003e4d8  mov     [rbp+8], r14
0x18003e4dc  jmp     short loc_18003E4E2
0x18003e4de  mov     r14, [rbp+8]
0x18003e4e2  test    r14, r14
0x18003e4e5  jnz     short loc_18003E510
0x18003e4e7  call    cs:__imp_GetLastError
0x18003e4ed  test    eax, eax
0x18003e4ef  jle     short loc_18003E4FB
0x18003e4f1  movzx   eax, ax
0x18003e4f4  or      eax, 80070000h
0x18003e4f9  test    eax, eax
0x18003e4fb  jns     short loc_18003E510
0x18003e4fd  mov     rcx, rbx; void *
0x18003e500  call    ??_GASYNC_PARAMS@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@QEAAPEAXI@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::ASYNC_PARAMS::`scalar deleting destructor'(uint)
0x18003e505  mov     rdx, rsi
0x18003e508  mov     rcx, rdi
0x18003e50b  call    ?DoAsyncWorkInternal@?$CGenericAsyncHelper@VCSettingBase@DataModel@SystemSettings@@@DataModel@SystemSettings@@AEAAXPEAVCSettingBase@23@@Z; SystemSettings::DataModel::CGenericAsyncHelper<SystemSettings::DataModel::CSettingBase>::DoAsyncWorkInternal(SystemSettings::DataModel::CSettingBase *)
0x18003e510  add     rsp, 30h
0x18003e514  pop     r14
0x18003e516  pop     rdi
0x18003e517  pop     rsi
0x18003e518  pop     rbp
0x18003e519  pop     rbx
0x18003e51a  retn
```
