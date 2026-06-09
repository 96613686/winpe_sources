# WPRCControlLogging

- ea: `0x180072450`
- end: `0x1800725e8`
- name: `WPRCControlLogging`
- size: `408`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009b40`
- `0x18004b39c`
- `0x180071be4`
- `0x180071cfc`
- `0x1800723e4`
- `0x180072450`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180072477`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180072477`

## string_xrefs

- `0x18007249e`: `wevtapi.dll`
- `0x1800724b1`: `EvtOpenChannelConfig`
- `0x18007258e`: `EvtSaveChannelConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WPRCControlLogging(int a1)
{
  HINSTANCE v2; // rdx
  const unsigned __int16 *v3; // r8
  bool v4; // r9
  int Error; // ebx
  __int64 (__fastcall *v6)(_QWORD, const wchar_t *, _QWORD); // rax
  enum _EVT_CHANNEL_CONFIG_PROPERTY_ID v7; // edx
  unsigned int (__fastcall *v8)(__int64, _QWORD); // rax
  _EVT_VARIANT v10; // [rsp+20h] [rbp-59h] BYREF
  __int64 v11; // [rsp+30h] [rbp-49h]
  char v12; // [rsp+38h] [rbp-41h]
  _QWORD v13[3]; // [rsp+40h] [rbp-39h] BYREF
  char v14; // [rsp+58h] [rbp-21h]
  _QWORD v15[3]; // [rsp+60h] [rbp-19h] BYREF
  char v16; // [rsp+78h] [rbp-1h]
  _QWORD v17[3]; // [rsp+80h] [rbp+7h] BYREF
  char v18; // [rsp+98h] [rbp+1Fh]
  __int64 v19; // [rsp+A0h] [rbp+27h]
  HMODULE phModule; // [rsp+E8h] [rbp+6Fh] BYREF

  phModule = 0;
  if ( GetModuleHandleExW(6u, (LPCWSTR)WPRCControlLogging, &phModule)
    || (Error = ATL::AtlHresultFromLastError(), Error >= 0) )
  {
    LOBYTE(v3) = 1;
    Error = Performance::EventLogConfiguration::ControlEventProviderRegistration(phModule, v2, v3, v4);
  }
  v13[0] = 0;
  v13[1] = L"wevtapi.dll";
  v15[0] = v13;
  v15[1] = "EvtOpenChannelConfig";
  v17[0] = v13;
  v17[1] = "EvtClose";
  v13[2] = 0;
  v14 = 0;
  v15[2] = 0;
  v16 = 0;
  v17[2] = 0;
  v18 = 0;
  v19 = 0;
  if ( Error >= 0 )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v15)
      && Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v17) )
    {
      v6 = (__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v15);
      v19 = v6(0, L"Microsoft-Windows-Performance-Recorder-Control/Operational", 0);
      if ( v19 || (Error = ATL::AtlHresultFromLastError(), Error >= 0) )
      {
        v10.Count = 0;
        v10.Type = 13;
        v10.Int64Val = a1 != 0;
        Error = Performance::EventLogConfiguration::CEventLogChannelConfiguration::SetProperty(
                  (Performance::EventLogConfiguration::CEventLogChannelConfiguration *)v13,
                  v7,
                  &v10);
        if ( Error >= 0 )
        {
          if ( v19
            && (v11 = 0,
                v10.Int64Val = (INT64)v13,
                v12 = 0,
                *(_QWORD *)&v10.Count = "EvtSaveChannelConfig",
                Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(&v10)) )
          {
            v8 = (unsigned int (__fastcall *)(__int64, _QWORD))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(&v10);
            if ( v8(v19, 0) )
              Error = 0;
            else
              Error = ATL::AtlHresultFromLastError();
          }
          else
          {
            Error = -2147418113;
          }
        }
      }
    }
    else
    {
      Error = -2147024894;
    }
  }
  Performance::EventLogConfiguration::CEventLogChannelConfiguration::~CEventLogChannelConfiguration((Performance::EventLogConfiguration::CEventLogChannelConfiguration *)v13);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180072450  push    rbp
