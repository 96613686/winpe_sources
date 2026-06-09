# update_thread_multibyte_data_internal

- ea: `0x180013398`
- end: `0x180013450`
- name: `update_thread_multibyte_data_internal`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800131d8`
- `0x1800134b0`

## callees

- `0x18000e7c8`
- `0x18000fe3c`
- `0x180011ff8`
- `0x180012058`
- `0x180013398`

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
        && v4 != (volatile signed __int32 *)&_acrt_initial_multibyte_data )
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
0x180013398  mov     [rsp+arg_8], rbx
0x18001339d  mov     [rsp+arg_10], rsi
0x1800133a2  push    rdi
0x1800133a3  sub     rsp, 20h
0x1800133a7  mov     rsi, rdx
0x1800133aa  mov     rdi, rcx
0x1800133ad  mov     eax, cs:__globallocalestatus
0x1800133b3  test    [rcx+3A8h], eax
0x1800133b9  jz      short loc_1800133CE
0x1800133bb  cmp     qword ptr [rcx+90h], 0
0x1800133c3  jz      short loc_1800133CE
0x1800133c5  mov     rbx, [rcx+88h]
0x1800133cc  jmp     short loc_180013432
0x1800133ce  mov     ecx, 5
0x1800133d3  call    __acrt_lock
0x1800133d8  nop
0x1800133d9  mov     rbx, [rdi+88h]
0x1800133e0  mov     [rsp+28h+Block], rbx
0x1800133e5  cmp     rbx, [rsi]
0x1800133e8  jz      short loc_180013428
0x1800133ea  test    rbx, rbx
0x1800133ed  jz      short loc_180013411
0x1800133ef  or      eax, 0FFFFFFFFh
0x1800133f2  lock xadd [rbx], eax
0x1800133f6  cmp     eax, 1
0x1800133f9  jnz     short loc_180013411
0x1800133fb  lea     rax, __acrt_initial_multibyte_data
0x180013402  mov     rcx, [rsp+28h+Block]; Block
0x180013407  cmp     rcx, rax
0x18001340a  jz      short loc_180013411
0x18001340c  call    _free_base
0x180013411  mov     rax, [rsi]
0x180013414  mov     [rdi+88h], rax
0x18001341b  mov     [rsp+28h+Block], rax
0x180013420  lock inc dword ptr [rax]
0x180013423  mov     rbx, [rsp+28h+Block]
0x180013428  mov     ecx, 5
0x18001342d  call    __acrt_unlock
0x180013432  test    rbx, rbx
0x180013435  jz      short loc_18001344A
0x180013437  mov     rax, rbx
0x18001343a  mov     rbx, [rsp+28h+arg_8]
0x18001343f  mov     rsi, [rsp+28h+arg_10]
0x180013444  add     rsp, 20h
0x180013448  pop     rdi
0x180013449  retn
0x18001344a  call    abort
0x180025209  push    rbp
0x18002520b  sub     rsp, 20h
0x18002520f  mov     rbp, rdx
0x180025212  mov     ecx, 5
0x180025217  add     rsp, 20h
0x18002521b  pop     rbp
0x18002521c  jmp     __acrt_unlock
```
