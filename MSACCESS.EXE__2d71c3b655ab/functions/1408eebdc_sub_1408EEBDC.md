# sub_1408EEBDC

- ea: `0x1408eebdc`
- end: `0x1408eed32`
- name: `sub_1408EEBDC`
- size: `342`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1408eede0`

## callees

- `0x14004f990`
- `0x1408eebdc`

## import_xrefs

- `mso40uiWin32Client!mso40uiWin32Client_39172` at `0x1408eed2b`
- `mso40uiWin32Client!mso40uiWin32Client_51751` at `0x1408eed18`
- `mso40uiWin32Client!mso40uiWin32Client_51751` at `0x1408eed18`
- `mso40uiWin32Client!mso40uiWin32Client_52735` at `0x1408eed0f`
- `mso40uiWin32Client!mso40uiWin32Client_52735` at `0x1408eed0f`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eec6a`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eec87`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eeca4`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eecc1`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eecde`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eec6a`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eec87`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eeca4`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eecc1`
- `mso40uiWin32Client!mso40uiWin32Client_55306` at `0x1408eecde`
- `GDI32!DeleteObject` at `0x1408eec10`
- `GDI32!DeleteObject` at `0x1408eec22`
- `GDI32!DeleteObject` at `0x1408eec34`
- `GDI32!DeleteObject` at `0x1408eec46`
- `GDI32!DeleteObject` at `0x1408eec58`
- `GDI32!DeleteObject` at `0x1408eec10`
- `GDI32!DeleteObject` at `0x1408eec22`
- `GDI32!DeleteObject` at `0x1408eec34`
- `GDI32!DeleteObject` at `0x1408eec46`
- `GDI32!DeleteObject` at `0x1408eec58`

## pseudocode

```c
__int64 __fastcall sub_1408EEBDC(_QWORD *a1)
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
0x1408eebdc  mov     [rsp+arg_0], rbx
0x1408eebe1  push    rdi
0x1408eebe2  sub     rsp, 20h
0x1408eebe6  lea     rax, ??_7GroupingPaneUI@@6B@; const GroupingPaneUI::`vftable'
0x1408eebed  mov     rbx, rcx
0x1408eebf0  mov     [rcx], rax
0x1408eebf3  lea     rdi, [rcx+0D0h]
0x1408eebfa  mov     rcx, [rcx+330h]; ho
0x1408eec01  lea     rax, ??_7GroupingPaneUI@@6B@_0; const GroupingPaneUI::`vftable'
0x1408eec08  mov     [rdi], rax
0x1408eec0b  test    rcx, rcx
0x1408eec0e  jz      short loc_1408EEC16
0x1408eec10  call    cs:DeleteObject
0x1408eec16  mov     rcx, [rbx+338h]; ho
0x1408eec1d  test    rcx, rcx
0x1408eec20  jz      short loc_1408EEC28
0x1408eec22  call    cs:DeleteObject
0x1408eec28  mov     rcx, [rbx+340h]; ho
0x1408eec2f  test    rcx, rcx
0x1408eec32  jz      short loc_1408EEC3A
0x1408eec34  call    cs:DeleteObject
0x1408eec3a  mov     rcx, [rbx+348h]; ho
0x1408eec41  test    rcx, rcx
0x1408eec44  jz      short loc_1408EEC4C
0x1408eec46  call    cs:DeleteObject
0x1408eec4c  mov     rcx, [rbx+350h]; ho
0x1408eec53  test    rcx, rcx
0x1408eec56  jz      short loc_1408EEC5E
0x1408eec58  call    cs:DeleteObject
0x1408eec5e  mov     rcx, [rbx+308h]
0x1408eec65  test    rcx, rcx
0x1408eec68  jz      short loc_1408EEC7B
0x1408eec6a  call    cs:mso40uiWin32Client_55306
0x1408eec70  mov     qword ptr [rbx+308h], 0
0x1408eec7b  mov     rcx, [rbx+310h]
0x1408eec82  test    rcx, rcx
0x1408eec85  jz      short loc_1408EEC98
0x1408eec87  call    cs:mso40uiWin32Client_55306
0x1408eec8d  mov     qword ptr [rbx+310h], 0
0x1408eec98  mov     rcx, [rbx+318h]
0x1408eec9f  test    rcx, rcx
0x1408eeca2  jz      short loc_1408EECB5
0x1408eeca4  call    cs:mso40uiWin32Client_55306
0x1408eecaa  mov     qword ptr [rbx+318h], 0
0x1408eecb5  mov     rcx, [rbx+320h]
0x1408eecbc  test    rcx, rcx
0x1408eecbf  jz      short loc_1408EECD2
0x1408eecc1  call    cs:mso40uiWin32Client_55306
0x1408eecc7  mov     qword ptr [rbx+320h], 0
0x1408eecd2  mov     rcx, [rbx+328h]
0x1408eecd9  test    rcx, rcx
0x1408eecdc  jz      short loc_1408EECEF
0x1408eecde  call    cs:mso40uiWin32Client_55306
0x1408eece4  mov     qword ptr [rbx+328h], 0
0x1408eecef  mov     rcx, [rbx+3A8h]; pv
0x1408eecf6  test    rcx, rcx
0x1408eecf9  jz      short loc_1408EED00
0x1408eecfb  call    Ptr
0x1408eed00  mov     rcx, [rbx+2E0h]
0x1408eed07  test    rcx, rcx
0x1408eed0a  jz      short loc_1408EED15
0x1408eed0c  mov     rdx, rdi
0x1408eed0f  call    cs:mso40uiWin32Client_52735
0x1408eed15  mov     rcx, rdi
0x1408eed18  call    cs:mso40uiWin32Client_51751
0x1408eed1e  mov     rcx, rbx
0x1408eed21  mov     rbx, [rsp+28h+arg_0]
0x1408eed26  add     rsp, 20h
0x1408eed2a  pop     rdi
0x1408eed2b  jmp     cs:mso40uiWin32Client_39172
```
