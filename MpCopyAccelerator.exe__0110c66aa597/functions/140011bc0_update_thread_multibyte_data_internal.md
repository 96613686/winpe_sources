# update_thread_multibyte_data_internal

- ea: `0x140011bc0`
- end: `0x140011c78`
- name: `update_thread_multibyte_data_internal`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140011950`
- `0x140011ce0`

## callees

- `0x140011bc0`
- `0x140013658`
- `0x140013e10`
- `0x140016848`
- `0x1400168a8`

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
0x140011bc0  mov     [rsp+arg_8], rbx
0x140011bc5  mov     [rsp+arg_10], rsi
0x140011bca  push    rdi
0x140011bcb  sub     rsp, 20h
0x140011bcf  mov     rsi, rdx
0x140011bd2  mov     rdi, rcx
0x140011bd5  mov     eax, cs:__globallocalestatus
0x140011bdb  test    [rcx+3A8h], eax
0x140011be1  jz      short loc_140011BF6
0x140011be3  cmp     qword ptr [rcx+90h], 0
0x140011beb  jz      short loc_140011BF6
0x140011bed  mov     rbx, [rcx+88h]
0x140011bf4  jmp     short loc_140011C5A
0x140011bf6  mov     ecx, 5
0x140011bfb  call    __acrt_lock
0x140011c00  nop
0x140011c01  mov     rbx, [rdi+88h]
0x140011c08  mov     [rsp+28h+Block], rbx
0x140011c0d  cmp     rbx, [rsi]
0x140011c10  jz      short loc_140011C50
0x140011c12  test    rbx, rbx
0x140011c15  jz      short loc_140011C39
0x140011c17  or      eax, 0FFFFFFFFh
0x140011c1a  lock xadd [rbx], eax
0x140011c1e  cmp     eax, 1
0x140011c21  jnz     short loc_140011C39
0x140011c23  lea     rax, __acrt_initial_multibyte_data
0x140011c2a  mov     rcx, [rsp+28h+Block]; Block
0x140011c2f  cmp     rcx, rax
0x140011c32  jz      short loc_140011C39
0x140011c34  call    _free_base
0x140011c39  mov     rax, [rsi]
0x140011c3c  mov     [rdi+88h], rax
0x140011c43  mov     [rsp+28h+Block], rax
0x140011c48  lock inc dword ptr [rax]
0x140011c4b  mov     rbx, [rsp+28h+Block]
0x140011c50  mov     ecx, 5
0x140011c55  call    __acrt_unlock
0x140011c5a  test    rbx, rbx
0x140011c5d  jz      short loc_140011C72
0x140011c5f  mov     rax, rbx
0x140011c62  mov     rbx, [rsp+28h+arg_8]
0x140011c67  mov     rsi, [rsp+28h+arg_10]
0x140011c6c  add     rsp, 20h
0x140011c70  pop     rdi
0x140011c71  retn
0x140011c72  call    abort
```
