# CServiceModule::StartControllerWatcher(void)

- ea: `0x180026e80`
- end: `0x180026fa1`
- name: `?StartControllerWatcher@CServiceModule@@QEAA_NXZ`
- size: `289`
- prototype: `bool(CServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18000f5d0`

## callees

- `0x180018434`
- `0x18001a1d8`
- `0x18001bc20`
- `0x18001f394`
- `0x180025a34`
- `0x180026e80`
- `0x18002f284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026f0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026f0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026f54`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180026f54`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026ea8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026ea8`

## string_xrefs

- `0x180026f2c`: `drivers\tablet\platform\pen\penservice\tpcquery\controllerdetector.cpp`

## pseudocode

```c
bool __fastcall CServiceModule::StartControllerWatcher(CServiceModule *this)
{
  _QWORD *v2; // rax
  __int64 v3; // rcx
  ControllerDetector *v4; // rdx
  RTL_SRWLOCK *v5; // rsi
  void *v6; // rbx
  int v7; // eax
  int v8; // ebx
  PVOID Ptr; // rcx
  __int64 v10; // rcx
  ControllerDetector *v11; // rdx
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v15; // [rsp+30h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 20) )
    *((_QWORD *)this + 20) = CreateEventW(0, 1, 0, 0);
  v2 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
  {
    v3 = 0;
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
  }
  v4 = (ControllerDetector *)*((_QWORD *)this + 80);
  *((_QWORD *)this + 80) = v2;
  if ( v4 )
    std::default_delete<ControllerDetector>::operator()(v3, v4);
  v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 80);
  if ( v5 )
  {
    v6 = (void *)*((_QWORD *)this + 20);
    AcquireSRWLockExclusive(*((PSRWLOCK *)this + 80));
    v15 = v5;
    v5[2].Ptr = v6;
    v7 = ControllerDetector::RegisterForXusbConnectionEvents((ControllerDetector *)v5);
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( IsXUsbDevicePresent() )
      {
        Ptr = v5[2].Ptr;
        if ( Ptr )
          SetEvent(Ptr);
      }
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53,
        (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\tpcquery\\controllerdetector.cpp",
        (const char *)(unsigned int)v7,
        v13);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
    if ( v8 < 0 )
    {
      v11 = (ControllerDetector *)*((_QWORD *)this + 80);
      *((_QWORD *)this + 80) = 0;
      if ( v11 )
        std::default_delete<ControllerDetector>::operator()(v10, v11);
    }
  }
  return *((_QWORD *)this + 80) != 0;
}

```

## disassembly

```asm
0x180026e80  mov     [rsp+arg_8], rbx
0x180026e85  mov     [rsp+arg_10], rsi
0x180026e8a  push    rdi; int
0x180026e8b  sub     rsp, 20h
0x180026e8f  cmp     qword ptr [rcx+0A0h], 0
0x180026e97  mov     rdi, rcx
0x180026e9a  jnz     short loc_180026EB5
0x180026e9c  xor     r9d, r9d; lpName
0x180026e9f  xor     r8d, r8d; bInitialState
0x180026ea2  xor     ecx, ecx; lpEventAttributes
0x180026ea4  lea     edx, [r9+1]; bManualReset
0x180026ea8  call    cs:__imp_CreateEventW
0x180026eae  mov     [rdi+0A0h], rax
0x180026eb5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026ebc  mov     ecx, 18h; unsigned __int64
0x180026ec1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026ec6  test    rax, rax
0x180026ec9  jz      short loc_180026ED8
0x180026ecb  xor     ecx, ecx
0x180026ecd  mov     [rax], rcx
0x180026ed0  mov     [rax+8], rcx
0x180026ed4  mov     [rax+10h], rcx
0x180026ed8  mov     rdx, [rdi+280h]
0x180026edf  mov     [rdi+280h], rax
0x180026ee6  test    rdx, rdx
0x180026ee9  jz      short loc_180026EF0
0x180026eeb  call    ??R?$default_delete@VControllerDetector@@@std@@QEBAXPEAVControllerDetector@@@Z; std::default_delete<ControllerDetector>::operator()(ControllerDetector *)
0x180026ef0  mov     rsi, [rdi+280h]
0x180026ef7  test    rsi, rsi
0x180026efa  jz      loc_180026F86
0x180026f00  mov     rbx, [rdi+0A0h]
0x180026f07  mov     rcx, rsi; SRWLock
0x180026f0a  call    cs:__imp_AcquireSRWLockExclusive
0x180026f10  mov     rcx, rsi; this
0x180026f13  mov     [rsp+28h+arg_0], rsi
0x180026f18  mov     [rsi+10h], rbx
0x180026f1c  call    ?RegisterForXusbConnectionEvents@ControllerDetector@@AEAAJXZ; ControllerDetector::RegisterForXusbConnectionEvents(void)
0x180026f21  mov     ebx, eax
0x180026f23  test    eax, eax
0x180026f25  jns     short loc_180026F42
0x180026f27  mov     rcx, [rsp+28h]; this
0x180026f2c  lea     r8, aDriversTabletP; "drivers\\tablet\\platform\\pen\\penserv"...
0x180026f33  mov     r9d, eax; char *
0x180026f36  mov     edx, 53h ; 'S'; void *
0x180026f3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f40  jmp     short loc_180026F5C
0x180026f42  call    ?IsXUsbDevicePresent@@YA_NXZ; IsXUsbDevicePresent(void)
0x180026f47  test    al, al
0x180026f49  jz      short loc_180026F5A
0x180026f4b  mov     rcx, [rsi+10h]; hEvent
0x180026f4f  test    rcx, rcx
0x180026f52  jz      short loc_180026F5A
0x180026f54  call    cs:__imp_SetEvent
0x180026f5a  xor     ebx, ebx
0x180026f5c  lea     rcx, [rsp+28h+arg_0]
0x180026f61  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026f66  test    ebx, ebx
0x180026f68  jns     short loc_180026F86
0x180026f6a  mov     rdx, [rdi+280h]
0x180026f71  mov     qword ptr [rdi+280h], 0
0x180026f7c  test    rdx, rdx
0x180026f7f  jz      short loc_180026F86
0x180026f81  call    ??R?$default_delete@VControllerDetector@@@std@@QEBAXPEAVControllerDetector@@@Z; std::default_delete<ControllerDetector>::operator()(ControllerDetector *)
0x180026f86  cmp     qword ptr [rdi+280h], 0
0x180026f8e  mov     rbx, [rsp+28h+arg_8]
0x180026f93  mov     rsi, [rsp+28h+arg_10]
0x180026f98  setnz   al
0x180026f9b  add     rsp, 20h
0x180026f9f  pop     rdi
0x180026fa0  retn
```
