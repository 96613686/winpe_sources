# COffscreenDC::FreeData(void)

- ea: `0x18006dd50`
- end: `0x18006ddb4`
- name: `?FreeData@COffscreenDC@@AEAAXXZ`
- size: `100`
- prototype: `void __fastcall(COffscreenDC *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18006d6c8`
- `0x18006d710`
- `0x18006f710`
- `0x18010dc0c`
- `0x1801304b4`

## callees

- `0x18006dd50`
- `0x1801e7ee8`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18006dd93`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18006dd93`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18006ddac`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18006ddac`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18006dd82`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18006dd82`

## pseudocode

```c
void __fastcall COffscreenDC::FreeData(COffscreenDC *this, __int64 a2, int a3)
{
  HDC v4; // rcx
  HPALETTE v5; // rdx
  void *v6; // rdx
  void *v7; // rcx

  v4 = *(HDC *)this;
  if ( v4 )
  {
    v5 = (HPALETTE)*((_QWORD *)this + 3);
    if ( v5 )
      CW32System::SelectPalette(v4, v5, a3);
    v6 = (void *)*((_QWORD *)this + 1);
    if ( v6 )
      SelectObject(*(HDC *)this, v6);
    v7 = (void *)*((_QWORD *)this + 2);
    if ( v7 )
    {
      DeleteObject(v7);
      *((_QWORD *)this + 2) = 0;
    }
    DeleteDC(*(HDC *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18006dd50  push    rbx
0x18006dd52  sub     rsp, 20h
0x18006dd56  mov     rbx, rcx
0x18006dd59  mov     rcx, [rcx]; HDC
0x18006dd5c  test    rcx, rcx
0x18006dd5f  jnz     short loc_18006DD67
0x18006dd61  add     rsp, 20h
0x18006dd65  pop     rbx
0x18006dd66  retn
0x18006dd67  mov     rdx, [rbx+18h]; HPALETTE
0x18006dd6b  test    rdx, rdx
0x18006dd6e  jnz     short loc_18006DDA2
0x18006dd70  mov     rdx, [rbx+8]; h
0x18006dd74  test    rdx, rdx
0x18006dd77  jnz     short loc_18006DDA9
0x18006dd79  mov     rcx, [rbx+10h]; ho
0x18006dd7d  test    rcx, rcx
0x18006dd80  jz      short loc_18006DD90
0x18006dd82  call    cs:__imp_DeleteObject
0x18006dd88  mov     qword ptr [rbx+10h], 0
0x18006dd90  mov     rcx, [rbx]; hdc
0x18006dd93  call    cs:__imp_DeleteDC
0x18006dd99  mov     qword ptr [rbx], 0
0x18006dda0  jmp     short loc_18006DD61
0x18006dda2  call    ?SelectPalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAU2@H@Z; CW32System::SelectPalette(HDC__ *,HPALETTE__ *,int)
0x18006dda7  jmp     short loc_18006DD70
0x18006dda9  mov     rcx, [rbx]; hdc
0x18006ddac  call    cs:__imp_SelectObject
0x18006ddb2  jmp     short loc_18006DD79
```
