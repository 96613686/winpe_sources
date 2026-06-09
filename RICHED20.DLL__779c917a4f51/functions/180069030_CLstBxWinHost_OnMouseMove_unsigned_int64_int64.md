# CLstBxWinHost::OnMouseMove(unsigned __int64,__int64)

- ea: `0x180069030`
- end: `0x1800691d9`
- name: `?OnMouseMove@CLstBxWinHost@@QEAA_J_K_J@Z`
- size: `425`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18006956c`
- `0x180069ec0`

## callees

- `0x180061fe0`
- `0x180066874`
- `0x180068060`
- `0x180069030`
- `0x18006960c`
- `0x1800696cc`
- `0x180092010`

## import_xrefs

- `USER32!PtInRect` at `0x180069078`
- `USER32!PtInRect` at `0x180069078`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::OnMouseMove(CLstBxWinHost *this, __int64 a2, __int64 a3)
{
  int v3; // ebp
  int v6; // r14d
  int ItemFromPoint; // esi
  int v8; // ecx
  int v9; // eax
  int *v10; // r8
  int v11; // ebp
  int v12; // edx
  struct tagPOINT v14; // [rsp+48h] [rbp+10h] BYREF

  v3 = (__int16)a3;
  v6 = SWORD1(a3);
  v14.x = (__int16)a3;
  v14.y = SWORD1(a3);
  if ( *((_QWORD *)this + 285) == a3 && PtInRect((const RECT *)((char *)this + 164), v14) )
    return 0;
  *((_QWORD *)this + 285) = a3;
  ItemFromPoint = CLstBxWinHost::GetItemFromPoint(this, &v14);
  if ( (*((_BYTE *)this + 128) & 0x40) == 0 )
  {
    if ( !(unsigned int)CLstBxWinHost::PointInRect(this, &v14) )
      return 0;
LABEL_27:
    if ( ItemFromPoint != *((_DWORD *)this + 50)
      || *((_DWORD *)this + 33) == 8
      && ItemFromPoint >= 0
      && !(unsigned int)CLstBxWinHost::IsSelected(this, ItemFromPoint) )
    {
      CLstBxWinHost::MouseMoveHelper(this, ItemFromPoint, 1);
    }
    return 0;
  }
  if ( v6 < 0 )
  {
    v9 = -v6;
  }
  else
  {
    v8 = *((_DWORD *)this + 44);
    if ( v6 <= v8 - 1 )
    {
      if ( *((_DWORD *)this + 33) == 8 && (v3 < 0 || v3 > *((_DWORD *)this + 43) - 1) )
        return 0;
      goto LABEL_27;
    }
    LOWORD(v9) = v6 - v8 + 1;
  }
  v10 = (int *)((char *)this + 192);
  v11 = 250 - 16 * (unsigned __int16)v9;
  if ( v6 > 0 )
  {
    v12 = *v10 - 1;
    if ( v12 >= ItemFromPoint + 1 )
      v12 = ItemFromPoint + 1;
  }
  else
  {
    v12 = 0;
    if ( ItemFromPoint - 1 >= 0 )
      v12 = ItemFromPoint - 1;
  }
  if ( v12 >= 0 && v12 < *v10 )
  {
    if ( v12 != *((_DWORD *)this + 50) )
      CLstBxWinHost::MouseMoveHelper(this, v12, *((_DWORD *)this + 33) != 8);
    CLstBxWinHost::OnVScroll(this, (unsigned __int64)(unsigned int)~v6 >> 31, (__int64)v10);
  }
  if ( v11 < 5 )
    v11 = 5;
  (*(void (__fastcall **)(CLstBxWinHost *, __int64, _QWORD))(*(_QWORD *)this + 112LL))(this, 28988, (unsigned int)v11);
  return 0;
}

```

## disassembly

