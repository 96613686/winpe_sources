# CommonUtil::UtilGetFilenameFromPath<ushort>(ushort const *,ushort const * *,unsigned __int64 *)

- ea: `0x180009110`
- end: `0x180009329`
- name: `??$UtilGetFilenameFromPath@G@CommonUtil@@YAJPEBGPEAPEBGPEA_K@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800071ac`

## callees

- `0x180009110`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFilenameFromPath<unsigned short>(_WORD *a1, _QWORD *a2)
{
  bool v3; // zf
  char v5; // bl
  __int64 v6; // r9
  __int16 v7; // ax
  __int16 v8; // cx
  unsigned __int64 v9; // r11
  __int64 v10; // rdx
  unsigned __int64 v11; // r10
  unsigned __int64 v12; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx

  v3 = *a1 == 47;
  *a2 = 0;
  v5 = 0;
  v6 = 0;
  if ( !v3 && *a1 != 92 || a1[1] != 47 && a1[1] != 92 )
    goto LABEL_28;
  v7 = a1[2];
  if ( v7 == 46 )
  {
    if ( a1[3] == 47 || a1[3] == 92 )
    {
      v6 = 4;
      goto LABEL_28;
    }
    goto LABEL_26;
  }
  if ( v7 != 63 )
  {
    if ( v7 == 47 || v7 == 92 )
      goto LABEL_28;
LABEL_26:
    v6 = 2;
LABEL_27:
    v5 = 1;
    goto LABEL_28;
  }
  if ( a1[3] != 47 && a1[3] != 92 )
    goto LABEL_26;
  v8 = a1[4];
  if ( ((v8 - 85) & 0xFFDF) == 0 && ((a1[5] - 78) & 0xFFDF) == 0 && ((a1[6] - 67) & 0xFFDF) == 0 )
  {
    if ( a1[7] != 47 && a1[7] != 92 )
      return 2147942402LL;
    v6 = 8;
    goto LABEL_27;
  }
  if ( (unsigned __int16)(v8 - 97) > 0x19u && (unsigned __int16)(v8 - 65) > 0x19u )
    return 2147942402LL;
  if ( a1[5] != 58 )
    return 2147942402LL;
  v6 = 4;
  if ( a1[6] != 47 && a1[6] != 92 )
    return 2147942402LL;
LABEL_28:
  v9 = 0;
  v10 = v6;
  v11 = v6;
  v12 = v6;
  if ( !a1[v6] )
    goto LABEL_41;
  while ( 1 )
  {
    if ( a1[v11] == 47 || a1[v11] == 92 )
    {
      while ( 1 )
      {
        v10 = v12 + 1;
        if ( a1[v12 + 1] != 47 && a1[v10] != 92 )
          break;
        ++v12;
      }
      goto LABEL_39;
    }
    if ( a1[v11] == 58 )
      break;
LABEL_40:
    v11 = v12 + 1;
    v12 = v11;
    if ( !a1[v11] )
      goto LABEL_41;
  }
  if ( v12 - v6 == 1 )
  {
    while ( 1 )
    {
      v10 = v12 + 1;
      if ( a1[v12 + 1] != 47 && a1[v10] != 92 )
        break;
      ++v12;
    }
LABEL_39:
    ++v9;
    goto LABEL_40;
  }
  if ( a1[v11 + 1] == 47 && a1[v11 + 2] == 47 )
    return 2147500033LL;
LABEL_41:
  if ( v12 > 0x104 && !v6 )
    return 2147942561LL;
  if ( v5 && v9 < 2 )
    return 2147942402LL;
  v14 = v12 - v10;
  if ( v14 > 2 )
    goto LABEL_55;
  v15 = v14 - 1;
  if ( !v15 )
    goto LABEL_53;
  if ( v15 != 1 )
    return 2147942402LL;
  if ( a1[v10 + 1] == 46 )
  {
LABEL_53:
    if ( a1[v10] == 46 )
      return 2147942402LL;
  }
LABEL_55:
  v3 = a1[v11] == 0;
  *a2 = &a1[v10];
  return !v3;
}

