# _Cnd_register_at_thread_exit

- ea: `0x1801d2fa0`
- end: `0x1801d30a3`
- name: `_Cnd_register_at_thread_exit`
- size: `259`
- prototype: `void __cdecl(_Cnd_t, _Mtx_t, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180037770`
- `0x18005e040`
- `0x180198e20`

## callees

- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801d2fa0`
- `0x180213270`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801d303e`
- `KERNEL32!GetCurrentThreadId` at `0x1801d303e`

## pseudocode

```c
void __cdecl Cnd_register_at_thread_exit(_Cnd_t a1, _Mtx_t a2, int *a3)
{
  __int64 *v6; // rdi
  __int64 **v7; // rbx
  __int64 v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rbx

  v6 = qword_1803DCC90;
  if ( Mtx_lock((_Mtx_t)qword_18033B620) )
    std::_Throw_Cpp_error(5);
  if ( dword_18033B66C == 0x7FFFFFFF )
  {
    dword_18033B66C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  while ( *((_DWORD *)v6 + 200) == 20 )
  {
    v7 = (__int64 **)(v6 + 101);
    v6 = (__int64 *)v6[101];
    if ( !v6 )
    {
      v6 = (__int64 *)calloc(1u, 0x330u);
      *v7 = v6;
      if ( !v6 )
        goto LABEL_12;
    }
  }
  v8 = 0;
  v9 = v6 + 2;
  while ( *v9 )
  {
    ++v8;
    v9 += 5;
    if ( v8 >= 20 )
      goto LABEL_12;
  }
  v10 = 5 * v8;
  LODWORD(v6[v10 + 1]) = GetCurrentThreadId();
  v6[v10 + 2] = (__int64)a2;
  v6[v10 + 3] = (__int64)a1;
  v6[v10 + 4] = (__int64)a3;
  ++*((_DWORD *)v6 + 200);
LABEL_12:
  Mtx_unlock((_Mtx_t)qword_18033B620);
}

```

## disassembly

```asm
0x1801d2fa0  mov     rax, rsp
0x1801d2fa3  mov     [rax+8], rbx
0x1801d2fa7  mov     [rax+10h], rbp
0x1801d2fab  mov     [rax+18h], rsi
0x1801d2faf  mov     [rax+20h], rdi
0x1801d2fb3  push    r14
0x1801d2fb5  sub     rsp, 20h
0x1801d2fb9  mov     rsi, r8
0x1801d2fbc  mov     rbp, rdx
0x1801d2fbf  mov     r14, rcx
0x1801d2fc2  lea     rdi, qword_1803DCC90
0x1801d2fc9  lea     rcx, qword_18033B620; _Mtx_t
0x1801d2fd0  call    _Mtx_lock
0x1801d2fd5  test    eax, eax
0x1801d2fd7  jnz     loc_1801D3098
0x1801d2fdd  cmp     cs:dword_18033B66C, 7FFFFFFFh
0x1801d2fe7  jz      loc_1801D3083
0x1801d2fed  cmp     dword ptr [rdi+320h], 14h
0x1801d2ff4  jnz     short loc_1801D301F
0x1801d2ff6  lea     rbx, [rdi+328h]
0x1801d2ffd  mov     rdi, [rbx]
0x1801d3000  test    rdi, rdi
0x1801d3003  jnz     short loc_1801D2FED
0x1801d3005  mov     edx, 330h; Size
0x1801d300a  lea     ecx, [rdi+1]; Count
0x1801d300d  call    calloc
0x1801d3012  mov     rdi, rax
0x1801d3015  mov     [rbx], rax
0x1801d3018  test    rax, rax
0x1801d301b  jnz     short loc_1801D2FED
0x1801d301d  jmp     short loc_1801D305D
0x1801d301f  xor     eax, eax
0x1801d3021  lea     rcx, [rdi+10h]
0x1801d3025  cmp     qword ptr [rcx], 0
0x1801d3029  jz      short loc_1801D303A
0x1801d302b  inc     rax
0x1801d302e  add     rcx, 28h ; '('
0x1801d3032  cmp     rax, 14h
0x1801d3036  jl      short loc_1801D3025
0x1801d3038  jmp     short loc_1801D305D
0x1801d303a  lea     rbx, [rax+rax*4]
0x1801d303e  call    cs:__imp_GetCurrentThreadId
0x1801d3044  mov     [rdi+rbx*8+8], eax
0x1801d3048  mov     [rdi+rbx*8+10h], rbp
0x1801d304d  mov     [rdi+rbx*8+18h], r14
0x1801d3052  mov     [rdi+rbx*8+20h], rsi
0x1801d3057  inc     dword ptr [rdi+320h]
0x1801d305d  lea     rcx, qword_18033B620
0x1801d3064  mov     rbx, [rsp+28h+arg_0]
0x1801d3069  mov     rbp, [rsp+28h+arg_8]
0x1801d306e  mov     rsi, [rsp+28h+arg_10]
0x1801d3073  mov     rdi, [rsp+28h+arg_18]
0x1801d3078  add     rsp, 20h
0x1801d307c  pop     r14
0x1801d307e  jmp     _Mtx_unlock
0x1801d3083  mov     cs:dword_18033B66C, 7FFFFFFEh
0x1801d308d  mov     ecx, 6; int
0x1801d3092  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1801d3098  mov     ecx, 5; int
0x1801d309d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
