# Microsoft::Applications::Events::PlatformAbstraction::detail::log_init(bool,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1400ff300`
- end: `0x1400ff4a8`
- name: `?log_init@detail@PlatformAbstraction@Events@Applications@Microsoft@@YA_N_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400feeb8`

## callees

- `0x14001cd4c`
- `0x14001cd94`
- `0x14001cdc0`
- `0x14003a0f4`
- `0x140084a18`
- `0x140084b3c`
- `0x14009d4d0`
- `0x1400fd370`
- `0x1400fe440`
- `0x1400ff300`
- `0x1400ff4a8`
- `0x140166250`
- `0x140166990`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400ff379`
- `KERNEL32!GetCurrentProcessId` at `0x1400ff379`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Microsoft::Applications::Events::PlatformAbstraction::detail::log_init(char a1)
{
  char v2; // di
  __int64 *v3; // rsi
  DWORD CurrentProcessId; // eax
  __int64 v5; // rax
  __int64 v6; // rdx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void *v8; // [rsp+20h] [rbp-38h]
  _BYTE v9[48]; // [rsp+28h] [rbp-30h] BYREF

  if ( !a1 )
    return 0;
  v2 = 1;
  if ( !Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream )
  {
    if ( Mtx_lock((_Mtx_t)&Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogMutex) )
      std::_Throw_Cpp_error(5);
    if ( dword_1401D9A2C == 0x7FFFFFFF )
    {
      dword_1401D9A2C = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v3 = &Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath;
    std::string::operator=(&Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath);
    std::string::append(&Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath);
    CurrentProcessId = GetCurrentProcessId();
    std::to_string(v9, CurrentProcessId);
    std::string::append(&Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath);
    std::string::_Tidy_deallocate(v9);
    std::string::append(&Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath);
    v8 = operator new(0x118u);
    memset(v8, 0, 0x118u);
    v5 = std::fstream::fstream(v8);
    v6 = Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream;
    Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream = v5;
    if ( v6 )
    {
      v7 = (void (__fastcall ***)(_QWORD, __int64))(v6 + *(int *)(*(_QWORD *)v6 + 4LL));
      (**v7)(v7, 1);
      v5 = Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream;
    }
    if ( (unsigned __int64)qword_1401D99D8 > 0xF )
      v3 = (__int64 *)Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath;
    std::fstream::open(v5, v3, 2);
    if ( !*(_QWORD *)(Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream + 152) )
    {
      std::fstream::open(Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream, "NUL", 3);
      v2 = 0;
    }
    Mtx_unlock((_Mtx_t)&Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogMutex);
  }
  return v2;
}

```

## disassembly

