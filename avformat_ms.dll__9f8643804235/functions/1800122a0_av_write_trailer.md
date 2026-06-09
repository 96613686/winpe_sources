# av_write_trailer

- ea: `0x1800122a0`
- end: `0x180012433`
- name: `av_write_trailer`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180003fb0`
- `0x180005290`
- `0x1800122a0`
- `0x180013d48`
- `0x18001436c`
- `0x18001b9f6`
- `0x18001bba6`
- `0x18001bbbe`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall av_write_trailer(__int64 a1)
{
  __int64 v1; // rbp
  __int64 v2; // rsi
  __int64 i; // rbx
  __int64 v5; // rdx
  int v6; // r14d
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rax
  void (__fastcall *v12)(__int64); // rax
  __int64 v13; // rcx
  __int64 j; // rbp

  v1 = *(_QWORD *)(a1 + 504);
  LODWORD(v2) = 0;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 44); i = (unsigned int)(i + 1) )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * i);
    if ( *(_QWORD *)(v5 + 232) )
    {
      v6 = sub_18001436C(a1, v5, v1, 1);
      if ( v6 < 0 )
      {
        _mm_lfence();
        av_packet_unref(v1);
      }
      if ( (int)v2 >= 0 )
        LODWORD(v2) = v6;
    }
  }
  v7 = sub_180013D48(a1, v1, 1);
  if ( (int)v2 >= 0 )
    LODWORD(v2) = v7;
  v8 = *(_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(v8 + 88) )
  {
    if ( (*(_BYTE *)(v8 + 44) & 1) == 0 )
    {
      v9 = *(_QWORD *)(a1 + 32);
      if ( v9 )
        avio_write_marker(v9, 0x8000000000000000uLL, 4);
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 16) + 88LL))(a1);
    if ( (int)v2 >= 0 )
      LODWORD(v2) = v10;
  }
  v11 = *(_QWORD *)(a1 + 16);
  if ( v11 )
  {
    v12 = *(void (__fastcall **)(__int64))(v11 + 152);
    if ( v12 )
    {
      if ( *(_DWORD *)(a1 + 544) )
        v12(a1);
    }
  }
  v13 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 544) = 0;
  if ( v13 )
    avio_flush(v13);
  if ( !(_DWORD)v2 )
  {
    v2 = *(_QWORD *)(a1 + 32);
    if ( v2 )
      LODWORD(v2) = *(_DWORD *)(v2 + 84);
  }
  for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 44); j = (unsigned int)(j + 1) )
  {
    av_freep(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * j) + 24LL);
    av_freep(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 8 * j) + 320LL);
  }
  if ( *(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL) )
    av_opt_free(*(_QWORD *)(a1 + 24));
  av_freep(a1 + 24);
  av_packet_unref(*(_QWORD *)(a1 + 512));
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800122a0  mov     rax, rsp
0x1800122a3  mov     [rax+8], rbx
0x1800122a7  mov     [rax+10h], rbp
0x1800122ab  mov     [rax+18h], rsi
0x1800122af  mov     [rax+20h], rdi
0x1800122b3  push    r14
0x1800122b5  sub     rsp, 20h
0x1800122b9  mov     rbp, [rcx+1F8h]
0x1800122c0  xor     esi, esi
0x1800122c2  xor     ebx, ebx
0x1800122c4  mov     rdi, rcx
0x1800122c7  cmp     [rcx+2Ch], ebx
0x1800122ca  jbe     short loc_18001230E
0x1800122cc  mov     rax, [rdi+30h]
0x1800122d0  mov     rdx, [rax+rbx*8]
0x1800122d4  cmp     qword ptr [rdx+0E8h], 0
0x1800122dc  jz      short loc_180012307
0x1800122de  mov     r9d, 1
0x1800122e4  mov     r8, rbp
0x1800122e7  mov     rcx, rdi
0x1800122ea  call    sub_18001436C
0x1800122ef  mov     r14d, eax
0x1800122f2  test    eax, eax
0x1800122f4  jns     short loc_180012301
0x1800122f6  lfence
0x1800122f9  mov     rcx, rbp
0x1800122fc  call    av_packet_unref
0x180012301  test    esi, esi
0x180012303  cmovns  esi, r14d
0x180012307  inc     ebx
0x180012309  cmp     ebx, [rdi+2Ch]
0x18001230c  jb      short loc_1800122CC
0x18001230e  xor     r9d, r9d
0x180012311  mov     rdx, rbp
0x180012314  mov     rcx, rdi
0x180012317  lea     r8d, [r9+1]
0x18001231b  call    sub_180013D48
0x180012320  test    esi, esi
0x180012322  cmovns  esi, eax
0x180012325  mov     rax, [rdi+10h]
0x180012329  cmp     qword ptr [rax+58h], 0
0x18001232e  jz      short loc_18001236A
0x180012330  test    byte ptr [rax+2Ch], 1
0x180012334  jnz     short loc_180012354
0x180012336  mov     rcx, [rdi+20h]
0x18001233a  test    rcx, rcx
0x18001233d  jz      short loc_180012354
0x18001233f  mov     rdx, 8000000000000000h
0x180012349  mov     r8d, 4
0x18001234f  call    avio_write_marker
0x180012354  mov     rax, [rdi+10h]
0x180012358  mov     rcx, rdi
0x18001235b  mov     rax, [rax+58h]
0x18001235f  call    cs:__guard_dispatch_icall_fptr
0x180012365  test    esi, esi
0x180012367  cmovns  esi, eax
0x18001236a  mov     rax, [rdi+10h]
0x18001236e  test    rax, rax
0x180012371  jz      short loc_180012391
0x180012373  mov     rax, [rax+98h]
0x18001237a  test    rax, rax
0x18001237d  jz      short loc_180012391
0x18001237f  cmp     dword ptr [rdi+220h], 0
0x180012386  jz      short loc_180012391
0x180012388  mov     rcx, rdi
0x18001238b  call    cs:__guard_dispatch_icall_fptr
0x180012391  mov     rcx, [rdi+20h]
0x180012395  mov     qword ptr [rdi+220h], 0
0x1800123a0  test    rcx, rcx
0x1800123a3  jz      short loc_1800123AA
0x1800123a5  call    avio_flush
0x1800123aa  test    esi, esi
0x1800123ac  jnz     short loc_1800123BA
0x1800123ae  mov     rsi, [rdi+20h]
0x1800123b2  test    rsi, rsi
0x1800123b5  jz      short loc_1800123BA
0x1800123b7  mov     esi, [rsi+54h]
0x1800123ba  xor     ebp, ebp
0x1800123bc  cmp     [rdi+2Ch], ebp
0x1800123bf  jbe     short loc_1800123ED
0x1800123c1  mov     rax, [rdi+30h]
0x1800123c5  mov     rcx, [rax+rbp*8]
0x1800123c9  add     rcx, 18h
0x1800123cd  call    av_freep
0x1800123d2  mov     rax, [rdi+30h]
0x1800123d6  mov     rcx, [rax+rbp*8]
0x1800123da  add     rcx, 140h
0x1800123e1  call    av_freep
0x1800123e6  inc     ebp
0x1800123e8  cmp     ebp, [rdi+2Ch]
0x1800123eb  jb      short loc_1800123C1
0x1800123ed  mov     rdx, [rdi+10h]
0x1800123f1  cmp     qword ptr [rdx+38h], 0
0x1800123f6  jz      short loc_180012401
0x1800123f8  mov     rcx, [rdi+18h]
0x1800123fc  call    av_opt_free
0x180012401  lea     rcx, [rdi+18h]
0x180012405  call    av_freep
0x18001240a  mov     rcx, [rdi+200h]
0x180012411  call    av_packet_unref
0x180012416  mov     rbx, [rsp+28h+arg_0]
0x18001241b  mov     eax, esi
0x18001241d  mov     rsi, [rsp+28h+arg_10]
0x180012422  mov     rbp, [rsp+28h+arg_8]
0x180012427  mov     rdi, [rsp+28h+arg_18]
0x18001242c  add     rsp, 20h
0x180012430  pop     r14
0x180012432  retn
```
