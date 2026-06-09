# Service::InitializePlatform(void)

- ea: `0x180003910`
- end: `0x180003bc4`
- name: `?InitializePlatform@Service@@AEAAJXZ`
- size: `692`
- prototype: `__int64 __fastcall(Service *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800032e8`

## callees

- `0x180003910`
- `0x180003e60`
- `0x180016458`
- `0x18001649c`
- `0x1800225d0`
- `0x18003aeb8`
- `0x18003dacc`
- `0x18003de10`
- `0x18006357c`
- `0x18006a010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000395a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000397b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000395a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000397b`
- `msvcp_win!_Mtx_lock` at `0x18000394b`
- `msvcp_win!_Mtx_lock` at `0x18000394b`
- `msvcp_win!_Mtx_unlock` at `0x180003a27`
- `msvcp_win!_Mtx_unlock` at `0x180003a27`
- `cdp!CDPGetHost` at `0x180003a4b`
- `cdp!CDPGetHost` at `0x180003a4b`
- `cdp!CDPGetLogger` at `0x18000399b`
- `cdp!CDPGetLogger` at `0x18000399b`
- `cdp!CDPSetServicePid` at `0x180003934`
- `cdp!CDPSetServicePid` at `0x180003934`
- `cdp!CDPInitializeForService` at `0x180003924`
- `cdp!CDPInitializeForService` at `0x180003924`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Service::InitializePlatform(Service *this)
{
  int v2; // edi
  __int64 v3; // rsi
  std::_Ref_count_base *v4; // rcx
  Service *v5; // rax
  __int64 *v6; // rdx
  _QWORD *v7; // rsi
  __int64 v8; // r14
  __int64 *v9; // rax
  std::_Ref_count_base *v10; // rcx
  Service *v11; // rax
  __int64 *v12; // rdx
  char *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  __int64 v19; // rax
  int v20; // edx
  int v21; // r8d
  __int64 v22; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-40h]
  std::_Ref_count_base *v24[2]; // [rsp+40h] [rbp-38h] BYREF
  Service *v25; // [rsp+88h] [rbp+10h] BYREF
  __int64 v26; // [rsp+90h] [rbp+18h] BYREF
  __int64 v27; // [rsp+98h] [rbp+20h] BYREF

  v2 = CDPInitializeForService(1);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v2 = CDPSetServicePid();
  if ( v2 < 0 )
    return (unsigned int)v2;
  if ( _Mtx_lock((_Mtx_t)&g_loggerMutex) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800C68EC == 0x7FFFFFFF )
  {
    dword_1800C68EC = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v22 = 0;
  v23 = &g_logger;
  v2 = CDPGetLogger(&v22);
  v3 = v22;
  if ( v22 )
  {
    v5 = (Service *)operator new(0x18u);
    v25 = v5;
    *(_OWORD *)v5 = 0;
    *((_DWORD *)v5 + 2) = 1;
    *((_DWORD *)v5 + 3) = 1;
    *(_QWORD *)v5 = &std::_Ref_count_resource<ICDPLogger *,cdp::detail::iunknown_deleter<ICDPLogger>>::`vftable';
    *((_QWORD *)v5 + 2) = v3;
    v6 = v23;
    *v23 = v3;
    v4 = (std::_Ref_count_base *)v6[1];
    v6[1] = (__int64)v5;
    if ( !v4 )
      goto LABEL_12;
  }
  else
  {
    *(_OWORD *)v24 = 0;
    std::shared_ptr<ICDPDeviceQuery>::operator=(v23, v24);
    v4 = v24[1];
    if ( !v24[1] )
      goto LABEL_12;
  }
  std::_Ref_count_base::_Decref(v4);
LABEL_12:
  _Mtx_unlock((_Mtx_t)&g_loggerMutex);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v22 = 0;
  v7 = (_QWORD *)((char *)this + 200);
  v23 = (__int64 *)((char *)this + 200);
  v2 = CDPGetHost(&v22);
  v8 = v22;
  if ( v22 )
  {
    v11 = (Service *)operator new(0x18u);
    v25 = v11;
    *(_OWORD *)v11 = 0;
    *((_DWORD *)v11 + 2) = 1;
    *((_DWORD *)v11 + 3) = 1;
    *(_QWORD *)v11 = &std::_Ref_count_resource<ICDPHost *,cdp::detail::iunknown_deleter<ICDPHost>>::`vftable';
    *((_QWORD *)v11 + 2) = v8;
    v12 = v23;
    *v23 = v8;
    v10 = (std::_Ref_count_base *)v12[1];
    v12[1] = (__int64)v11;
    if ( !v10 )
      goto LABEL_18;
    goto LABEL_17;
  }
  v9 = v23;
  *v23 = 0;
  v10 = (std::_Ref_count_base *)v9[1];
  v9[1] = 0;
  if ( v10 )
LABEL_17:
    std::_Ref_count_base::_Decref(v10);
LABEL_18:
  if ( v2 >= 0 )
  {
    v25 = this;
    cdp::MakeShared<Service::HostCallback,Service *>(v24, &v25);
    (*(void (__fastcall **)(_QWORD, std::_Ref_count_base *))(*(_QWORD *)*v7 + 40LL))(*v7, v24[0]);
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
    v2 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 24LL))(*v7);
    LODWORD(v25) = v2;
    if ( v2 >= 0 )
    {
      *((_BYTE *)this + 216) = 1;
      v13 = (char *)this + 248;
      std::shared_ptr<EventRegistration<IRadioStateEvent,Microsoft::WRL::InvokeModeOptions<2>>>::reset((char *)this + 248);
      try
      {
        v14 = std::make_shared<RadioEventWatcher,>(v24);
        std::shared_ptr<ICDPDeviceQuery>::operator=((char *)this + 232, v14);
        if ( v24[1] )
          std::_Ref_count_base::_Decref(v24[1]);
        v15 = *((_QWORD *)this + 29);
        v16 = (_QWORD *)Microsoft::WRL::Callback<IRadioStateEvent,long (bool)>(&v26);
        RadioEventWatcher::RegisterForRadioStateNotifications(v15, *v16, v13);
        v17 = v26;
        if ( v26 )
        {
          v26 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      catch ( ... )
      {
        LODWORD(v19) = GetCurrentThreadId();
        v27 = v19;
        LODWORD(v26) = 436;
        cdp::CatchAllToHR<char const (&)[14],int,unsigned __int64>(
          (unsigned int)&v25,
          v20,
          v21,
          (unsigned int)&v26,
          (__int64)&v27);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003910  push    rbx
0x180003912  push    rsi
0x180003913  push    rdi
0x180003914  push    r14
0x180003916  push    r15
0x180003918  sub     rsp, 50h
0x18000391c  mov     rbx, rcx
0x18000391f  mov     ecx, 1
0x180003924  call    cs:__imp_CDPInitializeForService
0x18000392a  mov     edi, eax
0x18000392c  test    eax, eax
0x18000392e  js      loc_180003BB6
0x180003934  call    cs:__imp_CDPSetServicePid
0x18000393a  mov     edi, eax
0x18000393c  test    eax, eax
0x18000393e  js      loc_180003BB6
0x180003944  lea     rcx, ?g_loggerMutex@@3Vmutex@std@@A; _Mtx_t
0x18000394b  call    cs:__imp__Mtx_lock
0x180003951  test    eax, eax
0x180003953  jz      short loc_180003961
0x180003955  mov     ecx, 5
0x18000395a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180003960  int     3; Trap to Debugger
0x180003961  mov     eax, cs:dword_1800C68EC
0x180003967  cmp     eax, 7FFFFFFFh
0x18000396c  jnz     short loc_180003982
0x18000396e  dec     eax
0x180003970  mov     cs:dword_1800C68EC, eax
0x180003976  mov     ecx, 6
0x18000397b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180003981  int     3; Trap to Debugger
0x180003982  xor     r15d, r15d
0x180003985  mov     [rsp+78h+var_48], r15
0x18000398a  lea     rax, ?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180003991  mov     [rsp+78h+var_40], rax
0x180003996  lea     rcx, [rsp+78h+var_48]
0x18000399b  call    cs:__imp_CDPGetLogger
0x1800039a1  mov     edi, eax
0x1800039a3  mov     rsi, [rsp+78h+var_48]
0x1800039a8  test    rsi, rsi
0x1800039ab  jnz     short loc_1800039D1
0x1800039ad  xorps   xmm0, xmm0
0x1800039b0  movdqu  xmmword ptr [rsp+78h+var_38], xmm0
0x1800039b6  lea     rdx, [rsp+78h+var_38]
0x1800039bb  mov     rcx, [rsp+78h+var_40]
0x1800039c0  call    ??4?$shared_ptr@VICDPDeviceQuery@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ICDPDeviceQuery>::operator=(std::shared_ptr<ICDPDeviceQuery> &&)
0x1800039c5  mov     rcx, [rsp+78h+var_38+8]
0x1800039ca  test    rcx, rcx
0x1800039cd  jz      short loc_180003A20
0x1800039cf  jmp     short loc_180003A1A
0x1800039d1  mov     ecx, 18h; Size
0x1800039d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039db  mov     [rsp+78h+arg_8], rax
0x1800039e3  xorps   xmm0, xmm0
0x1800039e6  movups  xmmword ptr [rax], xmm0
0x1800039e9  mov     dword ptr [rax+8], 1
0x1800039f0  mov     dword ptr [rax+0Ch], 1
0x1800039f7  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPLogger@@U?$iunknown_deleter@VICDPLogger@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPLogger *,cdp::detail::iunknown_deleter<ICDPLogger>>::`vftable'
0x1800039fe  mov     [rax], rcx
0x180003a01  mov     [rax+10h], rsi
0x180003a05  mov     rdx, [rsp+78h+var_40]
0x180003a0a  mov     [rdx], rsi
0x180003a0d  mov     rcx, [rdx+8]; this
0x180003a11  mov     [rdx+8], rax
0x180003a15  test    rcx, rcx
0x180003a18  jz      short loc_180003A20
0x180003a1a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003a1f  nop
0x180003a20  lea     rcx, ?g_loggerMutex@@3Vmutex@std@@A; _Mtx_t
0x180003a27  call    cs:__imp__Mtx_unlock
0x180003a2d  test    edi, edi
0x180003a2f  js      loc_180003BB6
0x180003a35  mov     [rsp+78h+var_48], r15
0x180003a3a  lea     rsi, [rbx+0C8h]
0x180003a41  mov     [rsp+78h+var_40], rsi
0x180003a46  lea     rcx, [rsp+78h+var_48]
0x180003a4b  call    cs:__imp_CDPGetHost
0x180003a51  mov     edi, eax
0x180003a53  mov     r14, [rsp+78h+var_48]
0x180003a58  test    r14, r14
0x180003a5b  jnz     short loc_180003A74
0x180003a5d  mov     rax, [rsp+78h+var_40]
0x180003a62  mov     [rax], r15
0x180003a65  mov     rcx, [rax+8]
0x180003a69  mov     [rax+8], r15
0x180003a6d  test    rcx, rcx
0x180003a70  jnz     short loc_180003ABD
0x180003a72  jmp     short loc_180003AC3
0x180003a74  mov     ecx, 18h; Size
0x180003a79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a7e  mov     [rsp+78h+arg_8], rax
0x180003a86  xorps   xmm0, xmm0
0x180003a89  movups  xmmword ptr [rax], xmm0
0x180003a8c  mov     dword ptr [rax+8], 1
0x180003a93  mov     dword ptr [rax+0Ch], 1
0x180003a9a  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPHost@@U?$iunknown_deleter@VICDPHost@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPHost *,cdp::detail::iunknown_deleter<ICDPHost>>::`vftable'
0x180003aa1  mov     [rax], rcx
0x180003aa4  mov     [rax+10h], r14
0x180003aa8  mov     rdx, [rsp+78h+var_40]
0x180003aad  mov     [rdx], r14
0x180003ab0  mov     rcx, [rdx+8]; this
0x180003ab4  mov     [rdx+8], rax
0x180003ab8  test    rcx, rcx
0x180003abb  jz      short loc_180003AC3
0x180003abd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003ac2  nop
0x180003ac3  test    edi, edi
0x180003ac5  js      loc_180003BB6
0x180003acb  mov     [rsp+78h+arg_8], rbx
0x180003ad3  lea     rdx, [rsp+78h+arg_8]
0x180003adb  lea     rcx, [rsp+78h+var_38]
0x180003ae0  call    ??$MakeShared@VHostCallback@Service@@PEAV2@@cdp@@YA?AV?$shared_ptr@VHostCallback@Service@@@std@@$$QEAPEAVService@@@Z; cdp::MakeShared<Service::HostCallback,Service *>(Service * &&)
0x180003ae5  nop
0x180003ae6  mov     rcx, [rsi]
0x180003ae9  mov     rax, [rcx]
0x180003aec  mov     rdx, [rsp+78h+var_38]
0x180003af1  mov     rax, [rax+28h]
0x180003af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afa  nop
0x180003afb  mov     rcx, [rsp+78h+var_38+8]; this
0x180003b00  test    rcx, rcx
0x180003b03  jz      short loc_180003B0A
0x180003b05  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003b0a  mov     rcx, [rsi]
0x180003b0d  mov     rax, [rcx]
0x180003b10  mov     rax, [rax+18h]
0x180003b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b19  mov     edi, eax
0x180003b1b  mov     dword ptr [rsp+78h+arg_8], eax
0x180003b22  test    eax, eax
0x180003b24  js      loc_180003BB6
0x180003b2a  mov     byte ptr [rbx+0D8h], 1
0x180003b31  lea     rsi, [rbx+0F8h]
0x180003b38  mov     rcx, rsi
0x180003b3b  call    ?reset@?$shared_ptr@V?$EventRegistration@UIRadioStateEvent@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@@@std@@QEAAXXZ; std::shared_ptr<EventRegistration<IRadioStateEvent,Microsoft::WRL::InvokeModeOptions<2>>>::reset(void)
0x180003b40  lea     rcx, [rsp+78h+var_38]
0x180003b45  call    ??$make_shared@VRadioEventWatcher@@$$V@std@@YA?AV?$shared_ptr@VRadioEventWatcher@@@0@XZ; std::make_shared<RadioEventWatcher,>(void)
0x180003b4a  mov     rdx, rax
0x180003b4d  lea     rcx, [rbx+0E8h]
0x180003b54  call    ??4?$shared_ptr@VICDPDeviceQuery@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ICDPDeviceQuery>::operator=(std::shared_ptr<ICDPDeviceQuery> &&)
0x180003b59  mov     rcx, [rsp+78h+var_38+8]; this
0x180003b5e  test    rcx, rcx
0x180003b61  jz      short loc_180003B68
0x180003b63  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003b68  mov     rbx, [rbx+0E8h]
0x180003b6f  lea     rcx, [rsp+78h+arg_10]
0x180003b77  call    ??$Callback@UIRadioStateEvent@@$$A6AJ_N@Z@WRL@Microsoft@@YA?AV?$ComPtr@UIRadioStateEvent@@@01@P6AJ_N@Z@Z; Microsoft::WRL::Callback<IRadioStateEvent,long (bool)>(long (*)(bool))
0x180003b7c  mov     r8, rsi
0x180003b7f  mov     rdx, [rax]
0x180003b82  mov     rcx, rbx
0x180003b85  call    ?RegisterForRadioStateNotifications@RadioEventWatcher@@QEAAJPEAUIRadioStateEvent@@AEAV?$shared_ptr@V?$EventRegistration@UIRadioStateEvent@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@@@std@@@Z; RadioEventWatcher::RegisterForRadioStateNotifications(IRadioStateEvent *,std::shared_ptr<EventRegistration<IRadioStateEvent,Microsoft::WRL::InvokeModeOptions<2>>> &)
0x180003b8a  nop
0x180003b8b  mov     rcx, [rsp+78h+arg_10]
0x180003b93  test    rcx, rcx
0x180003b96  jz      short loc_180003BAD
0x180003b98  mov     [rsp+78h+arg_10], r15
0x180003ba0  mov     rax, [rcx]
0x180003ba3  mov     rax, [rax+10h]
0x180003ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bac  nop
0x180003bad  jmp     short loc_180003BB6
0x180003baf  mov     edi, dword ptr [rsp+78h+arg_8]
0x180003bb6  mov     eax, edi
0x180003bb8  add     rsp, 50h
0x180003bbc  pop     r15
0x180003bbe  pop     r14
0x180003bc0  pop     rdi
0x180003bc1  pop     rsi
0x180003bc2  pop     rbx
0x180003bc3  retn
```
