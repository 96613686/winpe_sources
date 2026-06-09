# _mbtowc_internal

- ea: `0x18001b8ec`
- end: `0x18001ba64`
- name: `_mbtowc_internal`
- size: `376`
- prototype: `__int64 __fastcall(__crt_mbstring *this, wchar_t *, char *, __crt_cached_ptd_host *)`
- caller_count: `21`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180015210`
- `0x18001ba64`
- `0x18001bb08`
- `0x18004b464`
- `0x18004ba60`
- `0x18004c098`
- `0x18004c694`
- `0x18004cc0c`
- `0x18004d198`
- `0x1800504e8`
- `0x1800505ac`
- `0x1800506a4`
- `0x180050768`
- `0x18005082c`
- `0x180050924`
- `0x180054cb0`
- `0x180054f40`
- `0x1800551d0`
- `0x180055460`
- `0x180055694`
- `0x1800558c8`

## callees

- `0x18000b67c`
- `0x18001512c`
- `0x18001b8ec`
- `0x18001bbc8`

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
    qword_18007CAB8 = 0;
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
  result = __crt_mbstring::__mbrtowc_utf8(this, a2, a3, (unsigned __int64)&qword_18007CAB8, (struct _Mbstatet *)a4, v12);
  if ( (result & 0x80000000) != 0LL )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x18001b8ec  mov     rax, rsp
0x18001b8ef  mov     [rax+8], rbx
0x18001b8f3  mov     [rax+10h], rbp
0x18001b8f7  mov     [rax+18h], rsi
0x18001b8fb  mov     [rax+20h], rdi
0x18001b8ff  push    r14
0x18001b901  sub     rsp, 30h
0x18001b905  xor     r14d, r14d
0x18001b908  mov     rbx, r9
0x18001b90b  mov     rbp, r8
0x18001b90e  mov     rsi, rdx
0x18001b911  mov     rdi, rcx
0x18001b914  test    rdx, rdx
0x18001b917  jz      loc_18001BA40
0x18001b91d  test    r8, r8
0x18001b920  jz      loc_18001BA40
0x18001b926  cmp     [rdx], r14b
0x18001b929  jnz     short loc_18001B93D
0x18001b92b  test    rcx, rcx
0x18001b92e  jz      loc_18001BA47
0x18001b934  mov     [rcx], r14w
0x18001b938  jmp     loc_18001BA47
0x18001b93d  cmp     [r9+28h], r14b
0x18001b941  jnz     short loc_18001B94B
0x18001b943  mov     rcx, rbx; this
0x18001b946  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001b94b  mov     rdx, [rbx+18h]
0x18001b94f  mov     r10d, [rdx+0Ch]
0x18001b953  cmp     r10d, 0FDE9h
0x18001b95a  jnz     short loc_18001B983
0x18001b95c  lea     r9, qword_18007CAB8; unsigned __int64
0x18001b963  mov     [rsp+38h+var_18], rbx; struct _Mbstatet *
0x18001b968  mov     r8, rbp; char *
0x18001b96b  mov     rdx, rsi; wchar_t *
0x18001b96e  mov     rcx, rdi; this
0x18001b971  call    ?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b976  or      ecx, 0FFFFFFFFh
0x18001b979  test    eax, eax
0x18001b97b  cmovs   eax, ecx
0x18001b97e  jmp     loc_18001BA49
0x18001b983  cmp     [rdx+138h], r14
0x18001b98a  jnz     short loc_18001B9A0
0x18001b98c  test    rdi, rdi
0x18001b98f  jz      loc_18001BA39
0x18001b995  movzx   eax, byte ptr [rsi]
0x18001b998  mov     [rdi], ax
0x18001b99b  jmp     loc_18001BA39
0x18001b9a0  movzx   ecx, byte ptr [rsi]
0x18001b9a3  mov     rax, [rdx]
0x18001b9a6  cmp     [rax+rcx*2], r14w
0x18001b9ab  jge     short loc_18001BA0E
0x18001b9ad  mov     r9d, [rdx+8]
0x18001b9b1  cmp     r9d, 1
0x18001b9b5  jle     short loc_18001B9E2
0x18001b9b7  cmp     ebp, r9d
0x18001b9ba  jl      short loc_18001B9E2
0x18001b9bc  mov     eax, r14d
0x18001b9bf  test    rdi, rdi
0x18001b9c2  mov     r8, rsi
0x18001b9c5  mov     edx, 9
0x18001b9ca  setnz   al
0x18001b9cd  mov     ecx, r10d
0x18001b9d0  mov     [rsp+38h+var_10], eax
0x18001b9d4  mov     [rsp+38h+var_18], rdi
0x18001b9d9  call    __acrt_MultiByteToWideChar
0x18001b9de  test    eax, eax
0x18001b9e0  jnz     short loc_18001B9F5
0x18001b9e2  mov     rax, [rbx+18h]
0x18001b9e6  movsxd  rcx, dword ptr [rax+8]
0x18001b9ea  cmp     rbp, rcx
0x18001b9ed  jb      short loc_18001B9FE
0x18001b9ef  cmp     [rsi+1], r14b
0x18001b9f3  jz      short loc_18001B9FE
0x18001b9f5  mov     rax, [rbx+18h]
0x18001b9f9  mov     eax, [rax+8]
0x18001b9fc  jmp     short loc_18001BA49
0x18001b9fe  mov     byte ptr [rbx+30h], 1
0x18001ba02  or      eax, 0FFFFFFFFh
0x18001ba05  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x18001ba0c  jmp     short loc_18001BA49
0x18001ba0e  mov     eax, r14d
0x18001ba11  mov     r9d, 1
0x18001ba17  test    rdi, rdi
0x18001ba1a  mov     r8, rsi
0x18001ba1d  mov     ecx, r10d
0x18001ba20  setnz   al
0x18001ba23  mov     [rsp+38h+var_10], eax
0x18001ba27  lea     edx, [r9+8]
0x18001ba2b  mov     [rsp+38h+var_18], rdi
0x18001ba30  call    __acrt_MultiByteToWideChar
0x18001ba35  test    eax, eax
0x18001ba37  jz      short loc_18001B9FE
0x18001ba39  mov     eax, 1
0x18001ba3e  jmp     short loc_18001BA49
0x18001ba40  mov     cs:qword_18007CAB8, r14
0x18001ba47  xor     eax, eax
0x18001ba49  mov     rbx, [rsp+38h+arg_0]
0x18001ba4e  mov     rbp, [rsp+38h+arg_8]
0x18001ba53  mov     rsi, [rsp+38h+arg_10]
0x18001ba58  mov     rdi, [rsp+38h+arg_18]
0x18001ba5d  add     rsp, 30h
0x18001ba61  pop     r14
0x18001ba63  retn
```
