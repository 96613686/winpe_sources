# WpnUserService::OnStartingHelper(void)

- ea: `0x18000a1d8`
- end: `0x18000a43c`
- name: `?OnStartingHelper@WpnUserService@@AEAAJXZ`
- size: `612`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a170`

## callees

- `0x180006244`
- `0x18000a1d8`
- `0x18000e51c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a280`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a280`
- `combase!__imp_CoGetSharedServiceId` at `0x18000a342`
- `combase!__imp_CoGetSharedServiceId` at `0x18000a342`
- `combase!__imp_CoAddRefSharedService` at `0x18000a42b`
- `combase!__imp_CoAddRefSharedService` at `0x18000a42b`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18000a1e8`
- `iertutil!__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ` at `0x18000a1e8`

## string_xrefs

- `0x18000a216`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000a2a7`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000a369`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000a3f2`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnUserService::OnStartingHelper(LPVOID *this)
{
  char *v2; // rbp
  unsigned int v3; // eax
  int started; // eax
  unsigned int v5; // esi
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  __int64 v9; // rcx
  unsigned int Instance; // eax
  int v11; // eax
  __int64 v12; // rcx
  LPVOID v13; // rcx
  _DWORD *v14; // rsi
  unsigned int SharedServiceId; // eax
  int v16; // eax
  unsigned int v17; // edi
  __int64 v18; // rcx
  unsigned int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int ppv; // [rsp+20h] [rbp-78h]
  int ppva; // [rsp+20h] [rbp-78h]
  _QWORD v24[2]; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-48h] BYREF
  __int128 v26; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = (char *)(this + 1);
  v3 = UseEdgeBrowserComponentsForProcess();
  started = LogIfStartSrvFailedAndReturnHr(v3, v2, 12);
  v5 = started;
  v6 = this + 24;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)started,
      ppv);
    v7 = *v6;
    if ( *v6 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v5;
  }
  v9 = *v6;
  if ( *v6 )
  {
    *v6 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, this + 24);
  v11 = LogIfStartSrvFailedAndReturnHr(Instance, v2, 13);
  v5 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v11,
      ppva);
    v12 = *v6;
    if ( *v6 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v5;
  }
  v25[0] = 0;
  v26 = 0;
  v25[1] = this + 25;
  v13 = this[27];
  if ( v13 )
  {
    this[27] = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *(_QWORD *)&v26 = this + 27;
  *((_QWORD *)&v26 + 1) = this;
  v24[0] = 0;
  v24[1] = v25;
  v14 = (_DWORD *)this + 51;
  SharedServiceId = CoGetSharedServiceId((char *)this + 204);
  v16 = LogIfStartSrvFailedAndReturnHr(SharedServiceId, v2, 14);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v16,
      ppva);
    v18 = *v6;
    if ( *v6 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v17;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *))(*(_QWORD *)*v6 + 24LL))(
          *v6,
          WpnUserService::RegisterClassFactoryCallback,
          v24,
          &IID_IContextCallback);
  v20 = LogIfStartSrvFailedAndReturnHr(v19, v2, 15);
  v17 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v20,
      5);
    v21 = *v6;
    if ( *v6 )
    {
      *v6 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v17;
  }
  if ( *v14 )
    CoAddRefSharedService();
  return 0;
}

