# CVADServer::~CVADServer(void)

- ea: `0x180023468`
- end: `0x1800236fc`
- name: `??1CVADServer@@UEAA@XZ`
- size: `660`
- prototype: `void __fastcall(CVADServer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800249a0`

## callees

- `0x18001534c`
- `0x180023468`
- `0x1800237e0`
- `0x180024918`
- `0x18002d430`
- `0x18002f42c`
- `0x1800424ec`
- `0x1800cdd70`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023602`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002360f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023602`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002360f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002349e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023559`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002368b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002349e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023559`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002368b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800234c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800236af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800234c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023581`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800236af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023644`

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
0x180023468  push    rbx
0x18002346a  push    rbp
0x18002346b  push    rsi
0x18002346c  push    rdi
0x18002346d  sub     rsp, 28h
0x180023471  mov     rbx, rcx
0x180023474  lea     rax, ??_7CVADServer@@6B@; const CVADServer::`vftable'
0x18002347b  mov     [rcx], rax
0x18002347e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6BIUnknown@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `IUnknown'}
0x180023485  mov     [rcx+8], rax
0x180023489  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IUnknown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x180023490  mov     [rcx+10h], rax
0x180023494  lea     rbp, [rcx+1B8h]
0x18002349b  mov     rcx, rbp; lpCriticalSection
0x18002349e  call    cs:__imp_EnterCriticalSection
0x1800234a4  mov     rdi, [rbx+1E8h]
0x1800234ab  mov     qword ptr [rbx+1E0h], 0
0x1800234b6  mov     qword ptr [rbx+1E8h], 0
0x1800234c1  test    rbp, rbp
0x1800234c4  jz      short loc_1800234CF
0x1800234c6  mov     rcx, rbp; lpCriticalSection
0x1800234c9  call    cs:__imp_LeaveCriticalSection
0x1800234cf  test    rdi, rdi
0x1800234d2  jz      short loc_1800234DC
0x1800234d4  mov     rcx, rdi; this
0x1800234d7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800234dc  mov     rdi, [rbx+88h]
0x1800234e3  test    rdi, rdi
0x1800234e6  jz      short loc_180023513
0x1800234e8  or      eax, 0FFFFFFFFh
0x1800234eb  lock xadd [rdi+18h], eax
0x1800234f0  cmp     eax, 1
0x1800234f3  jnz     short loc_180023504
0x1800234f5  mov     rax, [rdi]
0x1800234f8  mov     rcx, rdi
0x1800234fb  mov     rax, [rax+68h]
0x1800234ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023504  mov     rax, [rdi]
0x180023507  mov     rcx, rdi
0x18002350a  mov     rax, [rax+10h]
0x18002350e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023513  lea     rdi, [rbx+0B0h]
0x18002351a  cmp     qword ptr [rdi], 0
0x18002351e  jnz     loc_180023681
0x180023524  mov     rcx, [rbx+90h]
0x18002352b  test    rcx, rcx
0x18002352e  jz      short loc_180023547
0x180023530  mov     rax, [rcx]
0x180023533  mov     rax, [rax+10h]
0x180023537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002353c  mov     qword ptr [rbx+90h], 0
0x180023547  mov     qword ptr [rbx+80h], 0
0x180023552  lea     rcx, ?g_csVadList@@3Vcritical_section@wil@@A; lpCriticalSection
0x180023559  call    cs:__imp_EnterCriticalSection
0x18002355f  mov     rdx, cs:?g_VADServerList@@3V?$CAtlList@PEAVCVADServer@@V?$CElementTraits@PEAVCVADServer@@@ATL@@@ATL@@A; ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>> g_VADServerList
0x180023566  test    rdx, rdx
0x180023569  jz      short loc_18002357A
0x18002356b  cmp     [rdx+10h], rbx
0x18002356f  jnz     loc_180023679
0x180023575  call    ?RemoveAt@?$CAtlList@PEAVCVADServer@@V?$CElementTraits@PEAVCVADServer@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CVADServer *,ATL::CElementTraits<CVADServer *>>::RemoveAt(__POSITION *)
0x18002357a  lea     rcx, ?g_csVadList@@3Vcritical_section@wil@@A; lpCriticalSection
0x180023581  call    cs:__imp_LeaveCriticalSection
0x180023587  nop
0x180023588  mov     rcx, [rbx+228h]
0x18002358f  test    rcx, rcx
0x180023592  jz      short loc_1800235AC
0x180023594  mov     qword ptr [rbx+228h], 0
0x18002359f  mov     rax, [rcx]
0x1800235a2  mov     rax, [rax+10h]
0x1800235a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ab  nop
0x1800235ac  mov     rcx, [rbx+208h]
0x1800235b3  test    rcx, rcx
0x1800235b6  jz      short loc_1800235C5
0x1800235b8  mov     rax, [rcx]
0x1800235bb  mov     rax, [rax+10h]
0x1800235bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235c4  nop
0x1800235c5  mov     rcx, [rbx+1F8h]; void *
0x1800235cc  test    rcx, rcx
0x1800235cf  jnz     loc_1800236ED
0x1800235d5  mov     rcx, [rbx+1F0h]
0x1800235dc  test    rcx, rcx
0x1800235df  jz      short loc_1800235EE
0x1800235e1  mov     rax, [rcx]
0x1800235e4  mov     rax, [rax+10h]
0x1800235e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235ed  nop
0x1800235ee  mov     rcx, [rbx+1E8h]; this
0x1800235f5  test    rcx, rcx
0x1800235f8  jz      short loc_1800235FF
0x1800235fa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800235ff  mov     rcx, rbp; lpCriticalSection
0x180023602  call    cs:__imp_DeleteCriticalSection
0x180023608  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002360f  call    cs:__imp_DeleteCriticalSection
0x180023615  mov     rcx, [rbx+0C0h]; pv
0x18002361c  test    rcx, rcx
0x18002361f  jz      short loc_180023628
0x180023621  call    cs:__imp_CoTaskMemFree
0x180023627  nop
0x180023628  mov     rcx, [rdi]
0x18002362b  test    rcx, rcx
0x18002362e  jz      short loc_18002363D
0x180023630  mov     rax, [rcx]
0x180023633  mov     rax, [rax+10h]
0x180023637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002363c  nop
0x18002363d  mov     rcx, [rbx+98h]; pv
0x180023644  call    cs:__imp_CoTaskMemFree
0x18002364a  mov     qword ptr [rbx+98h], 0
0x180023655  lea     rcx, [rbx+30h]; this
0x180023659  call    ??1CAudioSessionInstanceId@@QEAA@XZ; CAudioSessionInstanceId::~CAudioSessionInstanceId(void)
0x18002365e  mov     rcx, [rbx+20h]
0x180023662  test    rcx, rcx
0x180023665  jns     short loc_180023670
0x180023667  add     rcx, rcx
0x18002366a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18002366f  nop
0x180023670  add     rsp, 28h
0x180023674  pop     rdi
0x180023675  pop     rsi
0x180023676  pop     rbp
0x180023677  pop     rbx
0x180023678  retn
0x180023679  mov     rdx, [rdx]
0x18002367c  jmp     loc_180023566
0x180023681  lea     rsi, [rbx+0C8h]
0x180023688  mov     rcx, rsi; lpCriticalSection
0x18002368b  call    cs:__imp_EnterCriticalSection
0x180023691  mov     rdx, [rdi]
0x180023694  cmp     qword ptr [rdx+30h], 0
0x180023699  jnz     short loc_1800236BA
0x18002369b  mov     rcx, rdi
0x18002369e  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x1800236a3  test    rsi, rsi
0x1800236a6  jz      loc_180023524
0x1800236ac  mov     rcx, rsi; lpCriticalSection
0x1800236af  call    cs:__imp_LeaveCriticalSection
0x1800236b5  jmp     loc_180023524
0x1800236ba  cmp     dword ptr [rbx+0A8h], 1
0x1800236c1  jnz     short loc_1800236D9
0x1800236c3  mov     rcx, [rbx+90h]
0x1800236ca  mov     rax, [rcx]
0x1800236cd  mov     rax, [rax+0E8h]
0x1800236d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236d9  mov     r8b, 1; bool
0x1800236dc  mov     rdx, [rdi]; struct CAudioStream *
0x1800236df  mov     rcx, [rbx+90h]; this
0x1800236e6  call    ?RemoveStream@CAudioSession@@QEAAJPEAVCAudioStream@@_N@Z; CAudioSession::RemoveStream(CAudioStream *,bool)
0x1800236eb  jmp     short loc_18002369B
0x1800236ed  mov     edx, 1; struct std::nothrow_t *
0x1800236f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800236f7  jmp     loc_1800235D5
```
