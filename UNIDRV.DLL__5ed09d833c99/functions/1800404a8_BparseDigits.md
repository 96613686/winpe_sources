# BparseDigits

- ea: `0x1800404a8`
- end: `0x180040604`
- name: `BparseDigits`
- size: `348`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c814`

## callees

- `0x180007150`
- `0x1800404a8`

## string_xrefs

- `0x1800405e5`: `Command parameter: syntax error in value construct.`
- `0x1800404f9`: `Command Param-BparseDigits: no digits found in Hex value.`

## pseudocode

```c
__int64 __fastcall BparseDigits(_QWORD *a1, _DWORD *a2)
{
  _BYTE *v2; // r11
  int *v3; // r10
  __int64 v4; // r9
  unsigned int v5; // ebx
  _BYTE *v7; // r8
  bool v8; // zf
  int v9; // ecx
  int v10; // ecx
  __int64 result; // rax
  int v12; // r9d
  unsigned __int64 v13; // rax
  int v14; // r11d
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9

  v2 = (_BYTE *)*a1;
  v3 = (int *)(a1 + 1);
  v4 = 0;
  v5 = 0;
  if ( *(_BYTE *)*a1 == 48 )
  {
    v7 = v2 + 1;
    *a1 = v2 + 1;
    v8 = *v3 == 1;
    v9 = *v3 - 1;
    *v3 = v9;
    if ( v8 || ((*v7 - 88) & 0xDF) != 0 )
    {
      v5 = 1;
    }
    else
    {
      v7 = v2 + 2;
      v10 = v9 - 1;
      *a1 = v2 + 2;
      *v3 = v10;
      if ( !v10 )
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BparseDigits",
          "Command Param-BparseDigits: no digits found in Hex value.",
          v7,
          0);
        return 0;
      }
      while ( v10 )
      {
        if ( (unsigned __int8)(*v7 - 48) > 9u )
        {
          if ( (unsigned __int8)(*v7 - 97) > 5u )
          {
            if ( (unsigned __int8)(*v7 - 65) > 5u )
              break;
            v12 = 16 * v4 - 55;
          }
          else
          {
            v12 = 16 * v4 - 87;
          }
        }
        else
        {
          v12 = 16 * v4 - 48;
        }
        v5 = 1;
        v4 = (unsigned int)(unsigned __int8)*v7++ + v12;
        --v10;
        *a1 = v7;
        *v3 = v10;
      }
    }
  }
  else
  {
    v7 = (_BYTE *)*a1;
  }
  v13 = (unsigned int)*v3;
  if ( (_DWORD)v13 )
  {
    v14 = *v3;
    while ( *v7 >= 0x30u && *v7 <= 0x39u )
    {
      v15 = (unsigned __int8)*v7++;
      *a1 = v7;
      v5 = 1;
      v4 = (unsigned int)(v15 + 2 * (5 * v4 - 24));
      v13 = (unsigned int)(v14 - 1);
      *v3 = v13;
      --v14;
      if ( !(_DWORD)v13 )
        goto LABEL_22;
    }
    LOBYTE(v13) = *v7 - 63;
    if ( (unsigned __int8)v13 <= 0x3Bu )
    {
      v16 = 0xFFFFFFD0FFFFFFDLL;
      if ( _bittest64(&v16, v13) )
      {
        WriteDbgTraceErrorGpd((__int64)"BparseDigits", "Command parameter: syntax error in value construct.", v7, v4);
        WriteDbgTraceErrorGpd(
          (__int64)"BparseDigits",
          "  integer not clearly delimited using non Keyword characters.",
          v17,
          v18);
        return 0;
      }
    }
  }
