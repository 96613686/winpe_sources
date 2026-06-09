# Windows::Service::Task::SetMaintenance(void)

- ea: `0x18005e370`
- end: `0x18005e66d`
- name: `?SetMaintenance@Task@Service@Windows@@QEAAXXZ`
- size: `765`
- prototype: `void __fastcall(Windows::Service::Task *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18005b500`

## callees

- `0x1800209fc`
- `0x180023ac4`
- `0x18005e370`
- `0x180071010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e489`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e4f4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e489`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e4f4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e527`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e537`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e547`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e557`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e527`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e537`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e547`
- `OLEAUT32!__imp_SysFreeString` at `0x18005e557`

## string_xrefs

- `0x18005e5d9`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18005e5af`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e5c4`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e5ee`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e603`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e618`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e62d`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e646`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005e65b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Windows::Service::Task::SetMaintenance(Windows::Service::Task *this)
{
  int v2; // eax
  int v3; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-18h] BYREF
  BSTR v16; // [rsp+30h] [rbp-10h] BYREF
  __int64 *v17; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int16 v19; // [rsp+60h] [rbp+20h] BYREF
  __int64 *v20; // [rsp+68h] [rbp+28h] BYREF
  BSTR v21; // [rsp+70h] [rbp+30h] BYREF
  BSTR v22; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 88LL))(*(_QWORD *)this, &v14);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v2,
      v14);
  v17 = 0;
  v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v14)(
         v14,
         &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
         &v17);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v3,
      v14);
  v20 = 0;
  v4 = *v17;
  v20 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v4 + 424))(v17, &v20);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FB,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v5,
      v14);
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v20 + 96))(v20, &v19);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v6,
      v14);
  if ( v19 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v20 + 88))(v20, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v7,
        v14);
    *((_BYTE *)this + 40) = 1;
  }
  v22 = 0;
  v8 = *v20;
  v22 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v8 + 64))(v20, &v22);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v9,
      v14);
  wil::make_bstr(&v16, L"P1D");
  if ( (unsigned int)_o__wcsicmp(v22, v16) )
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v20 + 56))(v20, v16);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20D,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v10,
        v14);
    *((_BYTE *)this + 40) = 1;
  }
  v21 = 0;
  v11 = *v20;
  v21 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v11 + 80))(v20, &v21);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v12,
      v14);
  wil::make_bstr(&bstrString, L"P2D");
  if ( (unsigned int)_o__wcsicmp(v21, bstrString) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64 *, BSTR))(*v20 + 72))(v20, bstrString);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x218,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v13,
        v14);
    *((_BYTE *)this + 40) = 1;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v21 )
    SysFreeString(v21);
  if ( v16 )
    SysFreeString(v16);
  if ( v22 )
    SysFreeString(v22);
  if ( v20 )
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
  if ( v17 )
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
}

```

## disassembly

