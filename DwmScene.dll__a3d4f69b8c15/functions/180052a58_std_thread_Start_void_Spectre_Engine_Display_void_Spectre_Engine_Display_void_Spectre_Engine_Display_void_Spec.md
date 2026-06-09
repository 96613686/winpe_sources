# std::thread::_Start<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>(void (Spectre::Engine::Display::*&&)(void),Spectre::Engine::Display * &&)

- ea: `0x180052a58`
- end: `0x180052af8`
- name: `??$_Start@P8Display@Engine@Spectre@@EAAXXZPEAV123@@thread@std@@AEAAX$$QEAP8Display@Engine@Spectre@@EAAXXZ$$QEAPEAV234@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180053284`

## callees

- `0x18001c290`
- `0x180052a58`
- `0x180052e08`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052af1`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180052af1`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180052ab5`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180052ab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // r9
  __int64 v8; // rax
  _QWORD *v10; // [rsp+40h] [rbp+8h] BYREF

  v6 = operator new(0x10u);
  v7 = v6;
  if ( v6 )
  {
    *v6 = *a3;
    v6[1] = *a2;
  }
  else
  {
    v7 = 0;
  }
  v10 = v7;
  v8 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>,0,1>);
  *(_QWORD *)a1 = v8;
  if ( !v8 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180052AF7LL);
  }
  v10 = 0;
  return std::unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>(&v10);
}

```

## disassembly

```asm
0x180052a58  mov     [rsp+arg_8], rbx
0x180052a5d  mov     [rsp+arg_10], rsi
0x180052a62  push    rdi
0x180052a63  sub     rsp, 30h
0x180052a67  mov     rbx, r8
0x180052a6a  mov     rsi, rdx
0x180052a6d  mov     rdi, rcx
0x180052a70  mov     ecx, 10h; unsigned __int64
0x180052a75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180052a7a  mov     r9, rax
0x180052a7d  test    rax, rax
0x180052a80  jz      short loc_180052A91
0x180052a82  mov     rax, [rbx]
0x180052a85  mov     [r9], rax
0x180052a88  mov     rax, [rsi]
0x180052a8b  mov     [r9+8], rax
0x180052a8f  jmp     short loc_180052A94
0x180052a91  xor     r9d, r9d
0x180052a94  mov     [rsp+38h+arg_0], r9
0x180052a99  lea     rbx, [rdi+8]
0x180052a9d  mov     [rsp+38h+var_10], rbx
0x180052aa2  mov     [rsp+38h+var_18], 0
0x180052aaa  lea     r8, ??$_Invoke@V?$tuple@P8Display@Engine@Spectre@@EAAXXZPEAV123@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>,0,1>(void *)
0x180052ab1  xor     edx, edx
0x180052ab3  xor     ecx, ecx
0x180052ab5  call    cs:__imp__o__beginthreadex
0x180052abb  mov     [rdi], rax
0x180052abe  test    rax, rax
0x180052ac1  jz      short loc_180052AE6
0x180052ac3  mov     [rsp+38h+arg_0], 0
0x180052acc  lea     rcx, [rsp+38h+arg_0]
0x180052ad1  call    ??1?$unique_ptr@V?$tuple@P8Display@Engine@Spectre@@EAAXXZPEAV123@@std@@U?$default_delete@V?$tuple@P8Display@Engine@Spectre@@EAAXXZPEAV123@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Display::*)(void),Spectre::Engine::Display *>>(void)
0x180052ad6  mov     rbx, [rsp+38h+arg_8]
0x180052adb  mov     rsi, [rsp+38h+arg_10]
0x180052ae0  add     rsp, 30h
0x180052ae4  pop     rdi
0x180052ae5  retn
0x180052ae6  mov     dword ptr [rbx], 0
0x180052aec  mov     ecx, 6
0x180052af1  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