LABEL_22:
  a2[1] = 0;
  result = v5;
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x1800404a8  mov     [rsp+arg_0], rbx
0x1800404ad  push    rdi
0x1800404ae  sub     rsp, 20h
0x1800404b2  mov     r11, [rcx]
0x1800404b5  lea     r10, [rcx+8]
0x1800404b9  xor     r9d, r9d
0x1800404bc  xor     ebx, ebx
0x1800404be  mov     rdi, rcx
0x1800404c1  cmp     byte ptr [r11], 30h ; '0'
0x1800404c5  jnz     loc_18004056E
0x1800404cb  lea     r8, [r11+1]
0x1800404cf  mov     [rcx], r8
0x1800404d2  mov     ecx, [r10]
0x1800404d5  sub     ecx, 1
0x1800404d8  mov     [r10], ecx
0x1800404db  jz      loc_180040567
0x1800404e1  mov     al, [r8]
0x1800404e4  sub     al, 58h ; 'X'
0x1800404e6  test    al, 0DFh
0x1800404e8  jnz     short loc_180040567
0x1800404ea  lea     r8, [r11+2]
0x1800404ee  sub     ecx, 1
0x1800404f1  mov     [rdi], r8
0x1800404f4  mov     [r10], ecx
0x1800404f7  jnz     short loc_180040513
0x1800404f9  lea     rdx, aCommandParamBp; "Command Param-BparseDigits: no digits f"...
0x180040500  lea     rcx, aBparsedigits; "BparseDigits"
0x180040507  call    WriteDbgTraceErrorGpd
0x18004050c  xor     eax, eax
0x18004050e  jmp     loc_1800405BC
0x180040513  test    ecx, ecx
0x180040515  jz      short loc_180040571
0x180040517  mov     al, [r8]
0x18004051a  sub     al, 30h ; '0'
0x18004051c  cmp     al, 9
0x18004051e  ja      short loc_18004052A
0x180040520  shl     r9d, 4
0x180040524  add     r9d, 0FFFFFFD0h
0x180040528  jmp     short loc_18004054E
0x18004052a  mov     al, [r8]
0x18004052d  sub     al, 61h ; 'a'
0x18004052f  cmp     al, 5
0x180040531  ja      short loc_18004053D
0x180040533  shl     r9d, 4
0x180040537  add     r9d, 0FFFFFFA9h
0x18004053b  jmp     short loc_18004054E
0x18004053d  mov     al, [r8]
0x180040540  sub     al, 41h ; 'A'
0x180040542  cmp     al, 5
0x180040544  ja      short loc_180040571
0x180040546  shl     r9d, 4
0x18004054a  add     r9d, 0FFFFFFC9h
0x18004054e  movzx   eax, byte ptr [r8]
0x180040552  mov     ebx, 1
0x180040557  add     r9d, eax
0x18004055a  inc     r8
0x18004055d  dec     ecx
0x18004055f  mov     [rdi], r8
0x180040562  mov     [r10], ecx
0x180040565  jmp     short loc_180040513
0x180040567  mov     ebx, 1
0x18004056c  jmp     short loc_180040571
0x18004056e  mov     r8, r11
0x180040571  mov     eax, [r10]
0x180040574  test    eax, eax
0x180040576  jz      short loc_1800405B0
0x180040578  mov     r11d, eax
0x18004057b  cmp     byte ptr [r8], 30h ; '0'
0x18004057f  jb      short loc_1800405CC
0x180040581  cmp     byte ptr [r8], 39h ; '9'
0x180040585  ja      short loc_1800405C8
0x180040587  movzx   eax, byte ptr [r8]
0x18004058b  lea     r9d, [r9+r9*4]
0x18004058f  inc     r8
0x180040592  lea     r9d, [r9-18h]
0x180040596  mov     [rdi], r8
0x180040599  mov     ebx, 1
0x18004059e  lea     r9d, [rax+r9*2]
0x1800405a2  lea     eax, [r11-1]
0x1800405a6  mov     [r10], eax
0x1800405a9  mov     r11d, eax
0x1800405ac  test    eax, eax
0x1800405ae  jnz     short loc_18004057B
0x1800405b0  mov     dword ptr [rdx+4], 0
0x1800405b7  mov     eax, ebx
0x1800405b9  mov     [rdx], r9d
0x1800405bc  mov     rbx, [rsp+28h+arg_0]
0x1800405c1  add     rsp, 20h
0x1800405c5  pop     rdi
0x1800405c6  retn
0x1800405c8  test    eax, eax
0x1800405ca  jz      short loc_1800405B0
0x1800405cc  mov     al, [r8]
0x1800405cf  sub     al, 3Fh ; '?'
0x1800405d1  cmp     al, 3Bh ; ';'
0x1800405d3  ja      short loc_1800405B0
0x1800405d5  mov     rcx, 0FFFFFFD0FFFFFFDh
0x1800405df  bt      rcx, rax
0x1800405e3  jnb     short loc_1800405B0
0x1800405e5  lea     rdx, aCommandParamet_9; "Command parameter: syntax error in valu"...
0x1800405ec  lea     rcx, aBparsedigits; "BparseDigits"
0x1800405f3  call    WriteDbgTraceErrorGpd
0x1800405f8  lea     rdx, aIntegerNotClea; "  integer not clearly delimited using n"...
0x1800405ff  jmp     loc_180040500
```
