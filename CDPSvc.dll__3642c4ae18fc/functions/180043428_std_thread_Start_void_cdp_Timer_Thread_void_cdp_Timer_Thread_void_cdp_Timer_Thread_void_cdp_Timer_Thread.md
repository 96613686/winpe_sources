# std::thread::_Start<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>(void (cdp::Timer::Thread::*&&)(void),cdp::Timer::Thread * &&)

- ea: `0x180043428`
- end: `0x1800434be`
- name: `??$_Start@P8Thread@Timer@cdp@@EAAXXZPEAV123@@thread@std@@AEAAX$$QEAP8Thread@Timer@cdp@@EAAXXZ$$QEAPEAV234@@Z`
- size: `150`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180043654`

## callees

- `0x1800225d0`
- `0x180043428`
- `0x180043980`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800434b7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800434b7`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004347b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004347b`

## pseudocode

```c
__int64 __fastcall std::thread::_Start<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v9; // [rsp+40h] [rbp+8h] BYREF

  v6 = operator new(0x10u);
  *v6 = *a3;
  v6[1] = *a2;
  v9 = v6;
  v7 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>,0,1>,
         v6,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v7;
  if ( !v7 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x1800434BDLL);
  }
  v9 = 0;
  return std::unique_ptr<std::tuple<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>>::~unique_ptr<std::tuple<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>>(&v9);
}

```

## disassembly

```asm
0x180043428  mov     [rsp+arg_8], rbx
0x18004342d  mov     [rsp+arg_10], rsi
0x180043432  push    rdi
0x180043433  sub     rsp, 30h
0x180043437  mov     rbx, r8
0x18004343a  mov     rdi, rdx
0x18004343d  mov     rsi, rcx
0x180043440  mov     ecx, 10h; Size
0x180043445  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004344a  mov     r8, [rbx]
0x18004344d  mov     [rax], r8
0x180043450  mov     rdx, [rdi]
0x180043453  mov     [rax+8], rdx
0x180043457  mov     [rsp+38h+arg_0], rax
0x18004345c  lea     rbx, [rsi+8]
0x180043460  mov     [rsp+38h+var_10], rbx
0x180043465  mov     [rsp+38h+var_18], 0
0x18004346d  mov     r9, rax
0x180043470  lea     r8, ??$_Invoke@V?$tuple@P8Thread@Timer@cdp@@EAAXXZPEAV123@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>,0,1>(void *)
0x180043477  xor     edx, edx
0x180043479  xor     ecx, ecx
0x18004347b  call    cs:__imp__o__beginthreadex
0x180043481  mov     [rsi], rax
0x180043484  test    rax, rax
0x180043487  jz      short loc_1800434AC
0x180043489  mov     [rsp+38h+arg_0], 0
0x180043492  lea     rcx, [rsp+38h+arg_0]
0x180043497  call    ??1?$unique_ptr@V?$tuple@P8Thread@Timer@cdp@@EAAXXZPEAV123@@std@@U?$default_delete@V?$tuple@P8Thread@Timer@cdp@@EAAXXZPEAV123@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>>::~unique_ptr<std::tuple<void (cdp::Timer::Thread::*)(void),cdp::Timer::Thread *>>(void)
0x18004349c  mov     rbx, [rsp+38h+arg_8]
0x1800434a1  mov     rsi, [rsp+38h+arg_10]
0x1800434a6  add     rsp, 30h
0x1800434aa  pop     rdi
0x1800434ab  retn
0x1800434ac  mov     dword ptr [rbx], 0
0x1800434b2  mov     ecx, 6
0x1800434b7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
