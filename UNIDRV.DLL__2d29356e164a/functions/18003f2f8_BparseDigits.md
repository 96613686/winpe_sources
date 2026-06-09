# BparseDigits

- ea: `0x18003f2f8`
- end: `0x18003f453`
- name: `BparseDigits`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c818`

## callees

- `0x180007220`
- `0x18003f2f8`

## string_xrefs

- `0x18003f434`: `Command parameter: syntax error in value construct.`
- `0x18003f349`: `Command Param-BparseDigits: no digits found in Hex value.`

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
        WriteDbgTraceErrorGpd("BparseDigits", "Command Param-BparseDigits: no digits found in Hex value.", v7, 0);
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
        WriteDbgTraceErrorGpd("BparseDigits", "Command parameter: syntax error in value construct.", v7, v4);
        WriteDbgTraceErrorGpd("BparseDigits", "  integer not clearly delimited using non Keyword characters.", v17, v18);
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
0x18003f2f8  mov     [rsp+arg_0], rbx
0x18003f2fd  push    rdi
0x18003f2fe  sub     rsp, 20h
0x18003f302  mov     r11, [rcx]
0x18003f305  lea     r10, [rcx+8]
0x18003f309  xor     r9d, r9d
0x18003f30c  xor     ebx, ebx
0x18003f30e  mov     rdi, rcx
0x18003f311  cmp     byte ptr [r11], 30h ; '0'
0x18003f315  jnz     loc_18003F3BE
0x18003f31b  lea     r8, [r11+1]
0x18003f31f  mov     [rcx], r8
0x18003f322  mov     ecx, [r10]
0x18003f325  sub     ecx, 1
0x18003f328  mov     [r10], ecx
0x18003f32b  jz      loc_18003F3B7
0x18003f331  mov     al, [r8]
0x18003f334  sub     al, 58h ; 'X'
0x18003f336  test    al, 0DFh
0x18003f338  jnz     short loc_18003F3B7
0x18003f33a  lea     r8, [r11+2]
0x18003f33e  sub     ecx, 1
0x18003f341  mov     [rdi], r8
0x18003f344  mov     [r10], ecx
0x18003f347  jnz     short loc_18003F363
0x18003f349  lea     rdx, aCommandParamBp; "Command Param-BparseDigits: no digits f"...
0x18003f350  lea     rcx, aBparsedigits; "BparseDigits"
0x18003f357  call    WriteDbgTraceErrorGpd
0x18003f35c  xor     eax, eax
0x18003f35e  jmp     loc_18003F40C
0x18003f363  test    ecx, ecx
0x18003f365  jz      short loc_18003F3C1
0x18003f367  mov     al, [r8]
0x18003f36a  sub     al, 30h ; '0'
0x18003f36c  cmp     al, 9
0x18003f36e  ja      short loc_18003F37A
0x18003f370  shl     r9d, 4
0x18003f374  add     r9d, 0FFFFFFD0h
0x18003f378  jmp     short loc_18003F39E
0x18003f37a  mov     al, [r8]
0x18003f37d  sub     al, 61h ; 'a'
0x18003f37f  cmp     al, 5
0x18003f381  ja      short loc_18003F38D
0x18003f383  shl     r9d, 4
0x18003f387  add     r9d, 0FFFFFFA9h
0x18003f38b  jmp     short loc_18003F39E
0x18003f38d  mov     al, [r8]
0x18003f390  sub     al, 41h ; 'A'
0x18003f392  cmp     al, 5
0x18003f394  ja      short loc_18003F3C1
0x18003f396  shl     r9d, 4
0x18003f39a  add     r9d, 0FFFFFFC9h
0x18003f39e  movzx   eax, byte ptr [r8]
0x18003f3a2  mov     ebx, 1
0x18003f3a7  add     r9d, eax
0x18003f3aa  inc     r8
0x18003f3ad  dec     ecx
0x18003f3af  mov     [rdi], r8
0x18003f3b2  mov     [r10], ecx
0x18003f3b5  jmp     short loc_18003F363
0x18003f3b7  mov     ebx, 1
0x18003f3bc  jmp     short loc_18003F3C1
0x18003f3be  mov     r8, r11
0x18003f3c1  mov     eax, [r10]
0x18003f3c4  test    eax, eax
0x18003f3c6  jz      short loc_18003F400
0x18003f3c8  mov     r11d, eax
0x18003f3cb  cmp     byte ptr [r8], 30h ; '0'
0x18003f3cf  jb      short loc_18003F41B
0x18003f3d1  cmp     byte ptr [r8], 39h ; '9'
0x18003f3d5  ja      short loc_18003F417
0x18003f3d7  movzx   eax, byte ptr [r8]
0x18003f3db  lea     r9d, [r9+r9*4]
0x18003f3df  inc     r8
0x18003f3e2  lea     r9d, [r9-18h]
0x18003f3e6  mov     [rdi], r8
0x18003f3e9  mov     ebx, 1
0x18003f3ee  lea     r9d, [rax+r9*2]
0x18003f3f2  lea     eax, [r11-1]
0x18003f3f6  mov     [r10], eax
0x18003f3f9  mov     r11d, eax
0x18003f3fc  test    eax, eax
0x18003f3fe  jnz     short loc_18003F3CB
0x18003f400  mov     dword ptr [rdx+4], 0
0x18003f407  mov     eax, ebx
0x18003f409  mov     [rdx], r9d
0x18003f40c  mov     rbx, [rsp+28h+arg_0]
0x18003f411  add     rsp, 20h
0x18003f415  pop     rdi
0x18003f416  retn
0x18003f417  test    eax, eax
0x18003f419  jz      short loc_18003F400
0x18003f41b  mov     al, [r8]
0x18003f41e  sub     al, 3Fh ; '?'
0x18003f420  cmp     al, 3Bh ; ';'
0x18003f422  ja      short loc_18003F400
0x18003f424  mov     rcx, 0FFFFFFD0FFFFFFDh
0x18003f42e  bt      rcx, rax
0x18003f432  jnb     short loc_18003F400
0x18003f434  lea     rdx, aCommandParamet_9; "Command parameter: syntax error in valu"...
0x18003f43b  lea     rcx, aBparsedigits; "BparseDigits"
0x18003f442  call    WriteDbgTraceErrorGpd
0x18003f447  lea     rdx, aIntegerNotClea; "  integer not clearly delimited using n"...
0x18003f44e  jmp     loc_18003F350
```
