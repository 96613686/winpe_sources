# common_fgets<wchar_t>(wchar_t * const,int,__crt_stdio_stream)

- ea: `0x140023408`
- end: `0x1400234db`
- name: `??$common_fgets@_W@@YAPEA_WQEA_WHV__crt_stdio_stream@@@Z`
- size: `211`
- prototype: `_WORD *__fastcall(_WORD *, int, FILE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400234dc`

## callees

- `0x1400046cc`
- `0x14000fa6c`
- `0x140011a04`
- `0x140011bbc`
- `0x140011bc8`
- `0x140023408`

## pseudocode

```c
_WORD *__fastcall common_fgets<wchar_t>(_WORD *a1, int a2, FILE *a3)
{
  _WORD *v6; // rdi
  int v7; // eax
  _WORD *v9; // rsi
  int i; // r14d
  int v11; // ecx

  v6 = 0;
  if ( a1 || (v7 = 0, !a2) )
    v7 = 1;
  if ( !v7 || a2 < 0 || !a3 )
  {
    *(_DWORD *)sub_14000FA6C() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
  if ( !a2 )
    return 0;
  sub_140011BBC(a3);
  v9 = a1;
  for ( i = 1; i != a2; ++i )
  {
    v11 = (unsigned __int16)sub_140011A04(a3);
    if ( v11 == 0xFFFF )
    {
      if ( v9 == a1 )
        goto LABEL_18;
      break;
    }
    *v9++ = v11;
    if ( v11 == 10 )
      break;
  }
  *v9 = 0;
  v6 = a1;
LABEL_18:
  sub_140011BC8(a3);
  return v6;
}

```

## disassembly

```asm
0x140023408  mov     [rsp+arg_8], rbx
0x14002340d  mov     [rsp+arg_10], r8
0x140023412  push    rsi
0x140023413  push    rdi
0x140023414  push    r12
0x140023416  push    r14
0x140023418  push    r15
0x14002341a  sub     rsp, 30h
0x14002341e  mov     rbx, r8
0x140023421  mov     r15d, edx
0x140023424  mov     r12, rcx
0x140023427  xor     edi, edi
0x140023429  test    rcx, rcx
0x14002342c  jnz     short loc_140023434
0x14002342e  test    edx, edx
0x140023430  mov     eax, edi
0x140023432  jnz     short loc_140023439
0x140023434  mov     eax, 1
0x140023439  test    eax, eax
0x14002343b  jnz     short loc_140023461
0x14002343d  call    sub_14000FA6C
0x140023442  mov     dword ptr [rax], 16h
0x140023448  call    _invalid_parameter_noinfo
0x14002344d  xor     eax, eax
0x14002344f  mov     rbx, [rsp+58h+arg_8]
0x140023454  add     rsp, 30h
0x140023458  pop     r15
0x14002345a  pop     r14
0x14002345c  pop     r12
0x14002345e  pop     rdi
0x14002345f  pop     rsi
0x140023460  retn
0x140023461  test    r15d, r15d
0x140023464  js      short loc_14002343D
0x140023466  test    rbx, rbx
0x140023469  jz      short loc_14002343D
0x14002346b  test    r15d, r15d
0x14002346e  jz      short loc_14002344D
0x140023470  mov     rcx, rbx
0x140023473  call    sub_140011BBC
0x140023478  nop
0x140023479  mov     rsi, r12
0x14002347c  mov     [rsp+58h+var_30], r12
0x140023481  mov     r14d, 1
0x140023487  mov     [rsp+58h+var_38], r14d
0x14002348c  cmp     r14d, r15d
0x14002348f  jz      short loc_1400234C5
0x140023491  mov     rcx, rbx; File
0x140023494  call    sub_140011A04
0x140023499  movzx   ecx, ax
0x14002349c  mov     [rsp+58h+arg_0], ecx
0x1400234a0  cmp     ecx, 0FFFFh
0x1400234a6  jnz     short loc_1400234AF
0x1400234a8  cmp     rsi, r12
0x1400234ab  jz      short loc_1400234CB
0x1400234ad  jmp     short loc_1400234C5
0x1400234af  mov     [rsi], cx
0x1400234b2  add     rsi, 2
0x1400234b6  mov     [rsp+58h+var_30], rsi
0x1400234bb  cmp     ecx, 0Ah
0x1400234be  jz      short loc_1400234C5
0x1400234c0  inc     r14d
0x1400234c3  jmp     short loc_140023487
0x1400234c5  mov     [rsi], di
0x1400234c8  mov     rdi, r12
0x1400234cb  mov     rcx, rbx
0x1400234ce  call    sub_140011BC8
0x1400234d3  mov     rax, rdi
0x1400234d6  jmp     loc_14002344F
```
