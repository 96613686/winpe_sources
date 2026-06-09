# DllMain

- ea: `0x18000ba6c`
- end: `0x18000bbc5`
- name: `DllMain`
- size: `345`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001544`

## callees

- `0x1800016d0`
- `0x18000ba6c`
- `0x18001b820`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bb85`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bb85`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18000ba95`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18000ba95`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000baa5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000baa5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000bb2e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000bb2e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000bb0b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000bb0b`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000bba7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000bba7`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v4; // ecx
  REGHANDLE v5; // rcx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      gSystemLangId = GetSystemDefaultLangID();
      DisableThreadLibraryCalls(hinstDLL);
      gDebugRequestedMode = 3;
      gDebugEnabled = 1;
      InitializeClassStore(v4);
      ProviderId = *(GUID *)&(*off_180037008)[-16];
      if ( RegHandle )
        __fastfail(5u);
      xmmword_180037028 = 0;
      if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180037000, &RegHandle) )
        EventSetInformation(
          RegHandle,
          2,
          (char *)off_180037008,
          *(unsigned __int16 *)off_180037008,
          *(_QWORD *)&ProviderId.Data1,
          *(_QWORD *)ProviderId.Data4);
    }
  }
  else
  {
    if ( pCF )
      (*(void (__fastcall **)(struct CAppContainerCF *, DWORD, LPVOID))(*(_QWORD *)pCF + 16LL))(
        pCF,
        fdwReason,
        lpvReserved);
    if ( pCSAccessCF )
      (*(void (__fastcall **)(struct CClassAccessCF *, _QWORD, LPVOID))(*(_QWORD *)pCSAccessCF + 16LL))(
        pCSAccessCF,
        *(_QWORD *)&fdwReason,
        lpvReserved);
    if ( g_pCF )
      (*(void (__fastcall **)(struct CClassContainerCF *, _QWORD, LPVOID))(*(_QWORD *)g_pCF + 16LL))(
        g_pCF,
        *(_QWORD *)&fdwReason,
        lpvReserved);
    DeleteCriticalSection(&ClassStoreBindList);
    v5 = RegHandle;
    dword_180037000 = 0;
    RegHandle = 0;
    EventUnregister(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x18000ba6c  push    rbx
0x18000ba6e  sub     rsp, 40h
0x18000ba72  mov     rax, cs:__security_cookie
0x18000ba79  xor     rax, rsp
0x18000ba7c  mov     [rsp+48h+var_18], rax
0x18000ba81  mov     rbx, rcx
0x18000ba84  test    edx, edx
0x18000ba86  jz      loc_18000BB36
0x18000ba8c  cmp     edx, 1
0x18000ba8f  jnz     loc_18000BBAD
0x18000ba95  call    cs:__imp_GetSystemDefaultLangID
0x18000ba9b  mov     rcx, rbx; hLibModule
0x18000ba9e  mov     cs:?gSystemLangId@@3GA, ax; ushort gSystemLangId
0x18000baa5  call    cs:__imp_DisableThreadLibraryCalls
0x18000baab  mov     cs:?gDebugRequestedMode@@3KA, 3; ulong gDebugRequestedMode
0x18000bab5  mov     cs:?gDebugEnabled@@3KA, 1; ulong gDebugEnabled
0x18000babf  call    ?InitializeClassStore@@YAHH@Z; InitializeClassStore(int)
0x18000bac4  cmp     cs:RegHandle, 0
0x18000bacc  mov     rax, cs:off_180037008
0x18000bad3  movups  xmm0, xmmword ptr [rax-10h]
0x18000bad7  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000badd  jz      short loc_18000BAE6
0x18000badf  mov     ecx, 5
0x18000bae4  int     29h; Win8: RtlFailFast(ecx)
0x18000bae6  xorps   xmm0, xmm0
0x18000bae9  lea     r9, RegHandle; RegHandle
0x18000baf0  lea     r8, dword_180037000; CallbackContext
0x18000baf7  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000bafe  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000bb03  movdqu  cs:xmmword_180037028, xmm0
0x18000bb0b  call    cs:__imp_EventRegister
0x18000bb11  test    eax, eax
0x18000bb13  jnz     loc_18000BBAD
0x18000bb19  mov     r8, cs:off_180037008
0x18000bb20  lea     edx, [rax+2]
0x18000bb23  mov     rcx, cs:RegHandle
0x18000bb2a  movzx   r9d, word ptr [r8]
0x18000bb2e  call    cs:__imp_EventSetInformation
0x18000bb34  jmp     short loc_18000BBAD
0x18000bb36  mov     rcx, cs:?pCF@@3PEAVCAppContainerCF@@EA; CAppContainerCF * pCF
0x18000bb3d  test    rcx, rcx
0x18000bb40  jz      short loc_18000BB4E
0x18000bb42  mov     rax, [rcx]
0x18000bb45  mov     rax, [rax+10h]
0x18000bb49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb4e  mov     rcx, cs:?pCSAccessCF@@3PEAVCClassAccessCF@@EA; CClassAccessCF * pCSAccessCF
0x18000bb55  test    rcx, rcx
0x18000bb58  jz      short loc_18000BB66
0x18000bb5a  mov     rax, [rcx]
0x18000bb5d  mov     rax, [rax+10h]
0x18000bb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb66  mov     rcx, cs:?g_pCF@@3PEAVCClassContainerCF@@EA; CClassContainerCF * g_pCF
0x18000bb6d  test    rcx, rcx
0x18000bb70  jz      short loc_18000BB7E
0x18000bb72  mov     rax, [rcx]
0x18000bb75  mov     rax, [rax+10h]
0x18000bb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb7e  lea     rcx, ?ClassStoreBindList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bb85  call    cs:__imp_DeleteCriticalSection
0x18000bb8b  mov     rcx, cs:RegHandle; RegHandle
0x18000bb92  mov     cs:dword_180037000, 0
0x18000bb9c  mov     cs:RegHandle, 0
0x18000bba7  call    cs:__imp_EventUnregister
0x18000bbad  mov     eax, 1
0x18000bbb2  mov     rcx, [rsp+48h+var_18]
0x18000bbb7  xor     rcx, rsp; StackCookie
0x18000bbba  call    __security_check_cookie
0x18000bbbf  add     rsp, 40h
0x18000bbc3  pop     rbx
0x18000bbc4  retn
```
