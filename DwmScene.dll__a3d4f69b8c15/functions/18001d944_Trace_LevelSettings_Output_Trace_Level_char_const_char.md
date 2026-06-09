# Trace::LevelSettings::Output(Trace::Level,char const *,char *)

- ea: `0x18001d944`
- end: `0x18001daed`
- name: `?Output@LevelSettings@Trace@@QEAAXW4Level@2@PEBDPEAD@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001daf4`

## callees

- `0x18000ca90`
- `0x18000d6fc`
- `0x18000d7a8`
- `0x180011f64`
- `0x180012ba8`
- `0x180014a3c`
- `0x18001d0ac`
- `0x18001d730`
- `0x18001d82c`
- `0x18001d944`
- `0x18001de10`
- `0x1800d1540`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d9c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d9c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001daab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001daab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001dab8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001dab8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Trace::LevelSettings::Output(__int64 a1, int a2)
{
  __int64 v2; // r15
  const char *v4; // r8
  va_list ArgList; // r9
  int v6; // r13d
  int v7; // r14d
  DWORD CurrentThreadId; // esi
  const char *v9; // rdi
  const char *v10; // rbx
  __int64 TimeString; // rax
  const char *v12; // rax
  int v13; // [rsp+40h] [rbp-C0h]
  _BYTE v14[32]; // [rsp+48h] [rbp-B8h] BYREF
  CHAR v15[40]; // [rsp+68h] [rbp-98h] BYREF
  CHAR OutputString[2112]; // [rsp+90h] [rbp-70h] BYREF
  char Buffer[2048]; // [rsp+8D0h] [rbp+7D0h] BYREF

  v2 = a2;
  if ( (int)std::_Atomic_storage<unsigned int,4>::load(&qword_180236C98) <= 0 )
  {
    v6 = *(_DWORD *)(a1 + 8);
    v7 = *(_DWORD *)(a1 + 4);
    v13 = *(_DWORD *)a1;
    vsnprintf_s(Buffer, 0x800u, 0xFFFFFFFFFFFFFFFFuLL, v4, ArgList);
    CurrentThreadId = GetCurrentThreadId();
    std::string::string(v14, *(_QWORD *)(a1 + 16));
    v9 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v14);
    v10 = (&off_18022B0D0)[3 * v2];
    TimeString = anonymous_namespace_::GetTimeString(v15);
    v12 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(TimeString);
    sprintf_s<2112>(OutputString, "[%s][%s][%s][0x%.8x] %s\n", v12, v10, v9, CurrentThreadId, Buffer);
    std::string::_Tidy_deallocate(v15);
    std::string::_Tidy_deallocate(v14);
    if ( (int)v2 >= v7 )
    {
      std::string::string(v15, OutputString);
      std::string::string(v14, *(_QWORD *)(a1 + 16));
      Trace::NotifyHandlers(v14, (unsigned int)v2, v15);
      std::string::_Tidy_deallocate(v14);
      std::string::_Tidy_deallocate(v15);
    }
    if ( (int)v2 >= v6 )
      printf("%s", OutputString);
    OutputDebugStringA(OutputString);
    if ( (int)v2 >= v13 )
    {
      if ( !IsDebuggerPresent() )
        __fastfail(7u);
      __debugbreak();
    }
  }
}

