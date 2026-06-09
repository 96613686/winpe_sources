# sub_1408EDDCC

- ea: `0x1408eddcc`
- end: `0x1408edf22`
- name: `sub_1408EDDCC`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1408edfd0`

## callees

- `0x14004f990`
- `0x1408eddcc`

## import_xrefs

- `mso40uiWin32Client!mso40uiWin32Client_39172` at `0x1408edf1b`
- `mso40uiWin32Client!mso40uiWin32Client_51751` at `0x1408edf08`
- `mso40uiWin32Client!mso40uiWin32Client_51751` at `0x1408edf08`
- `mso40uiWin32Client!mso40uiWin32Client_52735` at `0x1408edeff`
- `mso40uiWin32Client!mso40uiWin32Client_52735` at `0x1408edeff`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408ede5a`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408ede77`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408ede94`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408edeb1`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408edece`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408ede5a`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408ede77`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408ede94`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408edeb1`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408edece`
- `GDI32!DeleteObject` at `0x1408ede00`
- `GDI32!DeleteObject` at `0x1408ede12`
- `GDI32!DeleteObject` at `0x1408ede24`
- `GDI32!DeleteObject` at `0x1408ede36`
- `GDI32!DeleteObject` at `0x1408ede48`
- `GDI32!DeleteObject` at `0x1408ede00`
- `GDI32!DeleteObject` at `0x1408ede12`
- `GDI32!DeleteObject` at `0x1408ede24`
- `GDI32!DeleteObject` at `0x1408ede36`
- `GDI32!DeleteObject` at `0x1408ede48`

## pseudocode

```c
__int64 __fastcall sub_1408EDDCC(_QWORD *a1)
{
  _QWORD *v2; // rdi
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  void *v13; // rcx
  __int64 v14; // rcx

  *a1 = &GroupingPaneUI::`vftable';
  v2 = a1 + 26;
  v3 = (void *)a1[102];
  *v2 = &GroupingPaneUI::`vftable';
  if ( v3 )
    DeleteObject(v3);
  v4 = (void *)a1[103];
  if ( v4 )
    DeleteObject(v4);
  v5 = (void *)a1[104];
  if ( v5 )
    DeleteObject(v5);
  v6 = (void *)a1[105];
  if ( v6 )
    DeleteObject(v6);
  v7 = (void *)a1[106];
  if ( v7 )
    DeleteObject(v7);
  v8 = a1[97];
  if ( v8 )
  {
    mso40uiWin32Client_55306(v8);
    a1[97] = 0;
  }
  v9 = a1[98];
  if ( v9 )
  {
    mso40uiWin32Client_55306(v9);
    a1[98] = 0;
  }
  v10 = a1[99];
  if ( v10 )
  {
    mso40uiWin32Client_55306(v10);
    a1[99] = 0;
  }
  v11 = a1[100];
  if ( v11 )
  {
    mso40uiWin32Client_55306(v11);
    a1[100] = 0;
  }
  v12 = a1[101];
  if ( v12 )
  {
    mso40uiWin32Client_55306(v12);
    a1[101] = 0;
  }
  v13 = (void *)a1[117];
  if ( v13 )
    Ptr(v13);
  v14 = a1[92];
  if ( v14 )
    mso40uiWin32Client_52735(v14, v2);
  mso40uiWin32Client_51751(v2);
  return mso40uiWin32Client_39172(a1);
}

```

## disassembly

```asm
0x1408eddcc  mov     [rsp+arg_0], rbx
0x1408eddd1  push    rdi
0x1408eddd2  sub     rsp, 20h
0x1408eddd6  lea     rax, ??_7GroupingPaneUI@@6B@; const GroupingPaneUI::`vftable'
0x1408edddd  mov     rbx, rcx
0x1408edde0  mov     [rcx], rax
0x1408edde3  lea     rdi, [rcx+0D0h]
0x1408eddea  mov     rcx, [rcx+330h]; ho
0x1408eddf1  lea     rax, ??_7GroupingPaneUI@@6B@_0; const GroupingPaneUI::`vftable'
0x1408eddf8  mov     [rdi], rax
0x1408eddfb  test    rcx, rcx
0x1408eddfe  jz      short loc_1408EDE06
0x1408ede00  call    cs:DeleteObject
0x1408ede06  mov     rcx, [rbx+338h]; ho
0x1408ede0d  test    rcx, rcx
0x1408ede10  jz      short loc_1408EDE18
0x1408ede12  call    cs:DeleteObject
0x1408ede18  mov     rcx, [rbx+340h]; ho
0x1408ede1f  test    rcx, rcx
0x1408ede22  jz      short loc_1408EDE2A
0x1408ede24  call    cs:DeleteObject
0x1408ede2a  mov     rcx, [rbx+348h]; ho
0x1408ede31  test    rcx, rcx
0x1408ede34  jz      short loc_1408EDE3C
0x1408ede36  call    cs:DeleteObject
0x1408ede3c  mov     rcx, [rbx+350h]; ho
0x1408ede43  test    rcx, rcx
0x1408ede46  jz      short loc_1408EDE4E
0x1408ede48  call    cs:DeleteObject
0x1408ede4e  mov     rcx, [rbx+308h]
0x1408ede55  test    rcx, rcx
0x1408ede58  jz      short loc_1408EDE6B
0x1408ede5a  call    cs:mso40uiWin32Client_55306
0x1408ede60  mov     qword ptr [rbx+308h], 0
0x1408ede6b  mov     rcx, [rbx+310h]
0x1408ede72  test    rcx, rcx
0x1408ede75  jz      short loc_1408EDE88
0x1408ede77  call    cs:mso40uiWin32Client_55306
0x1408ede7d  mov     qword ptr [rbx+310h], 0
0x1408ede88  mov     rcx, [rbx+318h]
0x1408ede8f  test    rcx, rcx
0x1408ede92  jz      short loc_1408EDEA5
0x1408ede94  call    cs:mso40uiWin32Client_55306
0x1408ede9a  mov     qword ptr [rbx+318h], 0
0x1408edea5  mov     rcx, [rbx+320h]
0x1408edeac  test    rcx, rcx
0x1408edeaf  jz      short loc_1408EDEC2
0x1408edeb1  call    cs:mso40uiWin32Client_55306
0x1408edeb7  mov     qword ptr [rbx+320h], 0
0x1408edec2  mov     rcx, [rbx+328h]
0x1408edec9  test    rcx, rcx
0x1408edecc  jz      short loc_1408EDEDF
0x1408edece  call    cs:mso40uiWin32Client_55306
0x1408eded4  mov     qword ptr [rbx+328h], 0
0x1408ededf  mov     rcx, [rbx+3A8h]; pv
0x1408edee6  test    rcx, rcx
0x1408edee9  jz      short loc_1408EDEF0
0x1408edeeb  call    Ptr
0x1408edef0  mov     rcx, [rbx+2E0h]
0x1408edef7  test    rcx, rcx
0x1408edefa  jz      short loc_1408EDF05
0x1408edefc  mov     rdx, rdi
0x1408edeff  call    cs:mso40uiWin32Client_52735
0x1408edf05  mov     rcx, rdi
0x1408edf08  call    cs:mso40uiWin32Client_51751
0x1408edf0e  mov     rcx, rbx
0x1408edf11  mov     rbx, [rsp+28h+arg_0]
0x1408edf16  add     rsp, 20h
0x1408edf1a  pop     rdi
0x1408edf1b  jmp     cs:mso40uiWin32Client_39172
```
