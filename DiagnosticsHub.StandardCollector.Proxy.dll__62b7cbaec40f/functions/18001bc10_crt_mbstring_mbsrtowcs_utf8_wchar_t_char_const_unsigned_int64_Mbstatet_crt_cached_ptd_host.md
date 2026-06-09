# __crt_mbstring::__mbsrtowcs_utf8(wchar_t *,char const * *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x18001bc10`
- end: `0x18001bdc5`
- name: `?__mbsrtowcs_utf8@__crt_mbstring@@YA_KPEA_WPEAPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `437`
- prototype: `unsigned __int64(__crt_mbstring *__hidden this, wchar_t *, const char **, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180015210`
- `0x18001c000`
- `0x180022380`
- `0x18004b464`
- `0x18004ba60`
- `0x18004c098`
- `0x18004c694`
- `0x18004cc0c`
- `0x18004d198`
- `0x180054cb0`
- `0x180054f40`
- `0x1800551d0`
- `0x180055460`
- `0x180055694`
- `0x1800558c8`

## callees

- `0x18001bc10`
- `0x180021460`

## pseudocode

```c
__int64 __fastcall __crt_mbstring::__mbsrtowcs_utf8(
        __crt_mbstring *this,
        wchar_t *a2,
        const char **a3,
        unsigned __int64 a4,
        struct _Mbstatet *a5)
{
  __int64 v5; // rdi
  const char **v7; // rsi
  __crt_mbstring *v10; // rbx
  struct _Mbstatet *v11; // r15
  __int64 v12; // r8
  unsigned __int64 v13; // rax
  __int16 v14; // cx
  unsigned int v15; // ecx
  __int64 i; // rbx
  struct _Mbstatet *v18; // rsi
  __int64 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  struct __crt_cached_ptd_host *v22; // [rsp+28h] [rbp-30h]
  unsigned int v23; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(_QWORD *)a2;
  v7 = a3;
  if ( !this )
  {
    v18 = a5;
    for ( i = 0; ; i = v21 + 1 )
    {
      if ( *(_BYTE *)v5 )
        v19 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v19 = 1;
      v20 = __crt_mbstring::__mbrtoc32_utf8(0, (char32_t *)v5, (const char *)v19, a4, v18, v22);
      if ( v20 == -1 )
        break;
      if ( !v20 )
        return i;
      v21 = i + 1;
      v5 += v20;
      if ( v20 != 4 )
        v21 = i;
    }
    LOBYTE(v18[6]._Wchar) = 1;
    *(_DWORD *)&v18[5]._Byte = 42;
    return -1;
  }
  v10 = this;
  if ( a3 )
  {
    v11 = a5;
    while ( 1 )
    {
      if ( *(_BYTE *)v5 )
        v12 = *(_BYTE *)(v5 + 1) ? (*(_BYTE *)(v5 + 2) != 0) + 3LL : 2LL;
      else
        v12 = 1;
      v23 = 0;
      v13 = __crt_mbstring::__mbrtoc32_utf8((__crt_mbstring *)&v23, (char32_t *)v5, (const char *)v12, a4, v11, v22);
      if ( v13 == -1 )
        break;
      if ( !v13 )
      {
        v5 = 0;
        *(_WORD *)v10 = 0;
        goto LABEL_15;
      }
      v14 = v23;
      if ( v23 > 0xFFFF )
      {
        if ( (unsigned __int64)v7 <= 1 )
          goto LABEL_15;
        v15 = v23 - 0x10000;
        v23 = v15;
        v7 = (const char **)((char *)v7 - 1);
        *(_WORD *)v10 = (v15 >> 10) | 0xD800;
        v10 = (__crt_mbstring *)((char *)v10 + 2);
        v14 = v15 & 0x3FF | 0xDC00;
      }
      *(_WORD *)v10 = v14;
      v5 += v13;
      v10 = (__crt_mbstring *)((char *)v10 + 2);
      v7 = (const char **)((char *)v7 - 1);
      if ( !v7 )
        goto LABEL_15;
    }
    *(_QWORD *)a2 = v5;
    LOBYTE(v11[6]._Wchar) = 1;
    *(_DWORD *)&v11[5]._Byte = 42;
    return -1;
  }
LABEL_15:
  *(_QWORD *)a2 = v5;
  return (v10 - this) >> 1;
}

```

## disassembly

```asm
0x18001bc10  mov     [rsp+arg_8], rbx
0x18001bc15  mov     [rsp+arg_10], rbp
0x18001bc1a  mov     [rsp+arg_18], rsi
0x18001bc1f  push    rdi
0x18001bc20  push    r12
0x18001bc22  push    r13
0x18001bc24  push    r14
0x18001bc26  push    r15
0x18001bc28  sub     rsp, 30h
0x18001bc2c  mov     rdi, [rdx]
0x18001bc2f  xor     r13d, r13d
0x18001bc32  mov     r12, r9
0x18001bc35  mov     rsi, r8
0x18001bc38  mov     r14, rdx
0x18001bc3b  mov     rbp, rcx
0x18001bc3e  test    rcx, rcx
0x18001bc41  jz      loc_18001BD32
0x18001bc47  mov     rbx, rcx
0x18001bc4a  test    r8, r8
0x18001bc4d  jz      loc_18001BD06
0x18001bc53  mov     r15, [rsp+58h+arg_20]
0x18001bc5b  cmp     [rdi], r13b
0x18001bc5e  jnz     short loc_18001BC68
0x18001bc60  mov     r8d, 1
0x18001bc66  jmp     short loc_18001BC85
0x18001bc68  cmp     [rdi+1], r13b
0x18001bc6c  jnz     short loc_18001BC76
0x18001bc6e  mov     r8d, 2
0x18001bc74  jmp     short loc_18001BC85
0x18001bc76  mov     al, [rdi+2]
0x18001bc79  neg     al
0x18001bc7b  sbb     r8, r8
0x18001bc7e  neg     r8
0x18001bc81  add     r8, 3; char *
0x18001bc85  mov     r9, r12; unsigned __int64
0x18001bc88  mov     [rsp+58h+arg_0], r13d
0x18001bc8d  mov     rdx, rdi; char32_t *
0x18001bc90  mov     [rsp+58h+var_38], r15; struct _Mbstatet *
0x18001bc95  lea     rcx, [rsp+58h+arg_0]; this
0x18001bc9a  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001bc9f  mov     rdx, rax
0x18001bca2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bca6  jz      short loc_18001BD20
0x18001bca8  test    rax, rax
0x18001bcab  jz      short loc_18001BD17
0x18001bcad  mov     ecx, [rsp+58h+arg_0]
0x18001bcb1  cmp     ecx, 0FFFFh
0x18001bcb7  jbe     short loc_18001BCF2
0x18001bcb9  cmp     rsi, 1
0x18001bcbd  jbe     short loc_18001BD06
0x18001bcbf  add     ecx, 0FFFF0000h
0x18001bcc5  mov     r8d, 0D800h
0x18001bccb  mov     eax, ecx
0x18001bccd  mov     [rsp+58h+arg_0], ecx
0x18001bcd1  shr     eax, 0Ah
0x18001bcd4  dec     rsi
0x18001bcd7  or      ax, r8w
0x18001bcdb  mov     [rbx], ax
0x18001bcde  mov     eax, 3FFh
0x18001bce3  and     cx, ax
0x18001bce6  add     rbx, 2
0x18001bcea  mov     eax, 0DC00h
0x18001bcef  or      cx, ax
0x18001bcf2  mov     [rbx], cx
0x18001bcf5  add     rdi, rdx
0x18001bcf8  add     rbx, 2
0x18001bcfc  sub     rsi, 1
0x18001bd00  jnz     loc_18001BC5B
0x18001bd06  sub     rbx, rbp
0x18001bd09  mov     [r14], rdi
0x18001bd0c  sar     rbx, 1
0x18001bd0f  mov     rax, rbx
0x18001bd12  jmp     loc_18001BDA8
0x18001bd17  mov     rdi, r13
0x18001bd1a  mov     [rbx], r13w
0x18001bd1e  jmp     short loc_18001BD06
0x18001bd20  mov     [r14], rdi
0x18001bd23  mov     byte ptr [r15+30h], 1
0x18001bd28  mov     dword ptr [r15+2Ch], 2Ah ; '*'
0x18001bd30  jmp     short loc_18001BDA4
0x18001bd32  mov     rsi, [rsp+58h+arg_20]
0x18001bd3a  mov     rbx, r13
0x18001bd3d  cmp     [rdi], r13b
0x18001bd40  jnz     short loc_18001BD4A
0x18001bd42  mov     r8d, 1
0x18001bd48  jmp     short loc_18001BD67
0x18001bd4a  cmp     [rdi+1], r13b
0x18001bd4e  jnz     short loc_18001BD58
0x18001bd50  mov     r8d, 2
0x18001bd56  jmp     short loc_18001BD67
0x18001bd58  mov     al, [rdi+2]
0x18001bd5b  neg     al
0x18001bd5d  sbb     r8, r8
0x18001bd60  neg     r8
0x18001bd63  add     r8, 3; char *
0x18001bd67  mov     r9, r12; unsigned __int64
0x18001bd6a  mov     [rsp+58h+var_38], rsi; struct _Mbstatet *
0x18001bd6f  mov     rdx, rdi; char32_t *
0x18001bd72  xor     ecx, ecx; this
0x18001bd74  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001bd79  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bd7d  jz      short loc_18001BD99
0x18001bd7f  test    rax, rax
0x18001bd82  jz      short loc_18001BD0F
0x18001bd84  lea     rcx, [rbx+1]
0x18001bd88  add     rdi, rax
0x18001bd8b  cmp     rax, 4
0x18001bd8f  cmovnz  rcx, rbx
0x18001bd93  lea     rbx, [rcx+1]
0x18001bd97  jmp     short loc_18001BD3D
0x18001bd99  mov     byte ptr [rsi+30h], 1
0x18001bd9d  mov     dword ptr [rsi+2Ch], 2Ah ; '*'
0x18001bda4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001bda8  mov     rbx, [rsp+58h+arg_8]
0x18001bdad  mov     rbp, [rsp+58h+arg_10]
0x18001bdb2  mov     rsi, [rsp+58h+arg_18]
0x18001bdb7  add     rsp, 30h
0x18001bdbb  pop     r15
0x18001bdbd  pop     r14
0x18001bdbf  pop     r13
0x18001bdc1  pop     r12
0x18001bdc3  pop     rdi
0x18001bdc4  retn
```