```

## disassembly

```asm
0x18001d944  push    rbp
0x18001d946  push    rbx
0x18001d947  push    rsi
0x18001d948  push    rdi
0x18001d949  push    r12
0x18001d94b  push    r13
0x18001d94d  push    r14
0x18001d94f  push    r15
0x18001d951  lea     rbp, [rsp-0FE8h]
0x18001d959  mov     eax, 10E8h
0x18001d95e  call    _alloca_probe
0x18001d963  sub     rsp, rax
0x18001d966  mov     rax, cs:__security_cookie
0x18001d96d  xor     rax, rsp
0x18001d970  mov     [rbp+1020h+var_50], rax
0x18001d977  movsxd  r15, edx
0x18001d97a  mov     r12, rcx
0x18001d97d  lea     rcx, qword_180236C98
0x18001d984  call    ?load@?$_Atomic_storage@I$03@std@@QEBAIW4memory_order@2@@Z; std::_Atomic_storage<uint,4>::load(std::memory_order)
0x18001d989  test    eax, eax
0x18001d98b  jg      loc_18001DACA
0x18001d991  mov     r13d, [r12+8]
0x18001d996  mov     r14d, [r12+4]
0x18001d99b  mov     eax, [r12]
0x18001d99f  mov     [rsp+1120h+var_10E0], eax
0x18001d9a3  mov     [rsp+1120h+ArgList], r9; ArgList
0x18001d9a8  mov     r9, r8; Format
0x18001d9ab  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001d9af  mov     edx, 800h; BufferCount
0x18001d9b4  lea     rcx, [rbp+1020h+Buffer]; Buffer
0x18001d9bb  call    _vsnprintf_s
0x18001d9c0  call    cs:__imp_GetCurrentThreadId
0x18001d9c6  mov     esi, eax
0x18001d9c8  mov     rdx, [r12+10h]
0x18001d9cd  lea     rcx, [rsp+1120h+var_10D8]
0x18001d9d2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001d9d7  nop
0x18001d9d8  lea     rcx, [rsp+1120h+var_10D8]
0x18001d9dd  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001d9e2  mov     rdi, rax
0x18001d9e5  lea     rdx, [r15+r15*2]
0x18001d9e9  lea     rbx, off_18022B0D0; "N"
0x18001d9f0  mov     rbx, [rbx+rdx*8]
0x18001d9f4  lea     rcx, [rsp+1120h+var_10B8]
0x18001d9f9  call    _anonymous_namespace___GetTimeString
0x18001d9fe  mov     rcx, rax
0x18001da01  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001da06  lea     rcx, [rbp+1020h+Buffer]
0x18001da0d  mov     [rsp+1120h+var_10F0], rcx
0x18001da12  mov     [rsp+1120h+var_10F8], esi
0x18001da16  mov     [rsp+1120h+ArgList], rdi
0x18001da1b  mov     r9, rbx
0x18001da1e  mov     r8, rax
0x18001da21  lea     rdx, aSSS0x8xS; "[%s][%s][%s][0x%.8x] %s\n"
0x18001da28  lea     rcx, [rbp+1020h+OutputString]
0x18001da2c  call    ??$sprintf_s@$0IEA@@@YAHAEAY0IEA@DPEBDZZ; sprintf_s<2112>(char (&)[2112],char const *,...)
0x18001da31  lea     rcx, [rsp+1120h+var_10B8]
0x18001da36  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001da3b  nop
0x18001da3c  lea     rcx, [rsp+1120h+var_10D8]
0x18001da41  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001da46  cmp     r15d, r14d
0x18001da49  jl      short loc_18001DA92
0x18001da4b  lea     rdx, [rbp+1020h+OutputString]
0x18001da4f  lea     rcx, [rsp+1120h+var_10B8]
0x18001da54  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001da59  nop
0x18001da5a  mov     rdx, [r12+10h]
0x18001da5f  lea     rcx, [rsp+1120h+var_10D8]
0x18001da64  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001da69  nop
0x18001da6a  lea     r8, [rsp+1120h+var_10B8]
0x18001da6f  mov     edx, r15d
0x18001da72  lea     rcx, [rsp+1120h+var_10D8]
0x18001da77  call    ?NotifyHandlers@Trace@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@1@0@Z; Trace::NotifyHandlers(std::string const &,Trace::Level,std::string const &)
0x18001da7c  nop
0x18001da7d  lea     rcx, [rsp+1120h+var_10D8]
0x18001da82  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001da87  nop
0x18001da88  lea     rcx, [rsp+1120h+var_10B8]
0x18001da8d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001da92  cmp     r15d, r13d
0x18001da95  jl      short loc_18001DAA7
0x18001da97  lea     rdx, [rbp+1020h+OutputString]
0x18001da9b  lea     rcx, Format; "%s"
0x18001daa2  call    printf
0x18001daa7  lea     rcx, [rbp+1020h+OutputString]; lpOutputString
0x18001daab  call    cs:__imp_OutputDebugStringA
0x18001dab1  cmp     r15d, [rsp+1120h+var_10E0]
0x18001dab6  jl      short loc_18001DACA
0x18001dab8  call    cs:__imp_IsDebuggerPresent
0x18001dabe  test    eax, eax
0x18001dac0  jnz     short loc_18001DAC9
0x18001dac2  lea     ecx, [rax+7]
0x18001dac5  int     29h; Win8: RtlFailFast(ecx)
0x18001dac7  jmp     short loc_18001DACA
0x18001dac9  int     3; Trap to Debugger
0x18001daca  mov     rcx, [rbp+1020h+var_50]
0x18001dad1  xor     rcx, rsp; StackCookie
0x18001dad4  call    __security_check_cookie
0x18001dad9  add     rsp, 10E8h
0x18001dae0  pop     r15
0x18001dae2  pop     r14
0x18001dae4  pop     r13
0x18001dae6  pop     r12
0x18001dae8  pop     rdi
0x18001dae9  pop     rsi
0x18001daea  pop     rbx
0x18001daeb  pop     rbp
0x18001daec  retn
```
