# std::_Stop_state::_Request_stop(void)

- ea: `0x18000c040`
- end: `0x18000c16f`
- name: `?_Request_stop@_Stop_state@std@@QEAA_NXZ`
- size: `303`
- prototype: `bool __fastcall(std::_Stop_state *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a8d4`
- `0x18000abe0`
- `0x18000ba70`

## callees

- `0x18000c040`
- `0x18000e010`

## import_xrefs

- `msvcp_win!__std_atomic_wait_direct` at `0x18000c0cf`
- `msvcp_win!__std_atomic_wait_direct` at `0x18000c0cf`
- `msvcp_win!__std_atomic_notify_all_direct` at `0x18000c100`
- `msvcp_win!__std_atomic_notify_all_direct` at `0x18000c130`
- `msvcp_win!__std_atomic_notify_all_direct` at `0x18000c157`
- `msvcp_win!__std_atomic_notify_all_direct` at `0x18000c100`
- `msvcp_win!__std_atomic_notify_all_direct` at `0x18000c130`
- `msvcp_win!__std_atomic_notify_all_direct` at `0x18000c157`
- `msvcp_win!_Thrd_id` at `0x18000c070`
- `msvcp_win!_Thrd_id` at `0x18000c070`

## pseudocode

```c
char __fastcall std::_Stop_state::_Request_stop(std::_Stop_state *this)
{
  volatile signed __int64 *v3; // rdi
  signed __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  bool v6; // zf
  signed __int64 v7; // rax
  signed __int64 v8; // rax
  __int64 v9; // rax
  signed __int64 i; // [rsp+30h] [rbp+8h] BYREF

  _m_prefetchw((char *)this + 4);
  if ( (_InterlockedOr((volatile signed __int32 *)this + 1, 1u) & 1) != 0 )
    return 0;
  *((_DWORD *)this + 6) = _Thrd_id();
  v3 = (volatile signed __int64 *)((char *)this + 8);
LABEL_4:
  while ( 2 )
  {
    v4 = *v3;
    while ( (v4 & 3) != 0 )
    {
      if ( (v4 & 3) != 1 )
      {
        if ( (v4 & 3) != 2 )
          __fastfail(5u);
        goto LABEL_11;
      }
      v5 = v4 & 0xFFFFFFFFFFFFFFFCuLL | 2;
      v7 = _InterlockedCompareExchange64(v3, v5, v4);
      v6 = v4 == v7;
      v4 = v7;
      if ( v6 )
      {
        v4 = v5;
LABEL_11:
        for ( i = v4; i == *v3; __std_atomic_wait_direct((char *)this + 8, &i, 8, 0xFFFFFFFFLL) )
          ;
        goto LABEL_4;
      }
LABEL_17:
      _mm_pause();
    }
    v8 = _InterlockedCompareExchange64(v3, v4 | 1, v4);
    if ( v4 != v8 )
    {
      v4 = v8;
      goto LABEL_17;
    }
    *((_QWORD *)this + 2) = v4;
    ((void (*)(void))__std_atomic_notify_all_direct)();
    if ( v4 )
    {
      v9 = *(_QWORD *)(v4 + 8);
      *(_QWORD *)(v4 + 8) = 0;
      if ( v9 )
        *(_QWORD *)(v9 + 16) = 0;
      if ( (_InterlockedExchange64(v3, v9) & 3) == 2 )
        __std_atomic_notify_all_direct((char *)this + 8);
      (*(void (__fastcall **)(signed __int64))(v4 + 24))(v4);
      continue;
    }
    break;
  }
  if ( (_InterlockedExchange64(v3, 0) & 3) == 2 )
    __std_atomic_notify_all_direct((char *)this + 8);
  return 1;
}

```

## disassembly

