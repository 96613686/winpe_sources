# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x140017708`
- end: `0x1400177c0`
- name: `?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z`
- size: `184`
- prototype: `struct __crt_multibyte_data *__fastcall(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140017498`
- `0x140017820`

## callees

- `0x140017708`
- `0x140019148`
- `0x140019930`
- `0x14001b4f8`
- `0x14001b558`

## pseudocode

```c
struct __crt_multibyte_data *__fastcall update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  if ( (dword_14003CA80 & *((_DWORD *)a1 + 234)) != 0 && *((_QWORD *)a1 + 18) )
  {
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
  }
  else
  {
    _vcrt_lock(5);
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
    if ( v4 != (volatile signed __int32 *)*a2 )
    {
      if ( v4 && _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 && v4 != (volatile signed __int32 *)qword_14003C250 )
        free_base((void *)v4);
      v5 = (volatile signed __int32 *)*a2;
      *((_QWORD *)a1 + 17) = *a2;
      _InterlockedIncrement(v5);
      v4 = v5;
    }
    _vcrt_unlock(5);
  }
  if ( !v4 )
    abort();
  return (struct __crt_multibyte_data *)v4;
}

```

## disassembly

```asm
0x140017708  mov     [rsp+arg_8], rbx
0x14001770d  mov     [rsp+arg_10], rsi
0x140017712  push    rdi
0x140017713  sub     rsp, 20h
0x140017717  mov     rsi, rdx
0x14001771a  mov     rdi, rcx
0x14001771d  mov     eax, cs:dword_14003CA80
0x140017723  test    [rcx+3A8h], eax
0x140017729  jz      short loc_14001773E
0x14001772b  cmp     qword ptr [rcx+90h], 0
0x140017733  jz      short loc_14001773E
0x140017735  mov     rbx, [rcx+88h]
0x14001773c  jmp     short loc_1400177A2
0x14001773e  mov     ecx, 5
0x140017743  call    __vcrt_lock
0x140017748  nop
0x140017749  mov     rbx, [rdi+88h]
0x140017750  mov     [rsp+28h+Block], rbx
0x140017755  cmp     rbx, [rsi]
0x140017758  jz      short loc_140017798
0x14001775a  test    rbx, rbx
0x14001775d  jz      short loc_140017781
0x14001775f  or      eax, 0FFFFFFFFh
0x140017762  lock xadd [rbx], eax
0x140017766  cmp     eax, 1
0x140017769  jnz     short loc_140017781
0x14001776b  lea     rax, qword_14003C250
0x140017772  mov     rcx, [rsp+28h+Block]; Block
0x140017777  cmp     rcx, rax
0x14001777a  jz      short loc_140017781
0x14001777c  call    _free_base
0x140017781  mov     rax, [rsi]
0x140017784  mov     [rdi+88h], rax
0x14001778b  mov     [rsp+28h+Block], rax
0x140017790  lock inc dword ptr [rax]
0x140017793  mov     rbx, [rsp+28h+Block]
0x140017798  mov     ecx, 5
0x14001779d  call    __vcrt_unlock
0x1400177a2  test    rbx, rbx
0x1400177a5  jz      short loc_1400177BA
0x1400177a7  mov     rax, rbx
0x1400177aa  mov     rbx, [rsp+28h+arg_8]
0x1400177af  mov     rsi, [rsp+28h+arg_10]
0x1400177b4  add     rsp, 20h
0x1400177b8  pop     rdi
0x1400177b9  retn
0x1400177ba  call    abort
```
