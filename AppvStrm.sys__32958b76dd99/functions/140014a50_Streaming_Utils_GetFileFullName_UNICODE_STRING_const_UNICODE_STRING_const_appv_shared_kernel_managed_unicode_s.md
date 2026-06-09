# Streaming::Utils::GetFileFullName(_UNICODE_STRING const &,_UNICODE_STRING const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &)

- ea: `0x140014a50`
- end: `0x140014af9`
- name: `?GetFileFullName@Utils@Streaming@@YAJAEBU_UNICODE_STRING@@0AEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1400020c8`
- `0x140007c24`
- `0x1400084b0`
- `0x140008bdc`
- `0x140008dc4`
- `0x14000935c`
- `0x140011f30`

## callees

- `0x140003408`
- `0x1400034fc`
- `0x1400147fc`
- `0x140014a50`
- `0x1400153c4`
- `0x140015b30`

## pseudocode

```c
__int64 __fastcall Streaming::Utils::GetFileFullName(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // esi
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *v7; // rdi
  _BYTE v9[8]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-10h]

  v5 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(
         a3,
         a1);
  if ( v5 < 0
    || (v5 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(a3, a2),
        v5 < 0) )
  {
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v9);
    LogWrite(1, *CurrentActivityID, L"Utils::GetFileFullName() - Low memory error.");
    v7 = v10;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140014a50  mov     [rsp+arg_0], rbx
0x140014a55  mov     [rsp+arg_8], rsi
0x140014a5a  push    rdi
0x140014a5b  sub     rsp, 30h
0x140014a5f  mov     rdi, rdx
0x140014a62  mov     rbx, r8
0x140014a65  mov     rdx, rcx
0x140014a68  mov     rcx, r8
0x140014a6b  call    ?build_managed_unicode_string@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::build_managed_unicode_string(_UNICODE_STRING const &)
0x140014a70  mov     esi, eax
0x140014a72  test    eax, eax
0x140014a74  js      short loc_140014A87
0x140014a76  mov     rdx, rdi
0x140014a79  mov     rcx, rbx
0x140014a7c  call    ?append@?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator>::append(_UNICODE_STRING const &)
0x140014a81  mov     esi, eax
0x140014a83  test    eax, eax
0x140014a85  jns     short loc_140014AE6
0x140014a87  lea     rcx, [rsp+38h+var_18]
0x140014a8c  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x140014a91  lea     r8, aUtilsGetfilefu; "Utils::GetFileFullName() - Low memory e"...
0x140014a98  mov     ecx, 1
0x140014a9d  mov     rdx, [rax]
0x140014aa0  call    LogWrite
0x140014aa5  mov     rdi, [rsp+38h+var_10]
0x140014aaa  test    rdi, rdi
0x140014aad  jz      short loc_140014AE6
0x140014aaf  or      ebx, 0FFFFFFFFh
0x140014ab2  mov     eax, ebx
0x140014ab4  lock xadd [rdi+8], eax
0x140014ab9  add     eax, ebx
0x140014abb  jnz     short loc_140014AE6
0x140014abd  mov     rax, [rdi]
0x140014ac0  mov     rcx, rdi
0x140014ac3  mov     rax, [rax+8]
0x140014ac7  call    _guard_dispatch_icall
0x140014acc  mov     eax, ebx
0x140014ace  lock xadd [rdi+0Ch], eax
0x140014ad3  add     eax, ebx
0x140014ad5  jnz     short loc_140014AE6
0x140014ad7  mov     rax, [rdi]
0x140014ada  mov     rcx, rdi
0x140014add  mov     rax, [rax+10h]
0x140014ae1  call    _guard_dispatch_icall
0x140014ae6  mov     rbx, [rsp+38h+arg_0]
0x140014aeb  mov     eax, esi
0x140014aed  mov     rsi, [rsp+38h+arg_8]
0x140014af2  add     rsp, 30h
0x140014af6  pop     rdi
0x140014af7  retn
```
