# CRegistry::operator=(CRegistry const &)

- ea: `0x140011d40`
- end: `0x140011e16`
- name: `??4CRegistry@@QEAAAEAV0@AEBV0@@Z`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000ffc0`
- `0x140011d40`

## pseudocode

```c
__int64 __fastcall CRegistry::operator=(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx

  *(_QWORD *)a1 = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
  CHString::operator=((const unsigned __int16 **)(a1 + 24), (const unsigned __int16 **)(a2 + 24));
  v4 = 19;
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 32);
  v5 = 260;
  *(_BYTE *)(a1 + 36) = *(_BYTE *)(a2 + 36);
  do
  {
    *(_WORD *)(a1 + 2 * v4) = *(_WORD *)(a2 + 2 * v4);
    ++v4;
    --v5;
  }
  while ( v5 );
  *(_DWORD *)(a1 + 560) = *(_DWORD *)(a2 + 560);
  *(_DWORD *)(a1 + 564) = *(_DWORD *)(a2 + 564);
  *(_DWORD *)(a1 + 568) = *(_DWORD *)(a2 + 568);
  *(_DWORD *)(a1 + 572) = *(_DWORD *)(a2 + 572);
  *(_DWORD *)(a1 + 576) = *(_DWORD *)(a2 + 576);
  *(_DWORD *)(a1 + 580) = *(_DWORD *)(a2 + 580);
  *(_DWORD *)(a1 + 584) = *(_DWORD *)(a2 + 584);
  *(_DWORD *)(a1 + 588) = *(_DWORD *)(a2 + 588);
  *(_QWORD *)(a1 + 592) = *(_QWORD *)(a2 + 592);
  return a1;
}

```

## disassembly

```asm
0x140011d40  mov     [rsp+arg_0], rbx
0x140011d45  push    rdi
0x140011d46  sub     rsp, 20h
0x140011d4a  mov     rax, [rdx]
0x140011d4d  mov     rdi, rdx
0x140011d50  mov     [rcx], rax
0x140011d53  mov     rbx, rcx
0x140011d56  mov     rax, [rdx+8]
0x140011d5a  mov     [rcx+8], rax
0x140011d5e  mov     rax, [rdx+10h]
0x140011d62  add     rdx, 18h
0x140011d66  mov     [rcx+10h], rax
0x140011d6a  add     rcx, 18h; this
0x140011d6e  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x140011d73  mov     eax, [rdi+20h]
0x140011d76  mov     ecx, 13h
0x140011d7b  mov     [rbx+20h], eax
0x140011d7e  mov     edx, 104h
0x140011d83  mov     al, [rdi+24h]
0x140011d86  mov     [rbx+24h], al
0x140011d89  movzx   eax, word ptr [rdi+rcx*2]
0x140011d8d  mov     [rbx+rcx*2], ax
0x140011d91  inc     rcx
0x140011d94  sub     rdx, 1
0x140011d98  jnz     short loc_140011D89
0x140011d9a  mov     eax, [rdi+230h]
0x140011da0  mov     [rbx+230h], eax
0x140011da6  mov     eax, [rdi+234h]
0x140011dac  mov     [rbx+234h], eax
0x140011db2  mov     eax, [rdi+238h]
0x140011db8  mov     [rbx+238h], eax
0x140011dbe  mov     eax, [rdi+23Ch]
0x140011dc4  mov     [rbx+23Ch], eax
0x140011dca  mov     eax, [rdi+240h]
0x140011dd0  mov     [rbx+240h], eax
0x140011dd6  mov     eax, [rdi+244h]
0x140011ddc  mov     [rbx+244h], eax
0x140011de2  mov     eax, [rdi+248h]
0x140011de8  mov     [rbx+248h], eax
0x140011dee  mov     eax, [rdi+24Ch]
0x140011df4  mov     [rbx+24Ch], eax
0x140011dfa  mov     rax, [rdi+250h]
0x140011e01  mov     [rbx+250h], rax
0x140011e08  mov     rax, rbx
0x140011e0b  mov     rbx, [rsp+28h+arg_0]
0x140011e10  add     rsp, 20h
0x140011e14  pop     rdi
0x140011e15  retn
```
