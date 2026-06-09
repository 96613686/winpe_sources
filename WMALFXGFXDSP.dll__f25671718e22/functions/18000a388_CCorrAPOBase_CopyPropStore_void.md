# CCorrAPOBase::CopyPropStore(void)

- ea: `0x18000a388`
- end: `0x18000a4e3`
- name: `?CopyPropStore@CCorrAPOBase@@QEAAJXZ`
- size: `347`
- prototype: `__int64 __fastcall(CCorrAPOBase *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800090e0`
- `0x180076c4c`

## callees

- `0x18000a388`
- `0x180012658`
- `0x180015190`
- `0x180016ab5`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a4db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a4db`

## pseudocode

```c
__int64 __fastcall CCorrAPOBase::CopyPropStore(CCorrAPOBase *this)
{
  unsigned int i; // edi
  __int64 v4; // rcx
  __int64 *v5; // rsi
  __int128 v6; // xmm0
  int v7; // esi
  PROPVARIANT pvar; // [rsp+20h] [rbp-40h] BYREF
  __int128 Buf2; // [rsp+38h] [rbp-28h] BYREF
  int v10; // [rsp+48h] [rbp-18h]

  if ( *((_QWORD *)this + 46) )
  {
    for ( i = 0; i < 0x11; ++i )
    {
      v4 = 12LL * (int)i;
      if ( !*(_DWORD *)(*((_QWORD *)this + 2) + v4 * 8 + 88) )
      {
        v5 = &qword_1801B85A0[v4];
        if ( memcmp_0(&xmmword_18008F558, &qword_1801B85A0[v4], 0x10u) )
        {
          if ( memcmp_0(&xmmword_18008F588, v5, 0x10u) )
          {
            v6 = *(_OWORD *)v5;
            v7 = *((_DWORD *)this + 96);
            v10 = v7;
            Buf2 = v6;
            memset(&pvar, 0, sizeof(pvar));
            if ( *((_DWORD *)this + 37)
              && (!memcmp_0(&xmmword_18008F570, &Buf2, 0x10u) || !memcmp_0(&xmmword_18008F5A0, &Buf2, 0x10u)) )
            {
              v10 = v7 + 1;
            }
            if ( (*(int (__fastcall **)(_QWORD, __int128 *, PROPVARIANT *))(**((_QWORD **)this + 46) + 40LL))(
                   *((_QWORD *)this + 46),
                   &Buf2,
                   &pvar) >= 0
              && pvar.vt )
            {
              CCorrAPOBase::IntermediateSetValue(this, i, &pvar);
              PropVariantClear(&pvar);
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a388  mov     [rsp-18h+arg_8], rbx
0x18000a38d  mov     [rsp-18h+arg_10], rsi
0x18000a392  push    rbp
0x18000a393  push    rdi
0x18000a394  push    r15
0x18000a396  mov     rbp, rsp
0x18000a399  sub     rsp, 60h
0x18000a39d  mov     rax, cs:__security_cookie
0x18000a3a4  xor     rax, rsp
0x18000a3a7  mov     [rbp+var_10], rax
0x18000a3ab  cmp     qword ptr [rcx+170h], 0
0x18000a3b3  mov     rbx, rcx
0x18000a3b6  jnz     short loc_18000A3DB
0x18000a3b8  xor     eax, eax
0x18000a3ba  mov     rcx, [rbp+var_10]
0x18000a3be  xor     rcx, rsp; StackCookie
0x18000a3c1  call    __security_check_cookie
0x18000a3c6  lea     r11, [rsp+60h+var_s0]
0x18000a3cb  mov     rbx, [r11+28h]
0x18000a3cf  mov     rsi, [r11+30h]
0x18000a3d3  mov     rsp, r11
0x18000a3d6  pop     r15
0x18000a3d8  pop     rdi
0x18000a3d9  pop     rbp
0x18000a3da  retn
0x18000a3db  xor     edi, edi
0x18000a3dd  lea     r15d, [rdi+10h]
0x18000a3e1  movsxd  rax, edi
0x18000a3e4  lea     rcx, [rax+rax*2]
0x18000a3e8  mov     rax, [rbx+10h]
0x18000a3ec  shl     rcx, 5
0x18000a3f0  cmp     dword ptr [rax+rcx+58h], 0
0x18000a3f5  jnz     loc_18000A4B9
0x18000a3fb  lea     rsi, qword_1801B85A0
0x18000a402  mov     r8, r15; Size
0x18000a405  add     rsi, rcx
0x18000a408  lea     rcx, xmmword_18008F558; Buf1
0x18000a40f  mov     rdx, rsi; Buf2
0x18000a412  call    memcmp_0
0x18000a417  test    eax, eax
0x18000a419  jz      loc_18000A4B9
0x18000a41f  mov     r8, r15; Size
0x18000a422  lea     rcx, xmmword_18008F588; Buf1
0x18000a429  mov     rdx, rsi; Buf2
0x18000a42c  call    memcmp_0
0x18000a431  test    eax, eax
0x18000a433  jz      loc_18000A4B9
0x18000a439  movups  xmm0, xmmword ptr [rsi]
0x18000a43c  mov     esi, [rbx+180h]
0x18000a442  xor     eax, eax
0x18000a444  mov     [rbp+var_18], esi
0x18000a447  movdqu  [rbp+Buf2], xmm0
0x18000a44c  mov     qword ptr [rbp+pvar+10h], rax
0x18000a450  xorps   xmm0, xmm0
0x18000a453  movups  xmmword ptr [rbp+pvar], xmm0
0x18000a457  cmp     [rbx+94h], eax
0x18000a45d  jz      short loc_18000A492
0x18000a45f  mov     r8, r15; Size
0x18000a462  lea     rdx, [rbp+Buf2]; Buf2
0x18000a466  lea     rcx, xmmword_18008F570; Buf1
0x18000a46d  call    memcmp_0
0x18000a472  test    eax, eax
0x18000a474  jz      short loc_18000A48D
0x18000a476  mov     r8, r15; Size
0x18000a479  lea     rdx, [rbp+Buf2]; Buf2
0x18000a47d  lea     rcx, xmmword_18008F5A0; Buf1
0x18000a484  call    memcmp_0
0x18000a489  test    eax, eax
0x18000a48b  jnz     short loc_18000A492
0x18000a48d  inc     esi
0x18000a48f  mov     [rbp+var_18], esi
0x18000a492  mov     rcx, [rbx+170h]
0x18000a499  lea     r8, [rbp+pvar]
0x18000a49d  lea     rdx, [rbp+Buf2]
0x18000a4a1  mov     rax, [rcx]
0x18000a4a4  mov     rax, [rax+28h]
0x18000a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ad  test    eax, eax
0x18000a4af  js      short loc_18000A4B9
0x18000a4b1  xor     eax, eax
0x18000a4b3  cmp     ax, word ptr [rbp+pvar]
0x18000a4b7  jnz     short loc_18000A4C9
0x18000a4b9  inc     edi
0x18000a4bb  cmp     edi, 11h
0x18000a4be  jb      loc_18000A3E1
0x18000a4c4  jmp     loc_18000A3B8
0x18000a4c9  lea     r8, [rbp+pvar]; struct tagPROPVARIANT *
0x18000a4cd  mov     edx, edi; unsigned int
0x18000a4cf  mov     rcx, rbx; this
0x18000a4d2  call    ?IntermediateSetValue@CCorrAPOBase@@IEAAJKAEBUtagPROPVARIANT@@@Z; CCorrAPOBase::IntermediateSetValue(ulong,tagPROPVARIANT const &)
0x18000a4d7  lea     rcx, [rbp+pvar]; pvar
0x18000a4db  call    cs:__imp_PropVariantClear
0x18000a4e1  jmp     short loc_18000A4B9
```
