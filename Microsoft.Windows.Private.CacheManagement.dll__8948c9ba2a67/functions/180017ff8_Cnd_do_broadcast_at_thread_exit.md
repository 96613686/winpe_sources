# _Cnd_do_broadcast_at_thread_exit

- ea: `0x180017ff8`
- end: `0x1800180ed`
- name: `_Cnd_do_broadcast_at_thread_exit`
- size: `245`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009f30`

## callees

- `0x1800165b8`
- `0x1800165c0`
- `0x18001700c`
- `0x180017308`
- `0x180017f3c`
- `0x180017ff8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __cdecl Cnd_do_broadcast_at_thread_exit()
{
  __int64 *v0; // rbx
  _Thrd_id_t v1; // ebp
  __int64 v2; // rsi
  int v3; // eax
  __int64 *v4; // rdi
  int v5; // ecx
  _DWORD *v6; // rax

  v0 = qword_18002DB30;
  v1 = Thrd_id();
  if ( Mtx_lock((_Mtx_t)qword_18002D190) )
    std::_Throw_Cpp_error(5);
  if ( dword_18002D1DC == 0x7FFFFFFF )
  {
    dword_18002D1DC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  do
  {
    v2 = 0;
    v3 = *((_DWORD *)v0 + 200);
    if ( v3 )
    {
      v4 = v0 + 2;
      do
      {
        if ( v2 >= 20 )
          break;
        v5 = v3;
        if ( *v4 && *((_DWORD *)v4 - 2) == v1 )
        {
          v6 = (_DWORD *)v4[2];
          if ( v6 )
            *v6 = 1;
          Mtx_unlock((_Mtx_t)*v4);
          Cnd_broadcast((_Cnd_t)v4[1]);
          *v4 = 0;
          v5 = --*((_DWORD *)v0 + 200);
        }
        ++v2;
        v4 += 5;
        v3 = v5;
      }
      while ( v5 );
    }
    v0 = (__int64 *)v0[101];
  }
  while ( v0 );
  Mtx_unlock((_Mtx_t)qword_18002D190);
}

```

## disassembly

```asm
0x180017ff8  mov     [rsp+arg_0], rbx
0x180017ffd  mov     [rsp+arg_8], rbp
0x180018002  mov     [rsp+arg_10], rsi
0x180018007  push    rdi
0x180018008  sub     rsp, 20h
0x18001800c  lea     rbx, qword_18002DB30
0x180018013  call    _Thrd_id
0x180018018  mov     ebp, eax
0x18001801a  lea     rcx, qword_18002D190; _Mtx_t
0x180018021  call    _Mtx_lock
0x180018026  test    eax, eax
0x180018028  jnz     loc_1800180E2
0x18001802e  cmp     cs:dword_18002D1DC, 7FFFFFFFh
0x180018038  jz      loc_1800180CD
0x18001803e  xor     esi, esi
0x180018040  mov     eax, [rbx+320h]
0x180018046  test    eax, eax
0x180018048  jz      short loc_1800180A1
0x18001804a  lea     rdi, [rbx+10h]
0x18001804e  cmp     rsi, 14h
0x180018052  jge     short loc_1800180A1
0x180018054  mov     ecx, eax
0x180018056  cmp     qword ptr [rdi], 0
0x18001805a  jz      short loc_180018094
0x18001805c  cmp     [rdi-8], ebp
0x18001805f  jnz     short loc_180018094
0x180018061  mov     rax, [rdi+10h]
0x180018065  test    rax, rax
0x180018068  jz      short loc_180018070
0x18001806a  mov     dword ptr [rax], 1
0x180018070  mov     rcx, [rdi]; _Mtx_t
0x180018073  call    _Mtx_unlock
0x180018078  mov     rcx, [rdi+8]; _Cnd_t
0x18001807c  call    _Cnd_broadcast
0x180018081  mov     qword ptr [rdi], 0
0x180018088  dec     dword ptr [rbx+320h]
0x18001808e  mov     ecx, [rbx+320h]
0x180018094  inc     rsi
0x180018097  add     rdi, 28h ; '('
0x18001809b  mov     eax, ecx
0x18001809d  test    ecx, ecx
0x18001809f  jnz     short loc_18001804E
0x1800180a1  mov     rbx, [rbx+328h]
0x1800180a8  test    rbx, rbx
0x1800180ab  jnz     short loc_18001803E
0x1800180ad  lea     rcx, qword_18002D190
0x1800180b4  mov     rbx, [rsp+28h+arg_0]
0x1800180b9  mov     rbp, [rsp+28h+arg_8]
0x1800180be  mov     rsi, [rsp+28h+arg_10]
0x1800180c3  add     rsp, 20h
0x1800180c7  pop     rdi
0x1800180c8  jmp     _Mtx_unlock
0x1800180cd  mov     cs:dword_18002D1DC, 7FFFFFFEh
0x1800180d7  mov     ecx, 6; int
0x1800180dc  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800180e2  mov     ecx, 5; int
0x1800180e7  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
