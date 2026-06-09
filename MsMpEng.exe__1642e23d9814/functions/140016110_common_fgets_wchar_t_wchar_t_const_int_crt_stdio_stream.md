# common_fgets<wchar_t>(wchar_t * const,int,__crt_stdio_stream)

- ea: `0x140016110`
- end: `0x1400161e3`
- name: `??$common_fgets@_W@@YAPEA_WQEA_WHV__crt_stdio_stream@@@Z`
- size: `211`
- prototype: `_WORD *__fastcall(_WORD *, int, FILE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400161e4`

## callees

- `0x14001609c`
- `0x140016110`
- `0x140016ea0`
- `0x14001b1ec`
- `0x14001b1f8`
- `0x14001b8bc`

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
    *(_DWORD *)sub_140016EA0() = 22;
    invalid_parameter_noinfo();
    return 0;
  }
  if ( !a2 )
    return 0;
  lock_file(a3);
  v9 = a1;
  for ( i = 1; i != a2; ++i )
  {
    v11 = (unsigned __int16)sub_14001B8BC(a3);
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
  unlock_file(a3);
  return v6;
}

```

## disassembly

```asm
0x140016110  mov     [rsp+arg_8], rbx
0x140016115  mov     [rsp+arg_10], r8
0x14001611a  push    rsi
0x14001611b  push    rdi
0x14001611c  push    r12
0x14001611e  push    r14
0x140016120  push    r15
0x140016122  sub     rsp, 30h
0x140016126  mov     rbx, r8
0x140016129  mov     r15d, edx
0x14001612c  mov     r12, rcx
0x14001612f  xor     edi, edi
0x140016131  test    rcx, rcx
0x140016134  jnz     short loc_14001613C
0x140016136  test    edx, edx
0x140016138  mov     eax, edi
0x14001613a  jnz     short loc_140016141
0x14001613c  mov     eax, 1
0x140016141  test    eax, eax
0x140016143  jnz     short loc_140016169
0x140016145  call    sub_140016EA0
0x14001614a  mov     dword ptr [rax], 16h
0x140016150  call    _invalid_parameter_noinfo
0x140016155  xor     eax, eax
0x140016157  mov     rbx, [rsp+58h+arg_8]
0x14001615c  add     rsp, 30h
0x140016160  pop     r15
0x140016162  pop     r14
0x140016164  pop     r12
0x140016166  pop     rdi
0x140016167  pop     rsi
0x140016168  retn
0x140016169  test    r15d, r15d
0x14001616c  js      short loc_140016145
0x14001616e  test    rbx, rbx
0x140016171  jz      short loc_140016145
0x140016173  test    r15d, r15d
0x140016176  jz      short loc_140016155
0x140016178  mov     rcx, rbx; File
0x14001617b  call    _lock_file
0x140016180  nop
0x140016181  mov     rsi, r12
0x140016184  mov     [rsp+58h+var_30], r12
0x140016189  mov     r14d, 1
0x14001618f  mov     [rsp+58h+var_38], r14d
0x140016194  cmp     r14d, r15d
0x140016197  jz      short loc_1400161CD
0x140016199  mov     rcx, rbx; File
0x14001619c  call    sub_14001B8BC
0x1400161a1  movzx   ecx, ax
0x1400161a4  mov     [rsp+58h+arg_0], ecx
0x1400161a8  cmp     ecx, 0FFFFh
0x1400161ae  jnz     short loc_1400161B7
0x1400161b0  cmp     rsi, r12
0x1400161b3  jz      short loc_1400161D3
0x1400161b5  jmp     short loc_1400161CD
0x1400161b7  mov     [rsi], cx
0x1400161ba  add     rsi, 2
0x1400161be  mov     [rsp+58h+var_30], rsi
0x1400161c3  cmp     ecx, 0Ah
0x1400161c6  jz      short loc_1400161CD
0x1400161c8  inc     r14d
0x1400161cb  jmp     short loc_14001618F
0x1400161cd  mov     [rsi], di
0x1400161d0  mov     rdi, r12
0x1400161d3  mov     rcx, rbx; File
0x1400161d6  call    _unlock_file
0x1400161db  mov     rax, rdi
0x1400161de  jmp     loc_140016157
```
