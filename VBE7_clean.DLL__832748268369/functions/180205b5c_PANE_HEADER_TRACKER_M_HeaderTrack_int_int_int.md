# PANE_HEADER_TRACKER::M_HeaderTrack(int,int,int)

- ea: `0x180205b5c`
- end: `0x180205c42`
- name: `?M_HeaderTrack@PANE_HEADER_TRACKER@@QEAAXHHH@Z`
- size: `230`
- prototype: `void __fastcall(PANE_HEADER_TRACKER *__hidden this, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18020674c`

## callees

- `0x180205b5c`

## import_xrefs

- `USER32!GetDC` at `0x180205b84`
- `USER32!GetDC` at `0x180205b84`
- `USER32!ReleaseDC` at `0x180205c23`
- `USER32!ReleaseDC` at `0x180205c23`
- `GDI32!GetStockObject` at `0x180205baf`
- `GDI32!GetStockObject` at `0x180205baf`
- `GDI32!LineTo` at `0x180205bde`
- `GDI32!LineTo` at `0x180205c0b`
- `GDI32!LineTo` at `0x180205bde`
- `GDI32!LineTo` at `0x180205c0b`
- `GDI32!MoveToEx` at `0x180205bce`
- `GDI32!MoveToEx` at `0x180205bfb`
- `GDI32!MoveToEx` at `0x180205bce`
- `GDI32!MoveToEx` at `0x180205bfb`
- `GDI32!SetROP2` at `0x180205b9e`
- `GDI32!SetROP2` at `0x180205c16`
- `GDI32!SetROP2` at `0x180205b9e`
- `GDI32!SetROP2` at `0x180205c16`

## pseudocode

```c
void __fastcall PANE_HEADER_TRACKER::M_HeaderTrack(PANE_HEADER_TRACKER *this, int a2, int a3, int a4)
{
  HDC DC; // rax
  HDC v9; // rdi
  int v10; // esi
  int v11; // edx

  DC = GetDC(*((HWND *)this + 2));
  v9 = DC;
  if ( DC )
  {
    v10 = SetROP2(DC, 6);
    if ( v10 )
    {
      GetStockObject(7);
      if ( a3 )
        *((_DWORD *)this + 3) = a2 + *((_DWORD *)this + 1);
      MoveToEx(v9, *((_DWORD *)this + 3), 0, 0);
      LineTo(v9, *((_DWORD *)this + 3), *((_DWORD *)this + 2));
      if ( a4 )
      {
        v11 = a2 + *((_DWORD *)this + 1);
        *((_DWORD *)this + 3) = v11;
        MoveToEx(v9, v11, 0, 0);
        LineTo(v9, *((_DWORD *)this + 3), *((_DWORD *)this + 2));
      }
      SetROP2(v9, v10);
    }
    ReleaseDC(*((HWND *)this + 2), v9);
  }
}

```

## disassembly

```asm
0x180205b5c  mov     [rsp+arg_0], rbx
0x180205b61  mov     [rsp+arg_8], rbp
0x180205b66  mov     [rsp+arg_10], rsi
0x180205b6b  push    rdi
0x180205b6c  push    r14
0x180205b6e  push    r15
0x180205b70  sub     rsp, 20h
0x180205b74  mov     rbx, rcx
0x180205b77  mov     rcx, [rcx+10h]; hWnd
0x180205b7b  mov     r15d, r9d
0x180205b7e  mov     ebp, r8d
0x180205b81  mov     r14d, edx
0x180205b84  call    cs:__imp_GetDC
0x180205b8a  mov     rdi, rax
0x180205b8d  test    rax, rax
0x180205b90  jz      loc_180205C29
0x180205b96  mov     edx, 6; rop2
0x180205b9b  mov     rcx, rax; hdc
0x180205b9e  call    cs:__imp_SetROP2
0x180205ba4  mov     esi, eax
0x180205ba6  test    eax, eax
0x180205ba8  jz      short loc_180205C1C
0x180205baa  mov     ecx, 7; i
0x180205baf  call    cs:__imp_GetStockObject
0x180205bb5  test    ebp, ebp
0x180205bb7  jz      short loc_180205BC2
0x180205bb9  mov     edx, [rbx+4]
0x180205bbc  add     edx, r14d
0x180205bbf  mov     [rbx+0Ch], edx
0x180205bc2  mov     edx, [rbx+0Ch]; x
0x180205bc5  xor     r9d, r9d; lppt
0x180205bc8  xor     r8d, r8d; y
0x180205bcb  mov     rcx, rdi; hdc
0x180205bce  call    cs:__imp_MoveToEx
0x180205bd4  mov     r8d, [rbx+8]; y
0x180205bd8  mov     edx, [rbx+0Ch]; x
0x180205bdb  mov     rcx, rdi; hdc
0x180205bde  call    cs:__imp_LineTo
0x180205be4  test    r15d, r15d
0x180205be7  jz      short loc_180205C11
0x180205be9  mov     edx, [rbx+4]
0x180205bec  xor     r9d, r9d; lppt
0x180205bef  xor     r8d, r8d; y
0x180205bf2  add     edx, r14d; x
0x180205bf5  mov     rcx, rdi; hdc
0x180205bf8  mov     [rbx+0Ch], edx
0x180205bfb  call    cs:__imp_MoveToEx
0x180205c01  mov     r8d, [rbx+8]; y
0x180205c05  mov     edx, [rbx+0Ch]; x
0x180205c08  mov     rcx, rdi; hdc
0x180205c0b  call    cs:__imp_LineTo
0x180205c11  mov     edx, esi; rop2
0x180205c13  mov     rcx, rdi; hdc
0x180205c16  call    cs:__imp_SetROP2
0x180205c1c  mov     rcx, [rbx+10h]; hWnd
0x180205c20  mov     rdx, rdi; hDC
0x180205c23  call    cs:__imp_ReleaseDC
0x180205c29  mov     rbx, [rsp+38h+arg_0]
0x180205c2e  mov     rbp, [rsp+38h+arg_8]
0x180205c33  mov     rsi, [rsp+38h+arg_10]
0x180205c38  add     rsp, 20h
0x180205c3c  pop     r15
0x180205c3e  pop     r14
0x180205c40  pop     rdi
0x180205c41  retn
```
