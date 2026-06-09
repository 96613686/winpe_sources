# update_thread_multibyte_data_internal

- ea: `0x18000aad4`
- end: `0x18000ab8c`
- name: `update_thread_multibyte_data_internal`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a864`
- `0x18000ac10`

## callees

- `0x180007118`
- `0x180007178`
- `0x180008040`
- `0x18000aad4`
- `0x18000fef0`

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
0x18000aad4  mov     [rsp+arg_8], rbx
0x18000aad9  mov     [rsp+arg_10], rsi
0x18000aade  push    rdi
0x18000aadf  sub     rsp, 20h
0x18000aae3  mov     rsi, rdx
0x18000aae6  mov     rdi, rcx
0x18000aae9  mov     eax, cs:__globallocalestatus
0x18000aaef  test    [rcx+3A8h], eax
0x18000aaf5  jz      short loc_18000AB0A
0x18000aaf7  cmp     qword ptr [rcx+90h], 0
0x18000aaff  jz      short loc_18000AB0A
0x18000ab01  mov     rbx, [rcx+88h]
0x18000ab08  jmp     short loc_18000AB6E
0x18000ab0a  mov     ecx, 5
0x18000ab0f  call    __acrt_lock
0x18000ab14  nop
0x18000ab15  mov     rbx, [rdi+88h]
0x18000ab1c  mov     [rsp+28h+Block], rbx
0x18000ab21  cmp     rbx, [rsi]
0x18000ab24  jz      short loc_18000AB64
0x18000ab26  test    rbx, rbx
0x18000ab29  jz      short loc_18000AB4D
0x18000ab2b  or      eax, 0FFFFFFFFh
0x18000ab2e  lock xadd [rbx], eax
0x18000ab32  cmp     eax, 1
0x18000ab35  jnz     short loc_18000AB4D
0x18000ab37  lea     rax, __acrt_initial_multibyte_data
0x18000ab3e  mov     rcx, [rsp+28h+Block]; Block
0x18000ab43  cmp     rcx, rax
0x18000ab46  jz      short loc_18000AB4D
0x18000ab48  call    _free_base
0x18000ab4d  mov     rax, [rsi]
0x18000ab50  mov     [rdi+88h], rax
0x18000ab57  mov     [rsp+28h+Block], rax
0x18000ab5c  lock inc dword ptr [rax]
0x18000ab5f  mov     rbx, [rsp+28h+Block]
0x18000ab64  mov     ecx, 5
0x18000ab69  call    __acrt_unlock
0x18000ab6e  test    rbx, rbx
0x18000ab71  jz      short loc_18000AB86
0x18000ab73  mov     rax, rbx
0x18000ab76  mov     rbx, [rsp+28h+arg_8]
0x18000ab7b  mov     rsi, [rsp+28h+arg_10]
0x18000ab80  add     rsp, 20h
0x18000ab84  pop     rdi
0x18000ab85  retn
0x18000ab86  call    abort
```
