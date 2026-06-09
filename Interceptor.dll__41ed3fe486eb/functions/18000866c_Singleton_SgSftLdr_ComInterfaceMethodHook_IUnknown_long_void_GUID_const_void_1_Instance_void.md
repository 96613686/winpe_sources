# Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)

- ea: `0x18000866c`
- end: `0x18000881c`
- name: `?Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ`
- size: `432`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800070b8`
- `0x180007520`
- `0x1800076b0`

## callees

- `0x18000866c`
- `0x18000ab0c`
- `0x180026a68`
- `0x180026b0c`
- `0x180026b78`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008769`
- `KERNEL32!InitializeCriticalSection` at `0x180008773`
- `KERNEL32!InitializeCriticalSection` at `0x1800087df`
- `KERNEL32!InitializeCriticalSection` at `0x180008769`
- `KERNEL32!InitializeCriticalSection` at `0x180008773`
- `KERNEL32!InitializeCriticalSection` at `0x1800087df`
- `KERNEL32!GetCurrentThreadId` at `0x1800086df`
- `KERNEL32!GetCurrentThreadId` at `0x1800086df`
- `KERNEL32!EnterCriticalSection` at `0x1800086c6`
- `KERNEL32!EnterCriticalSection` at `0x1800086c6`
- `KERNEL32!LeaveCriticalSection` at `0x18000879e`
- `KERNEL32!LeaveCriticalSection` at `0x18000879e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180008704`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180008742`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180008704`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180008742`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance()
{
  __int64 result; // rax
  int v1; // eax
  _QWORD *v2; // rax
  __int64 v3; // rsi
  _QWORD *v4; // r14
  _QWORD *v5; // rax

  if ( __TSS0__1__Instance___Singleton_V__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr____SAAEAV__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) )
  {
    Init_thread_header(&__TSS0__1__Instance___Singleton_V__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr____SAAEAV__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr__XZ_4HA);
    if ( __TSS0__1__Instance___Singleton_V__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr____SAAEAV__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr__XZ_4HA == -1 )
    {
      InitializeCriticalSection(&`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_cs);
      qword_180065C88 = 0;
      atexit(`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::`dynamic atexit destructor for 's_cs'');
      Init_thread_footer(&__TSS0__1__Instance___Singleton_V__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr____SAAEAV__ComInterfaceMethodHook_UIUnknown__P6AJPEAXAEBU_GUID__PEAPEAX_Z_00_SgSftLdr__XZ_4HA);
    }
  }
  result = `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_instance;
  if ( !`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_instance )
  {
    EnterCriticalSection(&`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_cs);
    v1 = qword_180065C88 + 1;
    LODWORD(qword_180065C88) = v1;
    if ( v1 == 1 )
    {
      HIDWORD(qword_180065C88) = GetCurrentThreadId();
      v1 = qword_180065C88;
    }
    try
    {
      if ( !`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_instance )
      {
        v2 = malloc(0x68u);
        v3 = (__int64)v2;
        if ( !v2 )
          std::_Xbad_alloc();
        *v2 = &TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::`vftable';
        v4 = v2 + 1;
        v2[1] = 0;
        v2[2] = 0;
        v5 = malloc(0x30u);
        if ( !v5 )
          std::_Xbad_alloc();
        *v5 = v5;
        v5[1] = v5;
        v5[2] = v5;
        *((_WORD *)v5 + 12) = 257;
        *v4 = v5;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
        InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 64));
        `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_instance = v3;
        v1 = qword_180065C88;
      }
      LODWORD(qword_180065C88) = v1 - 1;
      if ( v1 == 1 )
        qword_180065C88 = 0;
      LeaveCriticalSection(&`Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_cs);
      result = `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance'::`2'::s_instance;
    }
    catch ( ... )
    {
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000866c  mov     [rsp+arg_10], rsi
0x180008671  mov     [rsp+arg_18], rdi
0x180008676  push    r14
0x180008678  sub     rsp, 30h
0x18000867c  mov     ecx, cs:_tls_index
0x180008682  mov     rax, gs:58h
0x18000868b  mov     edx, 10h
0x180008690  mov     rax, [rax+rcx*8]
0x180008694  mov     eax, [rdx+rax]
0x180008697  cmp     cs:?$TSS0@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4HA, eax
0x18000869d  jg      loc_1800087BC
0x1800086a3  lea     rdi, ?s_cs@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4Vcritical_section@shared@softricity@@A; softricity::shared::critical_section `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_cs
0x1800086aa  mov     rax, cs:?s_instance@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4PEAV34@EA; SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1> * `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_instance
0x1800086b1  test    rax, rax
0x1800086b4  jnz     loc_1800087AB
0x1800086ba  mov     [rsp+38h+var_18], al
0x1800086be  mov     [rsp+38h+var_10], rdi
0x1800086c3  mov     rcx, rdi; lpCriticalSection
0x1800086c6  call    cs:__imp_EnterCriticalSection
0x1800086cc  mov     eax, dword ptr cs:qword_180065C88
0x1800086d2  inc     eax
0x1800086d4  mov     dword ptr cs:qword_180065C88, eax
0x1800086da  cmp     eax, 1
0x1800086dd  jnz     short loc_1800086F1
0x1800086df  call    cs:__imp_GetCurrentThreadId
0x1800086e5  mov     dword ptr cs:qword_180065C88+4, eax
0x1800086eb  mov     eax, dword ptr cs:qword_180065C88
0x1800086f1  cmp     cs:?s_instance@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4PEAV34@EA, 0; SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1> * `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_instance
0x1800086f9  jnz     loc_180008786
0x1800086ff  mov     ecx, 68h ; 'h'; Size
0x180008704  call    cs:__imp_malloc
0x18000870a  mov     rsi, rax
0x18000870d  test    rax, rax
0x180008710  jz      loc_18000880D
0x180008716  mov     [rsp+38h+arg_0], rsi
0x18000871b  lea     rax, ??_7?$TSgMap@PEA_KP6AJPEAXAEBU_GUID@@PEAPEAX@Z@@6B@; const TSgMap<unsigned __int64 *,long (*)(void *,_GUID const &,void * *)>::`vftable'
0x180008722  mov     [rsi], rax
0x180008725  lea     r14, [rsi+8]
0x180008729  mov     [rsp+38h+arg_8], r14
0x18000872e  mov     qword ptr [r14], 0
0x180008735  mov     qword ptr [r14+8], 0
0x18000873d  mov     ecx, 30h ; '0'; Size
0x180008742  call    cs:__imp_malloc
0x180008748  test    rax, rax
0x18000874b  jz      loc_180008816
0x180008751  mov     [rax], rax
0x180008754  mov     [rax+8], rax
0x180008758  mov     [rax+10h], rax
0x18000875c  mov     word ptr [rax+18h], 101h
0x180008762  mov     [r14], rax
0x180008765  lea     rcx, [rsi+18h]; lpCriticalSection
0x180008769  call    cs:__imp_InitializeCriticalSection
0x18000876f  lea     rcx, [rsi+40h]; lpCriticalSection
0x180008773  call    cs:__imp_InitializeCriticalSection
0x180008779  mov     cs:?s_instance@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4PEAV34@EA, rsi; SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1> * `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_instance
0x180008780  mov     eax, dword ptr cs:qword_180065C88
0x180008786  sub     eax, 1
0x180008789  mov     dword ptr cs:qword_180065C88, eax
0x18000878f  jnz     short loc_18000879B
0x180008791  mov     dword ptr cs:qword_180065C88+4, 0
0x18000879b  mov     rcx, rdi; lpCriticalSection
0x18000879e  call    cs:__imp_LeaveCriticalSection
0x1800087a4  mov     rax, cs:?s_instance@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4PEAV34@EA; SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1> * `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_instance
0x1800087ab  mov     rsi, [rsp+38h+arg_10]
0x1800087b0  mov     rdi, [rsp+38h+arg_18]
0x1800087b5  add     rsp, 30h
0x1800087b9  pop     r14
0x1800087bb  retn
0x1800087bc  lea     rcx, ?$TSS0@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4HA
0x1800087c3  call    _Init_thread_header
0x1800087c8  cmp     cs:?$TSS0@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4HA, 0FFFFFFFFh
0x1800087cf  jnz     loc_1800086A3
0x1800087d5  lea     rdi, ?s_cs@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4Vcritical_section@shared@softricity@@A; softricity::shared::critical_section `Singleton<SgSftLdr::ComInterfaceMethodHook<IUnknown,long (*)(void *,_GUID const &,void * *),1>>::Instance(void)'::`2'::s_cs
0x1800087dc  mov     rcx, rdi; lpCriticalSection
0x1800087df  call    cs:__imp_InitializeCriticalSection
0x1800087e5  mov     cs:qword_180065C88, 0
0x1800087f0  lea     rcx, ??__Fs_cs@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@YAXXZ; void (__cdecl *)()
0x1800087f7  call    atexit
0x1800087fc  lea     rcx, ?$TSS0@?1??Instance@?$Singleton@V?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@@@SAAEAV?$ComInterfaceMethodHook@UIUnknown@@P6AJPEAXAEBU_GUID@@PEAPEAX@Z$00@SgSftLdr@@XZ@4HA
0x180008803  call    _Init_thread_footer
0x180008808  jmp     loc_1800086AA
0x18000880d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180008813  jmp     short $+2
0x180008815  nop
0x180008816  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
