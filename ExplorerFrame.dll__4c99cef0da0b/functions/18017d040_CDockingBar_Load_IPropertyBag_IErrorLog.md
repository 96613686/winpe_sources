# CDockingBar::Load(IPropertyBag *,IErrorLog *)

- ea: `0x18017d040`
- end: `0x18017d235`
- name: `?Load@CDockingBar@@UEAAJPEAUIPropertyBag@@PEAUIErrorLog@@@Z`
- size: `501`
- prototype: `int(CDockingBar *__hidden this, struct IPropertyBag *, struct IErrorLog *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18017be40`

## callees

- `0x180210010`

## import_xrefs

- `USER32!OffsetRect` at `0x18017d186`
- `USER32!OffsetRect` at `0x18017d186`
- `USER32!MonitorFromPoint` at `0x18017d201`
- `USER32!MonitorFromPoint` at `0x18017d201`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d082`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0a0`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0bb`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0dd`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0ff`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d121`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d14d`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d16b`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d1a3`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d1c2`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d082`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0a0`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0bb`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0dd`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d0ff`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d121`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d14d`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d16b`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d1a3`
- `PROPSYS!PSPropertyBag_ReadInt` at `0x18017d1c2`

## pseudocode

```c
__int64 __fastcall CDockingBar::Load(struct tagRECT *this, struct IPropertyBag *a2, struct IErrorLog *a3)
{
  INT top; // eax
  unsigned int v6; // esi
  unsigned int v7; // edi
  LONG v8; // ecx
  INT v9; // eax
  int v10; // ecx
  INT value; // [rsp+20h] [rbp-10h] BYREF
  INT v13; // [rsp+28h] [rbp-8h] BYREF
  unsigned __int64 v14; // [rsp+60h] [rbp+30h] BYREF
  INT v15; // [rsp+78h] [rbp+48h] BYREF

  this[4].left &= ~0x10u;
  this[4].left |= 0x20u;
  top = 0;
  if ( this[4].top != 7 )
    top = this[4].top;
  value = top;
  PSPropertyBag_ReadInt(a2, L"Mode", &value);
  v13 = this[4].left & 7;
  PSPropertyBag_ReadInt(a2, L"Side", &v13);
  LODWORD(v14) = this[1].left;
  PSPropertyBag_ReadInt(a2, L"Left", (INT *)&v14);
  this[1].left = v14;
  LODWORD(v14) = this[1].right;
  PSPropertyBag_ReadInt(a2, L"Right", (INT *)&v14);
  this[1].right = v14;
  LODWORD(v14) = this[1].top;
  PSPropertyBag_ReadInt(a2, L"Top", (INT *)&v14);
  this[1].top = v14;
  LODWORD(v14) = this[1].bottom;
  PSPropertyBag_ReadInt(a2, L"Bottom", (INT *)&v14);
  this[1].bottom = v14;
  LODWORD(v14) = this[2].left;
  PSPropertyBag_ReadInt(a2, L"X", (INT *)&v14);
  v6 = v14;
  LODWORD(v14) = this[2].top;
  PSPropertyBag_ReadInt(a2, L"Y", (INT *)&v14);
  v7 = v14;
  OffsetRect(this + 2, v6 - this[2].left, v14 - this[2].top);
  LODWORD(v14) = this[2].right - this[2].left;
  PSPropertyBag_ReadInt(a2, L"CX", (INT *)&v14);
  v15 = this[2].bottom - this[2].top;
  PSPropertyBag_ReadInt(a2, L"CY", &v15);
  v8 = v14 + this[2].left;
  v9 = value;
  this[4].left &= 0xFFFFFFF8;
  this[2].right = v8;
  v10 = v15 + this[2].top;
  this[4].top = v9;
  LOBYTE(v9) = v13;
  this[2].bottom = v10;
  this[4].left |= v9 & 7;
  v14 = __PAIR64__(v7, v6);
  *(_QWORD *)&this[3].left = MonitorFromPoint((POINT)__PAIR64__(v7, v6), 2u);
  (*(void (__fastcall **)(LONG *, _QWORD))(*(_QWORD *)&this[-10].right + 48LL))(&this[-10].right, 0);
  return 0;
}

