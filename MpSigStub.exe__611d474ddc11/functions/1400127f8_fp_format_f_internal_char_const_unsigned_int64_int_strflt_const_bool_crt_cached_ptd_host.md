# fp_format_f_internal(char * const,unsigned __int64,int,_strflt * const,bool,__crt_cached_ptd_host &)

- ea: `0x1400127f8`
- end: `0x14001294e`
- name: `?fp_format_f_internal@@YAHQEAD_KHQEAU_strflt@@_NAEAV__crt_cached_ptd_host@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(char *const Src, __int64, int, struct _strflt *const, bool, struct __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140012720`
- `0x140012950`

## callees

- `0x14000ad70`
- `0x1400127f8`
- `0x14001db10`
- `0x14001e2d0`

## pseudocode

```c
__int64 __fastcall fp_format_f_internal(
        char *const Src,
        __int64 a2,
        int a3,
        struct _strflt *const a4,
        bool a5,
        struct __crt_cached_ptd_host *a6)
{
  __int64 v7; // rcx
  int v9; // ebp
  __int64 v10; // rax
  __int64 v11; // rdi
  bool v12; // al
  char *v13; // rsi
  __int64 v14; // r8
  char *v15; // rbx
  _BYTE *v16; // rsi
  __int64 v17; // r8
  int v18; // eax
  int v19; // eax

  v7 = *((int *)a4 + 1);
  v9 = a3;
  if ( a5 && (_DWORD)v7 - 1 == a3 )
    *(_WORD *)&Src[(*(_DWORD *)a4 == 45) - 1 + v7] = 48;
  if ( *(_DWORD *)a4 == 45 )
    *Src++ = 45;
  v10 = *((int *)a4 + 1);
  v11 = -1;
  if ( (int)v10 > 0 )
  {
    v15 = &Src[v10];
  }
  else
  {
    v12 = !(_DWORD)v10 && **((_BYTE **)a4 + 1) == 48;
    if ( a5 && v12 )
    {
      v13 = Src + 1;
    }
    else
    {
      v13 = Src + 1;
      v14 = -1;
      do
        ++v14;
      while ( Src[v14] );
      memmove(Src + 1, Src, v14 + 1);
    }
    *Src = 48;
    v15 = v13;
  }
  if ( v9 > 0 )
  {
    v16 = v15 + 1;
    v17 = -1;
    do
      ++v17;
    while ( v15[v17] );
    memmove(v15 + 1, v15, v17 + 1);
    if ( !*((_BYTE *)a6 + 40) )
      __crt_cached_ptd_host::update_locale_slow(a6);
    *v15 = ***(_BYTE ***)(*((_QWORD *)a6 + 3) + 248LL);
    v18 = *((_DWORD *)a4 + 1);
    if ( v18 < 0 )
    {
      v19 = -v18;
      if ( a5 || v19 < v9 )
        v9 = v19;
      do
        ++v11;
      while ( v16[v11] );
      memmove(&v16[v9], v16, v11 + 1);
      memset(v16, 48, v9);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400127f8  mov     [rsp+arg_0], rbx
0x1400127fd  mov     [rsp+arg_8], rbp
0x140012802  mov     [rsp+arg_10], rsi
0x140012807  push    rdi
0x140012808  push    r14
0x14001280a  push    r15
0x14001280c  sub     rsp, 20h
0x140012810  cmp     [rsp+38h+arg_20], 0
0x140012815  mov     rbx, rcx
0x140012818  movsxd  rcx, dword ptr [r9+4]
0x14001281c  mov     r14, r9
0x14001281f  mov     ebp, r8d
0x140012822  jz      short loc_14001283F
0x140012824  lea     eax, [rcx-1]
0x140012827  cmp     eax, r8d
0x14001282a  jnz     short loc_14001283F
0x14001282c  xor     eax, eax
0x14001282e  cmp     dword ptr [r9], 2Dh ; '-'
0x140012832  setz    al
0x140012835  add     rax, rbx
0x140012838  mov     word ptr [rcx+rax-1], 30h ; '0'
0x14001283f  cmp     dword ptr [r9], 2Dh ; '-'
0x140012843  jnz     short loc_14001284B
0x140012845  mov     byte ptr [rbx], 2Dh ; '-'
0x140012848  inc     rbx
0x14001284b  movsxd  rax, dword ptr [r9+4]
0x14001284f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140012853  test    eax, eax
0x140012855  jg      short loc_1400128A0
0x140012857  jnz     short loc_140012866
0x140012859  mov     rax, [r9+8]
0x14001285d  cmp     byte ptr [rax], 30h ; '0'
0x140012860  jnz     short loc_140012866
0x140012862  mov     al, 1
0x140012864  jmp     short loc_140012868
0x140012866  xor     al, al
0x140012868  cmp     [rsp+38h+arg_20], 0
0x14001286d  jz      short loc_140012879
0x14001286f  test    al, al
0x140012871  jz      short loc_140012879
0x140012873  lea     rsi, [rbx+1]
0x140012877  jmp     short loc_140012898
0x140012879  lea     rsi, [rbx+1]
0x14001287d  mov     r8, rdi
0x140012880  inc     r8
0x140012883  cmp     byte ptr [rbx+r8], 0
0x140012888  jnz     short loc_140012880
0x14001288a  inc     r8; MaxCount
0x14001288d  mov     rdx, rbx; Src
0x140012890  mov     rcx, rsi; Dst
0x140012893  call    memmove
0x140012898  mov     byte ptr [rbx], 30h ; '0'
0x14001289b  mov     rbx, rsi
0x14001289e  jmp     short loc_1400128A3
0x1400128a0  add     rbx, rax
0x1400128a3  test    ebp, ebp
0x1400128a5  jle     loc_140012933
0x1400128ab  lea     rsi, [rbx+1]
0x1400128af  mov     r8, rdi
0x1400128b2  inc     r8
0x1400128b5  cmp     byte ptr [rbx+r8], 0
0x1400128ba  jnz     short loc_1400128B2
0x1400128bc  inc     r8; MaxCount
0x1400128bf  mov     rdx, rbx; Src
0x1400128c2  mov     rcx, rsi; Dst
0x1400128c5  call    memmove
0x1400128ca  mov     r15, [rsp+38h+arg_28]
0x1400128cf  cmp     byte ptr [r15+28h], 0
0x1400128d4  jnz     short loc_1400128DE
0x1400128d6  mov     rcx, r15; this
0x1400128d9  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x1400128de  mov     rax, [r15+18h]
0x1400128e2  mov     rcx, [rax+0F8h]
0x1400128e9  mov     rax, [rcx]
0x1400128ec  mov     cl, [rax]
0x1400128ee  mov     [rbx], cl
0x1400128f0  mov     eax, [r14+4]
0x1400128f4  test    eax, eax
0x1400128f6  jns     short loc_140012933
0x1400128f8  neg     eax
0x1400128fa  cmp     [rsp+38h+arg_20], 0
0x1400128ff  jnz     short loc_140012905
0x140012901  cmp     eax, ebp
0x140012903  jge     short loc_140012907
0x140012905  mov     ebp, eax
0x140012907  movsxd  rbx, ebp
0x14001290a  inc     rdi
0x14001290d  cmp     byte ptr [rsi+rdi], 0
0x140012911  jnz     short loc_14001290A
0x140012913  lea     r8, [rdi+1]; MaxCount
0x140012917  mov     rdx, rsi; Src
0x14001291a  lea     rcx, [rbx+rsi]; Dst
0x14001291e  call    memmove
0x140012923  mov     r8, rbx; Size
0x140012926  mov     edx, 30h ; '0'; Val
0x14001292b  mov     rcx, rsi; Dst
0x14001292e  call    memset
0x140012933  mov     rbx, [rsp+38h+arg_0]
0x140012938  xor     eax, eax
0x14001293a  mov     rbp, [rsp+38h+arg_8]
0x14001293f  mov     rsi, [rsp+38h+arg_10]
0x140012944  add     rsp, 20h
0x140012948  pop     r15
0x14001294a  pop     r14
0x14001294c  pop     rdi
0x14001294d  retn
```
