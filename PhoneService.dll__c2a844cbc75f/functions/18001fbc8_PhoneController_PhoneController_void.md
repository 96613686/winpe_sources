# PhoneController::~PhoneController(void)

- ea: `0x18001fbc8`
- end: `0x18001fe8b`
- name: `??1PhoneController@@IEAA@XZ`
- size: `707`
- prototype: `void __fastcall(PhoneController *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f1c4`

## callees

- `0x1800056a0`
- `0x18001d764`
- `0x18001fbc8`
- `0x18004b39c`
- `0x18004b41c`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fd86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fd86`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd4f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd61`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd4f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fd61`

## pseudocode

```c
void __fastcall PhoneController::~PhoneController(PhoneController *this)
{
  __int64 v2; // rcx
  __int64 **v3; // rdi
  __int64 *v4; // rcx
  __int64 *v5; // rdx
  __int64 v6; // rax
  void *v7; // rcx
  char *v8; // rcx
  __int64 **v9; // rdi
  __int64 *v10; // rcx
  __int64 *v11; // rdx
  __int64 v12; // rax
  void *v13; // rcx
  char *v14; // rcx
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  void (__fastcall ***v22)(_QWORD, __int64); // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 **v26; // rsi
  __int64 *v27; // rdi
  __int64 *v28; // rdx
  __int64 v29; // rax
  __int64 *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx

  v2 = *((_QWORD *)this + 92);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = (__int64 **)((char *)this + 688);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (__int64 *)v3 )
      break;
    v5 = (__int64 *)v4[1];
    v6 = *v4;
    *v5 = *v4;
    *(_QWORD *)(v6 + 8) = v5;
    operator delete(v4);
  }
  v7 = (void *)*((_QWORD *)this + 88);
  *((_QWORD *)this + 89) = 0;
  if ( v7 )
    operator delete(v7);
  v8 = (char *)*((_QWORD *)this + 82);
  if ( v8 != (char *)this + 672 )
    operator delete(v8);
  v9 = (__int64 **)((char *)this + 592);
  while ( 1 )
  {
    v10 = *v9;
    if ( *v9 == (__int64 *)v9 )
      break;
    v11 = (__int64 *)v10[1];
    v12 = *v10;
    *v11 = *v10;
    *(_QWORD *)(v12 + 8) = v11;
    operator delete(v10);
  }
  v13 = (void *)*((_QWORD *)this + 76);
  *((_QWORD *)this + 77) = 0;
  if ( v13 )
    operator delete(v13);
  v14 = (char *)*((_QWORD *)this + 66);
  if ( v14 != (char *)this + 544 )
    operator delete(v14);
  v15 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 64);
  if ( v15 )
    (**v15)(v15, 1);
  v16 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 63);
  if ( v16 )
    (**v16)(v16, 1);
  v17 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 62);
  if ( v17 )
    (**v17)(v17, 1);
  v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 61);
  if ( v18 )
    (**v18)(v18, 1);
  v19 = *((_QWORD *)this + 60);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = *((_QWORD *)this + 59);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( *((_QWORD *)this + 38) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( *((_QWORD *)this + 37) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  v21 = *((_QWORD *)this + 33);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  v22 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 27);
  if ( v22 )
    (**v22)(v22, 1);
  v23 = *((_QWORD *)this + 26);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear((char *)this + 184);
  v24 = *((_QWORD *)this + 22);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = *((_QWORD *)this + 19);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  utl::list<tlx::auto_ptr<PhoneController::ConferenceHandleInfo,&void tlx::_delete<PhoneController::ConferenceHandleInfo>(PhoneController::ConferenceHandleInfo *)>,utl::allocator<tlx::auto_ptr<PhoneController::ConferenceHandleInfo,&void tlx::_delete<PhoneController::ConferenceHandleInfo>(PhoneController::ConferenceHandleInfo *)>>>::clear((char *)this + 128);
  v26 = (__int64 **)((char *)this + 104);
  while ( 1 )
  {
    v27 = *v26;
    if ( *v26 == (__int64 *)v26 )
      break;
    v28 = (__int64 *)v27[1];
    v29 = *v27;
    *v28 = *v27;
    *(_QWORD *)(v29 + 8) = v28;
    v30 = (__int64 *)v27[2];
    if ( v30 )
      tlx::_delete<PhoneController::RequestInfo>(v30);
    operator delete(v27);
  }
  *((_QWORD *)this + 15) = 0;
  v31 = *((_QWORD *)this + 12);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v32 = *((_QWORD *)this + 11);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  v33 = *((_QWORD *)this + 9);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
}