0x180072452  push    rbx
0x180072453  push    rsi
0x180072454  push    rdi
0x180072455  lea     rbp, [rsp-3Fh]
0x18007245a  sub     rsp, 0B8h
0x180072461  xor     esi, esi
0x180072463  lea     r8, [rbp+57h+phModule]; phModule
0x180072467  mov     edi, ecx
0x180072469  mov     [rbp+57h+phModule], rsi
0x18007246d  lea     rdx, WPRCControlLogging; lpModuleName
0x180072474  lea     ecx, [rsi+6]; dwFlags
0x180072477  call    cs:__imp_GetModuleHandleExW
0x18007247d  test    eax, eax
0x18007247f  jnz     short loc_18007248C
0x180072481  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180072486  mov     ebx, eax
0x180072488  test    eax, eax
0x18007248a  js      short loc_18007249A
0x18007248c  mov     rcx, [rbp+57h+phModule]; hModule
0x180072490  mov     r8b, 1; unsigned __int16 *
0x180072493  call    ?ControlEventProviderRegistration@EventLogConfiguration@Performance@@YAJPEAUHINSTANCE__@@PEBG_N@Z; Performance::EventLogConfiguration::ControlEventProviderRegistration(HINSTANCE__ *,ushort const *,bool)
0x180072498  mov     ebx, eax
0x18007249a  mov     [rbp+57h+var_90], rsi
0x18007249e  lea     rax, aWevtapiDll; "wevtapi.dll"
0x1800724a5  mov     [rbp+57h+var_88], rax
0x1800724a9  lea     rax, [rbp+57h+var_90]
0x1800724ad  mov     [rbp+57h+var_70], rax
0x1800724b1  lea     rax, aEvtopenchannel; "EvtOpenChannelConfig"
0x1800724b8  mov     [rbp+57h+var_68], rax
0x1800724bc  lea     rax, [rbp+57h+var_90]
0x1800724c0  mov     [rbp+57h+var_50], rax
0x1800724c4  lea     rax, aEvtclose; "EvtClose"
0x1800724cb  mov     [rbp+57h+var_48], rax
0x1800724cf  mov     [rbp+57h+var_80], rsi
0x1800724d3  mov     [rbp+57h+var_78], sil
0x1800724d7  mov     [rbp+57h+var_60], rsi
0x1800724db  mov     [rbp+57h+var_58], sil
0x1800724df  mov     [rbp+57h+var_40], rsi
0x1800724e3  mov     [rbp+57h+var_38], sil
0x1800724e7  mov     [rbp+57h+var_30], rsi
0x1800724eb  test    ebx, ebx
0x1800724ed  js      loc_1800725D1
0x1800724f3  lea     rcx, [rbp+57h+var_70]
0x1800724f7  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800724fc  test    rax, rax
0x1800724ff  jz      loc_1800725CC
0x180072505  lea     rcx, [rbp+57h+var_50]
0x180072509  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18007250e  test    rax, rax
0x180072511  jz      loc_1800725CC
0x180072517  lea     rcx, [rbp+57h+var_70]
0x18007251b  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x180072520  xor     r8d, r8d
0x180072523  lea     rdx, aMicrosoftWindo_10; "Microsoft-Windows-Performance-Recorder-"...
0x18007252a  xor     ecx, ecx
0x18007252c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072531  mov     [rbp+57h+var_30], rax
0x180072535  test    rax, rax
0x180072538  jnz     short loc_180072549
0x18007253a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007253f  mov     ebx, eax
0x180072541  test    eax, eax
0x180072543  js      loc_1800725D1
0x180072549  mov     eax, esi
0x18007254b  mov     qword ptr [rbp+57h+var_B0+4], rsi
0x18007254f  test    edi, edi
0x180072551  mov     [rbp+57h+var_B0.Type], 0Dh
0x180072558  lea     r8, [rbp+57h+var_B0]; struct _EVT_VARIANT *
0x18007255c  setnz   al
0x18007255f  lea     rcx, [rbp+57h+var_90]; this
0x180072563  mov     dword ptr [rbp+57h+var_B0], eax
0x180072566  call    ?SetProperty@CEventLogChannelConfiguration@EventLogConfiguration@Performance@@AEAAJW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@PEAU_EVT_VARIANT@@@Z; Performance::EventLogConfiguration::CEventLogChannelConfiguration::SetProperty(_EVT_CHANNEL_CONFIG_PROPERTY_ID,_EVT_VARIANT *)
0x18007256b  mov     ebx, eax
0x18007256d  test    eax, eax
0x18007256f  js      short loc_1800725D1
0x180072571  cmp     [rbp+57h+var_30], rsi
0x180072575  jnz     short loc_18007257E
0x180072577  mov     ebx, 8000FFFFh
0x18007257c  jmp     short loc_1800725D1
0x18007257e  lea     rax, [rbp+57h+var_90]
0x180072582  mov     [rbp+57h+var_A0], rsi
0x180072586  mov     qword ptr [rbp+57h+var_B0], rax
0x18007258a  lea     rcx, [rbp+57h+var_B0]
0x18007258e  lea     rax, aEvtsavechannel; "EvtSaveChannelConfig"
0x180072595  mov     [rbp+57h+var_98], sil
0x180072599  mov     [rbp-51h], rax
0x18007259d  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800725a2  test    rax, rax
0x1800725a5  jz      short loc_180072577
0x1800725a7  lea     rcx, [rbp+57h+var_B0]
0x1800725ab  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800725b0  mov     rcx, [rbp+57h+var_30]
0x1800725b4  xor     edx, edx
0x1800725b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725bb  test    eax, eax
0x1800725bd  jnz     short loc_1800725C8
0x1800725bf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800725c4  mov     ebx, eax
0x1800725c6  jmp     short loc_1800725D1
0x1800725c8  mov     ebx, esi
0x1800725ca  jmp     short loc_1800725D1
0x1800725cc  mov     ebx, 80070002h
0x1800725d1  lea     rcx, [rbp+57h+var_90]; this
0x1800725d5  call    ??1CEventLogChannelConfiguration@EventLogConfiguration@Performance@@QEAA@XZ; Performance::EventLogConfiguration::CEventLogChannelConfiguration::~CEventLogChannelConfiguration(void)
0x1800725da  mov     eax, ebx
0x1800725dc  add     rsp, 0B8h
0x1800725e3  pop     rdi
0x1800725e4  pop     rsi
0x1800725e5  pop     rbx
0x1800725e6  pop     rbp
0x1800725e7  retn
```
