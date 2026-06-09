# _mbtowc_internal

- ea: `0x140014058`
- end: `0x1400141d0`
- name: `_mbtowc_internal`
- size: `376`
- prototype: `__int64 __fastcall(__crt_mbstring *this, wchar_t *, char *, __crt_cached_ptd_host *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000f6b0`
- `0x1400102c4`
- `0x14001a20c`

## callees

- `0x14000c750`
- `0x140014058`
- `0x1400156e4`
- `0x140017024`

## pseudocode

```c
unsigned __int64 __fastcall mbtowc_internal(__crt_mbstring *this, wchar_t *a2, char *a3, __crt_cached_ptd_host *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // r10d
  unsigned __int64 result; // rax
  int v11; // r9d
  struct __crt_cached_ptd_host *v12; // [rsp+28h] [rbp-10h]

  if ( !a2 || !a3 )
  {
    qword_14003CB80 = 0;
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
      if ( (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2) )
        return 1;
    }
    else
    {
      v11 = *(_DWORD *)(v8 + 8);
      if ( v11 > 1 && (int)a3 >= v11 && (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2)
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
  result = __crt_mbstring::__mbrtowc_utf8(this, a2, a3, (unsigned __int64)&qword_14003CB80, (struct _Mbstatet *)a4, v12);
  if ( (result & 0x80000000) != 0LL )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x140014058  mov     rax, rsp
0x14001405b  mov     [rax+8], rbx
0x14001405f  mov     [rax+10h], rbp
0x140014063  mov     [rax+18h], rsi
0x140014067  mov     [rax+20h], rdi
0x14001406b  push    r14
0x14001406d  sub     rsp, 30h
0x140014071  xor     r14d, r14d
0x140014074  mov     rbx, r9
0x140014077  mov     rbp, r8
0x14001407a  mov     rsi, rdx
0x14001407d  mov     rdi, rcx
0x140014080  test    rdx, rdx
0x140014083  jz      loc_1400141AC
0x140014089  test    r8, r8
0x14001408c  jz      loc_1400141AC
0x140014092  cmp     [rdx], r14b
0x140014095  jnz     short loc_1400140A9
0x140014097  test    rcx, rcx
0x14001409a  jz      loc_1400141B3
0x1400140a0  mov     [rcx], r14w
0x1400140a4  jmp     loc_1400141B3
0x1400140a9  cmp     [r9+28h], r14b
0x1400140ad  jnz     short loc_1400140B7
0x1400140af  mov     rcx, rbx; this
0x1400140b2  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x1400140b7  mov     rdx, [rbx+18h]
0x1400140bb  mov     r10d, [rdx+0Ch]
0x1400140bf  cmp     r10d, 0FDE9h
0x1400140c6  jnz     short loc_1400140EF
0x1400140c8  lea     r9, qword_14003CB80; unsigned __int64
0x1400140cf  mov     [rsp+38h+var_18], rbx; struct _Mbstatet *
0x1400140d4  mov     r8, rbp; char *
0x1400140d7  mov     rdx, rsi; wchar_t *
0x1400140da  mov     rcx, rdi; this
0x1400140dd  call    ?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x1400140e2  or      ecx, 0FFFFFFFFh
0x1400140e5  test    eax, eax
0x1400140e7  cmovs   eax, ecx
0x1400140ea  jmp     loc_1400141B5
0x1400140ef  cmp     [rdx+138h], r14
0x1400140f6  jnz     short loc_14001410C
0x1400140f8  test    rdi, rdi
0x1400140fb  jz      loc_1400141A5
0x140014101  movzx   eax, byte ptr [rsi]
0x140014104  mov     [rdi], ax
0x140014107  jmp     loc_1400141A5
0x14001410c  movzx   ecx, byte ptr [rsi]
0x14001410f  mov     rax, [rdx]
0x140014112  cmp     [rax+rcx*2], r14w
0x140014117  jge     short loc_14001417A
0x140014119  mov     r9d, [rdx+8]
0x14001411d  cmp     r9d, 1
0x140014121  jle     short loc_14001414E
0x140014123  cmp     ebp, r9d
0x140014126  jl      short loc_14001414E
0x140014128  mov     eax, r14d
0x14001412b  test    rdi, rdi
0x14001412e  mov     r8, rsi
0x140014131  mov     edx, 9
0x140014136  setnz   al
0x140014139  mov     ecx, r10d
0x14001413c  mov     [rsp+38h+var_10], eax
0x140014140  mov     [rsp+38h+var_18], rdi
0x140014145  call    __acrt_MultiByteToWideChar
0x14001414a  test    eax, eax
0x14001414c  jnz     short loc_140014161
0x14001414e  mov     rax, [rbx+18h]
0x140014152  movsxd  rcx, dword ptr [rax+8]
0x140014156  cmp     rbp, rcx
0x140014159  jb      short loc_14001416A
0x14001415b  cmp     [rsi+1], r14b
0x14001415f  jz      short loc_14001416A
0x140014161  mov     rax, [rbx+18h]
0x140014165  mov     eax, [rax+8]
0x140014168  jmp     short loc_1400141B5
0x14001416a  mov     byte ptr [rbx+30h], 1
0x14001416e  or      eax, 0FFFFFFFFh
0x140014171  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x140014178  jmp     short loc_1400141B5
0x14001417a  mov     eax, r14d
0x14001417d  mov     r9d, 1
0x140014183  test    rdi, rdi
0x140014186  mov     r8, rsi
0x140014189  mov     ecx, r10d
0x14001418c  setnz   al
0x14001418f  mov     [rsp+38h+var_10], eax
0x140014193  lea     edx, [r9+8]
0x140014197  mov     [rsp+38h+var_18], rdi
0x14001419c  call    __acrt_MultiByteToWideChar
0x1400141a1  test    eax, eax
0x1400141a3  jz      short loc_14001416A
0x1400141a5  mov     eax, 1
0x1400141aa  jmp     short loc_1400141B5
0x1400141ac  mov     cs:qword_14003CB80, r14
0x1400141b3  xor     eax, eax
0x1400141b5  mov     rbx, [rsp+38h+arg_0]
0x1400141ba  mov     rbp, [rsp+38h+arg_8]
0x1400141bf  mov     rsi, [rsp+38h+arg_10]
0x1400141c4  mov     rdi, [rsp+38h+arg_18]
0x1400141c9  add     rsp, 30h
0x1400141cd  pop     r14
0x1400141cf  retn
```
