# fp_format_f_internal

- ea: `0x180057688`
- end: `0x1800577d5`
- name: `fp_format_f_internal`
- size: `333`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, char, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800575b0`
- `0x1800577d8`

## callees

- `0x1800149cc`
- `0x180057688`
- `0x180060270`
- `0x180060630`

## pseudocode

```c
__int64 __fastcall fp_format_f_internal(char *Src, __int64 a2, int a3, __int64 a4, char a5, __crt_cached_ptd_host *a6)
{
  __int64 v7; // rcx
  int v9; // esi
  __int64 v10; // rax
  __int64 v11; // rdi
  bool v12; // al
  __int64 v13; // r8
  char *v14; // rbx
  _BYTE *v15; // r14
  __int64 v16; // r8
  int v17; // eax
  int v18; // eax

  v7 = *(int *)(a4 + 4);
  v9 = a3;
  if ( a5 && (_DWORD)v7 - 1 == a3 )
    *(_WORD *)&Src[(*(_DWORD *)a4 == 45) - 1 + v7] = 48;
  if ( *(_DWORD *)a4 == 45 )
    *Src++ = 45;
  v10 = *(int *)(a4 + 4);
  v11 = -1;
  if ( (int)v10 > 0 )
  {
    v14 = &Src[v10];
  }
  else
  {
    v12 = !(_DWORD)v10 && **(_BYTE **)(a4 + 8) == 48;
    if ( !a5 || !v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( Src[v13] );
      memmove(Src + 1, Src, v13 + 1);
    }
    *Src = 48;
    v14 = Src + 1;
  }
  if ( v9 > 0 )
  {
    v15 = v14 + 1;
    v16 = -1;
    do
      ++v16;
    while ( v14[v16] );
    memmove(v14 + 1, v14, v16 + 1);
    if ( !*((_BYTE *)a6 + 40) )
      __crt_cached_ptd_host::update_locale_slow(a6);
    *v14 = ***(_BYTE ***)(*((_QWORD *)a6 + 3) + 248LL);
    v17 = *(_DWORD *)(a4 + 4);
    if ( v17 < 0 )
    {
      v18 = -v17;
      if ( a5 || v18 < v9 )
        v9 = v18;
      do
        ++v11;
      while ( v15[v11] );
      memmove(&v15[v9], v15, v11 + 1);
      memset(v15, 48, v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180057688  mov     [rsp+arg_0], rbx
0x18005768d  mov     [rsp+arg_8], rbp
0x180057692  mov     [rsp+arg_10], rsi
0x180057697  push    rdi
0x180057698  push    r14
0x18005769a  push    r15
0x18005769c  sub     rsp, 20h
0x1800576a0  cmp     [rsp+38h+arg_20], 0
0x1800576a5  mov     rbx, rcx
0x1800576a8  movsxd  rcx, dword ptr [r9+4]
0x1800576ac  mov     rbp, r9
0x1800576af  mov     esi, r8d
0x1800576b2  jz      short loc_1800576CF
0x1800576b4  lea     eax, [rcx-1]
0x1800576b7  cmp     eax, r8d
0x1800576ba  jnz     short loc_1800576CF
0x1800576bc  xor     eax, eax
0x1800576be  cmp     dword ptr [r9], 2Dh ; '-'
0x1800576c2  setz    al
0x1800576c5  add     rax, rbx
0x1800576c8  mov     word ptr [rcx+rax-1], 30h ; '0'
0x1800576cf  cmp     dword ptr [r9], 2Dh ; '-'
0x1800576d3  jnz     short loc_1800576DB
0x1800576d5  mov     byte ptr [rbx], 2Dh ; '-'
0x1800576d8  inc     rbx
0x1800576db  movsxd  rax, dword ptr [r9+4]
0x1800576df  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800576e3  test    eax, eax
0x1800576e5  jg      short loc_180057727
0x1800576e7  jnz     short loc_1800576F6
0x1800576e9  mov     rax, [r9+8]
0x1800576ed  cmp     byte ptr [rax], 30h ; '0'
0x1800576f0  jnz     short loc_1800576F6
0x1800576f2  mov     al, 1
0x1800576f4  jmp     short loc_1800576F8
0x1800576f6  xor     al, al
0x1800576f8  cmp     [rsp+38h+arg_20], 0
0x1800576fd  jz      short loc_180057703
0x1800576ff  test    al, al
0x180057701  jnz     short loc_18005771F
0x180057703  mov     r8, rdi
0x180057706  inc     r8
0x180057709  cmp     byte ptr [rbx+r8], 0
0x18005770e  jnz     short loc_180057706
0x180057710  inc     r8; Size
0x180057713  lea     rcx, [rbx+1]; void *
0x180057717  mov     rdx, rbx; Src
0x18005771a  call    memmove
0x18005771f  mov     byte ptr [rbx], 30h ; '0'
0x180057722  inc     rbx
0x180057725  jmp     short loc_18005772A
0x180057727  add     rbx, rax
0x18005772a  test    esi, esi
0x18005772c  jle     loc_1800577BA
0x180057732  lea     r14, [rbx+1]
0x180057736  mov     r8, rdi
0x180057739  inc     r8
0x18005773c  cmp     byte ptr [rbx+r8], 0
0x180057741  jnz     short loc_180057739
0x180057743  inc     r8; Size
0x180057746  mov     rdx, rbx; Src
0x180057749  mov     rcx, r14; void *
0x18005774c  call    memmove
0x180057751  mov     r15, [rsp+38h+arg_28]
0x180057756  cmp     byte ptr [r15+28h], 0
0x18005775b  jnz     short loc_180057765
0x18005775d  mov     rcx, r15; this
0x180057760  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180057765  mov     rax, [r15+18h]
0x180057769  mov     rcx, [rax+0F8h]
0x180057770  mov     rax, [rcx]
0x180057773  mov     cl, [rax]
0x180057775  mov     [rbx], cl
0x180057777  mov     eax, [rbp+4]
0x18005777a  test    eax, eax
0x18005777c  jns     short loc_1800577BA
0x18005777e  neg     eax
0x180057780  cmp     [rsp+38h+arg_20], 0
0x180057785  jnz     short loc_18005778B
0x180057787  cmp     eax, esi
0x180057789  jge     short loc_18005778D
0x18005778b  mov     esi, eax
0x18005778d  movsxd  rbx, esi
0x180057790  inc     rdi
0x180057793  cmp     byte ptr [r14+rdi], 0
0x180057798  jnz     short loc_180057790
0x18005779a  lea     r8, [rdi+1]; Size
0x18005779e  mov     rdx, r14; Src
0x1800577a1  lea     rcx, [rbx+r14]; void *
0x1800577a5  call    memmove
0x1800577aa  mov     r8, rbx; Size
0x1800577ad  mov     edx, 30h ; '0'; Val
0x1800577b2  mov     rcx, r14; void *
0x1800577b5  call    memset
0x1800577ba  mov     rbx, [rsp+38h+arg_0]
0x1800577bf  xor     eax, eax
0x1800577c1  mov     rbp, [rsp+38h+arg_8]
0x1800577c6  mov     rsi, [rsp+38h+arg_10]
0x1800577cb  add     rsp, 20h
0x1800577cf  pop     r15
0x1800577d1  pop     r14
0x1800577d3  pop     rdi
0x1800577d4  retn
```
