# update_thread_multibyte_data_internal(__acrt_ptd * const,__crt_multibyte_data * * const)

- ea: `0x140007730`
- end: `0x1400077e8`
- name: `?update_thread_multibyte_data_internal@@YAPEAU__crt_multibyte_data@@QEAU__acrt_ptd@@QEAPEAU1@@Z`
- size: `184`
- prototype: `struct __crt_multibyte_data *__fastcall(struct __acrt_ptd *const, struct __crt_multibyte_data **const)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400074c0`
- `0x140007850`

## callees

- `0x140005a20`
- `0x140006940`
- `0x140007730`
- `0x1400081e8`
- `0x140008248`

## pseudocode

```c
struct __crt_multibyte_data *__fastcall update_thread_multibyte_data_internal(
        struct __acrt_ptd *const a1,
        struct __crt_multibyte_data **const a2)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rax

  if ( (dword_140019840 & *((_DWORD *)a1 + 234)) != 0 && *((_QWORD *)a1 + 18) )
  {
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
  }
  else
  {
    sub_1400081E8(5);
    v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 17);
    if ( v4 != (volatile signed __int32 *)*a2 )
    {
      if ( v4 && _InterlockedExchangeAdd(v4, 0xFFFFFFFF) == 1 && v4 != (volatile signed __int32 *)qword_1400190F0 )
        free_base((void *)v4);
      v5 = (volatile signed __int32 *)*a2;
      *((_QWORD *)a1 + 17) = *a2;
      _InterlockedIncrement(v5);
      v4 = v5;
    }
    sub_140008248(5);
  }
  if ( !v4 )
    abort();
  return (struct __crt_multibyte_data *)v4;
}

```

## disassembly

```asm
0x140007730  mov     [rsp+arg_8], rbx
0x140007735  mov     [rsp+arg_10], rsi
0x14000773a  push    rdi
0x14000773b  sub     rsp, 20h
0x14000773f  mov     rsi, rdx
0x140007742  mov     rdi, rcx
0x140007745  mov     eax, cs:dword_140019840
0x14000774b  test    [rcx+3A8h], eax
0x140007751  jz      short loc_140007766
0x140007753  cmp     qword ptr [rcx+90h], 0
0x14000775b  jz      short loc_140007766
0x14000775d  mov     rbx, [rcx+88h]
0x140007764  jmp     short loc_1400077CA
0x140007766  mov     ecx, 5
0x14000776b  call    sub_1400081E8
0x140007770  nop
0x140007771  mov     rbx, [rdi+88h]
0x140007778  mov     [rsp+28h+Block], rbx
0x14000777d  cmp     rbx, [rsi]
0x140007780  jz      short loc_1400077C0
0x140007782  test    rbx, rbx
0x140007785  jz      short loc_1400077A9
0x140007787  or      eax, 0FFFFFFFFh
0x14000778a  lock xadd [rbx], eax
0x14000778e  cmp     eax, 1
0x140007791  jnz     short loc_1400077A9
0x140007793  lea     rax, qword_1400190F0
0x14000779a  mov     rcx, [rsp+28h+Block]; Block
0x14000779f  cmp     rcx, rax
0x1400077a2  jz      short loc_1400077A9
0x1400077a4  call    _free_base
0x1400077a9  mov     rax, [rsi]
0x1400077ac  mov     [rdi+88h], rax
0x1400077b3  mov     [rsp+28h+Block], rax
0x1400077b8  lock inc dword ptr [rax]
0x1400077bb  mov     rbx, [rsp+28h+Block]
0x1400077c0  mov     ecx, 5
0x1400077c5  call    sub_140008248
0x1400077ca  test    rbx, rbx
0x1400077cd  jz      short loc_1400077E2
0x1400077cf  mov     rax, rbx
0x1400077d2  mov     rbx, [rsp+28h+arg_8]
0x1400077d7  mov     rsi, [rsp+28h+arg_10]
0x1400077dc  add     rsp, 20h
0x1400077e0  pop     rdi
0x1400077e1  retn
0x1400077e2  call    abort
```
