# Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)

- ea: `0x140014b00`
- end: `0x140014c38`
- name: `?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z`
- size: `312`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int16 *)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140001aa0`
- `0x1400020c8`
- `0x140007c24`
- `0x140007fe4`
- `0x1400084b0`
- `0x1400086a8`
- `0x140008bdc`
- `0x140008dc4`
- `0x14000935c`
- `0x14000984c`
- `0x140009d98`
- `0x14000a1f0`
- `0x14000a310`
- `0x14000abd8`
- `0x14000b0bc`
- `0x14000b32c`
- `0x14000b448`
- `0x14000b748`
- `0x14000bfe4`
- `0x14000c2ac`
- `0x14000c4ac`
- `0x14000d5a8`
- `0x14000f244`
- `0x140011f30`
- `0x140012b18`
- `0x140014dcc`

## callees

- `0x140014b00`
- `0x140015b30`
- `0x140015c00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140014bbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014bbe`
- `ntoskrnl!ExAllocatePool2` at `0x140014b39`
- `ntoskrnl!ExAllocatePool2` at `0x140014b55`
- `ntoskrnl!ExAllocatePool2` at `0x140014b39`
- `ntoskrnl!ExAllocatePool2` at `0x140014b55`

## pseudocode

```c
_QWORD *__fastcall Streaming::Utils::GetNullTerminated(_QWORD *a1, unsigned __int16 *a2)
{
  void *Pool2; // rsi
  __int64 v5; // rax
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rdi

  if ( !a2 || !*((_QWORD *)a2 + 1) )
  {
    *a1 = 0;
    a1[1] = 0;
    return a1;
  }
  Pool2 = (void *)ExAllocatePool2(256, *a2 + 2LL, 1937073779);
  v5 = ExAllocatePool2(256, 24, 1715758931);
  v6 = (volatile signed __int32 *)v5;
  if ( v5 )
  {
    *(_DWORD *)(v5 + 8) = 1;
    v7 = v5 + 8;
    *(_DWORD *)(v5 + 12) = 1;
    *(_QWORD *)v5 = &kernel_std::detail::sp_counted_impl_p<wchar_t>::`vftable';
    *(_QWORD *)(v5 + 16) = Pool2;
    if ( *(_DWORD *)(v5 + 8) )
    {
      if ( Pool2 )
      {
        memmove(Pool2, *((const void **)a2 + 1), *a2);
        *((_WORD *)Pool2 + ((unsigned __int64)*a2 >> 1)) = 0;
      }
      goto LABEL_11;
    }
  }
  else
  {
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    v7 = 8;
    v6 = 0;
  }
  Pool2 = 0;
LABEL_11:
  *a1 = Pool2;
  a1[1] = v6;
  if ( v6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v7);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140014b00  push    rbx
0x140014b02  push    rbp
0x140014b03  push    rsi
0x140014b04  push    rdi
0x140014b05  push    r14
0x140014b07  sub     rsp, 20h
0x140014b0b  mov     rbp, rdx
0x140014b0e  mov     r14, rcx
0x140014b11  test    rdx, rdx
0x140014b14  jz      loc_140014C1A
0x140014b1a  cmp     qword ptr [rdx+8], 0
0x140014b1f  jz      loc_140014C1A
0x140014b25  movzx   edx, word ptr [rdx]
0x140014b28  mov     ebx, 100h
0x140014b2d  add     rdx, 2
0x140014b31  mov     ecx, ebx
0x140014b33  mov     r8d, 73756673h
0x140014b39  call    cs:__imp_ExAllocatePool2
0x140014b40  nop     dword ptr [rax+rax+00h]
0x140014b45  mov     edx, 18h
0x140014b4a  mov     r8d, 66446753h
0x140014b50  mov     ecx, ebx
0x140014b52  mov     rsi, rax
0x140014b55  call    cs:__imp_ExAllocatePool2
0x140014b5c  nop     dword ptr [rax+rax+00h]
0x140014b61  mov     rbx, rax
0x140014b64  test    rax, rax
0x140014b67  jz      short loc_140014BB4
0x140014b69  mov     dword ptr [rax+8], 1
0x140014b70  lea     rdi, [rbx+8]
0x140014b74  mov     dword ptr [rax+0Ch], 1
0x140014b7b  lea     rax, ??_7?$sp_counted_impl_p@_W@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<wchar_t>::`vftable'
0x140014b82  mov     [rbx], rax
0x140014b85  mov     [rbx+10h], rsi
0x140014b89  mov     eax, [rdi]
0x140014b8b  test    eax, eax
0x140014b8d  jz      short loc_140014BD1
0x140014b8f  test    rsi, rsi
0x140014b92  jz      short loc_140014BD3
0x140014b94  movzx   r8d, word ptr [rbp+0]; Size
0x140014b99  mov     rcx, rsi; void *
0x140014b9c  mov     rdx, [rbp+8]; Src
0x140014ba0  call    memmove
0x140014ba5  movzx   ecx, word ptr [rbp+0]
0x140014ba9  shr     rcx, 1
0x140014bac  xor     eax, eax
0x140014bae  mov     [rsi+rcx*2], ax
0x140014bb2  jmp     short loc_140014BD3
0x140014bb4  test    rsi, rsi
0x140014bb7  jz      short loc_140014BCA
0x140014bb9  xor     edx, edx; Tag
0x140014bbb  mov     rcx, rsi; P
0x140014bbe  call    cs:__imp_ExFreePoolWithTag
0x140014bc5  nop     dword ptr [rax+rax+00h]
0x140014bca  mov     edi, 8
0x140014bcf  xor     ebx, ebx
0x140014bd1  xor     esi, esi
0x140014bd3  mov     [r14], rsi
0x140014bd6  mov     [r14+8], rbx
0x140014bda  test    rbx, rbx
0x140014bdd  jz      short loc_140014C29
0x140014bdf  lock inc dword ptr [rdi]
0x140014be2  or      esi, 0FFFFFFFFh
0x140014be5  mov     eax, esi
0x140014be7  lock xadd [rdi], eax
0x140014beb  add     eax, esi
0x140014bed  jnz     short loc_140014C29
0x140014bef  mov     rax, [rbx]
0x140014bf2  mov     rcx, rbx
0x140014bf5  mov     rax, [rax+8]
0x140014bf9  call    _guard_dispatch_icall
0x140014bfe  mov     eax, esi
0x140014c00  lock xadd [rbx+0Ch], eax
0x140014c05  add     eax, esi
0x140014c07  jnz     short loc_140014C29
0x140014c09  mov     rax, [rbx]
0x140014c0c  mov     rcx, rbx
0x140014c0f  mov     rax, [rax+10h]
0x140014c13  call    _guard_dispatch_icall
0x140014c18  jmp     short loc_140014C29
0x140014c1a  mov     qword ptr [rcx], 0
0x140014c21  mov     qword ptr [rcx+8], 0
0x140014c29  mov     rax, r14
0x140014c2c  add     rsp, 20h
0x140014c30  pop     r14
0x140014c32  pop     rdi
0x140014c33  pop     rsi
0x140014c34  pop     rbp
0x140014c35  pop     rbx
0x140014c36  retn
```
