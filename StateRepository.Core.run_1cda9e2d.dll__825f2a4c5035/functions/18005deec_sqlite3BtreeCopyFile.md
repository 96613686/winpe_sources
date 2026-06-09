# sqlite3BtreeCopyFile

- ea: `0x18005deec`
- end: `0x18005dffa`
- name: `sqlite3BtreeCopyFile`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180087060`

## callees

- `0x180023b30`
- `0x180024440`
- `0x18005deec`
- `0x18006910e`
- `0x180085c14`
- `0x18008bd60`
- `0x18008c010`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall sqlite3BtreeCopyFile(__int64 a1, _QWORD *a2)
{
  __int64 *v4; // rcx
  __int64 v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // esi
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v10; // [rsp+28h] [rbp-50h]
  int v11; // [rsp+38h] [rbp-40h]
  __int64 v12; // [rsp+40h] [rbp-38h]
  _QWORD *v13; // [rsp+48h] [rbp-30h]
  unsigned __int64 v14; // [rsp+80h] [rbp+8h] BYREF

  memset_0(v9, 0, 0x48u);
  sqlite3BtreeEnter(a1);
  sqlite3BtreeEnter(a2);
  v4 = *(__int64 **)(**(_QWORD **)(a1 + 8) + 72LL);
  v5 = *v4;
  if ( !*v4 )
    goto LABEL_5;
  v14 = *(int *)(a2[1] + 52LL) * (unsigned __int64)*(unsigned int *)(a2[1] + 64LL);
  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned __int64 *))(v5 + 80))(v4, 11, &v14);
  v7 = 0;
  if ( v6 != 12 )
    v7 = v6;
  if ( !v7 )
  {
LABEL_5:
    memset_0(v9, 0, 0x48u);
    v12 = *a2;
    v13 = a2;
    v10 = a1;
    v11 = 1;
    sqlite3_backup_step(v9, 0x7FFFFFFF);
    v7 = sqlite3_backup_finish(v9);
    if ( v7 )
      sqlite3PagerClearCache(**(_QWORD **)(v10 + 8));
    else
      *(_WORD *)(*(_QWORD *)(a1 + 8) + 40LL) &= ~2u;
  }
  sqlite3BtreeLeave(a2);
  sqlite3BtreeLeave(a1);
  return v7;
}

```

## disassembly

```asm
0x18005deec  mov     [rsp+arg_8], rbx
0x18005def1  mov     [rsp+arg_10], rsi
0x18005def6  push    rdi
0x18005def7  sub     rsp, 70h
0x18005defb  mov     rdi, rdx
0x18005defe  mov     rbx, rcx
0x18005df01  xor     edx, edx; Val
0x18005df03  lea     rcx, [rsp+78h+var_58]; void *
0x18005df08  lea     r8d, [rdx+48h]; Size
0x18005df0c  call    memset_0
0x18005df11  mov     rcx, rbx
0x18005df14  call    sqlite3BtreeEnter
0x18005df19  mov     rcx, rdi
0x18005df1c  call    sqlite3BtreeEnter
0x18005df21  mov     rax, [rbx+8]
0x18005df25  mov     r8, [rax]
0x18005df28  mov     rcx, [r8+48h]
0x18005df2c  mov     r9, [rcx]
0x18005df2f  test    r9, r9
0x18005df32  jz      short loc_18005DF6D
0x18005df34  mov     rax, [rdi+8]
0x18005df38  lea     r8, [rsp+78h+arg_0]
0x18005df40  mov     edx, [rax+40h]
0x18005df43  movsxd  rax, dword ptr [rax+34h]
0x18005df47  imul    rdx, rax
0x18005df4b  mov     [rsp+78h+arg_0], rdx
0x18005df53  mov     edx, 0Bh
0x18005df58  mov     rax, [r9+50h]
0x18005df5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005df61  xor     esi, esi
0x18005df63  cmp     eax, 0Ch
0x18005df66  cmovnz  esi, eax
0x18005df69  test    esi, esi
0x18005df6b  jnz     short loc_18005DFD6
0x18005df6d  xor     edx, edx; Val
0x18005df6f  lea     rcx, [rsp+78h+var_58]; void *
0x18005df74  lea     r8d, [rdx+48h]; Size
0x18005df78  call    memset_0
0x18005df7d  mov     rax, [rdi]
0x18005df80  lea     rcx, [rsp+78h+var_58]
0x18005df85  mov     edx, 7FFFFFFFh
0x18005df8a  mov     [rsp+78h+var_38], rax
0x18005df8f  mov     [rsp+78h+var_30], rdi
0x18005df94  mov     [rsp+78h+var_50], rbx
0x18005df99  mov     [rsp+78h+var_40], 1
0x18005dfa1  call    sqlite3_backup_step
0x18005dfa6  lea     rcx, [rsp+78h+var_58]
0x18005dfab  call    sqlite3_backup_finish
0x18005dfb0  mov     esi, eax
0x18005dfb2  test    eax, eax
0x18005dfb4  jnz     short loc_18005DFC5
0x18005dfb6  mov     rcx, [rbx+8]
0x18005dfba  mov     eax, 0FFFDh
0x18005dfbf  and     [rcx+28h], ax
0x18005dfc3  jmp     short loc_18005DFD6
0x18005dfc5  mov     rax, [rsp+78h+var_50]
0x18005dfca  mov     rcx, [rax+8]
0x18005dfce  mov     rcx, [rcx]
0x18005dfd1  call    sqlite3PagerClearCache
0x18005dfd6  mov     rcx, rdi
0x18005dfd9  call    sqlite3BtreeLeave
0x18005dfde  mov     rcx, rbx
0x18005dfe1  call    sqlite3BtreeLeave
0x18005dfe6  lea     r11, [rsp+78h+var_8]
0x18005dfeb  mov     eax, esi
0x18005dfed  mov     rbx, [r11+18h]
0x18005dff1  mov     rsi, [r11+20h]
0x18005dff5  mov     rsp, r11
0x18005dff8  pop     rdi
0x18005dff9  retn
```
