# ServiceCallbackNotifier<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>::CreateCallbackNotifier(CDPComNotifierData *)

- ea: `0x180004bf8`
- end: `0x180004df1`
- name: `?CreateCallbackNotifier@?$ServiceCallbackNotifier@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@@AEAAJPEAUCDPComNotifierData@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002af0`
- `0x1800030b8`
- `0x18000bcac`
- `0x18001eaa0`
- `0x180027860`
- `0x180046488`
- `0x1800465d0`
- `0x180046674`

## callees

- `0x180004a58`
- `0x180004a98`
- `0x180004bf8`
- `0x180004df8`
- `0x180006494`
- `0x18002c570`
- `0x18003e1cc`
- `0x180064010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180004d40`
- `msvcp_win!_Mtx_unlock` at `0x180004dd0`
- `msvcp_win!_Mtx_unlock` at `0x180004d40`
- `msvcp_win!_Mtx_unlock` at `0x180004dd0`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180004c82`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180004c82`
- `cdp!CDPCreateCallbackNotifierInternal` at `0x180004c3d`
- `cdp!CDPCreateCallbackNotifierInternal` at `0x180004c3d`

## string_xrefs

- `0x180004ccb`: `onecoreuap\windows\cdp\service\shared\ServiceCallbackNotifier.h`
- `0x180004d61`: `onecoreuap\windows\cdp\service\shared\ServiceCallbackNotifier.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceCallbackNotifier<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>::CreateCallbackNotifier(
        __int64 a1,
        __int64 *a2)
{
  _QWORD *v3; // r14
  int v4; // esi
  __int64 v5; // r8
  __int64 v7; // rsi
  void (__fastcall *v8)(__int64, __int64, _QWORD *); // rbx
  char v9; // al
  _QWORD *v10; // r8
  __int64 v11; // r14
  void (__fastcall *v12)(__int64, __int64, _QWORD *); // rbx
  char v13; // al
  _QWORD *v14; // r8
  __int64 v15; // rax
  int v16; // r8d
  int v17; // [rsp+30h] [rbp-178h] BYREF
  int v18; // [rsp+34h] [rbp-174h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-170h] BYREF
  _QWORD v20[5]; // [rsp+48h] [rbp-160h] BYREF
  _BYTE v21[272]; // [rsp+70h] [rbp-138h] BYREF

  if ( a2 )
  {
    v3 = (_QWORD *)(a1 + 120);
    v19[1] = a1 + 120;
    v19[0] = 0;
    v4 = CDPCreateCallbackNotifierInternal(v19);
    cdp::detail::address_of<ICDPCallbackNotifier>::~address_of<ICDPCallbackNotifier>(v19);
    if ( v4 < 0 )
    {
      cdp::detail::StringFormat(
        v20,
        "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
        v4,
        "onecoreuap\\windows\\cdp\\service\\shared\\ServiceCallbackNotifier.h",
        84);
      v19[0] = &g_loggerMutex;
      std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
      v11 = g_logger;
      if ( g_logger )
      {
        v12 = *(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)g_logger + 24LL);
        v13 = std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v20);
        v14 = v20;
        if ( v13 )
          v14 = (_QWORD *)v20[0];
        v12(v11, 1, v14);
      }
      _Mtx_unlock((_Mtx_t)&g_loggerMutex);
      std::string::_Tidy_deallocate(v20);
      return (unsigned int)v4;
    }
    else
    {
      v17 = 0;
      v21[0] = 0;
      v5 = *a2;
      v21[256] = *((_DWORD *)a2 + 2) != 0;
      if ( v5 )
        _o_strncpy_s(v21, 256, v5, 255);
      try
      {
        (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v3 + 24LL))(*v3, v21);
      }
      catch ( ... )
      {
        LODWORD(v15) = GetCurrentThreadId();
        v19[0] = v15;
        v18 = 92;
        cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(
          (unsigned int)&v17,
          (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"te"
                        "xt\":\"Failed to start callback notifier!\"}",
          v16,
          (unsigned int)&v18,
          (__int64)v19);
      }
      return 0;
    }
  }
  else
  {
    cdp::detail::StringFormat(
      v20,
      "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      -2147024809,
      "onecoreuap\\windows\\cdp\\service\\shared\\ServiceCallbackNotifier.h",
      82);
    v19[0] = &g_loggerMutex;
    std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
    v7 = g_logger;
    if ( g_logger )
    {
      v8 = *(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)g_logger + 24LL);
      v9 = std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v20);
      v10 = v20;
      if ( v9 )
        v10 = (_QWORD *)v20[0];
      v8(v7, 1, v10);
    }
    _Mtx_unlock((_Mtx_t)&g_loggerMutex);
    std::string::_Tidy_deallocate(v20);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180004bf8  mov     [rsp+arg_10], rbx
0x180004bfd  push    rsi
0x180004bfe  push    rdi
0x180004bff  push    r14
0x180004c01  sub     rsp, 190h
0x180004c08  mov     rax, cs:__security_cookie
0x180004c0f  xor     rax, rsp
0x180004c12  mov     [rsp+1A8h+var_28], rax
0x180004c1a  mov     rdi, rdx
0x180004c1d  test    rdx, rdx
0x180004c20  jz      loc_180004CC3
0x180004c26  lea     r14, [rcx+78h]
0x180004c2a  mov     [rsp+1A8h+var_168], r14
0x180004c2f  mov     [rsp+1A8h+var_170], 0
0x180004c38  lea     rcx, [rsp+1A8h+var_170]
0x180004c3d  call    cs:__imp_CDPCreateCallbackNotifierInternal
0x180004c43  mov     esi, eax
0x180004c45  lea     rcx, [rsp+1A8h+var_170]
0x180004c4a  call    ??1?$address_of@VICDPCallbackNotifier@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCallbackNotifier>::~address_of<ICDPCallbackNotifier>(void)
0x180004c4f  test    esi, esi
0x180004c51  js      loc_180004D59
0x180004c57  xor     ebx, ebx
0x180004c59  mov     [rsp+1A8h+var_178], ebx
0x180004c5d  mov     [rsp+1A8h+var_138], bl
0x180004c61  mov     r8, [rdi]
0x180004c64  cmp     [rdi+8], ebx
0x180004c67  setnz   [rsp+1A8h+var_38]
0x180004c6f  test    r8, r8
0x180004c72  jz      short loc_180004C88
0x180004c74  mov     edx, 100h
0x180004c79  lea     r9d, [rdx-1]
0x180004c7d  lea     rcx, [rsp+1A8h+var_138]
0x180004c82  call    cs:__imp__o_strncpy_s
0x180004c88  mov     rcx, [r14]
0x180004c8b  mov     rax, [rcx]
0x180004c8e  lea     rdx, [rsp+1A8h+var_138]
0x180004c93  mov     rax, [rax+18h]
0x180004c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c9c  nop
0x180004c9d  mov     eax, ebx
0x180004c9f  mov     rcx, [rsp+1A8h+var_28]
0x180004ca7  xor     rcx, rsp; StackCookie
0x180004caa  call    __security_check_cookie
0x180004caf  mov     rbx, [rsp+1A8h+arg_10]
0x180004cb7  add     rsp, 190h
0x180004cbe  pop     r14
0x180004cc0  pop     rdi
0x180004cc1  pop     rsi
0x180004cc2  retn
0x180004cc3  mov     [rsp+1A8h+var_188], 52h ; 'R'
0x180004ccb  lea     r9, aOnecoreuapWind; "onecoreuap\\windows\\cdp\\service\\shar"...
0x180004cd2  mov     r14d, 80070057h
0x180004cd8  mov     r8d, r14d
0x180004cdb  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180004ce2  lea     rcx, [rsp+1A8h+var_160]
0x180004ce7  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180004cec  nop
0x180004ced  lea     rdi, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x180004cf4  mov     [rsp+1A8h+var_170], rdi
0x180004cf9  mov     rcx, rdi; this
0x180004cfc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180004d01  nop
0x180004d02  mov     rsi, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180004d09  test    rsi, rsi
0x180004d0c  jz      short loc_180004D3D
0x180004d0e  mov     rax, [rsi]
0x180004d11  mov     rbx, [rax+18h]
0x180004d15  lea     rcx, [rsp+1A8h+var_160]
0x180004d1a  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x180004d1f  lea     r8, [rsp+1A8h+var_160]
0x180004d24  test    al, al
0x180004d26  cmovnz  r8, [rsp+1A8h+var_160]
0x180004d2c  mov     edx, 1
0x180004d31  mov     rcx, rsi
0x180004d34  mov     rax, rbx
0x180004d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3c  nop
0x180004d3d  mov     rcx, rdi; _Mtx_t
0x180004d40  call    cs:__imp__Mtx_unlock
0x180004d46  nop
0x180004d47  lea     rcx, [rsp+1A8h+var_160]
0x180004d4c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180004d51  mov     eax, r14d
0x180004d54  jmp     loc_180004C9F
0x180004d59  mov     [rsp+1A8h+var_188], 54h ; 'T'
0x180004d61  lea     r9, aOnecoreuapWind; "onecoreuap\\windows\\cdp\\service\\shar"...
0x180004d68  mov     r8d, esi
0x180004d6b  lea     rdx, aHr0x08xFileSLi_14; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180004d72  lea     rcx, [rsp+1A8h+var_160]
0x180004d77  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180004d7c  nop
0x180004d7d  lea     rdi, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x180004d84  mov     [rsp+1A8h+var_170], rdi
0x180004d89  mov     rcx, rdi; this
0x180004d8c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180004d91  nop
0x180004d92  mov     r14, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180004d99  test    r14, r14
0x180004d9c  jz      short loc_180004DCD
0x180004d9e  mov     rax, [r14]
0x180004da1  mov     rbx, [rax+18h]
0x180004da5  lea     rcx, [rsp+1A8h+var_160]
0x180004daa  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x180004daf  lea     r8, [rsp+1A8h+var_160]
0x180004db4  test    al, al
0x180004db6  cmovnz  r8, [rsp+1A8h+var_160]
0x180004dbc  mov     edx, 1
0x180004dc1  mov     rcx, r14
0x180004dc4  mov     rax, rbx
0x180004dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dcc  nop
0x180004dcd  mov     rcx, rdi; _Mtx_t
0x180004dd0  call    cs:__imp__Mtx_unlock
0x180004dd6  nop
0x180004dd7  lea     rcx, [rsp+1A8h+var_160]
0x180004ddc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180004de1  mov     eax, esi
0x180004de3  jmp     loc_180004C9F
0x180004de8  mov     ebx, [rsp+1A8h+var_178]
0x180004dec  jmp     loc_180004C9D
```