```asm
0x1400ff300  mov     [rsp+arg_0], rbx
0x1400ff305  mov     [rsp+arg_10], rsi
0x1400ff30a  push    rdi
0x1400ff30b  sub     rsp, 50h
0x1400ff30f  mov     rbx, rdx
0x1400ff312  test    cl, cl
0x1400ff314  jnz     short loc_1400FF31D
0x1400ff316  xor     al, al
0x1400ff318  jmp     loc_1400FF478
0x1400ff31d  mov     edi, 1
0x1400ff322  cmp     cs:?debugLogStream@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$unique_ptr@V?$basic_fstream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_fstream@DU?$char_traits@D@std@@@std@@@2@@std@@A, 0; std::unique_ptr<std::fstream> Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream
0x1400ff32a  jnz     loc_1400FF475
0x1400ff330  lea     rcx, ?debugLogMutex@detail@PlatformAbstraction@Events@Applications@Microsoft@@3Vrecursive_mutex@std@@A; _Mtx_t
0x1400ff337  call    _Mtx_lock
0x1400ff33c  test    eax, eax
0x1400ff33e  jnz     loc_1400FF49D
0x1400ff344  cmp     cs:dword_1401D9A2C, 7FFFFFFFh
0x1400ff34e  jz      loc_1400FF488
0x1400ff354  mov     rdx, rbx
0x1400ff357  lea     rsi, ?debugLogPath@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath
0x1400ff35e  mov     rcx, rsi; void *
0x1400ff361  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1400ff366  lea     r8d, [rdi+9]
0x1400ff36a  lea     rdx, aMatDebug; "mat-debug-"
0x1400ff371  mov     rcx, rsi; Src
0x1400ff374  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1400ff379  call    cs:__imp_GetCurrentProcessId
0x1400ff37f  mov     edx, eax
0x1400ff381  lea     rcx, [rsp+58h+var_30]
0x1400ff386  call    ?to_string@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@J@Z; std::to_string(long)
0x1400ff38b  nop
0x1400ff38c  mov     r8, [rax+10h]
0x1400ff390  cmp     qword ptr [rax+18h], 0Fh
0x1400ff395  jbe     short loc_1400FF39A
0x1400ff397  mov     rax, [rax]
0x1400ff39a  mov     rdx, rax
0x1400ff39d  mov     rcx, rsi; Src
0x1400ff3a0  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1400ff3a5  nop
0x1400ff3a6  lea     rcx, [rsp+58h+var_30]
0x1400ff3ab  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1400ff3b0  mov     r8d, 4
0x1400ff3b6  lea     rdx, aLog; ".log"
0x1400ff3bd  mov     rcx, rsi; Src
0x1400ff3c0  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x1400ff3c5  mov     ecx, 118h; Size
0x1400ff3ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400ff3cf  mov     rbx, rax
0x1400ff3d2  mov     [rsp+58h+var_38], rax
0x1400ff3d7  xor     edx, edx; Val
0x1400ff3d9  mov     r8d, 118h; Size
0x1400ff3df  mov     rcx, rax; void *
0x1400ff3e2  call    memset
0x1400ff3e7  mov     rcx, rbx
0x1400ff3ea  call    ??0?$basic_fstream@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::fstream::fstream(void)
0x1400ff3ef  nop
0x1400ff3f0  mov     rdx, cs:?debugLogStream@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$unique_ptr@V?$basic_fstream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_fstream@DU?$char_traits@D@std@@@std@@@2@@std@@A; std::unique_ptr<std::fstream> Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream
0x1400ff3f7  mov     cs:?debugLogStream@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$unique_ptr@V?$basic_fstream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_fstream@DU?$char_traits@D@std@@@std@@@2@@std@@A, rax; std::unique_ptr<std::fstream> Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream
0x1400ff3fe  test    rdx, rdx
0x1400ff401  jz      short loc_1400FF422
0x1400ff403  mov     rax, [rdx]
0x1400ff406  movsxd  rcx, dword ptr [rax+4]
0x1400ff40a  add     rcx, rdx
0x1400ff40d  mov     rax, [rcx]
0x1400ff410  mov     edx, edi
0x1400ff412  mov     rax, [rax]
0x1400ff415  call    cs:__guard_dispatch_icall_fptr
0x1400ff41b  mov     rax, cs:?debugLogStream@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$unique_ptr@V?$basic_fstream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_fstream@DU?$char_traits@D@std@@@std@@@2@@std@@A; std::unique_ptr<std::fstream> Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream
0x1400ff422  cmp     cs:qword_1401D99D8, 0Fh
0x1400ff42a  cmova   rsi, cs:?debugLogPath@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogPath
0x1400ff432  mov     r8d, 2
0x1400ff438  mov     rdx, rsi
0x1400ff43b  mov     rcx, rax
0x1400ff43e  call    ?open@?$basic_fstream@DU?$char_traits@D@std@@@std@@QEAAXPEBDHH@Z; std::fstream::open(char const *,int,int)
0x1400ff443  mov     rcx, cs:?debugLogStream@detail@PlatformAbstraction@Events@Applications@Microsoft@@3V?$unique_ptr@V?$basic_fstream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_fstream@DU?$char_traits@D@std@@@std@@@2@@std@@A; std::unique_ptr<std::fstream> Microsoft::Applications::Events::PlatformAbstraction::detail::debugLogStream
0x1400ff44a  cmp     qword ptr [rcx+98h], 0
0x1400ff452  jnz     short loc_1400FF469
0x1400ff454  mov     r8d, 3
0x1400ff45a  lea     rdx, aNul; "NUL"
0x1400ff461  call    ?open@?$basic_fstream@DU?$char_traits@D@std@@@std@@QEAAXPEBDHH@Z; std::fstream::open(char const *,int,int)
0x1400ff466  xor     dil, dil
0x1400ff469  lea     rcx, ?debugLogMutex@detail@PlatformAbstraction@Events@Applications@Microsoft@@3Vrecursive_mutex@std@@A; _Mtx_t
0x1400ff470  call    _Mtx_unlock
0x1400ff475  mov     al, dil
0x1400ff478  mov     rbx, [rsp+58h+arg_0]
0x1400ff47d  mov     rsi, [rsp+58h+arg_10]
0x1400ff482  add     rsp, 50h
0x1400ff486  pop     rdi
0x1400ff487  retn
0x1400ff488  mov     cs:dword_1401D9A2C, 7FFFFFFEh
0x1400ff492  mov     ecx, 6; int
0x1400ff497  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1400ff49d  mov     ecx, 5; int
0x1400ff4a2  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
