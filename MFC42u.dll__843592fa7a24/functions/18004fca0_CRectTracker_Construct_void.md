# CRectTracker::Construct(void)

- ea: `0x18004fca0`
- end: `0x18004fecf`
- name: `?Construct@CRectTracker@@IEAAXXZ`
- size: `559`
- prototype: `void __fastcall(CRectTracker *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18004fb10`
- `0x1800b4ca0`

## callees

- `0x1800087b0`
- `0x180016330`
- `0x180017020`
- `0x18004fca0`
- `0x18005d6f0`
- `0x1800d1fe0`

## import_xrefs

- `KERNEL32!GetProfileIntW` at `0x18004fe5f`
- `KERNEL32!GetProfileIntW` at `0x18004fe5f`
- `USER32!SetRectEmpty` at `0x18004fe9b`
- `USER32!SetRectEmpty` at `0x18004fe9b`
- `USER32!LoadCursorW` at `0x18004fda5`
- `USER32!LoadCursorW` at `0x18004fdba`
- `USER32!LoadCursorW` at `0x18004fdea`
- `USER32!LoadCursorW` at `0x18004fdff`
- `USER32!LoadCursorW` at `0x18004fe29`
- `USER32!LoadCursorW` at `0x18004fe3e`
- `USER32!LoadCursorW` at `0x18004fda5`
- `USER32!LoadCursorW` at `0x18004fdba`
- `USER32!LoadCursorW` at `0x18004fdea`
- `USER32!LoadCursorW` at `0x18004fdff`
- `USER32!LoadCursorW` at `0x18004fe29`
- `USER32!LoadCursorW` at `0x18004fe3e`
- `GDI32!CreatePen` at `0x18004fd6b`
- `GDI32!CreatePen` at `0x18004fd6b`
- `GDI32!CreatePatternBrush` at `0x18004fd29`
- `GDI32!CreatePatternBrush` at `0x18004fd29`
- `GDI32!CreateBitmap` at `0x18004fd18`
- `GDI32!CreateBitmap` at `0x18004fd18`
- `GDI32!DeleteObject` at `0x18004fd39`
- `GDI32!DeleteObject` at `0x18004fd39`

## pseudocode

```c
void __fastcall CRectTracker::Construct(CRectTracker *this)
{
  __int16 v2; // cx
  __int64 i; // rax
  HBITMAP Bitmap; // rax
  HBITMAP v5; // rdi
  HINSTANCE ResourceHandle; // rdi
  __int64 j; // rcx
  __int64 k; // rcx
  int v9; // eax
  _WORD Bits[8]; // [rsp+30h] [rbp-28h] BYREF

  AfxLockGlobals(5);
  if ( !dword_1801320AC )
  {
    if ( !_afxHatchBrush )
    {
      v2 = 4369;
      for ( i = 0; i != 4; ++i )
      {
        Bits[i] = v2;
        Bits[i + 4] = v2;
        v2 *= 2;
      }
      Bitmap = CreateBitmap(8, 8, 1u, 1u, Bits);
      v5 = Bitmap;
      if ( !Bitmap || (_afxHatchBrush = CreatePatternBrush(Bitmap), DeleteObject(v5), !_afxHatchBrush) )
      {
        AfxUnlockGlobals(5);
        AfxThrowResourceException();
      }
    }
    if ( !_afxBlackDottedPen )
    {
      _afxBlackDottedPen = CreatePen(2, 0, 0);
      if ( !_afxBlackDottedPen )
      {
        AfxUnlockGlobals(5);
        AfxThrowResourceException();
      }
    }
    ResourceHandle = AfxFindResourceHandle((LPCWSTR)0x790B, (LPCWSTR)0xC);
    _afxCursors = (HICON near *)LoadCursorW(ResourceHandle, (LPCWSTR)0x7907);
    qword_180131C98 = (__int64)LoadCursorW(ResourceHandle, (LPCWSTR)0x7908);
    for ( j = 0; j != 2; ++j )
      (&_afxCursors)[j + 2] = (&_afxCursors)[j];
    qword_180131CB0 = (__int64)LoadCursorW(ResourceHandle, (LPCWSTR)0x7909);
    qword_180131CB8 = (__int64)LoadCursorW(ResourceHandle, (LPCWSTR)0x790A);
    for ( k = 0; k != 2; ++k )
      (&_afxCursors)[k + 6] = (&_afxCursors)[k + 4];
    qword_180131CD0 = (__int64)LoadCursorW(ResourceHandle, (LPCWSTR)0x790B);
    qword_180131CD8 = (__int64)LoadCursorW(ResourceHandle, (LPCWSTR)0x790C);
    _afxHandleSize = GetProfileIntW(L"windows", L"oleinplaceborderwidth", 4);
    dword_1801320AC = 1;
  }
  AfxUnlockGlobals(5);
  v9 = _afxHandleSize;
  *((_DWORD *)this + 9) = _afxHandleSize;
  v9 *= 2;
  *((_DWORD *)this + 7) = v9;
  *((_DWORD *)this + 8) = v9;
  *((_DWORD *)this + 2) = 0;
  SetRectEmpty((LPRECT)((char *)this + 44));
  *(_QWORD *)((char *)this + 60) = 0;
  *(_QWORD *)((char *)this + 68) = 0;
}

```

