# CDPComUserServiceNotificationHost::RegisterUserDeviceWithDds(CDPComDdsRegistrationUserInfo *,CDPComDdsRegistrationReason)

- ea: `0x1800035f0`
- end: `0x180003876`
- name: `?RegisterUserDeviceWithDds@CDPComUserServiceNotificationHost@@UEAAJPEAUCDPComDdsRegistrationUserInfo@@W4CDPComDdsRegistrationReason@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(int, __int64, unsigned __int16, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800035f0`
- `0x180003880`
- `0x180003e60`
- `0x18001a5b4`
- `0x18001d444`
- `0x1800225a0`
- `0x1800225d0`
- `0x18006a010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000384a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000385e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000384a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000385e`
- `msvcp_win!_Mtx_lock` at `0x180003660`
- `msvcp_win!_Mtx_lock` at `0x180003660`
- `msvcp_win!_Mtx_unlock` at `0x1800036b1`
- `msvcp_win!_Mtx_unlock` at `0x1800036b1`
- `cdp!CDPCreateUserNotificationClientInternal` at `0x1800036f7`
- `cdp!CDPCreateUserNotificationClientInternal` at `0x1800036f7`

## string_xrefs

- `0x180003649`: `{"text":"CDPComUserServiceNotificationHost::RegisterUserDeviceWithDds() called for user %s. Channel URI is: %s"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDPComUserServiceNotificationHost::RegisterUserDeviceWithDds(
        int a1,
        __int64 a2,
        unsigned __int16 a3,
        int a4)
{
  const char *v6; // r8
  __int64 v7; // rax
  _QWORD *v8; // r8
  int v9; // ebx
  int v10; // r9d
  std::_Ref_count_base *v11; // rdi
  std::_Ref_count_base **v12; // rdx
  std::_Ref_count_base *v13; // rcx
  _DWORD *v15; // rax
  unsigned int v16; // edi
  volatile signed __int32 *v17; // rbx
  unsigned int v18; // [rsp+30h] [rbp-29h] BYREF
  int v19; // [rsp+34h] [rbp-25h] BYREF
  std::_Ref_count_base *v20[2]; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v21[3]; // [rsp+48h] [rbp-11h] BYREF
  _QWORD *v22; // [rsp+60h] [rbp+7h] BYREF
  std::_Ref_count_base **v23; // [rsp+68h] [rbp+Fh]
  unsigned __int64 v24; // [rsp+78h] [rbp+1Fh]

  v6 = *(const char **)a2;
  if ( !*(_QWORD *)a2 )
    goto LABEL_16;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  if ( !v7 )
  {
LABEL_16:
    v18 = -2147024809;
    v19 = 26;
    Log<long &,char const (&)[40],int>(a1, a2, (unsigned int)&v18, a4, (__int64)&v19);
    return v18;
  }
  cdp::detail::StringFormat(
    &v22,
    "{\"text\":\"CDPComUserServiceNotificationHost::RegisterUserDeviceWithDds() called for user %s. Channel URI is: %s\"}",
    v6,
    *(const char **)(a2 + 8));
  if ( _Mtx_lock((_Mtx_t)&g_loggerMutex) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800C68EC == 0x7FFFFFFF )
  {
    dword_1800C68EC = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  if ( g_logger )
  {
    v8 = &v22;
    if ( v24 > 0xF )
      v8 = v22;
    (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)g_logger + 24LL))(g_logger, 3, v8);
  }
  _Mtx_unlock((_Mtx_t)&g_loggerMutex);
  if ( v24 > 0xF )
    std::_Deallocate<16>(v22, v24 + 1);
  v21[0] = *(_QWORD *)a2;
  v21[1] = *(_QWORD *)(a2 + 8);
  v21[2] = *(_QWORD *)(a2 + 16);
  *(_OWORD *)v20 = 0;
  v22 = 0;
  v23 = v20;
  v9 = CDPCreateUserNotificationClientInternal(&v22);
  v11 = (std::_Ref_count_base *)v22;
  if ( !v22 )
  {
    v12 = v23;
    *v23 = 0;
    v13 = v12[1];
    v12[1] = 0;
    if ( !v13 )
      goto LABEL_19;
    goto LABEL_15;
  }
  v15 = operator new(0x18u);
  v15[2] = 1;
  v15[3] = 1;
  *(_QWORD *)v15 = &std::_Ref_count_resource<ICDPUserNotificationClient *,cdp::detail::iunknown_deleter<ICDPUserNotificationClient>>::`vftable';
  *((_QWORD *)v15 + 2) = v11;
  v12 = v23;
  *v23 = v11;
  v13 = v12[1];
  v12[1] = (std::_Ref_count_base *)v15;
  if ( v13 )