```asm
0x18000c040  mov     [rsp+arg_8], rbx
0x18000c045  mov     [rsp+arg_10], rsi
0x18000c04a  push    rdi
0x18000c04b  sub     rsp, 20h
0x18000c04f  mov     rsi, rcx
0x18000c052  prefetchw byte ptr [rcx+4]
0x18000c056  mov     eax, [rcx+4]
0x18000c059  mov     edx, eax
0x18000c05b  or      edx, 1
0x18000c05e  lock cmpxchg [rcx+4], edx
0x18000c063  jnz     short loc_18000C059
0x18000c065  test    al, 1
0x18000c067  jz      short loc_18000C070
0x18000c069  xor     al, al
0x18000c06b  jmp     loc_18000C15F
0x18000c070  call    cs:__imp__Thrd_id
0x18000c076  mov     [rsi+18h], eax
0x18000c079  lea     rdi, [rsi+8]
0x18000c07d  mov     rbx, [rdi]
0x18000c080  mov     rax, rbx
0x18000c083  and     eax, 3
0x18000c086  jz      short loc_18000C0E1
0x18000c088  sub     rax, 1
0x18000c08c  jz      short loc_18000C09B
0x18000c08e  cmp     rax, 1
0x18000c092  jz      short loc_18000C0B6
0x18000c094  mov     ecx, 5
0x18000c099  int     29h; Win8: RtlFailFast(ecx)
0x18000c09b  mov     rcx, rbx
0x18000c09e  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000c0a2  or      rcx, 2
0x18000c0a6  mov     rax, rbx
0x18000c0a9  lock cmpxchg [rdi], rcx
0x18000c0ae  mov     rbx, rax
0x18000c0b1  jnz     short loc_18000C0F5
0x18000c0b3  mov     rbx, rcx
0x18000c0b6  mov     [rsp+28h+arg_0], rbx
0x18000c0bb  jmp     short loc_18000C0D5
0x18000c0bd  or      r9d, 0FFFFFFFFh
0x18000c0c1  mov     r8d, 8
0x18000c0c7  lea     rdx, [rsp+28h+arg_0]
0x18000c0cc  mov     rcx, rdi
0x18000c0cf  call    cs:__imp___std_atomic_wait_direct
0x18000c0d5  mov     rax, [rdi]
0x18000c0d8  cmp     [rsp+28h+arg_0], rax
0x18000c0dd  jz      short loc_18000C0BD
0x18000c0df  jmp     short loc_18000C07D
0x18000c0e1  mov     rcx, rbx
0x18000c0e4  or      rcx, 1
0x18000c0e8  mov     rax, rbx
0x18000c0eb  lock cmpxchg [rdi], rcx
0x18000c0f0  jz      short loc_18000C0F9
0x18000c0f2  mov     rbx, rax
0x18000c0f5  pause
0x18000c0f7  jmp     short loc_18000C080
0x18000c0f9  lea     rcx, [rsi+10h]
0x18000c0fd  mov     [rcx], rbx
0x18000c100  call    cs:__imp___std_atomic_notify_all_direct
0x18000c106  test    rbx, rbx
0x18000c109  jz      short loc_18000C147
0x18000c10b  mov     rax, [rbx+8]
0x18000c10f  mov     qword ptr [rbx+8], 0
0x18000c117  test    rax, rax
0x18000c11a  jz      short loc_18000C124
0x18000c11c  mov     qword ptr [rax+10h], 0
0x18000c124  xchg    rax, [rdi]
0x18000c127  and     al, 3
0x18000c129  cmp     al, 2
0x18000c12b  jnz     short loc_18000C136
0x18000c12d  mov     rcx, rdi
0x18000c130  call    cs:__imp___std_atomic_notify_all_direct
0x18000c136  mov     rcx, rbx
0x18000c139  mov     rax, [rbx+18h]
0x18000c13d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c142  jmp     loc_18000C07D
0x18000c147  xor     edx, edx
0x18000c149  xchg    rdx, [rdi]
0x18000c14c  and     dl, 3
0x18000c14f  cmp     dl, 2
0x18000c152  jnz     short loc_18000C15D
0x18000c154  mov     rcx, rdi
0x18000c157  call    cs:__imp___std_atomic_notify_all_direct
0x18000c15d  mov     al, 1
0x18000c15f  mov     rbx, [rsp+28h+arg_8]
0x18000c164  mov     rsi, [rsp+28h+arg_10]
0x18000c169  add     rsp, 20h
0x18000c16d  pop     rdi
0x18000c16e  retn
```
