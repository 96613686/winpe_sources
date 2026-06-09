# _fputwc_nolock_internal

- ea: `0x1800588a8`
- end: `0x180058a3b`
- name: `_fputwc_nolock_internal`
- size: `403`
- prototype: ``
- caller_count: `22`
- callee_count: `6`
- tags: ``

## callers

- `0x180039468`
- `0x180040cb8`
- `0x180045020`
- `0x1800452e0`
- `0x180045640`
- `0x180046f40`
- `0x180046fa0`
- `0x180047024`
- `0x180047894`
- `0x1800478f4`
- `0x180047954`
- `0x18004b464`
- `0x18004ba60`
- `0x18004c098`
- `0x1800540a8`
- `0x1800541c8`
- `0x180054cb0`
- `0x180054f40`
- `0x1800551d0`
- `0x180055d68`
- `0x180058770`
- `0x18005880c`

## callees

- `0x180002810`
- `0x1800150d0`
- `0x1800580ec`
- `0x1800588a8`
- `0x180058d24`
- `0x18005cdc4`

## pseudocode

```c
__int64 __fastcall fputwc_nolock_internal(unsigned __int16 a1, __int64 a2, __int64 a3)
{
  struct _Mbstatet *v3; // rbp
  __int64 v4; // rdi
  unsigned __int16 v5; // si
  bool v6; // sf
  __int64 *v7; // r14
  __int64 v8; // rbx
  __int64 *v9; // rax
  __int64 v10; // rbx
  int v11; // ebx
  char *i; // r14
  int v14; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v15[12]; // [rsp+34h] [rbp-44h] BYREF

  v3 = (struct _Mbstatet *)a3;
  v4 = a2;
  v5 = a1;
  if ( (*(_DWORD *)(a2 + 20) & 0x1000) == 0 )
  {
    v7 = _badioinfo;
    if ( fileno((FILE *)a2) == -1 || fileno((FILE *)v4) == -2 )
    {
      v9 = _badioinfo;
    }
    else
    {
      v8 = (__int64)fileno((FILE *)v4) >> 6;
      v9 = (__int64 *)(72LL * (fileno((FILE *)v4) & 0x3F) + _pioinfo[v8]);
    }
    if ( (unsigned __int8)(*((_BYTE *)v9 + 57) - 1) > 1u )
    {
      if ( fileno((FILE *)v4) != -1 && fileno((FILE *)v4) != -2 )
      {
        v10 = (__int64)fileno((FILE *)v4) >> 6;
        v7 = (__int64 *)(_pioinfo[v10] + 72LL * (fileno((FILE *)v4) & 0x3F));
      }
      v11 = 0;
      if ( *((char *)v7 + 56) < 0 )
      {
        v14 = 0;
        if ( !(unsigned int)wctomb_internal(&v14, v15, 5u, v5, v3) )
        {
          if ( v14 <= 0 )
            return v5;
          for ( i = v15; (unsigned int)fputc_nolock_internal((unsigned int)*i, v4, v3) != -1; ++i )
          {
            if ( ++v11 >= v14 )
              return v5;
          }
        }
        return 0xFFFF;
      }
    }
    v6 = *(_DWORD *)(v4 + 16) - 2 < 0;
    *(_DWORD *)(v4 + 16) -= 2;
    if ( !v6 )
    {
      **(_WORD **)v4 = v5;
      *(_QWORD *)v4 += 2LL;
      return v5;
    }
    a3 = (__int64)v3;
    a2 = v4;
    return (unsigned __int16)_acrt_stdio_flush_and_write_wide_nolock(v5, a2, a3);
  }
  v6 = *(_DWORD *)(a2 + 16) - 2 < 0;
  *(_DWORD *)(a2 + 16) -= 2;
  if ( v6 )
    return (unsigned __int16)_acrt_stdio_flush_and_write_wide_nolock(v5, a2, a3);
  **(_WORD **)a2 = a1;
  *(_QWORD *)a2 += 2LL;
  return v5;
}

```

## disassembly

