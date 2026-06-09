# fp_format_f_internal

- ea: `0x140014da4`
- end: `0x140014ef1`
- name: `fp_format_f_internal`
- size: `333`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, char, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140014ccc`
- `0x140014ef4`

## callees

- `0x14000c750`
- `0x140014da4`
- `0x140024cc0`
- `0x140025080`

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
0x140014da4  mov     [rsp+arg_0], rbx
0x140014da9  mov     [rsp+arg_8], rbp
0x140014dae  mov     [rsp+arg_10], rsi
0x140014db3  push    rdi
0x140014db4  push    r14
0x140014db6  push    r15
0x140014db8  sub     rsp, 20h
0x140014dbc  cmp     [rsp+38h+arg_20], 0
0x140014dc1  mov     rbx, rcx
0x140014dc4  movsxd  rcx, dword ptr [r9+4]
0x140014dc8  mov     rbp, r9
0x140014dcb  mov     esi, r8d
0x140014dce  jz      short loc_140014DEB
0x140014dd0  lea     eax, [rcx-1]
0x140014dd3  cmp     eax, r8d
0x140014dd6  jnz     short loc_140014DEB
0x140014dd8  xor     eax, eax
0x140014dda  cmp     dword ptr [r9], 2Dh ; '-'
0x140014dde  setz    al
0x140014de1  add     rax, rbx
0x140014de4  mov     word ptr [rcx+rax-1], 30h ; '0'
0x140014deb  cmp     dword ptr [r9], 2Dh ; '-'
0x140014def  jnz     short loc_140014DF7
0x140014df1  mov     byte ptr [rbx], 2Dh ; '-'
0x140014df4  inc     rbx
0x140014df7  movsxd  rax, dword ptr [r9+4]
0x140014dfb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140014dff  test    eax, eax
0x140014e01  jg      short loc_140014E43
0x140014e03  jnz     short loc_140014E12
0x140014e05  mov     rax, [r9+8]
0x140014e09  cmp     byte ptr [rax], 30h ; '0'
0x140014e0c  jnz     short loc_140014E12
0x140014e0e  mov     al, 1
0x140014e10  jmp     short loc_140014E14
0x140014e12  xor     al, al
0x140014e14  cmp     [rsp+38h+arg_20], 0
0x140014e19  jz      short loc_140014E1F
0x140014e1b  test    al, al
0x140014e1d  jnz     short loc_140014E3B
0x140014e1f  mov     r8, rdi
0x140014e22  inc     r8
0x140014e25  cmp     byte ptr [rbx+r8], 0
0x140014e2a  jnz     short loc_140014E22
0x140014e2c  inc     r8; Size
0x140014e2f  lea     rcx, [rbx+1]; void *
0x140014e33  mov     rdx, rbx; Src
0x140014e36  call    memmove
0x140014e3b  mov     byte ptr [rbx], 30h ; '0'
0x140014e3e  inc     rbx
0x140014e41  jmp     short loc_140014E46
0x140014e43  add     rbx, rax
0x140014e46  test    esi, esi
0x140014e48  jle     loc_140014ED6
0x140014e4e  lea     r14, [rbx+1]
0x140014e52  mov     r8, rdi
0x140014e55  inc     r8
0x140014e58  cmp     byte ptr [rbx+r8], 0
0x140014e5d  jnz     short loc_140014E55
0x140014e5f  inc     r8; Size
0x140014e62  mov     rdx, rbx; Src
0x140014e65  mov     rcx, r14; void *
0x140014e68  call    memmove
0x140014e6d  mov     r15, [rsp+38h+arg_28]
0x140014e72  cmp     byte ptr [r15+28h], 0
0x140014e77  jnz     short loc_140014E81
0x140014e79  mov     rcx, r15; this
0x140014e7c  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x140014e81  mov     rax, [r15+18h]
0x140014e85  mov     rcx, [rax+0F8h]
0x140014e8c  mov     rax, [rcx]
0x140014e8f  mov     cl, [rax]
0x140014e91  mov     [rbx], cl
0x140014e93  mov     eax, [rbp+4]
0x140014e96  test    eax, eax
0x140014e98  jns     short loc_140014ED6
0x140014e9a  neg     eax
0x140014e9c  cmp     [rsp+38h+arg_20], 0
0x140014ea1  jnz     short loc_140014EA7
0x140014ea3  cmp     eax, esi
0x140014ea5  jge     short loc_140014EA9
0x140014ea7  mov     esi, eax
0x140014ea9  movsxd  rbx, esi
0x140014eac  inc     rdi
0x140014eaf  cmp     byte ptr [r14+rdi], 0
0x140014eb4  jnz     short loc_140014EAC
0x140014eb6  lea     r8, [rdi+1]; Size
0x140014eba  mov     rdx, r14; Src
0x140014ebd  lea     rcx, [rbx+r14]; void *
0x140014ec1  call    memmove
0x140014ec6  mov     r8, rbx; Size
0x140014ec9  mov     edx, 30h ; '0'; Val
0x140014ece  mov     rcx, r14; void *
0x140014ed1  call    memset
0x140014ed6  mov     rbx, [rsp+38h+arg_0]
0x140014edb  xor     eax, eax
0x140014edd  mov     rbp, [rsp+38h+arg_8]
0x140014ee2  mov     rsi, [rsp+38h+arg_10]
0x140014ee7  add     rsp, 20h
0x140014eeb  pop     r15
0x140014eed  pop     r14
0x140014eef  pop     rdi
0x140014ef0  retn
```
