# __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x1800582c0`
- end: `0x180058363`
- name: `?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `163`
- prototype: `unsigned __int64 __fastcall(__crt_mbstring *__hidden this, char *, char16_t, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x180049434`
- `0x18004996c`
- `0x180049ebc`
- `0x18004a3f4`
- `0x18004a864`
- `0x18004ad14`
- `0x180053f2c`
- `0x180054118`
- `0x180054304`
- `0x1800544f0`
- `0x180054690`
- `0x180054830`
- `0x1800583b4`

## callees

- `0x180021adc`
- `0x180021ae4`
- `0x1800582c0`
- `0x18005c4b4`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__c16rtomb_utf8(
        __crt_mbstring *this,
        char *a2,
        struct __crt_cached_ptd_host *a3,
        struct _Mbstatet *a4,
        struct __crt_cached_ptd_host *a5)
{
  __crt_mbstring *v5; // rbx
  unsigned __int16 v6; // ax
  __crt_mbstring *v8; // rax
  struct _Mbstatet *v9; // r8
  struct __crt_cached_ptd_host *v10; // [rsp+20h] [rbp-8h]
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v5 = (__crt_mbstring *)&qword_1800796B0;
  if ( a3 )
    v5 = a3;
  v6 = (_WORD)a2 + 9216;
  if ( *(_DWORD *)v5 )
  {
    if ( v6 > 0x3FFu )
      return __crt_mbstring::return_illegal_sequence(v5, a4, a3);
    v11 = 0;
    v8 = (__crt_mbstring *)__crt_mbstring::__c32rtomb_utf8(
                             this,
                             (char *)(*(_DWORD *)v5 + ((unsigned __int16)a2 & 0x23FFu)),
                             (char32_t)&v11,
                             a4,
                             v10);
    return __crt_mbstring::reset_and_return(v8, (unsigned __int64)v5, v9);
  }
  else
  {
    if ( v6 <= 0x3FFu )
      return __crt_mbstring::return_illegal_sequence(v5, a4, a3);
    if ( (unsigned __int16)((_WORD)a2 + 10240) > 0x3FFu )
    {
      return __crt_mbstring::__c32rtomb_utf8(this, (char *)(unsigned __int16)a2, (char32_t)v5, a4, a5);
    }
    else
    {
      *(_DWORD *)v5 = (((unsigned __int16)a2 << 10) & 0xFC9FFC00) + 0x10000;
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800582c0  push    rbx; struct __crt_cached_ptd_host *
0x1800582c2  sub     rsp, 20h
0x1800582c6  test    r8, r8
0x1800582c9  lea     rbx, qword_1800796B0
0x1800582d0  mov     eax, 2400h
0x1800582d5  mov     r10, rcx
0x1800582d8  cmovnz  rbx, r8
0x1800582dc  mov     ecx, 3FFh
0x1800582e1  add     eax, edx
0x1800582e3  cmp     dword ptr [rbx], 0
0x1800582e6  jnz     short loc_18005832F
0x1800582e8  cmp     ax, cx
0x1800582eb  ja      short loc_1800582FA
0x1800582ed  mov     rdx, r9; struct _Mbstatet *
0x1800582f0  mov     rcx, rbx; this
0x1800582f3  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x1800582f8  jmp     short loc_18005835D
0x1800582fa  mov     eax, 2800h
0x1800582ff  add     eax, edx
0x180058301  cmp     ax, cx
0x180058304  ja      short loc_18005831C
0x180058306  movzx   eax, dx
0x180058309  shl     eax, 0Ah
0x18005830c  and     eax, 0FC9FFC00h
0x180058311  add     eax, 10000h
0x180058316  mov     [rbx], eax
0x180058318  xor     eax, eax
0x18005831a  jmp     short loc_18005835D
0x18005831c  movzx   edx, dx; char *
0x18005831f  mov     r8, rbx; char32_t
0x180058322  mov     rcx, r10; this
0x180058325  add     rsp, 20h
0x180058329  pop     rbx
0x18005832a  jmp     ?__c32rtomb_utf8@__crt_mbstring@@YA_KPEAD_UPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c32rtomb_utf8(char *,char32_t,_Mbstatet *,__crt_cached_ptd_host &)
0x18005832f  cmp     ax, cx
0x180058332  ja      short loc_1800582ED
0x180058334  and     [rsp+28h+arg_10], 0
0x18005833a  lea     r8, [rsp+28h+arg_10]; char32_t
0x18005833f  movzx   edx, dx
0x180058342  mov     rcx, r10; this
0x180058345  and     edx, 0FFFF23FFh
0x18005834b  add     edx, [rbx]; char *
0x18005834d  call    ?__c32rtomb_utf8@__crt_mbstring@@YA_KPEAD_UPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c32rtomb_utf8(char *,char32_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180058352  mov     rdx, rbx; unsigned __int64
0x180058355  mov     rcx, rax; this
0x180058358  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x18005835d  add     rsp, 20h
0x180058361  pop     rbx
0x180058362  retn
```
