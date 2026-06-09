# _mbtowc_internal

- ea: `0x18001b18c`
- end: `0x18001b304`
- name: `_mbtowc_internal`
- size: `376`
- prototype: `__int64 __fastcall(__crt_mbstring *this, wchar_t *, char *, __crt_cached_ptd_host *)`
- caller_count: `21`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014ab0`
- `0x18001b304`
- `0x18001b3a8`
- `0x18004b184`
- `0x18004b780`
- `0x18004bdb8`
- `0x18004c3b4`
- `0x18004c92c`
- `0x18004ceb8`
- `0x180050208`
- `0x1800502cc`
- `0x1800503c4`
- `0x180050488`
- `0x18005054c`
- `0x180050644`
- `0x1800549d0`
- `0x180054c60`
- `0x180054ef0`
- `0x180055180`
- `0x1800553b4`
- `0x1800555e8`

## callees

- `0x18000af1c`
- `0x1800149cc`
- `0x18001b18c`
- `0x18001b468`

## pseudocode

```c
unsigned __int64 __fastcall mbtowc_internal(__crt_mbstring *this, wchar_t *a2, char *a3, __crt_cached_ptd_host *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // r10d
  unsigned __int64 result; // rax
  __int64 v11; // r9
  struct __crt_cached_ptd_host *v12; // [rsp+28h] [rbp-10h]

  if ( !a2 || !a3 )
  {
    qword_180079008 = 0;
    return 0;
  }
  if ( !*(_BYTE *)a2 )
  {
    if ( this )
      *(_WORD *)this = 0;
    return 0;
  }
  if ( !*((_BYTE *)a4 + 40) )
    __crt_cached_ptd_host::update_locale_slow(a4);
  v8 = *((_QWORD *)a4 + 3);
  v9 = *(_DWORD *)(v8 + 12);
  if ( v9 != 65001 )
  {
    if ( !*(_QWORD *)(v8 + 312) )
    {
      if ( this )
        *(_WORD *)this = *(unsigned __int8 *)a2;
      return 1;
    }
    if ( *(__int16 *)(*(_QWORD *)v8 + 2LL * *(unsigned __int8 *)a2) >= 0 )
    {
      if ( (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2, 1, this, this != 0) )
        return 1;
    }
    else
    {
      v11 = *(unsigned int *)(v8 + 8);
      if ( (int)v11 > 1
        && (int)a3 >= (int)v11
        && (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2, v11, this, this != 0)
        || (unsigned __int64)a3 >= *(int *)(*((_QWORD *)a4 + 3) + 8LL) && *((_BYTE *)a2 + 1) )
      {
        return *(unsigned int *)(*((_QWORD *)a4 + 3) + 8LL);
      }
    }
    *((_BYTE *)a4 + 48) = 1;
    result = 0xFFFFFFFFLL;
    *((_DWORD *)a4 + 11) = 42;
    return result;
  }
  result = __crt_mbstring::__mbrtowc_utf8(this, a2, a3, (unsigned __int64)&qword_180079008, (struct _Mbstatet *)a4, v12);
  if ( (result & 0x80000000) != 0LL )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x18001b18c  mov     rax, rsp
0x18001b18f  mov     [rax+8], rbx
0x18001b193  mov     [rax+10h], rbp
0x18001b197  mov     [rax+18h], rsi
0x18001b19b  mov     [rax+20h], rdi
0x18001b19f  push    r14
0x18001b1a1  sub     rsp, 30h
0x18001b1a5  xor     r14d, r14d
0x18001b1a8  mov     rbx, r9
0x18001b1ab  mov     rbp, r8
0x18001b1ae  mov     rsi, rdx
0x18001b1b1  mov     rdi, rcx
0x18001b1b4  test    rdx, rdx
0x18001b1b7  jz      loc_18001B2E0
0x18001b1bd  test    r8, r8
0x18001b1c0  jz      loc_18001B2E0
0x18001b1c6  cmp     [rdx], r14b
0x18001b1c9  jnz     short loc_18001B1DD
0x18001b1cb  test    rcx, rcx
0x18001b1ce  jz      loc_18001B2E7
0x18001b1d4  mov     [rcx], r14w
0x18001b1d8  jmp     loc_18001B2E7
0x18001b1dd  cmp     [r9+28h], r14b
0x18001b1e1  jnz     short loc_18001B1EB
0x18001b1e3  mov     rcx, rbx; this
0x18001b1e6  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001b1eb  mov     rdx, [rbx+18h]
0x18001b1ef  mov     r10d, [rdx+0Ch]
0x18001b1f3  cmp     r10d, 0FDE9h
0x18001b1fa  jnz     short loc_18001B223
0x18001b1fc  lea     r9, qword_180079008; unsigned __int64
0x18001b203  mov     [rsp+38h+var_18], rbx; struct _Mbstatet *
0x18001b208  mov     r8, rbp; char *
0x18001b20b  mov     rdx, rsi; wchar_t *
0x18001b20e  mov     rcx, rdi; this
0x18001b211  call    ?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b216  or      ecx, 0FFFFFFFFh
0x18001b219  test    eax, eax
0x18001b21b  cmovs   eax, ecx
0x18001b21e  jmp     loc_18001B2E9
0x18001b223  cmp     [rdx+138h], r14
0x18001b22a  jnz     short loc_18001B240
0x18001b22c  test    rdi, rdi
0x18001b22f  jz      loc_18001B2D9
0x18001b235  movzx   eax, byte ptr [rsi]
0x18001b238  mov     [rdi], ax
0x18001b23b  jmp     loc_18001B2D9
0x18001b240  movzx   ecx, byte ptr [rsi]
0x18001b243  mov     rax, [rdx]
0x18001b246  cmp     [rax+rcx*2], r14w
0x18001b24b  jge     short loc_18001B2AE
0x18001b24d  mov     r9d, [rdx+8]
0x18001b251  cmp     r9d, 1
0x18001b255  jle     short loc_18001B282
0x18001b257  cmp     ebp, r9d
0x18001b25a  jl      short loc_18001B282
0x18001b25c  mov     eax, r14d
0x18001b25f  test    rdi, rdi
0x18001b262  mov     r8, rsi
0x18001b265  mov     edx, 9
0x18001b26a  setnz   al
0x18001b26d  mov     ecx, r10d
0x18001b270  mov     [rsp+38h+var_10], eax
0x18001b274  mov     [rsp+38h+var_18], rdi
0x18001b279  call    __acrt_MultiByteToWideChar
0x18001b27e  test    eax, eax
0x18001b280  jnz     short loc_18001B295
0x18001b282  mov     rax, [rbx+18h]
0x18001b286  movsxd  rcx, dword ptr [rax+8]
0x18001b28a  cmp     rbp, rcx
0x18001b28d  jb      short loc_18001B29E
0x18001b28f  cmp     [rsi+1], r14b
0x18001b293  jz      short loc_18001B29E
0x18001b295  mov     rax, [rbx+18h]
0x18001b299  mov     eax, [rax+8]
0x18001b29c  jmp     short loc_18001B2E9
0x18001b29e  mov     byte ptr [rbx+30h], 1
0x18001b2a2  or      eax, 0FFFFFFFFh
0x18001b2a5  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x18001b2ac  jmp     short loc_18001B2E9
0x18001b2ae  mov     eax, r14d
0x18001b2b1  mov     r9d, 1
0x18001b2b7  test    rdi, rdi
0x18001b2ba  mov     r8, rsi
0x18001b2bd  mov     ecx, r10d
0x18001b2c0  setnz   al
0x18001b2c3  mov     [rsp+38h+var_10], eax
0x18001b2c7  lea     edx, [r9+8]
0x18001b2cb  mov     [rsp+38h+var_18], rdi
0x18001b2d0  call    __acrt_MultiByteToWideChar
0x18001b2d5  test    eax, eax
0x18001b2d7  jz      short loc_18001B29E
0x18001b2d9  mov     eax, 1
0x18001b2de  jmp     short loc_18001B2E9
0x18001b2e0  mov     cs:qword_180079008, r14
0x18001b2e7  xor     eax, eax
0x18001b2e9  mov     rbx, [rsp+38h+arg_0]
0x18001b2ee  mov     rbp, [rsp+38h+arg_8]
0x18001b2f3  mov     rsi, [rsp+38h+arg_10]
0x18001b2f8  mov     rdi, [rsp+38h+arg_18]
0x18001b2fd  add     rsp, 30h
0x18001b301  pop     r14
0x18001b303  retn
```