LABEL_15:
    std::_Ref_count_base::_Decref(v13);
LABEL_19:
  if ( v9 < 0 )
  {
    v18 = v9;
    v19 = 34;
    Log<long &,char const (&)[40],int>((_DWORD)v13, (_DWORD)v12, (unsigned int)&v18, v10, (__int64)&v19);
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
    return v18;
  }
  v16 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)v20[0] + 24LL))(
          v20[0],
          v21,
          a3,
          0);
  v17 = (volatile signed __int32 *)v20[1];
  if ( v20[1] && _InterlockedExchangeAdd((volatile signed __int32 *)v20[1] + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
    if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
  }
  return v16;
}

```

## disassembly

```asm
0x1800035f0  mov     [rsp-8+arg_0], rbx
0x1800035f5  push    rbp
0x1800035f6  push    rsi
0x1800035f7  push    rdi
0x1800035f8  push    r14
0x1800035fa  push    r15
0x1800035fc  lea     rbp, [rsp-37h]
0x180003601  sub     rsp, 90h
0x180003608  mov     rax, cs:__security_cookie
0x18000360f  xor     rax, rsp
0x180003612  mov     [rbp+57h+var_30], rax
0x180003616  mov     r14d, r8d
0x180003619  mov     rbx, rdx
0x18000361c  mov     r8, [rdx]
0x18000361f  test    r8, r8
0x180003622  jz      loc_18000372A
0x180003628  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000362f  mov     rax, rsi
0x180003632  inc     rax
0x180003635  cmp     byte ptr [r8+rax], 0
0x18000363a  jnz     short loc_180003632
0x18000363c  test    rax, rax
0x18000363f  jz      loc_18000372A
0x180003645  mov     r9, [rdx+8]
0x180003649  lea     rdx, aTextCdpcomuser; "{\"text\":\"CDPComUserServiceNotificati"...
0x180003650  lea     rcx, [rbp+57h+var_50]
0x180003654  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180003659  lea     rcx, ?g_loggerMutex@@3Vmutex@std@@A; _Mtx_t
0x180003660  call    cs:__imp__Mtx_lock
0x180003666  test    eax, eax
0x180003668  jnz     loc_180003845
0x18000366e  mov     eax, cs:dword_1800C68EC
0x180003674  cmp     eax, 7FFFFFFFh
0x180003679  jz      loc_180003851
0x18000367f  mov     rcx, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180003686  test    rcx, rcx
0x180003689  jz      short loc_1800036AA
0x18000368b  mov     rax, [rcx]
0x18000368e  lea     r8, [rbp+57h+var_50]
0x180003692  cmp     [rbp+57h+var_38], 0Fh
0x180003697  cmova   r8, [rbp+57h+var_50]
0x18000369c  mov     edx, 3
0x1800036a1  mov     rax, [rax+18h]
0x1800036a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036aa  lea     rcx, ?g_loggerMutex@@3Vmutex@std@@A; _Mtx_t
0x1800036b1  call    cs:__imp__Mtx_unlock
0x1800036b7  mov     rdx, [rbp+57h+var_38]
0x1800036bb  cmp     rdx, 0Fh
0x1800036bf  ja      loc_180003865
0x1800036c5  mov     rax, [rbx]
0x1800036c8  mov     [rbp+57h+var_68], rax
0x1800036cc  mov     rax, [rbx+8]
0x1800036d0  mov     [rbp+57h+var_60], rax
0x1800036d4  mov     rax, [rbx+10h]
0x1800036d8  mov     [rbp+57h+var_58], rax
0x1800036dc  xorps   xmm0, xmm0
0x1800036df  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x1800036e4  xor     r15d, r15d
0x1800036e7  mov     [rbp+57h+var_50], r15
0x1800036eb  lea     rax, [rbp+57h+var_78]
0x1800036ef  mov     [rbp+57h+var_48], rax
0x1800036f3  lea     rcx, [rbp+57h+var_50]
0x1800036f7  call    cs:__imp_CDPCreateUserNotificationClientInternal
0x1800036fd  mov     ebx, eax
0x1800036ff  mov     rdi, [rbp+57h+var_50]
0x180003703  test    rdi, rdi
0x180003706  jnz     short loc_180003770
0x180003708  mov     rdx, [rbp+57h+var_48]
0x18000370c  mov     [rdx], r15
0x18000370f  mov     rcx, [rdx+8]; this
0x180003713  mov     [rdx+8], r15
0x180003717  test    rcx, rcx
0x18000371a  jz      loc_1800037AE
0x180003720  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003725  jmp     loc_1800037AE
0x18000372a  mov     [rbp+57h+var_80], 80070057h
0x180003731  mov     [rbp+57h+var_7C], 1Ah
0x180003738  lea     rax, [rbp+57h+var_7C]
0x18000373c  mov     [rsp+0B0h+var_90], rax
0x180003741  lea     r8, [rbp+57h+var_80]
0x180003745  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18000374a  mov     eax, [rbp+57h+var_80]
0x18000374d  mov     rcx, [rbp+57h+var_30]
0x180003751  xor     rcx, rsp; StackCookie
0x180003754  call    __security_check_cookie
0x180003759  mov     rbx, [rsp+0B0h+arg_0]
0x180003761  add     rsp, 90h
0x180003768  pop     r15
0x18000376a  pop     r14
0x18000376c  pop     rdi
0x18000376d  pop     rsi
0x18000376e  pop     rbp
0x18000376f  retn
0x180003770  mov     ecx, 18h; Size
0x180003775  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000377a  mov     dword ptr [rax+8], 1
0x180003781  mov     dword ptr [rax+0Ch], 1
0x180003788  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPUserNotificationClient@@U?$iunknown_deleter@VICDPUserNotificationClient@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPUserNotificationClient *,cdp::detail::iunknown_deleter<ICDPUserNotificationClient>>::`vftable'
0x18000378f  mov     [rax], rcx
0x180003792  mov     [rax+10h], rdi
0x180003796  mov     rdx, [rbp+57h+var_48]
0x18000379a  mov     [rdx], rdi
0x18000379d  mov     rcx, [rdx+8]
0x1800037a1  mov     [rdx+8], rax
0x1800037a5  test    rcx, rcx
0x1800037a8  jnz     loc_180003720
0x1800037ae  test    ebx, ebx
0x1800037b0  js      short loc_180003812
0x1800037b2  mov     rcx, [rbp+57h+var_78]
0x1800037b6  mov     rax, [rcx]
0x1800037b9  movzx   r8d, r14w
0x1800037bd  xor     r9d, r9d
0x1800037c0  lea     rdx, [rbp+57h+var_68]
0x1800037c4  mov     rax, [rax+18h]
0x1800037c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037cd  mov     edi, eax
0x1800037cf  mov     rbx, [rbp+57h+var_78+8]
0x1800037d3  test    rbx, rbx
0x1800037d6  jz      short loc_18000380B
0x1800037d8  mov     ecx, esi
0x1800037da  lock xadd [rbx+8], ecx
0x1800037df  cmp     ecx, 1
0x1800037e2  jnz     short loc_18000380B
0x1800037e4  mov     rdx, [rbx]
0x1800037e7  mov     rcx, rbx
0x1800037ea  mov     rax, [rdx]
0x1800037ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f2  lock xadd [rbx+0Ch], esi
0x1800037f7  cmp     esi, 1
0x1800037fa  jnz     short loc_18000380B
0x1800037fc  mov     rax, [rbx]
0x1800037ff  mov     rcx, rbx
0x180003802  mov     rax, [rax+8]
0x180003806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000380b  mov     eax, edi
0x18000380d  jmp     loc_18000374D
0x180003812  mov     [rbp+57h+var_80], ebx
0x180003815  mov     [rbp+57h+var_7C], 22h ; '"'
0x18000381c  lea     rax, [rbp+57h+var_7C]
0x180003820  mov     [rsp+0B0h+var_90], rax
0x180003825  lea     r8, [rbp+57h+var_80]
0x180003829  call    ??$Log@AEAJAEAY0CI@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CI@$$CBD$$QEAH@Z; Log<long &,char const (&)[40],int>(CDPLogLevel,char const *,long &,char const (&)[40],int &&)
0x18000382e  mov     rcx, [rbp+57h+var_78+8]; this
0x180003832  test    rcx, rcx
0x180003835  jz      loc_18000374A
0x18000383b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180003840  jmp     loc_18000374A
0x180003845  mov     ecx, 5
0x18000384a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180003850  int     3; Trap to Debugger
0x180003851  dec     eax
0x180003853  mov     cs:dword_1800C68EC, eax
0x180003859  mov     ecx, 6
0x18000385e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180003864  int     3; Trap to Debugger
0x180003865  inc     rdx
0x180003868  mov     rcx, [rbp+57h+var_50]
0x18000386c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180003871  jmp     loc_1800036C5
```
