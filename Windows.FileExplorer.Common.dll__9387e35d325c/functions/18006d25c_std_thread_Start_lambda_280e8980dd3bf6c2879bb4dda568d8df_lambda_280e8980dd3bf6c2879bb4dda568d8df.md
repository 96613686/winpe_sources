# std::thread::_Start<_lambda_280e8980dd3bf6c2879bb4dda568d8df_,>(_lambda_280e8980dd3bf6c2879bb4dda568d8df_ &&)

- ea: `0x18006d25c`
- end: `0x18006d302`
- name: `??$_Start@V_lambda_280e8980dd3bf6c2879bb4dda568d8df_@@$$V@thread@std@@AEAAX$$QEAV_lambda_280e8980dd3bf6c2879bb4dda568d8df_@@@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180033d6c`

## callees

- `0x180026f4c`
- `0x180037c5c`
- `0x18006d25c`
- `0x18006d664`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006d2fb`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006d2fb`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18006d2c4`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18006d2c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start<_lambda_280e8980dd3bf6c2879bb4dda568d8df_,>(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  v4 = operator new(0x40u);
  *v4 = *(_QWORD *)a2;
  std::wstring::wstring(v4 + 1, a2 + 8);
  *(_QWORD *)(v5 + 40) = *(_QWORD *)(a2 + 40);
  *(_DWORD *)(v5 + 48) = *(_DWORD *)(a2 + 48);
  *(_QWORD *)(v5 + 56) = *(_QWORD *)(a2 + 56);
  v8 = v5;
  v6 = _o__beginthreadex(0, 0, std::thread::_Invoke<std::tuple<_lambda_280e8980dd3bf6c2879bb4dda568d8df_>,0>);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18006D301LL);
  }
  v8 = 0;
  return std::unique_ptr<std::tuple<_lambda_280e8980dd3bf6c2879bb4dda568d8df_>>::~unique_ptr<std::tuple<_lambda_280e8980dd3bf6c2879bb4dda568d8df_>>(&v8);
}

```

## disassembly

```asm
0x18006d25c  mov     [rsp+arg_8], rbx
0x18006d261  push    rdi
0x18006d262  sub     rsp, 30h
0x18006d266  mov     rbx, rdx
0x18006d269  mov     rdi, rcx
0x18006d26c  mov     ecx, 40h ; '@'; Size
0x18006d271  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d276  mov     r9, rax
0x18006d279  mov     r8, [rbx]
0x18006d27c  mov     [rax], r8
0x18006d27f  lea     rdx, [rbx+8]
0x18006d283  lea     rcx, [rax+8]
0x18006d287  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18006d28c  mov     r8, [rbx+28h]
0x18006d290  mov     [r9+28h], r8
0x18006d294  mov     edx, [rbx+30h]
0x18006d297  mov     [r9+30h], edx
0x18006d29b  mov     rcx, [rbx+38h]
0x18006d29f  mov     [r9+38h], rcx
0x18006d2a3  mov     [rsp+38h+arg_0], r9
0x18006d2a8  lea     rbx, [rdi+8]
0x18006d2ac  mov     [rsp+38h+var_10], rbx
0x18006d2b1  mov     [rsp+38h+var_18], 0
0x18006d2b9  lea     r8, ??$_Invoke@V?$tuple@V_lambda_280e8980dd3bf6c2879bb4dda568d8df_@@@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<_lambda_280e8980dd3bf6c2879bb4dda568d8df_>,0>(void *)
0x18006d2c0  xor     edx, edx
0x18006d2c2  xor     ecx, ecx
0x18006d2c4  call    cs:__imp__o__beginthreadex
0x18006d2ca  mov     [rdi], rax
0x18006d2cd  test    rax, rax
0x18006d2d0  jz      short loc_18006D2F0
0x18006d2d2  mov     [rsp+38h+arg_0], 0
0x18006d2db  lea     rcx, [rsp+38h+arg_0]
0x18006d2e0  call    ??1?$unique_ptr@V?$tuple@V_lambda_280e8980dd3bf6c2879bb4dda568d8df_@@@std@@U?$default_delete@V?$tuple@V_lambda_280e8980dd3bf6c2879bb4dda568d8df_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_280e8980dd3bf6c2879bb4dda568d8df_>>::~unique_ptr<std::tuple<_lambda_280e8980dd3bf6c2879bb4dda568d8df_>>(void)
0x18006d2e5  mov     rbx, [rsp+38h+arg_8]
0x18006d2ea  add     rsp, 30h
0x18006d2ee  pop     rdi
0x18006d2ef  retn
0x18006d2f0  mov     dword ptr [rbx], 0
0x18006d2f6  mov     ecx, 6
0x18006d2fb  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
