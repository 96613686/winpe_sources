# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Grow(unsigned __int64,bool)

- ea: `0x140007098`
- end: `0x1400070fb`
- name: `?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z`
- size: `99`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000749c`
- `0x14000758c`
- `0x1400077e4`
- `0x1400078b0`

## callees

- `0x140001680`
- `0x140006e80`
- `0x140007098`

## pseudocode

```c
bool __fastcall std::wstring::_Grow(_QWORD *a1, unsigned __int64 a2)
{
  bool v3; // zf
  _WORD *v4; // rdx

  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( a1[3] < a2 )
  {
    std::wstring::_Copy(a1, a2, a1[2]);
LABEL_10:
    v3 = a2 == 0;
    return !v3;
  }
  v3 = a2 == 0;
  if ( !a2 )
  {
    if ( a1[3] < 8u )
      v4 = a1;
    else
      v4 = (_WORD *)*a1;
    a1[2] = 0;
    *v4 = 0;
    goto LABEL_10;
  }
  return !v3;
}

```

## disassembly

```asm
0x140007098  push    rbx
0x14000709a  sub     rsp, 20h
0x14000709e  mov     rax, 7FFFFFFFFFFFFFFEh
0x1400070a8  mov     rbx, rdx
0x1400070ab  cmp     rdx, rax
0x1400070ae  jbe     short loc_1400070BD
0x1400070b0  lea     rcx, aStringTooLong; "string too long"
0x1400070b7  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400070bd  cmp     [rcx+18h], rbx
0x1400070c1  jnb     short loc_1400070CE
0x1400070c3  mov     r8, [rcx+10h]
0x1400070c7  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1400070cc  jmp     short loc_1400070EF
0x1400070ce  test    rbx, rbx
0x1400070d1  jnz     short loc_1400070F2
0x1400070d3  cmp     qword ptr [rcx+18h], 8
0x1400070d8  jb      short loc_1400070DF
0x1400070da  mov     rdx, [rcx]
0x1400070dd  jmp     short loc_1400070E2
0x1400070df  mov     rdx, rcx
0x1400070e2  xor     eax, eax
0x1400070e4  mov     qword ptr [rcx+10h], 0
0x1400070ec  mov     [rdx], ax
0x1400070ef  test    rbx, rbx
0x1400070f2  setnz   al
0x1400070f5  add     rsp, 20h
0x1400070f9  pop     rbx
0x1400070fa  retn
```
