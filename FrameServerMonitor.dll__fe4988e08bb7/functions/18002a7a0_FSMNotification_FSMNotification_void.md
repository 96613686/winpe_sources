# FSMNotification::~FSMNotification(void)

- ea: `0x18002a7a0`
- end: `0x18002a832`
- name: `??1FSMNotification@@MEAA@XZ`
- size: `146`
- prototype: `void __fastcall(FSMNotification *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002a840`

## callees

- `0x180003194`
- `0x1800060e8`
- `0x180006f9c`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18002a3d4`
- `0x18002a7a0`
- `0x18002b490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a81f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a81f`

## pseudocode

```c
void __fastcall FSMNotification::~FSMNotification(FSMNotification *this)
{
  FSMNotification *v2; // rcx
  void *v3; // rdx

  *(_QWORD *)this = &FSMNotification::`vftable'{for `FSMObject'};
  v2 = (FSMNotification *)((char *)this + 40);
  *(_QWORD *)v2 = &FSMNotification::`vftable'{for `IFSMNotification'};
  FSMNotification::Shutdown(v2);
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 14, &WPP_6a5df37b9d8e3fae40fd41b1c2ef84aa_Traceguids, this);
  CTUnkArray<IFSMemory>::~CTUnkArray<IFSMemory>((char *)this + 144);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((char *)this + 128);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((char *)this + 112);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    (wil::details **)this + 13,
    v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  FSMObject::~FSMObject(this);
}

```

## disassembly

```asm
0x18002a7a0  push    rbx
0x18002a7a2  sub     rsp, 20h
0x18002a7a6  lea     rax, ??_7FSMNotification@@6BFSMObject@@@; const FSMNotification::`vftable'{for `FSMObject'}
0x18002a7ad  mov     rbx, rcx
0x18002a7b0  mov     [rcx], rax
0x18002a7b3  add     rcx, 28h ; '('; this
0x18002a7b7  lea     rax, ??_7FSMNotification@@6BIFSMNotification@@@; const FSMNotification::`vftable'{for `IFSMNotification'}
0x18002a7be  mov     [rcx], rax
0x18002a7c1  call    ?Shutdown@FSMNotification@@UEAAJXZ; FSMNotification::Shutdown(void)
0x18002a7c6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002a7cb  cmp     al, 10h
0x18002a7cd  jb      short loc_18002A7F1
0x18002a7cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7d6  lea     r8, WPP_6a5df37b9d8e3fae40fd41b1c2ef84aa_Traceguids
0x18002a7dd  mov     edx, 0Eh
0x18002a7e2  mov     r9, rbx
0x18002a7e5  mov     rcx, [rcx+0D8h]
0x18002a7ec  call    WPP_SF_q
0x18002a7f1  lea     rcx, [rbx+90h]
0x18002a7f8  call    ??1?$CTUnkArray@UIFSMemory@@@@QEAA@XZ; CTUnkArray<IFSMemory>::~CTUnkArray<IFSMemory>(void)
0x18002a7fd  lea     rcx, [rbx+80h]
0x18002a804  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18002a809  lea     rcx, [rbx+70h]
0x18002a80d  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18002a812  lea     rcx, [rbx+68h]
0x18002a816  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a81b  lea     rcx, [rbx+38h]; lpCriticalSection
0x18002a81f  call    cs:__imp_DeleteCriticalSection
0x18002a825  mov     rcx, rbx; this
0x18002a828  add     rsp, 20h
0x18002a82c  pop     rbx
0x18002a82d  jmp     ??1FSMObject@@MEAA@XZ; FSMObject::~FSMObject(void)
```