```asm
0x1800588a8  mov     [rsp+arg_8], rbx
0x1800588ad  push    rbp
0x1800588ae  push    rsi
0x1800588af  push    rdi
0x1800588b0  push    r14
0x1800588b2  push    r15
0x1800588b4  sub     rsp, 50h
0x1800588b8  mov     rax, cs:__security_cookie
0x1800588bf  xor     rax, rsp
0x1800588c2  mov     [rsp+78h+var_38], rax
0x1800588c7  mov     eax, [rdx+14h]
0x1800588ca  mov     rbp, r8
0x1800588cd  shr     eax, 0Ch
0x1800588d0  mov     rdi, rdx
0x1800588d3  movzx   esi, cx
0x1800588d6  nop
0x1800588d7  test    al, 1
0x1800588d9  jz      short loc_1800588F4
0x1800588db  add     dword ptr [rdx+10h], 0FFFFFFFEh
0x1800588df  js      loc_180058A02
0x1800588e5  mov     rax, [rdx]
0x1800588e8  mov     [rax], si
0x1800588eb  add     qword ptr [rdx], 2
0x1800588ef  jmp     loc_180058A17
0x1800588f4  mov     rcx, rdi; Stream
0x1800588f7  call    _fileno
0x1800588fc  lea     r14, __badioinfo
0x180058903  lea     r15, __pioinfo
0x18005890a  cmp     eax, 0FFFFFFFFh
0x18005890d  jz      short loc_180058947
0x18005890f  mov     rcx, rdi; Stream
0x180058912  call    _fileno
0x180058917  cmp     eax, 0FFFFFFFEh
0x18005891a  jz      short loc_180058947
0x18005891c  mov     rcx, rdi; Stream
0x18005891f  call    _fileno
0x180058924  movsxd  rbx, eax
0x180058927  mov     rcx, rdi; Stream
0x18005892a  sar     rbx, 6
0x18005892e  call    _fileno
0x180058933  and     eax, 3Fh
0x180058936  lea     rcx, [rax+rax*8]
0x18005893a  mov     rax, [r15+rbx*8]
0x18005893e  shl     rcx, 3
0x180058942  add     rax, rcx
0x180058945  jmp     short loc_18005894A
0x180058947  mov     rax, r14
0x18005894a  mov     al, [rax+39h]
0x18005894d  dec     al
0x18005894f  cmp     al, 1
0x180058951  jbe     loc_1800589F6
0x180058957  mov     rcx, rdi; Stream
0x18005895a  call    _fileno
0x18005895f  cmp     eax, 0FFFFFFFFh
0x180058962  jz      short loc_180058997
0x180058964  mov     rcx, rdi; Stream
0x180058967  call    _fileno
0x18005896c  cmp     eax, 0FFFFFFFEh
0x18005896f  jz      short loc_180058997
0x180058971  mov     rcx, rdi; Stream
0x180058974  call    _fileno
0x180058979  movsxd  rbx, eax
0x18005897c  mov     rcx, rdi; Stream
0x18005897f  sar     rbx, 6
0x180058983  call    _fileno
0x180058988  and     eax, 3Fh
0x18005898b  lea     r14, [rax+rax*8]
0x18005898f  shl     r14, 3
0x180058993  add     r14, [r15+rbx*8]
0x180058997  xor     ebx, ebx
0x180058999  cmp     [r14+38h], bl
0x18005899d  jge     short loc_1800589F6
0x18005899f  movzx   r9d, si
0x1800589a3  mov     [rsp+78h+var_48], ebx
0x1800589a7  lea     r8d, [rbx+5]
0x1800589ab  mov     [rsp+78h+var_58], rbp
0x1800589b0  lea     rdx, [rsp+78h+var_44]
0x1800589b5  lea     rcx, [rsp+78h+var_48]
0x1800589ba  call    _wctomb_internal
0x1800589bf  test    eax, eax
0x1800589c1  jnz     short loc_1800589EF
0x1800589c3  cmp     [rsp+78h+var_48], ebx
0x1800589c7  jle     short loc_180058A17
0x1800589c9  lea     r14, [rsp+78h+var_44]
0x1800589ce  movsx   ecx, byte ptr [r14]
0x1800589d2  mov     r8, rbp
0x1800589d5  mov     rdx, rdi
0x1800589d8  call    _fputc_nolock_internal
0x1800589dd  cmp     eax, 0FFFFFFFFh
0x1800589e0  jz      short loc_1800589EF
0x1800589e2  inc     ebx
0x1800589e4  inc     r14
0x1800589e7  cmp     ebx, [rsp+78h+var_48]
0x1800589eb  jl      short loc_1800589CE
0x1800589ed  jmp     short loc_180058A17
0x1800589ef  mov     eax, 0FFFFh
0x1800589f4  jmp     short loc_180058A1A
0x1800589f6  add     dword ptr [rdi+10h], 0FFFFFFFEh
0x1800589fa  jns     short loc_180058A0D
0x1800589fc  mov     r8, rbp
0x1800589ff  mov     rdx, rdi
0x180058a02  mov     ecx, esi
0x180058a04  call    __acrt_stdio_flush_and_write_wide_nolock
0x180058a09  mov     esi, eax
0x180058a0b  jmp     short loc_180058A17
0x180058a0d  mov     rax, [rdi]
0x180058a10  mov     [rax], si
0x180058a13  add     qword ptr [rdi], 2
0x180058a17  movzx   eax, si
0x180058a1a  mov     rcx, [rsp+78h+var_38]
0x180058a1f  xor     rcx, rsp; StackCookie
0x180058a22  call    __security_check_cookie
0x180058a27  mov     rbx, [rsp+78h+arg_8]
0x180058a2f  add     rsp, 50h
0x180058a33  pop     r15
0x180058a35  pop     r14
0x180058a37  pop     rdi
0x180058a38  pop     rsi
0x180058a39  pop     rbp
0x180058a3a  retn
```
