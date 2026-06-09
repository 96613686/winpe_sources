# TieringJetDatabase::GetBackupDirectoryName(int,ushort *)

- ea: `0x1400367c0`
- end: `0x140036956`
- name: `?GetBackupDirectoryName@TieringJetDatabase@@QEAAJHPEAG@Z`
- size: `406`
- prototype: `__int64 __fastcall(TieringJetDatabase *this, __int16, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140036390`
- `0x14003695c`

## callees

- `0x14000b7f8`
- `0x1400367c0`

## pseudocode

```c
__int64 __fastcall TieringJetDatabase::GetBackupDirectoryName(
        TieringJetDatabase *this,
        __int16 a2,
        unsigned __int16 *a3)
{
  __int64 v3; // rdi
  unsigned __int16 *v7; // r10
  __int64 v8; // r9
  _WORD *v9; // rax
  __int64 v10; // r8
  unsigned int v11; // ebx
  unsigned __int64 v12; // rdx
  _QWORD *v13; // rcx
  int v14; // edx
  __int64 v15; // rax
  unsigned __int16 *v16; // r8
  unsigned __int16 *v17; // rcx
  __int64 v18; // r9
  unsigned __int64 v19; // rdx
  __int64 result; // rax

  v3 = *(_QWORD *)this;
  v7 = *(unsigned __int16 **)(*(_QWORD *)this + 600LL);
  if ( !v7 )
  {
    v11 = -2147024809;
LABEL_24:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v11;
    }
    v14 = 31;
LABEL_28:
    LODWORD(v18) = v3 + 592;
    goto LABEL_29;
  }
  v8 = 260;
  v9 = *(_WORD **)(*(_QWORD *)this + 600LL);
  v10 = 260;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v11 = v10 == 0 ? 0x80070057 : 0;
  if ( !v10 )
    goto LABEL_24;
  v12 = (2 * (260 - v10)) & -(__int64)(v10 != 0);
  if ( v12 >= 0x204 )
  {
    v13 = WPP_GLOBAL_Control;
    v11 = -2147417803;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v11;
    }
    v14 = 32;
    goto LABEL_28;
  }
  v15 = 2147483646;
  v16 = a3;
  do
  {
    if ( !v15 )
      break;
    if ( !*v7 )
      break;
    *v16++ = *v7++;
    --v15;
    --v8;
  }
  while ( v8 );
  v17 = v16 - 1;
  v11 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v17 = v16;
  *v17 = 0;
  if ( v8 )
  {
    v19 = v12 >> 1;
    result = 0;
    a3[v19 - 1] = a2 + 48;
    *(_DWORD *)&a3[v19] = 92;
    return result;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 33;
    v18 = *(_QWORD *)this + 592LL;
LABEL_29:
    WPP_SF_Zd(v13[2], v14, (unsigned int)WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids, v18, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1400367c0  push    rbx
0x1400367c2  push    rbp
0x1400367c3  push    rsi
0x1400367c4  push    rdi
0x1400367c5  push    r14
0x1400367c7  sub     rsp, 30h
0x1400367cb  mov     rdi, [rcx]
0x1400367ce  xor     ebp, ebp
0x1400367d0  mov     r11, r8
0x1400367d3  mov     esi, edx
0x1400367d5  mov     r14, rcx
0x1400367d8  mov     r10, [rdi+258h]
0x1400367df  test    r10, r10
0x1400367e2  jz      loc_140036905
0x1400367e8  mov     r9d, 104h
0x1400367ee  mov     rax, r10
0x1400367f1  mov     r8d, r9d
0x1400367f4  cmp     [rax], bp
0x1400367f7  jz      short loc_140036803
0x1400367f9  add     rax, 2
0x1400367fd  sub     r8, 1
0x140036801  jnz     short loc_1400367F4
0x140036803  mov     rax, r8
0x140036806  neg     rax
0x140036809  sbb     ebx, ebx
0x14003680b  not     ebx
0x14003680d  and     ebx, 80070057h
0x140036813  test    r8, r8
0x140036816  jz      loc_14003690A
0x14003681c  mov     rax, r9
0x14003681f  sub     rax, r8
0x140036822  add     rax, rax
0x140036825  neg     r8
0x140036828  sbb     rdx, rdx
0x14003682b  and     rdx, rax
0x14003682e  cmp     rdx, 204h
0x140036835  jb      short loc_140036871
0x140036837  mov     rcx, cs:WPP_GLOBAL_Control
0x14003683e  lea     rax, WPP_GLOBAL_Control
0x140036845  mov     ebx, 80010135h
0x14003684a  cmp     rcx, rax
0x14003684d  jz      loc_140036949
0x140036853  test    byte ptr [rcx+1Ch], 1
0x140036857  jz      loc_140036949
0x14003685d  cmp     byte ptr [rcx+19h], 2
0x140036861  jb      loc_140036949
0x140036867  mov     edx, 20h ; ' '
0x14003686c  jmp     loc_14003692E
0x140036871  mov     eax, 7FFFFFFEh
0x140036876  mov     r8, r11
0x140036879  test    rax, rax
0x14003687c  jz      short loc_14003689C
0x14003687e  movzx   ecx, word ptr [r10]
0x140036882  test    cx, cx
0x140036885  jz      short loc_14003689C
0x140036887  mov     [r8], cx
0x14003688b  add     r10, 2
0x14003688f  add     r8, 2
0x140036893  dec     rax
0x140036896  sub     r9, 1
0x14003689a  jnz     short loc_140036879
0x14003689c  mov     rax, r9
0x14003689f  lea     rcx, [r8-2]
0x1400368a3  neg     rax
0x1400368a6  sbb     ebx, ebx
0x1400368a8  not     ebx
0x1400368aa  and     ebx, 8007007Ah
0x1400368b0  test    r9, r9
0x1400368b3  cmovnz  rcx, r8
0x1400368b7  mov     [rcx], bp
0x1400368ba  jnz     short loc_1400368EC
0x1400368bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400368c3  lea     rax, WPP_GLOBAL_Control
0x1400368ca  cmp     rcx, rax
0x1400368cd  jz      short loc_140036949
0x1400368cf  test    byte ptr [rcx+1Ch], 1
0x1400368d3  jz      short loc_140036949
0x1400368d5  cmp     byte ptr [rcx+19h], 2
0x1400368d9  jb      short loc_140036949
0x1400368db  mov     r9, [r14]
0x1400368de  mov     edx, 21h ; '!'
0x1400368e3  add     r9, 250h
0x1400368ea  jmp     short loc_140036935
0x1400368ec  shr     rdx, 1
0x1400368ef  add     si, 30h ; '0'
0x1400368f3  xor     eax, eax
0x1400368f5  mov     [r11+rdx*2-2], si
0x1400368fb  mov     dword ptr [r11+rdx*2], 5Ch ; '\'
0x140036903  jmp     short loc_14003694B
0x140036905  mov     ebx, 80070057h
0x14003690a  mov     rcx, cs:WPP_GLOBAL_Control
0x140036911  lea     rax, WPP_GLOBAL_Control
0x140036918  cmp     rcx, rax
0x14003691b  jz      short loc_140036949
0x14003691d  test    byte ptr [rcx+1Ch], 1
0x140036921  jz      short loc_140036949
0x140036923  cmp     byte ptr [rcx+19h], 2
0x140036927  jb      short loc_140036949
0x140036929  mov     edx, 1Fh
0x14003692e  lea     r9, [rdi+250h]
0x140036935  mov     rcx, [rcx+10h]
0x140036939  lea     r8, WPP_35806d468ac3359b7b679ca6b7a243e6_Traceguids
0x140036940  mov     [rsp+58h+var_38], ebx
0x140036944  call    WPP_SF_Zd
0x140036949  mov     eax, ebx
0x14003694b  add     rsp, 30h
0x14003694f  pop     r14
0x140036951  pop     rdi
0x140036952  pop     rsi
0x140036953  pop     rbp
0x140036954  pop     rbx
0x140036955  retn
```
