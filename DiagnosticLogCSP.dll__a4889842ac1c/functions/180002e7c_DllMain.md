# DllMain

- ea: `0x180002e7c`
- end: `0x180002f41`
- name: `DllMain`
- size: `197`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019d4`

## callees

- `0x180001b60`
- `0x180002e7c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180002f00`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180002f00`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002ee1`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002ee1`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f24`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f24`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002e94`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002e94`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  REGHANDLE v3; // rcx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    ProviderId = *(GUID *)&(*off_180048E98)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_180048EB8 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_180048E90, &RegHandle) )
      EventSetInformation(
        RegHandle,
        2,
        (char *)off_180048E98,
        *(unsigned __int16 *)off_180048E98,
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
  }
  else if ( !fdwReason )
  {
    v3 = RegHandle;
    dword_180048E90 = 0;
    RegHandle = 0;
    EventUnregister(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x180002e7c  sub     rsp, 48h
0x180002e80  mov     rax, cs:__security_cookie
0x180002e87  xor     rax, rsp
0x180002e8a  mov     [rsp+48h+var_18], rax
0x180002e8f  cmp     edx, 1
0x180002e92  jnz     short loc_180002F08
0x180002e94  call    cs:__imp_DisableThreadLibraryCalls
0x180002e9a  cmp     cs:RegHandle, 0
0x180002ea2  mov     rax, cs:off_180048E98
0x180002ea9  movups  xmm0, xmmword ptr [rax-10h]
0x180002ead  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180002eb3  jz      short loc_180002EBC
0x180002eb5  mov     ecx, 5
0x180002eba  int     29h; Win8: RtlFailFast(ecx)
0x180002ebc  xorps   xmm0, xmm0
0x180002ebf  lea     r9, RegHandle; RegHandle
0x180002ec6  lea     r8, dword_180048E90; CallbackContext
0x180002ecd  lea     rdx, _tlgEnableCallback; EnableCallback
0x180002ed4  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180002ed9  movdqu  cs:xmmword_180048EB8, xmm0
0x180002ee1  call    cs:__imp_EventRegister
0x180002ee7  test    eax, eax
0x180002ee9  jnz     short loc_180002F2A
0x180002eeb  mov     r8, cs:off_180048E98
0x180002ef2  lea     edx, [rax+2]
0x180002ef5  mov     rcx, cs:RegHandle
0x180002efc  movzx   r9d, word ptr [r8]
0x180002f00  call    cs:__imp_EventSetInformation
0x180002f06  jmp     short loc_180002F2A
0x180002f08  test    edx, edx
0x180002f0a  jnz     short loc_180002F2A
0x180002f0c  mov     rcx, cs:RegHandle; RegHandle
0x180002f13  mov     cs:dword_180048E90, edx
0x180002f19  mov     cs:RegHandle, 0
0x180002f24  call    cs:__imp_EventUnregister
0x180002f2a  mov     eax, 1
0x180002f2f  mov     rcx, [rsp+48h+var_18]
0x180002f34  xor     rcx, rsp; StackCookie
0x180002f37  call    __security_check_cookie
0x180002f3c  add     rsp, 48h
0x180002f40  retn
```
