# CPANE::DragColumnToPoint(int,int)

- ea: `0x180243174`
- end: `0x18024364d`
- name: `?DragColumnToPoint@CPANE@@QEAAXHH@Z`
- size: `1241`
- prototype: `void __fastcall(CPANE *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18023c0d0`

## callees

- `0x1801f3898`
- `0x1801f43c4`
- `0x1801f45b8`
- `0x1801f4654`
- `0x1801f4838`
- `0x180243174`
- `0x1802b2dcc`
- `0x1802b3458`
- `0x180379520`

## import_xrefs

- `USER32!GetDC` at `0x180243362`
- `USER32!GetDC` at `0x180243362`
- `USER32!ReleaseDC` at `0x1802435e0`
- `USER32!ReleaseDC` at `0x1802435e0`
- `GDI32!InvertRgn` at `0x1802435ca`
- `GDI32!InvertRgn` at `0x1802435ca`
- `GDI32!CreateRectRgn` at `0x180243550`
- `GDI32!CreateRectRgn` at `0x18024358e`
- `GDI32!CreateRectRgn` at `0x180243550`
- `GDI32!CreateRectRgn` at `0x18024358e`
- `GDI32!CombineRgn` at `0x180243540`
- `GDI32!CombineRgn` at `0x180243570`
- `GDI32!CombineRgn` at `0x1802435ba`
- `GDI32!CombineRgn` at `0x180243540`
- `GDI32!CombineRgn` at `0x180243570`
- `GDI32!CombineRgn` at `0x1802435ba`
- `GDI32!CreateRectRgnIndirect` at `0x180243510`
- `GDI32!CreateRectRgnIndirect` at `0x180243520`
- `GDI32!CreateRectRgnIndirect` at `0x180243510`
- `GDI32!CreateRectRgnIndirect` at `0x180243520`
- `GDI32!DeleteObject` at `0x1802435eb`
- `GDI32!DeleteObject` at `0x1802435f6`
- `GDI32!DeleteObject` at `0x180243607`
- `GDI32!DeleteObject` at `0x1802435eb`
- `GDI32!DeleteObject` at `0x1802435f6`
- `GDI32!DeleteObject` at `0x180243607`

## pseudocode

