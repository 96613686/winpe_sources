# CacheDeleteItem

- ea: `0x180029578`
- end: `0x18002962e`
- name: `CacheDeleteItem`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800281b8`

## callees

- `0x18000de80`
- `0x180029578`
- `0x180029768`
- `0x18002982c`
- `0x18002cf46`
- `0x18002cfa0`

## pseudocode

```c
unsigned int __fastcall CacheDeleteItem(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax
  int v4; // edx
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rax
  UCHAR Buf2[32]; // [rsp+20h] [rbp-48h] BYREF

  v3 = I_CacheHashKeys(a2, a2, Buf2);
  if ( v3 )
    return errcntrctlib::WIN32_FROM_NTSTATUS((errcntrctlib *)v3, v4);
  v6 = Buf2[0] & 0xF;
  v7 = *(_QWORD *)(a1 + 8 * v6);
  if ( !v7 )
    return 1168;
  v8 = 0;
  while ( memcmp_0((const void *)(v7 + 24), Buf2, 0x20u) )
  {
    v8 = v7;
    v7 = *(_QWORD *)(v7 + 16);
    if ( !v7 )
      return 1168;
  }
  v9 = *(_QWORD *)(v7 + 16);
  if ( v8 )
    *(_QWORD *)(v8 + 16) = v9;
  else
    *(_QWORD *)(a1 + 8 * v6) = v9;
  CspFreeH(v7);
  --*(_DWORD *)(a1 + 128);
  return 0;
}

```

## disassembly

```asm
0x180029578  mov     [rsp+arg_10], rbx
0x18002957d  push    rbp
0x18002957e  push    rsi
0x18002957f  push    rdi
0x180029580  sub     rsp, 50h
0x180029584  mov     rax, cs:__security_cookie
0x18002958b  xor     rax, rsp
0x18002958e  mov     [rsp+68h+var_28], rax
0x180029593  mov     rsi, rcx
0x180029596  lea     r8, [rsp+68h+Buf2]
0x18002959b  mov     rcx, rdx
0x18002959e  call    I_CacheHashKeys
0x1800295a3  test    eax, eax
0x1800295a5  jz      short loc_1800295B0
0x1800295a7  mov     ecx, eax; this
0x1800295a9  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x1800295ae  jmp     short loc_1800295EC
0x1800295b0  movzx   edi, [rsp+68h+Buf2]
0x1800295b5  and     edi, 0Fh
0x1800295b8  mov     rbx, [rsi+rdi*8]
0x1800295bc  test    rbx, rbx
0x1800295bf  jz      short loc_1800295E7
0x1800295c1  xor     ebp, ebp
0x1800295c3  lea     rcx, [rbx+18h]; Buf1
0x1800295c7  mov     r8d, 20h ; ' '; Size
0x1800295cd  lea     rdx, [rsp+68h+Buf2]; Buf2
0x1800295d2  call    memcmp_0
0x1800295d7  test    eax, eax
0x1800295d9  jz      short loc_180029609
0x1800295db  mov     rbp, rbx
0x1800295de  mov     rbx, [rbx+10h]
0x1800295e2  test    rbx, rbx
0x1800295e5  jnz     short loc_1800295C3
0x1800295e7  mov     eax, 490h
0x1800295ec  mov     rcx, [rsp+68h+var_28]
0x1800295f1  xor     rcx, rsp; StackCookie
0x1800295f4  call    __security_check_cookie
0x1800295f9  mov     rbx, [rsp+68h+arg_10]
0x180029601  add     rsp, 50h
0x180029605  pop     rdi
0x180029606  pop     rsi
0x180029607  pop     rbp
0x180029608  retn
0x180029609  mov     rax, [rbx+10h]
0x18002960d  test    rbp, rbp
0x180029610  jnz     short loc_180029618
0x180029612  mov     [rsi+rdi*8], rax
0x180029616  jmp     short loc_18002961C
0x180029618  mov     [rbp+10h], rax
0x18002961c  mov     rcx, rbx
0x18002961f  call    CspFreeH
0x180029624  dec     dword ptr [rsi+80h]
0x18002962a  xor     eax, eax
0x18002962c  jmp     short loc_1800295EC
```
