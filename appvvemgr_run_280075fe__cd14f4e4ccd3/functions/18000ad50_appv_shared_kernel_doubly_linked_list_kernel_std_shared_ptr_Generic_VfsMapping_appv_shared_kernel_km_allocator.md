# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)

- ea: `0x18000ad50`
- end: `0x18000ade0`
- name: `?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ`
- size: `144`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d50`
- `0x180004e20`
- `0x180010b50`
- `0x180011538`
- `0x180011e9c`

## callees

- `0x18000ad50`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000adc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000adc1`

## pseudocode

```c
void __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(
        __int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // r14
  __int64 v4; // rax
  _QWORD *v5; // rbp
  volatile signed __int32 *v6; // rdi

  v1 = *(_QWORD **)(a1 + 32);
  v2 = (_QWORD *)(a1 + 8);
  while ( v1 != v2 )
  {
    v4 = v1[2];
    v5 = (_QWORD *)v1[3];
    *(_QWORD *)(v4 + 24) = v5;
    v5[2] = v4;
    v6 = (volatile signed __int32 *)v1[1];
    if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    ExFreePoolWithTag(v1, 0);
    --*(_DWORD *)a1;
    v1 = v5;
  }
}

```

## disassembly

```asm
0x18000ad50  push    rbx
0x18000ad52  push    rbp
0x18000ad53  push    rsi
0x18000ad54  push    rdi
0x18000ad55  push    r14
0x18000ad57  sub     rsp, 20h
0x18000ad5b  mov     rbx, [rcx+20h]
0x18000ad5f  lea     r14, [rcx+8]
0x18000ad63  mov     rsi, rcx
0x18000ad66  cmp     rbx, r14
0x18000ad69  jz      short loc_18000ADD4
0x18000ad6b  mov     rax, [rbx+10h]
0x18000ad6f  mov     rbp, [rbx+18h]
0x18000ad73  mov     [rax+18h], rbp
0x18000ad77  mov     [rbp+10h], rax
0x18000ad7b  mov     rdi, [rbx+8]
0x18000ad7f  test    rdi, rdi
0x18000ad82  jz      short loc_18000ADBC
0x18000ad84  or      eax, 0FFFFFFFFh
0x18000ad87  lock xadd [rdi+8], eax
0x18000ad8c  cmp     eax, 1
0x18000ad8f  jnz     short loc_18000ADBC
0x18000ad91  mov     rax, [rdi]
0x18000ad94  mov     rcx, rdi
0x18000ad97  mov     rax, [rax+8]
0x18000ad9b  call    _guard_dispatch_icall
0x18000ada0  or      eax, 0FFFFFFFFh
0x18000ada3  lock xadd [rdi+0Ch], eax
0x18000ada8  cmp     eax, 1
0x18000adab  jnz     short loc_18000ADBC
0x18000adad  mov     rax, [rdi]
0x18000adb0  mov     rcx, rdi
0x18000adb3  mov     rax, [rax+10h]
0x18000adb7  call    _guard_dispatch_icall
0x18000adbc  xor     edx, edx; Tag
0x18000adbe  mov     rcx, rbx; P
0x18000adc1  call    cs:__imp_ExFreePoolWithTag
0x18000adc8  nop     dword ptr [rax+rax+00h]
0x18000adcd  dec     dword ptr [rsi]
0x18000adcf  mov     rbx, rbp
0x18000add2  jmp     short loc_18000AD66
0x18000add4  add     rsp, 20h
0x18000add8  pop     r14
0x18000adda  pop     rdi
0x18000addb  pop     rsi
0x18000addc  pop     rbp
0x18000addd  pop     rbx
0x18000adde  retn
```