```asm
0x180069030  mov     r11, rsp
0x180069033  mov     [r11+8], rbx
0x180069037  mov     [r11+18h], rbp
0x18006903b  mov     [r11+10h], rdx
0x18006903f  push    rsi
0x180069040  push    rdi
0x180069041  push    r14
0x180069043  sub     rsp, 20h
0x180069047  mov     eax, r8d
0x18006904a  movsx   ebp, r8w
0x18006904e  shr     rax, 10h
0x180069052  mov     rdi, r8
0x180069055  mov     rbx, rcx
0x180069058  movsx   r14d, ax
0x18006905c  mov     [rsp+38h+arg_8.x], ebp
0x180069060  mov     [r11+14h], r14d
0x180069064  cmp     [rcx+8E8h], r8
0x18006906b  jnz     short loc_180069086
0x18006906d  mov     rdx, [r11+10h]; pt
0x180069071  add     rcx, 0A4h; lprc
0x180069078  call    cs:__imp_PtInRect
0x18006907e  test    eax, eax
0x180069080  jnz     loc_1800691C4
0x180069086  lea     rdx, [rsp+38h+arg_8]; struct tagPOINT *
0x18006908b  mov     [rbx+8E8h], rdi
0x180069092  mov     rcx, rbx; this
0x180069095  call    ?GetItemFromPoint@CLstBxWinHost@@QEAAHPEBUtagPOINT@@@Z; CLstBxWinHost::GetItemFromPoint(tagPOINT const *)
0x18006909a  test    byte ptr [rbx+80h], 40h
0x1800690a1  mov     esi, eax
0x1800690a3  jz      loc_180069180
0x1800690a9  mov     edi, r14d
0x1800690ac  test    r14d, r14d
0x1800690af  js      short loc_1800690F1
0x1800690b1  mov     ecx, [rbx+0B0h]
0x1800690b7  lea     eax, [rcx-1]
0x1800690ba  cmp     r14d, eax
0x1800690bd  jg      short loc_1800690E9
0x1800690bf  cmp     dword ptr [rbx+84h], 8
0x1800690c6  jnz     loc_180069191
0x1800690cc  test    ebp, ebp
0x1800690ce  js      loc_1800691C4
0x1800690d4  mov     eax, [rbx+0ACh]
0x1800690da  dec     eax
0x1800690dc  cmp     ebp, eax
0x1800690de  jg      loc_1800691C4
0x1800690e4  jmp     loc_180069191
0x1800690e9  mov     eax, edi
0x1800690eb  sub     eax, ecx
0x1800690ed  inc     eax
0x1800690ef  jmp     short loc_1800690F5
0x1800690f1  mov     eax, edi
0x1800690f3  neg     eax
0x1800690f5  movzx   eax, ax
0x1800690f8  lea     r8, [rbx+0C0h]
0x1800690ff  shl     eax, 4
0x180069102  mov     ebp, 0FAh
0x180069107  sub     ebp, eax
0x180069109  test    edi, edi
0x18006910b  jg      short loc_180069119
0x18006910d  lea     eax, [rsi-1]
0x180069110  xor     edx, edx
0x180069112  test    eax, eax
0x180069114  cmovns  edx, eax
0x180069117  jmp     short loc_180069126
0x180069119  mov     edx, [r8]
0x18006911c  lea     ecx, [rsi+1]
0x18006911f  dec     edx
0x180069121  cmp     edx, ecx
0x180069123  cmovge  edx, ecx; int
0x180069126  test    edx, edx
0x180069128  js      short loc_18006915D
0x18006912a  cmp     edx, [r8]
0x18006912d  jge     short loc_18006915D
0x18006912f  cmp     edx, [rbx+0C8h]
0x180069135  jz      short loc_18006914D
0x180069137  xor     r8d, r8d
0x18006913a  mov     rcx, rbx; this
0x18006913d  cmp     dword ptr [rbx+84h], 8
0x180069144  setnz   r8b; int
0x180069148  call    ?MouseMoveHelper@CLstBxWinHost@@IEAAXHH@Z; CLstBxWinHost::MouseMoveHelper(int,int)
0x18006914d  not     edi
0x18006914f  mov     rcx, rbx; this
0x180069152  mov     edx, edi
0x180069154  shr     rdx, 1Fh; unsigned __int64
0x180069158  call    ?OnVScroll@CLstBxWinHost@@QEAA_J_K_J@Z; CLstBxWinHost::OnVScroll(unsigned __int64,__int64)
0x18006915d  mov     rax, [rbx]
0x180069160  mov     ecx, 5
0x180069165  cmp     ebp, ecx
0x180069167  mov     edx, 713Ch
0x18006916c  cmovl   ebp, ecx
0x18006916f  mov     rcx, rbx
0x180069172  mov     rax, [rax+70h]
0x180069176  mov     r8d, ebp
0x180069179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006917e  jmp     short loc_1800691C4
0x180069180  lea     rdx, [rsp+38h+arg_8]; struct tagPOINT *
0x180069185  mov     rcx, rbx; this
0x180069188  call    ?PointInRect@CLstBxWinHost@@QEAAHPEBUtagPOINT@@@Z; CLstBxWinHost::PointInRect(tagPOINT const *)
0x18006918d  test    eax, eax
0x18006918f  jz      short loc_1800691C4
0x180069191  cmp     esi, [rbx+0C8h]
0x180069197  jnz     short loc_1800691B4
0x180069199  cmp     dword ptr [rbx+84h], 8
0x1800691a0  jnz     short loc_1800691C4
0x1800691a2  test    esi, esi
0x1800691a4  js      short loc_1800691C4
0x1800691a6  mov     edx, esi; int
0x1800691a8  mov     rcx, rbx; this
0x1800691ab  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x1800691b0  test    eax, eax
0x1800691b2  jnz     short loc_1800691C4
0x1800691b4  mov     r8d, 1; int
0x1800691ba  mov     edx, esi; int
0x1800691bc  mov     rcx, rbx; this
0x1800691bf  call    ?MouseMoveHelper@CLstBxWinHost@@IEAAXHH@Z; CLstBxWinHost::MouseMoveHelper(int,int)
0x1800691c4  mov     rbx, [rsp+38h+arg_0]
0x1800691c9  xor     eax, eax
0x1800691cb  mov     rbp, [rsp+38h+arg_10]
0x1800691d0  add     rsp, 20h
0x1800691d4  pop     r14
0x1800691d6  pop     rdi
0x1800691d7  pop     rsi
0x1800691d8  retn
```
