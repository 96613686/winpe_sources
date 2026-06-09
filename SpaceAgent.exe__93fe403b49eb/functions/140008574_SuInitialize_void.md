# SuInitialize(void)

- ea: `0x140008574`
- end: `0x140008791`
- name: `?SuInitialize@@YAHXZ`
- size: `541`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140002ce8`
- `0x140002f8c`

## callees

- `0x140003518`
- `0x14000353c`
- `0x140004530`
- `0x1400045c4`
- `0x140007db0`
- `0x140008574`
- `0x140009924`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140008736`
- `KERNEL32!GetLastError` at `0x140008736`
- `KERNEL32!CloseThreadpool` at `0x140008720`
- `KERNEL32!CloseThreadpool` at `0x140008720`
- `KERNEL32!CreateThreadpool` at `0x14000861b`
- `KERNEL32!CreateThreadpool` at `0x14000861b`
- `KERNEL32!GetModuleHandleExW` at `0x1400085eb`
- `KERNEL32!GetModuleHandleExW` at `0x1400085eb`
- `KERNEL32!GetModuleFileNameW` at `0x140008613`
- `KERNEL32!GetModuleFileNameW` at `0x140008613`
- `KERNEL32!CreateFileW` at `0x1400086f5`
- `KERNEL32!CreateFileW` at `0x1400086f5`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x140008653`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x140008653`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x140008641`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x140008641`

## string_xrefs

- `0x14000862d`: `CreateThreadpool`
- `0x140008666`: `SetThreadpoolThreadMinimum`
- `0x14000870f`: `CreateFile`

## pseudocode

```c
__int64 __fastcall SuInitialize(void **a1)
{
  __int64 v1; // rdx
  unsigned int v2; // ebx
  BOOL ModuleHandle; // ebx
  struct _TP_POOL *Threadpool; // rax
  const char *v5; // rsi
  char LastError; // al
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  HMODULE *p_hModule; // [rsp+40h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-20h] BYREF
  char v13; // [rsp+50h] [rbp-18h]
  HMODULE hModule; // [rsp+70h] [rbp+8h] BYREF

  hModule = 0;
  SiAcquireSpinLock(a1);
  if ( ReferenceCount )
  {
    v2 = 1;
    ++ReferenceCount;
  }
  else
  {
    McGenEventRegister_EventRegister(SpaceApiProvider, v1, SpaceApiProvider_Context, SpaceApiProvider_Context);
    phModule = 0;
    p_hModule = &hModule;
    v13 = 1;
    ModuleHandle = GetModuleHandleExW(4u, (LPCWSTR)&Spaceport, &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&p_hModule);
    if ( ModuleHandle )
      GetModuleFileNameW(hModule, &ModuleName, 0x104u);
    Threadpool = CreateThreadpool(0);
    ::Threadpool = Threadpool;
    if ( Threadpool )
    {
      SetThreadpoolThreadMaximum(Threadpool, 0x80u);
      v2 = SetThreadpoolThreadMinimum(::Threadpool, 1u);
      Threadpool = ::Threadpool;
      if ( v2 )
      {
        ThreadpoolEnv.Version = 3;
        *(_OWORD *)&ThreadpoolEnv.RaceDll = 0;
        ThreadpoolEnv.CleanupGroup = 0;
        ThreadpoolEnv.CleanupGroupCancelCallback = 0;
        ThreadpoolEnv.FinalizationCallback = 0;
        ThreadpoolEnv.u.Flags = 0;
        ThreadpoolEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
        ThreadpoolEnv.Size = 72;
        ThreadpoolEnv.Pool = ::Threadpool;
        Spaceport = CreateFileW(L"\\\\.\\Spaceport", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
        if ( Spaceport != (HANDLE)-1LL )
        {
          ++ReferenceCount;
          goto LABEL_17;
        }
        Threadpool = ::Threadpool;
        v5 = "CreateFile";
      }
      else
      {
        v5 = "SetThreadpoolThreadMinimum";
      }
    }
    else
    {
      v5 = "CreateThreadpool";
    }
    v2 = 0;
    if ( Threadpool )
    {
      CloseThreadpool(Threadpool);
      ::Threadpool = 0;
    }
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
    {
      LastError = GetLastError();
      McTemplateK0zssq_EventWriteTransfer(
        v7,
        (unsigned int)InitializeApiFailed,
        v8,
        v9,
        (__int64)"SuInitialize",
        (__int64)v5,
        LastError);
    }
    McGenEventUnregister_EventUnregister(SpaceApiProvider_Context);
  }
LABEL_17:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return v2;
}

```

## disassembly