```c
void __fastcall CPANE::DragColumnToPoint(CPANE *this, int a2, int a3)
{
  unsigned int v3; // [rsp+20h] [rbp-70h]
  unsigned int v4; // [rsp+24h] [rbp-6Ch]
  unsigned int v5; // [rsp+28h] [rbp-68h]
  HRGN hrgnSrc1; // [rsp+30h] [rbp-60h]
  LONG v7; // [rsp+38h] [rbp-58h]
  unsigned int v8; // [rsp+3Ch] [rbp-54h]
  HRGN hrgnDst; // [rsp+40h] [rbp-50h]
  int v10; // [rsp+48h] [rbp-48h]
  HRGN hrgnSrc2; // [rsp+50h] [rbp-40h]
  HDC hdc; // [rsp+60h] [rbp-30h]
  unsigned int v13; // [rsp+68h] [rbp-28h]
  RECT rect; // [rsp+70h] [rbp-20h] BYREF
  LONG v18; // [rsp+B0h] [rbp+20h]

  v4 = CPANE::DichWidth(this);
  if ( a3 >= *((_DWORD *)this + 24) )
  {
    if ( a3 > *((_DWORD *)this + 26) )
    {
      if ( a3 - 100 <= *((_DWORD *)this + 26) || (v13 = *((_DWORD *)this + 30) + 5, v13 > CPANE::LnTopLast(this)) )
      {
        if ( *((_DWORD *)this + 30) < CPANE::LnTopLast(this) )
          CPANE::SetLnTop(this, *((_DWORD *)this + 30) + 1);
      }
      else
      {
        CPANE::SetLnTop(this, *((_DWORD *)this + 30) + 5);
      }
    }
  }
  else if ( a3 + 100 >= *((_DWORD *)this + 24) || *((_DWORD *)this + 30) < (unsigned int)(*((_DWORD *)this + 28) + 5) )
  {
    if ( *((_DWORD *)this + 30) > *((_DWORD *)this + 28) )
      CPANE::SetLnTop(this, *((_DWORD *)this + 30) - 1);
  }
  else
  {
    CPANE::SetLnTop(this, *((_DWORD *)this + 30) - 5);
  }
  if ( a2 >= *((_DWORD *)this + 23) )
  {
    if ( a2 > *((_DWORD *)this + 25) )
    {
      v5 = *((_DWORD *)this + 31) + v4 / 4;
      if ( v5 > 1023 - v4 )
        v5 = 1023 - v4;
      CPANE::SetIchLeft(this, v5);
    }
  }
  else
  {
    v8 = 0;
    if ( *((_DWORD *)this + 31) >= v4 / 4 )
      v8 = *((_DWORD *)this + 31) - v4 / 4;
    CPANE::SetIchLeft(this, v8);
  }
  hdc = GetDC(*((HWND *)this + 35));
  if ( hdc )
  {
    v7 = CPANE::YFromLn(this, *((_DWORD *)this + 35));
    v3 = CPANE::LnFromY(this, a3);
    if ( v3 >= *((_DWORD *)this + 29) + *((_DWORD *)this + 28) )
    {
      if ( *((_DWORD *)this + 29) + *((_DWORD *)this + 28) )
        v3 = *((_DWORD *)this + 28) + *((_DWORD *)this + 29) - 1;
      else
        v3 = 0;
    }
    if ( a3 >= (int)CPANE::YFromLn(this, *((_DWORD *)this + 35)) )
    {
      v18 = CPANE::YFromLn(this, v3 + 1);
      rect.top = v7;
    }
    else
    {
      v18 = CPANE::YFromLn(this, v3);
      rect.top = *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) + v7;
    }
    rect.left = CPANE::XFromIch(this, *((unsigned int *)this + 35), *((unsigned int *)this + 34), 1);
    rect.bottom = v18;
    if ( (*(_DWORD *)(*((_QWORD *)this + 33) + 160LL) & 1) == 0 )
    {
      if ( a2 <= rect.left )
        v10 = 0;
      else
        v10 = *(_DWORD *)(*((_QWORD *)this + 33) + 256LL) - 1;
      a2 = *((_DWORD *)this + 23)
         + *(_DWORD *)(*((_QWORD *)this + 33) + 256LL)
         * ((v10 + a2 - *((_DWORD *)this + 23))
          / *(_DWORD *)(*((_QWORD *)this + 33) + 256LL));
    }
    rect.right = a2;
    hrgnSrc2 = CreateRectRgnIndirect((const RECT *)((char *)this + 92));
    hrgnDst = CreateRectRgnIndirect(&rect);
    CombineRgn(hrgnDst, hrgnDst, hrgnSrc2, 1);
    hrgnSrc1 = CreateRectRgn(0, 0, 0, 0);
    CombineRgn(hrgnSrc1, hrgnSrc1, hrgnSrc2, 1);
    if ( !*((_QWORD *)this + 20) )
      *((_QWORD *)this + 20) = CreateRectRgn(0, 0, 0, 0);
    CombineRgn(hrgnSrc1, *((HRGN *)this + 20), hrgnDst, 3);
    InvertRgn(hdc, hrgnSrc1);
    ReleaseDC(*((HWND *)this + 35), hdc);
    DeleteObject(hrgnSrc1);
    DeleteObject(hrgnSrc2);
    DeleteObject(*((HGDIOBJ *)this + 20));
    *((_QWORD *)this + 20) = hrgnDst;
    *((_DWORD *)this + 37) = a2;
    *((_DWORD *)this + 38) = v3;
  }
}

```

## disassembly

