# _fputwc_nolock_internal

- ea: `0x1800585c8`
- end: `0x18005875b`
- name: `_fputwc_nolock_internal`
- size: `403`
- prototype: ``
- caller_count: `22`
- callee_count: `6`
- tags: ``

## callers

- `0x180039188`
- `0x1800409d8`
- `0x180044d40`
- `0x180045000`
- `0x180045360`
- `0x180046c60`
- `0x180046cc0`
- `0x180046d44`
- `0x1800475b4`
- `0x180047614`
- `0x180047674`
- `0x18004b184`
- `0x18004b780`
- `0x18004bdb8`
- `0x180053dc8`
- `0x180053ee8`
- `0x1800549d0`
- `0x180054c60`
- `0x180054ef0`
- `0x180055a88`
- `0x180058490`
- `0x18005852c`

## callees

- `0x180014970`
- `0x180032370`
- `0x180057e0c`
- `0x1800585c8`
- `0x180058a44`
- `0x18005cae4`

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
0x1800585c8  mov     [rsp+arg_8], rbx
0x1800585cd  push    rbp
0x1800585ce  push    rsi
0x1800585cf  push    rdi
0x1800585d0  push    r14
0x1800585d2  push    r15
0x1800585d4  sub     rsp, 50h
0x1800585d8  mov     rax, cs:__security_cookie
0x1800585df  xor     rax, rsp
0x1800585e2  mov     [rsp+78h+var_38], rax
0x1800585e7  mov     eax, [rdx+14h]
0x1800585ea  mov     rbp, r8
0x1800585ed  shr     eax, 0Ch
0x1800585f0  mov     rdi, rdx
0x1800585f3  movzx   esi, cx
0x1800585f6  nop
0x1800585f7  test    al, 1
0x1800585f9  jz      short loc_180058614
0x1800585fb  add     dword ptr [rdx+10h], 0FFFFFFFEh
0x1800585ff  js      loc_180058722
0x180058605  mov     rax, [rdx]
0x180058608  mov     [rax], si
0x18005860b  add     qword ptr [rdx], 2
0x18005860f  jmp     loc_180058737
0x180058614  mov     rcx, rdi; Stream
0x180058617  call    _fileno
0x18005861c  lea     r14, __badioinfo
0x180058623  lea     r15, __pioinfo
0x18005862a  cmp     eax, 0FFFFFFFFh
0x18005862d  jz      short loc_180058667
0x18005862f  mov     rcx, rdi; Stream
0x180058632  call    _fileno
0x180058637  cmp     eax, 0FFFFFFFEh
0x18005863a  jz      short loc_180058667
0x18005863c  mov     rcx, rdi; Stream
0x18005863f  call    _fileno
0x180058644  movsxd  rbx, eax
0x180058647  mov     rcx, rdi; Stream
0x18005864a  sar     rbx, 6
0x18005864e  call    _fileno
0x180058653  and     eax, 3Fh
0x180058656  lea     rcx, [rax+rax*8]
0x18005865a  mov     rax, [r15+rbx*8]
0x18005865e  shl     rcx, 3
0x180058662  add     rax, rcx
0x180058665  jmp     short loc_18005866A
0x180058667  mov     rax, r14
0x18005866a  mov     al, [rax+39h]
0x18005866d  dec     al
0x18005866f  cmp     al, 1
0x180058671  jbe     loc_180058716
0x180058677  mov     rcx, rdi; Stream
0x18005867a  call    _fileno
0x18005867f  cmp     eax, 0FFFFFFFFh
0x180058682  jz      short loc_1800586B7
0x180058684  mov     rcx, rdi; Stream
0x180058687  call    _fileno
0x18005868c  cmp     eax, 0FFFFFFFEh
0x18005868f  jz      short loc_1800586B7
0x180058691  mov     rcx, rdi; Stream
0x180058694  call    _fileno
0x180058699  movsxd  rbx, eax
0x18005869c  mov     rcx, rdi; Stream
0x18005869f  sar     rbx, 6
0x1800586a3  call    _fileno
0x1800586a8  and     eax, 3Fh
0x1800586ab  lea     r14, [rax+rax*8]
0x1800586af  shl     r14, 3
0x1800586b3  add     r14, [r15+rbx*8]
0x1800586b7  xor     ebx, ebx
0x1800586b9  cmp     [r14+38h], bl
0x1800586bd  jge     short loc_180058716
0x1800586bf  movzx   r9d, si
0x1800586c3  mov     [rsp+78h+var_48], ebx
0x1800586c7  lea     r8d, [rbx+5]
0x1800586cb  mov     [rsp+78h+var_58], rbp
0x1800586d0  lea     rdx, [rsp+78h+var_44]
0x1800586d5  lea     rcx, [rsp+78h+var_48]
0x1800586da  call    _wctomb_internal
0x1800586df  test    eax, eax
0x1800586e1  jnz     short loc_18005870F
0x1800586e3  cmp     [rsp+78h+var_48], ebx
0x1800586e7  jle     short loc_180058737
0x1800586e9  lea     r14, [rsp+78h+var_44]
0x1800586ee  movsx   ecx, byte ptr [r14]
0x1800586f2  mov     r8, rbp
0x1800586f5  mov     rdx, rdi
0x1800586f8  call    _fputc_nolock_internal
0x1800586fd  cmp     eax, 0FFFFFFFFh
0x180058700  jz      short loc_18005870F
0x180058702  inc     ebx
0x180058704  inc     r14
0x180058707  cmp     ebx, [rsp+78h+var_48]
0x18005870b  jl      short loc_1800586EE
0x18005870d  jmp     short loc_180058737
0x18005870f  mov     eax, 0FFFFh
0x180058714  jmp     short loc_18005873A
0x180058716  add     dword ptr [rdi+10h], 0FFFFFFFEh
0x18005871a  jns     short loc_18005872D
0x18005871c  mov     r8, rbp
0x18005871f  mov     rdx, rdi
0x180058722  mov     ecx, esi
0x180058724  call    __acrt_stdio_flush_and_write_wide_nolock
0x180058729  mov     esi, eax
0x18005872b  jmp     short loc_180058737
0x18005872d  mov     rax, [rdi]
0x180058730  mov     [rax], si
0x180058733  add     qword ptr [rdi], 2
0x180058737  movzx   eax, si
0x18005873a  mov     rcx, [rsp+78h+var_38]
0x18005873f  xor     rcx, rsp; StackCookie
0x180058742  call    __security_check_cookie
0x180058747  mov     rbx, [rsp+78h+arg_8]
0x18005874f  add     rsp, 50h
0x180058753  pop     r15
0x180058755  pop     r14
0x180058757  pop     rdi
0x180058758  pop     rsi
0x180058759  pop     rbp
0x18005875a  retn
```
