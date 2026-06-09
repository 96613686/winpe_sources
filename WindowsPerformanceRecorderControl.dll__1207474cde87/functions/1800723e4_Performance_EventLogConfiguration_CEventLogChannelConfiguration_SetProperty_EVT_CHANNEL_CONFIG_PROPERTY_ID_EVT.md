# Performance::EventLogConfiguration::CEventLogChannelConfiguration::SetProperty(_EVT_CHANNEL_CONFIG_PROPERTY_ID,_EVT_VARIANT *)

- ea: `0x1800723e4`
- end: `0x180072440`
- name: `?SetProperty@CEventLogChannelConfiguration@EventLogConfiguration@Performance@@AEAAJW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@PEAU_EVT_VARIANT@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(Performance::EventLogConfiguration::CEventLogChannelConfiguration *__hidden this, enum _EVT_CHANNEL_CONFIG_PROPERTY_ID, struct _EVT_VARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180072450`

## callees

- `0x18004b314`
- `0x18004b39c`
- `0x1800723e4`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180072411`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180072411`

## string_xrefs

- `0x180072407`: `EvtSetChannelConfigProperty`

## pseudocode

```c
__int64 __fastcall Performance::EventLogConfiguration::CEventLogChannelConfiguration::SetProperty(
        Performance::EventLogConfiguration::CEventLogChannelConfiguration *this,
        enum _EVT_CHANNEL_CONFIG_PROPERTY_ID a2,
        struct _EVT_VARIANT *a3)
{
  HMODULE v6; // rax
  FARPROC ProcAddress; // rax

  if ( !*((_QWORD *)this + 12) )
    return 2147549183LL;
  v6 = Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *((__int64)this);
  ProcAddress = GetProcAddress(v6, "EvtSetChannelConfigProperty");
  if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, struct _EVT_VARIANT *))ProcAddress)(
         *((_QWORD *)this + 12),
         0,
         0,
         a3) )
  {
    return 0;
  }
  else
  {
    return ATL::AtlHresultFromLastError();
  }
}

```

## disassembly

```asm
0x1800723e4  mov     [rsp+arg_0], rbx
0x1800723e9  push    rdi
0x1800723ea  sub     rsp, 30h
0x1800723ee  cmp     qword ptr [rcx+60h], 0
0x1800723f3  mov     rdi, r8
0x1800723f6  mov     rbx, rcx
0x1800723f9  jnz     short loc_180072402
0x1800723fb  mov     eax, 8000FFFFh
0x180072400  jmp     short loc_180072435
0x180072402  call    ??B?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAPEAUHINSTANCE__@@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::operator HINSTANCE__ *(void)
0x180072407  lea     rdx, aEvtsetchannelc; "EvtSetChannelConfigProperty"
0x18007240e  mov     rcx, rax; hModule
0x180072411  call    cs:__imp_GetProcAddress
0x180072417  mov     rcx, [rbx+60h]
0x18007241b  mov     r9, rdi
0x18007241e  xor     r8d, r8d
0x180072421  xor     edx, edx
0x180072423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072428  test    eax, eax
0x18007242a  jnz     short loc_180072433
0x18007242c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180072431  jmp     short loc_180072435
0x180072433  xor     eax, eax
0x180072435  mov     rbx, [rsp+38h+arg_0]
0x18007243a  add     rsp, 30h
0x18007243e  pop     rdi
0x18007243f  retn
```
