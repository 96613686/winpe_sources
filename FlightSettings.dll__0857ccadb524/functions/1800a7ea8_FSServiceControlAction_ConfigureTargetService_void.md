# FSServiceControlAction::ConfigureTargetService(void)

- ea: `0x1800a7ea8`
- end: `0x1800a81d7`
- name: `?ConfigureTargetService@FSServiceControlAction@@AEAAJXZ`
- size: `815`
- prototype: `__int64 __fastcall(FSServiceControlAction *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a8560`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001d244`
- `0x18001ec78`
- `0x1800a7ea8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800a7edd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800a8056`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800a7edd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800a8056`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800a8198`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800a8198`

## string_xrefs

- `0x1800a808b`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicecontrolaction.cpp`
- `0x1800a81a6`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsservicecontrolaction.cpp`

## pseudocode

```c
__int64 __fastcall FSServiceControlAction::ConfigureTargetService(FSServiceControlAction *this)
{
  wchar_t *v2; // rcx
  DWORD v3; // r14d
  wchar_t *v4; // rsi
  DWORD v5; // edi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  const char *v12; // r9
  int lpBinaryPathName; // [rsp+20h] [rbp-60h]
  _QWORD v14[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  wchar_t *Context; // [rsp+B0h] [rbp+30h] BYREF

  v2 = (wchar_t *)*((_QWORD *)this + 13);
  v3 = 0;
  Context = 0;
  v4 = wcstok_s(v2, L"|", &Context);
  v5 = 1;
  while ( v4 )
  {
    memset(v14, 0, 24);
    v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v14, v4, -1);
    v7 = v6;
    if ( v6 < 0 )
    {
      v10 = (unsigned int)v6;
      v9 = 189;
      goto LABEL_25;
    }
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         v14,
                         L"own",
                         -1) == 2 )
    {
      v8 = 16;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"share",
                              -1) == 2 )
    {
      v8 = 32;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"interact",
                              -1) == 2 )
    {
      v8 = 256;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"kernel",
                              -1) == 2 )
    {
      v8 = 1;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"filesys",
                              -1) == 2 )
    {
      v8 = 2;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"rec",
                              -1) == 2 )
    {
      v8 = 8;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"adapt",
                              -1) == 2 )
    {
      v8 = 4;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              v14,
                              L"userown",
                              -1) == 2 )
    {
      v8 = 80;
    }
    else
    {
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           v14,
                           L"usershare",
                           -1) != 2 )
      {
        v7 = -2146698740;
        v9 = 228;
        v10 = 2148268556LL;
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
          (const char *)v10,
          lpBinaryPathName);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v14);
        return v7;
      }
      v8 = 96;
    }
    v4 = wcstok_s(0, L"|", &Context);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v14);
    v3 |= v8;
  }
  if ( !v3 )
    v3 = -1;
  if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                       (char *)this + 128,
                       L"boot",
                       -1) == 2 )
  {
    v5 = 0;
  }
  else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                            (char *)this + 128,
                            L"system",
                            -1) != 2 )
  {
    if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                         (char *)this + 128,
                         L"auto",
                         -1) == 2 )
    {
      v5 = 2;
    }
    else if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                              (char *)this + 128,
                              L"demand",
                              -1) == 2 )
    {
      v5 = 3;
    }
    else
    {
      v5 = -1;
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinalIgnoreCase(
                           (char *)this + 128,
                           L"disabled",
                           -1) == 2 )
        v5 = 4;
    }
  }
  if ( ChangeServiceConfigW(*((SC_HANDLE *)this + 19), v3, v5, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x10F,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsservicecontrolaction.cpp",
             v12);
}

```

## disassembly

