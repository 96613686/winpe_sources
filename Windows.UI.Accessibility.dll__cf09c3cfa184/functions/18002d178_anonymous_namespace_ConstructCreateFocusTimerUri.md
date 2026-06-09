# _anonymous_namespace_::ConstructCreateFocusTimerUri

- ea: `0x18002d178`
- end: `0x18002d2aa`
- name: `_anonymous_namespace_::ConstructCreateFocusTimerUri`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002d9e4`

## callees

- `0x18000841c`
- `0x1800126e4`
- `0x180024718`
- `0x18002c670`
- `0x18002c698`
- `0x18002cc9c`
- `0x18002ccc8`
- `0x18002d01c`
- `0x18002d178`
- `0x18002e2a0`
- `0x18002e30c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_round` at `0x18002d1dd`
- `api-ms-win-crt-private-l1-1-0!_o_round` at `0x18002d1dd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18002d263`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18002d27e`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18002d263`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18002d27e`

## string_xrefs

- `0x18002d24c`: `ms-clock://createfocustimer?skipBreaks=false&displayMode=aot&force=false&endTime=`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::ConstructCreateFocusTimerUri(__int64 a1, _QWORD *a2)
{
  double v4; // xmm0_8
  unsigned __int64 v5; // rax
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _BYTE v14[264]; // [rsp+30h] [rbp-108h] BYREF
  __int64 v15; // [rsp+148h] [rbp+10h] BYREF
  char v16; // [rsp+150h] [rbp+18h] BYREF
  char v17; // [rsp+158h] [rbp+20h] BYREF

  if ( *a2 == 0x7FFFFFFFFFFFFFFFLL )
  {
    std::wstring::wstring(a1, L"ms-clock://focustimer");
  }
  else
  {
    v15 = *a2 - *(_QWORD *)winrt::clock::now(&v16);
    std::chrono::duration<double,std::ratio<60,1>>::duration<double,std::ratio<60,1>>(&v17, &v15);
    v4 = _o_round();
    v5 = 0;
    if ( v4 >= 9.223372036854776e18 )
    {
      v4 = v4 - 9.223372036854776e18;
      if ( v4 < 9.223372036854776e18 )
        v5 = 0x8000000000000000uLL;
    }
    v6 = v5 + (unsigned int)(int)v4;
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v14);
    v7 = winrt::clock::to_sys<std::chrono::duration<__int64,std::ratio<1,10000000>>>(&v15, a2);
    v8 = wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(
           &v16,
           v7);
    v9 = 1000 * std::chrono::system_clock::to_time_t(v8);
    v10 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v14,
            L"ms-clock://createfocustimer?skipBreaks=false&displayMode=aot&force=false&endTime=");
    v11 = std::basic_ostream<unsigned short>::operator<<(v10, v9);
    v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L"&duration=");
    std::basic_ostream<unsigned short>::operator<<(v12, v6);
    std::basic_ostringstream<unsigned short>::str(v14, a1);
    std::basic_ostringstream<unsigned short>::`vbase destructor'(v14);
  }
  return a1;
}

```

## disassembly

```asm
0x18002d178  push    rbx
0x18002d17a  push    rsi
0x18002d17b  push    rdi
0x18002d17c  sub     rsp, 120h
0x18002d183  mov     rbx, rdx
0x18002d186  mov     rsi, rcx
0x18002d189  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002d193  cmp     [rdx], rax
0x18002d196  jnz     short loc_18002D1A9
0x18002d198  lea     rdx, aMsClockFocusti; "ms-clock://focustimer"
0x18002d19f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002d1a4  jmp     loc_18002D29C
0x18002d1a9  lea     rcx, [rsp+138h+arg_10]
0x18002d1b1  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x18002d1b6  mov     rcx, [rbx]
0x18002d1b9  sub     rcx, [rax]
0x18002d1bc  mov     [rsp+138h+arg_8], rcx
0x18002d1c4  lea     rdx, [rsp+138h+arg_8]
0x18002d1cc  lea     rcx, [rsp+138h+arg_18]
0x18002d1d4  call    ??$?0_JU?$ratio@$00$0JIJGIA@@std@@$0A@@?$duration@NU?$ratio@$0DM@$00@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@@Z; std::chrono::duration<double,std::ratio<60,1>>::duration<double,std::ratio<60,1>>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18002d1d9  movsd   xmm0, qword ptr [rax]
0x18002d1dd  call    cs:__imp__o_round
0x18002d1e3  xor     eax, eax
0x18002d1e5  movsd   xmm1, cs:__real@43e0000000000000
0x18002d1ed  comisd  xmm0, xmm1
0x18002d1f1  jb      short loc_18002D20A
0x18002d1f3  subsd   xmm0, xmm1
0x18002d1f7  comisd  xmm0, xmm1
0x18002d1fb  jnb     short loc_18002D20A
0x18002d1fd  mov     rcx, 8000000000000000h
0x18002d207  mov     rax, rcx
0x18002d20a  cvttsd2si rdi, xmm0
0x18002d20f  add     rdi, rax
0x18002d212  lea     rcx, [rsp+138h+var_108]
0x18002d217  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002d21c  nop
0x18002d21d  mov     rdx, rbx
0x18002d220  lea     rcx, [rsp+138h+arg_8]
0x18002d228  call    ??$to_sys@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@clock@winrt@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@34@@Z; winrt::clock::to_sys<std::chrono::duration<__int64,std::ratio<1,10000000>>>(std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18002d22d  mov     rdx, rax
0x18002d230  lea     rcx, [rsp+138h+arg_10]
0x18002d238  call    ??$?0PEAXUprocess_heap_deleter@wil@@@?$__compressed_pair@PEAXUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAPEAX$$QEAUprocess_heap_deleter@wil@@@Z; wistd::__compressed_pair<void *,wil::process_heap_deleter>::__compressed_pair<void *,wil::process_heap_deleter>(void * &&,wil::process_heap_deleter &&)
0x18002d23d  mov     rcx, rax
0x18002d240  call    ?to_time_t@system_clock@chrono@std@@SA_JAEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@23@@Z; std::chrono::system_clock::to_time_t(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18002d245  imul    rbx, rax, 3E8h
0x18002d24c  lea     rdx, aMsClockCreatef; "ms-clock://createfocustimer?skipBreaks="...
0x18002d253  lea     rcx, [rsp+138h+var_108]
0x18002d258  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d25d  mov     rdx, rbx
0x18002d260  mov     rcx, rax
0x18002d263  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x18002d269  lea     rdx, aDuration; "&duration="
0x18002d270  mov     rcx, rax
0x18002d273  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18002d278  mov     rdx, rdi
0x18002d27b  mov     rcx, rax
0x18002d27e  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x18002d284  mov     rdx, rsi
0x18002d287  lea     rcx, [rsp+138h+var_108]
0x18002d28c  call    ?str@?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_ostringstream<ushort>::str(void)
0x18002d291  nop
0x18002d292  lea     rcx, [rsp+138h+var_108]
0x18002d297  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18002d29c  mov     rax, rsi
0x18002d29f  add     rsp, 120h
0x18002d2a6  pop     rdi
0x18002d2a7  pop     rsi
0x18002d2a8  pop     rbx
0x18002d2a9  retn
```
