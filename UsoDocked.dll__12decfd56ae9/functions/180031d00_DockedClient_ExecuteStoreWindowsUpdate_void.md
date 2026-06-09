# DockedClient::ExecuteStoreWindowsUpdate(void)

- ea: `0x180031d00`
- end: `0x180031f73`
- name: `?ExecuteStoreWindowsUpdate@DockedClient@@UEAAJXZ`
- size: `627`
- prototype: `__int64 __fastcall(DockedClient *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x1800233b8`
- `0x180026f1c`
- `0x180031d00`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031de6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180031de6`

## string_xrefs

- `0x180031d7f`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x180031e3b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x180031eb1`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DockedClient::ExecuteStoreWindowsUpdate(DockedClient *this)
{
  __int64 *v1; // rax
  __int64 v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  __int64 *v5; // rdi
  __int64 v6; // rsi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  unsigned int v10; // esi
  int v11; // eax
  int v12; // eax
  _QWORD v14[2]; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+48h] [rbp-30h] BYREF
  __int64 *v17; // [rsp+50h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = (__int64 *)wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(v14);
  v2 = *v1;
  *v1 = 0;
  v14[1] = v2;
  if ( v14[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 16LL))(v14[0]);
  v17 = 0;
  v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v2)(
         v2,
         &GUID_20e1713b_cbcc_442d_b441_6440689b8912,
         &v17);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v3,
      v14[0]);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
LABEL_19:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    return v4;
  }
  v5 = v17;
  v6 = *v17;
  string = 0;
  v7 = WindowsCreateStringReference(L"USO", 3u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x180031F71LL);
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v6 + 48))(v5, string, 0);
  v18 = 0;
  v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v2)(
          v2,
          &GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e,
          &v18);
  v4 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v11,
      v14[0]);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    goto LABEL_19;
  }
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18);
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)(unsigned int)v12,
      v14[0]);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v17 )
      (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    goto LABEL_19;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v17 )
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return v10;
}

