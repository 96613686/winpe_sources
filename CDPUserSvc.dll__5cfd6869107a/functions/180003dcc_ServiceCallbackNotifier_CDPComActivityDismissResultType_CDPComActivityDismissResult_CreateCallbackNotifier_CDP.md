# ServiceCallbackNotifier<CDPComActivityDismissResultType,CDPComActivityDismissResult>::CreateCallbackNotifier(CDPComNotifierData *)

- ea: `0x180003dcc`
- end: `0x180003fab`
- name: `?CreateCallbackNotifier@?$ServiceCallbackNotifier@W4CDPComActivityDismissResultType@@UCDPComActivityDismissResult@@@@AEAAJPEAUCDPComNotifierData@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045760`
- `0x18004652c`

## callees

- `0x180002a4c`
- `0x180003dcc`
- `0x180004a58`
- `0x180004a98`
- `0x180004df8`
- `0x180006494`
- `0x18002c570`
- `0x180064010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180003f07`
- `msvcp_win!_Mtx_unlock` at `0x180003f8a`
- `msvcp_win!_Mtx_unlock` at `0x180003f07`
- `msvcp_win!_Mtx_unlock` at `0x180003f8a`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180003e56`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180003e56`
- `cdp!CDPCreateCallbackNotifierInternal` at `0x180003e11`
- `cdp!CDPCreateCallbackNotifierInternal` at `0x180003e11`

## string_xrefs

