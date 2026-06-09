# CacheGetItem

- ea: `0x1800296c0`
- end: `0x180029760`
- name: `CacheGetItem`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002835c`
- `0x18002896c`
- `0x180028c88`

## callees

- `0x1800296c0`
- `0x180029768`
- `0x18002982c`
- `0x18002cf46`
- `0x18002cfa0`

## pseudocode

```c
unsigned int __fastcall CacheGetItem(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // eax
  int v7; // edx
  __int64 i; // rbx
  UCHAR Buf2[32]; // [rsp+20h] [rbp-38h] BYREF

  v6 = I_CacheHashKeys(a2, a2, Buf2);
  if ( v6 )
    return errcntrctlib::WIN32_FROM_NTSTATUS((errcntrctlib *)v6, v7);
  for ( i = *(_QWORD *)(a1 + 8LL * (Buf2[0] & 0xF)); ; i = *(_QWORD *)(i + 16) )
  {
    if ( !i )
      return 1168;
    if ( !memcmp_0((const void *)(i + 24), Buf2, 0x20u) )
      break;
  }
  if ( !*(_QWORD *)(i + 8) || !*(_DWORD *)i )
    return 1168;
  *(_DWORD *)a4 = *(_DWORD *)i;
  *(_QWORD *)(a4 + 8) = *(_QWORD *)(i + 8);
  return 0;
}

```

## disassembly

```asm
0x1800296c0  mov     [rsp+arg_0], rbx
0x1800296c5  push    rdi
0x1800296c6  sub     rsp, 50h
0x1800296ca  mov     rax, cs:__security_cookie
0x1800296d1  xor     rax, rsp
0x1800296d4  mov     [rsp+58h+var_18], rax
0x1800296d9  mov     rbx, rcx
0x1800296dc  lea     r8, [rsp+58h+Buf2]
0x1800296e1  mov     rcx, rdx
0x1800296e4  mov     rdi, r9
0x1800296e7  call    I_CacheHashKeys
0x1800296ec  test    eax, eax
0x1800296ee  jz      short loc_1800296F9
0x1800296f0  mov     ecx, eax; this
0x1800296f2  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x1800296f7  jmp     short loc_18002972D
0x1800296f9  movzx   eax, [rsp+58h+Buf2]
0x1800296fe  and     eax, 0Fh
0x180029701  mov     rbx, [rbx+rax*8]
0x180029705  jmp     short loc_180029723
0x180029707  lea     rcx, [rbx+18h]; Buf1
0x18002970b  mov     r8d, 20h ; ' '; Size
0x180029711  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180029716  call    memcmp_0
0x18002971b  test    eax, eax
0x18002971d  jz      short loc_180029745
0x18002971f  mov     rbx, [rbx+10h]
0x180029723  test    rbx, rbx
0x180029726  jnz     short loc_180029707
0x180029728  mov     eax, 490h
0x18002972d  mov     rcx, [rsp+58h+var_18]
0x180029732  xor     rcx, rsp; StackCookie
0x180029735  call    __security_check_cookie
0x18002973a  mov     rbx, [rsp+58h+arg_0]
0x18002973f  add     rsp, 50h
0x180029743  pop     rdi
0x180029744  retn
0x180029745  cmp     qword ptr [rbx+8], 0
0x18002974a  jz      short loc_180029728
0x18002974c  mov     eax, [rbx]
0x18002974e  test    eax, eax
0x180029750  jz      short loc_180029728
0x180029752  mov     [rdi], eax
0x180029754  mov     rax, [rbx+8]
0x180029758  mov     [rdi+8], rax
0x18002975c  xor     eax, eax
0x18002975e  jmp     short loc_18002972D
```
