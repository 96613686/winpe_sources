# DllCanUnloadNow

- ea: `0x180034290`
- end: `0x180034340`
- name: `DllCanUnloadNow`
- size: `176`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180034290`
- `0x180034348`
- `0x180034458`
- `0x18008c950`
- `0x180123010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18003429d`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18003429d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800342ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034338`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034338`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180034304`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180034304`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180034311`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180034311`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax
  Microsoft::WRL::Details *v1; // rax
  struct Microsoft::WRL::Details::ModuleBase *v2; // rdx
  bool v3; // r9
  HRESULT v4; // ebx
  _unnamed_type_AudioCleanupTaskThreadPool_ *v5; // rcx

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
  {
    v1 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    if ( !Microsoft::WRL::Details::TerminateMap(v1, v2, 0, v3)
      || (*(unsigned int (__fastcall **)(void *))(_AtlModule + 24LL))(&_AtlModule) )
    {
      return 1;
    }
    v4 = 0;
    EnterCriticalSection(&_AudioClientThreadpoolLock);
    v5 = ptpcg;
    if ( ptpcg )
    {
      CloseThreadpoolCleanupGroupMembers(ptpcg, 1, 0);
      CloseThreadpoolCleanupGroup(ptpcg);
      ptpcg = 0;
    }
    if ( GeneralAudioThreadPool )
      GeneralAudioThreadPool = 0;
    _unnamed_type_AudioCleanupTaskThreadPool_::Cleanup(v5);
    LeaveCriticalSection(&_AudioClientThreadpoolLock);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180034290  push    rbx
0x180034292  sub     rsp, 20h
0x180034296  lea     rcx, gPFactory; pPSFactoryBuffer
0x18003429d  call    cs:__imp_NdrDllCanUnloadNow
0x1800342a3  test    eax, eax
0x1800342a5  jnz     short loc_1800342C2
0x1800342a7  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800342ac  xor     r8d, r8d; unsigned __int16 *
0x1800342af  mov     rcx, rax; this
0x1800342b2  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x1800342b7  test    al, al
0x1800342b9  jnz     short loc_1800342C8
0x1800342bb  mov     ebx, 1
0x1800342c0  mov     eax, ebx
0x1800342c2  add     rsp, 20h
0x1800342c6  pop     rbx
0x1800342c7  retn
0x1800342c8  mov     rax, cs:?_AtlModule@@3VCVirtualAudioDeviceModule@@A; CVirtualAudioDeviceModule _AtlModule
0x1800342cf  lea     rcx, ?_AtlModule@@3VCVirtualAudioDeviceModule@@A; CVirtualAudioDeviceModule _AtlModule
0x1800342d6  mov     rax, [rax+18h]
0x1800342da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342df  test    eax, eax
0x1800342e1  jnz     short loc_1800342BB
0x1800342e3  lea     rcx, ?_AudioClientThreadpoolLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x1800342ea  xor     ebx, ebx
0x1800342ec  call    cs:__imp_EnterCriticalSection
0x1800342f2  mov     rcx, cs:ptpcg; ptpcg
0x1800342f9  test    rcx, rcx
0x1800342fc  jz      short loc_18003431E
0x1800342fe  xor     r8d, r8d; pvCleanupContext
0x180034301  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x180034304  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18003430a  mov     rcx, cs:ptpcg; ptpcg
0x180034311  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180034317  mov     cs:ptpcg, rbx
0x18003431e  cmp     cs:?GeneralAudioThreadPool@@3U_unnamed_type_GeneralAudioThreadPool_@@A, bl; _unnamed_type_GeneralAudioThreadPool_ GeneralAudioThreadPool
0x180034324  jz      short loc_18003432C
0x180034326  mov     cs:?GeneralAudioThreadPool@@3U_unnamed_type_GeneralAudioThreadPool_@@A, bl; _unnamed_type_GeneralAudioThreadPool_ GeneralAudioThreadPool
0x18003432c  call    ?Cleanup@_unnamed_type_AudioCleanupTaskThreadPool_@@QEAAXXZ; _unnamed_type_AudioCleanupTaskThreadPool_::Cleanup(void)
0x180034331  lea     rcx, ?_AudioClientThreadpoolLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x180034338  call    cs:__imp_LeaveCriticalSection
0x18003433e  jmp     short loc_1800342C0
```
