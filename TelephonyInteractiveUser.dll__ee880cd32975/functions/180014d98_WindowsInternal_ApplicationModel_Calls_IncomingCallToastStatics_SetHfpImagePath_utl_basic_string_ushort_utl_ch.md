# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_SetHfpImagePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180014d98`
- end: `0x180015016`
- name: `?_SetHfpImagePath@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@IEAAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800130c0`

## callees

- `0x180001dc0`
- `0x1800021b4`
- `0x180004a0c`
- `0x180005a90`
- `0x180011e68`
- `0x180014d98`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014dd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014dcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180014dcf`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x180014e13`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x180014e13`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_SetHfpImagePath(
        __int64 a1,
        __int64 a2)
{
  signed int LastError; // eax
  __int64 v5; // r8
  unsigned int ScaleFactorForMonitor; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v10; // eax
  __int64 v11; // r8
  void *v12; // rcx
  bool v13; // zf
  int v14; // eax
  const wchar_t *v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+4Ah] [rbp-B6h]
  int v23; // [rsp+52h] [rbp-AEh]
  __int16 v24; // [rsp+56h] [rbp-AAh]
  void *v25[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+6Ah] [rbp-96h]
  int v28; // [rsp+72h] [rbp-8Eh]
  __int16 v29; // [rsp+76h] [rbp-8Ah]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !GetSystemWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    ScaleFactorForMonitor = LastError;
    if ( LastError > 0 )
      ScaleFactorForMonitor = (unsigned __int16)LastError | 0x80070000;
    v7 = 0;
    v8 = 215;
    goto LABEL_5;
  }
  v19 = 0;
  ScaleFactorForMonitor = GetScaleFactorForMonitor(0, &v19);
  if ( (ScaleFactorForMonitor & 0x80000000) != 0 )
  {
    v7 = 1;
    v8 = 218;
LABEL_5:
    Log_HREvent_1(ScaleFactorForMonitor, v7, v5, v8);
    return ScaleFactorForMonitor;
  }
  v22 = 0;
  v24 = 0;
  v23 = 0;
  Block[0] = &v21;
  Block[1] = &v21;
  v21 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)a1 + 160LL))(a1, v19, Block);
  ScaleFactorForMonitor = v10;
  if ( v10 < 0 )
  {
    Log_HREvent_1((unsigned int)v10, 1, v11, 221);
LABEL_11:
    v12 = Block[0];
    v13 = Block[0] == &v21;
LABEL_12:
    if ( !v13 )
      operator delete(v12);
    return ScaleFactorForMonitor;
  }
  v27 = 0;
  v29 = 0;
  v28 = 0;
  v25[0] = &v26;
  v25[1] = &v26;
  v26 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 168LL))(a1);
  v15 = L"white";
  if ( !v14 )
    v15 = L"black";
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v25,
                           v15) )
  {
    ScaleFactorForMonitor = -2147024882;
    Log_HREvent_1(2147942414LL, 0, v16, 224);
    if ( v25[0] != &v26 )
      operator delete(v25[0]);
    v12 = Block[0];
    v13 = Block[0] == &v21;
    goto LABEL_12;
  }
  v17 = tlx::append_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          a2,
          L"%s\\SystemResources\\Windows.Systemtoast.Calling\\Images\\YourPhoneCallingToast.scale-%s_contrast-%s.png",
          Buffer,
          Block[0],
          v25[0]);
  ScaleFactorForMonitor = v17;
  if ( v17 < 0 )
  {
    Log_HREvent_1((unsigned int)v17, 1, v18, 227);
    if ( v25[0] != &v26 )
      operator delete(v25[0]);
    goto LABEL_11;
  }
  if ( v25[0] != &v26 )
    operator delete(v25[0]);
  if ( Block[0] != &v21 )
    operator delete(Block[0]);
  return 0;
}

```

## disassembly