```

## disassembly

```asm
0x180031d00  mov     [rsp+arg_0], rbx
0x180031d05  mov     [rsp+arg_8], rsi
0x180031d0a  push    rdi
0x180031d0b  sub     rsp, 70h
0x180031d0f  mov     rax, cs:__security_cookie
0x180031d16  xor     rax, rsp
0x180031d19  mov     [rsp+78h+var_18], rax
0x180031d1e  lea     rcx, [rsp+78h+var_58]
0x180031d23  call    ??$ActivateInstance@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>(ushort const *)
0x180031d28  mov     rbx, [rax]
0x180031d2b  mov     qword ptr [rax], 0
0x180031d32  mov     [rsp+78h+var_50], rbx
0x180031d37  mov     rcx, [rsp+78h+var_58]
0x180031d3c  test    rcx, rcx
0x180031d3f  jz      short loc_180031D4E
0x180031d41  mov     rax, [rcx]
0x180031d44  mov     rax, [rax+10h]
0x180031d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d4d  nop
0x180031d4e  mov     [rsp+78h+var_28], 0
0x180031d57  mov     rax, [rbx]
0x180031d5a  lea     r8, [rsp+78h+var_28]
0x180031d5f  lea     rdx, _GUID_20e1713b_cbcc_442d_b441_6440689b8912
0x180031d66  mov     rcx, rbx
0x180031d69  mov     rax, [rax]
0x180031d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d71  mov     edi, eax
0x180031d73  test    eax, eax
0x180031d75  jns     short loc_180031DBF
0x180031d77  mov     rcx, [rsp+78h]; this
0x180031d7c  mov     r9d, eax; char *
0x180031d7f  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180031d86  mov     edx, 74h ; 't'; void *
0x180031d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d90  nop
0x180031d91  mov     rcx, [rsp+78h+var_28]
0x180031d96  test    rcx, rcx
0x180031d99  jz      short loc_180031DA8
0x180031d9b  mov     rax, [rcx]
0x180031d9e  mov     rax, [rax+10h]
0x180031da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031da7  nop
0x180031da8  mov     rax, [rbx]
0x180031dab  mov     rcx, rbx
0x180031dae  mov     rax, [rax+10h]
0x180031db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031db7  nop
0x180031db8  mov     eax, edi
0x180031dba  jmp     loc_180031F4B
0x180031dbf  mov     rdi, [rsp+78h+var_28]
0x180031dc4  mov     rsi, [rdi]
0x180031dc7  mov     [rsp+78h+string], 0
0x180031dd0  lea     r9, [rsp+78h+string]; string
0x180031dd5  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x180031dda  mov     edx, 3; length
0x180031ddf  lea     rcx, aUso; "USO"
0x180031de6  call    cs:__imp_WindowsCreateStringReference
0x180031dec  test    eax, eax
0x180031dee  js      loc_180031F6A
0x180031df4  xor     r8d, r8d
0x180031df7  mov     rdx, [rsp+78h+string]
0x180031dfc  mov     rcx, rdi
0x180031dff  mov     rax, [rsi+30h]
0x180031e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e08  mov     esi, eax
0x180031e0a  mov     [rsp+78h+var_20], 0
0x180031e13  mov     rcx, [rbx]
0x180031e16  mov     rax, [rcx]
0x180031e19  lea     r8, [rsp+78h+var_20]
0x180031e1e  lea     rdx, _GUID_30d5a829_7fa4_4026_83bb_d75bae4ea99e
0x180031e25  mov     rcx, rbx
0x180031e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e2d  mov     edi, eax
0x180031e2f  test    eax, eax
0x180031e31  jns     short loc_180031E92
0x180031e33  mov     rcx, [rsp+78h]; this
0x180031e38  mov     r9d, eax; char *
0x180031e3b  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180031e42  mov     edx, 79h ; 'y'; void *
0x180031e47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031e4c  nop
0x180031e4d  mov     rcx, [rsp+78h+var_20]
0x180031e52  test    rcx, rcx
0x180031e55  jz      short loc_180031E64
0x180031e57  mov     rax, [rcx]
0x180031e5a  mov     rax, [rax+10h]
0x180031e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e63  nop
0x180031e64  mov     rcx, [rsp+78h+var_28]
0x180031e69  test    rcx, rcx
0x180031e6c  jz      short loc_180031E7B
0x180031e6e  mov     rax, [rcx]
0x180031e71  mov     rax, [rax+10h]
0x180031e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e7a  nop
0x180031e7b  mov     rax, [rbx]
0x180031e7e  mov     rcx, rbx
0x180031e81  mov     rax, [rax+10h]
0x180031e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e8a  nop
0x180031e8b  mov     eax, edi
0x180031e8d  jmp     loc_180031F4B
0x180031e92  mov     rcx, [rsp+78h+var_20]
0x180031e97  mov     rax, [rcx]
0x180031e9a  mov     rax, [rax+30h]
0x180031e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ea3  mov     edi, eax
0x180031ea5  test    eax, eax
0x180031ea7  jns     short loc_180031F05
0x180031ea9  mov     rcx, [rsp+78h]; this
0x180031eae  mov     r9d, eax; char *
0x180031eb1  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180031eb8  mov     edx, 7Ah ; 'z'; void *
0x180031ebd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031ec2  nop
0x180031ec3  mov     rcx, [rsp+78h+var_20]
0x180031ec8  test    rcx, rcx
0x180031ecb  jz      short loc_180031EDA
0x180031ecd  mov     rax, [rcx]
0x180031ed0  mov     rax, [rax+10h]
0x180031ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ed9  nop
0x180031eda  mov     rcx, [rsp+78h+var_28]
0x180031edf  test    rcx, rcx
0x180031ee2  jz      short loc_180031EF1
0x180031ee4  mov     rax, [rcx]
0x180031ee7  mov     rax, [rax+10h]
0x180031eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ef0  nop
0x180031ef1  mov     rax, [rbx]
0x180031ef4  mov     rcx, rbx
0x180031ef7  mov     rax, [rax+10h]
0x180031efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f00  nop
0x180031f01  mov     eax, edi
0x180031f03  jmp     short loc_180031F4B
0x180031f05  mov     rcx, [rsp+78h+var_20]
0x180031f0a  test    rcx, rcx
0x180031f0d  jz      short loc_180031F1C
0x180031f0f  mov     rax, [rcx]
0x180031f12  mov     rax, [rax+10h]
0x180031f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f1b  nop
0x180031f1c  mov     rcx, [rsp+78h+var_28]
0x180031f21  test    rcx, rcx
0x180031f24  jz      short loc_180031F33
0x180031f26  mov     rax, [rcx]
0x180031f29  mov     rax, [rax+10h]
0x180031f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f32  nop
0x180031f33  mov     rax, [rbx]
0x180031f36  mov     rcx, rbx
0x180031f39  mov     rax, [rax+10h]
0x180031f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f42  nop
0x180031f43  mov     eax, esi
0x180031f45  jmp     short loc_180031F4B
0x180031f47  mov     eax, dword ptr [rsp+78h+var_28]
0x180031f4b  mov     rcx, [rsp+78h+var_18]
0x180031f50  xor     rcx, rsp; StackCookie
0x180031f53  call    __security_check_cookie
0x180031f58  lea     r11, [rsp+78h+var_8]
0x180031f5d  mov     rbx, [r11+10h]
0x180031f61  mov     rsi, [r11+18h]
0x180031f65  mov     rsp, r11
0x180031f68  pop     rdi
0x180031f69  retn
0x180031f6a  mov     ecx, eax; this
0x180031f6c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
