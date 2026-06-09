# DllMain

- ea: `0x180002eb8`
- end: `0x180002f9a`
- name: `DllMain`
- size: `226`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a04`

## callees

- `0x180001b90`
- `0x180002eb8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180002f4c`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180002f4c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002f27`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180002f27`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f76`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180002f76`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ed4`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180002ed4`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  REGHANDLE v3; // rcx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    ProviderId = *(GUID *)&(*off_18004AE98)[-16];
    if ( RegHandle )
      __fastfail(5u);
    xmmword_18004AEB8 = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_18004AE90, &RegHandle) )
      EventSetInformation(
        RegHandle,
        2,
        (char *)off_18004AE98,
        *(unsigned __int16 *)off_18004AE98,
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
  }
  else if ( !fdwReason )
  {
    v3 = RegHandle;
    dword_18004AE90 = 0;
    RegHandle = 0;
    EventUnregister(v3);
  }
  return 1;
}

```

## disassembly

```asm
0x180002eb8  sub     rsp, 48h
0x180002ebc  mov     rax, cs:__security_cookie
0x180002ec3  xor     rax, rsp
0x180002ec6  mov     [rsp+48h+var_18], rax
0x180002ecb  cmp     edx, 1
0x180002ece  jnz     loc_180002F5A
0x180002ed4  call    cs:__imp_DisableThreadLibraryCalls
0x180002edb  nop     dword ptr [rax+rax+00h]
0x180002ee0  cmp     cs:RegHandle, 0
0x180002ee8  mov     rax, cs:off_18004AE98
0x180002eef  movups  xmm0, xmmword ptr [rax-10h]
0x180002ef3  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180002ef9  jz      short loc_180002F02
0x180002efb  mov     ecx, 5
0x180002f00  int     29h; Win8: RtlFailFast(ecx)
0x180002f02  xorps   xmm0, xmm0
0x180002f05  lea     r9, RegHandle; RegHandle
0x180002f0c  lea     r8, dword_18004AE90; CallbackContext
0x180002f13  lea     rdx, _tlgEnableCallback; EnableCallback
0x180002f1a  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180002f1f  movdqu  cs:xmmword_18004AEB8, xmm0
0x180002f27  call    cs:__imp_EventRegister
0x180002f2e  nop     dword ptr [rax+rax+00h]
0x180002f33  test    eax, eax
0x180002f35  jnz     short loc_180002F82
0x180002f37  mov     r8, cs:off_18004AE98
0x180002f3e  lea     edx, [rax+2]
0x180002f41  mov     rcx, cs:RegHandle
0x180002f48  movzx   r9d, word ptr [r8]
0x180002f4c  call    cs:__imp_EventSetInformation
0x180002f53  nop     dword ptr [rax+rax+00h]
0x180002f58  jmp     short loc_180002F82
0x180002f5a  test    edx, edx
0x180002f5c  jnz     short loc_180002F82
0x180002f5e  mov     rcx, cs:RegHandle; RegHandle
0x180002f65  mov     cs:dword_18004AE90, edx
0x180002f6b  mov     cs:RegHandle, 0
0x180002f76  call    cs:__imp_EventUnregister
0x180002f7d  nop     dword ptr [rax+rax+00h]
0x180002f82  mov     eax, 1
0x180002f87  mov     rcx, [rsp+48h+var_18]
0x180002f8c  xor     rcx, rsp; StackCookie
0x180002f8f  call    __security_check_cookie
0x180002f94  add     rsp, 48h
0x180002f98  retn
```
