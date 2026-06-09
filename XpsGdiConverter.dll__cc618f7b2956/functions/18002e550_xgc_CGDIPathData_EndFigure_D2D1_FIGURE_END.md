# xgc::CGDIPathData::EndFigure(D2D1_FIGURE_END)

- ea: `0x18002e550`
- end: `0x18002e67e`
- name: `?EndFigure@CGDIPathData@xgc@@UEAAXW4D2D1_FIGURE_END@@@Z`
- size: `302`
- prototype: `void __fastcall(xgc::CGDIPathData *__hidden this, enum D2D1_FIGURE_END)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180015a88`
- `0x18002e43c`
- `0x18002e550`
- `0x1800304c8`
- `0x1800307a4`
- `0x1800308d0`
- `0x1800308f4`
- `0x180030910`
- `0x18003098c`

## pseudocode

```c
void __fastcall xgc::CGDIPathData::EndFigure(xgc::CGDIPathData *this, enum D2D1_FIGURE_END a2)
{
  int v3; // eax
  __int64 v4; // rcx
  _BYTE *v5; // rax
  char v6; // dl
  const struct tagPOINT **v7; // rdi
  __int64 v8; // rax
  const xpsrdr::hr_error *v9; // [rsp+20h] [rbp-18h] BYREF
  struct tagPOINT v11; // [rsp+50h] [rbp+18h] BYREF

  if ( *((int *)this + 6) >= 0 )
  {
    v3 = *((_DWORD *)this + 25);
    if ( !v3 || *((_DWORD *)this + 26) != 1 )
    {
      try
      {
        if ( a2 == D2D1_FIGURE_END_CLOSED )
        {
          if ( v3 )
          {
            if ( *(_BYTE *)std::vector<unsigned char>::back((char *)this + 64) != 6 )
            {
              v5 = (_BYTE *)std::vector<unsigned char>::back(v4);
              *v5 |= v6;
            }
          }
          else
          {
            v7 = (const struct tagPOINT **)((char *)this + 40);
            v8 = std::vector<tagPOINT>::at((char *)this + 40);
            std::vector<tagPOINT>::push_back(v7, v8);
            LOBYTE(v11.x) = 2;
            std::vector<unsigned char>::push_back((char *)this + 64, &v11);
            if ( (unsigned __int64)(v7[1] - *v7) >= 2 && (*(_BYTE *)(*((_QWORD *)this + 8) + 1LL) & 0xFE) != 6 )
            {
              v11 = xgc::DegenerateLineSegment(
                      (xgc *)*v7,
                      *v7 + 1,
                      (const struct tagPOINT *)*(unsigned int *)(*((_QWORD *)this + 2) + 8LL),
                      *(_DWORD *)(*((_QWORD *)this + 2) + 12LL),
                      (int)v9);
              std::vector<tagPOINT>::push_back(v7, &v11);
              LOBYTE(v11.x) = 2;
              std::vector<unsigned char>::push_back((char *)this + 64, &v11);
            }
          }
        }
        if ( !*((_DWORD *)this + 25) )
        {
          xgc::CGDIPathData::Stroke(this);
          std::vector<D2D_RECT_U>::clear((char *)this + 40);
          std::vector<D2D_RECT_U>::clear((char *)this + 64);
        }
        if ( !*((_BYTE *)this + 93) )
          xgc::CGDIPathData::FixDegeneratedRectangle(this);
      }
      catch ( std::bad_alloc )
      {
        *((_DWORD *)this + 6) = -2147024882;
        return;
      }
      catch ( const xpsrdr::hr_error *v9 )
      {
        *((_DWORD *)this + 6) = *((_DWORD *)v9 + 6);
        return;
      }
      catch ( std::exception )
      {
        *((_DWORD *)this + 6) = -2147467259;
        return;
      }
      catch ( ... )
      {
        *((_DWORD *)this + 6) = -2147418113;
      }
    }
  }
}

```

## disassembly

