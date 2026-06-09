# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x140007cc8`
- end: `0x140007d67`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `159`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140003028`
- `0x1400049f0`
- `0x140008694`

## callees

- `0x140007494`
- `0x140007544`
- `0x140007bfc`
- `0x140007cc8`
- `0x140007db4`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, _BYTE *a2, unsigned __int64 a3)
{
  _BYTE *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rcx

  if ( std::wstring::_Inside(a1, (unsigned __int64)a2) )
  {
    if ( (unsigned __int64)a1[3] < 8 )
      v6 = a1;
    else
      v6 = *a1;
    return std::wstring::assign(a1, a1, (a2 - v6) >> 1, a3);
  }
  else
  {
    if ( (unsigned __int8)std::wstring::_Grow(a1, a3) )
    {
      if ( (unsigned __int64)a1[3] < 8 )
        v8 = a1;
      else
        v8 = *a1;
      std::char_traits<unsigned short>::copy(v8, a2, a3);
      if ( (unsigned __int64)a1[3] < 8 )
        v9 = a1;
      else
        v9 = *a1;
      a1[2] = (void *)a3;
      *(_WORD *)&v9[2 * a3] = 0;
    }
    return a1;
  }
}

```

## disassembly

```asm
0x140007cc8  mov     [rsp+arg_0], rbx
0x140007ccd  mov     [rsp+arg_8], rsi
0x140007cd2  push    rdi
0x140007cd3  sub     rsp, 20h
0x140007cd7  mov     rdi, r8
0x140007cda  mov     rsi, rdx
0x140007cdd  mov     rbx, rcx
0x140007ce0  call    ?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z; std::wstring::_Inside(ushort const *)
0x140007ce5  test    al, al
0x140007ce7  jz      short loc_140007D11
0x140007ce9  cmp     qword ptr [rbx+18h], 8
0x140007cee  jb      short loc_140007CF5
0x140007cf0  mov     rax, [rbx]
0x140007cf3  jmp     short loc_140007CF8
0x140007cf5  mov     rax, rbx
0x140007cf8  sub     rsi, rax
0x140007cfb  mov     r9, rdi
0x140007cfe  sar     rsi, 1
0x140007d01  mov     rdx, rbx
0x140007d04  mov     r8, rsi
0x140007d07  mov     rcx, rbx
0x140007d0a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x140007d0f  jmp     short loc_140007D56
0x140007d11  mov     rdx, rdi
0x140007d14  mov     rcx, rbx
0x140007d17  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x140007d1c  test    al, al
0x140007d1e  jz      short loc_140007D53
0x140007d20  cmp     qword ptr [rbx+18h], 8
0x140007d25  jb      short loc_140007D2C
0x140007d27  mov     rcx, [rbx]
0x140007d2a  jmp     short loc_140007D2F
0x140007d2c  mov     rcx, rbx
0x140007d2f  mov     r8, rdi
0x140007d32  mov     rdx, rsi
0x140007d35  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x140007d3a  cmp     qword ptr [rbx+18h], 8
0x140007d3f  jb      short loc_140007D46
0x140007d41  mov     rcx, [rbx]
0x140007d44  jmp     short loc_140007D49
0x140007d46  mov     rcx, rbx
0x140007d49  xor     eax, eax
0x140007d4b  mov     [rbx+10h], rdi
0x140007d4f  mov     [rcx+rdi*2], ax
0x140007d53  mov     rax, rbx
0x140007d56  mov     rbx, [rsp+28h+arg_0]
0x140007d5b  mov     rsi, [rsp+28h+arg_8]
0x140007d60  add     rsp, 20h
0x140007d64  pop     rdi
0x140007d65  retn
```
