# __crt_mbstring::__c16rtomb_utf8(char *,char16_t,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x14001ada0`
- end: `0x14001ae43`
- name: `?__c16rtomb_utf8@__crt_mbstring@@YA_KPEAD_SPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `163`
- prototype: `__int64 __fastcall(__crt_mbstring *this, char *, struct __crt_cached_ptd_host *, struct _Mbstatet *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140012d30`

## callees

- `0x14001ada0`
- `0x140020554`
- `0x1400205f8`
- `0x140020600`

## pseudocode

```c
__int64 __fastcall __crt_mbstring::__c16rtomb_utf8(
        __crt_mbstring *this,
        char *a2,
        struct __crt_cached_ptd_host *a3,
        struct _Mbstatet *a4)
{
  __crt_mbstring *v4; // rbx
  unsigned __int16 v5; // ax
  __crt_mbstring *v7; // rax
  struct _Mbstatet *v8; // r8
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v4 = (__crt_mbstring *)&qword_14003E5C0;
  if ( a3 )
    v4 = a3;
  v5 = (_WORD)a2 + 9216;
  if ( *(_DWORD *)v4 )
  {
    if ( v5 > 0x3FFu )
      return __crt_mbstring::return_illegal_sequence(v4, a4, a3);
    v9 = 0;
    v7 = (__crt_mbstring *)sub_140020554(this, *(_DWORD *)v4 + ((unsigned __int16)a2 & 0x23FFu), &v9, a4);
    return __crt_mbstring::reset_and_return(v7, (unsigned __int64)v4, v8);
  }
  else
  {
    if ( v5 <= 0x3FFu )
      return __crt_mbstring::return_illegal_sequence(v4, a4, a3);
    if ( (unsigned __int16)((_WORD)a2 + 10240) > 0x3FFu )
    {
      return sub_140020554(this, (unsigned __int16)a2, v4, a4);
    }
    else
    {
      *(_DWORD *)v4 = (((unsigned __int16)a2 << 10) & 0xFC9FFC00) + 0x10000;
      return 0;
    }
  }
}

```

## disassembly

```asm
0x14001ada0  push    rbx
0x14001ada2  sub     rsp, 20h
0x14001ada6  test    r8, r8
0x14001ada9  lea     rbx, qword_14003E5C0
0x14001adb0  mov     eax, 2400h
0x14001adb5  mov     r10, rcx
0x14001adb8  cmovnz  rbx, r8
0x14001adbc  mov     ecx, 3FFh
0x14001adc1  add     eax, edx
0x14001adc3  cmp     dword ptr [rbx], 0
0x14001adc6  jnz     short loc_14001AE0F
0x14001adc8  cmp     ax, cx
0x14001adcb  ja      short loc_14001ADDA
0x14001adcd  mov     rdx, r9; struct _Mbstatet *
0x14001add0  mov     rcx, rbx; this
0x14001add3  call    ?return_illegal_sequence@__crt_mbstring@@YA_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z
0x14001add8  jmp     short loc_14001AE3D
0x14001adda  mov     eax, 2800h
0x14001addf  add     eax, edx
0x14001ade1  cmp     ax, cx
0x14001ade4  ja      short loc_14001ADFC
0x14001ade6  movzx   eax, dx
0x14001ade9  shl     eax, 0Ah
0x14001adec  and     eax, 0FC9FFC00h
0x14001adf1  add     eax, 10000h
0x14001adf6  mov     [rbx], eax
0x14001adf8  xor     eax, eax
0x14001adfa  jmp     short loc_14001AE3D
0x14001adfc  movzx   edx, dx
0x14001adff  mov     r8, rbx
0x14001ae02  mov     rcx, r10
0x14001ae05  add     rsp, 20h
0x14001ae09  pop     rbx
0x14001ae0a  jmp     sub_140020554
0x14001ae0f  cmp     ax, cx
0x14001ae12  ja      short loc_14001ADCD
0x14001ae14  and     [rsp+28h+arg_10], 0
0x14001ae1a  lea     r8, [rsp+28h+arg_10]
0x14001ae1f  movzx   edx, dx
0x14001ae22  mov     rcx, r10
0x14001ae25  and     edx, 0FFFF23FFh
0x14001ae2b  add     edx, [rbx]
0x14001ae2d  call    sub_140020554
0x14001ae32  mov     rdx, rbx; unsigned __int64
0x14001ae35  mov     rcx, rax; this
0x14001ae38  call    ?reset_and_return@__crt_mbstring@@YA_K_KPEAU_Mbstatet@@@Z
0x14001ae3d  add     rsp, 20h
0x14001ae41  pop     rbx
0x14001ae42  retn
```