```asm
0x18002e550  mov     [rsp+arg_8], rbx
0x18002e555  mov     [rsp+arg_18], rsi
0x18002e55a  mov     [rsp+arg_0], rcx
0x18002e55f  push    rdi
0x18002e560  sub     rsp, 30h
0x18002e564  mov     rbx, rcx
0x18002e567  cmp     dword ptr [rcx+18h], 0
0x18002e56b  jl      loc_18002E66D
0x18002e571  mov     eax, [rcx+64h]
0x18002e574  test    eax, eax
0x18002e576  jz      short loc_18002E582
0x18002e578  cmp     dword ptr [rcx+68h], 1
0x18002e57c  jz      loc_18002E66D
0x18002e582  cmp     edx, 1
0x18002e585  jnz     loc_18002E636
0x18002e58b  test    eax, eax
0x18002e58d  jz      short loc_18002E5AD
0x18002e58f  add     rcx, 40h ; '@'
0x18002e593  call    ?back@?$vector@EV?$allocator@E@std@@@std@@QEAAAEAEXZ; std::vector<uchar>::back(void)
0x18002e598  cmp     byte ptr [rax], 6
0x18002e59b  jz      loc_18002E636
0x18002e5a1  call    ?back@?$vector@EV?$allocator@E@std@@@std@@QEAAAEAEXZ; std::vector<uchar>::back(void)
0x18002e5a6  or      [rax], dl
0x18002e5a8  jmp     loc_18002E636
0x18002e5ad  lea     rdi, [rcx+28h]
0x18002e5b1  mov     rcx, rdi
0x18002e5b4  call    ?at@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@QEAAAEAUtagPOINT@@_K@Z; std::vector<tagPOINT>::at(unsigned __int64)
0x18002e5b9  mov     rdx, rax
0x18002e5bc  mov     rcx, rdi
0x18002e5bf  call    ?push_back@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@QEAAXAEBUtagPOINT@@@Z; std::vector<tagPOINT>::push_back(tagPOINT const &)
0x18002e5c4  lea     rsi, [rbx+40h]
0x18002e5c8  mov     byte ptr [rsp+38h+arg_10], 2
0x18002e5cd  lea     rdx, [rsp+38h+arg_10]
0x18002e5d2  mov     rcx, rsi
0x18002e5d5  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18002e5da  mov     rcx, [rdi]; this
0x18002e5dd  mov     rax, [rdi+8]
0x18002e5e1  sub     rax, rcx
0x18002e5e4  sar     rax, 3
0x18002e5e8  cmp     rax, 2
0x18002e5ec  jb      short loc_18002E636
0x18002e5ee  mov     rax, [rsi]
0x18002e5f1  movzx   edx, byte ptr [rax+1]
0x18002e5f5  and     edx, 0FFFFFFFEh
0x18002e5f8  cmp     dl, 6
0x18002e5fb  jz      short loc_18002E636
0x18002e5fd  mov     r8, [rbx+10h]
0x18002e601  lea     rdx, [rcx+8]; struct tagPOINT *
0x18002e605  mov     r9d, [r8+0Ch]; int
0x18002e609  mov     r8d, [r8+8]; struct tagPOINT *
0x18002e60d  call    ?DegenerateLineSegment@xgc@@YA?AUtagPOINT@@AEBU2@0HH@Z; xgc::DegenerateLineSegment(tagPOINT const &,tagPOINT const &,int,int)
0x18002e612  mov     [rsp+38h+arg_10], rax
0x18002e617  lea     rdx, [rsp+38h+arg_10]
0x18002e61c  mov     rcx, rdi
0x18002e61f  call    ?push_back@?$vector@UtagPOINT@@V?$allocator@UtagPOINT@@@std@@@std@@QEAAXAEBUtagPOINT@@@Z; std::vector<tagPOINT>::push_back(tagPOINT const &)
0x18002e624  mov     byte ptr [rsp+38h+arg_10], 2
0x18002e629  lea     rdx, [rsp+38h+arg_10]
0x18002e62e  mov     rcx, rsi
0x18002e631  call    ?push_back@?$vector@EV?$allocator@E@std@@@std@@QEAAX$$QEAE@Z; std::vector<uchar>::push_back(uchar &&)
0x18002e636  cmp     dword ptr [rbx+64h], 0
0x18002e63a  jnz     short loc_18002E656
0x18002e63c  mov     rcx, rbx; this
0x18002e63f  call    ?Stroke@CGDIPathData@xgc@@QEBAXXZ; xgc::CGDIPathData::Stroke(void)
0x18002e644  lea     rcx, [rbx+28h]
0x18002e648  call    ?clear@?$vector@UD2D_RECT_U@@V?$allocator@UD2D_RECT_U@@@std@@@std@@QEAAXXZ; std::vector<D2D_RECT_U>::clear(void)
0x18002e64d  lea     rcx, [rbx+40h]
0x18002e651  call    ?clear@?$vector@UD2D_RECT_U@@V?$allocator@UD2D_RECT_U@@@std@@@std@@QEAAXXZ; std::vector<D2D_RECT_U>::clear(void)
0x18002e656  cmp     byte ptr [rbx+5Dh], 0
0x18002e65a  jnz     short loc_18002E665
0x18002e65c  mov     rcx, rbx; this
0x18002e65f  call    ?FixDegeneratedRectangle@CGDIPathData@xgc@@AEAAXXZ; xgc::CGDIPathData::FixDegeneratedRectangle(void)
0x18002e664  nop
0x18002e665  jmp     short loc_18002E66D
0x18002e667  jmp     short loc_18002E66D
0x18002e669  jmp     short loc_18002E66D
0x18002e66b  jmp     short $+2
0x18002e66d  mov     rbx, [rsp+38h+arg_8]
0x18002e672  mov     rsi, [rsp+38h+arg_18]
0x18002e677  add     rsp, 30h
0x18002e67b  pop     rdi
0x18002e67c  retn
```
