# ATL::CComObject<WPCSecurityManager>::~CComObject<WPCSecurityManager>(void)

- ea: `0x1800318c8`
- end: `0x18003196d`
- name: `??1?$CComObject@VWPCSecurityManager@@@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031980`

## callees

- `0x1800318c8`
- `0x180035010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18003190a`
- `KERNEL32!EnterCriticalSection` at `0x18003190a`
- `KERNEL32!LeaveCriticalSection` at `0x18003192f`
- `KERNEL32!LeaveCriticalSection` at `0x18003192f`
- `KERNEL32!DeleteCriticalSection` at `0x18003194c`
- `KERNEL32!DeleteCriticalSection` at `0x180031960`
- `KERNEL32!DeleteCriticalSection` at `0x18003194c`
- `KERNEL32!DeleteCriticalSection` at `0x180031960`
- `urlmon!UnregisterWebPlatformPermanentSecurityManager` at `0x18003191a`
- `urlmon!UnregisterWebPlatformPermanentSecurityManager` at `0x18003191a`
- `iertutil!__imp_SetWebPlatformSecurityManagerFactoryCallback` at `0x180031922`
- `iertutil!__imp_SetWebPlatformSecurityManagerFactoryCallback` at `0x180031922`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ATL::CComObject<WPCSecurityManager>::~CComObject<WPCSecurityManager>(__int64 a1)
{
  *(_QWORD *)a1 = &ATL::CComObject<WPCSecurityManager>::`vftable'{for `IWebPlatformPermanentSecurityManager'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<WPCSecurityManager>::`vftable'{for `IWebPlatformPermanentSecurityManagerInternal'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<WPCSecurityManager>::`vftable'{for `IInternetSecurityManagerEx2'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<WPCSecurityManager>::`vftable'{for `IPermanentInternetSecurityManagerInternal'};
  *(_DWORD *)(a1 + 32) = -1073741823;
  EnterCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
  if ( WPCSecurityManager::s_spSecurityManager )
  {
    UnregisterWebPlatformPermanentSecurityManager();
    SetWebPlatformSecurityManagerFactoryCallback(0);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)&WPCSecurityManager::s_csInitializeLock);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( *(_BYTE *)(a1 + 80) )
  {
    *(_BYTE *)(a1 + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
}

```

## disassembly

```asm
0x1800318c8  push    rbx
0x1800318ca  sub     rsp, 20h
0x1800318ce  mov     rbx, rcx
0x1800318d1  lea     rax, ??_7?$CComObject@VWPCSecurityManager@@@ATL@@6BIWebPlatformPermanentSecurityManager@@@; const ATL::CComObject<WPCSecurityManager>::`vftable'{for `IWebPlatformPermanentSecurityManager'}
0x1800318d8  mov     [rcx], rax
0x1800318db  lea     rax, ??_7?$CComObject@VWPCSecurityManager@@@ATL@@6BIWebPlatformPermanentSecurityManagerInternal@@@; const ATL::CComObject<WPCSecurityManager>::`vftable'{for `IWebPlatformPermanentSecurityManagerInternal'}
0x1800318e2  mov     [rcx+8], rax
0x1800318e6  lea     rax, ??_7?$CComObject@VWPCSecurityManager@@@ATL@@6BIInternetSecurityManagerEx2@@@; const ATL::CComObject<WPCSecurityManager>::`vftable'{for `IInternetSecurityManagerEx2'}
0x1800318ed  mov     [rcx+10h], rax
0x1800318f1  lea     rax, ??_7?$CComObject@VWPCSecurityManager@@@ATL@@6BIPermanentInternetSecurityManagerInternal@@@; const ATL::CComObject<WPCSecurityManager>::`vftable'{for `IPermanentInternetSecurityManagerInternal'}
0x1800318f8  mov     [rcx+18h], rax
0x1800318fc  mov     dword ptr [rcx+20h], 0C0000001h
0x180031903  lea     rcx, ?s_csInitializeLock@WPCSecurityManager@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x18003190a  call    cs:__imp_EnterCriticalSection
0x180031910  cmp     cs:?s_spSecurityManager@WPCSecurityManager@@0V?$CComObjPtr@VWPCSecurityManager@@@@A, 0; CComObjPtr<WPCSecurityManager> WPCSecurityManager::s_spSecurityManager
0x180031918  jz      short loc_180031928
0x18003191a  call    cs:__imp_UnregisterWebPlatformPermanentSecurityManager
0x180031920  xor     ecx, ecx
0x180031922  call    cs:__imp_SetWebPlatformSecurityManagerFactoryCallback
0x180031928  lea     rcx, ?s_csInitializeLock@WPCSecurityManager@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x18003192f  call    cs:__imp_LeaveCriticalSection
0x180031935  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003193c  mov     rax, [rcx]
0x18003193f  mov     rax, [rax+10h]
0x180031943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031948  lea     rcx, [rbx+58h]; lpCriticalSection
0x18003194c  call    cs:__imp_DeleteCriticalSection
0x180031952  lea     rcx, [rbx+28h]; lpCriticalSection
0x180031956  cmp     byte ptr [rcx+28h], 0
0x18003195a  jz      short loc_180031967
0x18003195c  mov     byte ptr [rcx+28h], 0
0x180031960  call    cs:__imp_DeleteCriticalSection
0x180031966  nop
0x180031967  add     rsp, 20h
0x18003196b  pop     rbx
0x18003196c  retn
```
