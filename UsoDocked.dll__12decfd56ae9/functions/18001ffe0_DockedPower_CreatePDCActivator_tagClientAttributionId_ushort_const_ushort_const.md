# DockedPower::CreatePDCActivator(tagClientAttributionId,ushort const *,ushort const *)

- ea: `0x18001ffe0`
- end: `0x180020321`
- name: `?CreatePDCActivator@DockedPower@@UEAAJW4tagClientAttributionId@@PEBG1@Z`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callees

- `0x180006a18`
- `0x180006a28`
- `0x180006a38`
- `0x180006a48`
- `0x180007660`
- `0x180013ccc`
- `0x18001fba4`
- `0x18001ffe0`
- `0x1800209fc`
- `0x180020ac0`
- `0x180071010`

## import_xrefs

- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180020248`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180020248`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180020234`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x180020234`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180020119`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x180020119`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x1800201d4`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x1800201d4`

## string_xrefs

- `0x1800202ca`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x1800202df`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x1800202f6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x18002030e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall DockedPower::CreatePDCActivator(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rax
  __int64 v6; // rsi
  volatile signed __int32 *v7; // rbx
  unsigned int v8; // r12d
  unsigned int v9; // r13d
  bool v10; // r15
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  int v15; // [rsp+20h] [rbp-E8h]
  __int64 v16; // [rsp+40h] [rbp-C8h] BYREF
  int v17[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B8h]
  volatile signed __int32 *v19; // [rsp+58h] [rbp-B0h]
  _QWORD v20[3]; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD v21[2]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v22; // [rsp+80h] [rbp-88h]
  __int64 v23; // [rsp+88h] [rbp-80h]
  __int128 v24; // [rsp+90h] [rbp-78h]
  __int64 v25; // [rsp+A0h] [rbp-68h]
  __int64 v26; // [rsp+A8h] [rbp-60h]
  int v27; // [rsp+B0h] [rbp-58h]
  __int64 v28; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v29; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v16 = a4;
  *(_QWORD *)v17 = a3;
  v5 = *(_QWORD *)(a1 + 16LL * a2 + 48);
  if ( v5 )
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  v6 = *(_QWORD *)(a1 + 16LL * a2 + 40);
  v18 = v6;
  v7 = *(volatile signed __int32 **)(a1 + 16LL * a2 + 48);
  v19 = v7;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v14 = (const char *)(unsigned int)wil::verify_hresult<long>(2147500033LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        v14,
        v15);
    }
    v8 = 116;
    v9 = 1;
  }
  else
  {
    v8 = 115;
    v9 = 3;
  }
  Smtx_lock_shared((_Smtx_t *)(v6 + 24));
  v10 = *(_QWORD *)v6 && *(_QWORD *)(v6 + 8);
  Smtx_unlock_shared((_Smtx_t *)(v6 + 24));
  if ( v10 )
  {
    Smtx_lock_exclusive((_Smtx_t *)(v6 + 24));
    ++*(_DWORD *)(v6 + 16);
    Smtx_unlock_exclusive((_Smtx_t *)(v6 + 24));
    if ( v7 && _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    return 0;
  }
  else
  {
    v20[0] = 1;
    v20[1] = lambda_14454d8367f06cddc8e06bb9cb4f30e3_::_lambda_invoker_cdecl_;
    v20[2] = a1;
    v28 = 0;
    v12 = Pdcv2ActivationClientRegister(v8, v20, &v28);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)(unsigned int)v12,
        v15);
    if ( !v28 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)0x8000FFFFLL,
        v15);
    v22 = 0;
    v24 = 0;
    v25 = 3;
    v21[0] = 3;
    v26 = -1;
    v21[1] = 180;
    v23 = v16;
    v27 = -1;
    v29 = 0;
    v13 = Pdcv2ActivationClientActivate(v28, v21, 0, v9);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
        (const char *)(unsigned int)v13,
        v17[0]);
    *(_QWORD *)v17 = v29;
    v29 = 0;
    v16 = v28;
    v28 = 0;
    DockedPower::pdcRegistrationInfo::Add(v6, &v16, v17);
    if ( v29 )
      Pdcv2ActivationClientDeactivate();
    if ( v28 )
      Pdcv2ActivationClientUnregister();
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001ffe0  push    rbx
0x18001ffe2  push    rsi
0x18001ffe3  push    rdi
0x18001ffe4  push    r12
0x18001ffe6  push    r13
0x18001ffe8  push    r14
0x18001ffea  push    r15
0x18001ffec  sub     rsp, 0D0h
0x18001fff3  mov     rax, cs:__security_cookie
0x18001fffa  xor     rax, rsp
0x18001fffd  mov     [rsp+108h+var_40], rax
0x180020005  mov     [rsp+108h+var_C8], r9
0x18002000a  mov     qword ptr [rsp+108h+var_C0], r8
0x18002000f  mov     r14, rcx
0x180020012  movsxd  rbx, edx
0x180020015  add     rbx, rbx
0x180020018  mov     rax, [rcx+rbx*8+30h]
0x18002001d  test    rax, rax
0x180020020  jz      short loc_180020026
0x180020022  lock inc dword ptr [rax+8]
0x180020026  mov     rsi, [rcx+rbx*8+28h]
0x18002002b  mov     [rsp+108h+var_B8], rsi
0x180020030  mov     rbx, [rcx+rbx*8+30h]
0x180020035  mov     [rsp+108h+var_B0], rbx
0x18002003a  test    edx, edx
0x18002003c  jz      short loc_180020054
0x18002003e  cmp     edx, 1
0x180020041  jnz     loc_1800202B5
0x180020047  mov     r12d, 74h ; 't'
0x18002004d  lea     r13d, [r12-73h]
0x180020052  jmp     short loc_18002005F
0x180020054  mov     r12d, 73h ; 's'
0x18002005a  lea     r13d, [r12-70h]
0x18002005f  lea     rdi, [rsi+18h]
0x180020063  mov     rcx, rdi; _Smtx_t *
0x180020066  call    _Smtx_lock_shared
0x18002006b  cmp     qword ptr [rsi], 0
0x18002006f  jz      short loc_18002007D
0x180020071  cmp     qword ptr [rsi+8], 0
0x180020076  jz      short loc_18002007D
0x180020078  mov     r15b, 1
0x18002007b  jmp     short loc_180020080
0x18002007d  xor     r15b, r15b
0x180020080  mov     rcx, rdi; _Smtx_t *
0x180020083  call    _Smtx_unlock_shared
0x180020088  test    r15b, r15b
0x18002008b  jz      short loc_1800200E4
0x18002008d  mov     rcx, rdi; _Smtx_t *
0x180020090  call    _Smtx_lock_exclusive
0x180020095  inc     dword ptr [rsi+10h]
0x180020098  mov     rcx, rdi; _Smtx_t *
0x18002009b  call    _Smtx_unlock_exclusive
0x1800200a0  nop
0x1800200a1  test    rbx, rbx
0x1800200a4  jz      short loc_1800200DD
0x1800200a6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800200aa  mov     eax, edi
0x1800200ac  lock xadd [rbx+8], eax
0x1800200b1  add     eax, edi
0x1800200b3  jnz     short loc_1800200DD
0x1800200b5  mov     rax, [rbx]
0x1800200b8  mov     rcx, rbx
0x1800200bb  mov     rax, [rax]
0x1800200be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200c3  mov     eax, edi
0x1800200c5  lock xadd [rbx+0Ch], eax
0x1800200ca  add     eax, edi
0x1800200cc  jnz     short loc_1800200DD
0x1800200ce  mov     rax, [rbx]
0x1800200d1  mov     rcx, rbx
0x1800200d4  mov     rax, [rax+8]
0x1800200d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200dd  xor     eax, eax
0x1800200df  jmp     loc_180020292
0x1800200e4  mov     [rsp+108h+var_A8], 1
0x1800200ed  lea     rax, _lambda_14454d8367f06cddc8e06bb9cb4f30e3____lambda_invoker_cdecl_
0x1800200f4  mov     [rsp+108h+var_A0], rax
0x1800200f9  mov     [rsp+108h+var_98], r14
0x1800200fe  xor     r14d, r14d
0x180020101  mov     [rsp+108h+var_50], r14
0x180020109  lea     r8, [rsp+108h+var_50]
0x180020111  lea     rdx, [rsp+108h+var_A8]
0x180020116  mov     ecx, r12d
0x180020119  call    cs:__imp_Pdcv2ActivationClientRegister
0x18002011f  mov     rcx, [rsp+108h]; this
0x180020127  test    eax, eax
0x180020129  js      loc_1800202DC
0x18002012f  mov     rax, [rsp+108h]
0x180020137  mov     rcx, [rsp+108h+var_50]
0x18002013f  test    rcx, rcx
0x180020142  jz      loc_1800202F0
0x180020148  mov     [rsp+108h+var_88], r14
0x180020150  xorps   xmm0, xmm0
0x180020153  movdqu  [rsp+108h+var_78], xmm0
0x18002015c  mov     [rsp+108h+var_68], 3
0x180020168  mov     [rsp+108h+var_90], 3
0x180020170  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020174  mov     [rsp+108h+var_60], rdi
0x18002017c  mov     [rsp+108h+var_8C], 0B4h
0x180020184  mov     rax, [rsp+108h+var_C8]
0x180020189  mov     [rsp+108h+var_80], rax
0x180020191  mov     [rsp+108h+var_58], edi
0x180020198  mov     [rsp+108h+var_48], r14
0x1800201a0  lea     rax, [rsp+108h+var_58]
0x1800201a8  mov     [rsp+108h+var_D0], rax
0x1800201ad  lea     rax, [rsp+108h+var_48]
0x1800201b5  mov     [rsp+108h+var_D8], rax
0x1800201ba  mov     [rsp+108h+var_E0], r14d
0x1800201bf  mov     rax, qword ptr [rsp+108h+var_C0]
0x1800201c4  mov     qword ptr [rsp+108h+var_E8], rax; int
0x1800201c9  mov     r9d, r13d
0x1800201cc  xor     r8d, r8d
0x1800201cf  lea     rdx, [rsp+108h+var_90]
0x1800201d4  call    cs:__imp_Pdcv2ActivationClientActivate
0x1800201da  mov     rcx, [rsp+108h]; this
0x1800201e2  test    eax, eax
0x1800201e4  js      loc_18002030B
0x1800201ea  mov     rax, [rsp+108h+var_48]
0x1800201f2  mov     qword ptr [rsp+108h+var_C0], rax
0x1800201f7  mov     [rsp+108h+var_48], r14
0x1800201ff  mov     rax, [rsp+108h+var_50]
0x180020207  mov     [rsp+108h+var_C8], rax
0x18002020c  mov     [rsp+108h+var_50], r14
0x180020214  lea     r8, [rsp+108h+var_C0]
0x180020219  lea     rdx, [rsp+108h+var_C8]
0x18002021e  mov     rcx, rsi
0x180020221  call    ?Add@pdcRegistrationInfo@DockedPower@@QEAAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?Pdcv2ActivationClientDeactivate@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z; DockedPower::pdcRegistrationInfo::Add(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&Pdcv2ActivationClientDeactivate(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>)
0x180020226  nop
0x180020227  mov     rcx, [rsp+108h+var_48]
0x18002022f  test    rcx, rcx
0x180020232  jz      short loc_18002023B
0x180020234  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x18002023a  nop
0x18002023b  mov     rcx, [rsp+108h+var_50]
0x180020243  test    rcx, rcx
0x180020246  jz      short loc_18002024F
0x180020248  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18002024e  nop
0x18002024f  test    rbx, rbx
0x180020252  jz      short loc_180020287
0x180020254  mov     eax, edi
0x180020256  lock xadd [rbx+8], eax
0x18002025b  add     eax, edi
0x18002025d  jnz     short loc_180020287
0x18002025f  mov     rax, [rbx]
0x180020262  mov     rcx, rbx
0x180020265  mov     rax, [rax]
0x180020268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002026d  mov     eax, edi
0x18002026f  lock xadd [rbx+0Ch], eax
0x180020274  add     eax, edi
0x180020276  jnz     short loc_180020287
0x180020278  mov     rax, [rbx]
0x18002027b  mov     rcx, rbx
0x18002027e  mov     rax, [rax+8]
0x180020282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020287  xor     eax, eax
0x180020289  jmp     short loc_180020292
0x18002028b  mov     eax, [rsp+108h+var_58]
0x180020292  mov     rcx, [rsp+108h+var_40]
0x18002029a  xor     rcx, rsp; StackCookie
0x18002029d  call    __security_check_cookie
0x1800202a2  add     rsp, 0D0h
0x1800202a9  pop     r15
0x1800202ab  pop     r14
0x1800202ad  pop     r13
0x1800202af  pop     r12
0x1800202b1  pop     rdi
0x1800202b2  pop     rsi
0x1800202b3  pop     rbx
0x1800202b4  retn
0x1800202b5  mov     ecx, 80004001h
0x1800202ba  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800202bf  mov     r9d, eax; char *
0x1800202c2  mov     rcx, [rsp+108h]; this
0x1800202ca  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800202d1  mov     edx, 0D9h; void *
0x1800202d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800202dc  mov     r9d, eax; char *
0x1800202df  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800202e6  mov     edx, 0F9h; void *
0x1800202eb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800202f0  mov     r9d, 8000FFFFh; char *
0x1800202f6  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800202fd  mov     edx, 0FAh; void *
0x180020302  mov     rcx, rax; this
0x180020305  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002030b  mov     r9d, eax; char *
0x18002030e  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180020315  mov     edx, 10Ah; void *
0x18002031a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