```

## disassembly

```asm
0x180009110  mov     [rsp+arg_0], rbx
0x180009115  mov     [rsp+arg_10], r8
0x18000911a  push    rdi
0x18000911b  push    r14
0x18000911d  xor     r14d, r14d
0x180009120  mov     rdi, rdx
0x180009123  cmp     word ptr [rcx], 2Fh ; '/'
0x180009127  mov     r8, rcx
0x18000912a  mov     [rdx], r14
0x18000912d  mov     bl, r14b
0x180009130  mov     r9d, r14d
0x180009133  jz      short loc_18000913F
0x180009135  cmp     word ptr [rcx], 5Ch ; '\'
0x180009139  jnz     loc_18000922F
0x18000913f  cmp     word ptr [rcx+2], 2Fh ; '/'
0x180009144  jz      short loc_180009151
0x180009146  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000914b  jnz     loc_18000922F
0x180009151  movzx   eax, word ptr [rcx+4]
0x180009155  cmp     ax, 2Eh ; '.'
0x180009159  jnz     short loc_180009178
0x18000915b  cmp     word ptr [rcx+6], 2Fh ; '/'
0x180009160  jz      short loc_18000916D
0x180009162  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180009167  jnz     loc_180009227
0x18000916d  mov     r9d, 4
0x180009173  jmp     loc_18000922F
0x180009178  cmp     ax, 3Fh ; '?'
0x18000917c  jnz     loc_18000921B
0x180009182  cmp     word ptr [rcx+6], 2Fh ; '/'
0x180009187  jz      short loc_180009194
0x180009189  cmp     word ptr [rcx+6], 5Ch ; '\'
0x18000918e  jnz     loc_180009227
0x180009194  movzx   ecx, word ptr [rcx+8]
0x180009198  mov     edx, 0FFDFh
0x18000919d  lea     eax, [rcx-55h]
0x1800091a0  test    dx, ax
0x1800091a3  jnz     short loc_1800091DD
0x1800091a5  movzx   eax, word ptr [r8+0Ah]
0x1800091aa  sub     ax, 4Eh ; 'N'
0x1800091ae  test    dx, ax
0x1800091b1  jnz     short loc_1800091DD
0x1800091b3  movzx   eax, word ptr [r8+0Ch]
0x1800091b8  sub     ax, 43h ; 'C'
0x1800091bc  test    dx, ax
0x1800091bf  jnz     short loc_1800091DD
0x1800091c1  cmp     word ptr [r8+0Eh], 2Fh ; '/'
0x1800091c7  jz      short loc_1800091D5
0x1800091c9  cmp     word ptr [r8+0Eh], 5Ch ; '\'
0x1800091cf  jnz     loc_180009307
0x1800091d5  mov     r9d, 8
0x1800091db  jmp     short loc_18000922D
0x1800091dd  lea     eax, [rcx-61h]
0x1800091e0  cmp     ax, 19h
0x1800091e4  jbe     short loc_1800091F4
0x1800091e6  sub     cx, 41h ; 'A'
0x1800091ea  cmp     cx, 19h
0x1800091ee  ja      loc_180009307
0x1800091f4  cmp     word ptr [r8+0Ah], 3Ah ; ':'
0x1800091fa  jnz     loc_180009307
0x180009200  cmp     word ptr [r8+0Ch], 2Fh ; '/'
0x180009206  mov     r9d, 4
0x18000920c  jz      short loc_18000922F
0x18000920e  cmp     word ptr [r8+0Ch], 5Ch ; '\'
0x180009214  jz      short loc_18000922F
0x180009216  jmp     loc_180009307
0x18000921b  cmp     ax, 2Fh ; '/'
0x18000921f  jz      short loc_18000922F
0x180009221  cmp     ax, 5Ch ; '\'
0x180009225  jz      short loc_18000922F
0x180009227  mov     r9d, 2
0x18000922d  mov     bl, 1
0x18000922f  mov     r11, r14
0x180009232  mov     rdx, r9
0x180009235  mov     r10, r9
0x180009238  mov     rcx, r9
0x18000923b  cmp     [r8+r9*2], r14w
0x180009240  jz      short loc_1800092A9
0x180009242  cmp     word ptr [r8+r10*2], 2Fh ; '/'
0x180009248  jz      short loc_18000927F
0x18000924a  cmp     word ptr [r8+r10*2], 5Ch ; '\'
0x180009250  jz      short loc_18000927F
0x180009252  cmp     word ptr [r8+r10*2], 3Ah ; ':'
0x180009258  jnz     short loc_18000929B
0x18000925a  mov     rax, rcx
0x18000925d  sub     rax, r9
0x180009260  cmp     rax, 1
0x180009264  jnz     short loc_1800092BE
0x180009266  lea     rdx, [rcx+1]
0x18000926a  cmp     word ptr [r8+rdx*2], 2Fh ; '/'
0x180009270  jz      short loc_18000927A
0x180009272  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x180009278  jnz     short loc_180009298
0x18000927a  mov     rcx, rdx
0x18000927d  jmp     short loc_180009266
0x18000927f  lea     rdx, [rcx+1]
0x180009283  cmp     word ptr [r8+rdx*2], 2Fh ; '/'
0x180009289  jz      short loc_180009293
0x18000928b  cmp     word ptr [r8+rdx*2], 5Ch ; '\'
0x180009291  jnz     short loc_180009298
0x180009293  mov     rcx, rdx
0x180009296  jmp     short loc_18000927F
0x180009298  inc     r11
0x18000929b  lea     r10, [rcx+1]
0x18000929f  mov     rcx, r10
0x1800092a2  cmp     [r8+r10*2], r14w
0x1800092a7  jnz     short loc_180009242
0x1800092a9  cmp     rcx, 104h
0x1800092b0  jbe     short loc_1800092D7
0x1800092b2  test    r9, r9
0x1800092b5  jnz     short loc_1800092D7
0x1800092b7  mov     eax, 800700A1h
0x1800092bc  jmp     short loc_180009320
0x1800092be  cmp     word ptr [r8+r10*2+2], 2Fh ; '/'
0x1800092c5  jnz     short loc_1800092A9
0x1800092c7  cmp     word ptr [r8+r10*2+4], 2Fh ; '/'
0x1800092ce  jnz     short loc_1800092A9
0x1800092d0  mov     eax, 80004001h
0x1800092d5  jmp     short loc_180009320
0x1800092d7  test    bl, bl
0x1800092d9  jz      short loc_1800092E1
0x1800092db  cmp     r11, 2
0x1800092df  jb      short loc_180009307
0x1800092e1  sub     rcx, rdx
0x1800092e4  cmp     rcx, 2
0x1800092e8  ja      short loc_18000930E
0x1800092ea  sub     rcx, 1
0x1800092ee  jz      short loc_1800092FF
0x1800092f0  cmp     rcx, 1
0x1800092f4  jnz     short loc_180009307
0x1800092f6  cmp     word ptr [r8+rdx*2+2], 2Eh ; '.'
0x1800092fd  jnz     short loc_18000930E
0x1800092ff  cmp     word ptr [r8+rdx*2], 2Eh ; '.'
0x180009305  jnz     short loc_18000930E
0x180009307  mov     eax, 80070002h
0x18000930c  jmp     short loc_180009320
0x18000930e  cmp     r14w, [r8+r10*2]
0x180009313  lea     rax, [r8+rdx*2]
0x180009317  mov     [rdi], rax
0x18000931a  mov     eax, r14d
0x18000931d  setnz   al
0x180009320  mov     rbx, [rsp+10h+arg_0]
0x180009325  pop     r14
0x180009327  pop     rdi
0x180009328  retn
```
