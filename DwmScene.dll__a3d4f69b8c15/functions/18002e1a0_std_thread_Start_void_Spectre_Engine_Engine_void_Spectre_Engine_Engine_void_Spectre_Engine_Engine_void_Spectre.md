# std::thread::_Start<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>(void (Spectre::Engine::Engine::*&&)(void),Spectre::Engine::Engine * &&)

- ea: `0x18002e1a0`
- end: `0x18002e242`
- name: `??$_Start@P8Engine@1Spectre@@EAAXXZPEAV112@@thread@std@@AEAAX$$QEAP8Engine@2Spectre@@EAAXXZ$$QEAPEAV223@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003565c`

## callees

- `0x18001c290`
- `0x18002e1a0`
- `0x1800305b8`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002e23b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18002e23b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002e1ff`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002e1ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>(
        __int64 a1,
        _OWORD *a2,
        _QWORD *a3)
{
  char *v6; // r9
  __int64 v7; // rax
  char *v9; // [rsp+40h] [rbp+8h] BYREF

  v6 = (char *)operator new(0x18u);
  if ( v6 )
  {
    *(_QWORD *)v6 = *a3;
    *(_OWORD *)(v6 + 8) = *a2;
  }
  else
  {
    v6 = 0;
  }
  v9 = v6;
  v7 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>,0,1>);
  *(_QWORD *)a1 = v7;
  if ( !v7 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18002E241LL);
  }
  v9 = 0;
  return std::unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>(&v9);
}

```

## disassembly

```asm
0x18002e1a0  mov     [rsp+arg_8], rbx
0x18002e1a5  mov     [rsp+arg_10], rsi
0x18002e1aa  push    rdi
0x18002e1ab  sub     rsp, 30h
0x18002e1af  mov     rbx, r8
0x18002e1b2  mov     rsi, rdx
0x18002e1b5  mov     rdi, rcx
0x18002e1b8  mov     ecx, 18h; unsigned __int64
0x18002e1bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e1c2  mov     r9, rax
0x18002e1c5  test    rax, rax
0x18002e1c8  jz      short loc_18002E1DB
0x18002e1ca  mov     rax, [rbx]
0x18002e1cd  mov     [r9], rax
0x18002e1d0  movups  xmm0, xmmword ptr [rsi]
0x18002e1d3  movdqu  xmmword ptr [r9+8], xmm0
0x18002e1d9  jmp     short loc_18002E1DE
0x18002e1db  xor     r9d, r9d
0x18002e1de  mov     [rsp+38h+arg_0], r9
0x18002e1e3  lea     rbx, [rdi+8]
0x18002e1e7  mov     [rsp+38h+var_10], rbx
0x18002e1ec  mov     [rsp+38h+var_18], 0
0x18002e1f4  lea     r8, ??$_Invoke@V?$tuple@P8Engine@1Spectre@@EAAXXZPEAV112@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>,0,1>(void *)
0x18002e1fb  xor     edx, edx
0x18002e1fd  xor     ecx, ecx
0x18002e1ff  call    cs:__imp__o__beginthreadex
0x18002e205  mov     [rdi], rax
0x18002e208  test    rax, rax
0x18002e20b  jz      short loc_18002E230
0x18002e20d  mov     [rsp+38h+arg_0], 0
0x18002e216  lea     rcx, [rsp+38h+arg_0]
0x18002e21b  call    ??1?$unique_ptr@V?$tuple@P8Engine@1Spectre@@EAAXXZPEAV112@@std@@U?$default_delete@V?$tuple@P8Engine@1Spectre@@EAAXXZPEAV112@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>::~unique_ptr<std::tuple<void (Spectre::Engine::Engine::*)(void),Spectre::Engine::Engine *>>(void)
0x18002e220  mov     rbx, [rsp+38h+arg_8]
0x18002e225  mov     rsi, [rsp+38h+arg_10]
0x18002e22a  add     rsp, 30h
0x18002e22e  pop     rdi
0x18002e22f  retn
0x18002e230  mov     dword ptr [rbx], 0
0x18002e236  mov     ecx, 6
0x18002e23b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
