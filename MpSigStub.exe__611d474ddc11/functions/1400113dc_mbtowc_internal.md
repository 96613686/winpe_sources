# _mbtowc_internal

- ea: `0x1400113dc`
- end: `0x140011554`
- name: `_mbtowc_internal`
- size: `376`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int8 *, unsigned __int64, __crt_cached_ptd_host *this)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000e470`
- `0x14000ef7c`
- `0x140011554`
- `0x1400191f8`

## callees

- `0x14000ad70`
- `0x1400113dc`
- `0x1400149ac`
- `0x14001511c`

## pseudocode

```c
__int64 __fastcall mbtowc_internal(_WORD *a1, unsigned __int8 *a2, unsigned __int64 a3, __crt_cached_ptd_host *this)
{
  __int64 v8; // rdx
  unsigned int v9; // r10d
  __int64 result; // rax
  __int64 v11; // r9

  if ( !a2 || !a3 )
  {
    *(_QWORD *)&qword_1400D6998 = 0;
    return 0;
  }
  if ( !*a2 )
  {
    if ( a1 )
      *a1 = 0;
    return 0;
  }
  if ( !*((_BYTE *)this + 40) )
    __crt_cached_ptd_host::update_locale_slow(this);
  v8 = *((_QWORD *)this + 3);
  v9 = *(_DWORD *)(v8 + 12);
  if ( v9 != 65001 )
  {
    if ( !*(_QWORD *)(v8 + 312) )
    {
      if ( a1 )
        *a1 = *a2;
      return 1;
    }
    if ( *(__int16 *)(*(_QWORD *)v8 + 2LL * *a2) >= 0 )
    {
      if ( (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2, 1, a1, a1 != 0) )
        return 1;
    }
    else
    {
      v11 = *(unsigned int *)(v8 + 8);
      if ( (int)v11 > 1 && (int)a3 >= (int)v11 && (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2, v11, a1, a1 != 0)
        || a3 >= *(int *)(*((_QWORD *)this + 3) + 8LL) && a2[1] )
      {
        return *(unsigned int *)(*((_QWORD *)this + 3) + 8LL);
      }
    }
    *((_BYTE *)this + 48) = 1;
    result = 0xFFFFFFFFLL;
    *((_DWORD *)this + 11) = 42;
    return result;
  }
  result = sub_14001511C((int)a1, (int)a2, a3, (int)&qword_1400D6998, (struct _Mbstatet *)this);
  if ( (int)result < 0 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x1400113dc  mov     rax, rsp
0x1400113df  mov     [rax+8], rbx
0x1400113e3  mov     [rax+10h], rbp
0x1400113e7  mov     [rax+18h], rsi
0x1400113eb  mov     [rax+20h], rdi
0x1400113ef  push    r14
0x1400113f1  sub     rsp, 30h
0x1400113f5  xor     r14d, r14d
0x1400113f8  mov     rbx, r9
0x1400113fb  mov     rbp, r8
0x1400113fe  mov     rsi, rdx
0x140011401  mov     rdi, rcx
0x140011404  test    rdx, rdx
0x140011407  jz      loc_140011530
0x14001140d  test    r8, r8
0x140011410  jz      loc_140011530
0x140011416  cmp     [rdx], r14b
0x140011419  jnz     short loc_14001142D
0x14001141b  test    rcx, rcx
0x14001141e  jz      loc_140011537
0x140011424  mov     [rcx], r14w
0x140011428  jmp     loc_140011537
0x14001142d  cmp     [r9+28h], r14b
0x140011431  jnz     short loc_14001143B
0x140011433  mov     rcx, rbx; this
0x140011436  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14001143b  mov     rdx, [rbx+18h]
0x14001143f  mov     r10d, [rdx+0Ch]
0x140011443  cmp     r10d, 0FDE9h
0x14001144a  jnz     short loc_140011473
0x14001144c  lea     r9, qword_1400D6998; int
0x140011453  mov     [rsp+38h+var_18], rbx; struct _Mbstatet *
0x140011458  mov     r8, rbp; int
0x14001145b  mov     rdx, rsi; int
0x14001145e  mov     rcx, rdi; int
0x140011461  call    sub_14001511C
0x140011466  or      ecx, 0FFFFFFFFh
0x140011469  test    eax, eax
0x14001146b  cmovs   eax, ecx
0x14001146e  jmp     loc_140011539
0x140011473  cmp     [rdx+138h], r14
0x14001147a  jnz     short loc_140011490
0x14001147c  test    rdi, rdi
0x14001147f  jz      loc_140011529
0x140011485  movzx   eax, byte ptr [rsi]
0x140011488  mov     [rdi], ax
0x14001148b  jmp     loc_140011529
0x140011490  movzx   ecx, byte ptr [rsi]
0x140011493  mov     rax, [rdx]
0x140011496  cmp     [rax+rcx*2], r14w
0x14001149b  jge     short loc_1400114FE
0x14001149d  mov     r9d, [rdx+8]
0x1400114a1  cmp     r9d, 1
0x1400114a5  jle     short loc_1400114D2
0x1400114a7  cmp     ebp, r9d
0x1400114aa  jl      short loc_1400114D2
0x1400114ac  mov     eax, r14d
0x1400114af  test    rdi, rdi
0x1400114b2  mov     r8, rsi
0x1400114b5  mov     edx, 9
0x1400114ba  setnz   al
0x1400114bd  mov     ecx, r10d
0x1400114c0  mov     [rsp+38h+var_10], eax
0x1400114c4  mov     [rsp+38h+var_18], rdi
0x1400114c9  call    __acrt_MultiByteToWideChar
0x1400114ce  test    eax, eax
0x1400114d0  jnz     short loc_1400114E5
0x1400114d2  mov     rax, [rbx+18h]
0x1400114d6  movsxd  rcx, dword ptr [rax+8]
0x1400114da  cmp     rbp, rcx
0x1400114dd  jb      short loc_1400114EE
0x1400114df  cmp     [rsi+1], r14b
0x1400114e3  jz      short loc_1400114EE
0x1400114e5  mov     rax, [rbx+18h]
0x1400114e9  mov     eax, [rax+8]
0x1400114ec  jmp     short loc_140011539
0x1400114ee  mov     byte ptr [rbx+30h], 1
0x1400114f2  or      eax, 0FFFFFFFFh
0x1400114f5  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x1400114fc  jmp     short loc_140011539
0x1400114fe  mov     eax, r14d
0x140011501  mov     r9d, 1
0x140011507  test    rdi, rdi
0x14001150a  mov     r8, rsi
0x14001150d  mov     ecx, r10d
0x140011510  setnz   al
0x140011513  mov     [rsp+38h+var_10], eax
0x140011517  lea     edx, [r9+8]
0x14001151b  mov     [rsp+38h+var_18], rdi
0x140011520  call    __acrt_MultiByteToWideChar
0x140011525  test    eax, eax
0x140011527  jz      short loc_1400114EE
0x140011529  mov     eax, 1
0x14001152e  jmp     short loc_140011539
0x140011530  mov     cs:qword_1400D6998, r14
0x140011537  xor     eax, eax
0x140011539  mov     rbx, [rsp+38h+arg_0]
0x14001153e  mov     rbp, [rsp+38h+arg_8]
0x140011543  mov     rsi, [rsp+38h+arg_10]
0x140011548  mov     rdi, [rsp+38h+arg_18]
0x14001154d  add     rsp, 30h
0x140011551  pop     r14
0x140011553  retn
```