```asm
0x18005e370  push    rbp
0x18005e372  push    rbx
0x18005e373  push    rdi
0x18005e374  mov     rbp, rsp
0x18005e377  sub     rsp, 40h
0x18005e37b  mov     rbx, rcx
0x18005e37e  xor     edi, edi
0x18005e380  mov     [rbp+var_20], rdi
0x18005e384  mov     rcx, [rcx]
0x18005e387  mov     rax, [rcx]
0x18005e38a  mov     [rbp+var_20], rdi
0x18005e38e  lea     rdx, [rbp+var_20]
0x18005e392  mov     rax, [rax+58h]
0x18005e396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e39b  mov     rcx, [rbp+18h]; this
0x18005e39f  test    eax, eax
0x18005e3a1  js      loc_18005E5C1
0x18005e3a7  mov     rcx, [rbp+var_20]
0x18005e3ab  mov     [rbp+var_8], rdi
0x18005e3af  mov     rax, [rcx]
0x18005e3b2  lea     r8, [rbp+var_8]
0x18005e3b6  lea     rdx, _GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528
0x18005e3bd  mov     rax, [rax]
0x18005e3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3c5  mov     rcx, [rbp+18h]; this
0x18005e3c9  test    eax, eax
0x18005e3cb  js      loc_18005E5D6
0x18005e3d1  mov     [rbp+arg_8], rdi
0x18005e3d5  mov     rcx, [rbp+var_8]
0x18005e3d9  mov     rax, [rcx]
0x18005e3dc  mov     [rbp+arg_8], rdi
0x18005e3e0  lea     rdx, [rbp+arg_8]
0x18005e3e4  mov     rax, [rax+1A8h]
0x18005e3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3f0  mov     rcx, [rbp+18h]; this
0x18005e3f4  test    eax, eax
0x18005e3f6  js      loc_18005E5EB
0x18005e3fc  mov     [rbp+arg_0], di
0x18005e400  mov     rcx, [rbp+arg_8]
0x18005e404  mov     rax, [rcx]
0x18005e407  lea     rdx, [rbp+arg_0]
0x18005e40b  mov     rax, [rax+60h]
0x18005e40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e414  mov     rcx, [rbp+18h]; this
0x18005e418  test    eax, eax
0x18005e41a  js      loc_18005E600
0x18005e420  cmp     [rbp+arg_0], di
0x18005e424  jz      short loc_18005E448
0x18005e426  mov     rcx, [rbp+arg_8]
0x18005e42a  mov     rax, [rcx]
0x18005e42d  xor     edx, edx
0x18005e42f  mov     rax, [rax+58h]
0x18005e433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e438  mov     rcx, [rbp+18h]; this
0x18005e43c  test    eax, eax
0x18005e43e  js      loc_18005E615
0x18005e444  mov     byte ptr [rbx+28h], 1
0x18005e448  mov     [rbp+arg_18], rdi
0x18005e44c  mov     rcx, [rbp+arg_8]
0x18005e450  mov     rax, [rcx]
0x18005e453  mov     [rbp+arg_18], rdi
0x18005e457  lea     rdx, [rbp+arg_18]
0x18005e45b  mov     rax, [rax+40h]
0x18005e45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e464  mov     rcx, [rbp+18h]; this
0x18005e468  test    eax, eax
0x18005e46a  js      loc_18005E62A
0x18005e470  lea     rdx, aP1d; "P1D"
0x18005e477  lea     rcx, [rbp+var_10]
0x18005e47b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005e480  nop
0x18005e481  mov     rdx, [rbp+var_10]
0x18005e485  mov     rcx, [rbp+arg_18]
0x18005e489  call    cs:__imp__o__wcsicmp
0x18005e48f  test    eax, eax
0x18005e491  jz      short loc_18005E4B3
0x18005e493  mov     rcx, [rbp+arg_8]
0x18005e497  mov     rax, [rcx]
0x18005e49a  mov     rdx, [rbp+var_10]
0x18005e49e  mov     rax, [rax+38h]
0x18005e4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4a7  test    eax, eax
0x18005e4a9  js      loc_18005E63F
0x18005e4af  mov     byte ptr [rbx+28h], 1
0x18005e4b3  mov     [rbp+arg_10], rdi
0x18005e4b7  mov     rcx, [rbp+arg_8]
0x18005e4bb  mov     rax, [rcx]
0x18005e4be  mov     [rbp+arg_10], rdi
0x18005e4c2  lea     rdx, [rbp+arg_10]
0x18005e4c6  mov     rax, [rax+50h]
0x18005e4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e4cf  mov     rcx, [rbp+18h]; this
0x18005e4d3  test    eax, eax
0x18005e4d5  js      loc_18005E658
0x18005e4db  lea     rdx, aP2d; "P2D"
0x18005e4e2  lea     rcx, [rbp+bstrString]
0x18005e4e6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005e4eb  nop
0x18005e4ec  mov     rdx, [rbp+bstrString]
0x18005e4f0  mov     rcx, [rbp+arg_10]
0x18005e4f4  call    cs:__imp__o__wcsicmp
0x18005e4fa  test    eax, eax
0x18005e4fc  jz      short loc_18005E51E
0x18005e4fe  mov     rcx, [rbp+arg_8]
0x18005e502  mov     rax, [rcx]
0x18005e505  mov     rdx, [rbp+bstrString]
0x18005e509  mov     rax, [rax+48h]
0x18005e50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e512  test    eax, eax
0x18005e514  js      loc_18005E5A8
0x18005e51a  mov     byte ptr [rbx+28h], 1
0x18005e51e  mov     rcx, [rbp+bstrString]; bstrString
0x18005e522  test    rcx, rcx
0x18005e525  jz      short loc_18005E52E
0x18005e527  call    cs:__imp_SysFreeString
0x18005e52d  nop
0x18005e52e  mov     rcx, [rbp+arg_10]; bstrString
0x18005e532  test    rcx, rcx
0x18005e535  jz      short loc_18005E53E
0x18005e537  call    cs:__imp_SysFreeString
0x18005e53d  nop
0x18005e53e  mov     rcx, [rbp+var_10]; bstrString
0x18005e542  test    rcx, rcx
0x18005e545  jz      short loc_18005E54E
0x18005e547  call    cs:__imp_SysFreeString
0x18005e54d  nop
0x18005e54e  mov     rcx, [rbp+arg_18]; bstrString
0x18005e552  test    rcx, rcx
0x18005e555  jz      short loc_18005E55E
0x18005e557  call    cs:__imp_SysFreeString
0x18005e55d  nop
0x18005e55e  mov     rcx, [rbp+arg_8]
0x18005e562  test    rcx, rcx
0x18005e565  jz      short loc_18005E574
0x18005e567  mov     rax, [rcx]
0x18005e56a  mov     rax, [rax+10h]
0x18005e56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e573  nop
0x18005e574  mov     rcx, [rbp+var_8]
0x18005e578  test    rcx, rcx
0x18005e57b  jz      short loc_18005E58A
0x18005e57d  mov     rax, [rcx]
0x18005e580  mov     rax, [rax+10h]
0x18005e584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e589  nop
0x18005e58a  mov     rcx, [rbp+var_20]
0x18005e58e  test    rcx, rcx
0x18005e591  jz      short loc_18005E5A0
0x18005e593  mov     rax, [rcx]
0x18005e596  mov     rax, [rax+10h]
0x18005e59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e59f  nop
0x18005e5a0  add     rsp, 40h
0x18005e5a4  pop     rdi
0x18005e5a5  pop     rbx
0x18005e5a6  pop     rbp
0x18005e5a7  retn
0x18005e5a8  mov     rcx, [rbp+18h]; this
0x18005e5ac  mov     r9d, eax; char *
0x18005e5af  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e5b6  mov     edx, 218h; void *
0x18005e5bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e5c1  mov     r9d, eax; char *
0x18005e5c4  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e5cb  mov     edx, 1F5h; void *
0x18005e5d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e5d6  mov     r9d, eax; char *
0x18005e5d9  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005e5e0  mov     edx, 1CBEh; void *
0x18005e5e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e5eb  mov     r9d, eax; char *
0x18005e5ee  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e5f5  mov     edx, 1FBh; void *
0x18005e5fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e600  mov     r9d, eax; char *
0x18005e603  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e60a  mov     edx, 1FFh; void *
0x18005e60f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e615  mov     r9d, eax; char *
0x18005e618  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e61f  mov     edx, 202h; void *
0x18005e624  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e62a  mov     r9d, eax; char *
0x18005e62d  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e634  mov     edx, 208h; void *
0x18005e639  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e63f  mov     rcx, [rbp+18h]; this
0x18005e643  mov     r9d, eax; char *
0x18005e646  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e64d  mov     edx, 20Dh; void *
0x18005e652  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e658  mov     r9d, eax; char *
0x18005e65b  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005e662  mov     edx, 213h; void *
0x18005e667  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
