# HampIpcChannelAddCallbackUnsafe

- ea: `0x180009d40`
- end: `0x180009e62`
- name: `HampIpcChannelAddCallbackUnsafe`
- size: `290`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800098f0`
- `0x180009ad0`
- `0x18000bed0`
- `0x180019620`

## callees

- `0x180009d40`
- `0x180009e70`

## import_xrefs

- `ntdll!RtlRbInsertNodeEx` at `0x180009e04`

## pseudocode

```c
__int64 __fastcall HampIpcChannelAddCallbackUnsafe(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r14
  unsigned __int64 v5; // rbx
  int v6; // edi
  int v7; // eax
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rbx
  int v10; // edi
  unsigned __int64 v11; // rax

  v4 = *(_QWORD *)(a1 + 40) + 24LL;
  v5 = *(_QWORD *)v4;
  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 40) + 32LL) & 1) == 0 )
  {
LABEL_2:
    v6 = *(_BYTE *)(*(_QWORD *)(a1 + 40) + 32LL) & 1;
    if ( !v5 )
      goto LABEL_8;
    while ( 1 )
    {
      v7 = HampIpcChannelObjectCompareObjectsForTree(a1, v5);
      if ( v7 < 0 )
      {
        v8 = *(_QWORD *)v5;
        if ( v6 && v8 )
          goto LABEL_28;
      }
      else
      {
        if ( v7 <= 0 )
        {
          __int2c();
          goto LABEL_8;
        }
        v8 = *(_QWORD *)(v5 + 8);
        if ( v6 && v8 )
        {
LABEL_28:
          v5 ^= v8;
          goto LABEL_7;
        }
      }
      v5 = v8;
LABEL_7:
      if ( !v5 )
        goto LABEL_8;
    }
  }
  if ( v5 )
  {
    v5 ^= v4;
    goto LABEL_2;
  }
LABEL_8:
  v9 = *(_QWORD *)v4;
  if ( (*(_BYTE *)(v4 + 8) & 1) != 0 )
  {
    if ( !v9 )
    {
LABEL_24:
      LOBYTE(a3) = 0;
      return RtlRbInsertNodeEx(v4, v9, a3, a1);
    }
    v9 ^= v4;
  }
  LOBYTE(a3) = 0;
  v10 = *(_BYTE *)(v4 + 8) & 1;
  if ( v9 )
  {
    while ( 1 )
    {
      if ( (int)HampIpcChannelObjectCompareObjectsForTree(a1, v9) < 0 )
      {
        v11 = *(_QWORD *)v9;
        if ( v10 )
        {
          if ( !v11 )
            goto LABEL_24;
          v11 ^= v9;
        }
        if ( !v11 )
          goto LABEL_24;
      }
      else
      {
        v11 = *(_QWORD *)(v9 + 8);
        if ( v10 )
        {
          if ( !v11 )
          {
LABEL_18:
            LOBYTE(a3) = 1;
            return RtlRbInsertNodeEx(v4, v9, a3, a1);
          }
          v11 ^= v9;
        }
        if ( !v11 )
          goto LABEL_18;
      }
      v9 = v11;
    }
  }
  return RtlRbInsertNodeEx(v4, v9, a3, a1);
}

```

## disassembly

```asm
0x180009d40  push    rbx
0x180009d42  push    rsi
0x180009d43  push    rdi
0x180009d44  push    r14
0x180009d46  sub     rsp, 28h
0x180009d4a  mov     r14, [rcx+28h]
0x180009d4e  mov     rsi, rcx
0x180009d51  add     r14, 18h
0x180009d55  test    byte ptr [r14+8], 1
0x180009d5a  mov     rbx, [r14]
0x180009d5d  jnz     loc_180009E24
0x180009d63  movzx   edi, byte ptr [r14+8]
0x180009d68  and     edi, 1
0x180009d6b  test    rbx, rbx
0x180009d6e  jz      short loc_180009D95
0x180009d70  mov     rdx, rbx
0x180009d73  mov     rcx, rsi
0x180009d76  call    HampIpcChannelObjectCompareObjectsForTree
0x180009d7b  test    eax, eax
0x180009d7d  js      short loc_180009DD8
0x180009d7f  jle     short loc_180009DE6
0x180009d81  mov     rax, [rbx+8]
0x180009d85  test    edi, edi
0x180009d87  jnz     loc_180009E35
0x180009d8d  mov     rbx, rax
0x180009d90  test    rbx, rbx
0x180009d93  jnz     short loc_180009D70
0x180009d95  test    byte ptr [r14+8], 1
0x180009d9a  mov     rbx, [r14]
0x180009d9d  jnz     loc_180009E46
0x180009da3  movzx   edi, byte ptr [r14+8]
0x180009da8  xor     r8b, r8b
0x180009dab  and     edi, 1
0x180009dae  test    rbx, rbx
0x180009db1  jz      short loc_180009DF2
0x180009db3  mov     rdx, rbx
0x180009db6  mov     rcx, rsi
0x180009db9  call    HampIpcChannelObjectCompareObjectsForTree
0x180009dbe  test    eax, eax
0x180009dc0  js      short loc_180009E0B
0x180009dc2  mov     rax, [rbx+8]
0x180009dc6  test    edi, edi
0x180009dc8  jnz     loc_180009E55
0x180009dce  test    rax, rax
0x180009dd1  jz      short loc_180009DEF
0x180009dd3  mov     rbx, rax
0x180009dd6  jmp     short loc_180009DB3
0x180009dd8  mov     rax, [rbx]
0x180009ddb  test    edi, edi
0x180009ddd  jz      short loc_180009D8D
0x180009ddf  test    rax, rax
0x180009de2  jz      short loc_180009D8D
0x180009de4  jmp     short loc_180009E3E
0x180009de6  test    rbx, rbx
0x180009de9  jz      short loc_180009D95
0x180009deb  int     2Ch; Windows NT - assertion failure
0x180009ded  jmp     short loc_180009D95
0x180009def  mov     r8b, 1
0x180009df2  mov     r9, rsi
0x180009df5  mov     rdx, rbx
0x180009df8  mov     rcx, r14
0x180009dfb  add     rsp, 28h
0x180009dff  pop     r14
0x180009e01  pop     rdi
0x180009e02  pop     rsi
0x180009e03  pop     rbx
0x180009e04  jmp     cs:__imp_RtlRbInsertNodeEx
0x180009e0b  mov     rax, [rbx]
0x180009e0e  test    edi, edi
0x180009e10  jz      short loc_180009E1A
0x180009e12  test    rax, rax
0x180009e15  jz      short loc_180009E1F
0x180009e17  xor     rax, rbx
0x180009e1a  test    rax, rax
0x180009e1d  jnz     short loc_180009DD3
0x180009e1f  xor     r8b, r8b
0x180009e22  jmp     short loc_180009DF2
0x180009e24  test    rbx, rbx
0x180009e27  jz      loc_180009D95
0x180009e2d  xor     rbx, r14
0x180009e30  jmp     loc_180009D63
0x180009e35  test    rax, rax
0x180009e38  jz      loc_180009D8D
0x180009e3e  xor     rbx, rax
0x180009e41  jmp     loc_180009D90
0x180009e46  test    rbx, rbx
0x180009e49  jz      short loc_180009E53
0x180009e4b  xor     rbx, r14
0x180009e4e  jmp     loc_180009DA3
0x180009e53  jmp     short loc_180009E1F
0x180009e55  test    rax, rax
0x180009e58  jz      short loc_180009DEF
0x180009e5a  xor     rax, rbx
0x180009e5d  jmp     loc_180009DCE
```
