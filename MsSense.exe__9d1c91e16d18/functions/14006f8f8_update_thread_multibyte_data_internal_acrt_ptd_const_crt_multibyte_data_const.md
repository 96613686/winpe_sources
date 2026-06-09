# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x14006f8f8`
- end: `0x14006f9b0`
- name: `?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z`
- size: `184`
- prototype: `struct __crt_multibyte_data *__fastcall(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14006f688`
- `0x14006fa10`

## callees

- `0x14006d034`
- `0x14006f8f8`
- `0x14006fd48`
- `0x14006fda8`
- `0x140072280`

## pseudocode

```c
struct __crt_multibyte_data *__fastcall update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  if ( (dword_1400BE1D4 & *((_DWORD *)a1 + 234)) != 0 && *((_QWORD *)a1 + 18) )
  {
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
  }
  else
  {
    _vcrt_lock_0(5);
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
    if ( v4 != (volatile signed __int32 *)*a2 )
    {
      if ( v4 && _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 && v4 != (volatile signed __int32 *)qword_1400BDB10 )
        free_base((void *)v4);
      v5 = (volatile signed __int32 *)*a2;
      *((_QWORD *)a1 + 17) = *a2;
      _InterlockedIncrement(v5);
      v4 = v5;
    }
    _vcrt_unlock_0(5);
  }
  if ( !v4 )
    abort();
  return (struct __crt_multibyte_data *)v4;
}

```

## disassembly

```asm
0x14006f8f8  mov     [rsp+arg_8], rbx
0x14006f8fd  mov     [rsp+arg_10], rsi
0x14006f902  push    rdi
0x14006f903  sub     rsp, 20h
0x14006f907  mov     rsi, rdx
0x14006f90a  mov     rdi, rcx
0x14006f90d  mov     eax, cs:dword_1400BE1D4
0x14006f913  test    [rcx+3A8h], eax
0x14006f919  jz      short loc_14006F92E
0x14006f91b  cmp     qword ptr [rcx+90h], 0
0x14006f923  jz      short loc_14006F92E
0x14006f925  mov     rbx, [rcx+88h]
0x14006f92c  jmp     short loc_14006F992
0x14006f92e  mov     ecx, 5
0x14006f933  call    __vcrt_lock_0
0x14006f938  nop
0x14006f939  mov     rbx, [rdi+88h]
0x14006f940  mov     [rsp+28h+Block], rbx
0x14006f945  cmp     rbx, [rsi]
0x14006f948  jz      short loc_14006F988
0x14006f94a  test    rbx, rbx
0x14006f94d  jz      short loc_14006F971
0x14006f94f  or      eax, 0FFFFFFFFh
0x14006f952  lock xadd [rbx], eax
0x14006f956  cmp     eax, 1
0x14006f959  jnz     short loc_14006F971
0x14006f95b  lea     rax, qword_1400BDB10
0x14006f962  mov     rcx, [rsp+28h+Block]; Block
0x14006f967  cmp     rcx, rax
0x14006f96a  jz      short loc_14006F971
0x14006f96c  call    _free_base
0x14006f971  mov     rax, [rsi]
0x14006f974  mov     [rdi+88h], rax
0x14006f97b  mov     [rsp+28h+Block], rax
0x14006f980  lock inc dword ptr [rax]
0x14006f983  mov     rbx, [rsp+28h+Block]
0x14006f988  mov     ecx, 5
0x14006f98d  call    __vcrt_unlock_0
0x14006f992  test    rbx, rbx
0x14006f995  jz      short loc_14006F9AA
0x14006f997  mov     rax, rbx
0x14006f99a  mov     rbx, [rsp+28h+arg_8]
0x14006f99f  mov     rsi, [rsp+28h+arg_10]
0x14006f9a4  add     rsp, 20h
0x14006f9a8  pop     rdi
0x14006f9a9  retn
0x14006f9aa  call    abort
```