```

## disassembly

```asm
0x18001fbc8  push    rbx
0x18001fbca  push    rsi
0x18001fbcb  push    rdi
0x18001fbcc  push    r14
0x18001fbce  sub     rsp, 28h
0x18001fbd2  mov     rbx, rcx
0x18001fbd5  mov     rcx, [rcx+2E0h]
0x18001fbdc  test    rcx, rcx
0x18001fbdf  jz      short loc_18001FBED
0x18001fbe1  mov     rax, [rcx]
0x18001fbe4  mov     rax, [rax+10h]
0x18001fbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbed  lea     rdi, [rbx+2B0h]
0x18001fbf4  lea     r14, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001fbfb  mov     rcx, [rdi]; Block
0x18001fbfe  cmp     rcx, rdi
0x18001fc01  jz      short loc_18001FC1B
0x18001fc03  mov     rdx, [rcx+8]
0x18001fc07  mov     rax, [rcx]
0x18001fc0a  mov     [rdx], rax
0x18001fc0d  mov     [rax+8], rdx
0x18001fc11  mov     rdx, r14
0x18001fc14  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc19  jmp     short loc_18001FBFB
0x18001fc1b  mov     rcx, [rdi+10h]; Block
0x18001fc1f  mov     qword ptr [rdi+18h], 0
0x18001fc27  test    rcx, rcx
0x18001fc2a  jz      short loc_18001FC34
0x18001fc2c  mov     rdx, r14
0x18001fc2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc34  mov     rcx, [rbx+290h]; Block
0x18001fc3b  lea     rax, [rbx+2A0h]
0x18001fc42  cmp     rcx, rax
0x18001fc45  jz      short loc_18001FC4F
0x18001fc47  mov     rdx, r14
0x18001fc4a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc4f  lea     rdi, [rbx+250h]
0x18001fc56  mov     rcx, [rdi]; Block
0x18001fc59  cmp     rcx, rdi
0x18001fc5c  jz      short loc_18001FC76
0x18001fc5e  mov     rdx, [rcx+8]
0x18001fc62  mov     rax, [rcx]
0x18001fc65  mov     [rdx], rax
0x18001fc68  mov     [rax+8], rdx
0x18001fc6c  mov     rdx, r14
0x18001fc6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc74  jmp     short loc_18001FC56
0x18001fc76  mov     rcx, [rdi+10h]; Block
0x18001fc7a  mov     qword ptr [rdi+18h], 0
0x18001fc82  test    rcx, rcx
0x18001fc85  jz      short loc_18001FC8F
0x18001fc87  mov     rdx, r14
0x18001fc8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc8f  mov     rcx, [rbx+210h]; Block
0x18001fc96  lea     rax, [rbx+220h]
0x18001fc9d  cmp     rcx, rax
0x18001fca0  jz      short loc_18001FCAA
0x18001fca2  mov     rdx, r14
0x18001fca5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fcaa  mov     rcx, [rbx+200h]
0x18001fcb1  mov     edi, 1
0x18001fcb6  test    rcx, rcx
0x18001fcb9  jz      short loc_18001FCC8
0x18001fcbb  mov     rax, [rcx]
0x18001fcbe  mov     edx, edi
0x18001fcc0  mov     rax, [rax]
0x18001fcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcc8  mov     rcx, [rbx+1F8h]
0x18001fccf  test    rcx, rcx
0x18001fcd2  jz      short loc_18001FCE1
0x18001fcd4  mov     rax, [rcx]
0x18001fcd7  mov     edx, edi
0x18001fcd9  mov     rax, [rax]
0x18001fcdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce1  mov     rcx, [rbx+1F0h]
0x18001fce8  test    rcx, rcx
0x18001fceb  jz      short loc_18001FCFA
0x18001fced  mov     rax, [rcx]
0x18001fcf0  mov     edx, edi
0x18001fcf2  mov     rax, [rax]
0x18001fcf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcfa  mov     rcx, [rbx+1E8h]
0x18001fd01  test    rcx, rcx
0x18001fd04  jz      short loc_18001FD13
0x18001fd06  mov     rax, [rcx]
0x18001fd09  mov     edx, edi
0x18001fd0b  mov     rax, [rax]
0x18001fd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd13  mov     rcx, [rbx+1E0h]
0x18001fd1a  test    rcx, rcx
0x18001fd1d  jz      short loc_18001FD2B
0x18001fd1f  mov     rax, [rcx]
0x18001fd22  mov     rax, [rax+10h]
0x18001fd26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd2b  mov     rcx, [rbx+1D8h]
0x18001fd32  test    rcx, rcx
0x18001fd35  jz      short loc_18001FD43
0x18001fd37  mov     rax, [rcx]
0x18001fd3a  mov     rax, [rax+10h]
0x18001fd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd43  mov     rcx, [rbx+130h]
0x18001fd4a  test    rcx, rcx
0x18001fd4d  jz      short loc_18001FD55
0x18001fd4f  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fd55  mov     rcx, [rbx+128h]
0x18001fd5c  test    rcx, rcx
0x18001fd5f  jz      short loc_18001FD67
0x18001fd61  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fd67  mov     rcx, [rbx+108h]
0x18001fd6e  test    rcx, rcx
0x18001fd71  jz      short loc_18001FD7F
0x18001fd73  mov     rax, [rcx]
0x18001fd76  mov     rax, [rax+10h]
0x18001fd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd7f  lea     rcx, [rbx+0E0h]; lpCriticalSection
0x18001fd86  call    cs:__imp_DeleteCriticalSection
0x18001fd8c  mov     rcx, [rbx+0D8h]
0x18001fd93  test    rcx, rcx
0x18001fd96  jz      short loc_18001FDA5
0x18001fd98  mov     rax, [rcx]
0x18001fd9b  mov     edx, edi
0x18001fd9d  mov     rax, [rax]
0x18001fda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fda5  mov     rcx, [rbx+0D0h]
0x18001fdac  test    rcx, rcx
0x18001fdaf  jz      short loc_18001FDBD
0x18001fdb1  mov     rax, [rcx]
0x18001fdb4  mov     rax, [rax+10h]
0x18001fdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdbd  lea     rcx, [rbx+0B8h]
0x18001fdc4  call    ?clear@?$list@V?$CComPtr@VRegistryValue@@@ATL@@V?$allocator@V?$CComPtr@VRegistryValue@@@ATL@@@utl@@@utl@@QEAAXXZ; utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear(void)
0x18001fdc9  mov     rcx, [rbx+0B0h]
0x18001fdd0  test    rcx, rcx
0x18001fdd3  jz      short loc_18001FDE1
0x18001fdd5  mov     rax, [rcx]
0x18001fdd8  mov     rax, [rax+10h]
0x18001fddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fde1  mov     rcx, [rbx+98h]
0x18001fde8  test    rcx, rcx
0x18001fdeb  jz      short loc_18001FDF9
0x18001fded  mov     rax, [rcx]
0x18001fdf0  mov     rax, [rax+10h]
0x18001fdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdf9  lea     rcx, [rbx+80h]
0x18001fe00  call    ?clear@?$list@V?$auto_ptr@VConferenceHandleInfo@PhoneController@@$1??$_delete@VConferenceHandleInfo@PhoneController@@@tlx@@YAXPEAV12@@Z@tlx@@V?$allocator@V?$auto_ptr@VConferenceHandleInfo@PhoneController@@$1??$_delete@VConferenceHandleInfo@PhoneController@@@tlx@@YAXPEAV12@@Z@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::auto_ptr<PhoneController::ConferenceHandleInfo,&tlx::_delete<PhoneController::ConferenceHandleInfo>(PhoneController::ConferenceHandleInfo *)>,utl::allocator<tlx::auto_ptr<PhoneController::ConferenceHandleInfo,&tlx::_delete<PhoneController::ConferenceHandleInfo>(PhoneController::ConferenceHandleInfo *)>>>::clear(void)
0x18001fe05  lea     rsi, [rbx+68h]
0x18001fe09  mov     rdi, [rsi]
0x18001fe0c  cmp     rdi, rsi
0x18001fe0f  jz      short loc_18001FE3A
0x18001fe11  mov     rdx, [rdi+8]
0x18001fe15  mov     rax, [rdi]
0x18001fe18  mov     [rdx], rax
0x18001fe1b  mov     [rax+8], rdx
0x18001fe1f  mov     rcx, [rdi+10h]; Block
0x18001fe23  test    rcx, rcx
0x18001fe26  jz      short loc_18001FE2D
0x18001fe28  call    ??$_delete@URequestInfo@PhoneController@@@tlx@@YAXPEAURequestInfo@PhoneController@@@Z; tlx::_delete<PhoneController::RequestInfo>(PhoneController::RequestInfo *)
0x18001fe2d  mov     rdx, r14
0x18001fe30  mov     rcx, rdi; Block
0x18001fe33  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fe38  jmp     short loc_18001FE09
0x18001fe3a  mov     qword ptr [rsi+10h], 0
0x18001fe42  mov     rcx, [rbx+60h]
0x18001fe46  test    rcx, rcx
0x18001fe49  jz      short loc_18001FE57
0x18001fe4b  mov     rax, [rcx]
0x18001fe4e  mov     rax, [rax+10h]
0x18001fe52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe57  mov     rcx, [rbx+58h]
0x18001fe5b  test    rcx, rcx
0x18001fe5e  jz      short loc_18001FE6C
0x18001fe60  mov     rax, [rcx]
0x18001fe63  mov     rax, [rax+10h]
0x18001fe67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe6c  mov     rcx, [rbx+48h]
0x18001fe70  test    rcx, rcx
0x18001fe73  jz      short loc_18001FE81
0x18001fe75  mov     rax, [rcx]
0x18001fe78  mov     rax, [rax+10h]
0x18001fe7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe81  add     rsp, 28h
0x18001fe85  pop     r14
0x18001fe87  pop     rdi
0x18001fe88  pop     rsi
0x18001fe89  pop     rbx
0x18001fe8a  retn
```