```asm
0x140008574  mov     [rsp+arg_8], rbx
0x140008579  push    rsi
0x14000857a  sub     rsp, 60h
0x14000857e  mov     [rsp+68h+hModule], 0
0x140008587  call    ?SiAcquireSpinLock@@YAXPEAPEAX@Z; SiAcquireSpinLock(void * *)
0x14000858c  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x140008592  test    eax, eax
0x140008594  jz      short loc_1400085A8
0x140008596  inc     eax
0x140008598  mov     ebx, 1
0x14000859d  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x1400085a3  jmp     loc_140008771
0x1400085a8  lea     r9, SpaceApiProvider_Context
0x1400085af  lea     r8, SpaceApiProvider_Context
0x1400085b6  lea     rcx, SpaceApiProvider
0x1400085bd  call    McGenEventRegister_EventRegister
0x1400085c2  lea     rax, [rsp+68h+hModule]
0x1400085c7  mov     [rsp+68h+phModule], 0
0x1400085d0  lea     r8, [rsp+68h+phModule]; phModule
0x1400085d5  mov     [rsp+68h+var_28], rax
0x1400085da  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x1400085e1  mov     [rsp+68h+var_18], 1
0x1400085e6  mov     ecx, 4; dwFlags
0x1400085eb  call    cs:__imp_GetModuleHandleExW
0x1400085f1  lea     rcx, [rsp+68h+var_28]
0x1400085f6  mov     ebx, eax
0x1400085f8  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x1400085fd  test    ebx, ebx
0x1400085ff  jz      short loc_140008619
0x140008601  mov     rcx, [rsp+68h+hModule]; hModule
0x140008606  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x14000860d  mov     r8d, 104h; nSize
0x140008613  call    cs:__imp_GetModuleFileNameW
0x140008619  xor     ecx, ecx; reserved
0x14000861b  call    cs:__imp_CreateThreadpool
0x140008621  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x140008628  test    rax, rax
0x14000862b  jnz     short loc_140008639
0x14000862d  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x140008634  jmp     loc_140008716
0x140008639  mov     edx, 80h; cthrdMost
0x14000863e  mov     rcx, rax; ptpp
0x140008641  call    cs:__imp_SetThreadpoolThreadMaximum
0x140008647  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x14000864e  mov     edx, 1; cthrdMic
0x140008653  call    cs:__imp_SetThreadpoolThreadMinimum
0x140008659  mov     ebx, eax
0x14000865b  test    eax, eax
0x14000865d  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x140008664  jnz     short loc_140008672
0x140008666  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x14000866d  jmp     loc_140008716
0x140008672  mov     r8d, 3; dwShareMode
0x140008678  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x140008681  xorps   xmm0, xmm0
0x140008684  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x14000868c  xor     r9d, r9d; lpSecurityAttributes
0x14000868f  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x140008696  mov     edx, 0C0000000h; dwDesiredAccess
0x14000869b  movdqa  xmmword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086a3  lea     rcx, FileName; "\\\\.\\Spaceport"
0x1400086aa  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400086af  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086ba  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086c5  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086d0  mov     dword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086da  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086e4  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086ee  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1400086f5  call    cs:__imp_CreateFileW
0x1400086fb  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x140008702  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140008706  jnz     short loc_14000876B
0x140008708  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x14000870f  lea     rsi, aCreatefile; "CreateFile"
0x140008716  xor     ebx, ebx
0x140008718  test    rax, rax
0x14000871b  jz      short loc_14000872D
0x14000871d  mov     rcx, rax; ptpp
0x140008720  call    cs:__imp_CloseThreadpool
0x140008726  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x14000872d  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x140008734  jz      short loc_14000875D
0x140008736  call    cs:__imp_GetLastError
0x14000873c  mov     dword ptr [rsp+68h+hTemplateFile], eax
0x140008740  lea     rdx, InitializeApiFailed
0x140008747  lea     rax, aSuinitialize; "SuInitialize"
0x14000874e  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi
0x140008753  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x140008758  call    McTemplateK0zssq_EventWriteTransfer
0x14000875d  lea     rcx, SpaceApiProvider_Context
0x140008764  call    McGenEventUnregister_EventUnregister
0x140008769  jmp     short loc_140008771
0x14000876b  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x140008771  xor     ecx, ecx
0x140008773  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x14000877a  lea     rcx, [rsp+68h+hModule]
0x14000877f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140008784  mov     eax, ebx
0x140008786  mov     rbx, [rsp+68h+arg_8]
0x14000878b  add     rsp, 60h
0x14000878f  pop     rsi
0x140008790  retn
```
