# __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x1800585a0`
- end: `0x180058643`
- name: `?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `163`
- prototype: `unsigned __int64 __fastcall(__crt_mbstring *__hidden this, char *, char16_t, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x180049714`
- `0x180049c4c`
- `0x18004a19c`
- `0x18004a6d4`
- `0x18004ab44`
- `0x18004aff4`
- `0x18005420c`
- `0x1800543f8`
- `0x1800545e4`
- `0x1800547d0`
- `0x180054970`
- `0x180054b10`
- `0x180058694`

## callees

- `0x18002223c`
- `0x180022244`
- `0x1800585a0`
- `0x18005c794`

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

  v5 = (__crt_mbstring *)&qword_18007CBE8;
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
0x1800585a0  push    rbx; struct __crt_cached_ptd_host *
0x1800585a2  sub     rsp, 20h
0x1800585a6  test    r8, r8
0x1800585a9  lea     rbx, qword_18007CBE8
0x1800585b0  mov     eax, 2400h
0x1800585b5  mov     r10, rcx
0x1800585b8  cmovnz  rbx, r8
0x1800585bc  mov     ecx, 3FFh
0x1800585c1  add     eax, edx
0x1800585c3  cmp     dword ptr [rbx], 0
0x1800585c6  jnz     short loc_18005860F
0x1800585c8  cmp     ax, cx
0x1800585cb  ja      short loc_1800585DA
0x1800585cd  mov     rdx, r9; struct _Mbstatet *
0x1800585d0  mov     rcx, rbx; this
0x1800585d3  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::return_illegal_sequence(_Mbstatet *,__crt_cached_ptd_host &)
0x1800585d8  jmp     short loc_18005863D
0x1800585da  mov     eax, 2800h
0x1800585df  add     eax, edx
0x1800585e1  cmp     ax, cx
0x1800585e4  ja      short loc_1800585FC
0x1800585e6  movzx   eax, dx
0x1800585e9  shl     eax, 0Ah
0x1800585ec  and     eax, 0FC9FFC00h
0x1800585f1  add     eax, 10000h
0x1800585f6  mov     [rbx], eax
0x1800585f8  xor     eax, eax
0x1800585fa  jmp     short loc_18005863D
0x1800585fc  movzx   edx, dx; char *
0x1800585ff  mov     r8, rbx; char32_t
0x180058602  mov     rcx, r10; this
0x180058605  add     rsp, 20h
0x180058609  pop     rbx
0x18005860a  jmp     ?__c32rtomb_utf8@__crt_mbstring@@YA_KPEAD_UPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c32rtomb_utf8(char *,char32_t,_Mbstatet *,__crt_cached_ptd_host &)
0x18005860f  cmp     ax, cx
0x180058612  ja      short loc_1800585CD
0x180058614  and     [rsp+28h+arg_10], 0
0x18005861a  lea     r8, [rsp+28h+arg_10]; char32_t
0x18005861f  movzx   edx, dx
0x180058622  mov     rcx, r10; this
0x180058625  and     edx, 0FFFF23FFh
0x18005862b  add     edx, [rbx]; char *
0x18005862d  call    ?__c32rtomb_utf8@__crt_mbstring@@YA_KPEAD_UPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__c32rtomb_utf8(char *,char32_t,_Mbstatet *,__crt_cached_ptd_host &)
0x180058632  mov     rdx, rbx; unsigned __int64
0x180058635  mov     rcx, rax; this
0x180058638  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z; __crt_mbstring::reset_and_return(unsigned __int64,_Mbstatet *)
0x18005863d  add     rsp, 20h
0x180058641  pop     rbx
0x180058642  retn
```
