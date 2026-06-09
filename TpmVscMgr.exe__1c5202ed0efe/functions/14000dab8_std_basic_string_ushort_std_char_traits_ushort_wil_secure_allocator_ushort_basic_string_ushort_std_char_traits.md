# std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)

- ea: `0x14000dab8`
- end: `0x14000db37`
- name: `??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ`
- size: `127`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `37`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000d5a8`
- `0x14000db60`
- `0x14000dbfc`
- `0x14000dc78`
- `0x14000dc98`
- `0x14000dcf8`
- `0x14000ded8`
- `0x14000ecf4`
- `0x14000eef8`
- `0x14000f280`
- `0x14000f54c`
- `0x140010a68`
- `0x140010c90`
- `0x14001206a`
- `0x1400121d4`
- `0x140012200`
- `0x14001222c`
- `0x140012316`
- `0x140012328`
- `0x14001235e`
- `0x1400124e0`
- `0x140012500`
- `0x140012520`
- `0x140012540`
- `0x140012560`
- `0x140012580`
- `0x1400125a0`
- `0x1400125c0`
- `0x1400125e0`
- `0x140012600`
- `0x140012620`
- `0x140012640`
- `0x140012660`
- `0x140012680`
- `0x1400126a0`
- `0x1400126c0`
- `0x1400126e0`

## callees

- `0x140001934`
- `0x14000dab8`

## pseudocode

```c
__int64 __fastcall std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
        _QWORD *a1)
{
  unsigned __int64 v1; // rdx
  _BYTE *v3; // rax
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r8
  _BYTE *i; // rcx
  _BYTE *v7; // rcx
  __int64 result; // rax

  v1 = a1[3];
  if ( v1 > 7 )
  {
    v3 = (_BYTE *)*a1;
    v4 = 2 * v1 + 2;
    v5 = v4;
    for ( i = (_BYTE *)*a1; v5; --v5 )
      *i++ = 0;
    if ( v4 < 0x1000 )
    {
      v7 = v3;
    }
    else
    {
      v7 = (_BYTE *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v7 - 8) > 0x1F )
        __fastfail(5u);
      v4 += 39LL;
    }
    operator delete(v7, v4);
  }
  result = 0;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  a1[3] = 7;
  return result;
}

```

## disassembly

```asm
0x14000dab8  push    rbx
0x14000daba  sub     rsp, 20h
0x14000dabe  mov     rdx, [rcx+18h]
0x14000dac2  mov     rbx, rcx
0x14000dac5  cmp     rdx, 7
0x14000dac9  jbe     short loc_14000DB1C
0x14000dacb  mov     rax, [rcx]
0x14000dace  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x14000dad6  mov     r8, rdx
0x14000dad9  mov     rcx, rax
0x14000dadc  test    rdx, rdx
0x14000dadf  jz      short loc_14000DAED
0x14000dae1  mov     byte ptr [rcx], 0
0x14000dae4  inc     rcx
0x14000dae7  sub     r8, 1
0x14000daeb  jnz     short loc_14000DAE1
0x14000daed  cmp     rdx, 1000h
0x14000daf4  jb      short loc_14000DB14
0x14000daf6  mov     rcx, [rax-8]
0x14000dafa  sub     rax, rcx
0x14000dafd  sub     rax, 8
0x14000db01  cmp     rax, 1Fh
0x14000db05  ja      short loc_14000DB0D
0x14000db07  add     rdx, 27h ; '''
0x14000db0b  jmp     short loc_14000DB17
0x14000db0d  mov     ecx, 5
0x14000db12  int     29h; Win8: RtlFailFast(ecx)
0x14000db14  mov     rcx, rax; void *
0x14000db17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000db1c  xor     eax, eax
0x14000db1e  mov     qword ptr [rbx+10h], 0
0x14000db26  mov     [rbx], ax
0x14000db29  mov     qword ptr [rbx+18h], 7
0x14000db31  add     rsp, 20h
0x14000db35  pop     rbx
0x14000db36  retn
```
