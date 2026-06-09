# Microsoft::Applications::Experimentation::ExpCommon::RegisterLogger(Microsoft::Applications::Events::ILogger *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x140151300`
- end: `0x1401514a5`
- name: `?RegisterLogger@ExpCommon@Experimentation@Applications@Microsoft@@UEAA_NPEAVILogger@Events@34@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `421`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a5c0`
- `0x14009d4d0`
- `0x1400ff188`
- `0x1401505e4`
- `0x140151300`

## string_xrefs

- `0x140151353`: `RegisterLogger[%d]: this=0x%x, ILogger=0x%x, agent=%s`
- `0x14015135a`: `MATSDK.ExpCommonClient`
- `0x14015140f`: `MATSDK.ExpCommonClient`
- `0x140151460`: `MATSDK.ExpCommonClient`
- `0x140151459`: `RegisterLogger: Either the logger provided is null or the agentname is empty`
- `0x140151408`: `RegisterLogger: Logger provided was registered already`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Microsoft::Applications::Experimentation::ExpCommon::RegisterLogger(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  const char *v6; // rax
  __int64 v7; // r8
  __int64 *v8; // r10
  __int64 *v9; // rcx
  __int64 *v10; // rdx
  __int64 *v11; // rax
  void *v12; // rax
  unsigned __int64 v14; // [rsp+60h] [rbp-28h] BYREF

  v14 = a2;
  v5 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
  {
    v6 = (const char *)a3;
    if ( *(_QWORD *)(a3 + 24) > 0xFu )
      v6 = *(const char **)a3;
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "MATSDK.ExpCommonClient",
      "RegisterLogger[%d]: this=0x%x, ILogger=0x%x, agent=%s",
      154,
      a1,
      a2,
      v6);
    v5 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
    a2 = v14;
  }
  if ( a2 && *(_QWORD *)(a3 + 16) )
  {
    if ( Mtx_lock((_Mtx_t)(a1 + 112)) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(a1 + 188) == 0x7FFFFFFF )
    {
      *(_DWORD *)(a1 + 188) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v8 = *(__int64 **)(a1 + 216);
    v9 = (__int64 *)v8[1];
    v10 = v8;
    if ( !*((_BYTE *)v9 + 25) )
    {
      do
      {
        if ( v9[4] >= v14 )
        {
          v7 = 0;
          v10 = v9;
        }
        else
        {
          LOBYTE(v7) = 1;
        }
        v11 = v9 + 2;
        if ( !(_BYTE)v7 )
          v11 = v9;
        v9 = (__int64 *)*v11;
      }
      while ( !*(_BYTE *)(*v11 + 25) );
    }
    if ( *((_BYTE *)v10 + 25) || v14 < v10[4] || v10 == v8 )
    {
      v12 = (void *)std::map<Microsoft::Applications::Events::ILogger *,std::string>::operator[](
                      a1 + 216,
                      &v14,
                      v7,
                      v14);
      std::string::operator=(v12);
      Mtx_unlock((_Mtx_t)(a1 + 112));
      return 1;
    }
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 1 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        1,
        "MATSDK.ExpCommonClient",
        "RegisterLogger: Logger provided was registered already",
        v14);
    Mtx_unlock((_Mtx_t)(a1 + 112));
  }
  else if ( v5 >= 1 )
  {
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      1,
      "MATSDK.ExpCommonClient",
      "RegisterLogger: Either the logger provided is null or the agentname is empty");
  }
  return 0;
}

