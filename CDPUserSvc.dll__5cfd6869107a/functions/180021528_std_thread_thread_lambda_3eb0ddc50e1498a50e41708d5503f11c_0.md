# std::thread::thread__lambda_3eb0ddc50e1498a50e41708d5503f11c__0_

- ea: `0x180021528`
- end: `0x18002159a`
- name: `std::thread::thread__lambda_3eb0ddc50e1498a50e41708d5503f11c__0_`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d288`

## callees

- `0x180021528`
- `0x18002c5a0`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180021593`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180021593`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002156c`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18002156c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::thread__lambda_3eb0ddc50e1498a50e41708d5503f11c__0_(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rax

  v4 = operator new(8u);
  *v4 = *a2;
  v5 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke_std::tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c____0_,
         v4,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v5;
  if ( !v5 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x180021599LL);
  }
  return a1;
}

```

## disassembly

```asm
0x180021528  mov     [rsp+arg_8], rbx
0x18002152d  push    rdi
0x18002152e  sub     rsp, 30h
0x180021532  mov     rbx, rdx
0x180021535  mov     rdi, rcx
0x180021538  mov     ecx, 8; Size
0x18002153d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021542  mov     rdx, [rbx]
0x180021545  mov     [rax], rdx
0x180021548  mov     [rsp+38h+arg_0], rax
0x18002154d  lea     rbx, [rdi+8]
0x180021551  mov     [rsp+38h+var_10], rbx
0x180021556  mov     [rsp+38h+var_18], 0
0x18002155e  mov     r9, rax
0x180021561  lea     r8, std__thread___Invoke_std__tuple__lambda_3eb0ddc50e1498a50e41708d5503f11c____0_
0x180021568  xor     edx, edx
0x18002156a  xor     ecx, ecx
0x18002156c  call    cs:__imp__o__beginthreadex
0x180021572  mov     [rdi], rax
0x180021575  test    rax, rax
0x180021578  jz      short loc_180021588
0x18002157a  mov     rax, rdi
0x18002157d  mov     rbx, [rsp+38h+arg_8]
0x180021582  add     rsp, 30h
0x180021586  pop     rdi
0x180021587  retn
0x180021588  mov     dword ptr [rbx], 0
0x18002158e  mov     ecx, 6
0x180021593  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
