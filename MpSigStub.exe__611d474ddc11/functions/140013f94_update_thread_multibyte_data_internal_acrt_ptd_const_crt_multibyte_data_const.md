# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x140013f94`
- end: `0x14001404c`
- name: `?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z`
- size: `184`
- prototype: `struct __crt_multibyte_data *__fastcall(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140013d24`
- `0x1400140b0`

## callees

- `0x1400104cc`
- `0x1400107c4`
- `0x140013398`
- `0x1400133f8`
- `0x140013f94`

## pseudocode

```c
struct __crt_multibyte_data *__fastcall update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  if ( (dword_1400D67C0 & *((_DWORD *)a1 + 234)) != 0 && *((_QWORD *)a1 + 18) )
  {
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
  }
  else
  {
    sub_140013398(5);
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
    if ( v4 != (volatile signed __int32 *)*a2 )
    {
      if ( v4 && _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 && v4 != (volatile signed __int32 *)qword_1400D6280 )
        free_base((void *)v4);
      v5 = (volatile signed __int32 *)*a2;
      *((_QWORD *)a1 + 17) = *a2;
      _InterlockedIncrement(v5);
      v4 = v5;
    }
    sub_1400133F8(5);
  }
  if ( !v4 )
    abort();
  return (struct __crt_multibyte_data *)v4;
}

```

## disassembly

```asm
0x140013f94  mov     [rsp+arg_8], rbx
0x140013f99  mov     [rsp+arg_10], rsi
0x140013f9e  push    rdi
0x140013f9f  sub     rsp, 20h
0x140013fa3  mov     rsi, rdx
0x140013fa6  mov     rdi, rcx
0x140013fa9  mov     eax, cs:dword_1400D67C0
0x140013faf  test    [rcx+3A8h], eax
0x140013fb5  jz      short loc_140013FCA
0x140013fb7  cmp     qword ptr [rcx+90h], 0
0x140013fbf  jz      short loc_140013FCA
0x140013fc1  mov     rbx, [rcx+88h]
0x140013fc8  jmp     short loc_14001402E
0x140013fca  mov     ecx, 5
0x140013fcf  call    sub_140013398
0x140013fd4  nop
0x140013fd5  mov     rbx, [rdi+88h]
0x140013fdc  mov     [rsp+28h+Block], rbx
0x140013fe1  cmp     rbx, [rsi]
0x140013fe4  jz      short loc_140014024
0x140013fe6  test    rbx, rbx
0x140013fe9  jz      short loc_14001400D
0x140013feb  or      eax, 0FFFFFFFFh
0x140013fee  lock xadd [rbx], eax
0x140013ff2  cmp     eax, 1
0x140013ff5  jnz     short loc_14001400D
0x140013ff7  lea     rax, qword_1400D6280
0x140013ffe  mov     rcx, [rsp+28h+Block]; Block
0x140014003  cmp     rcx, rax
0x140014006  jz      short loc_14001400D
0x140014008  call    _free_base
0x14001400d  mov     rax, [rsi]
0x140014010  mov     [rdi+88h], rax
0x140014017  mov     [rsp+28h+Block], rax
0x14001401c  lock inc dword ptr [rax]
0x14001401f  mov     rbx, [rsp+28h+Block]
0x140014024  mov     ecx, 5
0x140014029  call    sub_1400133F8
0x14001402e  test    rbx, rbx
0x140014031  jz      short loc_140014046
0x140014033  mov     rax, rbx
0x140014036  mov     rbx, [rsp+28h+arg_8]
0x14001403b  mov     rsi, [rsp+28h+arg_10]
0x140014040  add     rsp, 20h
0x140014044  pop     rdi
0x140014045  retn
0x140014046  call    abort
```