```

## disassembly

```asm
0x140151300  push    rbx
0x140151302  push    rsi
0x140151303  push    rdi
0x140151304  sub     rsp, 70h
0x140151308  mov     rax, cs:__security_cookie
0x14015130f  xor     rax, rsp
0x140151312  mov     [rsp+88h+var_20], rax
0x140151317  mov     rdi, r8
0x14015131a  mov     rsi, rcx
0x14015131d  mov     [rsp+88h+var_28], rdx
0x140151322  mov     eax, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140151328  mov     ecx, 4
0x14015132d  cmp     eax, ecx
0x14015132f  jl      short loc_140151371
0x140151331  mov     rax, r8
0x140151334  cmp     qword ptr [r8+18h], 0Fh
0x140151339  jbe     short loc_14015133E
0x14015133b  mov     rax, [r8]
0x14015133e  mov     [rsp+88h+var_58], rax
0x140151343  mov     [rsp+88h+var_60], rdx
0x140151348  mov     [rsp+88h+var_68], rsi
0x14015134d  mov     r9d, 9Ah
0x140151353  lea     r8, aRegisterlogger_1; "RegisterLogger[%d]: this=0x%x, ILogger="...
0x14015135a  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140151361  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140151366  mov     eax, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x14015136c  mov     rdx, [rsp+88h+var_28]
0x140151371  test    rdx, rdx
0x140151374  jz      loc_140151454
0x14015137a  cmp     qword ptr [rdi+10h], 0
0x14015137f  jz      loc_140151454
0x140151385  lea     rbx, [rsi+70h]
0x140151389  mov     [rsp+88h+var_48], rbx
0x14015138e  mov     rcx, rbx; _Mtx_t
0x140151391  call    _Mtx_lock
0x140151396  test    eax, eax
0x140151398  jnz     loc_14015149A
0x14015139e  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1401513a5  jz      loc_140151488
0x1401513ab  mov     r10, [rsi+0D8h]
0x1401513b2  mov     rcx, [r10+8]
0x1401513b6  xor     eax, eax
0x1401513b8  mov     [rsp+88h+var_34], eax
0x1401513bc  mov     rdx, r10
0x1401513bf  mov     r9, [rsp+88h+var_28]
0x1401513c4  cmp     [rcx+19h], al
0x1401513c7  jnz     short loc_1401513EE
0x1401513c9  cmp     [rcx+20h], r9
0x1401513cd  jnb     short loc_1401513D4
0x1401513cf  mov     r8b, 1
0x1401513d2  jmp     short loc_1401513DA
0x1401513d4  xor     r8d, r8d
0x1401513d7  mov     rdx, rcx
0x1401513da  lea     rax, [rcx+10h]
0x1401513de  test    r8b, r8b
0x1401513e1  cmovz   rax, rcx
0x1401513e5  mov     rcx, [rax]
0x1401513e8  cmp     byte ptr [rcx+19h], 0
0x1401513ec  jz      short loc_1401513C9
0x1401513ee  cmp     byte ptr [rdx+19h], 0
0x1401513f2  jnz     short loc_14015142B
0x1401513f4  cmp     r9, [rdx+20h]
0x1401513f8  jb      short loc_14015142B
0x1401513fa  cmp     rdx, r10
0x1401513fd  jz      short loc_14015142B
0x1401513ff  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 1; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140151406  jl      short loc_140151421
0x140151408  lea     r8, aRegisterlogger; "RegisterLogger: Logger provided was reg"...
0x14015140f  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140151416  mov     ecx, 1
0x14015141b  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140151420  nop
0x140151421  mov     rcx, rbx; _Mtx_t
0x140151424  call    _Mtx_unlock
0x140151429  jmp     short loc_140151471
0x14015142b  lea     rdx, [rsp+88h+var_28]
0x140151430  lea     rcx, [rsi+0D8h]
0x140151437  call    ??A?$map@PEAVILogger@Events@Applications@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@PEAVILogger@Events@Applications@Microsoft@@@6@V?$allocator@U?$pair@QEAVILogger@Events@Applications@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@6@@std@@QEAAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEBQEAVILogger@Events@Applications@Microsoft@@@Z; std::map<Microsoft::Applications::Events::ILogger *,std::string>::operator[](Microsoft::Applications::Events::ILogger * const &)
0x14015143c  mov     rcx, rax; void *
0x14015143f  mov     rdx, rdi
0x140151442  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x140151447  nop
0x140151448  mov     rcx, rbx; _Mtx_t
0x14015144b  call    _Mtx_unlock
0x140151450  mov     al, 1
0x140151452  jmp     short loc_140151473
0x140151454  cmp     eax, 1
0x140151457  jl      short loc_140151471
0x140151459  lea     r8, aRegisterlogger_0; "RegisterLogger: Either the logger provi"...
0x140151460  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x140151467  mov     ecx, 1
0x14015146c  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140151471  xor     al, al
0x140151473  mov     rcx, [rsp+88h+var_20]
0x140151478  xor     rcx, rsp; StackCookie
0x14015147b  call    __security_check_cookie
0x140151480  add     rsp, 70h
0x140151484  pop     rdi
0x140151485  pop     rsi
0x140151486  pop     rbx
0x140151487  retn
0x140151488  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x14015148f  mov     ecx, 6; int
0x140151494  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14015149a  mov     ecx, 5; int
0x14015149f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
