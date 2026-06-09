# update_thread_multibyte_data_internal

- ea: `0x18000a374`
- end: `0x18000a42c`
- name: `update_thread_multibyte_data_internal`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a104`
- `0x18000a4b0`

## callees

- `0x1800069b8`
- `0x180006a18`
- `0x1800078e0`
- `0x18000a374`
- `0x18000f790`

## pseudocode

```c
volatile signed __int32 *__fastcall update_thread_multibyte_data_internal(__int64 a1, volatile signed __int32 **a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  if ( (_globallocalestatus & *(_DWORD *)(a1 + 936)) != 0 && *(_QWORD *)(a1 + 144) )
  {
    v4 = *(volatile signed __int32 **)(a1 + 136);
  }
  else
  {
    _acrt_lock(5);
    v4 = *(volatile signed __int32 **)(a1 + 136);
    if ( v4 != *a2 )
    {
      if ( v4
        && _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1
        && v4 != (volatile signed __int32 *)_acrt_initial_multibyte_data )
      {
        free_base((void *)v4);
      }
      v5 = *a2;
      *(_QWORD *)(a1 + 136) = *a2;
      _InterlockedIncrement(v5);
      v4 = v5;
    }
    _acrt_unlock(5);
  }
  if ( !v4 )
    abort();
  return v4;
}

```

## disassembly

```asm
0x18000a374  mov     [rsp+arg_8], rbx
0x18000a379  mov     [rsp+arg_10], rsi
0x18000a37e  push    rdi
0x18000a37f  sub     rsp, 20h
0x18000a383  mov     rsi, rdx
0x18000a386  mov     rdi, rcx
0x18000a389  mov     eax, cs:__globallocalestatus
0x18000a38f  test    [rcx+3A8h], eax
0x18000a395  jz      short loc_18000A3AA
0x18000a397  cmp     qword ptr [rcx+90h], 0
0x18000a39f  jz      short loc_18000A3AA
0x18000a3a1  mov     rbx, [rcx+88h]
0x18000a3a8  jmp     short loc_18000A40E
0x18000a3aa  mov     ecx, 5
0x18000a3af  call    __acrt_lock
0x18000a3b4  nop
0x18000a3b5  mov     rbx, [rdi+88h]
0x18000a3bc  mov     [rsp+28h+Block], rbx
0x18000a3c1  cmp     rbx, [rsi]
0x18000a3c4  jz      short loc_18000A404
0x18000a3c6  test    rbx, rbx
0x18000a3c9  jz      short loc_18000A3ED
0x18000a3cb  or      eax, 0FFFFFFFFh
0x18000a3ce  lock xadd [rbx], eax
0x18000a3d2  cmp     eax, 1
0x18000a3d5  jnz     short loc_18000A3ED
0x18000a3d7  lea     rax, __acrt_initial_multibyte_data
0x18000a3de  mov     rcx, [rsp+28h+Block]; Block
0x18000a3e3  cmp     rcx, rax
0x18000a3e6  jz      short loc_18000A3ED
0x18000a3e8  call    _free_base
0x18000a3ed  mov     rax, [rsi]
0x18000a3f0  mov     [rdi+88h], rax
0x18000a3f7  mov     [rsp+28h+Block], rax
0x18000a3fc  lock inc dword ptr [rax]
0x18000a3ff  mov     rbx, [rsp+28h+Block]
0x18000a404  mov     ecx, 5
0x18000a409  call    __acrt_unlock
0x18000a40e  test    rbx, rbx
0x18000a411  jz      short loc_18000A426
0x18000a413  mov     rax, rbx
0x18000a416  mov     rbx, [rsp+28h+arg_8]
0x18000a41b  mov     rsi, [rsp+28h+arg_10]
0x18000a420  add     rsp, 20h
0x18000a424  pop     rdi
0x18000a425  retn
0x18000a426  call    abort
```
