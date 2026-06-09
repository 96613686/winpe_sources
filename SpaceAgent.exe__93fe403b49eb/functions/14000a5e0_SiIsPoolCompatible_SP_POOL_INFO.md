# SiIsPoolCompatible(_SP_POOL_INFO *)

- ea: `0x14000a5e0`
- end: `0x14000a6f1`
- name: `?SiIsPoolCompatible@@YAHPEAU_SP_POOL_INFO@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct _SP_POOL_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140018750`

## callees

- `0x14000a5e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000a6e2`
- `KERNEL32!SetLastError` at `0x14000a6e2`

## pseudocode

```c
__int64 __fastcall SiIsPoolCompatible(struct _SP_POOL_INFO *a1)
{
  unsigned int v1; // r8d
  unsigned int v2; // edx
  __int64 i; // r9
  unsigned int j; // r9d
  __int64 k; // r9
  int v6; // eax

  v1 = *((_DWORD *)a1 + 647);
  v2 = 1;
  if ( v1 <= 1 )
  {
    if ( *((_QWORD *)a1 + 350) != -1 )
      goto LABEL_33;
    goto LABEL_5;
  }
  if ( v1 <= 2 )
  {
LABEL_5:
    for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)a1 + 6 * i + 681) == 3 && *((_DWORD *)a1 + 6 * i + 682) != 1 )
        goto LABEL_33;
    }
    goto LABEL_11;
  }
  if ( v1 <= 4 )
  {
LABEL_11:
    for ( j = 0; j < 3; ++j )
    {
      if ( *((_DWORD *)a1 + 6 * j + 684) != 1 )
        goto LABEL_33;
    }
LABEL_16:
    if ( *((_BYTE *)a1 + 2672) )
      goto LABEL_33;
    goto LABEL_19;
  }
  if ( v1 <= 5 )
    goto LABEL_16;
  if ( v1 > 0x12 )
  {
    if ( v1 > 0x15 )
      goto LABEL_31;
    goto LABEL_22;
  }
LABEL_19:
  if ( *((_DWORD *)a1 + 676) )
    goto LABEL_33;
LABEL_22:
  if ( *((_QWORD *)a1 + 335) != 0x10000000 )
  {
LABEL_33:
    SetLastError(0x32u);
    return 0;
  }
  for ( k = 0; (unsigned int)k < 3; k = (unsigned int)(k + 1) )
  {
    v6 = *((_DWORD *)a1 + 6 * k + 681);
    if ( v6 == 2 )
    {
      if ( *((_DWORD *)a1 + 6 * k + 683) == 4 )
        goto LABEL_33;
    }
    else if ( v6 == 3 && *((_DWORD *)a1 + 6 * k + 683) > 1u )
    {
      goto LABEL_33;
    }
  }
LABEL_31:
  if ( v1 <= 0x1B && *((_QWORD *)a1 + 351) )
    goto LABEL_33;
  return v2;
}

```

## disassembly

```asm
0x14000a5e0  sub     rsp, 28h
0x14000a5e4  mov     r8d, [rcx+0A1Ch]
0x14000a5eb  mov     edx, 1
0x14000a5f0  cmp     r8d, edx
0x14000a5f3  ja      short loc_14000A604
0x14000a5f5  cmp     qword ptr [rcx+0AF0h], 0FFFFFFFFFFFFFFFFh
0x14000a5fd  jz      short loc_14000A60A
0x14000a5ff  jmp     loc_14000A6DD
0x14000a604  cmp     r8d, 2
0x14000a608  ja      short loc_14000A635
0x14000a60a  xor     r9d, r9d
0x14000a60d  cmp     r9d, 3
0x14000a611  jnb     short loc_14000A63B
0x14000a613  lea     r10, [r9+r9*2]
0x14000a617  cmp     dword ptr [rcx+r10*8+0AA4h], 3
0x14000a620  jnz     short loc_14000A630
0x14000a622  cmp     [rcx+r10*8+0AA8h], edx
0x14000a62a  jnz     loc_14000A6DD
0x14000a630  add     r9d, edx
0x14000a633  jmp     short loc_14000A60D
0x14000a635  cmp     r8d, 4
0x14000a639  ja      short loc_14000A65D
0x14000a63b  xor     r9d, r9d
0x14000a63e  cmp     r9d, 3
0x14000a642  jnb     short loc_14000A663
0x14000a644  mov     eax, r9d
0x14000a647  add     rax, 72h ; 'r'
0x14000a64b  lea     rax, [rax+rax*2]
0x14000a64f  cmp     [rcx+rax*8], edx
0x14000a652  jnz     loc_14000A6DD
0x14000a658  add     r9d, edx
0x14000a65b  jmp     short loc_14000A63E
0x14000a65d  cmp     r8d, 5
0x14000a661  ja      short loc_14000A66E
0x14000a663  cmp     byte ptr [rcx+0A70h], 0
0x14000a66a  jz      short loc_14000A674
0x14000a66c  jmp     short loc_14000A6DD
0x14000a66e  cmp     r8d, 12h
0x14000a672  ja      short loc_14000A67F
0x14000a674  cmp     dword ptr [rcx+0A90h], 0
0x14000a67b  jz      short loc_14000A685
0x14000a67d  jmp     short loc_14000A6DD
0x14000a67f  cmp     r8d, 15h
0x14000a683  ja      short loc_14000A6CD
0x14000a685  cmp     qword ptr [rcx+0A78h], 10000000h
0x14000a690  jnz     short loc_14000A6DD
0x14000a692  xor     r9d, r9d
0x14000a695  cmp     r9d, 3
0x14000a699  jnb     short loc_14000A6CD
0x14000a69b  lea     r10, [r9+r9*2]
0x14000a69f  mov     eax, [rcx+r10*8+0AA4h]
0x14000a6a7  cmp     eax, 2
0x14000a6aa  jnz     short loc_14000A6B9
0x14000a6ac  cmp     dword ptr [rcx+r10*8+0AACh], 4
0x14000a6b5  jz      short loc_14000A6DD
0x14000a6b7  jmp     short loc_14000A6C8
0x14000a6b9  cmp     eax, 3
0x14000a6bc  jnz     short loc_14000A6C8
0x14000a6be  cmp     [rcx+r10*8+0AACh], edx
0x14000a6c6  ja      short loc_14000A6DD
0x14000a6c8  add     r9d, edx
0x14000a6cb  jmp     short loc_14000A695
0x14000a6cd  cmp     r8d, 1Bh
0x14000a6d1  ja      short loc_14000A6EA
0x14000a6d3  cmp     qword ptr [rcx+0AF8h], 0
0x14000a6db  jbe     short loc_14000A6EA
0x14000a6dd  mov     ecx, 32h ; '2'; dwErrCode
0x14000a6e2  call    cs:__imp_SetLastError
0x14000a6e8  xor     edx, edx
0x14000a6ea  mov     eax, edx
0x14000a6ec  add     rsp, 28h
0x14000a6f0  retn
```