```

## disassembly

```asm
0x18017d040  mov     [rsp-28h+arg_8], rbx
0x18017d045  mov     [rsp-28h+arg_10], rsi
0x18017d04a  push    rbp
0x18017d04b  push    rdi
0x18017d04c  push    r13
0x18017d04e  push    r14
0x18017d050  push    r15
0x18017d052  mov     rbp, rsp
0x18017d055  sub     rsp, 30h
0x18017d059  and     dword ptr [rcx+40h], 0FFFFFFEFh
0x18017d05d  lea     r8, [rbp+value]; value
0x18017d061  or      dword ptr [rcx+40h], 20h
0x18017d065  xor     eax, eax
0x18017d067  cmp     dword ptr [rcx+44h], 7
0x18017d06b  mov     r15, rdx
0x18017d06e  mov     r13, rcx
0x18017d071  lea     rdx, aMode; "Mode"
0x18017d078  cmovnz  eax, [rcx+44h]
0x18017d07c  mov     rcx, r15; propBag
0x18017d07f  mov     [rbp+value], eax
0x18017d082  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d088  mov     eax, [r13+40h]
0x18017d08c  lea     r8, [rbp+var_8]; value
0x18017d090  and     eax, 7
0x18017d093  lea     rdx, aSide; "Side"
0x18017d09a  mov     rcx, r15; propBag
0x18017d09d  mov     [rbp+var_8], eax
0x18017d0a0  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d0a6  mov     eax, [r13+10h]
0x18017d0aa  lea     r8, [rbp+arg_0]; value
0x18017d0ae  lea     rdx, aLeft; "Left"
0x18017d0b5  mov     dword ptr [rbp+arg_0], eax
0x18017d0b8  mov     rcx, r15; propBag
0x18017d0bb  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d0c1  mov     eax, dword ptr [rbp+arg_0]
0x18017d0c4  lea     r8, [rbp+arg_0]; value
0x18017d0c8  mov     [r13+10h], eax
0x18017d0cc  lea     rdx, aRight; "Right"
0x18017d0d3  mov     eax, [r13+18h]
0x18017d0d7  mov     rcx, r15; propBag
0x18017d0da  mov     dword ptr [rbp+arg_0], eax
0x18017d0dd  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d0e3  mov     eax, dword ptr [rbp+arg_0]
0x18017d0e6  lea     r8, [rbp+arg_0]; value
0x18017d0ea  mov     [r13+18h], eax
0x18017d0ee  lea     rdx, aTop; "Top"
0x18017d0f5  mov     eax, [r13+14h]
0x18017d0f9  mov     rcx, r15; propBag
0x18017d0fc  mov     dword ptr [rbp+arg_0], eax
0x18017d0ff  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d105  mov     eax, dword ptr [rbp+arg_0]
0x18017d108  lea     r8, [rbp+arg_0]; value
0x18017d10c  mov     [r13+14h], eax
0x18017d110  lea     rdx, aBottom; "Bottom"
0x18017d117  mov     eax, [r13+1Ch]
0x18017d11b  mov     rcx, r15; propBag
0x18017d11e  mov     dword ptr [rbp+arg_0], eax
0x18017d121  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d127  mov     eax, dword ptr [rbp+arg_0]
0x18017d12a  lea     r14, [r13-98h]
0x18017d131  mov     [r13+1Ch], eax
0x18017d135  lea     r8, [rbp+arg_0]; value
0x18017d139  mov     eax, [r14+0B8h]
0x18017d140  lea     rdx, asc_18024764C; "X"
0x18017d147  mov     rcx, r15; propBag
0x18017d14a  mov     dword ptr [rbp+arg_0], eax
0x18017d14d  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d153  mov     eax, [r13+24h]
0x18017d157  lea     r8, [rbp+arg_0]; value
0x18017d15b  mov     esi, dword ptr [rbp+arg_0]
0x18017d15e  lea     rdx, aY; "Y"
0x18017d165  mov     rcx, r15; propBag
0x18017d168  mov     dword ptr [rbp+arg_0], eax
0x18017d16b  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d171  mov     edi, dword ptr [rbp+arg_0]
0x18017d174  lea     rbx, [r13+20h]
0x18017d178  mov     r8d, edi
0x18017d17b  mov     edx, esi
0x18017d17d  sub     r8d, [r13+24h]; dy
0x18017d181  mov     rcx, rbx; lprc
0x18017d184  sub     edx, [rbx]; dx
0x18017d186  call    cs:__imp_OffsetRect
0x18017d18c  mov     eax, [r13+28h]
0x18017d190  lea     r8, [rbp+arg_0]; value
0x18017d194  sub     eax, [rbx]
0x18017d196  lea     rdx, aCx; "CX"
0x18017d19d  mov     rcx, r15; propBag
0x18017d1a0  mov     dword ptr [rbp+arg_0], eax
0x18017d1a3  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d1a9  mov     eax, [r13+2Ch]
0x18017d1ad  sub     eax, [r13+24h]
0x18017d1b1  lea     r8, [rbp+arg_18]; value
0x18017d1b5  lea     rdx, aCy; "CY"
0x18017d1bc  mov     [rbp+arg_18], eax
0x18017d1bf  mov     rcx, r15; propBag
0x18017d1c2  call    cs:__imp_PSPropertyBag_ReadInt
0x18017d1c8  mov     ecx, [rbx]
0x18017d1ca  mov     edx, 2; dwFlags
0x18017d1cf  add     ecx, dword ptr [rbp+arg_0]
0x18017d1d2  mov     eax, [rbp+value]
0x18017d1d5  and     dword ptr [r13+40h], 0FFFFFFF8h
0x18017d1da  mov     [r13+28h], ecx
0x18017d1de  mov     ecx, [r13+24h]
0x18017d1e2  add     ecx, [rbp+arg_18]
0x18017d1e5  mov     [r13+44h], eax
0x18017d1e9  mov     eax, [rbp+var_8]
0x18017d1ec  mov     [r13+2Ch], ecx
0x18017d1f0  and     eax, 7
0x18017d1f3  or      [r13+40h], eax
0x18017d1f7  mov     dword ptr [rbp+arg_0], esi
0x18017d1fa  mov     dword ptr [rbp+arg_0+4], edi
0x18017d1fd  mov     rcx, [rbp+arg_0]; pt
0x18017d201  call    cs:__imp_MonitorFromPoint
0x18017d207  mov     [r13+30h], rax
0x18017d20b  xor     edx, edx
0x18017d20d  mov     rax, [r14]
0x18017d210  mov     rcx, r14
0x18017d213  mov     rax, [rax+30h]
0x18017d217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017d21c  mov     rbx, [rsp+30h+arg_8]
0x18017d221  xor     eax, eax
0x18017d223  mov     rsi, [rsp+30h+arg_10]
0x18017d228  add     rsp, 30h
0x18017d22c  pop     r15
0x18017d22e  pop     r14
0x18017d230  pop     r13
0x18017d232  pop     rdi
0x18017d233  pop     rbp
0x18017d234  retn
```
