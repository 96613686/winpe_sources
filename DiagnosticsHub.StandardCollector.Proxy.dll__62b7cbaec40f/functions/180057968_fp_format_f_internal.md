# fp_format_f_internal

- ea: `0x180057968`
- end: `0x180057ab5`
- name: `fp_format_f_internal`
- size: `333`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, char, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180057890`
- `0x180057ab8`

## callees

- `0x18001512c`
- `0x180057968`
- `0x180060550`
- `0x180060910`

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
0x180057968  mov     [rsp+arg_0], rbx
0x18005796d  mov     [rsp+arg_8], rbp
0x180057972  mov     [rsp+arg_10], rsi
0x180057977  push    rdi
0x180057978  push    r14
0x18005797a  push    r15
0x18005797c  sub     rsp, 20h
0x180057980  cmp     [rsp+38h+arg_20], 0
0x180057985  mov     rbx, rcx
0x180057988  movsxd  rcx, dword ptr [r9+4]
0x18005798c  mov     rbp, r9
0x18005798f  mov     esi, r8d
0x180057992  jz      short loc_1800579AF
0x180057994  lea     eax, [rcx-1]
0x180057997  cmp     eax, r8d
0x18005799a  jnz     short loc_1800579AF
0x18005799c  xor     eax, eax
0x18005799e  cmp     dword ptr [r9], 2Dh ; '-'
0x1800579a2  setz    al
0x1800579a5  add     rax, rbx
0x1800579a8  mov     word ptr [rcx+rax-1], 30h ; '0'
0x1800579af  cmp     dword ptr [r9], 2Dh ; '-'
0x1800579b3  jnz     short loc_1800579BB
0x1800579b5  mov     byte ptr [rbx], 2Dh ; '-'
0x1800579b8  inc     rbx
0x1800579bb  movsxd  rax, dword ptr [r9+4]
0x1800579bf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800579c3  test    eax, eax
0x1800579c5  jg      short loc_180057A07
0x1800579c7  jnz     short loc_1800579D6
0x1800579c9  mov     rax, [r9+8]
0x1800579cd  cmp     byte ptr [rax], 30h ; '0'
0x1800579d0  jnz     short loc_1800579D6
0x1800579d2  mov     al, 1
0x1800579d4  jmp     short loc_1800579D8
0x1800579d6  xor     al, al
0x1800579d8  cmp     [rsp+38h+arg_20], 0
0x1800579dd  jz      short loc_1800579E3
0x1800579df  test    al, al
0x1800579e1  jnz     short loc_1800579FF
0x1800579e3  mov     r8, rdi
0x1800579e6  inc     r8
0x1800579e9  cmp     byte ptr [rbx+r8], 0
0x1800579ee  jnz     short loc_1800579E6
0x1800579f0  inc     r8; Size
0x1800579f3  lea     rcx, [rbx+1]; void *
0x1800579f7  mov     rdx, rbx; Src
0x1800579fa  call    memmove
0x1800579ff  mov     byte ptr [rbx], 30h ; '0'
0x180057a02  inc     rbx
0x180057a05  jmp     short loc_180057A0A
0x180057a07  add     rbx, rax
0x180057a0a  test    esi, esi
0x180057a0c  jle     loc_180057A9A
0x180057a12  lea     r14, [rbx+1]
0x180057a16  mov     r8, rdi
0x180057a19  inc     r8
0x180057a1c  cmp     byte ptr [rbx+r8], 0
0x180057a21  jnz     short loc_180057A19
0x180057a23  inc     r8; Size
0x180057a26  mov     rdx, rbx; Src
0x180057a29  mov     rcx, r14; void *
0x180057a2c  call    memmove
0x180057a31  mov     r15, [rsp+38h+arg_28]
0x180057a36  cmp     byte ptr [r15+28h], 0
0x180057a3b  jnz     short loc_180057A45
0x180057a3d  mov     rcx, r15; this
0x180057a40  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x180057a45  mov     rax, [r15+18h]
0x180057a49  mov     rcx, [rax+0F8h]
0x180057a50  mov     rax, [rcx]
0x180057a53  mov     cl, [rax]
0x180057a55  mov     [rbx], cl
0x180057a57  mov     eax, [rbp+4]
0x180057a5a  test    eax, eax
0x180057a5c  jns     short loc_180057A9A
0x180057a5e  neg     eax
0x180057a60  cmp     [rsp+38h+arg_20], 0
0x180057a65  jnz     short loc_180057A6B
0x180057a67  cmp     eax, esi
0x180057a69  jge     short loc_180057A6D
0x180057a6b  mov     esi, eax
0x180057a6d  movsxd  rbx, esi
0x180057a70  inc     rdi
0x180057a73  cmp     byte ptr [r14+rdi], 0
0x180057a78  jnz     short loc_180057A70
0x180057a7a  lea     r8, [rdi+1]; Size
0x180057a7e  mov     rdx, r14; Src
0x180057a81  lea     rcx, [rbx+r14]; void *
0x180057a85  call    memmove
0x180057a8a  mov     r8, rbx; Size
0x180057a8d  mov     edx, 30h ; '0'; Val
0x180057a92  mov     rcx, r14; void *
0x180057a95  call    memset
0x180057a9a  mov     rbx, [rsp+38h+arg_0]
0x180057a9f  xor     eax, eax
0x180057aa1  mov     rbp, [rsp+38h+arg_8]
0x180057aa6  mov     rsi, [rsp+38h+arg_10]
0x180057aab  add     rsp, 20h
0x180057aaf  pop     r15
0x180057ab1  pop     r14
0x180057ab3  pop     rdi
0x180057ab4  retn
```
