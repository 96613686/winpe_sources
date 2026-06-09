# CVADServer::~CVADServer(void)

- ea: `0x180023318`
- end: `0x1800235ac`
- name: `??1CVADServer@@UEAA@XZ`
- size: `660`
- prototype: `void __fastcall(CVADServer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180024850`

## callees

- `0x1800151fc`
- `0x180023318`
- `0x180023690`
- `0x1800247c8`
- `0x18002d2d0`
- `0x18002f2cc`
- `0x1800423cc`
- `0x1800cfd60`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800234b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800234bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800234b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800234bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002334e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023409`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002353b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002334e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023409`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002353b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023379`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023431`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002355f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023379`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023431`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002355f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800234f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVADServer::~CVADServer(CVADServer *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  std::_Ref_count_base *v3; // rdi
  volatile signed __int32 *v4; // rdi
  struct CAudioStream **v5; // rdi
  __int64 v6; // rcx
  __int64 i; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx
  __int64 v11; // rcx
  std::_Ref_count_base *v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx

  *(_QWORD *)this = &CVADServer::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 440);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 11);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 61);
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  if ( v2 )
    LeaveCriticalSection(v2);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 17);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 6, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 104LL))(v4);
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = (struct CAudioStream **)((char *)this + 176);
  if ( *((_QWORD *)this + 22) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
    if ( *((_QWORD *)*v5 + 6) )
    {
      if ( *((_DWORD *)this + 42) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 232LL))(*((_QWORD *)this + 18));
      CAudioSession::RemoveStream(*((CAudioSession **)this + 18), *v5, 1);
    }
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset((char *)this + 176);
    if ( this != (CVADServer *)-200LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 5);
  }
  v6 = *((_QWORD *)this + 18);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 18) = 0;
  }
  *((_QWORD *)this + 16) = 0;
  EnterCriticalSection(&g_csVadList);
  for ( i = g_VADServerList; i; i = *(_QWORD *)i )
  {
    if ( *(CVADServer **)(i + 16) == this )
    {
      ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>>::RemoveAt();
      break;
    }
  }
  LeaveCriticalSection(&g_csVadList);
  v8 = *((_QWORD *)this + 69);
  if ( v8 )
  {
    *((_QWORD *)this + 69) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *((_QWORD *)this + 65);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = (void *)*((_QWORD *)this + 63);
  if ( v10 )
    operator delete(v10, (const struct std::nothrow_t *)1);
  v11 = *((_QWORD *)this + 62);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = (std::_Ref_count_base *)*((_QWORD *)this + 61);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  DeleteCriticalSection(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  v13 = (void *)*((_QWORD *)this + 24);
  if ( v13 )
    CoTaskMemFree(v13);
  if ( *v5 )
    (*(void (__fastcall **)(struct CAudioStream *))(*(_QWORD *)*v5 + 16LL))(*v5);
  CoTaskMemFree(*((LPVOID *)this + 19));
  *((_QWORD *)this + 19) = 0;
  CAudioSessionInstanceId::~CAudioSessionInstanceId((CVADServer *)((char *)this + 48));
  v14 = *((_QWORD *)this + 4);
  if ( v14 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v14);
}

```

## disassembly

```asm
0x180023318  push    rbx
0x18002331a  push    rbp
0x18002331b  push    rsi
0x18002331c  push    rdi
0x18002331d  sub     rsp, 28h
0x180023321  mov     rbx, rcx
0x180023324  lea     rax, ??_7CVADServer@@6B@; const CVADServer::`vftable'
0x18002332b  mov     [rcx], rax
0x18002332e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6BIUnknown@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'}
0x180023335  mov     [rcx+8], rax
0x180023339  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180023340  mov     [rcx+10h], rax
0x180023344  lea     rbp, [rcx+1B8h]
0x18002334b  mov     rcx, rbp; lpCriticalSection
0x18002334e  call    cs:__imp_EnterCriticalSection
0x180023354  mov     rdi, [rbx+1E8h]
0x18002335b  mov     qword ptr [rbx+1E0h], 0
0x180023366  mov     qword ptr [rbx+1E8h], 0
0x180023371  test    rbp, rbp
0x180023374  jz      short loc_18002337F
0x180023376  mov     rcx, rbp; lpCriticalSection
0x180023379  call    cs:__imp_LeaveCriticalSection
0x18002337f  test    rdi, rdi
0x180023382  jz      short loc_18002338C
0x180023384  mov     rcx, rdi; this
0x180023387  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002338c  mov     rdi, [rbx+88h]
0x180023393  test    rdi, rdi
0x180023396  jz      short loc_1800233C3
0x180023398  or      eax, 0FFFFFFFFh
0x18002339b  lock xadd [rdi+18h], eax
0x1800233a0  cmp     eax, 1
0x1800233a3  jnz     short loc_1800233B4
0x1800233a5  mov     rax, [rdi]
0x1800233a8  mov     rcx, rdi
0x1800233ab  mov     rax, [rax+68h]
0x1800233af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233b4  mov     rax, [rdi]
0x1800233b7  mov     rcx, rdi
0x1800233ba  mov     rax, [rax+10h]
0x1800233be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233c3  lea     rdi, [rbx+0B0h]
0x1800233ca  cmp     qword ptr [rdi], 0
0x1800233ce  jnz     loc_180023531
0x1800233d4  mov     rcx, [rbx+90h]
0x1800233db  test    rcx, rcx
0x1800233de  jz      short loc_1800233F7
0x1800233e0  mov     rax, [rcx]
0x1800233e3  mov     rax, [rax+10h]
0x1800233e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233ec  mov     qword ptr [rbx+90h], 0
0x1800233f7  mov     qword ptr [rbx+80h], 0
0x180023402  lea     rcx, ?g_csVadList@@3Vcritical_section@wil@@A; lpCriticalSection
0x180023409  call    cs:__imp_EnterCriticalSection
0x18002340f  mov     rdx, cs:?g_VADServerList@@3V?$CAtlList@PEAVCVADServer@@V?$CElementTraits@PEAVCVADServer@@@ATL@@@ATL@@A; ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>> g_VADServerList
0x180023416  test    rdx, rdx
0x180023419  jz      short loc_18002342A
0x18002341b  cmp     [rdx+10h], rbx
0x18002341f  jnz     loc_180023529
0x180023425  call    ?RemoveAt@?$CAtlList@PEAVCVADServer@@V?$CElementTraits@PEAVCVADServer@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>>::RemoveAt(__POSITION *)
0x18002342a  lea     rcx, ?g_csVadList@@3Vcritical_section@wil@@A; lpCriticalSection
0x180023431  call    cs:__imp_LeaveCriticalSection
0x180023437  nop
0x180023438  mov     rcx, [rbx+228h]
0x18002343f  test    rcx, rcx
0x180023442  jz      short loc_18002345C
0x180023444  mov     qword ptr [rbx+228h], 0
0x18002344f  mov     rax, [rcx]
0x180023452  mov     rax, [rax+10h]
0x180023456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002345b  nop
0x18002345c  mov     rcx, [rbx+208h]
0x180023463  test    rcx, rcx
0x180023466  jz      short loc_180023475
0x180023468  mov     rax, [rcx]
0x18002346b  mov     rax, [rax+10h]
0x18002346f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023474  nop
0x180023475  mov     rcx, [rbx+1F8h]; void *
0x18002347c  test    rcx, rcx
0x18002347f  jnz     loc_18002359D
0x180023485  mov     rcx, [rbx+1F0h]
0x18002348c  test    rcx, rcx
0x18002348f  jz      short loc_18002349E
0x180023491  mov     rax, [rcx]
0x180023494  mov     rax, [rax+10h]
0x180023498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002349d  nop
0x18002349e  mov     rcx, [rbx+1E8h]; this
0x1800234a5  test    rcx, rcx
0x1800234a8  jz      short loc_1800234AF
0x1800234aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800234af  mov     rcx, rbp; lpCriticalSection
0x1800234b2  call    cs:__imp_DeleteCriticalSection
0x1800234b8  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800234bf  call    cs:__imp_DeleteCriticalSection
0x1800234c5  mov     rcx, [rbx+0C0h]; pv
0x1800234cc  test    rcx, rcx
0x1800234cf  jz      short loc_1800234D8
0x1800234d1  call    cs:__imp_CoTaskMemFree
0x1800234d7  nop
0x1800234d8  mov     rcx, [rdi]
0x1800234db  test    rcx, rcx
0x1800234de  jz      short loc_1800234ED
0x1800234e0  mov     rax, [rcx]
0x1800234e3  mov     rax, [rax+10h]
0x1800234e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234ec  nop
0x1800234ed  mov     rcx, [rbx+98h]; pv
0x1800234f4  call    cs:__imp_CoTaskMemFree
0x1800234fa  mov     qword ptr [rbx+98h], 0
0x180023505  lea     rcx, [rbx+30h]; this
0x180023509  call    ??1CAudioSessionInstanceId@@QEAA@XZ; CAudioSessionInstanceId::~CAudioSessionInstanceId(void)
0x18002350e  mov     rcx, [rbx+20h]
0x180023512  test    rcx, rcx
0x180023515  jns     short loc_180023520
0x180023517  add     rcx, rcx
0x18002351a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18002351f  nop
0x180023520  add     rsp, 28h
0x180023524  pop     rdi
0x180023525  pop     rsi
0x180023526  pop     rbp
0x180023527  pop     rbx
0x180023528  retn
0x180023529  mov     rdx, [rdx]
0x18002352c  jmp     loc_180023416
0x180023531  lea     rsi, [rbx+0C8h]
0x180023538  mov     rcx, rsi; lpCriticalSection
0x18002353b  call    cs:__imp_EnterCriticalSection
0x180023541  mov     rdx, [rdi]
0x180023544  cmp     qword ptr [rdx+30h], 0
0x180023549  jnz     short loc_18002356A
0x18002354b  mov     rcx, rdi
0x18002354e  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180023553  test    rsi, rsi
0x180023556  jz      loc_1800233D4
0x18002355c  mov     rcx, rsi; lpCriticalSection
0x18002355f  call    cs:__imp_LeaveCriticalSection
0x180023565  jmp     loc_1800233D4
0x18002356a  cmp     dword ptr [rbx+0A8h], 1
0x180023571  jnz     short loc_180023589
0x180023573  mov     rcx, [rbx+90h]
0x18002357a  mov     rax, [rcx]
0x18002357d  mov     rax, [rax+0E8h]
0x180023584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023589  mov     r8b, 1; bool
0x18002358c  mov     rdx, [rdi]; struct CAudioStream *
0x18002358f  mov     rcx, [rbx+90h]; this
0x180023596  call    ?RemoveStream@CAudioSession@@QEAAJPEAVCAudioStream@@_N@Z; CAudioSession::RemoveStream(CAudioStream *,bool)
0x18002359b  jmp     short loc_18002354B
0x18002359d  mov     edx, 1; struct std::nothrow_t *
0x1800235a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800235a7  jmp     loc_180023485
```
