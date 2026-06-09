# OobeBootstrapTask::~OobeBootstrapTask(void)

- ea: `0x18004aa34`
- end: `0x18004aaec`
- name: `??1OobeBootstrapTask@@EEAA@XZ`
- size: `184`
- prototype: `void __fastcall(OobeBootstrapTask *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036290`

## callees

- `0x180002150`
- `0x18000ad20`
- `0x18001f5b8`
- `0x180035fec`
- `0x18004aa34`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004aabf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004aabf`

## string_xrefs

- `0x18004aa50`: `OobeBootstrapTask::~OobeBootstrapTask`

## pseudocode

```c
void __fastcall OobeBootstrapTask::~OobeBootstrapTask(OobeBootstrapTask *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &OobeBootstrapTask::`vftable';
  MBSettingUXLogging::Info("OobeBootstrapTask::~OobeBootstrapTask", 34, "OobeBootstrapTask::~OobeBootstrapTask");
  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 40LL))(v2, 0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
  }
  std::wstring::_Tidy_deallocate((char *)this + 128);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>((char *)this + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 16);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18004aa34  mov     [rsp+arg_0], rbx
0x18004aa39  mov     [rsp+arg_8], rsi
0x18004aa3e  push    rdi
0x18004aa3f  sub     rsp, 20h
0x18004aa43  mov     rbx, rcx
0x18004aa46  lea     rax, ??_7OobeBootstrapTask@@6B@; const OobeBootstrapTask::`vftable'
0x18004aa4d  mov     [rcx], rax
0x18004aa50  lea     rcx, aOobebootstrapt_1; "OobeBootstrapTask::~OobeBootstrapTask"
0x18004aa57  mov     r8, rcx; char *
0x18004aa5a  mov     edx, 22h ; '"'; unsigned int
0x18004aa5f  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004aa64  lea     rsi, [rbx+18h]
0x18004aa68  mov     rcx, [rsi]
0x18004aa6b  test    rcx, rcx
0x18004aa6e  jz      short loc_18004AA86
0x18004aa70  mov     rax, [rcx]
0x18004aa73  xor     edx, edx
0x18004aa75  mov     rax, [rax+28h]
0x18004aa79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa7e  mov     rcx, rsi
0x18004aa81  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004aa86  lea     rdi, [rbx+10h]
0x18004aa8a  mov     rcx, [rdi]
0x18004aa8d  test    rcx, rcx
0x18004aa90  jz      short loc_18004AAA6
0x18004aa92  mov     rax, [rcx]
0x18004aa95  mov     rax, [rax+20h]
0x18004aa99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa9e  mov     rcx, rdi
0x18004aaa1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004aaa6  lea     rcx, [rbx+80h]
0x18004aaad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004aab2  lea     rcx, [rbx+70h]
0x18004aab6  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18004aabb  lea     rcx, [rbx+20h]; lpCriticalSection
0x18004aabf  call    cs:__imp_DeleteCriticalSection
0x18004aac5  mov     rcx, rsi
0x18004aac8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004aacd  mov     rcx, rdi
0x18004aad0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004aad5  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18004aadc  mov     rbx, [rsp+28h+arg_0]
0x18004aae1  mov     rsi, [rsp+28h+arg_8]
0x18004aae6  add     rsp, 20h
0x18004aaea  pop     rdi
0x18004aaeb  retn
```