```asm
0x180014d98  mov     [rsp-8+arg_10], rbx
0x180014d9d  push    rbp
0x180014d9e  push    rsi
0x180014d9f  push    rdi
0x180014da0  lea     rbp, [rsp-1A0h]
0x180014da8  sub     rsp, 2A0h
0x180014daf  mov     rax, cs:__security_cookie
0x180014db6  xor     rax, rsp
0x180014db9  mov     [rbp+1B0h+var_20], rax
0x180014dc0  mov     rsi, rdx
0x180014dc3  mov     rdi, rcx
0x180014dc6  mov     edx, 104h; uSize
0x180014dcb  lea     rcx, [rbp+1B0h+Buffer]; lpBuffer
0x180014dcf  call    cs:__imp_GetSystemWindowsDirectoryW
0x180014dd5  test    eax, eax
0x180014dd7  jnz     short loc_180014E04
0x180014dd9  call    cs:__imp_GetLastError
0x180014ddf  mov     ebx, eax
0x180014de1  test    eax, eax
0x180014de3  jle     short loc_180014DEE
0x180014de5  movzx   ebx, ax
0x180014de8  or      ebx, 80070000h
0x180014dee  xor     edx, edx
0x180014df0  mov     r9d, 0D7h
0x180014df6  mov     ecx, ebx
0x180014df8  call    Log_HREvent_1
0x180014dfd  mov     eax, ebx
0x180014dff  jmp     loc_180014FF4
0x180014e04  lea     rdx, [rsp+2B0h+var_280]
0x180014e09  mov     [rsp+2B0h+var_280], 0
0x180014e11  xor     ecx, ecx
0x180014e13  call    cs:__imp_GetScaleFactorForMonitor
0x180014e19  mov     ebx, eax
0x180014e1b  test    eax, eax
0x180014e1d  jns     short loc_180014E2C
0x180014e1f  mov     edx, 1
0x180014e24  mov     r9d, 0DAh
0x180014e2a  jmp     short loc_180014DF6
0x180014e2c  mov     edx, [rsp+2B0h+var_280]
0x180014e30  lea     r8, [rsp+2B0h+Block]
0x180014e35  xor     eax, eax
0x180014e37  mov     [rsp+2B0h+var_266], 0
0x180014e40  mov     [rsp+2B0h+var_25A], ax
0x180014e45  mov     rcx, rdi
0x180014e48  lea     rax, [rsp+2B0h+var_268]
0x180014e4d  mov     [rsp+2B0h+var_25E], 0
0x180014e55  mov     [rsp+2B0h+Block], rax
0x180014e5a  lea     rax, [rsp+2B0h+var_268]
0x180014e5f  mov     [rsp+2B0h+var_270], rax
0x180014e64  xor     eax, eax
0x180014e66  mov     [rsp+2B0h+var_268], ax
0x180014e6b  mov     rax, [rdi]
0x180014e6e  mov     rax, [rax+0A0h]
0x180014e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e7a  mov     ebx, eax
0x180014e7c  test    eax, eax
0x180014e7e  jns     short loc_180014EB6
0x180014e80  mov     edx, 1
0x180014e85  mov     r9d, 0DDh
0x180014e8b  mov     ecx, eax
0x180014e8d  call    Log_HREvent_1
0x180014e92  mov     rcx, [rsp+2B0h+Block]; Block
0x180014e97  lea     rax, [rsp+2B0h+var_268]
0x180014e9c  cmp     rcx, rax
0x180014e9f  jz      loc_180014DFD
0x180014ea5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014eac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014eb1  jmp     loc_180014DFD
0x180014eb6  xor     eax, eax
0x180014eb8  mov     [rsp+2B0h+var_246], 0
0x180014ec1  mov     [rsp+2B0h+var_23A], ax
0x180014ec6  mov     rcx, rdi
0x180014ec9  lea     rax, [rsp+2B0h+var_248]
0x180014ece  mov     [rsp+2B0h+var_23E], 0
0x180014ed6  mov     [rsp+2B0h+var_258], rax
0x180014edb  lea     rax, [rsp+2B0h+var_248]
0x180014ee0  mov     [rsp+2B0h+var_250], rax
0x180014ee5  xor     eax, eax
0x180014ee7  mov     [rsp+2B0h+var_248], ax
0x180014eec  mov     rax, [rdi]
0x180014eef  mov     rax, [rax+0A8h]
0x180014ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014efb  test    eax, eax
0x180014efd  lea     rcx, aBlack; "black"
0x180014f04  lea     rdx, aWhite; "white"
0x180014f0b  cmovz   rdx, rcx
0x180014f0f  lea     rcx, [rsp+2B0h+var_258]
0x180014f14  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180014f19  test    al, al
0x180014f1b  jnz     short loc_180014F5E
0x180014f1d  mov     ebx, 8007000Eh
0x180014f22  xor     edx, edx
0x180014f24  mov     ecx, ebx
0x180014f26  mov     r9d, 0E0h
0x180014f2c  call    Log_HREvent_1
0x180014f31  mov     rcx, [rsp+2B0h+var_258]; Block
0x180014f36  lea     rax, [rsp+2B0h+var_248]
0x180014f3b  cmp     rcx, rax
0x180014f3e  jz      short loc_180014F4C
0x180014f40  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014f47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014f4c  mov     rcx, [rsp+2B0h+Block]
0x180014f51  lea     rdx, [rsp+2B0h+var_268]
0x180014f56  cmp     rcx, rdx
0x180014f59  jmp     loc_180014E9F
0x180014f5e  mov     rax, [rsp+2B0h+var_258]
0x180014f63  lea     r8, [rbp+1B0h+Buffer]
0x180014f67  mov     r9, [rsp+2B0h+Block]
0x180014f6c  lea     rdx, aSSystemresourc_0; "%s\\SystemResources\\Windows.Systemtoas"...
0x180014f73  mov     rcx, rsi
0x180014f76  mov     [rsp+2B0h+var_290], rax
0x180014f7b  call    ??$append_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::append_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180014f80  mov     ebx, eax
0x180014f82  test    eax, eax
0x180014f84  jns     short loc_180014FBC
0x180014f86  mov     edx, 1
0x180014f8b  mov     r9d, 0E3h
0x180014f91  mov     ecx, eax
0x180014f93  call    Log_HREvent_1
0x180014f98  mov     rcx, [rsp+2B0h+var_258]; Block
0x180014f9d  lea     rax, [rsp+2B0h+var_248]
0x180014fa2  cmp     rcx, rax
0x180014fa5  jz      loc_180014E92
0x180014fab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014fb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014fb7  jmp     loc_180014E92
0x180014fbc  mov     rcx, [rsp+2B0h+var_258]; Block
0x180014fc1  lea     rax, [rsp+2B0h+var_248]
0x180014fc6  cmp     rcx, rax
0x180014fc9  jz      short loc_180014FD7
0x180014fcb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014fd2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014fd7  mov     rcx, [rsp+2B0h+Block]; Block
0x180014fdc  lea     rax, [rsp+2B0h+var_268]
0x180014fe1  cmp     rcx, rax
0x180014fe4  jz      short loc_180014FF2
0x180014fe6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180014fed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014ff2  xor     eax, eax
0x180014ff4  mov     rcx, [rbp+1B0h+var_20]
0x180014ffb  xor     rcx, rsp; StackCookie
0x180014ffe  call    __security_check_cookie
0x180015003  mov     rbx, [rsp+2B0h+arg_10]
0x18001500b  add     rsp, 2A0h
0x180015012  pop     rdi
0x180015013  pop     rsi
0x180015014  pop     rbp
0x180015015  retn
```
