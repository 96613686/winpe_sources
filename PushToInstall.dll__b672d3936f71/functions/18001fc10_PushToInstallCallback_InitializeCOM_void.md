# PushToInstallCallback::InitializeCOM(void)

- ea: `0x18001fc10`
- end: `0x18001fcd3`
- name: `?InitializeCOM@PushToInstallCallback@@UEAA_NXZ`
- size: `195`
- prototype: `bool __fastcall(PushToInstallCallback *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18001fc10`
- `0x18002008c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fc46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fc46`

## string_xrefs

- `0x18001fcac`: `onecoreuap\enduser\winstore\pushtoinstall\svc\svcmain.cpp`
- `0x18001fcc0`: `onecoreuap\enduser\winstore\pushtoinstall\svc\svcmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall PushToInstallCallback::InitializeCOM(PushToInstallCallback *this)
{
  HRESULT v1; // eax
  int v2; // eax
  const char *v3; // r9
  _QWORD *v4; // rcx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v1 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v8);
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB5,
        (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\svc\\svcmain.cpp",
        (const char *)(unsigned int)v1,
        ppv);
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, 5, 1);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB6,
        (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\svc\\svcmain.cpp",
        (const char *)(unsigned int)v2,
        ppv);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\svc\\svcmain.cpp",
      v3);
  }
  v4 = v8;
  if ( v8 )
  {
    v8 = 0;
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v4 + 16LL))(v4, *v4);
  }
  return 1;
}

```

## disassembly

```asm
0x18001fc10  push    rbx
0x18001fc12  sub     rsp, 30h
0x18001fc16  mov     [rsp+38h+arg_8], 0
0x18001fc1b  mov     [rsp+38h+arg_10], 0
0x18001fc24  lea     rax, [rsp+38h+arg_10]
0x18001fc29  mov     qword ptr [rsp+38h+ppv], rax; int
0x18001fc2e  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18001fc35  mov     ebx, 1
0x18001fc3a  mov     r8d, ebx; dwClsContext
0x18001fc3d  xor     edx, edx; pUnkOuter
0x18001fc3f  lea     rcx, CLSID_GlobalOptions; rclsid
0x18001fc46  call    cs:__imp_CoCreateInstance
0x18001fc4c  mov     rcx, [rsp+38h]; this
0x18001fc51  test    eax, eax
0x18001fc53  js      short loc_18001FCA9
0x18001fc55  mov     rcx, [rsp+38h+arg_10]
0x18001fc5a  mov     rax, [rcx]
0x18001fc5d  mov     r8, rbx
0x18001fc60  mov     edx, 5
0x18001fc65  mov     rax, [rax+18h]
0x18001fc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc6e  mov     rcx, [rsp+38h]; this
0x18001fc73  test    eax, eax
0x18001fc75  js      short loc_18001FCBD
0x18001fc77  mov     [rsp+38h+arg_8], bl
0x18001fc7b  jmp     short loc_18001FC81
0x18001fc7d  mov     bl, [rsp+38h+arg_8]
0x18001fc81  mov     rcx, [rsp+38h+arg_10]
0x18001fc86  test    rcx, rcx
0x18001fc89  jz      short loc_18001FCA1
0x18001fc8b  mov     [rsp+38h+arg_10], 0
0x18001fc94  mov     rdx, [rcx]
0x18001fc97  mov     rax, [rdx+10h]
0x18001fc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fca0  nop
0x18001fca1  mov     al, bl
0x18001fca3  add     rsp, 30h
0x18001fca7  pop     rbx
0x18001fca8  retn
0x18001fca9  mov     r9d, eax; char *
0x18001fcac  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18001fcb3  mov     edx, 0B5h; void *
0x18001fcb8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001fcbd  mov     r9d, eax; char *
0x18001fcc0  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18001fcc7  mov     edx, 0B6h; void *
0x18001fccc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