- `0x180003e9f`: `onecoreuap\windows\cdp\service\shared\ServiceCallbackNotifier.h`
- `0x180003f28`: `onecoreuap\windows\cdp\service\shared\ServiceCallbackNotifier.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceCallbackNotifier<enum CDPComActivityDismissResultType,CDPComActivityDismissResult>::CreateCallbackNotifier(
        __int64 a1,
        __int64 *a2)
{
  _QWORD *v3; // r14
  int v4; // esi
  __int64 v5; // r8
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r14
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // r8d
  int v15; // [rsp+30h] [rbp-178h] BYREF
  int v16; // [rsp+34h] [rbp-174h] BYREF
  _QWORD v17[2]; // [rsp+38h] [rbp-170h] BYREF
  _BYTE v18[40]; // [rsp+48h] [rbp-160h] BYREF
  _BYTE v19[272]; // [rsp+70h] [rbp-138h] BYREF

  if ( a2 )
  {
    v3 = (_QWORD *)(a1 + 120);
    v17[1] = a1 + 120;
    v17[0] = 0;
    v4 = CDPCreateCallbackNotifierInternal(v17);
    cdp::detail::address_of<ICDPCallbackNotifier>::~address_of<ICDPCallbackNotifier>(v17);
    if ( v4 < 0 )
    {
      cdp::detail::StringFormat(
        v18,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        v4,
        "onecoreuap\\windows\\cdp\\service\\shared\\ServiceCallbackNotifier.h",
        84);
      v17[0] = &g_loggerMutex;
      std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
      v10 = g_logger;
      if ( g_logger )
      {
        v11 = *(_QWORD *)g_logger;
        v12 = std::_String_val<std::_Simple_types<char>>::_Myptr(v18);
        (*(void (__fastcall **)(__int64, __int64, __int64))(v11 + 24))(v10, 1, v12);
      }
      _Mtx_unlock((_Mtx_t)&g_loggerMutex);
      std::string::_Tidy_deallocate(v18);
      return (unsigned int)v4;
    }
    else
    {
      v15 = 0;
      v19[0] = 0;
      v5 = *a2;
      v19[256] = *((_DWORD *)a2 + 2) != 0;
      if ( v5 )
        _o_strncpy_s(v19, 256, v5, 255);
      try
      {
        (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v3 + 24LL))(*v3, v19);
      }
      catch ( ... )
      {
        LODWORD(v13) = GetCurrentThreadId();
        v17[0] = v13;
        v16 = 92;
        cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(
          (unsigned int)&v15,
          (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"te"
                        "xt\":\"Failed to start callback notifier!\"}",
          v14,
          (unsigned int)&v16,
          (__int64)v17);
      }
      return 0;
    }
  }
  else
  {
    cdp::detail::StringFormat(
      v18,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      -2147024809,
      "onecoreuap\\windows\\cdp\\service\\shared\\ServiceCallbackNotifier.h",
      82);
    v17[0] = &g_loggerMutex;
    std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
    v7 = g_logger;
    if ( g_logger )
    {
      v8 = *(_QWORD *)g_logger;
      v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(v18);
      (*(void (__fastcall **)(__int64, __int64, __int64))(v8 + 24))(v7, 1, v9);
    }
    _Mtx_unlock((_Mtx_t)&g_loggerMutex);
    std::string::_Tidy_deallocate(v18);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003dcc  mov     [rsp+arg_10], rbx
0x180003dd1  push    rsi
0x180003dd2  push    rdi
0x180003dd3  push    r14
0x180003dd5  sub     rsp, 190h
0x180003ddc  mov     rax, cs:__security_cookie
0x180003de3  xor     rax, rsp
0x180003de6  mov     [rsp+1A8h+var_28], rax
0x180003dee  mov     rdi, rdx
0x180003df1  test    rdx, rdx
0x180003df4  jz      loc_180003E97
0x180003dfa  lea     r14, [rcx+78h]
0x180003dfe  mov     [rsp+1A8h+var_168], r14
0x180003e03  mov     [rsp+1A8h+var_170], 0
0x180003e0c  lea     rcx, [rsp+1A8h+var_170]
0x180003e11  call    cs:__imp_CDPCreateCallbackNotifierInternal
0x180003e17  mov     esi, eax
0x180003e19  lea     rcx, [rsp+1A8h+var_170]
0x180003e1e  call    ??1?$address_of@VICDPCallbackNotifier@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCallbackNotifier>::~address_of<ICDPCallbackNotifier>(void)
0x180003e23  test    esi, esi
0x180003e25  js      loc_180003F20
0x180003e2b  xor     ebx, ebx
0x180003e2d  mov     [rsp+1A8h+var_178], ebx
0x180003e31  mov     [rsp+1A8h+var_138], bl
0x180003e35  mov     r8, [rdi]
0x180003e38  cmp     [rdi+8], ebx
0x180003e3b  setnz   [rsp+1A8h+var_38]
0x180003e43  test    r8, r8
0x180003e46  jz      short loc_180003E5C
0x180003e48  mov     edx, 100h
0x180003e4d  lea     r9d, [rdx-1]
0x180003e51  lea     rcx, [rsp+1A8h+var_138]
0x180003e56  call    cs:__imp__o_strncpy_s
0x180003e5c  mov     rcx, [r14]
0x180003e5f  mov     rax, [rcx]
0x180003e62  lea     rdx, [rsp+1A8h+var_138]
0x180003e67  mov     rax, [rax+18h]
0x180003e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e70  nop
0x180003e71  mov     eax, ebx
0x180003e73  mov     rcx, [rsp+1A8h+var_28]
0x180003e7b  xor     rcx, rsp; StackCookie
0x180003e7e  call    __security_check_cookie
0x180003e83  mov     rbx, [rsp+1A8h+arg_10]
0x180003e8b  add     rsp, 190h
0x180003e92  pop     r14
0x180003e94  pop     rdi
0x180003e95  pop     rsi
0x180003e96  retn
0x180003e97  mov     [rsp+1A8h+var_188], 52h ; 'R'
0x180003e9f  lea     r9, aOnecoreuapWind; "onecoreuap\\windows\\cdp\\service\\shar"...
0x180003ea6  mov     r14d, 80070057h
0x180003eac  mov     r8d, r14d
0x180003eaf  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003eb6  lea     rcx, [rsp+1A8h+var_160]
0x180003ebb  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180003ec0  nop
0x180003ec1  lea     rdi, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x180003ec8  mov     [rsp+1A8h+var_170], rdi
0x180003ecd  mov     rcx, rdi; this
0x180003ed0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180003ed5  nop
0x180003ed6  mov     rsi, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180003edd  test    rsi, rsi
0x180003ee0  jz      short loc_180003F04
0x180003ee2  mov     rbx, [rsi]
0x180003ee5  lea     rcx, [rsp+1A8h+var_160]
0x180003eea  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180003eef  mov     r8, rax
0x180003ef2  mov     edx, 1
0x180003ef7  mov     rcx, rsi
0x180003efa  mov     rax, [rbx+18h]
0x180003efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f03  nop
0x180003f04  mov     rcx, rdi; _Mtx_t
0x180003f07  call    cs:__imp__Mtx_unlock
0x180003f0d  nop
0x180003f0e  lea     rcx, [rsp+1A8h+var_160]
0x180003f13  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180003f18  mov     eax, r14d
0x180003f1b  jmp     loc_180003E73
0x180003f20  mov     [rsp+1A8h+var_188], 54h ; 'T'
0x180003f28  lea     r9, aOnecoreuapWind; "onecoreuap\\windows\\cdp\\service\\shar"...
0x180003f2f  mov     r8d, esi
0x180003f32  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180003f39  lea     rcx, [rsp+1A8h+var_160]
0x180003f3e  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180003f43  nop
0x180003f44  lea     rdi, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x180003f4b  mov     [rsp+1A8h+var_170], rdi
0x180003f50  mov     rcx, rdi; this
0x180003f53  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180003f58  nop
0x180003f59  mov     r14, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180003f60  test    r14, r14
0x180003f63  jz      short loc_180003F87
0x180003f65  mov     rbx, [r14]
0x180003f68  lea     rcx, [rsp+1A8h+var_160]
0x180003f6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180003f72  mov     r8, rax
0x180003f75  mov     edx, 1
0x180003f7a  mov     rcx, r14
0x180003f7d  mov     rax, [rbx+18h]
0x180003f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f86  nop
0x180003f87  mov     rcx, rdi; _Mtx_t
0x180003f8a  call    cs:__imp__Mtx_unlock
0x180003f90  nop
0x180003f91  lea     rcx, [rsp+1A8h+var_160]
0x180003f96  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180003f9b  mov     eax, esi
0x180003f9d  jmp     loc_180003E73
0x180003fa2  mov     ebx, [rsp+1A8h+var_178]
0x180003fa6  jmp     loc_180003E71
```