```

## disassembly

```asm
0x18000a1d8  push    rbx
0x18000a1da  push    rbp
0x18000a1db  push    rsi
0x18000a1dc  push    rdi
0x18000a1dd  sub     rsp, 78h
0x18000a1e1  mov     rdi, rcx
0x18000a1e4  lea     rbp, [rcx+8]
0x18000a1e8  call    cs:__imp_?UseEdgeBrowserComponentsForProcess@@YAJXZ; UseEdgeBrowserComponentsForProcess(void)
0x18000a1ee  mov     r8d, 0Ch
0x18000a1f4  mov     rdx, rbp
0x18000a1f7  mov     ecx, eax
0x18000a1f9  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18000a1fe  mov     esi, eax
0x18000a200  lea     rbx, [rdi+0C0h]
0x18000a207  test    eax, eax
0x18000a209  jns     short loc_18000A24B
0x18000a20b  mov     rcx, [rsp+98h]; this
0x18000a213  mov     r9d, eax; char *
0x18000a216  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a21d  mov     edx, 63h ; 'c'; void *
0x18000a222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a227  nop
0x18000a228  mov     rcx, [rbx]
0x18000a22b  test    rcx, rcx
0x18000a22e  jz      short loc_18000A244
0x18000a230  mov     qword ptr [rbx], 0
0x18000a237  mov     rax, [rcx]
0x18000a23a  mov     rax, [rax+10h]
0x18000a23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a243  nop
0x18000a244  mov     eax, esi
0x18000a246  jmp     loc_18000A433
0x18000a24b  mov     rcx, [rbx]
0x18000a24e  test    rcx, rcx
0x18000a251  jz      short loc_18000A267
0x18000a253  mov     qword ptr [rbx], 0
0x18000a25a  mov     rax, [rcx]
0x18000a25d  mov     rax, [rax+10h]
0x18000a261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a266  nop
0x18000a267  mov     [rsp+98h+ppv], rbx; int
0x18000a26c  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18000a273  xor     edx, edx; pUnkOuter
0x18000a275  lea     r8d, [rdx+1]; dwClsContext
0x18000a279  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18000a280  call    cs:__imp_CoCreateInstance
0x18000a286  mov     r8d, 0Dh
0x18000a28c  mov     rdx, rbp
0x18000a28f  mov     ecx, eax
0x18000a291  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18000a296  mov     esi, eax
0x18000a298  test    eax, eax
0x18000a29a  jns     short loc_18000A2DA
0x18000a29c  mov     rcx, [rsp+98h]; this
0x18000a2a4  mov     r9d, eax; char *
0x18000a2a7  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a2ae  mov     edx, 68h ; 'h'; void *
0x18000a2b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2b8  nop
0x18000a2b9  mov     rcx, [rbx]
0x18000a2bc  test    rcx, rcx
0x18000a2bf  jz      short loc_18000A2D5
0x18000a2c1  mov     qword ptr [rbx], 0
0x18000a2c8  mov     rax, [rcx]
0x18000a2cb  mov     rax, [rax+10h]
0x18000a2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d4  nop
0x18000a2d5  jmp     loc_18000A244
0x18000a2da  mov     [rsp+98h+var_48], 0
0x18000a2e3  xorps   xmm0, xmm0
0x18000a2e6  movdqu  [rsp+98h+var_38], xmm0
0x18000a2ec  lea     rax, [rdi+0C8h]
0x18000a2f3  mov     [rsp+98h+var_40], rax
0x18000a2f8  lea     rsi, [rdi+0D8h]
0x18000a2ff  mov     rcx, [rsi]
0x18000a302  test    rcx, rcx
0x18000a305  jz      short loc_18000A31B
0x18000a307  mov     qword ptr [rsi], 0
0x18000a30e  mov     rax, [rcx]
0x18000a311  mov     rax, [rax+10h]
0x18000a315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31a  nop
0x18000a31b  mov     qword ptr [rsp+98h+var_38], rsi
0x18000a320  mov     qword ptr [rsp+98h+var_38+8], rdi
0x18000a325  mov     [rsp+98h+var_58], 0
0x18000a32e  lea     rax, [rsp+98h+var_48]
0x18000a333  mov     [rsp+98h+var_50], rax
0x18000a338  lea     rsi, [rdi+0CCh]
0x18000a33f  mov     rcx, rsi
0x18000a342  call    cs:__imp_CoGetSharedServiceId
0x18000a348  mov     r8d, 0Eh
0x18000a34e  mov     rdx, rbp
0x18000a351  mov     ecx, eax
0x18000a353  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18000a358  mov     edi, eax
0x18000a35a  test    eax, eax
0x18000a35c  jns     short loc_18000A39E
0x18000a35e  mov     rcx, [rsp+98h]; this
0x18000a366  mov     r9d, eax; char *
0x18000a369  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a370  mov     edx, 74h ; 't'; void *
0x18000a375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a37a  nop
0x18000a37b  mov     rcx, [rbx]
0x18000a37e  test    rcx, rcx
0x18000a381  jz      short loc_18000A397
0x18000a383  mov     qword ptr [rbx], 0
0x18000a38a  mov     rax, [rcx]
0x18000a38d  mov     rax, [rax+10h]
0x18000a391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a396  nop
0x18000a397  mov     eax, edi
0x18000a399  jmp     loc_18000A433
0x18000a39e  mov     rcx, [rbx]
0x18000a3a1  mov     rax, [rcx]
0x18000a3a4  mov     [rsp+98h+var_70], 0
0x18000a3ad  mov     dword ptr [rsp+98h+ppv], 5; int
0x18000a3b5  lea     r9, IID_IContextCallback
0x18000a3bc  lea     r8, [rsp+98h+var_58]
0x18000a3c1  lea     rdx, ?RegisterClassFactoryCallback@WpnUserService@@SAJPEAUtagComCallData@@@Z; WpnUserService::RegisterClassFactoryCallback(tagComCallData *)
0x18000a3c8  mov     rax, [rax+18h]
0x18000a3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d1  mov     r8d, 0Fh
0x18000a3d7  mov     rdx, rbp
0x18000a3da  mov     ecx, eax
0x18000a3dc  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18000a3e1  mov     edi, eax
0x18000a3e3  test    eax, eax
0x18000a3e5  jns     short loc_18000A425
0x18000a3e7  mov     rcx, [rsp+98h]; this
0x18000a3ef  mov     r9d, eax; char *
0x18000a3f2  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a3f9  mov     edx, 7Dh ; '}'; void *
0x18000a3fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a403  nop
0x18000a404  mov     rcx, [rbx]
0x18000a407  test    rcx, rcx
0x18000a40a  jz      short loc_18000A420
0x18000a40c  mov     qword ptr [rbx], 0
0x18000a413  mov     rax, [rcx]
0x18000a416  mov     rax, [rax+10h]
0x18000a41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41f  nop
0x18000a420  jmp     loc_18000A397
0x18000a425  mov     ecx, [rsi]
0x18000a427  test    ecx, ecx
0x18000a429  jz      short loc_18000A431
0x18000a42b  call    cs:__imp_CoAddRefSharedService
0x18000a431  xor     eax, eax
0x18000a433  add     rsp, 78h
0x18000a437  pop     rdi
0x18000a438  pop     rsi
0x18000a439  pop     rbp
0x18000a43a  pop     rbx
0x18000a43b  retn
```