```asm
0x180243174  mov     [rsp-8+arg_10], r8d
0x180243179  mov     [rsp-8+arg_8], edx
0x18024317d  mov     [rsp-8+arg_0], rcx
0x180243182  push    rbp
0x180243183  mov     rbp, rsp
0x180243186  sub     rsp, 90h
0x18024318d  mov     rax, cs:__security_cookie
0x180243194  xor     rax, rsp
0x180243197  mov     [rbp+var_10], rax
0x18024319b  mov     [rsp+90h+hrgnDst], 0
0x1802431a4  mov     [rsp+90h+hrgnSrc1], 0
0x1802431ad  mov     [rsp+90h+hrgnSrc2], 0
0x1802431b6  mov     rcx, [rbp+arg_0]; this
0x1802431ba  call    ?DichWidth@CPANE@@QEAAIXZ; CPANE::DichWidth(void)
0x1802431bf  mov     [rsp+90h+var_6C], eax
0x1802431c3  mov     rax, [rbp+arg_0]
0x1802431c7  mov     eax, [rax+60h]
0x1802431ca  cmp     [rbp+arg_10], eax
0x1802431cd  jge     short loc_18024323E
0x1802431cf  mov     eax, [rbp+arg_10]
0x1802431d2  add     eax, 64h ; 'd'
0x1802431d5  mov     rcx, [rbp+arg_0]
0x1802431d9  cmp     eax, [rcx+60h]
0x1802431dc  jge     short loc_180243210
0x1802431de  mov     rax, [rbp+arg_0]
0x1802431e2  mov     eax, [rax+70h]
0x1802431e5  mov     [rsp+90h+var_38], eax
0x1802431e9  mov     eax, [rsp+90h+var_38]
0x1802431ed  add     eax, 5
0x1802431f0  mov     rcx, [rbp+arg_0]
0x1802431f4  cmp     [rcx+78h], eax
0x1802431f7  jb      short loc_180243210
0x1802431f9  mov     rax, [rbp+arg_0]
0x1802431fd  mov     eax, [rax+78h]
0x180243200  sub     eax, 5
0x180243203  mov     edx, eax; unsigned int
0x180243205  mov     rcx, [rbp+arg_0]; this
0x180243209  call    ?SetLnTop@CPANE@@QEAAXI@Z; CPANE::SetLnTop(uint)
0x18024320e  jmp     short loc_18024323C
0x180243210  mov     rax, [rbp+arg_0]
0x180243214  mov     eax, [rax+70h]
0x180243217  mov     [rsp+90h+var_34], eax
0x18024321b  mov     rax, [rbp+arg_0]
0x18024321f  mov     ecx, [rsp+90h+var_34]
0x180243223  cmp     [rax+78h], ecx
0x180243226  jbe     short loc_18024323C
0x180243228  mov     rax, [rbp+arg_0]
0x18024322c  mov     eax, [rax+78h]
0x18024322f  dec     eax
0x180243231  mov     edx, eax; unsigned int
0x180243233  mov     rcx, [rbp+arg_0]; this
0x180243237  call    ?SetLnTop@CPANE@@QEAAXI@Z; CPANE::SetLnTop(uint)
0x18024323c  jmp     short loc_1802432B5
0x18024323e  mov     rax, [rbp+arg_0]
0x180243242  mov     eax, [rax+68h]
0x180243245  cmp     [rbp+arg_10], eax
0x180243248  jle     short loc_1802432B5
0x18024324a  mov     eax, [rbp+arg_10]
0x18024324d  sub     eax, 64h ; 'd'
0x180243250  mov     rcx, [rbp+arg_0]
0x180243254  cmp     eax, [rcx+68h]
0x180243257  jle     short loc_18024328F
0x180243259  mov     rax, [rbp+arg_0]
0x18024325d  mov     eax, [rax+78h]
0x180243260  add     eax, 5
0x180243263  mov     [rsp+90h+var_28], eax
0x180243267  mov     rcx, [rbp+arg_0]; this
0x18024326b  call    ?LnTopLast@CPANE@@QEAAIXZ; CPANE::LnTopLast(void)
0x180243270  mov     ecx, [rsp+90h+var_28]
0x180243274  cmp     ecx, eax
0x180243276  ja      short loc_18024328F
0x180243278  mov     rax, [rbp+arg_0]
0x18024327c  mov     eax, [rax+78h]
0x18024327f  add     eax, 5
0x180243282  mov     edx, eax; unsigned int
0x180243284  mov     rcx, [rbp+arg_0]; this
0x180243288  call    ?SetLnTop@CPANE@@QEAAXI@Z; CPANE::SetLnTop(uint)
0x18024328d  jmp     short loc_1802432B5
0x18024328f  mov     rcx, [rbp+arg_0]; this
0x180243293  call    ?LnTopLast@CPANE@@QEAAIXZ; CPANE::LnTopLast(void)
0x180243298  mov     rcx, [rbp+arg_0]
0x18024329c  cmp     [rcx+78h], eax
0x18024329f  jnb     short loc_1802432B5
0x1802432a1  mov     rax, [rbp+arg_0]
0x1802432a5  mov     eax, [rax+78h]
0x1802432a8  inc     eax
0x1802432aa  mov     edx, eax; unsigned int
0x1802432ac  mov     rcx, [rbp+arg_0]; this
0x1802432b0  call    ?SetLnTop@CPANE@@QEAAXI@Z; CPANE::SetLnTop(uint)
0x1802432b5  mov     rax, [rbp+arg_0]
0x1802432b9  mov     eax, [rax+5Ch]
0x1802432bc  cmp     [rbp+arg_8], eax
0x1802432bf  jge     short loc_18024330A
0x1802432c1  mov     [rsp+90h+var_54], 0
0x1802432c9  xor     edx, edx
0x1802432cb  mov     eax, [rsp+90h+var_6C]
0x1802432cf  mov     ecx, 4
0x1802432d4  div     ecx
0x1802432d6  mov     rcx, [rbp+arg_0]
0x1802432da  cmp     [rcx+7Ch], eax
0x1802432dd  jb      short loc_1802432FB
0x1802432df  xor     edx, edx
0x1802432e1  mov     eax, [rsp+90h+var_6C]
0x1802432e5  mov     ecx, 4
0x1802432ea  div     ecx
0x1802432ec  mov     rcx, [rbp+arg_0]
0x1802432f0  mov     ecx, [rcx+7Ch]
0x1802432f3  sub     ecx, eax
0x1802432f5  mov     eax, ecx
0x1802432f7  mov     [rsp+90h+var_54], eax
0x1802432fb  mov     edx, [rsp+90h+var_54]; unsigned int
0x1802432ff  mov     rcx, [rbp+arg_0]; this
0x180243303  call    ?SetIchLeft@CPANE@@QEAAXI@Z; CPANE::SetIchLeft(uint)
0x180243308  jmp     short loc_180243357
0x18024330a  mov     rax, [rbp+arg_0]
0x18024330e  mov     eax, [rax+64h]
0x180243311  cmp     [rbp+arg_8], eax
0x180243314  jle     short loc_180243357
0x180243316  xor     edx, edx
0x180243318  mov     eax, [rsp+90h+var_6C]
0x18024331c  mov     ecx, 4
0x180243321  div     ecx
0x180243323  mov     rcx, [rbp+arg_0]
0x180243327  add     eax, [rcx+7Ch]
0x18024332a  mov     [rsp+90h+var_68], eax
0x18024332e  mov     eax, 3FFh
0x180243333  sub     eax, [rsp+90h+var_6C]
0x180243337  cmp     [rsp+90h+var_68], eax
0x18024333b  jbe     short loc_18024334A
0x18024333d  mov     eax, 3FFh
0x180243342  sub     eax, [rsp+90h+var_6C]
0x180243346  mov     [rsp+90h+var_68], eax
0x18024334a  mov     edx, [rsp+90h+var_68]; unsigned int
0x18024334e  mov     rcx, [rbp+arg_0]; this
0x180243352  call    ?SetIchLeft@CPANE@@QEAAXI@Z; CPANE::SetIchLeft(uint)
0x180243357  mov     rax, [rbp+arg_0]
0x18024335b  mov     rcx, [rax+118h]; hWnd
0x180243362  call    cs:__imp_GetDC
0x180243368  mov     [rsp+90h+hdc], rax
0x18024336d  cmp     [rsp+90h+hdc], 0
0x180243373  jnz     short loc_18024337A
0x180243375  jmp     loc_180243638
0x18024337a  mov     rax, [rbp+arg_0]
0x18024337e  mov     edx, [rax+8Ch]; unsigned int
0x180243384  mov     rcx, [rbp+arg_0]; this
0x180243388  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18024338d  mov     [rsp+90h+var_58], eax
0x180243391  mov     edx, [rbp+arg_10]; int
0x180243394  mov     rcx, [rbp+arg_0]; this
0x180243398  call    ?LnFromY@CPANE@@QEAAIH@Z; CPANE::LnFromY(int)
0x18024339d  mov     [rsp+90h+var_70], eax
0x1802433a1  mov     rax, [rbp+arg_0]
0x1802433a5  mov     eax, [rax+70h]
0x1802433a8  mov     rcx, [rbp+arg_0]
0x1802433ac  add     eax, [rcx+74h]
0x1802433af  cmp     [rsp+90h+var_70], eax
0x1802433b3  jb      short loc_1802433E7
0x1802433b5  mov     rax, [rbp+arg_0]
0x1802433b9  mov     eax, [rax+70h]
0x1802433bc  mov     rcx, [rbp+arg_0]
0x1802433c0  add     eax, [rcx+74h]
0x1802433c3  test    eax, eax
0x1802433c5  jbe     short loc_1802433DF
0x1802433c7  mov     rax, [rbp+arg_0]
0x1802433cb  mov     eax, [rax+70h]
0x1802433ce  mov     rcx, [rbp+arg_0]
0x1802433d2  mov     ecx, [rcx+74h]
0x1802433d5  lea     eax, [rax+rcx-1]
0x1802433d9  mov     [rsp+90h+var_70], eax
0x1802433dd  jmp     short loc_1802433E7
0x1802433df  mov     [rsp+90h+var_70], 0
0x1802433e7  mov     rax, [rbp+arg_0]
0x1802433eb  mov     edx, [rax+8Ch]; unsigned int
0x1802433f1  mov     rcx, [rbp+arg_0]; this
0x1802433f5  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x1802433fa  cmp     [rbp+arg_10], eax
0x1802433fd  jge     short loc_18024342E
0x1802433ff  mov     edx, [rsp+90h+var_70]; unsigned int
0x180243403  mov     rcx, [rbp+arg_0]; this
0x180243407  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18024340c  mov     [rbp+arg_10], eax
0x18024340f  mov     rax, [rbp+arg_0]
0x180243413  mov     rax, [rax+108h]
0x18024341a  mov     eax, [rax+104h]
0x180243420  mov     ecx, [rsp+90h+var_58]
0x180243424  add     ecx, eax
0x180243426  mov     eax, ecx
0x180243428  mov     [rsp+90h+rect.top], eax
0x18024342c  jmp     short loc_18024344A
0x18024342e  mov     eax, [rsp+90h+var_70]
0x180243432  inc     eax
0x180243434  mov     edx, eax; unsigned int
0x180243436  mov     rcx, [rbp+arg_0]; this
0x18024343a  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18024343f  mov     [rbp+arg_10], eax
0x180243442  mov     eax, [rsp+90h+var_58]
0x180243446  mov     [rsp+90h+rect.top], eax
0x18024344a  mov     r9d, 1
0x180243450  mov     rax, [rbp+arg_0]
0x180243454  mov     r8d, [rax+88h]
0x18024345b  mov     rax, [rbp+arg_0]
0x18024345f  mov     edx, [rax+8Ch]
0x180243465  mov     rcx, [rbp+arg_0]
0x180243469  call    ?XFromIch@CPANE@@QEAAHIIW4SPACE_MODE@@@Z; CPANE::XFromIch(uint,uint,SPACE_MODE)
0x18024346e  mov     [rsp+90h+rect.left], eax
0x180243472  mov     eax, [rbp+arg_10]
0x180243475  mov     [rsp+90h+rect.bottom], eax
0x180243479  mov     rax, [rbp+arg_0]
0x18024347d  mov     rax, [rax+108h]
0x180243484  mov     eax, [rax+0A0h]
0x18024348a  shl     eax, 1Fh
0x18024348d  sar     eax, 1Fh
0x180243490  test    eax, eax
0x180243492  jnz     short loc_1802434FE
0x180243494  mov     eax, [rsp+90h+rect.left]
0x180243498  cmp     [rbp+arg_8], eax
0x18024349b  jle     short loc_1802434B6
0x18024349d  mov     rax, [rbp+arg_0]
0x1802434a1  mov     rax, [rax+108h]
0x1802434a8  mov     eax, [rax+100h]
0x1802434ae  dec     eax
0x1802434b0  mov     [rsp+90h+var_48], eax
0x1802434b4  jmp     short loc_1802434BE
0x1802434b6  mov     [rsp+90h+var_48], 0
0x1802434be  mov     rax, [rbp+arg_0]
0x1802434c2  mov     eax, [rax+5Ch]
0x1802434c5  mov     ecx, [rbp+arg_8]
0x1802434c8  sub     ecx, eax
0x1802434ca  mov     eax, ecx
0x1802434cc  add     eax, [rsp+90h+var_48]
0x1802434d0  mov     rcx, [rbp+arg_0]
0x1802434d4  mov     rcx, [rcx+108h]
0x1802434db  cdq
0x1802434dc  idiv    dword ptr [rcx+100h]
0x1802434e2  mov     rcx, [rbp+arg_0]
0x1802434e6  mov     rcx, [rcx+108h]
0x1802434ed  imul    eax, [rcx+100h]
0x1802434f4  mov     rcx, [rbp+arg_0]
0x1802434f8  add     eax, [rcx+5Ch]
0x1802434fb  mov     [rbp+arg_8], eax
0x1802434fe  mov     eax, [rbp+arg_8]
0x180243501  mov     [rsp+90h+rect.right], eax
0x180243505  mov     rax, [rbp+arg_0]
0x180243509  add     rax, 5Ch ; '\'
0x18024350d  mov     rcx, rax; lprect
0x180243510  call    cs:__imp_CreateRectRgnIndirect
0x180243516  mov     [rsp+90h+hrgnSrc2], rax
0x18024351b  lea     rcx, [rsp+90h+rect]; lprect
0x180243520  call    cs:__imp_CreateRectRgnIndirect
0x180243526  mov     [rsp+90h+hrgnDst], rax
0x18024352b  mov     r9d, 1; iMode
0x180243531  mov     r8, [rsp+90h+hrgnSrc2]; hrgnSrc2
0x180243536  mov     rdx, [rsp+90h+hrgnDst]; hrgnSrc1
0x18024353b  mov     rcx, [rsp+90h+hrgnDst]; hrgnDst
0x180243540  call    cs:__imp_CombineRgn
0x180243546  xor     r9d, r9d; y2
0x180243549  xor     r8d, r8d; x2
0x18024354c  xor     edx, edx; y1
0x18024354e  xor     ecx, ecx; x1
0x180243550  call    cs:__imp_CreateRectRgn
0x180243556  mov     [rsp+90h+hrgnSrc1], rax
0x18024355b  mov     r9d, 1; iMode
0x180243561  mov     r8, [rsp+90h+hrgnSrc2]; hrgnSrc2
0x180243566  mov     rdx, [rsp+90h+hrgnSrc1]; hrgnSrc1
0x18024356b  mov     rcx, [rsp+90h+hrgnSrc1]; hrgnDst
0x180243570  call    cs:__imp_CombineRgn
0x180243576  mov     rax, [rbp+arg_0]
0x18024357a  cmp     qword ptr [rax+0A0h], 0
0x180243582  jnz     short loc_18024359F
0x180243584  xor     r9d, r9d; y2
0x180243587  xor     r8d, r8d; x2
0x18024358a  xor     edx, edx; y1
0x18024358c  xor     ecx, ecx; x1
0x18024358e  call    cs:__imp_CreateRectRgn
0x180243594  mov     rcx, [rbp+arg_0]
0x180243598  mov     [rcx+0A0h], rax
0x18024359f  mov     r9d, 3; iMode
0x1802435a5  mov     r8, [rsp+90h+hrgnDst]; hrgnSrc2
0x1802435aa  mov     rax, [rbp+arg_0]
0x1802435ae  mov     rdx, [rax+0A0h]; hrgnSrc1
0x1802435b5  mov     rcx, [rsp+90h+hrgnSrc1]; hrgnDst
0x1802435ba  call    cs:__imp_CombineRgn
0x1802435c0  mov     rdx, [rsp+90h+hrgnSrc1]; hrgn
0x1802435c5  mov     rcx, [rsp+90h+hdc]; hdc
0x1802435ca  call    cs:__imp_InvertRgn
0x1802435d0  mov     rdx, [rsp+90h+hdc]; hDC
0x1802435d5  mov     rax, [rbp+arg_0]
0x1802435d9  mov     rcx, [rax+118h]; hWnd
0x1802435e0  call    cs:__imp_ReleaseDC
0x1802435e6  mov     rcx, [rsp+90h+hrgnSrc1]; ho
0x1802435eb  call    cs:__imp_DeleteObject
0x1802435f1  mov     rcx, [rsp+90h+hrgnSrc2]; ho
0x1802435f6  call    cs:__imp_DeleteObject
0x1802435fc  mov     rax, [rbp+arg_0]
0x180243600  mov     rcx, [rax+0A0h]; ho
0x180243607  call    cs:__imp_DeleteObject
0x18024360d  mov     rax, [rbp+arg_0]
0x180243611  mov     rcx, [rsp+90h+hrgnDst]
0x180243616  mov     [rax+0A0h], rcx
0x18024361d  mov     rax, [rbp+arg_0]
  ... truncated ...
```