```asm
0x1800a7ea8  mov     [rsp-28h+arg_8], rbx
0x1800a7ead  mov     [rsp-28h+arg_10], rsi
0x1800a7eb2  push    rbp
0x1800a7eb3  push    rdi
0x1800a7eb4  push    r13
0x1800a7eb6  push    r14
0x1800a7eb8  push    r15
0x1800a7eba  mov     rbp, rsp
0x1800a7ebd  sub     rsp, 80h
0x1800a7ec4  mov     r15, rcx
0x1800a7ec7  lea     r8, [rbp+Context]; Context
0x1800a7ecb  mov     rcx, [rcx+68h]; String
0x1800a7ecf  lea     rdx, asc_1800E2098; "|"
0x1800a7ed6  xor     r14d, r14d
0x1800a7ed9  mov     [rbp+Context], r14
0x1800a7edd  call    cs:__imp_wcstok_s
0x1800a7ee3  mov     rsi, rax
0x1800a7ee6  lea     edi, [r14+1]
0x1800a7eea  lea     r13d, [r14+2]
0x1800a7eee  test    rsi, rsi
0x1800a7ef1  jz      loc_1800A80A7
0x1800a7ef7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a7efb  mov     [rbp+var_20], 0
0x1800a7f03  mov     rdx, rsi
0x1800a7f06  mov     [rbp+var_18], 0
0x1800a7f0e  lea     rcx, [rbp+var_20]
0x1800a7f12  mov     [rbp+var_10], 0
0x1800a7f1a  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800a7f1f  mov     ebx, eax
0x1800a7f21  test    eax, eax
0x1800a7f23  js      loc_1800A807F
0x1800a7f29  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800a7f2d  lea     rdx, aOwn; "own"
0x1800a7f34  mov     r8, rbx
0x1800a7f37  lea     rcx, [rbp+var_20]
0x1800a7f3b  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a7f40  cmp     eax, r13d
0x1800a7f43  jnz     short loc_1800A7F4F
0x1800a7f45  mov     ebx, 10h
0x1800a7f4a  jmp     loc_1800A8049
0x1800a7f4f  mov     r8, rbx
0x1800a7f52  lea     rdx, aShare; "share"
0x1800a7f59  lea     rcx, [rbp+var_20]
0x1800a7f5d  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a7f62  cmp     eax, r13d
0x1800a7f65  jnz     short loc_1800A7F71
0x1800a7f67  mov     ebx, 20h ; ' '
0x1800a7f6c  jmp     loc_1800A8049
0x1800a7f71  mov     r8, rbx
0x1800a7f74  lea     rdx, aInteract; "interact"
0x1800a7f7b  lea     rcx, [rbp+var_20]
0x1800a7f7f  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a7f84  cmp     eax, r13d
0x1800a7f87  jnz     short loc_1800A7F93
0x1800a7f89  mov     ebx, 100h
0x1800a7f8e  jmp     loc_1800A8049
0x1800a7f93  mov     r8, rbx
0x1800a7f96  lea     rdx, aKernel; "kernel"
0x1800a7f9d  lea     rcx, [rbp+var_20]
0x1800a7fa1  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a7fa6  cmp     eax, r13d
0x1800a7fa9  jnz     short loc_1800A7FB2
0x1800a7fab  mov     ebx, edi
0x1800a7fad  jmp     loc_1800A8049
0x1800a7fb2  mov     r8, rbx
0x1800a7fb5  lea     rdx, aFilesys; "filesys"
0x1800a7fbc  lea     rcx, [rbp+var_20]
0x1800a7fc0  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a7fc5  cmp     eax, r13d
0x1800a7fc8  jnz     short loc_1800A7FCF
0x1800a7fca  mov     ebx, r13d
0x1800a7fcd  jmp     short loc_1800A8049
0x1800a7fcf  mov     r8, rbx
0x1800a7fd2  lea     rdx, aRec; "rec"
0x1800a7fd9  lea     rcx, [rbp+var_20]
0x1800a7fdd  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a7fe2  cmp     eax, r13d
0x1800a7fe5  jnz     short loc_1800A7FEE
0x1800a7fe7  mov     ebx, 8
0x1800a7fec  jmp     short loc_1800A8049
0x1800a7fee  mov     r8, rbx
0x1800a7ff1  lea     rdx, aAdapt; "adapt"
0x1800a7ff8  lea     rcx, [rbp+var_20]
0x1800a7ffc  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a8001  cmp     eax, r13d
0x1800a8004  jnz     short loc_1800A800D
0x1800a8006  mov     ebx, 4
0x1800a800b  jmp     short loc_1800A8049
0x1800a800d  mov     r8, rbx
0x1800a8010  lea     rdx, aUserown; "userown"
0x1800a8017  lea     rcx, [rbp+var_20]
0x1800a801b  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a8020  cmp     eax, r13d
0x1800a8023  jnz     short loc_1800A802C
0x1800a8025  mov     ebx, 50h ; 'P'
0x1800a802a  jmp     short loc_1800A8049
0x1800a802c  mov     r8, rbx
0x1800a802f  lea     rdx, aUsershare; "usershare"
0x1800a8036  lea     rcx, [rbp+var_20]
0x1800a803a  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a803f  cmp     eax, r13d
0x1800a8042  jnz     short loc_1800A8070
0x1800a8044  mov     ebx, 60h ; '`'
0x1800a8049  lea     r8, [rbp+Context]; Context
0x1800a804d  xor     ecx, ecx; String
0x1800a804f  lea     rdx, asc_1800E2098; "|"
0x1800a8056  call    cs:__imp_wcstok_s
0x1800a805c  lea     rcx, [rbp+var_20]
0x1800a8060  mov     rsi, rax
0x1800a8063  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a8068  or      r14d, ebx
0x1800a806b  jmp     loc_1800A7EEE
0x1800a8070  mov     ebx, 800BFA0Ch
0x1800a8075  mov     edx, 0E4h
0x1800a807a  mov     r9d, ebx
0x1800a807d  jmp     short loc_1800A8087
0x1800a807f  mov     r9d, eax; char *
0x1800a8082  mov     edx, 0BDh; void *
0x1800a8087  mov     rcx, [rbp+28h]; this
0x1800a808b  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\flightsetting"...
0x1800a8092  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8097  lea     rcx, [rbp+var_20]
0x1800a809b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a80a0  mov     eax, ebx
0x1800a80a2  jmp     loc_1800A81BB
0x1800a80a7  or      eax, 0FFFFFFFFh
0x1800a80aa  lea     rbx, [r15+80h]
0x1800a80b1  test    r14d, r14d
0x1800a80b4  lea     rdx, aBoot; "boot"
0x1800a80bb  mov     rcx, rbx
0x1800a80be  cmovz   r14d, eax
0x1800a80c2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a80c6  mov     r8, rsi
0x1800a80c9  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a80ce  cmp     eax, r13d
0x1800a80d1  jnz     short loc_1800A80D7
0x1800a80d3  xor     edi, edi
0x1800a80d5  jmp     short loc_1800A8148
0x1800a80d7  mov     r8, rsi
0x1800a80da  lea     rdx, aSystem_0; "system"
0x1800a80e1  mov     rcx, rbx
0x1800a80e4  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a80e9  cmp     eax, r13d
0x1800a80ec  jz      short loc_1800A8148
0x1800a80ee  mov     r8, rsi
0x1800a80f1  lea     rdx, aAuto; "auto"
0x1800a80f8  mov     rcx, rbx
0x1800a80fb  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a8100  cmp     eax, r13d
0x1800a8103  jnz     short loc_1800A810A
0x1800a8105  mov     edi, r13d
0x1800a8108  jmp     short loc_1800A8148
0x1800a810a  mov     r8, rsi
0x1800a810d  lea     rdx, aDemand; "demand"
0x1800a8114  mov     rcx, rbx
0x1800a8117  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a811c  cmp     eax, r13d
0x1800a811f  jnz     short loc_1800A8128
0x1800a8121  mov     edi, 3
0x1800a8126  jmp     short loc_1800A8148
0x1800a8128  mov     r8, rsi
0x1800a812b  lea     rdx, aDisabled_0; "disabled"
0x1800a8132  mov     rcx, rbx
0x1800a8135  or      edi, 0FFFFFFFFh
0x1800a8138  call    ?CompareOrdinalIgnoreCase@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinalIgnoreCase(ushort const *,unsigned __int64)
0x1800a813d  cmp     eax, r13d
0x1800a8140  mov     eax, 4
0x1800a8145  cmovz   edi, eax
0x1800a8148  mov     rcx, [r15+98h]; hService
0x1800a814f  or      r9d, 0FFFFFFFFh; dwErrorControl
0x1800a8153  mov     [rsp+80h+lpDisplayName], 0; lpDisplayName
0x1800a815c  mov     r8d, edi; dwStartType
0x1800a815f  mov     [rsp+80h+lpPassword], 0; lpPassword
0x1800a8168  mov     edx, r14d; dwServiceType
0x1800a816b  mov     [rsp+80h+lpServiceStartName], 0; lpServiceStartName
0x1800a8174  mov     [rsp+80h+lpDependencies], 0; lpDependencies
0x1800a817d  mov     [rsp+80h+lpdwTagId], 0; lpdwTagId
0x1800a8186  mov     [rsp+80h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1800a818f  mov     [rsp+80h+lpBinaryPathName], 0; lpBinaryPathName
0x1800a8198  call    cs:__imp_ChangeServiceConfigW
0x1800a819e  test    eax, eax
0x1800a81a0  jnz     short loc_1800A81B9
0x1800a81a2  mov     rcx, [rbp+28h]; this
0x1800a81a6  lea     r8, aOnecoreBaseFli_32; "onecore\\base\\flighting\\flightsetting"...
0x1800a81ad  mov     edx, 10Fh; void *
0x1800a81b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a81b7  jmp     short loc_1800A81BB
0x1800a81b9  xor     eax, eax
0x1800a81bb  lea     r11, [rsp+80h+var_s0]
0x1800a81c3  mov     rbx, [r11+38h]
0x1800a81c7  mov     rsi, [r11+40h]
0x1800a81cb  mov     rsp, r11
0x1800a81ce  pop     r15
0x1800a81d0  pop     r14
0x1800a81d2  pop     r13
0x1800a81d4  pop     rdi
0x1800a81d5  pop     rbp
0x1800a81d6  retn
```
