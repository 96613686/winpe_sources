# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>)

- ea: `0x18002040c`
- end: `0x18002049a`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@@Z`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013be8`
- `0x180013db8`
- `0x180020990`
- `0x1800359b8`

## callees

- `0x1800086fc`
- `0x18000875c`
- `0x1800131d4`
- `0x180013998`
- `0x18002040c`

## pseudocode

```c
__int64 __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>>>::_Assign_grow(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  __int64 size_of; // rax
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  __int64 result; // rax
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = a3;
  if ( (__int64)(a1[1] - *a1) >> 3 >= a2 )
    return std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>>(
             *a1,
             a1[1],
             &v10);
  size_of = std::_Get_size_of_n<8>(a2);
  v7 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v8 = (__int64)(a1[2] - *a1) >> 3;
  if ( v8 )
    std::_Deallocate<16>(*a1, 8 * v8);
  result = (__int64)&v7[a2];
  *a1 = v7;
  a1[1] = result;
  a1[2] = result;
  while ( v7 != (_QWORD *)result )
    *v7++ = a3;
  return result;
}

```

## disassembly

```asm
0x18002040c  mov     [rsp+arg_10], r8
0x180020411  push    rbx
0x180020412  push    rbp
0x180020413  push    rsi
0x180020414  push    rdi
0x180020415  sub     rsp, 28h
0x180020419  mov     rbp, rdx
0x18002041c  mov     rbx, r8
0x18002041f  mov     rdx, [rcx+8]
0x180020423  mov     rsi, rcx
0x180020426  mov     rax, rdx
0x180020429  sub     rax, [rcx]
0x18002042c  sar     rax, 3
0x180020430  cmp     rax, rbp
0x180020433  jnb     short loc_180020483
0x180020435  mov     rcx, rbp
0x180020438  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18002043d  mov     rcx, rax
0x180020440  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180020445  mov     rdx, [rsi+10h]
0x180020449  mov     rdi, rax
0x18002044c  sub     rdx, [rsi]
0x18002044f  sar     rdx, 3
0x180020453  test    rdx, rdx
0x180020456  jz      short loc_180020464
0x180020458  mov     rcx, [rsi]
0x18002045b  shl     rdx, 3
0x18002045f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180020464  lea     rax, [rdi+rbp*8]
0x180020468  mov     [rsi], rdi
0x18002046b  mov     [rsi+8], rax
0x18002046f  mov     [rsi+10h], rax
0x180020473  jmp     short loc_18002047C
0x180020475  mov     [rdi], rbx
0x180020478  add     rdi, 8
0x18002047c  cmp     rdi, rax
0x18002047f  jnz     short loc_180020475
0x180020481  jmp     short loc_180020490
0x180020483  mov     rcx, [rcx]
0x180020486  lea     r8, [rsp+48h+arg_10]
0x18002048b  call    ??$fill@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@V12@@std@@YAXQEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIIoPacket@Avenc@Rdp@@V?$com_ptr_t@VCIoPacket@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@0@0AEBV10@@Z; std::fill<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>> * const,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<Rdp::Avenc::IIoPacket * const,wil::com_ptr_t<CIoPacket,wil::err_exception_policy>>>>> const &)
0x180020490  add     rsp, 28h
0x180020494  pop     rdi
0x180020495  pop     rsi
0x180020496  pop     rbp
0x180020497  pop     rbx
0x180020498  retn
```
