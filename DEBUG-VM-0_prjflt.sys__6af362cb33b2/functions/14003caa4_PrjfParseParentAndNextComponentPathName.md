# PrjfParseParentAndNextComponentPathName

- ea: `0x14003caa4`
- end: `0x14003cc0e`
- name: `PrjfParseParentAndNextComponentPathName`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140024184`

## callees

- `0x14000b1d0`
- `0x14003caa4`

## pseudocode

```c
__int64 __fastcall PrjfParseParentAndNextComponentPathName(
        unsigned __int16 *a1,
        unsigned __int16 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _BYTE *a6)
{
  unsigned __int16 v6; // r11
  unsigned int v7; // esi
  __int64 v8; // rdi
  unsigned __int64 v10; // rax
  unsigned __int16 v11; // bx
  __int64 v12; // rcx
  unsigned __int16 v13; // ax
  __int64 v14; // rbp
  unsigned __int16 v16; // bx
  _WORD *v17; // r13
  __int64 i; // rcx
  __int64 v19; // rbx
  unsigned __int16 v20; // ax
  unsigned __int64 v21; // rcx
  unsigned __int16 v22; // bx

  v6 = *a1;
  v7 = 0;
  v8 = *((_QWORD *)a1 + 1);
  v10 = (unsigned __int64)*a1 >> 1;
  v11 = *a1 - 2;
  *a6 = 0;
  if ( *(_WORD *)(v8 + 2 * v10 - 2) != 92 )
    v11 = v6;
  if ( a2 && a2 <= v11 )
  {
    v12 = a1[1];
    *(_WORD *)a3 = v11 - a2;
    if ( (unsigned __int16)v12 < a2 )
    {
      *(_WORD *)(a3 + 2) = -1;
      return (unsigned int)-1073741675;
    }
    else
    {
      LOWORD(v12) = v12 - a2;
      v13 = ((unsigned __int16)(v11 - a2) >> 1) + 1;
      *(_WORD *)(a3 + 2) = v12;
      v14 = v13;
      *(_QWORD *)(a3 + 8) = v8;
      if ( *(_WORD *)(v8 + 2LL * v13 - 2) != 92 )
        return 3221225485LL;
      v16 = v11 >> 1;
      v17 = (_WORD *)(v8 + 2LL * v13);
      if ( *v17 == 92 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v12);
      for ( i = (unsigned int)(v14 + 1); (unsigned __int16)i <= v16; LOWORD(i) = i + 1 )
      {
        if ( (_WORD)i == v16 )
        {
          *a6 = 1;
          break;
        }
        if ( *(_WORD *)(v8 + 2LL * (unsigned __int16)i) == 92 )
          break;
      }
      LOWORD(i) = i - 1;
      v19 = (unsigned __int16)i;
      if ( *(_WORD *)(v8 + 2LL * (unsigned __int16)i) == 92 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(i);
      if ( !*a6 && *(_WORD *)(v8 + 2 * v19 + 2) != 92 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(i);
      *(_QWORD *)(a4 + 8) = v8;
      v20 = 2 * (v19 + 1);
      *(_WORD *)a4 = v20;
      *(_WORD *)(a4 + 2) = v20;
      v21 = (unsigned __int64)v20 >> 1;
      if ( *(_WORD *)(v8 + 2 * v21 - 2) == 92 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v21);
      v22 = 2 * (v19 - v14 + 1);
      *(_WORD *)a5 = v22;
      *(_WORD *)(a5 + 2) = v22;
      *(_QWORD *)(a5 + 8) = v17;
      if ( *(_WORD *)(v8 + 2 * (v14 + ((unsigned __int64)v22 >> 1)) - 2) == 92 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(a5);
    }
  }
  else
  {
    return (unsigned int)-1073741766;
  }
  return v7;
}

```

## disassembly

```asm
0x14003caa4  push    rbx
0x14003caa6  push    rbp
0x14003caa7  push    rsi
0x14003caa8  push    rdi
0x14003caa9  push    r12
0x14003caab  push    r13
0x14003caad  push    r14
0x14003caaf  push    r15
0x14003cab1  sub     rsp, 28h
0x14003cab5  movzx   r11d, word ptr [rcx]
0x14003cab9  xor     esi, esi
0x14003cabb  mov     rdi, [rcx+8]
0x14003cabf  mov     eax, r11d
0x14003cac2  mov     r15, [rsp+68h+arg_28]
0x14003caca  mov     r12, r9
0x14003cacd  shr     rax, 1
0x14003cad0  lea     ebx, [r11-2]
0x14003cad4  mov     [r15], sil
0x14003cad7  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x14003cadd  cmovnz  bx, r11w
0x14003cae2  test    dx, dx
0x14003cae5  jz      loc_14003CBF5
0x14003caeb  cmp     dx, bx
0x14003caee  ja      loc_14003CBF5
0x14003caf4  movzx   ecx, word ptr [rcx+2]
0x14003caf8  movzx   eax, bx
0x14003cafb  sub     ax, dx
0x14003cafe  mov     [r8], ax
0x14003cb02  cmp     cx, dx
0x14003cb05  jb      loc_14003CBE7
0x14003cb0b  shr     ax, 1
0x14003cb0e  sub     cx, dx
0x14003cb11  inc     ax
0x14003cb14  mov     [r8+2], cx
0x14003cb19  movzx   ebp, ax
0x14003cb1c  mov     [r8+8], rdi
0x14003cb20  cmp     word ptr [rdi+rbp*2-2], 5Ch ; '\'
0x14003cb26  jz      short loc_14003CB32
0x14003cb28  mov     eax, 0C000000Dh
0x14003cb2d  jmp     loc_14003CBFC
0x14003cb32  shr     bx, 1
0x14003cb35  lea     r13, [rdi+rbp*2]
0x14003cb39  cmp     word ptr [r13+0], 5Ch ; '\'
0x14003cb3f  jnz     short loc_14003CB46
0x14003cb41  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003cb46  lea     ecx, [rbp+1]
0x14003cb49  jmp     short loc_14003CB5A
0x14003cb4b  jz      short loc_14003CB61
0x14003cb4d  movzx   eax, cx
0x14003cb50  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x14003cb55  jz      short loc_14003CB65
0x14003cb57  inc     cx
0x14003cb5a  cmp     cx, bx
0x14003cb5d  jbe     short loc_14003CB4B
0x14003cb5f  jmp     short loc_14003CB65
0x14003cb61  mov     byte ptr [r15], 1
0x14003cb65  dec     cx
0x14003cb68  movzx   ebx, cx
0x14003cb6b  cmp     word ptr [rdi+rbx*2], 5Ch ; '\'
0x14003cb70  jnz     short loc_14003CB77
0x14003cb72  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003cb77  cmp     byte ptr [r15], 0
0x14003cb7b  jnz     short loc_14003CB8A
0x14003cb7d  cmp     word ptr [rdi+rbx*2+2], 5Ch ; '\'
0x14003cb83  jz      short loc_14003CB8A
0x14003cb85  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003cb8a  lea     eax, [rbx+1]
0x14003cb8d  mov     [r12+8], rdi
0x14003cb92  add     ax, ax
0x14003cb95  movzx   ecx, ax
0x14003cb98  mov     [r12], cx
0x14003cb9d  mov     [r12+2], cx
0x14003cba3  shr     rcx, 1
0x14003cba6  cmp     word ptr [rdi+rcx*2-2], 5Ch ; '\'
0x14003cbac  jnz     short loc_14003CBB3
0x14003cbae  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003cbb3  mov     rcx, [rsp+68h+arg_20]
0x14003cbbb  sub     bx, bp
0x14003cbbe  inc     bx
0x14003cbc1  add     bx, bx
0x14003cbc4  movzx   eax, bx
0x14003cbc7  mov     [rcx], ax
0x14003cbca  mov     [rcx+2], ax
0x14003cbce  shr     rax, 1
0x14003cbd1  add     rax, rbp
0x14003cbd4  mov     [rcx+8], r13
0x14003cbd8  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x14003cbde  jnz     short loc_14003CBFA
0x14003cbe0  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003cbe5  jmp     short loc_14003CBFA
0x14003cbe7  mov     word ptr [r8+2], 0FFFFh
0x14003cbee  mov     esi, 0C0000095h
0x14003cbf3  jmp     short loc_14003CBFA
0x14003cbf5  mov     esi, 0C000003Ah
0x14003cbfa  mov     eax, esi
0x14003cbfc  add     rsp, 28h
0x14003cc00  pop     r15
0x14003cc02  pop     r14
0x14003cc04  pop     r13
0x14003cc06  pop     r12
0x14003cc08  pop     rdi
0x14003cc09  pop     rsi
0x14003cc0a  pop     rbp
0x14003cc0b  pop     rbx
0x14003cc0c  retn
```