## disassembly

```asm
0x18004fca0  mov     [rsp+arg_8], rbx
0x18004fca5  mov     [rsp+arg_10], rdi
0x18004fcaa  push    r15
0x18004fcac  sub     rsp, 50h
0x18004fcb0  mov     rax, cs:__security_cookie
0x18004fcb7  xor     rax, rsp
0x18004fcba  mov     [rsp+58h+var_18], rax
0x18004fcbf  mov     rbx, rcx
0x18004fcc2  mov     ecx, 5; int
0x18004fcc7  call    ?AfxLockGlobals@@YAXH@Z; AfxLockGlobals(int)
0x18004fccc  cmp     cs:dword_1801320AC, 0
0x18004fcd3  jnz     loc_18004FE75
0x18004fcd9  cmp     cs:?_afxHatchBrush@@3PEAUHBRUSH__@@EA, 0; HBRUSH__ * _afxHatchBrush
0x18004fce1  jnz     short loc_18004FD59
0x18004fce3  mov     ecx, 1111h
0x18004fce8  xor     eax, eax
0x18004fcea  mov     [rsp+rax*2+58h+Bits], cx
0x18004fcef  mov     [rsp+rax*2+58h+var_20], cx
0x18004fcf4  add     cx, cx
0x18004fcf7  inc     rax
0x18004fcfa  cmp     rax, 4
0x18004fcfe  jnz     short loc_18004FCEA
0x18004fd00  mov     ecx, 8; nWidth
0x18004fd05  lea     rax, [rsp+58h+Bits]
0x18004fd0a  mov     edx, ecx; nHeight
0x18004fd0c  mov     [rsp+58h+lpBits], rax; lpBits
0x18004fd11  lea     r9d, [rcx-7]; nBitCount
0x18004fd15  mov     r8d, r9d; nPlanes
0x18004fd18  call    cs:__imp_CreateBitmap
0x18004fd1e  mov     rdi, rax
0x18004fd21  test    rax, rax
0x18004fd24  jz      short loc_18004FD49
0x18004fd26  mov     rcx, rax; hbm
0x18004fd29  call    cs:__imp_CreatePatternBrush
0x18004fd2f  mov     rcx, rdi; ho
0x18004fd32  mov     cs:?_afxHatchBrush@@3PEAUHBRUSH__@@EA, rax; HBRUSH__ * _afxHatchBrush
0x18004fd39  call    cs:__imp_DeleteObject
0x18004fd3f  cmp     cs:?_afxHatchBrush@@3PEAUHBRUSH__@@EA, 0; HBRUSH__ * _afxHatchBrush
0x18004fd47  jnz     short loc_18004FD59
0x18004fd49  mov     ecx, 5; int
0x18004fd4e  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x18004fd53  call    ?AfxThrowResourceException@@YAXXZ; AfxThrowResourceException(void)
0x18004fd59  cmp     cs:?_afxBlackDottedPen@@3PEAUHPEN__@@EA, 0; HPEN__ * _afxBlackDottedPen
0x18004fd61  jnz     short loc_18004FD8B
0x18004fd63  xor     edx, edx; cWidth
0x18004fd65  xor     r8d, r8d; color
0x18004fd68  lea     ecx, [rdx+2]; iStyle
0x18004fd6b  call    cs:__imp_CreatePen
0x18004fd71  mov     cs:?_afxBlackDottedPen@@3PEAUHPEN__@@EA, rax; HPEN__ * _afxBlackDottedPen
0x18004fd78  test    rax, rax
0x18004fd7b  jnz     short loc_18004FD8B
0x18004fd7d  lea     ecx, [rax+5]; int
0x18004fd80  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x18004fd85  call    ?AfxThrowResourceException@@YAXXZ; AfxThrowResourceException(void)
0x18004fd8b  mov     edx, 0Ch; lpType
0x18004fd90  mov     ecx, 790Bh; lpName
0x18004fd95  call    ?AfxFindResourceHandle@@YAPEAUHINSTANCE__@@PEBG0@Z; AfxFindResourceHandle(ushort const *,ushort const *)
0x18004fd9a  mov     edx, 7907h; lpCursorName
0x18004fd9f  mov     rcx, rax; hInstance
0x18004fda2  mov     rdi, rax
0x18004fda5  call    cs:__imp_LoadCursorW
0x18004fdab  mov     edx, 7908h; lpCursorName
0x18004fdb0  mov     rcx, rdi; hInstance
0x18004fdb3  mov     cs:?_afxCursors@@3PAPEAUHICON__@@A, rax; HICON__ * near * _afxCursors
0x18004fdba  call    cs:__imp_LoadCursorW
0x18004fdc0  mov     cs:qword_180131C98, rax
0x18004fdc7  xor     ecx, ecx
0x18004fdc9  lea     r15, ?_afxCursors@@3PAPEAUHICON__@@A; HICON__ * near * _afxCursors
0x18004fdd0  mov     rax, [r15+rcx*8]
0x18004fdd4  mov     [r15+rcx*8+10h], rax
0x18004fdd9  inc     rcx
0x18004fddc  cmp     rcx, 2
0x18004fde0  jnz     short loc_18004FDD0
0x18004fde2  mov     edx, 7909h; lpCursorName
0x18004fde7  mov     rcx, rdi; hInstance
0x18004fdea  call    cs:__imp_LoadCursorW
0x18004fdf0  mov     edx, 790Ah; lpCursorName
0x18004fdf5  mov     rcx, rdi; hInstance
0x18004fdf8  mov     cs:qword_180131CB0, rax
0x18004fdff  call    cs:__imp_LoadCursorW
0x18004fe05  mov     cs:qword_180131CB8, rax
0x18004fe0c  xor     ecx, ecx
0x18004fe0e  mov     rax, [r15+rcx*8+20h]
0x18004fe13  mov     [r15+rcx*8+30h], rax
0x18004fe18  inc     rcx
0x18004fe1b  cmp     rcx, 2
0x18004fe1f  jnz     short loc_18004FE0E
0x18004fe21  mov     edx, 790Bh; lpCursorName
0x18004fe26  mov     rcx, rdi; hInstance
0x18004fe29  call    cs:__imp_LoadCursorW
0x18004fe2f  mov     edx, 790Ch; lpCursorName
0x18004fe34  mov     rcx, rdi; hInstance
0x18004fe37  mov     cs:qword_180131CD0, rax
0x18004fe3e  call    cs:__imp_LoadCursorW
0x18004fe44  mov     r8d, 4; nDefault
0x18004fe4a  lea     rdx, aOleinplacebord; "oleinplaceborderwidth"
0x18004fe51  lea     rcx, aWindows; "windows"
0x18004fe58  mov     cs:qword_180131CD8, rax
0x18004fe5f  call    cs:__imp_GetProfileIntW
0x18004fe65  mov     cs:?_afxHandleSize@@3HA, eax; int _afxHandleSize
0x18004fe6b  mov     cs:dword_1801320AC, 1
0x18004fe75  mov     ecx, 5; int
0x18004fe7a  call    ?AfxUnlockGlobals@@YAXH@Z; AfxUnlockGlobals(int)
0x18004fe7f  mov     eax, cs:?_afxHandleSize@@3HA; int _afxHandleSize
0x18004fe85  lea     rcx, [rbx+2Ch]; lprc
0x18004fe89  mov     [rbx+24h], eax
0x18004fe8c  add     eax, eax
0x18004fe8e  mov     [rbx+1Ch], eax
0x18004fe91  mov     [rbx+20h], eax
0x18004fe94  mov     dword ptr [rbx+8], 0
0x18004fe9b  call    cs:__imp_SetRectEmpty
0x18004fea1  mov     qword ptr [rbx+3Ch], 0
0x18004fea9  mov     qword ptr [rbx+44h], 0
0x18004feb1  mov     rcx, [rsp+58h+var_18]
0x18004feb6  xor     rcx, rsp; StackCookie
0x18004feb9  call    __security_check_cookie
0x18004febe  mov     rbx, [rsp+58h+arg_8]
0x18004fec3  mov     rdi, [rsp+58h+arg_10]
0x18004fec8  add     rsp, 50h
0x18004fecc  pop     r15
0x18004fece  retn
```
