# Windows::Reboot::WaitForStorageReserveInitialization(void)

- ea: `0x180093570`
- end: `0x180093836`
- name: `?WaitForStorageReserveInitialization@Reboot@Windows@@UEAAXXZ`
- size: `710`
- prototype: `void __fastcall(Windows::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180010890`
- `0x180011b8c`
- `0x18001aee4`
- `0x1800420e0`
- `0x18006ea28`
- `0x180093570`
- `0x180093b90`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180093596`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800935e0`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180093596`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800935e0`

## string_xrefs

- `0x180093823`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1800937ec`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x1800935c5`: `TiAttemptedInitialization`
- `0x1800937da`: `Timed out waiting for Trusted Installer Signal - TiAttemptedInitialization`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Reboot::WaitForStorageReserveInitialization(Windows::Reboot *this)
{
  signed __int64 v1; // rsi
  signed __int64 v2; // rdx
  __int64 *System; // rax
  __int64 v4; // rdi
  int *traits_2_unsigned_short; // rax
  const char *v6; // r9
  __int64 v7; // rbx
  __int128 *v8; // rax
  __int64 v9; // rdx
  char SystemBoolOrDefault; // di
  const char *v11; // r9
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  __int64 *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rax
  volatile signed __int32 *v17; // rbx
  const char *v18; // [rsp+28h] [rbp-A0h]
  _QWORD v19[2]; // [rsp+30h] [rbp-98h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-88h] BYREF
  __int128 v21; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-68h] BYREF
  volatile signed __int32 *v23; // [rsp+68h] [rbp-60h]
  __int64 v24; // [rsp+70h] [rbp-58h] BYREF
  volatile signed __int32 *v25; // [rsp+78h] [rbp-50h]
  __int64 v26; // [rsp+80h] [rbp-48h] BYREF
  volatile signed __int32 *v27; // [rsp+88h] [rbp-40h]
  _BYTE v28[16]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  __int64 v30; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v31; // [rsp+E0h] [rbp+18h] BYREF

  v30 = 0;
  GetSystemTimePreciseAsFileTime(&v30);
  v1 = (unsigned int)v30 + ((unsigned __int64)HIDWORD(v30) << 32) - 116444727000000000LL;
  try
  {
    while ( 1 )
    {
      v30 = 0;
      GetSystemTimePreciseAsFileTime(&v30);
      v2 = (unsigned int)v30 + ((unsigned __int64)HIDWORD(v30) << 32) - 116444736000000000LL;
      if ( v1 == v2 || v1 < v2 )
        break;
      System = SystemInterface::Service::GetSystem(&v24);
      v4 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*System + 32LL))(*System, v22);
      traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"TiAttemptedInitialization",
                                         &dword_18012466C,
                                         0);
      if ( traits_2_unsigned_short == &dword_18012466C
        || (v7 = ((char *)traits_2_unsigned_short - (char *)L"TiAttemptedInitialization") >> 1, v7 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v6);
      }
      v8 = (__int128 *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v28);
      v9 = -1;
      do
        ++v9;
      while ( SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID[v9] );
      v19[0] = L"TiAttemptedInitialization";
      v19[1] = v7;
      v21 = *v8;
      v20[0] = SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID;
      v20[1] = v9;
      SystemBoolOrDefault = SystemInterface::Registry::GetSystemBoolOrDefault(v4, v20, &v21, v19);
      v12 = v23;
      if ( v23 )
      {
        if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( !_InterlockedDecrement(v12 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      v13 = v25;
      if ( v25 )
      {
        if ( !_InterlockedDecrement(v25 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( !_InterlockedDecrement(v13 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      if ( SystemBoolOrDefault )
        return;
      v14 = SystemInterface::Service::GetSystem(&v26);
      v15 = (_QWORD *)*v14;
      v16 = *(_QWORD *)*v14;
      v31 = 5000;
      (*(void (__fastcall **)(_QWORD *, __int64 *))(v16 + 248))(v15, &v31);
      v17 = v27;
      if ( v27 && _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    wil::details::in1diag3::Log_Win32Msg(
      retaddr,
      (void *)0xB8,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      (const char *)0x5B4,
      (unsigned int)"Timed out waiting for Trusted Installer Signal - TiAttemptedInitialization",
      v18);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xBA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v11);
  }
}

```

## disassembly

```asm
0x180093570  mov     rax, rsp
0x180093573  mov     [rax+8], rbx
0x180093577  mov     [rax+20h], rsi
0x18009357b  push    rdi
0x18009357c  push    r12
0x18009357e  push    r13
0x180093580  push    r14
0x180093582  push    r15
0x180093584  sub     rsp, 0A0h
0x18009358b  xor     r15d, r15d
0x18009358e  mov     [rax+10h], r15
0x180093592  lea     rcx, [rax+10h]
0x180093596  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18009359c  mov     esi, dword ptr [rsp+0C8h+arg_8+4]
0x1800935a3  shl     rsi, 20h
0x1800935a7  mov     ecx, dword ptr [rsp+0C8h+arg_8]
0x1800935ae  mov     rdx, 0FE624E2343329A00h
0x1800935b8  add     rsi, rdx
0x1800935bb  add     rsi, rcx
0x1800935be  lea     r13, dword_18012466C
0x1800935c5  lea     r12, aTiattemptedini; "TiAttemptedInitialization"
0x1800935cc  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800935d0  mov     [rsp+0C8h+arg_8], r15
0x1800935d8  lea     rcx, [rsp+0C8h+arg_8]
0x1800935e0  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800935e6  mov     eax, dword ptr [rsp+0C8h+arg_8+4]
0x1800935ed  shl     rax, 20h
0x1800935f1  mov     ecx, dword ptr [rsp+0C8h+arg_8]
0x1800935f8  mov     rdx, 0FE624E212AC18000h
0x180093602  add     rdx, rax
0x180093605  add     rdx, rcx
0x180093608  cmp     rsi, rdx
0x18009360b  jz      loc_1800937D2
0x180093611  jl      loc_1800937D2
0x180093617  lea     rcx, [rsp+0C8h+var_58]
0x18009361c  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180093621  nop
0x180093622  mov     rcx, [rax]
0x180093625  mov     rax, [rcx]
0x180093628  lea     rdx, [rsp+0C8h+var_68]
0x18009362d  mov     rax, [rax+20h]
0x180093631  call    _guard_dispatch_icall
0x180093636  nop
0x180093637  mov     rdi, [rax]
0x18009363a  xor     r8d, r8d
0x18009363d  mov     rdx, r13
0x180093640  mov     rcx, r12
0x180093643  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180093648  mov     rbx, rax
0x18009364b  cmp     rax, r13
0x18009364e  jz      loc_18009381B
0x180093654  sub     rbx, r12
0x180093657  sar     rbx, 1
0x18009365a  cmp     rbx, r14
0x18009365d  jz      loc_18009381B
0x180093663  lea     rcx, [rsp+0C8h+var_38]
0x18009366b  call    ??$?0$00@?$basic_zstring_view@_W@wil@@QEAA@AEAY00$$CB_W@Z; wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(wchar_t const (&)[1])
0x180093670  mov     r8, cs:?RESERVEMANAGER_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::RESERVEMANAGER_REDIRECTION_ID
0x180093677  mov     rdx, r14
0x18009367a  inc     rdx
0x18009367d  cmp     [r8+rdx*2], r15w
0x180093682  jnz     short loc_18009367A
0x180093684  mov     [rsp+0C8h+var_98], r12
0x180093689  mov     [rsp+0C8h+var_90], rbx
0x18009368e  movups  xmm0, xmmword ptr [rax]
0x180093691  movdqu  [rsp+0C8h+var_78], xmm0
0x180093697  mov     [rsp+0C8h+var_88], r8
0x18009369c  mov     [rsp+0C8h+var_80], rdx
0x1800936a1  lea     r9, [rsp+0C8h+var_98]
0x1800936a6  lea     r8, [rsp+0C8h+var_78]
0x1800936ab  lea     rdx, [rsp+0C8h+var_88]
0x1800936b0  mov     rcx, rdi
0x1800936b3  call    ?GetSystemBoolOrDefault@Registry@SystemInterface@@QEAA_NV?$basic_zstring_view@_W@wil@@00_N@Z; SystemInterface::Registry::GetSystemBoolOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,bool)
0x1800936b8  mov     dil, al
0x1800936bb  mov     rbx, [rsp+0C8h+var_60]
0x1800936c0  test    rbx, rbx
0x1800936c3  jz      short loc_1800936FD
0x1800936c5  mov     ecx, r14d
0x1800936c8  lock xadd [rbx+8], ecx
0x1800936cd  add     ecx, r14d
0x1800936d0  jnz     short loc_1800936FD
0x1800936d2  mov     rax, [rbx]
0x1800936d5  mov     rcx, rbx
0x1800936d8  mov     rax, [rax]
0x1800936db  call    _guard_dispatch_icall
0x1800936e0  mov     eax, r14d
0x1800936e3  lock xadd [rbx+0Ch], eax
0x1800936e8  add     eax, r14d
0x1800936eb  jnz     short loc_1800936FD
0x1800936ed  mov     rax, [rbx]
0x1800936f0  mov     rcx, rbx
0x1800936f3  mov     rax, [rax+8]
0x1800936f7  call    _guard_dispatch_icall
0x1800936fc  nop
0x1800936fd  mov     rbx, [rsp+0C8h+var_50]
0x180093702  test    rbx, rbx
0x180093705  jz      short loc_18009373E
0x180093707  mov     eax, r14d
0x18009370a  lock xadd [rbx+8], eax
0x18009370f  add     eax, r14d
0x180093712  jnz     short loc_18009373E
0x180093714  mov     rax, [rbx]
0x180093717  mov     rcx, rbx
0x18009371a  mov     rax, [rax]
0x18009371d  call    _guard_dispatch_icall
0x180093722  mov     eax, r14d
0x180093725  lock xadd [rbx+0Ch], eax
0x18009372a  add     eax, r14d
0x18009372d  jnz     short loc_18009373E
0x18009372f  mov     rax, [rbx]
0x180093732  mov     rcx, rbx
0x180093735  mov     rax, [rax+8]
0x180093739  call    _guard_dispatch_icall
0x18009373e  test    dil, dil
0x180093741  jz      short loc_180093748
0x180093743  jmp     loc_1800937FE
0x180093748  lea     rcx, [rsp+0C8h+var_48]
0x180093750  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180093755  nop
0x180093756  mov     rcx, [rax]
0x180093759  mov     rax, [rcx]
0x18009375c  mov     [rsp+0C8h+arg_10], 1388h
0x180093768  lea     rdx, [rsp+0C8h+arg_10]
0x180093770  mov     rax, [rax+0F8h]
0x180093777  call    _guard_dispatch_icall
0x18009377c  nop
0x18009377d  mov     rbx, [rsp+0C8h+var_40]
0x180093785  test    rbx, rbx
0x180093788  jz      loc_1800935D0
0x18009378e  mov     eax, r14d
0x180093791  lock xadd [rbx+8], eax
0x180093796  add     eax, r14d
0x180093799  jnz     loc_1800935D0
0x18009379f  mov     rax, [rbx]
0x1800937a2  mov     rcx, rbx
0x1800937a5  mov     rax, [rax]
0x1800937a8  call    _guard_dispatch_icall
0x1800937ad  mov     eax, r14d
0x1800937b0  lock xadd [rbx+0Ch], eax
0x1800937b5  add     eax, r14d
0x1800937b8  jnz     loc_1800935D0
0x1800937be  mov     rax, [rbx]
0x1800937c1  mov     rcx, rbx
0x1800937c4  mov     rax, [rax+8]
0x1800937c8  call    _guard_dispatch_icall
0x1800937cd  jmp     loc_1800935D0
0x1800937d2  mov     rcx, [rsp+0C8h]; this
0x1800937da  lea     rax, aTimedOutWaitin; "Timed out waiting for Trusted Installer"...
0x1800937e1  mov     qword ptr [rsp+0C8h+var_A8], rax; unsigned int
0x1800937e6  mov     r9d, 5B4h; char *
0x1800937ec  lea     r8, aCW1SSrcOrchest_27; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800937f3  mov     edx, 0B8h; void *
0x1800937f8  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800937fd  nop
0x1800937fe  lea     r11, [rsp+0C8h+var_28]
0x180093806  mov     rbx, [r11+30h]
0x18009380a  mov     rsi, [r11+48h]
0x18009380e  mov     rsp, r11
0x180093811  pop     r15
0x180093813  pop     r14
0x180093815  pop     r13
0x180093817  pop     r12
0x180093819  pop     rdi
0x18009381a  retn
0x18009381b  mov     rcx, [rsp+0C8h]; this
0x180093823  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18009382a  mov     edx, 0C9h; void *
0x18009382f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
