# avio_read_to_bprint

- ea: `0x180004870`
- end: `0x180004915`
- name: `avio_read_to_bprint`
- size: `165`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004660`
- `0x180004870`
- `0x18001bc2a`
- `0x18001bed0`

## pseudocode

```c
__int64 __fastcall avio_read_to_bprint(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 i; // rdi
  __int64 v6; // r8
  __int64 result; // rax
  __int64 v8; // rbx
  _BYTE v9[1024]; // [rsp+20h] [rbp-438h] BYREF

  for ( i = a3; i; i -= v8 )
  {
    v6 = (unsigned int)i;
    if ( i > 0x400 )
      v6 = 1024;
    LODWORD(result) = avio_read(a1, v9, v6);
    v8 = (int)result;
    if ( (_DWORD)result == -541478725 )
      break;
    _mm_lfence();
    if ( (int)result <= 0 )
      return (unsigned int)result;
    av_bprint_append_data(a2, v9, (unsigned int)result);
    if ( *(_DWORD *)(a2 + 8) >= *(_DWORD *)(a2 + 12) )
      return 4294967284LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180004870  push    rbx
0x180004872  push    rbp
0x180004873  push    rsi
0x180004874  push    rdi
0x180004875  push    r14
0x180004877  sub     rsp, 430h
0x18000487e  mov     rax, cs:__security_cookie
0x180004885  xor     rax, rsp
0x180004888  mov     [rsp+458h+var_38], rax
0x180004890  mov     rdi, r8
0x180004893  mov     rsi, rdx
0x180004896  mov     rbp, rcx
0x180004899  test    r8, r8
0x18000489c  jz      short loc_1800048EA
0x18000489e  mov     r14d, 400h
0x1800048a4  mov     r8d, edi
0x1800048a7  lea     rdx, [rsp+458h+var_438]
0x1800048ac  cmp     rdi, r14
0x1800048af  mov     rcx, rbp
0x1800048b2  cmova   r8d, r14d
0x1800048b6  call    avio_read
0x1800048bb  movsxd  rbx, eax
0x1800048be  cmp     ebx, 0DFB9B0BBh
0x1800048c4  jz      short loc_1800048EA
0x1800048c6  lfence
0x1800048c9  test    eax, eax
0x1800048cb  jle     short loc_180004911
0x1800048cd  mov     r8d, ebx
0x1800048d0  lea     rdx, [rsp+458h+var_438]
0x1800048d5  mov     rcx, rsi
0x1800048d8  call    av_bprint_append_data
0x1800048dd  mov     ecx, [rsi+0Ch]
0x1800048e0  cmp     [rsi+8], ecx
0x1800048e3  jnb     short loc_18000490A
0x1800048e5  sub     rdi, rbx
0x1800048e8  jnz     short loc_1800048A4
0x1800048ea  xor     eax, eax
0x1800048ec  mov     rcx, [rsp+458h+var_38]
0x1800048f4  xor     rcx, rsp; StackCookie
0x1800048f7  call    __security_check_cookie
0x1800048fc  add     rsp, 430h
0x180004903  pop     r14
0x180004905  pop     rdi
0x180004906  pop     rsi
0x180004907  pop     rbp
0x180004908  pop     rbx
0x180004909  retn
0x18000490a  mov     eax, 0FFFFFFF4h
0x18000490f  jmp     short loc_1800048EC
0x180004911  mov     eax, ebx
0x180004913  jmp     short loc_1800048EC
```
